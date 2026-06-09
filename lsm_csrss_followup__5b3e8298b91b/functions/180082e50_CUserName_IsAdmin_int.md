# CUserName::IsAdmin(int *)

- ea: `0x180082e50`
- end: `0x180082f86`
- name: `?IsAdmin@CUserName@@UEAAJPEAH@Z`
- size: `310`
- prototype: `__int64 __fastcall(CUserName *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18007e504`
- `0x180082e50`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180082f64`
- `ntdll!RtlFreeSid` at `0x180082f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082f73`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180082f13`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180082f13`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180082ee0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180082ee0`

## string_xrefs

- `0x180082e84`: `No token`
- `0x180082eb6`: `CUtil::CreateAdminSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::IsAdmin(CUserName *this, int *a2)
{
  PSID v2; // rsi
  bool v4; // zf
  unsigned int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  WINBOOL IsMember; // [rsp+50h] [rbp+30h] BYREF
  PSID SidToCheck; // [rsp+60h] [rbp+40h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v4 = (*((_BYTE *)this + 1600) & 4) == 0;
  SidToCheck = 0;
  DuplicateTokenHandle = 0;
  if ( v4 )
  {
    if ( !*((_QWORD *)this + 199) )
    {
      _DbgPrintMessage(8, "No token");
      v6 = -2147023888;
      goto LABEL_17;
    }
    v7 = CUtils::CreateAdminSid(&SidToCheck);
    v6 = v7;
    if ( v7 < 0 )
    {
      _DbgPrintMessage(8, "CUtil::CreateAdminSid failed: 0x%x in %s", v7, "CUserName::IsAdmin");
LABEL_6:
      v2 = SidToCheck;
      goto LABEL_15;
    }
    if ( !DuplicateToken(*((HANDLE *)this + 199), SecurityIdentification, &DuplicateTokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_6;
    }
    IsMember = 0;
    v2 = SidToCheck;
    if ( !CheckTokenMembership(DuplicateTokenHandle, SidToCheck, &IsMember) )
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_15;
    }
    *((_DWORD *)this + 670) &= ~1u;
    *((_DWORD *)this + 670) |= IsMember & 1;
    *((_DWORD *)this + 400) |= 4u;
  }
  *a2 = *((_DWORD *)this + 670) & 1;
  v6 = 0;
LABEL_15:
  if ( v2 )
    RtlFreeSid(v2);
LABEL_17:
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  return v6;
}

```

## disassembly

```asm
0x180082e50  push    rbp
0x180082e52  push    rbx
0x180082e53  push    rsi
0x180082e54  push    rdi
0x180082e55  push    r14
0x180082e57  mov     rbp, rsp
0x180082e5a  sub     rsp, 20h
0x180082e5e  xor     esi, esi
0x180082e60  mov     r14, rdx
0x180082e63  test    byte ptr [rcx+640h], 4
0x180082e6a  mov     rdi, rcx
0x180082e6d  mov     [rbp+SidToCheck], rsi
0x180082e71  mov     [rbp+DuplicateTokenHandle], rsi
0x180082e75  jnz     loc_180082F4E
0x180082e7b  cmp     [rcx+638h], rsi
0x180082e82  jnz     short loc_180082E9D
0x180082e84  lea     rdx, aNoToken; "No token"
0x180082e8b  lea     ecx, [rsi+8]; int
0x180082e8e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082e93  mov     ebx, 800703F0h
0x180082e98  jmp     loc_180082F6A
0x180082e9d  lea     rcx, [rbp+SidToCheck]; void **
0x180082ea1  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x180082ea6  mov     ebx, eax
0x180082ea8  test    eax, eax
0x180082eaa  jns     short loc_180082ED0
0x180082eac  lea     r9, aCusernameIsadm; "CUserName::IsAdmin"
0x180082eb3  mov     r8d, eax
0x180082eb6  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x180082ebd  mov     ecx, 8; int
0x180082ec2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082ec7  mov     rsi, [rbp+SidToCheck]
0x180082ecb  jmp     loc_180082F5C
0x180082ed0  mov     rcx, [rdi+638h]; ExistingTokenHandle
0x180082ed7  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x180082edb  mov     edx, 1; ImpersonationLevel
0x180082ee0  call    cs:__imp_DuplicateToken
0x180082ee6  test    eax, eax
0x180082ee8  jnz     short loc_180082F01
0x180082eea  call    cs:__imp_GetLastError
0x180082ef0  mov     ebx, eax
0x180082ef2  test    eax, eax
0x180082ef4  jle     short loc_180082EC7
0x180082ef6  movzx   ebx, ax
0x180082ef9  or      ebx, 80070000h
0x180082eff  jmp     short loc_180082EC7
0x180082f01  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x180082f05  lea     r8, [rbp+IsMember]; IsMember
0x180082f09  mov     [rbp+IsMember], esi
0x180082f0c  mov     rsi, [rbp+SidToCheck]
0x180082f10  mov     rdx, rsi; SidToCheck
0x180082f13  call    cs:__imp_CheckTokenMembership
0x180082f19  test    eax, eax
0x180082f1b  jnz     short loc_180082F34
0x180082f1d  call    cs:__imp_GetLastError
0x180082f23  mov     ebx, eax
0x180082f25  test    eax, eax
0x180082f27  jle     short loc_180082F5C
0x180082f29  movzx   ebx, ax
0x180082f2c  or      ebx, 80070000h
0x180082f32  jmp     short loc_180082F5C
0x180082f34  and     dword ptr [rdi+0A78h], 0FFFFFFFEh
0x180082f3b  mov     eax, [rbp+IsMember]
0x180082f3e  and     eax, 1
0x180082f41  or      [rdi+0A78h], eax
0x180082f47  or      dword ptr [rdi+640h], 4
0x180082f4e  mov     eax, [rdi+0A78h]
0x180082f54  and     eax, 1
0x180082f57  mov     [r14], eax
0x180082f5a  xor     ebx, ebx
0x180082f5c  test    rsi, rsi
0x180082f5f  jz      short loc_180082F6A
0x180082f61  mov     rcx, rsi; Sid
0x180082f64  call    cs:__imp_RtlFreeSid
0x180082f6a  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x180082f6e  test    rcx, rcx
0x180082f71  jz      short loc_180082F79
0x180082f73  call    cs:__imp_CloseHandle
0x180082f79  mov     eax, ebx
0x180082f7b  add     rsp, 20h
0x180082f7f  pop     r14
0x180082f81  pop     rdi
0x180082f82  pop     rsi
0x180082f83  pop     rbx
0x180082f84  pop     rbp
0x180082f85  retn
```
