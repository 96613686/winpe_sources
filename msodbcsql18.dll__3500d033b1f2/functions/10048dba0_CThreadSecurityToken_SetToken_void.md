# CThreadSecurityToken::SetToken(void)

- ea: `0x10048dba0`
- end: `0x10048dd88`
- name: `?SetToken@CThreadSecurityToken@@QEBAJXZ`
- size: `488`
- prototype: `__int64 __fastcall(CThreadSecurityToken *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10048c98c`

## callees

- `0x10048dba0`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10048dc4c`
- `KERNEL32!GetLastError` at `0x10048dc97`
- `KERNEL32!GetLastError` at `0x10048dc4c`
- `KERNEL32!GetLastError` at `0x10048dc97`
- `ADVAPI32!RevertToSelf` at `0x10048dc05`
- `ADVAPI32!RevertToSelf` at `0x10048dc05`
- `ADVAPI32!SetThreadToken` at `0x10048dc8d`
- `ADVAPI32!SetThreadToken` at `0x10048dc8d`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::SetToken(CThreadSecurityToken *this)
{
  unsigned int v1; // ebx
  wchar_t *v2; // r9
  __int64 v3; // r8
  signed int LastError; // eax
  wchar_t *v5; // r8
  __int64 v6; // rdx
  signed int v7; // eax

  v1 = 0;
  if ( *(_QWORD *)this == -1 )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`62'::_bidPtrSA_030_4688[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        4800512,
        `CThreadSecurityToken::SetToken'::`62'::_bidPtrSA_030_4688[0],
        0);
    return (unsigned int)-2147467259;
  }
  if ( *((_BYTE *)this + 8) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`13'::_bidPtrSA_030_4659[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        4770816,
        `CThreadSecurityToken::SetToken'::`13'::_bidPtrSA_030_4659[0],
        0);
    if ( RevertToSelf() )
    {
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`23'::_bidPtrSA_030_4663[0] && bidID != -1 )
      {
        v2 = `CThreadSecurityToken::SetToken'::`23'::_bidPtrSA_030_4663[0];
        v3 = 4774912;
LABEL_28:
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(bidID, 0, v3, v2, 0);
        return v1;
      }
      return v1;
    }
    LastError = GetLastError();
    v1 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v1 = LastError;
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_4668[0] )
      return v1;
    v5 = `CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_4668[0];
    v6 = 4780032;
LABEL_23:
    bidTraceW(0, v6, v5, v1);
    return v1;
  }
  if ( !SetThreadToken(0, *(HANDLE *)this) )
  {
    v7 = GetLastError();
    v1 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 <= 0 )
      v1 = v7;
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_4678[0] )
      return v1;
    v5 = `CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_4678[0];
    v6 = 4790272;
    goto LABEL_23;
  }
  if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`53'::_bidPtrSA_030_4682[0] && bidID != -1 )
  {
    v2 = `CThreadSecurityToken::SetToken'::`53'::_bidPtrSA_030_4682[0];
    v3 = 4794368;
    goto LABEL_28;
  }
  return v1;
}

