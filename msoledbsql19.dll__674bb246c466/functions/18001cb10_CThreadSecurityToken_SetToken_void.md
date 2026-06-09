# CThreadSecurityToken::SetToken(void)

- ea: `0x18001cb10`
- end: `0x18001cd59`
- name: `?SetToken@CThreadSecurityToken@@QEBAJXZ`
- size: `585`
- prototype: `__int64 __fastcall(CThreadSecurityToken *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bd40`
- `0x180031080`
- `0x1801940e0`

## callees

- `0x1800030c0`
- `0x18001cb10`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cbe4`
- `KERNEL32!GetLastError` at `0x18001cc48`
- `KERNEL32!GetLastError` at `0x18001cbe4`
- `KERNEL32!GetLastError` at `0x18001cc48`
- `ADVAPI32!SetThreadToken` at `0x18001cc3e`
- `ADVAPI32!SetThreadToken` at `0x18001cc3e`
- `ADVAPI32!RevertToSelf` at `0x18001cb7a`
- `ADVAPI32!RevertToSelf` at `0x18001cb7a`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::SetToken(HANDLE *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  __int64 v4; // r9
  signed int v5; // eax
  __int64 v6; // r9

  v1 = 0;
  if ( *this == (HANDLE)-1LL )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`62'::_bidPtrSA_030_3465[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        `CThreadSecurityToken::SetToken'::`62'::_bidSrcFileA[0],
        3548160,
        `CThreadSecurityToken::SetToken'::`62'::_bidPtrSA_030_3465[0],
        0);
    return (unsigned int)-2147467259;
  }
  else if ( *((_BYTE *)this + 8) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`13'::_bidPtrSA_030_3438[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        `CThreadSecurityToken::SetToken'::`13'::_bidSrcFileA[0],
        3520512,
        `CThreadSecurityToken::SetToken'::`13'::_bidPtrSA_030_3438[0],
        0);
    if ( RevertToSelf() )
    {
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`23'::_bidPtrSA_030_3442[0] && bidID != -1 )
      {
        ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
          bidID,
          `CThreadSecurityToken::SetToken'::`23'::_bidSrcFileA[0],
          3524608,
          `CThreadSecurityToken::SetToken'::`23'::_bidPtrSA_030_3442[0],
          0);
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = (unsigned int)LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v1 = v4;
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_3447[0] )
      {
        bidTraceW(
          `CThreadSecurityToken::SetToken'::`32'::_bidSrcFileA[0],
          3529728,
          `CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_3447[0],
          v4);
        return v1;
      }
    }
  }
  else if ( SetThreadToken(0, *this) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`53'::_bidPtrSA_030_3459[0] && bidID != -1 )
    {
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        `CThreadSecurityToken::SetToken'::`53'::_bidSrcFileA[0],
        3542016,
        `CThreadSecurityToken::SetToken'::`53'::_bidPtrSA_030_3459[0],
        0);
      return 0;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = (unsigned int)v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v1 = v6;
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_3455[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::SetToken'::`44'::_bidSrcFileA[0],
        3537920,
        `CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_3455[0],
        v6);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001cb10  push    rbx
0x18001cb12  sub     rsp, 30h
0x18001cb16  mov     rdx, [rcx]; Token
0x18001cb19  xor     ebx, ebx
0x18001cb1b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001cb1f  jz      loc_18001CD00
0x18001cb25  cmp     [rcx+8], bl
0x18001cb28  jz      loc_18001CC3C
0x18001cb2e  test    byte ptr cs:_bidGblFlags, 2
0x18001cb35  jz      short loc_18001CB7A
0x18001cb37  mov     rax, cs:?_bidPtrSA_030_3438@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_3438
0x18001cb3e  test    rax, rax
0x18001cb41  jz      short loc_18001CB7A
0x18001cb43  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001cb4b  jz      short loc_18001CB7A
0x18001cb4d  mov     r9, cs:?_bidPtrSA_030_3438@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_3438
0x18001cb54  mov     r8d, 35B800h
0x18001cb5a  mov     rdx, cs:?_bidSrcFileA@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidSrcFileA
0x18001cb61  mov     rcx, cs:_bidID
0x18001cb68  mov     rax, cs:off_180248050
0x18001cb6f  mov     [rsp+38h+var_18], rbx
0x18001cb74  call    cs:__guard_dispatch_icall_fptr
0x18001cb7a  call    cs:__imp_RevertToSelf
0x18001cb80  test    eax, eax
0x18001cb82  jz      short loc_18001CBE4
0x18001cb84  test    byte ptr cs:_bidGblFlags, 2
0x18001cb8b  jz      loc_18001CD51
0x18001cb91  mov     rax, cs:?_bidPtrSA_030_3442@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_3442
0x18001cb98  test    rax, rax
0x18001cb9b  jz      loc_18001CD51
0x18001cba1  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001cba9  jz      loc_18001CD51
0x18001cbaf  mov     r9, cs:?_bidPtrSA_030_3442@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_3442
0x18001cbb6  mov     r8d, 35C800h
0x18001cbbc  mov     rdx, cs:?_bidSrcFileA@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidSrcFileA
0x18001cbc3  mov     rcx, cs:_bidID
0x18001cbca  mov     rax, cs:off_180248050
0x18001cbd1  mov     [rsp+38h+var_18], rbx
0x18001cbd6  call    cs:__guard_dispatch_icall_fptr
0x18001cbdc  mov     eax, ebx
0x18001cbde  add     rsp, 30h
0x18001cbe2  pop     rbx
0x18001cbe3  retn
0x18001cbe4  call    cs:__imp_GetLastError
0x18001cbea  mov     r9d, eax
0x18001cbed  test    eax, eax
0x18001cbef  jle     short loc_18001CBFC
0x18001cbf1  movzx   r9d, ax
0x18001cbf5  or      r9d, 80070000h
0x18001cbfc  test    byte ptr cs:_bidGblFlags, 2
0x18001cc03  mov     ebx, r9d
0x18001cc06  jz      loc_18001CD51
0x18001cc0c  mov     rax, cs:?_bidPtrSA_030_3447@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_3447
0x18001cc13  test    rax, rax
0x18001cc16  jz      loc_18001CD51
0x18001cc1c  mov     r8, cs:?_bidPtrSA_030_3447@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_3447
0x18001cc23  mov     edx, 35DC00h
0x18001cc28  mov     rcx, cs:?_bidSrcFileA@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidSrcFileA
0x18001cc2f  call    _bidTraceW
0x18001cc34  mov     eax, ebx
0x18001cc36  add     rsp, 30h
0x18001cc3a  pop     rbx
0x18001cc3b  retn
0x18001cc3c  xor     ecx, ecx; Thread
0x18001cc3e  call    cs:__imp_SetThreadToken
0x18001cc44  test    eax, eax
0x18001cc46  jnz     short loc_18001CCA0
0x18001cc48  call    cs:__imp_GetLastError
0x18001cc4e  mov     r9d, eax
0x18001cc51  test    eax, eax
0x18001cc53  jle     short loc_18001CC60
0x18001cc55  movzx   r9d, ax
0x18001cc59  or      r9d, 80070000h
0x18001cc60  test    byte ptr cs:_bidGblFlags, 2
0x18001cc67  mov     ebx, r9d
0x18001cc6a  jz      loc_18001CD51
0x18001cc70  mov     rax, cs:?_bidPtrSA_030_3455@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_3455
0x18001cc77  test    rax, rax
0x18001cc7a  jz      loc_18001CD51
0x18001cc80  mov     r8, cs:?_bidPtrSA_030_3455@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_3455
0x18001cc87  mov     edx, 35FC00h
0x18001cc8c  mov     rcx, cs:?_bidSrcFileA@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidSrcFileA
0x18001cc93  call    _bidTraceW
0x18001cc98  mov     eax, ebx
0x18001cc9a  add     rsp, 30h
0x18001cc9e  pop     rbx
0x18001cc9f  retn
0x18001cca0  test    byte ptr cs:_bidGblFlags, 2
0x18001cca7  jz      loc_18001CD51
0x18001ccad  mov     rax, cs:?_bidPtrSA_030_3459@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_3459
0x18001ccb4  test    rax, rax
0x18001ccb7  jz      loc_18001CD51
0x18001ccbd  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001ccc5  jz      loc_18001CD51
0x18001cccb  mov     r9, cs:?_bidPtrSA_030_3459@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_3459
0x18001ccd2  mov     r8d, 360C00h
0x18001ccd8  mov     rdx, cs:?_bidSrcFileA@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidSrcFileA
0x18001ccdf  mov     rcx, cs:_bidID
0x18001cce6  mov     rax, cs:off_180248050
0x18001cced  mov     [rsp+38h+var_18], rbx
0x18001ccf2  call    cs:__guard_dispatch_icall_fptr
0x18001ccf8  mov     eax, ebx
0x18001ccfa  add     rsp, 30h
0x18001ccfe  pop     rbx
0x18001ccff  retn
0x18001cd00  test    byte ptr cs:_bidGblFlags, 2
0x18001cd07  jz      short loc_18001CD4C
0x18001cd09  mov     rax, cs:?_bidPtrSA_030_3465@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_3465
0x18001cd10  test    rax, rax
0x18001cd13  jz      short loc_18001CD4C
0x18001cd15  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001cd1d  jz      short loc_18001CD4C
0x18001cd1f  mov     r9, cs:?_bidPtrSA_030_3465@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_3465
0x18001cd26  mov     r8d, 362400h
0x18001cd2c  mov     rdx, cs:?_bidSrcFileA@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidSrcFileA
0x18001cd33  mov     rcx, cs:_bidID
0x18001cd3a  mov     rax, cs:off_180248050
0x18001cd41  mov     [rsp+38h+var_18], rbx
0x18001cd46  call    cs:__guard_dispatch_icall_fptr
0x18001cd4c  mov     ebx, 80004005h
0x18001cd51  mov     eax, ebx
0x18001cd53  add     rsp, 30h
0x18001cd57  pop     rbx
0x18001cd58  retn
```
