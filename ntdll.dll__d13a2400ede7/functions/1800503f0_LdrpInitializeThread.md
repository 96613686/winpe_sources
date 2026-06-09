# LdrpInitializeThread

- ea: `0x1800503f0`
- end: `0x18005069a`
- name: `LdrpInitializeThread`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18004ff78`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x1800254d0`
- `0x1800259ec`
- `0x18004f8e4`
- `0x1800503f0`
- `0x18005f0fc`
- `0x1800694f0`
- `0x180069950`
- `0x18006d6e8`
- `0x18006d980`
- `0x180070370`
- `0x1800847b0`
- `0x18015f060`
- `0x18015f160`

## pseudocode

```c
__int64 __fastcall LdrpInitializeThread(__int64 a1)
{
  struct _TEB *v1; // rbx
  _PEB *ProcessEnvironmentBlock; // rsi
  __int64 result; // rax
  int Tls; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 i; // rbx
  __int64 v8; // rdi
  _QWORD v9[2]; // [rsp+20h] [rbp-D8h] BYREF
  __int128 v10; // [rsp+30h] [rbp-C8h]
  __int128 v11; // [rsp+40h] [rbp-B8h]
  __int128 v12; // [rsp+50h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-98h]
  _QWORD v14[2]; // [rsp+70h] [rbp-88h] BYREF
  __int128 v15; // [rsp+80h] [rbp-78h]
  __int128 v16; // [rsp+90h] [rbp-68h]
  __int128 v17; // [rsp+A0h] [rbp-58h]
  __int64 v18; // [rsp+B0h] [rbp-48h]
  __int64 v19; // [rsp+C0h] [rbp-38h]
  __int64 v20; // [rsp+C8h] [rbp-30h]
  __int64 v21; // [rsp+108h] [rbp+10h] BYREF

  v21 = 0;
  v1 = NtCurrentTeb();
  ProcessEnvironmentBlock = v1->ProcessEnvironmentBlock;
  if ( UseCOR && (v1->SameTebFlags & 0x400) != 0 )
    *(_QWORD *)(a1 + 128) = __ROR8__(LdrpCorExeMainRoutine, 64 - (MEMORY[0x7FFE0330] & 0x3Fu)) ^ MEMORY[0x7FFE0330];
  LdrpAcquireSchedulerSharedDataSlot(v1);
  RtlpInitializeThreadActivationContextStack(v1);
  if ( (NtCurrentTeb()->SameTebFlags & 8) == 0
    || (result = (__int64)NtCurrentTeb(), (*(_BYTE *)(result + 6126) & 0x20) != 0) )
  {
    result = 0x2000;
    if ( (v1->SameTebFlags & 0x2000) == 0 )
    {
      while ( 1 )
      {
        Tls = LdrpAllocateTls();
        v5 = Tls;
        if ( Tls != -1073741801 )
          break;
        v21 = -3000000;
        ZwDelayExecution(0, &v21);
      }
      if ( Tls < 0 )
      {
        ZwTerminateProcess(-1, (unsigned int)Tls);
        RtlRaiseStatus(v5);
      }
      LdrpDrainWorkQueue(0);
      LdrpAcquireLoaderLock();
      for ( i = qword_1801CA8D0; (__int64 *)i != &qword_1801CA8D0; i = *(_QWORD *)i )
      {
        v19 = i;
        v6 = *(unsigned int *)(*(_QWORD *)(i + 152) + 56LL);
        if ( (int)v6 >= 9
          && ProcessEnvironmentBlock->ImageBaseAddress != *(void **)(i + 48)
          && (*(_DWORD *)(i + 104) & 0x40000) == 0 )
        {
          v8 = *(_QWORD *)(i + 56);
          v20 = v8;
          if ( v8 )
          {
            if ( (*(_DWORD *)(i + 104) & 0x80000) != 0 && (*(_DWORD *)(i + 104) & 4) != 0 )
            {
              if ( byte_1801CA908 )
                goto LABEL_23;
              v9[0] = 72;
              v9[1] = 1;
              v10 = 0;
              v11 = 0;
              v12 = 0;
              v13 = 0;
              RtlActivateActivationContextUnsafeFast(v9, *(_QWORD *)(i + 136));
              if ( *(_WORD *)(i + 110) )
                LdrpCallTlsInitializers(2u, i);
              LdrpCallInitRoutine(v8, *(_QWORD *)(i + 48), 2, 0);
              RtlDeactivateActivationContextUnsafeFast(v9);
            }
          }
        }
      }
      if ( *(_WORD *)(LdrpImageEntry + 110) && !byte_1801CA908 )
      {
        v14[0] = 72;
        v14[1] = 1;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        v18 = 0;
        RtlActivateActivationContextUnsafeFast(v14, *(_QWORD *)(LdrpImageEntry + 136));
        LdrpCallTlsInitializers(2u, LdrpImageEntry);
        RtlDeactivateActivationContextUnsafeFast(v14);
      }
LABEL_23:
      LdrpReleaseLoaderLock(v6, 21, 0);
      return LdrpDropLastInProgressCount();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800503f0  mov     rax, rsp
0x1800503f3  push    rbx
0x1800503f4  push    rsi
0x1800503f5  push    rdi
0x1800503f6  push    r14
0x1800503f8  sub     rsp, 0D8h
0x1800503ff  mov     r8, rcx
0x180050402  xor     r14d, r14d
0x180050405  mov     [rax+10h], r14
0x180050409  mov     rbx, gs:30h
0x180050412  mov     rsi, [rbx+60h]
0x180050416  cmp     cs:UseCOR, r14b
0x18005041d  jnz     loc_18005061D
0x180050423  mov     rcx, rbx
0x180050426  call    LdrpAcquireSchedulerSharedDataSlot
0x18005042b  mov     rcx, rbx
0x18005042e  call    RtlpInitializeThreadActivationContextStack
0x180050433  mov     r9, gs:30h
0x18005043c  test    byte ptr [r9+17EEh], 8
0x180050444  jnz     loc_180050606
0x18005044a  mov     eax, 2000h
0x18005044f  test    [rbx+17EEh], ax
0x180050456  jnz     loc_1800505F8
0x18005045c  call    LdrpAllocateTls
0x180050461  test    eax, eax
0x180050463  mov     ebx, eax
0x180050465  js      loc_18005065B
0x18005046b  test    ebx, ebx
0x18005046d  js      loc_180050687
0x180050473  xor     ecx, ecx
0x180050475  call    LdrpDrainWorkQueue
0x18005047a  call    LdrpAcquireLoaderLock
0x18005047f  nop
0x180050480  mov     rbx, cs:qword_1801CA8D0
0x180050487  lea     rax, qword_1801CA8D0
0x18005048e  cmp     rbx, rax
0x180050491  jz      loc_18005056A
0x180050497  mov     [rsp+0F8h+var_38], rbx
0x18005049f  mov     rax, [rbx+98h]
0x1800504a6  mov     ecx, [rax+38h]
0x1800504a9  cmp     ecx, 9
0x1800504ac  jge     short loc_1800504B3
0x1800504ae  mov     rbx, [rbx]
0x1800504b1  jmp     short loc_180050487
0x1800504b3  mov     rax, [rbx+30h]
0x1800504b7  cmp     [rsi+10h], rax
0x1800504bb  jnz     short loc_1800504BF
0x1800504bd  jmp     short loc_1800504AE
0x1800504bf  mov     eax, [rbx+68h]
0x1800504c2  bt      eax, 12h
0x1800504c6  jb      short loc_1800504BD
0x1800504c8  mov     rdi, [rbx+38h]
0x1800504cc  mov     [rsp+0F8h+var_30], rdi
0x1800504d4  test    rdi, rdi
0x1800504d7  jz      short loc_1800504BD
0x1800504d9  mov     eax, [rbx+68h]
0x1800504dc  bt      eax, 13h
0x1800504e0  jnb     short loc_1800504BD
0x1800504e2  mov     eax, [rbx+68h]
0x1800504e5  test    al, 4
0x1800504e7  jz      short loc_1800504BD
0x1800504e9  cmp     cs:byte_1801CA908, r14b
0x1800504f0  jnz     loc_1800505E7
0x1800504f6  mov     [rsp+0F8h+var_D8], 48h ; 'H'
0x1800504ff  mov     [rsp+0F8h+var_D0], 1
0x180050508  xorps   xmm0, xmm0
0x18005050b  xor     eax, eax
0x18005050d  movups  [rsp+0F8h+var_C8], xmm0
0x180050512  movups  [rsp+0F8h+var_B8], xmm0
0x180050517  movups  [rsp+0F8h+var_A8], xmm0
0x18005051c  mov     [rsp+0F8h+var_98], rax
0x180050521  mov     rdx, [rbx+88h]
0x180050528  lea     rcx, [rsp+0F8h+var_D8]
0x18005052d  call    RtlActivateActivationContextUnsafeFast
0x180050532  nop
0x180050533  cmp     [rbx+6Eh], r14w
0x180050538  jz      short loc_180050547
0x18005053a  mov     rdx, rbx
0x18005053d  mov     ecx, 2
0x180050542  call    LdrpCallTlsInitializers
0x180050547  xor     r9d, r9d
0x18005054a  lea     r8d, [r9+2]
0x18005054e  mov     rdx, [rbx+30h]
0x180050552  mov     rcx, rdi
0x180050555  call    LdrpCallInitRoutine
0x18005055a  nop
0x18005055b  lea     rcx, [rsp+0F8h+var_D8]
0x180050560  call    RtlDeactivateActivationContextUnsafeFast
0x180050565  jmp     loc_1800504BD
0x18005056a  mov     rdx, cs:LdrpImageEntry
0x180050571  cmp     [rdx+6Eh], r14w
0x180050576  jz      short loc_1800505E7
0x180050578  cmp     cs:byte_1801CA908, r14b
0x18005057f  jnz     short loc_1800505E7
0x180050581  mov     [rsp+0F8h+var_88], 48h ; 'H'
0x18005058a  mov     [rsp+0F8h+var_80], 1
0x180050593  xorps   xmm0, xmm0
0x180050596  xor     eax, eax
0x180050598  movups  [rsp+0F8h+var_78], xmm0
0x1800505a0  movups  [rsp+0F8h+var_68], xmm0
0x1800505a8  movups  [rsp+0F8h+var_58], xmm0
0x1800505b0  mov     [rsp+0F8h+var_48], rax
0x1800505b8  mov     rdx, [rdx+88h]
0x1800505bf  lea     rcx, [rsp+0F8h+var_88]
0x1800505c4  call    RtlActivateActivationContextUnsafeFast
0x1800505c9  nop
0x1800505ca  mov     rdx, cs:LdrpImageEntry
0x1800505d1  mov     ecx, 2
0x1800505d6  call    LdrpCallTlsInitializers
0x1800505db  nop
0x1800505dc  lea     rcx, [rsp+0F8h+var_88]
0x1800505e1  call    RtlDeactivateActivationContextUnsafeFast
0x1800505e6  nop
0x1800505e7  xor     r8d, r8d
0x1800505ea  lea     edx, [r8+15h]
0x1800505ee  call    LdrpReleaseLoaderLock
0x1800505f3  call    LdrpDropLastInProgressCount
0x1800505f8  add     rsp, 0D8h
0x1800505ff  pop     r14
0x180050601  pop     rdi
0x180050602  pop     rsi
0x180050603  pop     rbx
0x180050604  retn
0x180050606  mov     rax, gs:30h
0x18005060f  test    byte ptr [rax+17EEh], 20h
0x180050616  jz      short loc_1800505F8
0x180050618  jmp     loc_18005044A
0x18005061d  mov     eax, 400h
0x180050622  test    [rbx+17EEh], ax
0x180050629  jz      loc_180050423
0x18005062f  mov     edx, ds:7FFE0330h
0x180050636  mov     eax, edx
0x180050638  and     eax, 3Fh
0x18005063b  mov     ecx, 40h ; '@'
0x180050640  sub     ecx, eax
0x180050642  mov     rax, cs:LdrpCorExeMainRoutine
0x180050649  ror     rax, cl
0x18005064c  xor     rdx, rax
0x18005064f  mov     [r8+80h], rdx
0x180050656  jmp     loc_180050423
0x18005065b  cmp     ebx, 0C0000017h
0x180050661  jnz     loc_18005046B
0x180050667  mov     [rsp+0F8h+arg_8], 0FFFFFFFFFFD23940h
0x180050673  lea     rdx, [rsp+0F8h+arg_8]
0x18005067b  xor     ecx, ecx
0x18005067d  call    ZwDelayExecution
0x180050682  jmp     loc_18005045C
0x180050687  mov     edx, ebx
0x180050689  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005068d  call    ZwTerminateProcess
0x180050692  mov     ecx, ebx
0x180050694  call    RtlRaiseStatus
0x180166625  push    rbp
0x180166627  sub     rsp, 20h
0x18016662b  mov     rbp, rdx
0x18016662e  lea     rcx, [rbp+20h]
0x180166632  call    RtlDeactivateActivationContextUnsafeFast
0x180166637  nop
0x180166638  add     rsp, 20h
0x18016663c  pop     rbp
0x18016663d  retn
0x18016663f  push    rbp
0x180166641  sub     rsp, 20h
0x180166645  mov     rbp, rdx
0x180166648  lea     rcx, [rbp+70h]
0x18016664c  call    RtlDeactivateActivationContextUnsafeFast
0x180166651  nop
0x180166652  add     rsp, 20h
0x180166656  pop     rbp
0x180166657  retn
0x180166659  push    rbp
0x18016665b  sub     rsp, 20h
0x18016665f  mov     rbp, rdx
0x180166662  xor     r8d, r8d
0x180166665  lea     edx, [r8+15h]
0x180166669  call    LdrpReleaseLoaderLock
0x18016666e  call    LdrpDropLastInProgressCount
0x180166673  nop
0x180166674  add     rsp, 20h
0x180166678  pop     rbp
0x180166679  retn
```
