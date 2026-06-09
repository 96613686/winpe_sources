# TlsMessageSizeLimit::ReadValues(void)

- ea: `0x18006900c`
- end: `0x1800690ee`
- name: `?ReadValues@TlsMessageSizeLimit@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(TlsMessageSizeLimit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800691a0`

## callees

- `0x180068c9c`
- `0x180068dfc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x18006906c`
- `ntoskrnl!ZwOpenKey` at `0x18006906c`

## string_xrefs

- `0x180069019`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel\Messaging`

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
0x18006900c  mov     [rsp-8+arg_8], rbx
0x180069011  push    rbp
0x180069012  mov     rbp, rsp
0x180069015  sub     rsp, 60h
0x180069019  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x180069020  mov     [rbp+var_40], 0B000AEh
0x180069028  mov     [rbp+var_38], rax
0x18006902c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180069030  lea     rax, [rbp+var_40]
0x180069034  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006903c  mov     rbx, rcx
0x18006903f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180069043  xorps   xmm0, xmm0
0x180069046  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x18006904e  mov     edx, 1; DesiredAccess
0x180069053  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006905b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18006905f  mov     [rbp+KeyHandle], 0
0x180069067  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006906c  call    cs:__imp_ZwOpenKey
0x180069073  nop     dword ptr [rax+rax+00h]
0x180069078  mov     rdx, [rbp+KeyHandle]
0x18006907c  xor     ecx, ecx
0x18006907e  test    eax, eax
0x180069080  mov     [rbp+var_40], 260024h
0x180069088  lea     rax, aMessagelimitse; "MessageLimitServer"
0x18006908f  mov     r9d, 4000h
0x180069095  cmovs   rdx, rcx
0x180069099  mov     [rbp+var_38], rax
0x18006909d  mov     [rbp+KeyHandle], rdx
0x1800690a1  lea     rcx, [rbp+KeyHandle]
0x1800690a5  lea     rdx, [rbp+var_40]
0x1800690a9  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x1800690ae  mov     [rbx], eax
0x1800690b0  lea     rdx, [rbp+var_40]
0x1800690b4  lea     rax, aMessagelimitse_0; "MessageLimitServerClientAuth"
0x1800690bb  mov     [rbp+var_40], 3A0038h
0x1800690c3  mov     r9d, 8000h
0x1800690c9  mov     [rbp+var_38], rax
0x1800690cd  lea     rcx, [rbp+KeyHandle]
0x1800690d1  call    ??$GetRegistryValue@H@RegistryReader@@QEBAHAEBU_UNICODE_STRING@@KH@Z; RegistryReader::GetRegistryValue<int>(_UNICODE_STRING const &,ulong,int)
0x1800690d6  lea     rcx, [rbp+KeyHandle]; this
0x1800690da  mov     [rbx+4], eax
0x1800690dd  call    ??1SafeRegistryKey@@QEAA@XZ; SafeRegistryKey::~SafeRegistryKey(void)
0x1800690e2  mov     rbx, [rsp+60h+arg_8]
0x1800690e7  add     rsp, 60h
0x1800690eb  pop     rbp
0x1800690ec  retn
```
