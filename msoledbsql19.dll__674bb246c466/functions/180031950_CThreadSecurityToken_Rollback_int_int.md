# CThreadSecurityToken::Rollback(int,int)

- ea: `0x180031950`
- end: `0x180031af9`
- name: `?Rollback@CThreadSecurityToken@@QEAAJHH@Z`
- size: `425`
- prototype: `__int64 __fastcall(CThreadSecurityToken *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002e3f0`

## callees

- `0x1800030c0`
- `0x180031950`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800319de`
- `KERNEL32!GetLastError` at `0x180031a54`
- `KERNEL32!GetLastError` at `0x1800319de`
- `KERNEL32!GetLastError` at `0x180031a54`
- `ADVAPI32!SetThreadToken` at `0x180031a4a`
- `ADVAPI32!SetThreadToken` at `0x180031a4a`
- `ADVAPI32!RevertToSelf` at `0x18003199f`
- `ADVAPI32!RevertToSelf` at `0x18003199f`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::Rollback(HANDLE *this, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // ebx
  wchar_t *v5; // r8
  __int64 v6; // rdx
  char *v7; // rcx
  signed int LastError; // eax
  signed int v10; // eax

  v3 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`10'::_bidPtrSA_030_3486[0] )
      bidTraceW(
        `CThreadSecurityToken::Rollback'::`10'::_bidSrcFileA[0],
        3569664,
        `CThreadSecurityToken::Rollback'::`10'::_bidPtrSA_030_3486[0],
        a2);
    if ( !RevertToSelf() )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`29'::_bidPtrSA_030_3497[0] )
      {
        bidTraceW(
          `CThreadSecurityToken::Rollback'::`29'::_bidSrcFileA[0],
          3580928,
          `CThreadSecurityToken::Rollback'::`29'::_bidPtrSA_030_3497[0],
          v3);
        return v3;
      }
      return v3;
    }
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`20'::_bidPtrSA_030_3491[0] )
    {
      v5 = `CThreadSecurityToken::Rollback'::`20'::_bidPtrSA_030_3491[0];
      v6 = 3574784;
      v7 = `CThreadSecurityToken::Rollback'::`20'::_bidSrcFileA[0];
LABEL_23:
      bidTraceW(v7, v6, v5, a3);
    }
  }
  else
  {
    if ( SetThreadToken(0, *this) )
    {
      if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Rollback'::`49'::_bidPtrSA_030_3510[0] )
        return v3;
      v5 = `CThreadSecurityToken::Rollback'::`49'::_bidPtrSA_030_3510[0];
      v6 = 3594240;
      v7 = `CThreadSecurityToken::Rollback'::`49'::_bidSrcFileA[0];
      goto LABEL_23;
    }
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`40'::_bidPtrSA_030_3505[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::Rollback'::`40'::_bidSrcFileA[0],
        3589120,
        `CThreadSecurityToken::Rollback'::`40'::_bidPtrSA_030_3505[0],
        v3);
      return v3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180031950  mov     [rsp+arg_0], rbx
