# RemoveAccountRights(ushort const *,ushort const *)

- ea: `0x180038494`
- end: `0x18003861f`
- name: `?RemoveAccountRights@@YAJPEBG0@Z`
- size: `395`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034424`

## callees

- `0x180038330`
- `0x180038494`

## import_xrefs

- `msvcrt!free` at `0x1800385fd`
- `msvcrt!free` at `0x1800385fd`
- `logoncli!NetGetDCName` at `0x18003854c`
- `logoncli!NetGetDCName` at `0x18003854c`
- `netutils!NetApiBufferFree` at `0x1800385ed`
- `netutils!NetApiBufferFree` at `0x1800385ed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800384e1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800385b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800384e1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800385b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x180038533`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x1800385d4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x180038533`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x1800385d4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003858c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003860c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003858c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003860c`

## pseudocode

```c
int __fastcall RemoveAccountRights(wchar_t *Str, const unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  int UserSID; // eax
  PVOID v6; // rcx
  int v7; // ebx
  NTSTATUS v8; // eax
  __int64 v9; // rax
  struct _LSA_UNICODE_STRING UserRights; // [rsp+30h] [rbp-50h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+A8h] [rbp+28h] BYREF
  PSID AccountSid; // [rsp+B0h] [rbp+30h]
  LPBYTE bufptr; // [rsp+B8h] [rbp+38h] BYREF

  PolicyHandle = 0;
  AccountSid = 0;
  bufptr = 0;
  UserRights = 0;
  SystemName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x811u, &PolicyHandle);
  if ( v3 )
    return v3 | 0x10000000;
  UserSID = GetUserSID(Str);
  v6 = PolicyHandle;
  v7 = UserSID;
  if ( !UserSID )
  {
    UserRights.Buffer = L"SeBatchLogonRight";
    *(_DWORD *)&UserRights.Length = 2359330;
    v8 = LsaRemoveAccountRights(PolicyHandle, AccountSid, 0, &UserRights, 1u);
    if ( v8 != -1073741433 )
      goto LABEL_11;
    if ( NetGetDCName(0, 0, &bufptr) )
    {
      v7 = -2147418113;
      goto LABEL_12;
    }
    SystemName.Buffer = (PWSTR)(bufptr + 4);
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&bufptr[2 * v9 + 4] );
    SystemName.Length = 2 * v9;
    SystemName.MaximumLength = 2 * v9 + 2;
    LsaClose(PolicyHandle);
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v8 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x811u, &PolicyHandle);
    if ( v8 || (v8 = LsaRemoveAccountRights(PolicyHandle, AccountSid, 0, &UserRights, 1u)) != 0 )
LABEL_11:
      v7 = v8 | 0x10000000;
LABEL_12:
    if ( bufptr )
      NetApiBufferFree(bufptr);
    if ( AccountSid )
      free(AccountSid);
    v6 = PolicyHandle;
    if ( !PolicyHandle )
      return v7;
  }
  LsaClose(v6);
  return v7;
}

