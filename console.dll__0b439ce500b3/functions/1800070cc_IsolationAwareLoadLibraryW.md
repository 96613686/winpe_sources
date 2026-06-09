# IsolationAwareLoadLibraryW

- ea: `0x1800070cc`
- end: `0x180007198`
- name: `IsolationAwareLoadLibraryW`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006e74`

## callees

- `0x1800070cc`
- `0x1800071a0`
- `0x180014008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007184`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007157`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007172`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007172`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180007129`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180007129`

## string_xrefs

- `0x180007122`: `ComCtl32.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryW()
{
  HMODULE LibraryW; // rax
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
  LibraryW = LoadLibraryW(L"ComCtl32.dll");
  v2 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
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
0x1800070cc  mov     rax, rsp
0x1800070cf  mov     [rax+10h], rbx
0x1800070d3  mov     [rax+18h], rsi
0x1800070d7  mov     [rax+8], rcx
0x1800070db  push    rdi
0x1800070dc  sub     rsp, 30h
0x1800070e0  mov     qword ptr [rax-18h], 0
0x1800070e8  mov     qword ptr [rax+8], 0
0x1800070f0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800070f7  jnz     short loc_180007122
0x1800070f9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007100  jnz     short loc_180007122
0x180007102  lea     rcx, [rax+8]; lpCookie
0x180007106  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000710b  test    eax, eax
0x18000710d  jnz     short loc_180007122
0x18000710f  xor     eax, eax
0x180007111  mov     rbx, [rsp+38h+arg_8]
0x180007116  mov     rsi, [rsp+38h+arg_10]
0x18000711b  add     rsp, 30h
0x18000711f  pop     rdi
0x180007120  retn
0x180007122  lea     rcx, LibFileName; "ComCtl32.dll"
0x180007129  call    cs:__imp_LoadLibraryW
0x180007130  nop     dword ptr [rax+rax+00h]
0x180007135  mov     rbx, rax
0x180007138  mov     [rsp+38h+var_18], rax
0x18000713d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007144  jz      short loc_18000714F
0x180007146  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000714d  jnz     short loc_180007190
0x18000714f  test    rbx, rbx
0x180007152  jnz     short loc_180007167
0x180007154  lea     esi, [rbx+1]
0x180007157  call    cs:__imp_GetLastError
0x18000715e  nop     dword ptr [rax+rax+00h]
0x180007163  mov     edi, eax
0x180007165  jmp     short loc_18000716B
0x180007167  xor     esi, esi
0x180007169  xor     edi, edi
0x18000716b  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180007170  xor     ecx, ecx; dwFlags
0x180007172  call    cs:__imp_DeactivateActCtx
0x180007179  nop     dword ptr [rax+rax+00h]
0x18000717e  test    esi, esi
0x180007180  jz      short loc_180007190
0x180007182  mov     ecx, edi; dwErrCode
0x180007184  call    cs:__imp_SetLastError
0x18000718b  nop     dword ptr [rax+rax+00h]
0x180007190  mov     rax, rbx
0x180007193  jmp     loc_180007111
0x180019112  push    rbx
0x180019114  push    rbp
0x180019115  push    rdi
0x180019116  sub     rsp, 20h
0x18001911a  mov     rbp, rdx
0x18001911d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180019124  jz      short loc_18001912F
0x180019126  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001912d  jnz     short loc_180019174
0x18001912f  cmp     qword ptr [rbp+20h], 0
0x180019134  jnz     short loc_18001914B
0x180019136  mov     edi, 1
0x18001913b  call    cs:__imp_GetLastError
0x180019142  nop     dword ptr [rax+rax+00h]
0x180019147  mov     ebx, eax
0x180019149  jmp     short loc_18001914F
0x18001914b  xor     edi, edi
0x18001914d  xor     ebx, ebx
0x18001914f  mov     rdx, [rbp+40h]; ulCookie
0x180019153  xor     ecx, ecx; dwFlags
0x180019155  call    cs:__imp_DeactivateActCtx
0x18001915c  nop     dword ptr [rax+rax+00h]
0x180019161  test    edi, edi
0x180019163  jz      short loc_180019174
0x180019165  mov     ecx, ebx; dwErrCode
0x180019167  call    cs:__imp_SetLastError
0x18001916e  nop     dword ptr [rax+rax+00h]
0x180019173  nop
0x180019174  add     rsp, 20h
0x180019178  pop     rdi
0x180019179  pop     rbp
0x18001917a  pop     rbx
0x18001917b  retn
```