```

## disassembly

```asm
0x10048dba0  push    rbx
0x10048dba2  sub     rsp, 30h
0x10048dba6  mov     rdx, [rcx]; Token
0x10048dba9  xor     ebx, ebx
0x10048dbab  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x10048dbaf  jz      loc_10048DD34
0x10048dbb5  cmp     [rcx+8], bl
0x10048dbb8  jz      loc_10048DC8B
0x10048dbbe  test    byte ptr cs:_bidGblFlags, 2
0x10048dbc5  jz      short loc_10048DC05
0x10048dbc7  mov     rax, cs:?_bidPtrSA_030_4659@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_4659
0x10048dbce  test    rax, rax
0x10048dbd1  jz      short loc_10048DC05
0x10048dbd3  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048dbdb  jz      short loc_10048DC05
0x10048dbdd  mov     r9, cs:?_bidPtrSA_030_4659@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_4659
0x10048dbe4  xor     edx, edx
0x10048dbe6  mov     rcx, cs:_bidID
0x10048dbed  mov     r8d, 48CC00h
0x10048dbf3  mov     rax, cs:off_1005D39E0
0x10048dbfa  and     [rsp+38h+var_18], rbx
0x10048dbff  call    cs:__guard_dispatch_icall_fptr
0x10048dc05  call    cs:__imp_RevertToSelf
0x10048dc0b  test    eax, eax
0x10048dc0d  jz      short loc_10048DC4C
0x10048dc0f  test    byte ptr cs:_bidGblFlags, 2
0x10048dc16  jz      loc_10048DD80
0x10048dc1c  mov     rax, cs:?_bidPtrSA_030_4663@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_4663
0x10048dc23  test    rax, rax
0x10048dc26  jz      loc_10048DD80
0x10048dc2c  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048dc34  jz      loc_10048DD80
0x10048dc3a  mov     r9, cs:?_bidPtrSA_030_4663@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_4663
0x10048dc41  mov     r8d, 48DC00h
0x10048dc47  jmp     loc_10048DD17
0x10048dc4c  call    cs:__imp_GetLastError
0x10048dc52  movzx   ebx, ax
0x10048dc55  or      ebx, 80070000h
0x10048dc5b  test    eax, eax
0x10048dc5d  cmovle  ebx, eax
0x10048dc60  test    byte ptr cs:_bidGblFlags, 2
0x10048dc67  jz      loc_10048DD80
0x10048dc6d  mov     rax, cs:?_bidPtrSA_030_4668@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_4668
0x10048dc74  test    rax, rax
0x10048dc77  jz      loc_10048DD80
0x10048dc7d  mov     r8, cs:?_bidPtrSA_030_4668@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_4668
0x10048dc84  mov     edx, 48F000h
0x10048dc89  jmp     short loc_10048DCD4
0x10048dc8b  xor     ecx, ecx; Thread
0x10048dc8d  call    cs:__imp_SetThreadToken
0x10048dc93  test    eax, eax
0x10048dc95  jnz     short loc_10048DCE3
0x10048dc97  call    cs:__imp_GetLastError
0x10048dc9d  movzx   ebx, ax
0x10048dca0  or      ebx, 80070000h
0x10048dca6  test    eax, eax
0x10048dca8  cmovle  ebx, eax
0x10048dcab  test    byte ptr cs:_bidGblFlags, 2
0x10048dcb2  jz      loc_10048DD80
0x10048dcb8  mov     rax, cs:?_bidPtrSA_030_4678@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_4678
0x10048dcbf  test    rax, rax
0x10048dcc2  jz      loc_10048DD80
0x10048dcc8  mov     r8, cs:?_bidPtrSA_030_4678@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_4678
0x10048dccf  mov     edx, 491800h
0x10048dcd4  mov     r9d, ebx
0x10048dcd7  xor     ecx, ecx
0x10048dcd9  call    _bidTraceW
0x10048dcde  jmp     loc_10048DD80
0x10048dce3  test    byte ptr cs:_bidGblFlags, 2
0x10048dcea  jz      loc_10048DD80
0x10048dcf0  mov     rax, cs:?_bidPtrSA_030_4682@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_4682
0x10048dcf7  test    rax, rax
0x10048dcfa  jz      loc_10048DD80
0x10048dd00  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048dd08  jz      short loc_10048DD80
0x10048dd0a  mov     r9, cs:?_bidPtrSA_030_4682@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_4682
0x10048dd11  mov     r8d, 492800h
0x10048dd17  and     [rsp+38h+var_18], rbx
0x10048dd1c  xor     edx, edx
0x10048dd1e  mov     rax, cs:off_1005D39E0
0x10048dd25  mov     rcx, cs:_bidID
0x10048dd2c  call    cs:__guard_dispatch_icall_fptr
0x10048dd32  jmp     short loc_10048DD80
0x10048dd34  test    byte ptr cs:_bidGblFlags, 2
0x10048dd3b  jz      short loc_10048DD7B
0x10048dd3d  mov     rax, cs:?_bidPtrSA_030_4688@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_4688
0x10048dd44  test    rax, rax
0x10048dd47  jz      short loc_10048DD7B
0x10048dd49  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048dd51  jz      short loc_10048DD7B
0x10048dd53  mov     r9, cs:?_bidPtrSA_030_4688@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_4688
0x10048dd5a  xor     edx, edx
0x10048dd5c  mov     rcx, cs:_bidID
0x10048dd63  mov     r8d, 494000h
0x10048dd69  mov     rax, cs:off_1005D39E0
0x10048dd70  and     [rsp+38h+var_18], rbx
0x10048dd75  call    cs:__guard_dispatch_icall_fptr
0x10048dd7b  mov     ebx, 80004005h
0x10048dd80  mov     eax, ebx
0x10048dd82  add     rsp, 30h
0x10048dd86  pop     rbx
0x10048dd87  retn
```
