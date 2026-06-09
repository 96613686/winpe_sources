# IsolationAwareLoadLibraryExW

- ea: `0x18000bd08`
- end: `0x18000bddc`
- name: `IsolationAwareLoadLibraryExW`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b5a0`

## callees

- `0x1800071a0`
- `0x18000bd08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019405`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000bdb6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001941f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000bdb6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001941f`

## string_xrefs

- `0x18000bd66`: `conhostv1.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryExW()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(L"conhostv1.dll", 0, 0x802u);
  v2 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
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
0x18000bd08  mov     rax, rsp
0x18000bd0b  mov     [rax+8], rbx
0x18000bd0f  mov     [rax+18h], rsi
0x18000bd13  mov     [rax+10h], rdx
0x18000bd17  push    rdi
0x18000bd18  sub     rsp, 30h
0x18000bd1c  mov     qword ptr [rax-18h], 0
0x18000bd24  mov     qword ptr [rax+10h], 0
0x18000bd2c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bd33  jnz     short loc_18000BD5E
0x18000bd35  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bd3c  jnz     short loc_18000BD5E
0x18000bd3e  lea     rcx, [rax+10h]; lpCookie
0x18000bd42  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000bd47  test    eax, eax
0x18000bd49  jnz     short loc_18000BD5E
0x18000bd4b  xor     eax, eax
0x18000bd4d  mov     rbx, [rsp+38h+arg_0]
0x18000bd52  mov     rsi, [rsp+38h+arg_10]
0x18000bd57  add     rsp, 30h
0x18000bd5b  pop     rdi
0x18000bd5c  retn
0x18000bd5e  xor     edx, edx; hFile
0x18000bd60  mov     r8d, 802h; dwFlags
0x18000bd66  lea     rcx, aConhostv1Dll; "conhostv1.dll"
0x18000bd6d  call    cs:__imp_LoadLibraryExW
0x18000bd74  nop     dword ptr [rax+rax+00h]
0x18000bd79  mov     rbx, rax
0x18000bd7c  mov     [rsp+38h+var_18], rax
0x18000bd81  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bd88  jz      short loc_18000BD93
0x18000bd8a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bd91  jnz     short loc_18000BDD4
0x18000bd93  test    rbx, rbx
0x18000bd96  jnz     short loc_18000BDAB
0x18000bd98  lea     esi, [rbx+1]
0x18000bd9b  call    cs:__imp_GetLastError
0x18000bda2  nop     dword ptr [rax+rax+00h]
0x18000bda7  mov     edi, eax
0x18000bda9  jmp     short loc_18000BDAF
0x18000bdab  xor     esi, esi
0x18000bdad  xor     edi, edi
0x18000bdaf  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000bdb4  xor     ecx, ecx; dwFlags
0x18000bdb6  call    cs:__imp_DeactivateActCtx
0x18000bdbd  nop     dword ptr [rax+rax+00h]
0x18000bdc2  test    esi, esi
0x18000bdc4  jz      short loc_18000BDD4
0x18000bdc6  mov     ecx, edi; dwErrCode
0x18000bdc8  call    cs:__imp_SetLastError
0x18000bdcf  nop     dword ptr [rax+rax+00h]
0x18000bdd4  mov     rax, rbx
0x18000bdd7  jmp     loc_18000BD4D
0x1800193dc  push    rbx
0x1800193de  push    rbp
0x1800193df  push    rdi
0x1800193e0  sub     rsp, 20h
0x1800193e4  mov     rbp, rdx
0x1800193e7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800193ee  jz      short loc_1800193F9
0x1800193f0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800193f7  jnz     short loc_18001943E
0x1800193f9  cmp     qword ptr [rbp+20h], 0
0x1800193fe  jnz     short loc_180019415
0x180019400  mov     edi, 1
0x180019405  call    cs:__imp_GetLastError
0x18001940c  nop     dword ptr [rax+rax+00h]
0x180019411  mov     ebx, eax
0x180019413  jmp     short loc_180019419
0x180019415  xor     edi, edi
0x180019417  xor     ebx, ebx
0x180019419  mov     rdx, [rbp+48h]; ulCookie
0x18001941d  xor     ecx, ecx; dwFlags
0x18001941f  call    cs:__imp_DeactivateActCtx
0x180019426  nop     dword ptr [rax+rax+00h]
0x18001942b  test    edi, edi
0x18001942d  jz      short loc_18001943E
0x18001942f  mov     ecx, ebx; dwErrCode
0x180019431  call    cs:__imp_SetLastError
0x180019438  nop     dword ptr [rax+rax+00h]
0x18001943d  nop
0x18001943e  add     rsp, 20h
0x180019442  pop     rdi
0x180019443  pop     rbp
0x180019444  pop     rbx
0x180019445  retn
```
