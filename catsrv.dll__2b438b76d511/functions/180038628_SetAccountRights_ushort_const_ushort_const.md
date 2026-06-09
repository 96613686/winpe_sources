# SetAccountRights(ushort const *,ushort const *)

- ea: `0x180038628`
- end: `0x180038853`
- name: `?SetAccountRights@@YAJPEBG0@Z`
- size: `555`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033df0`
- `0x180034424`

## callees

- `0x180038330`
- `0x180038628`

## import_xrefs

- `msvcrt!free` at `0x180038824`
- `msvcrt!free` at `0x180038824`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038728`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038728`
- `logoncli!NetGetDCName` at `0x180038777`
- `logoncli!NetGetDCName` at `0x180038777`
- `netutils!NetApiBufferFree` at `0x180038814`
- `netutils!NetApiBufferFree` at `0x180038814`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003868a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800387d5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003868a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800387d5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x1800386e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x1800386e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800387ae`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180038833`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800387ae`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180038833`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180038805`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180038805`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18003874d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18003874d`

## pseudocode

```c
int __fastcall SetAccountRights(wchar_t *Str, const unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  int UserSID; // ebx
  PVOID v6; // rcx
  int i; // r14d
  ULONG j; // edi
  NTSTATUS v9; // eax
  __int64 v10; // rax
  PLSA_UNICODE_STRING UserRights; // [rsp+30h] [rbp-29h] BYREF
  LPBYTE bufptr; // [rsp+38h] [rbp-21h] BYREF
  PCNZWCH lpString2[2]; // [rsp+40h] [rbp-19h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+50h] [rbp-9h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  ULONG CountOfRights; // [rsp+C8h] [rbp+6Fh] BYREF
  int v17; // [rsp+CCh] [rbp+73h]
  PVOID PolicyHandle; // [rsp+D0h] [rbp+77h] BYREF
  PSID AccountSid; // [rsp+D8h] [rbp+7Fh]

  v17 = HIDWORD(a2);
  PolicyHandle = 0;
  AccountSid = 0;
  bufptr = 0;
  UserRights = 0;
  CountOfRights = 0;
  *(_OWORD *)lpString2 = 0;
  SystemName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x811u, &PolicyHandle);
  if ( v3 )
    return v3 | 0x10000000;
  UserSID = GetUserSID(Str);
  if ( UserSID )
  {
    v6 = PolicyHandle;
  }
  else
  {
    LODWORD(lpString2[0]) = 2359330;
    lpString2[1] = L"SeBatchLogonRight";
    for ( i = 0; ; i = 1 )
    {
      if ( !LsaEnumerateAccountRights(PolicyHandle, AccountSid, &UserRights, &CountOfRights) )
      {
        for ( j = 0; j < CountOfRights; ++j )
        {
          if ( CompareStringW(
                 0x400u,
                 1u,
                 UserRights[j].Buffer,
                 UserRights[j].Length >> 1,
                 lpString2[1],
                 LOWORD(lpString2[0]) >> 1) == 2 )
          {
            UserSID = 1;
            goto LABEL_22;
          }
        }
      }
      v9 = LsaAddAccountRights(PolicyHandle, AccountSid, (PLSA_UNICODE_STRING)lpString2, 1u);
      if ( !v9 )
        break;
      if ( v9 != -1073741433 || i )
        goto LABEL_21;
      if ( NetGetDCName(0, 0, &bufptr) )
      {
        UserSID = -2147418113;
        break;
      }
      SystemName.Buffer = (PWSTR)(bufptr + 4);
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&bufptr[2 * v10 + 4] );
      SystemName.Length = 2 * v10;
      SystemName.MaximumLength = 2 * v10 + 2;
      LsaClose(PolicyHandle);
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v9 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x811u, &PolicyHandle);
      if ( v9 )
      {
LABEL_21:
        UserSID = v9 | 0x10000000;
        break;
      }
    }
LABEL_22:
    if ( UserRights )
      LsaFreeMemory(UserRights);
    if ( bufptr )
      NetApiBufferFree(bufptr);
    if ( AccountSid )
      free(AccountSid);
    v6 = PolicyHandle;
    if ( !PolicyHandle )
      return UserSID;
  }
  LsaClose(v6);
  return UserSID;
}

```

