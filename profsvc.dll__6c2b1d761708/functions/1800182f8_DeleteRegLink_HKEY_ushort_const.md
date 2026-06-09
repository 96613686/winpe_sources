# DeleteRegLink(HKEY__ *,ushort const *)

- ea: `0x1800182f8`
- end: `0x1800183cc`
- name: `?DeleteRegLink@@YAJPEAUHKEY__@@PEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800181c8`

## callees

- `0x1800182f8`
- `0x1800183d4`
- `0x1800292fc`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180018364`
- `ntdll!NtOpenKey` at `0x180018364`
- `ntdll!RtlInitUnicodeString` at `0x18001831f`
- `ntdll!RtlInitUnicodeString` at `0x18001831f`
- `ntdll!NtClose` at `0x180018386`
- `ntdll!NtClose` at `0x180018386`
- `ntdll!NtDeleteKey` at `0x180018398`
- `ntdll!NtDeleteKey` at `0x180018398`

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
0x1800182f8  mov     [rsp-8+arg_0], rbx
0x1800182fd  mov     [rsp-8+KeyHandle], rdx
0x180018302  push    rbp
0x180018303  mov     rbp, rsp
0x180018306  sub     rsp, 60h
0x18001830a  mov     rbx, rcx
0x18001830d  lea     rdx, SourceString; "Software\\Classes\\"
0x180018314  xorps   xmm0, xmm0
0x180018317  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001831b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001831f  call    cs:__imp_RtlInitUnicodeString
0x180018326  nop     dword ptr [rax+rax+00h]
0x18001832b  lea     rax, [rbp+DestinationString]
0x18001832f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180018337  xorps   xmm0, xmm0
0x18001833a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001833e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180018342  mov     qword ptr [rbp+ObjectAttributes.Attributes], 140h
0x18001834a  mov     edx, 2000000h; DesiredAccess
0x18001834f  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180018353  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180018357  mov     [rbp+KeyHandle], 0
0x18001835f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180018364  call    cs:__imp_NtOpenKey
0x18001836b  nop     dword ptr [rax+rax+00h]
0x180018370  test    eax, eax
0x180018372  jns     short loc_180018394
0x180018374  mov     ecx, eax; this
0x180018376  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001837b  mov     rcx, [rbp+KeyHandle]; Handle
0x18001837f  mov     ebx, eax
0x180018381  test    rcx, rcx
0x180018384  jz      short loc_1800183BE
0x180018386  call    cs:__imp_NtClose
0x18001838d  nop     dword ptr [rax+rax+00h]
0x180018392  jmp     short loc_1800183BE
0x180018394  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180018398  call    cs:__imp_NtDeleteKey
0x18001839f  nop     dword ptr [rax+rax+00h]
0x1800183a4  test    eax, eax
0x1800183a6  jns     short loc_1800183B3
0x1800183a8  mov     ecx, eax; this
0x1800183aa  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800183af  mov     ebx, eax
0x1800183b1  jmp     short loc_1800183B5
0x1800183b3  xor     ebx, ebx
0x1800183b5  lea     rcx, [rbp+KeyHandle]
0x1800183b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800183be  mov     eax, ebx
0x1800183c0  mov     rbx, [rsp+60h+arg_0]
0x1800183c5  add     rsp, 60h
0x1800183c9  pop     rbp
0x1800183ca  retn
```
