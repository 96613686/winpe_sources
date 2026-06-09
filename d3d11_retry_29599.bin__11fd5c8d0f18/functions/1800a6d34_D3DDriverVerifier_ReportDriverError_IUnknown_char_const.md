# D3DDriverVerifier::ReportDriverError(IUnknown *,char const *)

- ea: `0x1800a6d34`
- end: `0x1800a6ddc`
- name: `?ReportDriverError@D3DDriverVerifier@@YAXPEAUIUnknown@@PEBD@Z`
- size: `168`
- prototype: `void __fastcall(D3DDriverVerifier *__hidden this, struct IUnknown *, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a6af0`

## callees

- `0x1800a6d34`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a6dc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a6dc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6d68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6d68`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800a6d50`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800a6d50`

## string_xrefs

- `0x1800a6d49`: `D3DDriverVerifier.dll`

## pseudocode

```c
void __fastcall D3DDriverVerifier::ReportDriverError(D3DDriverVerifier *this, struct IUnknown *a2, const char *a3)
{
  HMODULE LibraryA; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  LibraryA = LoadLibraryA("D3DDriverVerifier.dll");
  v5 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "RetrieveVerifierInterface");
    if ( ProcAddress )
    {
      v7 = 0;
      ((void (__fastcall *)(GUID *, __int64 *))ProcAddress)(&IID_ID3DDriverVerifier1, &v7);
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64, D3DDriverVerifier *, __int64))(*(_QWORD *)v7 + 64LL))(v7, this, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    FreeLibrary(v5);
  }
}

```

## disassembly

```asm
0x1800a6d34  mov     [rsp+arg_0], rbx
0x1800a6d39  mov     [rsp+arg_8], rsi
0x1800a6d3e  push    rdi
0x1800a6d3f  sub     rsp, 30h
0x1800a6d43  mov     rsi, rcx
0x1800a6d46  mov     rdi, rdx
0x1800a6d49  lea     rcx, aD3ddriververif_0; "D3DDriverVerifier.dll"
0x1800a6d50  call    cs:__imp_LoadLibraryA
0x1800a6d56  mov     rbx, rax
0x1800a6d59  test    rax, rax
0x1800a6d5c  jz      short loc_1800A6DCC
0x1800a6d5e  lea     rdx, aRetrieveverifi; "RetrieveVerifierInterface"
0x1800a6d65  mov     rcx, rax; hModule
0x1800a6d68  call    cs:__imp_GetProcAddress
0x1800a6d6e  test    rax, rax
0x1800a6d71  jz      short loc_1800A6DC3
0x1800a6d73  lea     rdx, [rsp+38h+arg_10]
0x1800a6d78  mov     [rsp+38h+arg_10], 0
0x1800a6d81  lea     rcx, IID_ID3DDriverVerifier1
0x1800a6d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d8d  mov     rcx, [rsp+38h+arg_10]
0x1800a6d92  test    rcx, rcx
0x1800a6d95  jz      short loc_1800A6DC3
0x1800a6d97  mov     rax, [rcx]
0x1800a6d9a  xor     r9d, r9d
0x1800a6d9d  mov     rdx, rsi
0x1800a6da0  mov     [rsp+38h+var_18], rdi
0x1800a6da5  mov     rax, [rax+40h]
0x1800a6da9  lea     r8d, [r9+1]
0x1800a6dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6db2  mov     rcx, [rsp+38h+arg_10]
0x1800a6db7  mov     rax, [rcx]
0x1800a6dba  mov     rax, [rax+10h]
0x1800a6dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dc3  mov     rcx, rbx; hLibModule
0x1800a6dc6  call    cs:__imp_FreeLibrary
0x1800a6dcc  mov     rbx, [rsp+38h+arg_0]
0x1800a6dd1  mov     rsi, [rsp+38h+arg_8]
0x1800a6dd6  add     rsp, 30h
0x1800a6dda  pop     rdi
0x1800a6ddb  retn
```