## disassembly

```asm
0x180038628  mov     [rsp-8+arg_0], rbx
0x18003862d  mov     qword ptr [rsp-8+CountOfRights], rdx
0x180038632  push    rbp
0x180038633  push    rdi
0x180038634  push    r13
0x180038636  push    r14
0x180038638  push    r15
0x18003863a  lea     rbp, [rsp-37h]
0x18003863f  sub     rsp, 90h
0x180038646  xor     r15d, r15d
0x180038649  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18003864d  xorps   xmm0, xmm0
0x180038650  mov     [rbp+57h+PolicyHandle], r15
0x180038654  mov     rbx, rcx
0x180038657  mov     [rbp+57h+AccountSid], r15
0x18003865b  xorps   xmm1, xmm1
0x18003865e  mov     [rbp+57h+bufptr], r15
0x180038662  xor     ecx, ecx; SystemName
0x180038664  mov     [rbp+57h+UserRights], r15
0x180038668  mov     r8d, 811h; DesiredAccess
0x18003866e  mov     [rbp+57h+CountOfRights], r15d
0x180038672  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180038676  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18003867a  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm1
0x18003867e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180038682  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180038686  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003868a  call    cs:__imp_LsaOpenPolicy
0x180038690  test    eax, eax
0x180038692  jz      short loc_18003869D
0x180038694  bts     eax, 1Ch
0x180038698  jmp     loc_18003883B
0x18003869d  lea     rdx, [rbp+57h+AccountSid]
0x1800386a1  mov     rcx, rbx; Str
0x1800386a4  call    GetUserSID
0x1800386a9  mov     ebx, eax
0x1800386ab  test    eax, eax
0x1800386ad  jz      short loc_1800386B8
0x1800386af  mov     rcx, [rbp+57h+PolicyHandle]
0x1800386b3  jmp     loc_180038833
0x1800386b8  lea     rax, aSebatchlogonri; "SeBatchLogonRight"
0x1800386bf  mov     dword ptr [rbp+57h+var_70], 240022h
0x1800386c6  mov     [rbp+57h+var_70+8], rax
0x1800386ca  mov     r14d, r15d
0x1800386cd  mov     r13d, 2
0x1800386d3  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x1800386d7  lea     r9, [rbp+57h+CountOfRights]; CountOfRights
0x1800386db  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800386df  lea     r8, [rbp+57h+UserRights]; UserRights
0x1800386e3  call    cs:__imp_LsaEnumerateAccountRights
0x1800386e9  test    eax, eax
0x1800386eb  jnz     short loc_18003873B
0x1800386ed  mov     edi, r15d
0x1800386f0  cmp     edi, [rbp+57h+CountOfRights]
0x1800386f3  jnb     short loc_18003873B
0x1800386f5  mov     r8, [rbp+57h+UserRights]
0x1800386f9  mov     edx, 1; dwCmpFlags
0x1800386fe  movzx   eax, word ptr [rbp+57h+var_70]
0x180038702  shr     eax, 1
0x180038704  mov     [rsp+0B0h+cchCount2], eax; cchCount2
0x180038708  mov     rax, [rbp+57h+var_70+8]
0x18003870c  mov     ecx, edi
0x18003870e  add     rcx, rcx
0x180038711  mov     [rsp+0B0h+lpString2], rax; lpString2
0x180038716  movzx   r9d, word ptr [r8+rcx*8]
0x18003871b  mov     r8, [r8+rcx*8+8]; lpString1
0x180038720  mov     ecx, 400h; Locale
0x180038725  shr     r9d, 1; cchCount1
0x180038728  call    cs:__imp_CompareStringW
0x18003872e  cmp     eax, r13d
0x180038731  jz      loc_1800387E8
0x180038737  inc     edi
0x180038739  jmp     short loc_1800386F0
0x18003873b  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x18003873f  lea     r8, [rbp+57h+var_70]; UserRights
0x180038743  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180038747  mov     r9d, 1; CountOfRights
0x18003874d  call    cs:__imp_LsaAddAccountRights
0x180038753  test    eax, eax
0x180038755  jz      loc_1800387FC
0x18003875b  cmp     eax, 0C0000187h
0x180038760  jnz     loc_1800387F6
0x180038766  test    r14d, r14d
0x180038769  jnz     loc_1800387F6
0x18003876f  lea     r8, [rbp+57h+bufptr]; bufptr
0x180038773  xor     edx, edx; domainname
0x180038775  xor     ecx, ecx; servername
0x180038777  call    cs:__imp_NetGetDCName
0x18003877d  test    eax, eax
0x18003877f  jnz     short loc_1800387EF
0x180038781  mov     rcx, [rbp+57h+bufptr]
0x180038785  add     rcx, 4
0x180038789  mov     [rbp+57h+SystemName.Buffer], rcx
0x18003878d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038791  inc     rax
0x180038794  cmp     [rcx+rax*2], r15w
0x180038799  jnz     short loc_180038791
0x18003879b  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18003879f  add     ax, ax
0x1800387a2  mov     [rbp+57h+SystemName.Length], ax
0x1800387a6  add     ax, r13w
0x1800387aa  mov     [rbp+57h+SystemName.MaximumLength], ax
0x1800387ae  call    cs:__imp_LsaClose
0x1800387b4  xorps   xmm0, xmm0
0x1800387b7  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800387bb  mov     r8d, 811h; DesiredAccess
0x1800387c1  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800387c5  lea     rcx, [rbp+57h+SystemName]; SystemName
0x1800387c9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800387cd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800387d1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800387d5  call    cs:__imp_LsaOpenPolicy
0x1800387db  test    eax, eax
0x1800387dd  jnz     short loc_1800387F6
0x1800387df  lea     r14d, [rax+1]
0x1800387e3  jmp     loc_1800386D3
0x1800387e8  mov     ebx, 1
0x1800387ed  jmp     short loc_1800387FC
0x1800387ef  mov     ebx, 8000FFFFh
0x1800387f4  jmp     short loc_1800387FC
0x1800387f6  mov     ebx, eax
0x1800387f8  bts     ebx, 1Ch
0x1800387fc  mov     rcx, [rbp+57h+UserRights]; Buffer
0x180038800  test    rcx, rcx
0x180038803  jz      short loc_18003880B
0x180038805  call    cs:__imp_LsaFreeMemory
0x18003880b  mov     rcx, [rbp+57h+bufptr]; Buffer
0x18003880f  test    rcx, rcx
0x180038812  jz      short loc_18003881A
0x180038814  call    cs:__imp_NetApiBufferFree
0x18003881a  cmp     [rbp+57h+AccountSid], r15
0x18003881e  jz      short loc_18003882A
0x180038820  mov     rcx, [rbp+57h+AccountSid]; Block
0x180038824  call    cs:__imp_free
0x18003882a  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18003882e  test    rcx, rcx
0x180038831  jz      short loc_180038839
0x180038833  call    cs:__imp_LsaClose
0x180038839  mov     eax, ebx
0x18003883b  mov     rbx, [rsp+0B0h+arg_0]
0x180038843  add     rsp, 90h
0x18003884a  pop     r15
0x18003884c  pop     r14
0x18003884e  pop     r13
0x180038850  pop     rdi
0x180038851  pop     rbp
0x180038852  retn
```
