# IsolationAwareLoadLibraryA

- ea: `0x180008904`
- end: `0x1800089b4`
- name: `IsolationAwareLoadLibraryA`
- size: `176`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007f18`
- `0x18002a710`
- `0x1800336b0`
- `0x1800339d0`
- `0x180033d90`
- `0x1800343d4`

## callees

- `0x180005160`
- `0x180008904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed44`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180008960`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180008960`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000899d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ed38`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000899d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ed38`

## string_xrefs

- `0x180008959`: `msftedit.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryA()
{
  HMODULE LibraryA; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryA = LoadLibraryA("msftedit.dll");
  v2 = LibraryA;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryA )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180008904  mov     rax, rsp
0x180008907  mov     [rax+10h], rbx
0x18000890b  mov     [rax+18h], rsi
0x18000890f  mov     [rax+8], rcx
0x180008913  push    rdi
0x180008914  sub     rsp, 30h
0x180008918  mov     qword ptr [rax-18h], 0
0x180008920  mov     qword ptr [rax+8], 0
0x180008928  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000892f  jnz     short loc_180008959
0x180008931  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008938  jnz     short loc_180008959
0x18000893a  lea     rcx, [rax+8]; lpCookie
0x18000893e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180008943  test    eax, eax
0x180008945  jnz     short loc_180008959
0x180008947  xor     eax, eax
0x180008949  mov     rbx, [rsp+38h+arg_8]
0x18000894e  mov     rsi, [rsp+38h+arg_10]
0x180008953  add     rsp, 30h
0x180008957  pop     rdi
0x180008958  retn
0x180008959  lea     rcx, aMsfteditDll; "msftedit.dll"
0x180008960  call    cs:__imp_LoadLibraryA
0x180008966  mov     rbx, rax
0x180008969  mov     [rsp+38h+var_18], rax
0x18000896e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180008975  jz      short loc_180008980
0x180008977  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000897e  jnz     short loc_1800089AF
0x180008980  test    rbx, rbx
0x180008983  jnz     short loc_180008992
0x180008985  lea     esi, [rbx+1]
0x180008988  call    cs:__imp_GetLastError
0x18000898e  mov     edi, eax
0x180008990  jmp     short loc_180008996
0x180008992  xor     esi, esi
0x180008994  xor     edi, edi
0x180008996  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000899b  xor     ecx, ecx; dwFlags
0x18000899d  call    cs:__imp_DeactivateActCtx
0x1800089a3  test    esi, esi
0x1800089a5  jz      short loc_1800089AF
0x1800089a7  mov     ecx, edi; dwErrCode
0x1800089a9  call    cs:__imp_SetLastError
0x1800089af  mov     rax, rbx
0x1800089b2  jmp     short loc_180008949
0x18003ecfb  push    rbx
0x18003ecfd  push    rbp
0x18003ecfe  push    rdi
0x18003ecff  sub     rsp, 20h
0x18003ed03  mov     rbp, rdx
0x18003ed06  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003ed0d  jz      short loc_18003ED18
0x18003ed0f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003ed16  jnz     short loc_18003ED4B
0x18003ed18  cmp     qword ptr [rbp+20h], 0
0x18003ed1d  jnz     short loc_18003ED2E
0x18003ed1f  mov     edi, 1
0x18003ed24  call    cs:__imp_GetLastError
0x18003ed2a  mov     ebx, eax
0x18003ed2c  jmp     short loc_18003ED32
0x18003ed2e  xor     edi, edi
0x18003ed30  xor     ebx, ebx
0x18003ed32  mov     rdx, [rbp+40h]; ulCookie
0x18003ed36  xor     ecx, ecx; dwFlags
0x18003ed38  call    cs:__imp_DeactivateActCtx
0x18003ed3e  test    edi, edi
0x18003ed40  jz      short loc_18003ED4B
0x18003ed42  mov     ecx, ebx; dwErrCode
0x18003ed44  call    cs:__imp_SetLastError
0x18003ed4a  nop
0x18003ed4b  add     rsp, 20h
0x18003ed4f  pop     rdi
0x18003ed50  pop     rbp
0x18003ed51  pop     rbx
0x18003ed52  retn
```
