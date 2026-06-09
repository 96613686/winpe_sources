# LdrShutdownThread

- ea: `0x180043490`
- end: `0x1800437ac`
- name: `LdrShutdownThread`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x180043140`

## callees

- `0x18001861c`
- `0x18001a0d0`
- `0x18001a420`
- `0x1800254e0`
- `0x1800259fc`
- `0x18004244c`
- `0x1800424d0`
- `0x180042650`
- `0x180043490`
- `0x180044310`
- `0x180044380`
- `0x18004c8f0`
- `0x18004cd50`
- `0x180050d08`
- `0x180050fa0`
- `0x1800535c0`
- `0x180053ab0`
- `0x1800e76c0`

## pseudocode

```c
__int64 LdrShutdownThread()
{
  struct _TEB *v0; // rbx
  _PEB *ProcessEnvironmentBlock; // r12
  void *FlsData; // r14
  $784A3C5A756B5433E5F1114C8EC150B5 *v3; // rsi
  __int16 v4; // r13
  __int64 v5; // rcx
  __int64 *v6; // r15
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // r12
  void **TlsExpansionSlots; // rdi
  __int64 result; // rax
  void *FiberData; // r8
  _QWORD v13[2]; // [rsp+20h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-C8h]
  __int128 v15; // [rsp+40h] [rbp-B8h]
  __int128 v16; // [rsp+50h] [rbp-A8h]
  __int64 v17; // [rsp+60h] [rbp-98h]
  _QWORD v18[2]; // [rsp+70h] [rbp-88h] BYREF
  __int128 v19; // [rsp+80h] [rbp-78h]
  __int128 v20; // [rsp+90h] [rbp-68h]
  __int128 v21; // [rsp+A0h] [rbp-58h]
  __int64 v22; // [rsp+B0h] [rbp-48h]
  __int64 v23; // [rsp+C0h] [rbp-38h]
  __int64 v24; // [rsp+C8h] [rbp-30h]
  _PEB *v25; // [rsp+108h] [rbp+10h]

  v0 = NtCurrentTeb();
  ProcessEnvironmentBlock = v0->ProcessEnvironmentBlock;
  v25 = ProcessEnvironmentBlock;
  FlsData = v0->FlsData;
  if ( FlsData )
    RtlpFlsDataCleanup(&RtlpFlsContext, v0->FlsData, 1);
  if ( (NtCurrentTeb()->SameTebFlags & 8) == 0 || (NtCurrentTeb()->SameTebFlags & 0x20) != 0 )
  {
    v3 = &v0->6126;
    if ( (v0->SameTebFlags & 0x2000) == 0 )
    {
      v4 = NtCurrentTeb()->SameTebFlags & 0x1000;
      if ( !v4 )
        LdrpDrainWorkQueue(0);
      LdrpAcquireLoaderLock();
      v6 = (__int64 *)qword_1801CA8F8;
      while ( v6 != &qword_1801CA8F0 )
      {
        v7 = (__int64)(v6 - 4);
        v23 = v7;
        v6 = (__int64 *)v6[1];
        if ( ProcessEnvironmentBlock->ImageBaseAddress != *(void **)(v7 + 48) )
        {
          v8 = *(_DWORD *)(v7 + 104);
          if ( (v8 & 0x40000) == 0 )
          {
            v9 = *(_QWORD *)(v7 + 56);
            if ( v9 && (v8 & 0x80004) == 0x80004 )
            {
              v24 = *(_QWORD *)(v7 + 56);
              v13[0] = 72;
              v13[1] = 1;
              v14 = 0;
              v15 = 0;
              v16 = 0;
              v17 = 0;
              RtlActivateActivationContextUnsafeFast(v13, *(_QWORD *)(v7 + 136));
              if ( *(_WORD *)(v7 + 110) )
                LdrpCallTlsInitializers(3u, v7);
              LdrpCallInitRoutine(v9, *(_QWORD *)(v7 + 48), 3, 0);
              RtlDeactivateActivationContextUnsafeFast(v13);
            }
            ProcessEnvironmentBlock = v25;
          }
        }
      }
      if ( *(_WORD *)(LdrpImageEntry + 110) )
      {
        v18[0] = 72;
        v18[1] = 1;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v22 = 0;
        RtlActivateActivationContextUnsafeFast(v18, *(_QWORD *)(LdrpImageEntry + 136));
        LdrpCallTlsInitializers(3u, LdrpImageEntry);
        RtlDeactivateActivationContextUnsafeFast(v18);
      }
      LdrpReleaseLoaderLock(v5, 19, 0);
      if ( !v4 )
        LdrpDropLastInProgressCount();
      LdrpFreeTls();
    }
  }
  else
  {
    v3 = &v0->6126;
  }
  if ( FlsData )
  {
    v0->FlsData = 0;
    RtlpFlsDataCleanup(&RtlpFlsContext, FlsData, 2);
  }
  if ( (v3->SameTebFlags & 4) != 0 )
  {
    FiberData = v0->NtTib.FiberData;
    v0->NtTib.FiberData = 0;
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, FiberData);
  }
  RtlFreeThreadActivationContextStack();
  if ( (v3->SameTebFlags & 0x400) != 0 && LdrInitState == 3 )
    TpTrimPools();
  RtlpHpEnvFlsCleanup(3);
  TlsExpansionSlots = v0->TlsExpansionSlots;
  result = 0;
  if ( TlsExpansionSlots )
  {
    v0->TlsExpansionSlots = 0;
    RtlEnterCriticalSection(&FastPebLock);
    RtlLeaveCriticalSection(&FastPebLock);
    return RtlpFreeHeapMetadata(NtCurrentPeb()->ProcessHeap, TlsExpansionSlots);
  }
  return result;
}

