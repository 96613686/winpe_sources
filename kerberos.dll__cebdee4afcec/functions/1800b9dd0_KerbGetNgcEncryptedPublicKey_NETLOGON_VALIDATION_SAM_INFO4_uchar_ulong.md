# KerbGetNgcEncryptedPublicKey(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar * *,ulong *)

- ea: `0x1800b9dd0`
- end: `0x1800b9fac`
- name: `?KerbGetNgcEncryptedPublicKey@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z`
- size: `476`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b72b4`

## callees

- `0x18008b70c`
- `0x1800b5f9c`
- `0x1800b9b20`
- `0x1800b9dd0`
- `0x1800dd634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e89`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b9e7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b9e7f`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800b9f5b`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800b9f5b`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800b9f11`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800b9f11`

## string_xrefs

- `0x1800b9e69`: `Get UserSid fail : 0x%x\n`
- `0x1800b9ea2`: `ConvertSidToStringSid: 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbGetNgcEncryptedPublicKey(
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  void *DomainRelativeSid; // rax
  signed int LogonDecryptionKeyName; // ebx
  signed int LastError; // eax
  int NgcContainerInfo; // eax
  const char *v10; // r9
  __int64 v11; // r8
  unsigned __int8 *v12; // [rsp+30h] [rbp-29h] BYREF
  struct _NGC_CONTAINER_ENUM_INFO *v13; // [rsp+38h] [rbp-21h] BYREF
  __int64 v14; // [rsp+40h] [rbp-19h] BYREF
  void *v15; // [rsp+48h] [rbp-11h] BYREF
  void *v16; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v17[6]; // [rsp+58h] [rbp-1h] BYREF
  char v18; // [rsp+88h] [rbp+2Fh]
  unsigned int v19; // [rsp+C0h] [rbp+67h] BYREF
  LPWSTR StringSid; // [rsp+D8h] [rbp+7Fh] BYREF

  v15 = 0;
  v13 = 0;
  v16 = 0;
  v14 = 0;
  v12 = 0;
  v19 = 0;
  StringSid = 0;
  v17[0] = &v13;
  v17[1] = &StringSid;
  v17[2] = &v15;
  v17[3] = &v14;
  v17[4] = &v16;
  v17[5] = &v12;
  v18 = 1;
  DomainRelativeSid = KerbMakeDomainRelativeSid(*((PSID *)a1 + 28), *((_DWORD *)a1 + 37));
  v15 = DomainRelativeSid;
  if ( !DomainRelativeSid )
  {
    LogonDecryptionKeyName = -1073740759;
    KerbTracerT::Log(1, "KerbGetNgcEncryptedPublicKey", 7687, "Get UserSid fail : 0x%x\n", -1073740759);
LABEL_9:
    v18 = 0;
    lambda_5ce1277023e27e3b21f708429b8278aa_::operator()(v17);
    return (unsigned int)LogonDecryptionKeyName;
  }
  if ( !ConvertSidToStringSidW(DomainRelativeSid, &StringSid) )
  {
    LastError = GetLastError();
    LogonDecryptionKeyName = LastError;
    if ( LastError > 0 )
      LogonDecryptionKeyName = (unsigned __int16)LastError | 0xC0070000;
    KerbTracerT::Log(1, "KerbGetNgcEncryptedPublicKey", 7695, "ConvertSidToStringSid: 0x%x\n", LogonDecryptionKeyName);
    goto LABEL_9;
  }
  NgcContainerInfo = KerbGetNgcContainerInfo(StringSid, &v13, &v16);
  LogonDecryptionKeyName = NgcContainerInfo;
  if ( NgcContainerInfo < 0 )
  {
    KerbTracerT::Log(
      1,
      "KerbGetNgcEncryptedPublicKey",
      7706,
      "KerbGetNgcContainerInfo fails, no logon containers found: 0x%x\n",
      NgcContainerInfo);
    goto LABEL_9;
  }
  LogonDecryptionKeyName = NgcGetLogonDecryptionKeyName(StringSid, *((_QWORD *)v13 + 4), *((_QWORD *)v13 + 5), &v14);
  if ( LogonDecryptionKeyName < 0 )
  {
    v10 = "NgcGetLogonDecryptionKeyName: 0x%x\n";
    v11 = 7719;
    goto LABEL_12;
  }
  LogonDecryptionKeyName = NgcGetUserIdKeyPublicKey(v14, &v12, &v19);
  if ( LogonDecryptionKeyName < 0 )
  {
    v10 = "NgcGetUserIdKeyPublicKey: 0x%x\n";
    v11 = 7731;
LABEL_12:
    KerbTracerT::Log(1, "KerbGetNgcEncryptedPublicKey", v11, v10, LogonDecryptionKeyName);
    LogonDecryptionKeyName = (unsigned __int16)LogonDecryptionKeyName;
    if ( (_WORD)LogonDecryptionKeyName )
      LogonDecryptionKeyName = (unsigned __int16)LogonDecryptionKeyName | 0xC0070000;
    goto LABEL_9;
  }
  *a2 = v12;
  v12 = 0;
  *a3 = v19;
  v18 = 0;
  lambda_5ce1277023e27e3b21f708429b8278aa_::operator()(v17);
  return 0;
}

```

