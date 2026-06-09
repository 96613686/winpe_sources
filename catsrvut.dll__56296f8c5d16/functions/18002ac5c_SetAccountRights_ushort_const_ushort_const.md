# SetAccountRights(ushort const *,ushort const *)

- ea: `0x18002ac5c`
- end: `0x18002ae87`
- name: `?SetAccountRights@@YAJPEBG0@Z`
- size: `555`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026a30`
- `0x180027074`

## callees

- `0x18002a964`
- `0x18002ac5c`

## import_xrefs

- `msvcrt!free` at `0x18002ae58`
- `msvcrt!free` at `0x18002ae58`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002ad5c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002ad5c`
- `netutils!NetApiBufferFree` at `0x18002ae48`
- `netutils!NetApiBufferFree` at `0x18002ae48`
- `logoncli!NetGetDCName` at `0x18002adab`
- `logoncli!NetGetDCName` at `0x18002adab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x18002ad17`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x18002ad17`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18002ad81`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18002ad81`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ade2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ae67`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ade2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ae67`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ae39`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ae39`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002acbe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002ae09`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002acbe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002ae09`

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
0x18002ac5c  mov     [rsp-8+arg_0], rbx
0x18002ac61  mov     qword ptr [rsp-8+CountOfRights], rdx
0x18002ac66  push    rbp
0x18002ac67  push    rdi
0x18002ac68  push    r13
0x18002ac6a  push    r14
0x18002ac6c  push    r15
0x18002ac6e  lea     rbp, [rsp-37h]
0x18002ac73  sub     rsp, 90h
0x18002ac7a  xor     r15d, r15d
0x18002ac7d  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ac81  xorps   xmm0, xmm0
0x18002ac84  mov     [rbp+57h+PolicyHandle], r15
0x18002ac88  mov     rbx, rcx
0x18002ac8b  mov     [rbp+57h+AccountSid], r15
0x18002ac8f  xorps   xmm1, xmm1
0x18002ac92  mov     [rbp+57h+bufptr], r15
0x18002ac96  xor     ecx, ecx; SystemName
0x18002ac98  mov     [rbp+57h+UserRights], r15
0x18002ac9c  mov     r8d, 811h; DesiredAccess
0x18002aca2  mov     [rbp+57h+CountOfRights], r15d
0x18002aca6  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002acaa  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18002acae  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm1
0x18002acb2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002acb6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002acba  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002acbe  call    cs:__imp_LsaOpenPolicy
0x18002acc4  test    eax, eax
0x18002acc6  jz      short loc_18002ACD1
0x18002acc8  bts     eax, 1Ch
0x18002accc  jmp     loc_18002AE6F
0x18002acd1  lea     rdx, [rbp+57h+AccountSid]
0x18002acd5  mov     rcx, rbx; Str
0x18002acd8  call    GetUserSID
0x18002acdd  mov     ebx, eax
0x18002acdf  test    eax, eax
0x18002ace1  jz      short loc_18002ACEC
0x18002ace3  mov     rcx, [rbp+57h+PolicyHandle]
0x18002ace7  jmp     loc_18002AE67
0x18002acec  lea     rax, aSebatchlogonri; "SeBatchLogonRight"
0x18002acf3  mov     dword ptr [rbp+57h+var_70], 240022h
0x18002acfa  mov     [rbp+57h+var_70+8], rax
0x18002acfe  mov     r14d, r15d
0x18002ad01  mov     r13d, 2
0x18002ad07  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x18002ad0b  lea     r9, [rbp+57h+CountOfRights]; CountOfRights
0x18002ad0f  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ad13  lea     r8, [rbp+57h+UserRights]; UserRights
0x18002ad17  call    cs:__imp_LsaEnumerateAccountRights
0x18002ad1d  test    eax, eax
0x18002ad1f  jnz     short loc_18002AD6F
0x18002ad21  mov     edi, r15d
0x18002ad24  cmp     edi, [rbp+57h+CountOfRights]
0x18002ad27  jnb     short loc_18002AD6F
0x18002ad29  mov     r8, [rbp+57h+UserRights]
0x18002ad2d  mov     edx, 1; dwCmpFlags
0x18002ad32  movzx   eax, word ptr [rbp+57h+var_70]
0x18002ad36  shr     eax, 1
0x18002ad38  mov     [rsp+0B0h+cchCount2], eax; cchCount2
0x18002ad3c  mov     rax, [rbp+57h+var_70+8]
0x18002ad40  mov     ecx, edi
0x18002ad42  add     rcx, rcx
0x18002ad45  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18002ad4a  movzx   r9d, word ptr [r8+rcx*8]
0x18002ad4f  mov     r8, [r8+rcx*8+8]; lpString1
0x18002ad54  mov     ecx, 400h; Locale
0x18002ad59  shr     r9d, 1; cchCount1
0x18002ad5c  call    cs:__imp_CompareStringW
0x18002ad62  cmp     eax, r13d
0x18002ad65  jz      loc_18002AE1C
0x18002ad6b  inc     edi
0x18002ad6d  jmp     short loc_18002AD24
0x18002ad6f  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x18002ad73  lea     r8, [rbp+57h+var_70]; UserRights
0x18002ad77  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ad7b  mov     r9d, 1; CountOfRights
0x18002ad81  call    cs:__imp_LsaAddAccountRights
0x18002ad87  test    eax, eax
0x18002ad89  jz      loc_18002AE30
0x18002ad8f  cmp     eax, 0C0000187h
0x18002ad94  jnz     loc_18002AE2A
0x18002ad9a  test    r14d, r14d
0x18002ad9d  jnz     loc_18002AE2A
0x18002ada3  lea     r8, [rbp+57h+bufptr]; bufptr
0x18002ada7  xor     edx, edx; domainname
0x18002ada9  xor     ecx, ecx; servername
0x18002adab  call    cs:__imp_NetGetDCName
0x18002adb1  test    eax, eax
0x18002adb3  jnz     short loc_18002AE23
0x18002adb5  mov     rcx, [rbp+57h+bufptr]
0x18002adb9  add     rcx, 4
0x18002adbd  mov     [rbp+57h+SystemName.Buffer], rcx
0x18002adc1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002adc5  inc     rax
0x18002adc8  cmp     [rcx+rax*2], r15w
0x18002adcd  jnz     short loc_18002ADC5
0x18002adcf  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002add3  add     ax, ax
0x18002add6  mov     [rbp+57h+SystemName.Length], ax
0x18002adda  add     ax, r13w
0x18002adde  mov     [rbp+57h+SystemName.MaximumLength], ax
0x18002ade2  call    cs:__imp_LsaClose
0x18002ade8  xorps   xmm0, xmm0
0x18002adeb  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002adef  mov     r8d, 811h; DesiredAccess
0x18002adf5  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002adf9  lea     rcx, [rbp+57h+SystemName]; SystemName
0x18002adfd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002ae01  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002ae05  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ae09  call    cs:__imp_LsaOpenPolicy
0x18002ae0f  test    eax, eax
0x18002ae11  jnz     short loc_18002AE2A
0x18002ae13  lea     r14d, [rax+1]
0x18002ae17  jmp     loc_18002AD07
0x18002ae1c  mov     ebx, 1
0x18002ae21  jmp     short loc_18002AE30
0x18002ae23  mov     ebx, 8000FFFFh
0x18002ae28  jmp     short loc_18002AE30
0x18002ae2a  mov     ebx, eax
0x18002ae2c  bts     ebx, 1Ch
0x18002ae30  mov     rcx, [rbp+57h+UserRights]; Buffer
0x18002ae34  test    rcx, rcx
0x18002ae37  jz      short loc_18002AE3F
0x18002ae39  call    cs:__imp_LsaFreeMemory
0x18002ae3f  mov     rcx, [rbp+57h+bufptr]; Buffer
0x18002ae43  test    rcx, rcx
0x18002ae46  jz      short loc_18002AE4E
0x18002ae48  call    cs:__imp_NetApiBufferFree
0x18002ae4e  cmp     [rbp+57h+AccountSid], r15
0x18002ae52  jz      short loc_18002AE5E
0x18002ae54  mov     rcx, [rbp+57h+AccountSid]; Block
0x18002ae58  call    cs:__imp_free
0x18002ae5e  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002ae62  test    rcx, rcx
0x18002ae65  jz      short loc_18002AE6D
0x18002ae67  call    cs:__imp_LsaClose
0x18002ae6d  mov     eax, ebx
0x18002ae6f  mov     rbx, [rsp+0B0h+arg_0]
0x18002ae77  add     rsp, 90h
0x18002ae7e  pop     r15
0x18002ae80  pop     r14
0x18002ae82  pop     r13
0x18002ae84  pop     rdi
0x18002ae85  pop     rbp
0x18002ae86  retn
```
