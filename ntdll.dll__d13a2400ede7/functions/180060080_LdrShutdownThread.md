# LdrShutdownThread

- ea: `0x180060080`
- end: `0x18006039c`
- name: `LdrShutdownThread`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x18005fd30`

## callees

- `0x18001861c`
- `0x18001a0d0`
- `0x18001a420`
- `0x1800254d0`
- `0x1800259ec`
- `0x18005f03c`
- `0x18005f0c0`
- `0x18005f240`
- `0x180060080`
- `0x180060f00`
- `0x180060f70`
- `0x1800694f0`
- `0x180069950`
- `0x18006d6e8`
- `0x18006d980`
- `0x18006ffa0`
- `0x180070490`
- `0x1800e7a40`

## pseudocode

```c
__int64 LdrShutdownThread()
{
  struct _TEB *v0; // rbx
  _PEB *ProcessEnvironmentBlock; // r12
  void *FlsData; // r14
  $D8066A78EF7494050A826D52E79FBB12 *v3; // rsi
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
0x180060080  mov     [rsp+arg_10], rbx
0x180060085  mov     [rsp+arg_18], rsi
0x18006008a  push    rdi
0x18006008b  push    r12
0x18006008d  push    r13
0x18006008f  push    r14
0x180060091  push    r15
0x180060093  sub     rsp, 0D0h
0x18006009a  mov     rbx, gs:30h
0x1800600a3  mov     r12, [rbx+60h]
0x1800600a7  mov     [rsp+0F8h+arg_8], r12
0x1800600af  mov     r14, [rbx+17C8h]
0x1800600b6  xor     edi, edi
0x1800600b8  test    r14, r14
0x1800600bb  jz      short loc_1800600D0
0x1800600bd  lea     r8d, [rdi+1]
0x1800600c1  mov     rdx, r14
0x1800600c4  lea     rcx, RtlpFlsContext
0x1800600cb  call    RtlpFlsDataCleanup
0x1800600d0  mov     rax, gs:30h
0x1800600d9  test    byte ptr [rax+17EEh], 8
0x1800600e0  jnz     loc_180060342
0x1800600e6  lea     rsi, [rbx+17EEh]
0x1800600ed  mov     eax, 2000h
0x1800600f2  test    [rsi], ax
0x1800600f5  jnz     loc_18006029B
0x1800600fb  mov     rax, gs:30h
0x180060104  mov     r13d, 1000h
0x18006010a  and     r13w, [rax+17EEh]
0x180060112  setnz   [rsp+0F8h+arg_0]
0x18006011a  test    r13w, r13w
0x18006011e  jnz     short loc_180060127
0x180060120  xor     ecx, ecx
0x180060122  call    LdrpDrainWorkQueue
0x180060127  call    LdrpAcquireLoaderLock
0x18006012c  nop
0x18006012d  mov     r15, cs:qword_1801CA8F8
0x180060134  lea     rax, qword_1801CA8F0
0x18006013b  cmp     r15, rax
0x18006013e  jz      loc_18006020C
0x180060144  lea     rdi, [r15-20h]
0x180060148  mov     [rsp+0F8h+var_38], rdi
0x180060150  mov     r15, [r15+8]
0x180060154  mov     rax, [rdi+30h]
0x180060158  cmp     [r12+10h], rax
0x18006015d  jz      loc_180060207
0x180060163  mov     eax, [rdi+68h]
0x180060166  bt      eax, 12h
0x18006016a  jb      loc_180060207
0x180060170  mov     r12, [rdi+38h]
0x180060174  test    r12, r12
0x180060177  jz      loc_1800601FF
0x18006017d  and     eax, 80004h
0x180060182  cmp     eax, 80004h
0x180060187  jnz     short loc_1800601FF
0x180060189  mov     [rsp+0F8h+var_30], r12
0x180060191  mov     [rsp+0F8h+var_D8], 48h ; 'H'
0x18006019a  mov     [rsp+0F8h+var_D0], 1
0x1800601a3  xorps   xmm0, xmm0
0x1800601a6  xor     eax, eax
0x1800601a8  movups  [rsp+0F8h+var_C8], xmm0
0x1800601ad  movups  [rsp+0F8h+var_B8], xmm0
0x1800601b2  movups  [rsp+0F8h+var_A8], xmm0
0x1800601b7  mov     [rsp+0F8h+var_98], rax
0x1800601bc  mov     rdx, [rdi+88h]
0x1800601c3  lea     rcx, [rsp+0F8h+var_D8]
0x1800601c8  call    RtlActivateActivationContextUnsafeFast
0x1800601cd  nop
0x1800601ce  xor     eax, eax
0x1800601d0  cmp     [rdi+6Eh], ax
0x1800601d4  jz      short loc_1800601E1
0x1800601d6  mov     rdx, rdi
0x1800601d9  lea     ecx, [rax+3]
0x1800601dc  call    LdrpCallTlsInitializers
0x1800601e1  xor     r9d, r9d
0x1800601e4  lea     r8d, [r9+3]
0x1800601e8  mov     rdx, [rdi+30h]
0x1800601ec  mov     rcx, r12
0x1800601ef  call    LdrpCallInitRoutine
0x1800601f4  nop
0x1800601f5  lea     rcx, [rsp+0F8h+var_D8]
0x1800601fa  call    RtlDeactivateActivationContextUnsafeFast
0x1800601ff  mov     r12, [rsp+0F8h+arg_8]
0x180060207  jmp     loc_180060134
0x18006020c  mov     rdx, cs:LdrpImageEntry
0x180060213  xor     edi, edi
0x180060215  cmp     [rdx+6Eh], di
0x180060219  jz      short loc_18006027F
0x18006021b  mov     [rsp+0F8h+var_88], 48h ; 'H'
0x180060224  mov     [rsp+0F8h+var_80], 1
0x18006022d  xorps   xmm0, xmm0
0x180060230  xor     eax, eax
0x180060232  movups  [rsp+0F8h+var_78], xmm0
0x18006023a  movups  [rsp+0F8h+var_68], xmm0
0x180060242  movups  [rsp+0F8h+var_58], xmm0
0x18006024a  mov     [rsp+0F8h+var_48], rax
0x180060252  mov     rdx, [rdx+88h]
0x180060259  lea     rcx, [rsp+0F8h+var_88]
0x18006025e  call    RtlActivateActivationContextUnsafeFast
0x180060263  nop
0x180060264  mov     rdx, cs:LdrpImageEntry
0x18006026b  lea     ecx, [rdi+3]
0x18006026e  call    LdrpCallTlsInitializers
0x180060273  nop
0x180060274  lea     rcx, [rsp+0F8h+var_88]
0x180060279  call    RtlDeactivateActivationContextUnsafeFast
0x18006027e  nop
0x18006027f  xor     r8d, r8d
0x180060282  lea     edx, [r8+13h]
0x180060286  call    LdrpReleaseLoaderLock
0x18006028b  test    r13w, r13w
0x18006028f  jnz     short loc_180060296
0x180060291  call    LdrpDropLastInProgressCount
0x180060296  call    LdrpFreeTls
0x18006029b  test    r14, r14
0x18006029e  jz      short loc_1800602BC
0x1800602a0  mov     [rbx+17C8h], rdi
0x1800602a7  mov     r8d, 2
0x1800602ad  mov     rdx, r14
0x1800602b0  lea     rcx, RtlpFlsContext
0x1800602b7  call    RtlpFlsDataCleanup
0x1800602bc  test    byte ptr [rsi], 4
0x1800602bf  jnz     loc_18006037B
0x1800602c5  call    RtlFreeThreadActivationContextStack
0x1800602ca  mov     eax, 400h
0x1800602cf  test    [rsi], ax
0x1800602d2  jnz     loc_180060364
0x1800602d8  mov     ecx, 3
0x1800602dd  call    RtlpHpEnvFlsCleanup
0x1800602e2  mov     rdi, [rbx+1780h]
0x1800602e9  xor     eax, eax
0x1800602eb  test    rdi, rdi
0x1800602ee  jz      short loc_180060324
0x1800602f0  mov     [rbx+1780h], rax
0x1800602f7  lea     rcx, FastPebLock
0x1800602fe  call    RtlEnterCriticalSection
0x180060303  lea     rcx, FastPebLock
0x18006030a  call    RtlLeaveCriticalSection
0x18006030f  mov     rcx, gs:60h
0x180060318  mov     rdx, rdi
0x18006031b  mov     rcx, [rcx+30h]
0x18006031f  call    RtlpFreeHeapMetadata
0x180060324  lea     r11, [rsp+0F8h+var_28]
0x18006032c  mov     rbx, [r11+40h]
0x180060330  mov     rsi, [r11+48h]
0x180060334  mov     rsp, r11
0x180060337  pop     r15
0x180060339  pop     r14
0x18006033b  pop     r13
0x18006033d  pop     r12
0x18006033f  pop     rdi
0x180060340  retn
0x180060342  mov     rax, gs:30h
0x18006034b  test    byte ptr [rax+17EEh], 20h
0x180060352  jnz     loc_1800600E6
0x180060358  lea     rsi, [rbx+17EEh]
0x18006035f  jmp     loc_18006029B
0x180060364  cmp     cs:LdrInitState, 3
0x18006036b  jnz     loc_1800602D8
0x180060371  call    TpTrimPools
0x180060376  jmp     loc_1800602D8
0x18006037b  mov     r8, [rbx+20h]
0x18006037f  mov     [rbx+20h], rdi
0x180060383  mov     rcx, gs:60h
0x18006038c  xor     edx, edx
0x18006038e  mov     rcx, [rcx+30h]
0x180060392  call    RtlFreeHeap_0
0x180060397  jmp     loc_1800602C5
0x18016685f  push    rbp
0x180166861  sub     rsp, 20h
0x180166865  mov     rbp, rdx
0x180166868  lea     rcx, [rbp+20h]
0x18016686c  call    RtlDeactivateActivationContextUnsafeFast
0x180166871  nop
0x180166872  add     rsp, 20h
0x180166876  pop     rbp
0x180166877  retn
0x180166879  push    rbp
0x18016687b  sub     rsp, 20h
0x18016687f  mov     rbp, rdx
0x180166882  lea     rcx, [rbp+70h]
0x180166886  call    RtlDeactivateActivationContextUnsafeFast
0x18016688b  nop
0x18016688c  add     rsp, 20h
0x180166890  pop     rbp
0x180166891  retn
0x180166893  push    rbp
0x180166895  sub     rsp, 20h
0x180166899  mov     rbp, rdx
0x18016689c  xor     r8d, r8d
0x18016689f  lea     edx, [r8+13h]
0x1801668a3  call    LdrpReleaseLoaderLock
0x1801668a8  cmp     byte ptr [rbp+100h], 0
0x1801668af  jnz     short loc_1801668B7
0x1801668b1  call    LdrpDropLastInProgressCount
0x1801668b6  nop
0x1801668b7  add     rsp, 20h
0x1801668bb  pop     rbp
0x1801668bc  retn
```
