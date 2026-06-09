# CUserName::IsAdmin(int *)

- ea: `0x180087ae0`
- end: `0x180087c2f`
- name: `?IsAdmin@CUserName@@UEAAJPEAH@Z`
- size: `335`
- prototype: `__int64 __fastcall(CUserName *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180012650`
- `0x180082efc`
- `0x180087ae0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180087c0c`
- `ntdll!RtlFreeSid` at `0x180087c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bbf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180087baf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180087baf`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087b70`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087b70`

## string_xrefs

- `0x180087b14`: `No token`
- `0x180087b46`: `CUtil::CreateAdminSid failed: 0x%x in %s`

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
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&DuplicateTokenHandle);
  return v6;
}

```

## disassembly

```asm
0x180087ae0  push    rbp
0x180087ae2  push    rbx
0x180087ae3  push    rsi
0x180087ae4  push    rdi
0x180087ae5  push    r14
0x180087ae7  mov     rbp, rsp
0x180087aea  sub     rsp, 20h
0x180087aee  xor     esi, esi
0x180087af0  mov     r14, rdx
0x180087af3  test    byte ptr [rcx+640h], 4
0x180087afa  mov     rdi, rcx
0x180087afd  mov     [rbp+SidToCheck], rsi
0x180087b01  mov     [rbp+DuplicateTokenHandle], rsi
0x180087b05  jnz     loc_180087BF6
0x180087b0b  cmp     [rcx+638h], rsi
0x180087b12  jnz     short loc_180087B2D
0x180087b14  lea     rdx, aNoToken; "No token"
0x180087b1b  lea     ecx, [rsi+8]; int
0x180087b1e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180087b23  mov     ebx, 800703F0h
0x180087b28  jmp     loc_180087C18
0x180087b2d  lea     rcx, [rbp+SidToCheck]; void **
0x180087b31  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x180087b36  mov     ebx, eax
0x180087b38  test    eax, eax
0x180087b3a  jns     short loc_180087B60
0x180087b3c  lea     r9, aCusernameIsadm; "CUserName::IsAdmin"
0x180087b43  mov     r8d, eax
0x180087b46  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x180087b4d  mov     ecx, 8; int
0x180087b52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180087b57  mov     rsi, [rbp+SidToCheck]
0x180087b5b  jmp     loc_180087C04
0x180087b60  mov     rcx, [rdi+638h]; ExistingTokenHandle
0x180087b67  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x180087b6b  mov     edx, 1; ImpersonationLevel
0x180087b70  call    cs:__imp_DuplicateToken
0x180087b77  nop     dword ptr [rax+rax+00h]
0x180087b7c  test    eax, eax
0x180087b7e  jnz     short loc_180087B9D
0x180087b80  call    cs:__imp_GetLastError
0x180087b87  nop     dword ptr [rax+rax+00h]
0x180087b8c  mov     ebx, eax
0x180087b8e  test    eax, eax
0x180087b90  jle     short loc_180087B57
0x180087b92  movzx   ebx, ax
0x180087b95  or      ebx, 80070000h
0x180087b9b  jmp     short loc_180087B57
0x180087b9d  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x180087ba1  lea     r8, [rbp+IsMember]; IsMember
0x180087ba5  mov     [rbp+IsMember], esi
0x180087ba8  mov     rsi, [rbp+SidToCheck]
0x180087bac  mov     rdx, rsi; SidToCheck
0x180087baf  call    cs:__imp_CheckTokenMembership
0x180087bb6  nop     dword ptr [rax+rax+00h]
0x180087bbb  test    eax, eax
0x180087bbd  jnz     short loc_180087BDC
0x180087bbf  call    cs:__imp_GetLastError
0x180087bc6  nop     dword ptr [rax+rax+00h]
0x180087bcb  mov     ebx, eax
0x180087bcd  test    eax, eax
0x180087bcf  jle     short loc_180087C04
0x180087bd1  movzx   ebx, ax
0x180087bd4  or      ebx, 80070000h
0x180087bda  jmp     short loc_180087C04
0x180087bdc  and     dword ptr [rdi+0A78h], 0FFFFFFFEh
0x180087be3  mov     eax, [rbp+IsMember]
0x180087be6  and     eax, 1
0x180087be9  or      [rdi+0A78h], eax
0x180087bef  or      dword ptr [rdi+640h], 4
0x180087bf6  mov     eax, [rdi+0A78h]
0x180087bfc  and     eax, 1
0x180087bff  mov     [r14], eax
0x180087c02  xor     ebx, ebx
0x180087c04  test    rsi, rsi
0x180087c07  jz      short loc_180087C18
0x180087c09  mov     rcx, rsi; Sid
0x180087c0c  call    cs:__imp_RtlFreeSid
0x180087c13  nop     dword ptr [rax+rax+00h]
0x180087c18  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x180087c1c  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180087c21  mov     eax, ebx
0x180087c23  add     rsp, 20h
0x180087c27  pop     r14
0x180087c29  pop     rdi
0x180087c2a  pop     rsi
0x180087c2b  pop     rbx
0x180087c2c  pop     rbp
0x180087c2d  retn
```