```

## disassembly

```asm
0x180038494  mov     [rsp-18h+PolicyHandle], rdx
0x180038499  push    rbp
0x18003849a  push    rbx
0x18003849b  push    rsi
0x18003849c  mov     rbp, rsp
0x18003849f  sub     rsp, 80h
0x1800384a6  xorps   xmm0, xmm0
0x1800384a9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800384ad  xor     esi, esi
0x1800384af  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800384b3  mov     rbx, rcx
0x1800384b6  mov     [rbp+PolicyHandle], rsi
0x1800384ba  xorps   xmm1, xmm1
0x1800384bd  mov     [rbp+AccountSid], rsi
0x1800384c1  xor     ecx, ecx; SystemName
0x1800384c3  mov     [rbp+bufptr], rsi
0x1800384c7  mov     r8d, 811h; DesiredAccess
0x1800384cd  movups  xmmword ptr [rbp+UserRights.Length], xmm0
0x1800384d1  movups  xmmword ptr [rbp+SystemName.Length], xmm1
0x1800384d5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800384d9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800384dd  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800384e1  call    cs:__imp_LsaOpenPolicy
0x1800384e7  test    eax, eax
0x1800384e9  jz      short loc_1800384F4
0x1800384eb  bts     eax, 1Ch
0x1800384ef  jmp     loc_180038614
0x1800384f4  lea     rdx, [rbp+AccountSid]
0x1800384f8  mov     rcx, rbx; Str
0x1800384fb  call    GetUserSID
0x180038500  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180038504  mov     ebx, eax
0x180038506  test    eax, eax
0x180038508  jnz     loc_18003860C
0x18003850e  mov     rdx, [rbp+AccountSid]; AccountSid
0x180038512  lea     rax, aSebatchlogonri; "SeBatchLogonRight"
0x180038519  lea     r9, [rbp+UserRights]; UserRights
0x18003851d  mov     [rbp+UserRights.Buffer], rax
0x180038521  xor     r8d, r8d; AllRights
0x180038524  mov     dword ptr [rbp+UserRights.Length], 240022h
0x18003852b  mov     [rsp+80h+CountOfRights], 1; CountOfRights
0x180038533  call    cs:__imp_LsaRemoveAccountRights
0x180038539  cmp     eax, 0C0000187h
0x18003853e  jnz     loc_1800385DE
0x180038544  lea     r8, [rbp+bufptr]; bufptr
0x180038548  xor     edx, edx; domainname
0x18003854a  xor     ecx, ecx; servername
0x18003854c  call    cs:__imp_NetGetDCName
0x180038552  test    eax, eax
0x180038554  jz      short loc_180038560
0x180038556  mov     ebx, 8000FFFFh
0x18003855b  jmp     loc_1800385E4
0x180038560  mov     rcx, [rbp+bufptr]
0x180038564  add     rcx, 4
0x180038568  mov     [rbp+SystemName.Buffer], rcx
0x18003856c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038570  inc     rax
0x180038573  cmp     [rcx+rax*2], si
0x180038577  jnz     short loc_180038570
0x180038579  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18003857d  add     ax, ax
0x180038580  mov     [rbp+SystemName.Length], ax
0x180038584  add     ax, 2
0x180038588  mov     [rbp+SystemName.MaximumLength], ax
0x18003858c  call    cs:__imp_LsaClose
0x180038592  xorps   xmm0, xmm0
0x180038595  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180038599  mov     r8d, 811h; DesiredAccess
0x18003859f  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800385a3  lea     rcx, [rbp+SystemName]; SystemName
0x1800385a7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800385ab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800385af  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800385b3  call    cs:__imp_LsaOpenPolicy
0x1800385b9  test    eax, eax
0x1800385bb  jnz     short loc_1800385DE
0x1800385bd  mov     rdx, [rbp+AccountSid]; AccountSid
0x1800385c1  lea     r9, [rbp+UserRights]; UserRights
0x1800385c5  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800385c9  xor     r8d, r8d; AllRights
0x1800385cc  mov     [rsp+80h+CountOfRights], 1; CountOfRights
0x1800385d4  call    cs:__imp_LsaRemoveAccountRights
0x1800385da  test    eax, eax
0x1800385dc  jz      short loc_1800385E4
0x1800385de  mov     ebx, eax
0x1800385e0  bts     ebx, 1Ch
0x1800385e4  mov     rcx, [rbp+bufptr]; Buffer
0x1800385e8  test    rcx, rcx
0x1800385eb  jz      short loc_1800385F3
0x1800385ed  call    cs:__imp_NetApiBufferFree
0x1800385f3  cmp     [rbp+AccountSid], rsi
0x1800385f7  jz      short loc_180038603
0x1800385f9  mov     rcx, [rbp+AccountSid]; Block
0x1800385fd  call    cs:__imp_free
0x180038603  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180038607  test    rcx, rcx
0x18003860a  jz      short loc_180038612
0x18003860c  call    cs:__imp_LsaClose
0x180038612  mov     eax, ebx
0x180038614  add     rsp, 80h
0x18003861b  pop     rsi
0x18003861c  pop     rbx
0x18003861d  pop     rbp
0x18003861e  retn
```
