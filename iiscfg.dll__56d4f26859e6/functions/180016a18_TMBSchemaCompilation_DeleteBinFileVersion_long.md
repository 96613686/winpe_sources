# TMBSchemaCompilation::DeleteBinFileVersion(long)

- ea: `0x180016a18`
- end: `0x180016ade`
- name: `?DeleteBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z`
- size: `198`
- prototype: `__int64 __fastcall(TMBSchemaCompilation *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017814`
- `0x180017b70`

## callees

- `0x180005870`
- `0x180016a18`
- `0x180017b44`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180016a8a`
- `msvcrt!swprintf_s` at `0x180016a8a`
- `KERNEL32!DeleteFileW` at `0x180016aba`
- `KERNEL32!DeleteFileW` at `0x180016aba`
- `ole32!CoTaskMemAlloc` at `0x180016a54`
- `ole32!CoTaskMemAlloc` at `0x180016a54`

## pseudocode

```c
__int64 __fastcall TMBSchemaCompilation::DeleteBinFileVersion(TMBSchemaCompilation *this, int a2)
{
  wchar_t *v5; // rax
  const WCHAR *v6; // rbx
  unsigned int v7; // ebx
  wchar_t *v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 < 0 )
    return 2147942487LL;
  v5 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v6 = v5;
  v8 = v5;
  if ( v5 )
  {
    swprintf_s(v5, *((_QWORD *)this + 320), L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), a2);
    TMBSchemaCompilation::TBinFileName::UnloadBinFile((TMBSchemaCompilation *)((char *)this + 40 * (a2 % 0x3Fu)));
    DeleteFileW(v6);
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
  }
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v8);
  return v7;
}

```

## disassembly

```asm
0x180016a18  mov     [rsp+arg_0], rbx
0x180016a1d  mov     [rsp+arg_8], rsi
0x180016a22  push    rdi
0x180016a23  sub     rsp, 30h
0x180016a27  mov     edi, edx
0x180016a29  mov     rsi, rcx
0x180016a2c  test    edx, edx
0x180016a2e  jns     short loc_180016A3A
0x180016a30  mov     eax, 80070057h
0x180016a35  jmp     loc_180016ACE
0x180016a3a  mov     eax, 2
0x180016a3f  mul     qword ptr [rcx+0A00h]
0x180016a46  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016a4d  cmovb   rax, rcx
0x180016a51  mov     rcx, rax; cb
0x180016a54  call    cs:__imp_CoTaskMemAlloc
0x180016a5a  mov     rbx, rax
0x180016a5d  mov     [rsp+38h+arg_10], rax
0x180016a62  test    rax, rax
0x180016a65  jnz     short loc_180016A6E
0x180016a67  mov     ebx, 8007000Eh
0x180016a6c  jmp     short loc_180016AC2
0x180016a6e  mov     [rsp+38h+var_18], edi
0x180016a72  mov     r9, [rsi+0A08h]
0x180016a79  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x180016a80  mov     rdx, [rsi+0A00h]; BufferCount
0x180016a87  mov     rcx, rbx; Buffer
0x180016a8a  call    cs:__imp_swprintf_s
0x180016a90  mov     eax, 4104105h
0x180016a95  mul     edi
0x180016a97  mov     eax, edi
0x180016a99  sub     eax, edx
0x180016a9b  shr     eax, 1
0x180016a9d  add     eax, edx
0x180016a9f  shr     eax, 5
0x180016aa2  imul    eax, 3Fh ; '?'
0x180016aa5  sub     edi, eax
0x180016aa7  movsxd  rax, edi
0x180016aaa  lea     rcx, [rax+rax*4]
0x180016aae  lea     rcx, [rsi+rcx*8]; this
0x180016ab2  call    ?UnloadBinFile@TBinFileName@TMBSchemaCompilation@@QEAAXXZ; TMBSchemaCompilation::TBinFileName::UnloadBinFile(void)
0x180016ab7  mov     rcx, rbx; lpFileName
0x180016aba  call    cs:__imp_DeleteFileW
0x180016ac0  xor     ebx, ebx
0x180016ac2  lea     rcx, [rsp+38h+arg_10]; void *
0x180016ac7  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180016acc  mov     eax, ebx
0x180016ace  mov     rbx, [rsp+38h+arg_0]
0x180016ad3  mov     rsi, [rsp+38h+arg_8]
0x180016ad8  add     rsp, 30h
0x180016adc  pop     rdi
0x180016add  retn
```
