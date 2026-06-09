# LdrpWriteBackProtectedDelayLoad

- ea: `0x1800c0b5c`
- end: `0x1800c0c97`
- name: `LdrpWriteBackProtectedDelayLoad`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800c0690`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001eb80`
- `0x180083bf0`
- `0x1800c0b5c`
- `0x1800eac88`
- `0x18015f4e0`

## string_xrefs

- `0x1800c0c7f`: `LdrpWriteBackProtectedDelayLoad:Unable to unsuppress the export suppressed functions that is imported in the DLL based at 0x%p.Status = 0x%x\n`
- `0x1800c0c65`: `LdrpWriteBackProtectedDelayLoad`

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
0x1800c0b5c  mov     rax, rsp
0x1800c0b5f  mov     [rax+18h], rbx
0x1800c0b63  push    rbp
0x1800c0b64  push    rsi
0x1800c0b65  push    rdi
0x1800c0b66  push    r14
0x1800c0b68  push    r15
0x1800c0b6a  sub     rsp, 40h
0x1800c0b6e  mov     dword ptr [rax+20h], 0
0x1800c0b75  lea     rsi, [rcx+90h]
0x1800c0b7c  mov     [rax+10h], rdx
0x1800c0b80  mov     rbp, rcx
0x1800c0b83  mov     eax, r9d
0x1800c0b86  mov     rcx, rsi
0x1800c0b89  shl     rax, 3
0x1800c0b8d  mov     r14, r8
0x1800c0b90  mov     [rsp+68h+arg_0], rax
0x1800c0b95  mov     rdi, rdx
0x1800c0b98  mov     ebx, r9d
0x1800c0b9b  call    RtlAcquireSRWLockExclusive
0x1800c0ba0  mov     r9d, [rsp+68h+arg_20]
0x1800c0ba8  mov     rax, [rdi+r9*8]
0x1800c0bac  cmp     rax, [r14+r9*8]
0x1800c0bb0  jz      short loc_1800C0C23
0x1800c0bb2  lea     rax, [rsp+68h+arg_18]
0x1800c0bba  mov     r9d, 4
0x1800c0bc0  lea     r8, [rsp+68h+arg_0]
0x1800c0bc5  mov     [rsp+68h+Format], rax
0x1800c0bca  lea     rdx, [rsp+68h+arg_8]
0x1800c0bcf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c0bd3  call    ZwProtectVirtualMemory
0x1800c0bd8  test    eax, eax
0x1800c0bda  js      short loc_1800C0C23
0x1800c0bdc  mov     r15d, ebx
0x1800c0bdf  test    ebx, ebx
0x1800c0be1  jz      short loc_1800C0BF4
0x1800c0be3  dec     ebx
0x1800c0be5  mov     rdx, [r14+rbx*8]
0x1800c0be9  test    rdx, rdx
0x1800c0bec  jz      short loc_1800C0BDF
0x1800c0bee  mov     [rdi+rbx*8], rdx
0x1800c0bf2  jmp     short loc_1800C0BDF
0x1800c0bf4  lea     rax, [rsp+68h+arg_18]
0x1800c0bfc  mov     r9d, 2
0x1800c0c02  lea     r8, [rsp+68h+arg_0]
0x1800c0c07  mov     [rsp+68h+Format], rax
0x1800c0c0c  lea     rdx, [rsp+68h+arg_8]
0x1800c0c11  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c0c15  call    ZwProtectVirtualMemory
0x1800c0c1a  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800c0c1f  test    eax, eax
0x1800c0c21  jnz     short loc_1800C0C40
0x1800c0c23  mov     rcx, rsi
0x1800c0c26  call    RtlReleaseSRWLockExclusive
0x1800c0c2b  mov     rbx, [rsp+68h+arg_10]
0x1800c0c33  add     rsp, 40h
0x1800c0c37  pop     r15
0x1800c0c39  pop     r14
0x1800c0c3b  pop     rdi
0x1800c0c3c  pop     rsi
0x1800c0c3d  pop     rbp
0x1800c0c3e  retn
0x1800c0c40  mov     rcx, [rbp+30h]
0x1800c0c44  lea     r8d, ds:0[r15*8]
0x1800c0c4c  sub     r8d, [rbp+30h]
0x1800c0c50  add     r8d, 0FFFFFFF8h
0x1800c0c54  add     r8d, edi
0x1800c0c57  sub     edi, [rbp+30h]
0x1800c0c5a  mov     edx, edi
0x1800c0c5c  call    LdrpUnsuppressAddressTakenIat
0x1800c0c61  mov     [rsp+68h+var_38], eax
0x1800c0c65  lea     r8, aLdrpwritebackp_0; "LdrpWriteBackProtectedDelayLoad"
0x1800c0c6c  mov     rax, [rbp+30h]
0x1800c0c70  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800c0c77  mov     qword ptr [rsp+68h+ArgList], rax; ArgList
0x1800c0c7c  xor     r9d, r9d; int
0x1800c0c7f  lea     rax, aLdrpwritebackp; "LdrpWriteBackProtectedDelayLoad:Unable "...
0x1800c0c86  mov     edx, 3A9h; int
0x1800c0c8b  mov     [rsp+68h+Format], rax; Format
0x1800c0c90  call    LdrpLogInternal
0x1800c0c95  jmp     short loc_1800C0C23
```