```

## disassembly

```asm
0x180043490  mov     [rsp+arg_10], rbx
0x180043495  mov     [rsp+arg_18], rsi
0x18004349a  push    rdi
0x18004349b  push    r12
0x18004349d  push    r13
0x18004349f  push    r14
0x1800434a1  push    r15
0x1800434a3  sub     rsp, 0D0h
0x1800434aa  mov     rbx, gs:30h
0x1800434b3  mov     r12, [rbx+60h]
0x1800434b7  mov     [rsp+0F8h+arg_8], r12
0x1800434bf  mov     r14, [rbx+17C8h]
0x1800434c6  xor     edi, edi
0x1800434c8  test    r14, r14
0x1800434cb  jz      short loc_1800434E0
0x1800434cd  lea     r8d, [rdi+1]
0x1800434d1  mov     rdx, r14
0x1800434d4  lea     rcx, RtlpFlsContext
0x1800434db  call    RtlpFlsDataCleanup
0x1800434e0  mov     rax, gs:30h
0x1800434e9  test    byte ptr [rax+17EEh], 8
0x1800434f0  jnz     loc_180043752
0x1800434f6  lea     rsi, [rbx+17EEh]
0x1800434fd  mov     eax, 2000h
0x180043502  test    [rsi], ax
0x180043505  jnz     loc_1800436AB
0x18004350b  mov     rax, gs:30h
0x180043514  mov     r13d, 1000h
0x18004351a  and     r13w, [rax+17EEh]
0x180043522  setnz   [rsp+0F8h+arg_0]
0x18004352a  test    r13w, r13w
0x18004352e  jnz     short loc_180043537
0x180043530  xor     ecx, ecx
0x180043532  call    LdrpDrainWorkQueue
0x180043537  call    LdrpAcquireLoaderLock
0x18004353c  nop
0x18004353d  mov     r15, cs:qword_1801CA8F8
0x180043544  lea     rax, qword_1801CA8F0
0x18004354b  cmp     r15, rax
0x18004354e  jz      loc_18004361C
0x180043554  lea     rdi, [r15-20h]
0x180043558  mov     [rsp+0F8h+var_38], rdi
0x180043560  mov     r15, [r15+8]
0x180043564  mov     rax, [rdi+30h]
0x180043568  cmp     [r12+10h], rax
0x18004356d  jz      loc_180043617
0x180043573  mov     eax, [rdi+68h]
0x180043576  bt      eax, 12h
0x18004357a  jb      loc_180043617
0x180043580  mov     r12, [rdi+38h]
0x180043584  test    r12, r12
0x180043587  jz      loc_18004360F
0x18004358d  and     eax, 80004h
0x180043592  cmp     eax, 80004h
0x180043597  jnz     short loc_18004360F
0x180043599  mov     [rsp+0F8h+var_30], r12
0x1800435a1  mov     [rsp+0F8h+var_D8], 48h ; 'H'
0x1800435aa  mov     [rsp+0F8h+var_D0], 1
0x1800435b3  xorps   xmm0, xmm0
0x1800435b6  xor     eax, eax
0x1800435b8  movups  [rsp+0F8h+var_C8], xmm0
0x1800435bd  movups  [rsp+0F8h+var_B8], xmm0
0x1800435c2  movups  [rsp+0F8h+var_A8], xmm0
0x1800435c7  mov     [rsp+0F8h+var_98], rax
0x1800435cc  mov     rdx, [rdi+88h]
0x1800435d3  lea     rcx, [rsp+0F8h+var_D8]
0x1800435d8  call    RtlActivateActivationContextUnsafeFast
0x1800435dd  nop
0x1800435de  xor     eax, eax
0x1800435e0  cmp     [rdi+6Eh], ax
0x1800435e4  jz      short loc_1800435F1
0x1800435e6  mov     rdx, rdi
0x1800435e9  lea     ecx, [rax+3]
0x1800435ec  call    LdrpCallTlsInitializers
0x1800435f1  xor     r9d, r9d
0x1800435f4  lea     r8d, [r9+3]
0x1800435f8  mov     rdx, [rdi+30h]
0x1800435fc  mov     rcx, r12
0x1800435ff  call    LdrpCallInitRoutine
0x180043604  nop
0x180043605  lea     rcx, [rsp+0F8h+var_D8]
0x18004360a  call    RtlDeactivateActivationContextUnsafeFast
0x18004360f  mov     r12, [rsp+0F8h+arg_8]
0x180043617  jmp     loc_180043544
0x18004361c  mov     rdx, cs:LdrpImageEntry
0x180043623  xor     edi, edi
0x180043625  cmp     [rdx+6Eh], di
0x180043629  jz      short loc_18004368F
0x18004362b  mov     [rsp+0F8h+var_88], 48h ; 'H'
0x180043634  mov     [rsp+0F8h+var_80], 1
0x18004363d  xorps   xmm0, xmm0
0x180043640  xor     eax, eax
0x180043642  movups  [rsp+0F8h+var_78], xmm0
0x18004364a  movups  [rsp+0F8h+var_68], xmm0
0x180043652  movups  [rsp+0F8h+var_58], xmm0
0x18004365a  mov     [rsp+0F8h+var_48], rax
0x180043662  mov     rdx, [rdx+88h]
0x180043669  lea     rcx, [rsp+0F8h+var_88]
0x18004366e  call    RtlActivateActivationContextUnsafeFast
0x180043673  nop
0x180043674  mov     rdx, cs:LdrpImageEntry
0x18004367b  lea     ecx, [rdi+3]
0x18004367e  call    LdrpCallTlsInitializers
0x180043683  nop
0x180043684  lea     rcx, [rsp+0F8h+var_88]
0x180043689  call    RtlDeactivateActivationContextUnsafeFast
0x18004368e  nop
0x18004368f  xor     r8d, r8d
0x180043692  lea     edx, [r8+13h]
0x180043696  call    LdrpReleaseLoaderLock
0x18004369b  test    r13w, r13w
0x18004369f  jnz     short loc_1800436A6
0x1800436a1  call    LdrpDropLastInProgressCount
0x1800436a6  call    LdrpFreeTls
0x1800436ab  test    r14, r14
0x1800436ae  jz      short loc_1800436CC
0x1800436b0  mov     [rbx+17C8h], rdi
0x1800436b7  mov     r8d, 2
0x1800436bd  mov     rdx, r14
0x1800436c0  lea     rcx, RtlpFlsContext
0x1800436c7  call    RtlpFlsDataCleanup
0x1800436cc  test    byte ptr [rsi], 4
0x1800436cf  jnz     loc_18004378B
0x1800436d5  call    RtlFreeThreadActivationContextStack
0x1800436da  mov     eax, 400h
0x1800436df  test    [rsi], ax
0x1800436e2  jnz     loc_180043774
0x1800436e8  mov     ecx, 3
0x1800436ed  call    RtlpHpEnvFlsCleanup
0x1800436f2  mov     rdi, [rbx+1780h]
0x1800436f9  xor     eax, eax
0x1800436fb  test    rdi, rdi
0x1800436fe  jz      short loc_180043734
0x180043700  mov     [rbx+1780h], rax
0x180043707  lea     rcx, FastPebLock
0x18004370e  call    RtlEnterCriticalSection
0x180043713  lea     rcx, FastPebLock
0x18004371a  call    RtlLeaveCriticalSection
0x18004371f  mov     rcx, gs:60h
0x180043728  mov     rdx, rdi
0x18004372b  mov     rcx, [rcx+30h]
0x18004372f  call    RtlpFreeHeapMetadata
0x180043734  lea     r11, [rsp+0F8h+var_28]
0x18004373c  mov     rbx, [r11+40h]
0x180043740  mov     rsi, [r11+48h]
0x180043744  mov     rsp, r11
0x180043747  pop     r15
0x180043749  pop     r14
0x18004374b  pop     r13
0x18004374d  pop     r12
0x18004374f  pop     rdi
0x180043750  retn
0x180043752  mov     rax, gs:30h
0x18004375b  test    byte ptr [rax+17EEh], 20h
0x180043762  jnz     loc_1800434F6
0x180043768  lea     rsi, [rbx+17EEh]
0x18004376f  jmp     loc_1800436AB
0x180043774  cmp     cs:LdrInitState, 3
0x18004377b  jnz     loc_1800436E8
0x180043781  call    TpTrimPools
0x180043786  jmp     loc_1800436E8
0x18004378b  mov     r8, [rbx+20h]
0x18004378f  mov     [rbx+20h], rdi
0x180043793  mov     rcx, gs:60h
0x18004379c  xor     edx, edx
0x18004379e  mov     rcx, [rcx+30h]
0x1800437a2  call    RtlFreeHeap_0
0x1800437a7  jmp     loc_1800436D5
0x180165d4f  push    rbp
0x180165d51  sub     rsp, 20h
0x180165d55  mov     rbp, rdx
0x180165d58  lea     rcx, [rbp+20h]
0x180165d5c  call    RtlDeactivateActivationContextUnsafeFast
0x180165d61  nop
0x180165d62  add     rsp, 20h
0x180165d66  pop     rbp
0x180165d67  retn
0x180165d69  push    rbp
0x180165d6b  sub     rsp, 20h
0x180165d6f  mov     rbp, rdx
0x180165d72  lea     rcx, [rbp+70h]
0x180165d76  call    RtlDeactivateActivationContextUnsafeFast
0x180165d7b  nop
0x180165d7c  add     rsp, 20h
0x180165d80  pop     rbp
0x180165d81  retn
0x180165d83  push    rbp
0x180165d85  sub     rsp, 20h
0x180165d89  mov     rbp, rdx
0x180165d8c  xor     r8d, r8d
0x180165d8f  lea     edx, [r8+13h]
0x180165d93  call    LdrpReleaseLoaderLock
0x180165d98  cmp     byte ptr [rbp+100h], 0
0x180165d9f  jnz     short loc_180165DA7
0x180165da1  call    LdrpDropLastInProgressCount
0x180165da6  nop
0x180165da7  add     rsp, 20h
0x180165dab  pop     rbp
0x180165dac  retn
```
