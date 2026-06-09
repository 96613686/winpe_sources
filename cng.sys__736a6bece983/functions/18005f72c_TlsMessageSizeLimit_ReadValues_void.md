# TlsMessageSizeLimit::ReadValues(void)

- ea: `0x18005f72c`
- end: `0x18005f80e`
- name: `?ReadValues@TlsMessageSizeLimit@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(TlsMessageSizeLimit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005f8c0`

## callees

- `0x18005f3bc`
- `0x18005f51c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x18005f78c`
- `ntoskrnl!ZwOpenKey` at `0x18005f78c`

## string_xrefs

- `0x18005f739`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel\Messaging`

## pseudocode

```c
void __fastcall TlsMessageSizeLimit::ReadValues(TlsMessageSizeLimit *this)
{
  NTSTATUS v2; // eax
  __int64 v3; // r8
  void *v4; // rdx
  __int64 v5; // r8
  __int64 v6; // [rsp+20h] [rbp-40h] BYREF
  const wchar_t *v7; // [rsp+28h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  v6 = 11534510;
  v7 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\SecurityProviders\\Schannel\\Messaging";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v6;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v4 = KeyHandle;
  v6 = 2490404;
  if ( v2 < 0 )
    v4 = 0;
  v7 = L"MessageLimitServer";
  KeyHandle = v4;
  *(_DWORD *)this = ((__int64 (__fastcall *)(void **, __int64 *, __int64, __int64))RegistryReader::GetRegistryValue<int>)(
                      &KeyHandle,
                      &v6,
                      v3,
                      0x4000);
  v6 = 3801144;
  v7 = L"MessageLimitServerClientAuth";
  *((_DWORD *)this + 1) = ((__int64 (__fastcall *)(void **, __int64 *, __int64, __int64))RegistryReader::GetRegistryValue<int>)(
                            &KeyHandle,
                            &v6,
                            v5,
                            0x8000);
  SafeRegistryKey::~SafeRegistryKey((SafeRegistryKey *)&KeyHandle);
}

```

## disassembly

```asm
0x18005f72c  mov     [rsp-8+arg_8], rbx
0x18005f731  push    rbp
0x18005f732  mov     rbp, rsp
0x18005f735  sub     rsp, 60h
0x18005f739  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005f740  mov     [rbp+var_40], 0B000AEh
0x18005f748  mov     [rbp+var_38], rax
0x18005f74c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005f750  lea     rax, [rbp+var_40]
0x18005f754  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005f75c  mov     rbx, rcx
0x18005f75f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005f763  xorps   xmm0, xmm0
0x18005f766  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x18005f76e  mov     edx, 1; DesiredAccess
0x18005f773  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18005f77b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18005f77f  mov     [rbp+KeyHandle], 0
0x18005f787  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f78c  call    cs:__imp_ZwOpenKey
0x18005f793  nop     dword ptr [rax+rax+00h]
0x18005f798  mov     rdx, [rbp+KeyHandle]
0x18005f79c  xor     ecx, ecx
0x18005f79e  test    eax, eax
0x18005f7a0  mov     [rbp+var_40], 260024h
0x18005f7a8  lea     rax, aMessagelimitse; "MessageLimitServer"
0x18005f7af  mov     r9d, 4000h
0x18005f7b5  cmovs   rdx, rcx
0x18005f7b9  mov     [rbp+var_38], rax
0x18005f7bd  mov     [rbp+KeyHandle], rdx
0x18005f7c1  lea     rcx, [rbp+KeyHandle]
0x18005f7c5  lea     rdx, [rbp+var_40]
0x18005f7c9  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x18005f7ce  mov     [rbx], eax
0x18005f7d0  lea     rdx, [rbp+var_40]
0x18005f7d4  lea     rax, aMessagelimitse_0; "MessageLimitServerClientAuth"
0x18005f7db  mov     [rbp+var_40], 3A0038h
0x18005f7e3  mov     r9d, 8000h
0x18005f7e9  mov     [rbp+var_38], rax
0x18005f7ed  lea     rcx, [rbp+KeyHandle]
0x18005f7f1  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x18005f7f6  lea     rcx, [rbp+KeyHandle]; this
0x18005f7fa  mov     [rbx+4], eax
0x18005f7fd  call    ??1SafeRegistryKey@@QEAA@XZ; SafeRegistryKey::~SafeRegistryKey(void)
0x18005f802  mov     rbx, [rsp+60h+arg_8]
0x18005f807  add     rsp, 60h
0x18005f80b  pop     rbp
0x18005f80c  retn
```
