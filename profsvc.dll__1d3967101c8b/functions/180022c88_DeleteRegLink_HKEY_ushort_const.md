# DeleteRegLink(HKEY__ *,ushort const *)

- ea: `0x180022c88`
- end: `0x180022d43`
- name: `?DeleteRegLink@@YAJPEAUHKEY__@@PEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022b60`

## callees

- `0x180022c88`
- `0x180022d4c`
- `0x1800272ec`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180022cee`
- `ntdll!NtOpenKey` at `0x180022cee`
- `ntdll!RtlInitUnicodeString` at `0x180022caf`
- `ntdll!RtlInitUnicodeString` at `0x180022caf`
- `ntdll!NtClose` at `0x180022d0a`
- `ntdll!NtClose` at `0x180022d0a`
- `ntdll!NtDeleteKey` at `0x180022d16`
- `ntdll!NtDeleteKey` at `0x180022d16`

## pseudocode

```c
__int64 __fastcall DeleteRegLink(HKEY a1, unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  int v4; // edx
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  int v7; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Software\\Classes\\");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 320;
  ObjectAttributes.RootDirectory = a1;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    v6 = NtDeleteKey(KeyHandle);
    if ( v6 >= 0 )
      v5 = 0;
    else
      v5 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v6, v7);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  }
  else
  {
    v5 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v3, v4);
    if ( KeyHandle )
      NtClose(KeyHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x180022c88  mov     [rsp-8+arg_0], rbx
0x180022c8d  mov     [rsp-8+KeyHandle], rdx
0x180022c92  push    rbp
0x180022c93  mov     rbp, rsp
0x180022c96  sub     rsp, 60h
0x180022c9a  mov     rbx, rcx
0x180022c9d  lea     rdx, aSoftwareClasse; "Software\\Classes\\"
0x180022ca4  xorps   xmm0, xmm0
0x180022ca7  lea     rcx, [rbp+DestinationString]; DestinationString
0x180022cab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180022caf  call    cs:__imp_RtlInitUnicodeString
0x180022cb5  lea     rax, [rbp+DestinationString]
0x180022cb9  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180022cc1  xorps   xmm0, xmm0
0x180022cc4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180022cc8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180022ccc  mov     qword ptr [rbp+ObjectAttributes.Attributes], 140h
0x180022cd4  mov     edx, 2000000h; DesiredAccess
0x180022cd9  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180022cdd  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180022ce1  mov     [rbp+KeyHandle], 0
0x180022ce9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180022cee  call    cs:__imp_NtOpenKey
0x180022cf4  test    eax, eax
0x180022cf6  jns     short loc_180022D12
0x180022cf8  mov     ecx, eax; this
0x180022cfa  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180022cff  mov     rcx, [rbp+KeyHandle]; Handle
0x180022d03  mov     ebx, eax
0x180022d05  test    rcx, rcx
0x180022d08  jz      short loc_180022D36
0x180022d0a  call    cs:__imp_NtClose
0x180022d10  jmp     short loc_180022D36
0x180022d12  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180022d16  call    cs:__imp_NtDeleteKey
0x180022d1c  test    eax, eax
0x180022d1e  jns     short loc_180022D2B
0x180022d20  mov     ecx, eax; this
0x180022d22  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180022d27  mov     ebx, eax
0x180022d29  jmp     short loc_180022D2D
0x180022d2b  xor     ebx, ebx
0x180022d2d  lea     rcx, [rbp+KeyHandle]
0x180022d31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022d36  mov     eax, ebx
0x180022d38  mov     rbx, [rsp+60h+arg_0]
0x180022d3d  add     rsp, 60h
0x180022d41  pop     rbp
0x180022d42  retn
```
