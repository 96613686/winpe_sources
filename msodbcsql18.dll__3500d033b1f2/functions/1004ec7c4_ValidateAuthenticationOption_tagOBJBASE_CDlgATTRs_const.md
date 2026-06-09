# ValidateAuthenticationOption(tagOBJBASE *,CDlgATTRs const &)

- ea: `0x1004ec7c4`
- end: `0x1004ec94f`
- name: `?ValidateAuthenticationOption@@YAJPEAUtagOBJBASE@@AEBVCDlgATTRs@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct tagOBJBASE *, const struct CDlgATTRs *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1004e5b60`

## callees

- `0x1004ec7c4`
- `0x100520028`
- `0x100520370`
- `0x100546a7c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec822`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec86c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec887`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec897`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec8d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec8f7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec822`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec86c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec887`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec897`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec8d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ec8f7`

## string_xrefs

- `0x1004ec85f`: `ActiveDirectoryPassword`
- `0x1004ec872`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall ValidateAuthenticationOption(struct tagOBJBASE *a1, const struct CDlgATTRs *a2)
{
  __int64 v2; // r8
  __int64 v6; // rcx
  const wchar_t *v7; // rsi
  const wchar_t *v8; // rdi
  __int64 v9; // rdx
  __int16 v10; // ax

  v2 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v2 + 912) & 1) == 0 )
    return 0;
  v6 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
  v7 = (const wchar_t *)(v6 + *(_QWORD *)(v2 + 920));
  if ( (*(_BYTE *)(v2 + 192) & 1) == 0 || _wcsicmp((const wchar_t *)(*(_QWORD *)(v2 + 200) + v6), L"Yes") )
  {
    v8 = L"ActiveDirectoryPassword";
    if ( _wcsicmp(v7, L"ActiveDirectoryPassword")
      && _wcsicmp(v7, L"SqlPassword")
      && _wcsicmp(v7, L"ActiveDirectoryServicePrincipal") )
    {
      return 0;
    }
    v9 = *((_QWORD *)a2 + 1);
    v10 = *(_WORD *)(v9 + 144);
    if ( (v10 & 1) != 0 && (v10 & 0xC) == 0 && (*(_BYTE *)(v9 + 168) & 1) != 0 )
      return 0;
    if ( _wcsicmp(
           (const wchar_t *)(*(_QWORD *)(v9 + 920) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
           L"ActiveDirectoryPassword") )
    {
      v8 = L"SqlPassword";
      if ( !_wcsicmp(
              (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
              L"ActiveDirectoryServicePrincipal") )
        v8 = L"ActiveDirectoryServicePrincipal";
    }
    PostFormattedError(a1, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF, 1, 0xA1BBu, v8);
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 4326409);
    PostSQLErrorEx(a1, 0xA1B9u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1004ec7c4  mov     rax, rsp
0x1004ec7c7  mov     [rax+8], rbx
0x1004ec7cb  mov     [rax+10h], rbp
0x1004ec7cf  mov     [rax+18h], rsi
0x1004ec7d3  mov     [rax+20h], rdi
0x1004ec7d7  push    r15
0x1004ec7d9  sub     rsp, 30h
0x1004ec7dd  mov     r8, [rdx+8]
0x1004ec7e1  mov     rbx, rdx
0x1004ec7e4  mov     rbp, rcx
0x1004ec7e7  test    byte ptr [r8+390h], 1
0x1004ec7ef  jnz     short loc_1004EC7F8
0x1004ec7f1  xor     eax, eax
0x1004ec7f3  jmp     loc_1004EC934
0x1004ec7f8  mov     rax, [rdx+10h]
0x1004ec7fc  mov     rsi, [r8+398h]
0x1004ec803  mov     rcx, [rax+20h]
0x1004ec807  add     rsi, rcx
0x1004ec80a  test    byte ptr [r8+0C0h], 1
0x1004ec812  jz      short loc_1004EC85F
0x1004ec814  add     rcx, [r8+0C8h]; String1
0x1004ec81b  lea     rdx, aYes_1; "Yes"
0x1004ec822  call    cs:__imp__wcsicmp
0x1004ec828  test    eax, eax
0x1004ec82a  jnz     short loc_1004EC85F
0x1004ec82c  test    byte ptr cs:_bidGblFlags, 2
0x1004ec833  jz      short loc_1004EC841
0x1004ec835  mov     edx, 420409h
0x1004ec83a  xor     ecx, ecx
0x1004ec83c  call    _bidTraceMark
0x1004ec841  or      dword ptr [rsp+38h+var_18], 0FFFFFFFFh
0x1004ec846  mov     edx, 0A1B9h; unsigned __int16
0x1004ec84b  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1004ec84f  xor     r8d, r8d; int
0x1004ec852  mov     rcx, rbp; struct tagOBJBASE *
0x1004ec855  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004ec85a  jmp     loc_1004EC92F
0x1004ec85f  lea     rdi, aActivedirector_2; "ActiveDirectoryPassword"
0x1004ec866  mov     rcx, rsi; String1
0x1004ec869  mov     rdx, rdi; String2
0x1004ec86c  call    cs:__imp__wcsicmp
0x1004ec872  lea     r15, aActivedirector_0; "ActiveDirectoryServicePrincipal"
0x1004ec879  test    eax, eax
0x1004ec87b  jz      short loc_1004EC8A5
0x1004ec87d  lea     rdx, aSqlpassword; "SqlPassword"
0x1004ec884  mov     rcx, rsi; String1
0x1004ec887  call    cs:__imp__wcsicmp
0x1004ec88d  test    eax, eax
0x1004ec88f  jz      short loc_1004EC8A5
0x1004ec891  mov     rdx, r15; String2
0x1004ec894  mov     rcx, rsi; String1
0x1004ec897  call    cs:__imp__wcsicmp
0x1004ec89d  test    eax, eax
0x1004ec89f  jnz     loc_1004EC7F1
0x1004ec8a5  mov     rdx, [rbx+8]
0x1004ec8a9  movzx   eax, word ptr [rdx+90h]
0x1004ec8b0  test    al, 1
0x1004ec8b2  jz      short loc_1004EC8C5
0x1004ec8b4  test    al, 0Ch
0x1004ec8b6  jnz     short loc_1004EC8C5
0x1004ec8b8  test    byte ptr [rdx+0A8h], 1
0x1004ec8bf  jnz     loc_1004EC7F1
0x1004ec8c5  mov     rax, [rbx+10h]
0x1004ec8c9  mov     rcx, [rax+20h]
0x1004ec8cd  add     rcx, [rdx+398h]; String1
0x1004ec8d4  mov     rdx, rdi; String2
0x1004ec8d7  call    cs:__imp__wcsicmp
0x1004ec8dd  test    eax, eax
0x1004ec8df  jz      short loc_1004EC90A
0x1004ec8e1  mov     rdx, [rbx+8]
0x1004ec8e5  mov     rax, [rbx+10h]
0x1004ec8e9  mov     rcx, [rax+20h]
0x1004ec8ed  add     rcx, [rdx+398h]; String1
0x1004ec8f4  mov     rdx, r15; String2
0x1004ec8f7  call    cs:__imp__wcsicmp
0x1004ec8fd  test    eax, eax
0x1004ec8ff  lea     rdi, aSqlpassword; "SqlPassword"
0x1004ec906  cmovz   rdi, r15
0x1004ec90a  mov     eax, 0A1BBh
0x1004ec90f  mov     [rsp+38h+var_10], rdi
0x1004ec914  mov     r9d, 1; int
0x1004ec91a  mov     [rsp+38h+var_18], ax; unsigned __int16
0x1004ec91f  or      r8d, 0FFFFFFFFh; unsigned int
0x1004ec923  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1004ec927  mov     rcx, rbp; struct tagOBJBASE *
0x1004ec92a  call    ?PostFormattedError@@YAFPEAUtagOBJBASE@@_KKHGZZ; PostFormattedError(tagOBJBASE *,unsigned __int64,ulong,int,ushort,...)
0x1004ec92f  mov     eax, 80004005h
0x1004ec934  mov     rbx, [rsp+38h+arg_0]
0x1004ec939  mov     rbp, [rsp+38h+arg_8]
0x1004ec93e  mov     rsi, [rsp+38h+arg_10]
0x1004ec943  mov     rdi, [rsp+38h+arg_18]
0x1004ec948  add     rsp, 30h
0x1004ec94c  pop     r15
0x1004ec94e  retn
```
