# LdrpWriteBackProtectedDelayLoad

- ea: `0x1800bc87c`
- end: `0x1800bc9b7`
- name: `LdrpWriteBackProtectedDelayLoad`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800bc3b0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001eb80`
- `0x180067210`
- `0x1800bc87c`
- `0x1800ea628`
- `0x18015ecd0`

## string_xrefs

- `0x1800bc99f`: `LdrpWriteBackProtectedDelayLoad:Unable to unsuppress the export suppressed functions that is imported in the DLL based at 0x%p.Status = 0x%x\n`
- `0x1800bc985`: `LdrpWriteBackProtectedDelayLoad`

## pseudocode

```c
__int64 __fastcall LdrpWriteBackProtectedDelayLoad(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rsi
  __int64 v9; // rbx
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF
  __int64 v14; // [rsp+78h] [rbp+10h] BYREF
  int v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  v5 = a1 + 144;
  v14 = a2;
  v13 = 8LL * a4;
  LODWORD(v9) = a4;
  RtlAcquireSRWLockExclusive(a1 + 144);
  if ( *(_QWORD *)(a2 + 8LL * a5) != *(_QWORD *)(a3 + 8LL * a5)
    && (int)ZwProtectVirtualMemory(-1, &v14, &v13, 4, &v15) >= 0 )
  {
    v10 = v9;
    while ( (_DWORD)v9 )
    {
      v9 = (unsigned int)(v9 - 1);
      v11 = *(_QWORD *)(a3 + 8 * v9);
      if ( v11 )
        *(_QWORD *)(a2 + 8 * v9) = v11;
    }
    ZwProtectVirtualMemory(-1, &v14, &v13, 2, &v15);
    if ( (unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression() )
    {
      LdrpUnsuppressAddressTakenIat(
        *(_QWORD *)(a1 + 48),
        (unsigned int)(a2 - *(_DWORD *)(a1 + 48)),
        (unsigned int)(a2 + 8 * v10 - *(_DWORD *)(a1 + 48) - 8));
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrdload.c",
        937,
        (int)"LdrpWriteBackProtectedDelayLoad",
        0,
        "LdrpWriteBackProtectedDelayLoad:Unable to unsuppress the export suppressed functions that is imported in the DLL"
        " based at 0x%p.Status = 0x%x\n",
        *(_QWORD *)(a1 + 48));
    }
  }
  return RtlReleaseSRWLockExclusive(v5);
}

```

## disassembly

```asm
0x1800bc87c  mov     rax, rsp
0x1800bc87f  mov     [rax+18h], rbx
0x1800bc883  push    rbp
0x1800bc884  push    rsi
0x1800bc885  push    rdi
0x1800bc886  push    r14
0x1800bc888  push    r15
0x1800bc88a  sub     rsp, 40h
0x1800bc88e  mov     dword ptr [rax+20h], 0
0x1800bc895  lea     rsi, [rcx+90h]
0x1800bc89c  mov     [rax+10h], rdx
0x1800bc8a0  mov     rbp, rcx
0x1800bc8a3  mov     eax, r9d
0x1800bc8a6  mov     rcx, rsi
0x1800bc8a9  shl     rax, 3
0x1800bc8ad  mov     r14, r8
0x1800bc8b0  mov     [rsp+68h+arg_0], rax
0x1800bc8b5  mov     rdi, rdx
0x1800bc8b8  mov     ebx, r9d
0x1800bc8bb  call    RtlAcquireSRWLockExclusive
0x1800bc8c0  mov     r9d, [rsp+68h+arg_20]
0x1800bc8c8  mov     rax, [rdi+r9*8]
0x1800bc8cc  cmp     rax, [r14+r9*8]
0x1800bc8d0  jz      short loc_1800BC943
0x1800bc8d2  lea     rax, [rsp+68h+arg_18]
0x1800bc8da  mov     r9d, 4
0x1800bc8e0  lea     r8, [rsp+68h+arg_0]
0x1800bc8e5  mov     [rsp+68h+Format], rax
0x1800bc8ea  lea     rdx, [rsp+68h+arg_8]
0x1800bc8ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bc8f3  call    ZwProtectVirtualMemory
0x1800bc8f8  test    eax, eax
0x1800bc8fa  js      short loc_1800BC943
0x1800bc8fc  mov     r15d, ebx
0x1800bc8ff  test    ebx, ebx
0x1800bc901  jz      short loc_1800BC914
0x1800bc903  dec     ebx
0x1800bc905  mov     rdx, [r14+rbx*8]
0x1800bc909  test    rdx, rdx
0x1800bc90c  jz      short loc_1800BC8FF
0x1800bc90e  mov     [rdi+rbx*8], rdx
0x1800bc912  jmp     short loc_1800BC8FF
0x1800bc914  lea     rax, [rsp+68h+arg_18]
0x1800bc91c  mov     r9d, 2
0x1800bc922  lea     r8, [rsp+68h+arg_0]
0x1800bc927  mov     [rsp+68h+Format], rax
0x1800bc92c  lea     rdx, [rsp+68h+arg_8]
0x1800bc931  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bc935  call    ZwProtectVirtualMemory
0x1800bc93a  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800bc93f  test    eax, eax
0x1800bc941  jnz     short loc_1800BC960
0x1800bc943  mov     rcx, rsi
0x1800bc946  call    RtlReleaseSRWLockExclusive
0x1800bc94b  mov     rbx, [rsp+68h+arg_10]
0x1800bc953  add     rsp, 40h
0x1800bc957  pop     r15
0x1800bc959  pop     r14
0x1800bc95b  pop     rdi
0x1800bc95c  pop     rsi
0x1800bc95d  pop     rbp
0x1800bc95e  retn
0x1800bc960  mov     rcx, [rbp+30h]
0x1800bc964  lea     r8d, ds:0[r15*8]
0x1800bc96c  sub     r8d, [rbp+30h]
0x1800bc970  add     r8d, 0FFFFFFF8h
0x1800bc974  add     r8d, edi
0x1800bc977  sub     edi, [rbp+30h]
0x1800bc97a  mov     edx, edi
0x1800bc97c  call    LdrpUnsuppressAddressTakenIat
0x1800bc981  mov     [rsp+68h+var_38], eax
0x1800bc985  lea     r8, aLdrpwritebackp_0; "LdrpWriteBackProtectedDelayLoad"
0x1800bc98c  mov     rax, [rbp+30h]
0x1800bc990  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800bc997  mov     qword ptr [rsp+68h+ArgList], rax; ArgList
0x1800bc99c  xor     r9d, r9d; int
0x1800bc99f  lea     rax, aLdrpwritebackp; "LdrpWriteBackProtectedDelayLoad:Unable "...
0x1800bc9a6  mov     edx, 3A9h; int
0x1800bc9ab  mov     [rsp+68h+Format], rax; Format
0x1800bc9b0  call    LdrpLogInternal
0x1800bc9b5  jmp     short loc_1800BC943
```