## disassembly

```asm
0x1800b9dd0  mov     [rsp-8+arg_8], rbx
0x1800b9dd5  push    rbp
0x1800b9dd6  push    rsi
0x1800b9dd7  push    rdi
0x1800b9dd8  push    r14
0x1800b9dda  push    r15
0x1800b9ddc  lea     rbp, [rsp-37h]
0x1800b9de1  sub     rsp, 90h
0x1800b9de8  mov     rdi, r8
0x1800b9deb  mov     rsi, rdx
0x1800b9dee  xor     r14d, r14d
0x1800b9df1  mov     [rbp+57h+var_68], r14
0x1800b9df5  mov     [rbp+57h+var_78], r14
0x1800b9df9  mov     [rbp+57h+var_60], r14
0x1800b9dfd  mov     [rbp+57h+var_70], r14
0x1800b9e01  mov     [rbp+57h+var_80], r14
0x1800b9e05  mov     [rbp+57h+arg_0], r14d
0x1800b9e09  mov     [rbp+57h+StringSid], r14
0x1800b9e0d  lea     rax, [rbp+57h+var_78]
0x1800b9e11  mov     [rbp+57h+var_58], rax
0x1800b9e15  lea     rax, [rbp+57h+StringSid]
0x1800b9e19  mov     [rbp+57h+var_50], rax
0x1800b9e1d  lea     rax, [rbp+57h+var_68]
0x1800b9e21  mov     [rbp+57h+var_48], rax
0x1800b9e25  lea     rax, [rbp+57h+var_70]
0x1800b9e29  mov     [rbp+57h+var_40], rax
0x1800b9e2d  lea     rax, [rbp+57h+var_60]
0x1800b9e31  mov     [rbp+57h+var_38], rax
0x1800b9e35  lea     rax, [rbp+57h+var_80]
0x1800b9e39  mov     [rbp+57h+var_30], rax
0x1800b9e3d  lea     r15d, [r14+1]
0x1800b9e41  mov     [rbp+57h+var_28], r15b
0x1800b9e45  mov     edx, [rcx+94h]; unsigned int
0x1800b9e4b  mov     rcx, [rcx+0E0h]; SourceSid
0x1800b9e52  call    ?KerbMakeDomainRelativeSid@@YAPEAXPEAXK@Z; KerbMakeDomainRelativeSid(void *,ulong)
0x1800b9e57  mov     [rbp+57h+var_68], rax
0x1800b9e5b  test    rax, rax
0x1800b9e5e  jnz     short loc_1800B9E78
0x1800b9e60  mov     ebx, 0C0000429h
0x1800b9e65  mov     [rsp+0B0h+var_90], ebx
0x1800b9e69  lea     r9, aGetUsersidFail; "Get UserSid fail : 0x%x\n"
0x1800b9e70  mov     r8d, 1E07h
0x1800b9e76  jmp     short loc_1800B9ED9
0x1800b9e78  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800b9e7c  mov     rcx, rax; Sid
0x1800b9e7f  call    cs:__imp_ConvertSidToStringSidW
0x1800b9e85  test    eax, eax
0x1800b9e87  jnz     short loc_1800B9EB1
0x1800b9e89  call    cs:__imp_GetLastError
0x1800b9e8f  mov     ebx, eax
0x1800b9e91  test    eax, eax
0x1800b9e93  jle     short loc_1800B9E9E
0x1800b9e95  movzx   ebx, ax
0x1800b9e98  or      ebx, 0C0070000h
0x1800b9e9e  mov     [rsp+0B0h+var_90], ebx
0x1800b9ea2  lea     r9, aConvertsidtost_0; "ConvertSidToStringSid: 0x%x\n"
0x1800b9ea9  mov     r8d, 1E0Fh
0x1800b9eaf  jmp     short loc_1800B9ED9
0x1800b9eb1  lea     r8, [rbp+57h+var_60]; void **
0x1800b9eb5  lea     rdx, [rbp+57h+var_78]; struct _NGC_CONTAINER_ENUM_INFO **
0x1800b9eb9  mov     rcx, [rbp+57h+StringSid]; unsigned __int16 *
0x1800b9ebd  call    ?KerbGetNgcContainerInfo@@YAJPEAGPEAPEAU_NGC_CONTAINER_ENUM_INFO@@PEAPEAX@Z; KerbGetNgcContainerInfo(ushort *,_NGC_CONTAINER_ENUM_INFO * *,void * *)
0x1800b9ec2  mov     ebx, eax
0x1800b9ec4  test    eax, eax
0x1800b9ec6  jns     short loc_1800B9EFD
0x1800b9ec8  mov     [rsp+0B0h+var_90], eax
0x1800b9ecc  lea     r9, aKerbgetngccont; "KerbGetNgcContainerInfo fails, no logon"...
0x1800b9ed3  mov     r8d, 1E1Ah
0x1800b9ed9  lea     rdx, aKerbgetngcencr; "KerbGetNgcEncryptedPublicKey"
0x1800b9ee0  mov     ecx, r15d
0x1800b9ee3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9ee8  nop
0x1800b9ee9  mov     [rbp+57h+var_28], r14b
0x1800b9eed  lea     rcx, [rbp+57h+var_58]
0x1800b9ef1  call    _lambda_5ce1277023e27e3b21f708429b8278aa___operator__
0x1800b9ef6  mov     eax, ebx
0x1800b9ef8  jmp     loc_1800B9F95
0x1800b9efd  lea     r9, [rbp+57h+var_70]
0x1800b9f01  mov     rdx, [rbp+57h+var_78]
0x1800b9f05  mov     r8, [rdx+28h]
0x1800b9f09  mov     rdx, [rdx+20h]
0x1800b9f0d  mov     rcx, [rbp+57h+StringSid]
0x1800b9f11  call    cs:__imp_NgcGetLogonDecryptionKeyName
0x1800b9f17  mov     ebx, eax
0x1800b9f19  test    eax, eax
0x1800b9f1b  jns     short loc_1800B9F4F
0x1800b9f1d  lea     r9, aNgcgetlogondec_0; "NgcGetLogonDecryptionKeyName: 0x%x\n"
0x1800b9f24  mov     r8d, 1E27h
0x1800b9f2a  mov     [rsp+0B0h+var_90], ebx
0x1800b9f2e  lea     rdx, aKerbgetngcencr; "KerbGetNgcEncryptedPublicKey"
0x1800b9f35  mov     ecx, r15d
0x1800b9f38  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9f3d  movzx   ebx, bx
0x1800b9f40  mov     ecx, ebx
0x1800b9f42  or      ecx, 0C0070000h
0x1800b9f48  test    ebx, ebx
0x1800b9f4a  cmovnz  ebx, ecx
0x1800b9f4d  jmp     short loc_1800B9EE9
0x1800b9f4f  lea     r8, [rbp+57h+arg_0]
0x1800b9f53  lea     rdx, [rbp+57h+var_80]
0x1800b9f57  mov     rcx, [rbp+57h+var_70]
0x1800b9f5b  call    cs:__imp_NgcGetUserIdKeyPublicKey
0x1800b9f61  mov     ebx, eax
0x1800b9f63  test    eax, eax
0x1800b9f65  jns     short loc_1800B9F76
0x1800b9f67  lea     r9, aNgcgetuseridke_0; "NgcGetUserIdKeyPublicKey: 0x%x\n"
0x1800b9f6e  mov     r8d, 1E33h
0x1800b9f74  jmp     short loc_1800B9F2A
0x1800b9f76  mov     rax, [rbp+57h+var_80]
0x1800b9f7a  mov     [rsi], rax
0x1800b9f7d  mov     [rbp+57h+var_80], r14
0x1800b9f81  mov     eax, [rbp+57h+arg_0]
0x1800b9f84  mov     [rdi], eax
0x1800b9f86  mov     [rbp+57h+var_28], r14b
0x1800b9f8a  lea     rcx, [rbp+57h+var_58]
0x1800b9f8e  call    _lambda_5ce1277023e27e3b21f708429b8278aa___operator__
0x1800b9f93  xor     eax, eax
0x1800b9f95  mov     rbx, [rsp+0B0h+arg_8]
0x1800b9f9d  add     rsp, 90h
0x1800b9fa4  pop     r15
0x1800b9fa6  pop     r14
0x1800b9fa8  pop     rdi
0x1800b9fa9  pop     rsi
0x1800b9faa  pop     rbp
0x1800b9fab  retn
```
