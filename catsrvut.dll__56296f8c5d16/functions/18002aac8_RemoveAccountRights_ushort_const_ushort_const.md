# RemoveAccountRights(ushort const *,ushort const *)

- ea: `0x18002aac8`
- end: `0x18002ac53`
- name: `?RemoveAccountRights@@YAJPEBG0@Z`
- size: `395`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027074`

## callees

- `0x18002a964`
- `0x18002aac8`

## import_xrefs

- `msvcrt!free` at `0x18002ac31`
- `msvcrt!free` at `0x18002ac31`
- `netutils!NetApiBufferFree` at `0x18002ac21`
- `netutils!NetApiBufferFree` at `0x18002ac21`
- `logoncli!NetGetDCName` at `0x18002ab80`
- `logoncli!NetGetDCName` at `0x18002ab80`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002ab67`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002ac08`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002ab67`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002ac08`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002abc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ac40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002abc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ac40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002ab15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002abe7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002ab15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002abe7`

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
0x18002aac8  mov     [rsp-18h+PolicyHandle], rdx
0x18002aacd  push    rbp
0x18002aace  push    rbx
0x18002aacf  push    rsi
0x18002aad0  mov     rbp, rsp
0x18002aad3  sub     rsp, 80h
0x18002aada  xorps   xmm0, xmm0
0x18002aadd  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002aae1  xor     esi, esi
0x18002aae3  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002aae7  mov     rbx, rcx
0x18002aaea  mov     [rbp+PolicyHandle], rsi
0x18002aaee  xorps   xmm1, xmm1
0x18002aaf1  mov     [rbp+AccountSid], rsi
0x18002aaf5  xor     ecx, ecx; SystemName
0x18002aaf7  mov     [rbp+bufptr], rsi
0x18002aafb  mov     r8d, 811h; DesiredAccess
0x18002ab01  movups  xmmword ptr [rbp+UserRights.Length], xmm0
0x18002ab05  movups  xmmword ptr [rbp+SystemName.Length], xmm1
0x18002ab09  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002ab0d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002ab11  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ab15  call    cs:__imp_LsaOpenPolicy
0x18002ab1b  test    eax, eax
0x18002ab1d  jz      short loc_18002AB28
0x18002ab1f  bts     eax, 1Ch
0x18002ab23  jmp     loc_18002AC48
0x18002ab28  lea     rdx, [rbp+AccountSid]
0x18002ab2c  mov     rcx, rbx; Str
0x18002ab2f  call    GetUserSID
0x18002ab34  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002ab38  mov     ebx, eax
0x18002ab3a  test    eax, eax
0x18002ab3c  jnz     loc_18002AC40
0x18002ab42  mov     rdx, [rbp+AccountSid]; AccountSid
0x18002ab46  lea     rax, aSebatchlogonri; "SeBatchLogonRight"
0x18002ab4d  lea     r9, [rbp+UserRights]; UserRights
0x18002ab51  mov     [rbp+UserRights.Buffer], rax
0x18002ab55  xor     r8d, r8d; AllRights
0x18002ab58  mov     dword ptr [rbp+UserRights.Length], 240022h
0x18002ab5f  mov     [rsp+80h+CountOfRights], 1; CountOfRights
0x18002ab67  call    cs:__imp_LsaRemoveAccountRights
0x18002ab6d  cmp     eax, 0C0000187h
0x18002ab72  jnz     loc_18002AC12
0x18002ab78  lea     r8, [rbp+bufptr]; bufptr
0x18002ab7c  xor     edx, edx; domainname
0x18002ab7e  xor     ecx, ecx; servername
0x18002ab80  call    cs:__imp_NetGetDCName
0x18002ab86  test    eax, eax
0x18002ab88  jz      short loc_18002AB94
0x18002ab8a  mov     ebx, 8000FFFFh
0x18002ab8f  jmp     loc_18002AC18
0x18002ab94  mov     rcx, [rbp+bufptr]
0x18002ab98  add     rcx, 4
0x18002ab9c  mov     [rbp+SystemName.Buffer], rcx
0x18002aba0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aba4  inc     rax
0x18002aba7  cmp     [rcx+rax*2], si
0x18002abab  jnz     short loc_18002ABA4
0x18002abad  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002abb1  add     ax, ax
0x18002abb4  mov     [rbp+SystemName.Length], ax
0x18002abb8  add     ax, 2
0x18002abbc  mov     [rbp+SystemName.MaximumLength], ax
0x18002abc0  call    cs:__imp_LsaClose
0x18002abc6  xorps   xmm0, xmm0
0x18002abc9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002abcd  mov     r8d, 811h; DesiredAccess
0x18002abd3  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002abd7  lea     rcx, [rbp+SystemName]; SystemName
0x18002abdb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002abdf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002abe3  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002abe7  call    cs:__imp_LsaOpenPolicy
0x18002abed  test    eax, eax
0x18002abef  jnz     short loc_18002AC12
0x18002abf1  mov     rdx, [rbp+AccountSid]; AccountSid
0x18002abf5  lea     r9, [rbp+UserRights]; UserRights
0x18002abf9  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002abfd  xor     r8d, r8d; AllRights
0x18002ac00  mov     [rsp+80h+CountOfRights], 1; CountOfRights
0x18002ac08  call    cs:__imp_LsaRemoveAccountRights
0x18002ac0e  test    eax, eax
0x18002ac10  jz      short loc_18002AC18
0x18002ac12  mov     ebx, eax
0x18002ac14  bts     ebx, 1Ch
0x18002ac18  mov     rcx, [rbp+bufptr]; Buffer
0x18002ac1c  test    rcx, rcx
0x18002ac1f  jz      short loc_18002AC27
0x18002ac21  call    cs:__imp_NetApiBufferFree
0x18002ac27  cmp     [rbp+AccountSid], rsi
0x18002ac2b  jz      short loc_18002AC37
0x18002ac2d  mov     rcx, [rbp+AccountSid]; Block
0x18002ac31  call    cs:__imp_free
0x18002ac37  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002ac3b  test    rcx, rcx
0x18002ac3e  jz      short loc_18002AC46
0x18002ac40  call    cs:__imp_LsaClose
0x18002ac46  mov     eax, ebx
0x18002ac48  add     rsp, 80h
0x18002ac4f  pop     rsi
0x18002ac50  pop     rbx
0x18002ac51  pop     rbp
0x18002ac52  retn
```