0x180031955  mov     [rsp+arg_8], rsi
0x18003195a  push    rdi
0x18003195b  sub     rsp, 30h
0x18003195f  xor     ebx, ebx
0x180031961  mov     esi, r8d
0x180031964  mov     edi, edx
0x180031966  cmp     [rcx+8], bl
0x180031969  jz      loc_180031A45
0x18003196f  test    byte ptr cs:_bidGblFlags, 2
0x180031976  jz      short loc_18003199F
0x180031978  mov     rax, cs:?_bidPtrSA_030_3486@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidPtrSA_030_3486
0x18003197f  test    rax, rax
0x180031982  jz      short loc_18003199F
0x180031984  mov     r8, cs:?_bidPtrSA_030_3486@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidPtrSA_030_3486
0x18003198b  mov     r9d, edx
0x18003198e  mov     rcx, cs:?_bidSrcFileA@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidSrcFileA
0x180031995  mov     edx, 367800h
0x18003199a  call    _bidTraceW
0x18003199f  call    cs:__imp_RevertToSelf
0x1800319a5  test    eax, eax
0x1800319a7  jz      short loc_1800319DE
0x1800319a9  test    byte ptr cs:_bidGblFlags, 2
0x1800319b0  jz      loc_180031AE7
0x1800319b6  mov     rax, cs:?_bidPtrSA_030_3491@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidPtrSA_030_3491
0x1800319bd  test    rax, rax
0x1800319c0  jz      loc_180031AE7
0x1800319c6  mov     r8, cs:?_bidPtrSA_030_3491@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidPtrSA_030_3491
0x1800319cd  mov     edx, 368C00h
0x1800319d2  mov     rcx, cs:?_bidSrcFileA@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidSrcFileA
0x1800319d9  jmp     loc_180031ADB
0x1800319de  call    cs:__imp_GetLastError
0x1800319e4  mov     ebx, eax
0x1800319e6  test    eax, eax
0x1800319e8  jle     short loc_1800319F3
0x1800319ea  movzx   ebx, ax
0x1800319ed  or      ebx, 80070000h
0x1800319f3  test    byte ptr cs:_bidGblFlags, 2
0x1800319fa  jz      loc_180031AE7
0x180031a00  mov     rax, cs:?_bidPtrSA_030_3497@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidPtrSA_030_3497
0x180031a07  test    rax, rax
0x180031a0a  jz      loc_180031AE7
0x180031a10  mov     r8, cs:?_bidPtrSA_030_3497@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidPtrSA_030_3497
0x180031a17  mov     r9d, ebx
0x180031a1a  mov     rcx, cs:?_bidSrcFileA@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidSrcFileA
0x180031a21  mov     edx, 36A400h
0x180031a26  mov     [rsp+38h+var_10], edi
0x180031a2a  mov     [rsp+38h+var_18], esi
0x180031a2e  call    _bidTraceW
0x180031a33  mov     eax, ebx
0x180031a35  mov     rbx, [rsp+38h+arg_0]
0x180031a3a  mov     rsi, [rsp+38h+arg_8]
0x180031a3f  add     rsp, 30h
0x180031a43  pop     rdi
0x180031a44  retn
0x180031a45  mov     rdx, [rcx]; Token
0x180031a48  xor     ecx, ecx; Thread
0x180031a4a  call    cs:__imp_SetThreadToken
0x180031a50  test    eax, eax
0x180031a52  jnz     short loc_180031AB3
0x180031a54  call    cs:__imp_GetLastError
0x180031a5a  mov     ebx, eax
0x180031a5c  test    eax, eax
0x180031a5e  jle     short loc_180031A69
0x180031a60  movzx   ebx, ax
0x180031a63  or      ebx, 80070000h
0x180031a69  test    byte ptr cs:_bidGblFlags, 2
0x180031a70  jz      short loc_180031AE7
0x180031a72  mov     rax, cs:?_bidPtrSA_030_3505@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidPtrSA_030_3505
0x180031a79  test    rax, rax
0x180031a7c  jz      short loc_180031AE7
0x180031a7e  mov     r8, cs:?_bidPtrSA_030_3505@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidPtrSA_030_3505
0x180031a85  mov     r9d, ebx
0x180031a88  mov     rcx, cs:?_bidSrcFileA@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidSrcFileA
0x180031a8f  mov     edx, 36C400h
0x180031a94  mov     [rsp+38h+var_10], edi
0x180031a98  mov     [rsp+38h+var_18], esi
0x180031a9c  call    _bidTraceW
0x180031aa1  mov     eax, ebx
0x180031aa3  mov     rbx, [rsp+38h+arg_0]
0x180031aa8  mov     rsi, [rsp+38h+arg_8]
0x180031aad  add     rsp, 30h
0x180031ab1  pop     rdi
0x180031ab2  retn
0x180031ab3  test    byte ptr cs:_bidGblFlags, 2
0x180031aba  jz      short loc_180031AE7
0x180031abc  mov     rcx, cs:?_bidPtrSA_030_3510@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidPtrSA_030_3510
0x180031ac3  test    rcx, rcx
0x180031ac6  jz      short loc_180031AE7
0x180031ac8  mov     r8, cs:?_bidPtrSA_030_3510@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidPtrSA_030_3510
0x180031acf  mov     edx, 36D800h
0x180031ad4  mov     rcx, cs:?_bidSrcFileA@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidSrcFileA
0x180031adb  mov     r9d, esi
0x180031ade  mov     [rsp+38h+var_18], edi
0x180031ae2  call    _bidTraceW
0x180031ae7  mov     rsi, [rsp+38h+arg_8]
0x180031aec  mov     eax, ebx
0x180031aee  mov     rbx, [rsp+38h+arg_0]
0x180031af3  add     rsp, 30h
0x180031af7  pop     rdi
0x180031af8  retn
```
