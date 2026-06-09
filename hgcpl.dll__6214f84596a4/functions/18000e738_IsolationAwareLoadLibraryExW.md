# IsolationAwareLoadLibraryExW

- ea: `0x18000e738`
- end: `0x18000e7ef`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c980`
- `0x18000d5d0`

## callees

- `0x18000b990`
- `0x18000e738`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e79b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e79b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f28`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000e7d8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180018f1c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000e7d8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180018f1c`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName, __int64 a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, a3);
  v7 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e738  mov     rax, rsp
0x18000e73b  mov     [rax+8], rbx
0x18000e73f  mov     [rax+18h], rsi
0x18000e743  mov     [rax+10h], rdx
0x18000e747  push    rdi
0x18000e748  sub     rsp, 30h
0x18000e74c  mov     ebx, r8d
0x18000e74f  mov     rdi, rcx
0x18000e752  mov     qword ptr [rax-18h], 0
0x18000e75a  mov     qword ptr [rax+10h], 0
0x18000e762  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e769  jnz     short loc_18000E793
0x18000e76b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e772  jnz     short loc_18000E793
0x18000e774  lea     rcx, [rax+10h]; lpCookie
0x18000e778  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e77d  test    eax, eax
0x18000e77f  jnz     short loc_18000E793
0x18000e781  xor     eax, eax
0x18000e783  mov     rbx, [rsp+38h+arg_0]
0x18000e788  mov     rsi, [rsp+38h+arg_10]
0x18000e78d  add     rsp, 30h
0x18000e791  pop     rdi
0x18000e792  retn
0x18000e793  mov     r8d, ebx; dwFlags
0x18000e796  xor     edx, edx; hFile
0x18000e798  mov     rcx, rdi; lpLibFileName
0x18000e79b  call    cs:__imp_LoadLibraryExW
0x18000e7a1  mov     rbx, rax
0x18000e7a4  mov     [rsp+38h+var_18], rax
0x18000e7a9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e7b0  jz      short loc_18000E7BB
0x18000e7b2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e7b9  jnz     short loc_18000E7EA
0x18000e7bb  test    rbx, rbx
0x18000e7be  jnz     short loc_18000E7CD
0x18000e7c0  lea     esi, [rbx+1]
0x18000e7c3  call    cs:__imp_GetLastError
0x18000e7c9  mov     edi, eax
0x18000e7cb  jmp     short loc_18000E7D1
0x18000e7cd  xor     esi, esi
0x18000e7cf  xor     edi, edi
0x18000e7d1  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e7d6  xor     ecx, ecx; dwFlags
0x18000e7d8  call    cs:__imp_DeactivateActCtx
0x18000e7de  test    esi, esi
0x18000e7e0  jz      short loc_18000E7EA
0x18000e7e2  mov     ecx, edi; dwErrCode
0x18000e7e4  call    cs:__imp_SetLastError
0x18000e7ea  mov     rax, rbx
0x18000e7ed  jmp     short loc_18000E783
0x180018edf  push    rbx
0x180018ee1  push    rbp
0x180018ee2  push    rdi
0x180018ee3  sub     rsp, 20h
0x180018ee7  mov     rbp, rdx
0x180018eea  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180018ef1  jz      short loc_180018EFC
0x180018ef3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180018efa  jnz     short loc_180018F2F
0x180018efc  cmp     qword ptr [rbp+20h], 0
0x180018f01  jnz     short loc_180018F12
0x180018f03  mov     edi, 1
0x180018f08  call    cs:__imp_GetLastError
0x180018f0e  mov     ebx, eax
0x180018f10  jmp     short loc_180018F16
0x180018f12  xor     edi, edi
0x180018f14  xor     ebx, ebx
0x180018f16  mov     rdx, [rbp+48h]; ulCookie
0x180018f1a  xor     ecx, ecx; dwFlags
0x180018f1c  call    cs:__imp_DeactivateActCtx
0x180018f22  test    edi, edi
0x180018f24  jz      short loc_180018F2F
0x180018f26  mov     ecx, ebx; dwErrCode
0x180018f28  call    cs:__imp_SetLastError
0x180018f2e  nop
0x180018f2f  add     rsp, 20h
0x180018f33  pop     rdi
0x180018f34  pop     rbp
0x180018f35  pop     rbx
0x180018f36  retn
```
