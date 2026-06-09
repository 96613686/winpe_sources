# TlsMessageSizeLimit::ReadValues(void)

- ea: `0x18005ee3c`
- end: `0x18005ef1e`
- name: `?ReadValues@TlsMessageSizeLimit@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(TlsMessageSizeLimit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005efd0`

## callees

- `0x18005eacc`
- `0x18005ec2c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x18005ee9c`
- `ntoskrnl!ZwOpenKey` at `0x18005ee9c`

## string_xrefs

- `0x18005ee49`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel\Messaging`

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
0x18005ee3c  mov     [rsp-8+arg_8], rbx
0x18005ee41  push    rbp
0x18005ee42  mov     rbp, rsp
0x18005ee45  sub     rsp, 60h
0x18005ee49  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005ee50  mov     [rbp+var_40], 0B000AEh
0x18005ee58  mov     [rbp+var_38], rax
0x18005ee5c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005ee60  lea     rax, [rbp+var_40]
0x18005ee64  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005ee6c  mov     rbx, rcx
0x18005ee6f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005ee73  xorps   xmm0, xmm0
0x18005ee76  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x18005ee7e  mov     edx, 1; DesiredAccess
0x18005ee83  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18005ee8b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18005ee8f  mov     [rbp+KeyHandle], 0
0x18005ee97  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ee9c  call    cs:__imp_ZwOpenKey
0x18005eea3  nop     dword ptr [rax+rax+00h]
0x18005eea8  mov     rdx, [rbp+KeyHandle]
0x18005eeac  xor     ecx, ecx
0x18005eeae  test    eax, eax
0x18005eeb0  mov     [rbp+var_40], 260024h
0x18005eeb8  lea     rax, aMessagelimitse; "MessageLimitServer"
0x18005eebf  mov     r9d, 4000h
0x18005eec5  cmovs   rdx, rcx
0x18005eec9  mov     [rbp+var_38], rax
0x18005eecd  mov     [rbp+KeyHandle], rdx
0x18005eed1  lea     rcx, [rbp+KeyHandle]
0x18005eed5  lea     rdx, [rbp+var_40]
0x18005eed9  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x18005eede  mov     [rbx], eax
0x18005eee0  lea     rdx, [rbp+var_40]
0x18005eee4  lea     rax, aMessagelimitse_0; "MessageLimitServerClientAuth"
0x18005eeeb  mov     [rbp+var_40], 3A0038h
0x18005eef3  mov     r9d, 8000h
0x18005eef9  mov     [rbp+var_38], rax
0x18005eefd  lea     rcx, [rbp+KeyHandle]
0x18005ef01  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x18005ef06  lea     rcx, [rbp+KeyHandle]; this
0x18005ef0a  mov     [rbx+4], eax
0x18005ef0d  call    ??1SafeRegistryKey@@QEAA@XZ; SafeRegistryKey::~SafeRegistryKey(void)
0x18005ef12  mov     rbx, [rsp+60h+arg_8]
0x18005ef17  add     rsp, 60h
0x18005ef1b  pop     rbp
0x18005ef1c  retn
```
