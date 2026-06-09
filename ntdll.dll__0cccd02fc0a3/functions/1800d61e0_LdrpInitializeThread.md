# LdrpInitializeThread

- ea: `0x1800d61e0`
- end: `0x1800d648a`
- name: `LdrpInitializeThread`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800d5d68`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x1800254e0`
- `0x1800259fc`
- `0x18004250c`
- `0x18004c8f0`
- `0x18004cd50`
- `0x180050d08`
- `0x180050fa0`
- `0x180053990`
- `0x180067dd0`
- `0x1800d61e0`
- `0x1800d82f4`
- `0x18015e850`
- `0x18015e950`

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
0x1800d61e0  mov     rax, rsp
0x1800d61e3  push    rbx
0x1800d61e4  push    rsi
0x1800d61e5  push    rdi
0x1800d61e6  push    r14
0x1800d61e8  sub     rsp, 0D8h
0x1800d61ef  mov     r8, rcx
0x1800d61f2  xor     r14d, r14d
0x1800d61f5  mov     [rax+10h], r14
0x1800d61f9  mov     rbx, gs:30h
0x1800d6202  mov     rsi, [rbx+60h]
0x1800d6206  cmp     cs:UseCOR, r14b
0x1800d620d  jnz     loc_1800D640D
0x1800d6213  mov     rcx, rbx
0x1800d6216  call    LdrpAcquireSchedulerSharedDataSlot
0x1800d621b  mov     rcx, rbx
0x1800d621e  call    RtlpInitializeThreadActivationContextStack
0x1800d6223  mov     r9, gs:30h
0x1800d622c  test    byte ptr [r9+17EEh], 8
0x1800d6234  jnz     loc_1800D63F6
0x1800d623a  mov     eax, 2000h
0x1800d623f  test    [rbx+17EEh], ax
0x1800d6246  jnz     loc_1800D63E8
0x1800d624c  call    LdrpAllocateTls
0x1800d6251  test    eax, eax
0x1800d6253  mov     ebx, eax
0x1800d6255  js      loc_1800D644B
0x1800d625b  test    ebx, ebx
0x1800d625d  js      loc_1800D6477
0x1800d6263  xor     ecx, ecx
0x1800d6265  call    LdrpDrainWorkQueue
0x1800d626a  call    LdrpAcquireLoaderLock
0x1800d626f  nop
0x1800d6270  mov     rbx, cs:qword_1801CA8D0
0x1800d6277  lea     rax, qword_1801CA8D0
0x1800d627e  cmp     rbx, rax
0x1800d6281  jz      loc_1800D635A
0x1800d6287  mov     [rsp+0F8h+var_38], rbx
0x1800d628f  mov     rax, [rbx+98h]
0x1800d6296  mov     ecx, [rax+38h]
0x1800d6299  cmp     ecx, 9
0x1800d629c  jge     short loc_1800D62A3
0x1800d629e  mov     rbx, [rbx]
0x1800d62a1  jmp     short loc_1800D6277
0x1800d62a3  mov     rax, [rbx+30h]
0x1800d62a7  cmp     [rsi+10h], rax
0x1800d62ab  jnz     short loc_1800D62AF
0x1800d62ad  jmp     short loc_1800D629E
0x1800d62af  mov     eax, [rbx+68h]
0x1800d62b2  bt      eax, 12h
0x1800d62b6  jb      short loc_1800D62AD
0x1800d62b8  mov     rdi, [rbx+38h]
0x1800d62bc  mov     [rsp+0F8h+var_30], rdi
0x1800d62c4  test    rdi, rdi
0x1800d62c7  jz      short loc_1800D62AD
0x1800d62c9  mov     eax, [rbx+68h]
0x1800d62cc  bt      eax, 13h
0x1800d62d0  jnb     short loc_1800D62AD
0x1800d62d2  mov     eax, [rbx+68h]
0x1800d62d5  test    al, 4
0x1800d62d7  jz      short loc_1800D62AD
0x1800d62d9  cmp     cs:byte_1801CA908, r14b
0x1800d62e0  jnz     loc_1800D63D7
0x1800d62e6  mov     [rsp+0F8h+var_D8], 48h ; 'H'
0x1800d62ef  mov     [rsp+0F8h+var_D0], 1
0x1800d62f8  xorps   xmm0, xmm0
0x1800d62fb  xor     eax, eax
0x1800d62fd  movups  [rsp+0F8h+var_C8], xmm0
0x1800d6302  movups  [rsp+0F8h+var_B8], xmm0
0x1800d6307  movups  [rsp+0F8h+var_A8], xmm0
0x1800d630c  mov     [rsp+0F8h+var_98], rax
0x1800d6311  mov     rdx, [rbx+88h]
0x1800d6318  lea     rcx, [rsp+0F8h+var_D8]
0x1800d631d  call    RtlActivateActivationContextUnsafeFast
0x1800d6322  nop
0x1800d6323  cmp     [rbx+6Eh], r14w
0x1800d6328  jz      short loc_1800D6337
0x1800d632a  mov     rdx, rbx
0x1800d632d  mov     ecx, 2
0x1800d6332  call    LdrpCallTlsInitializers
0x1800d6337  xor     r9d, r9d
0x1800d633a  lea     r8d, [r9+2]
0x1800d633e  mov     rdx, [rbx+30h]
0x1800d6342  mov     rcx, rdi
0x1800d6345  call    LdrpCallInitRoutine
0x1800d634a  nop
0x1800d634b  lea     rcx, [rsp+0F8h+var_D8]
0x1800d6350  call    RtlDeactivateActivationContextUnsafeFast
0x1800d6355  jmp     loc_1800D62AD
0x1800d635a  mov     rdx, cs:LdrpImageEntry
0x1800d6361  cmp     [rdx+6Eh], r14w
0x1800d6366  jz      short loc_1800D63D7
0x1800d6368  cmp     cs:byte_1801CA908, r14b
0x1800d636f  jnz     short loc_1800D63D7
0x1800d6371  mov     [rsp+0F8h+var_88], 48h ; 'H'
0x1800d637a  mov     [rsp+0F8h+var_80], 1
0x1800d6383  xorps   xmm0, xmm0
0x1800d6386  xor     eax, eax
0x1800d6388  movups  [rsp+0F8h+var_78], xmm0
0x1800d6390  movups  [rsp+0F8h+var_68], xmm0
0x1800d6398  movups  [rsp+0F8h+var_58], xmm0
0x1800d63a0  mov     [rsp+0F8h+var_48], rax
0x1800d63a8  mov     rdx, [rdx+88h]
0x1800d63af  lea     rcx, [rsp+0F8h+var_88]
0x1800d63b4  call    RtlActivateActivationContextUnsafeFast
0x1800d63b9  nop
0x1800d63ba  mov     rdx, cs:LdrpImageEntry
0x1800d63c1  mov     ecx, 2
0x1800d63c6  call    LdrpCallTlsInitializers
0x1800d63cb  nop
0x1800d63cc  lea     rcx, [rsp+0F8h+var_88]
0x1800d63d1  call    RtlDeactivateActivationContextUnsafeFast
0x1800d63d6  nop
0x1800d63d7  xor     r8d, r8d
0x1800d63da  lea     edx, [r8+15h]
0x1800d63de  call    LdrpReleaseLoaderLock
0x1800d63e3  call    LdrpDropLastInProgressCount
0x1800d63e8  add     rsp, 0D8h
0x1800d63ef  pop     r14
0x1800d63f1  pop     rdi
0x1800d63f2  pop     rsi
0x1800d63f3  pop     rbx
0x1800d63f4  retn
0x1800d63f6  mov     rax, gs:30h
0x1800d63ff  test    byte ptr [rax+17EEh], 20h
0x1800d6406  jz      short loc_1800D63E8
0x1800d6408  jmp     loc_1800D623A
0x1800d640d  mov     eax, 400h
0x1800d6412  test    [rbx+17EEh], ax
0x1800d6419  jz      loc_1800D6213
0x1800d641f  mov     edx, ds:7FFE0330h
0x1800d6426  mov     eax, edx
0x1800d6428  and     eax, 3Fh
0x1800d642b  mov     ecx, 40h ; '@'
0x1800d6430  sub     ecx, eax
0x1800d6432  mov     rax, cs:LdrpCorExeMainRoutine
0x1800d6439  ror     rax, cl
0x1800d643c  xor     rdx, rax
0x1800d643f  mov     [r8+80h], rdx
0x1800d6446  jmp     loc_1800D6213
0x1800d644b  cmp     ebx, 0C0000017h
0x1800d6451  jnz     loc_1800D625B
0x1800d6457  mov     [rsp+0F8h+arg_8], 0FFFFFFFFFFD23940h
0x1800d6463  lea     rdx, [rsp+0F8h+arg_8]
0x1800d646b  xor     ecx, ecx
0x1800d646d  call    ZwDelayExecution
0x1800d6472  jmp     loc_1800D624C
0x1800d6477  mov     edx, ebx
0x1800d6479  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d647d  call    ZwTerminateProcess
0x1800d6482  mov     ecx, ebx
0x1800d6484  call    RtlRaiseStatus
0x180167ac7  push    rbp
0x180167ac9  sub     rsp, 20h
0x180167acd  mov     rbp, rdx
0x180167ad0  lea     rcx, [rbp+20h]
0x180167ad4  call    RtlDeactivateActivationContextUnsafeFast
0x180167ad9  nop
0x180167ada  add     rsp, 20h
0x180167ade  pop     rbp
0x180167adf  retn
0x180167ae1  push    rbp
0x180167ae3  sub     rsp, 20h
0x180167ae7  mov     rbp, rdx
0x180167aea  lea     rcx, [rbp+70h]
0x180167aee  call    RtlDeactivateActivationContextUnsafeFast
0x180167af3  nop
0x180167af4  add     rsp, 20h
0x180167af8  pop     rbp
0x180167af9  retn
0x180167afb  push    rbp
0x180167afd  sub     rsp, 20h
0x180167b01  mov     rbp, rdx
0x180167b04  xor     r8d, r8d
0x180167b07  lea     edx, [r8+15h]
0x180167b0b  call    LdrpReleaseLoaderLock
0x180167b10  call    LdrpDropLastInProgressCount
0x180167b15  nop
0x180167b16  add     rsp, 20h
0x180167b1a  pop     rbp
0x180167b1b  retn
```
