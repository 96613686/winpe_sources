# DISABLED_FEATURES::INIT_DISABLED_FEATURES(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800190b0`
- end: `0x180019228`
- name: `?INIT_DISABLED_FEATURES@DISABLED_FEATURES@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `376`
- prototype: `int __fastcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180014090`
- `0x180017894`
- `0x1800190b0`

## import_xrefs

- `ntdll!ZwClose` at `0x1800191e2`
- `ntdll!ZwClose` at `0x18001921d`
- `ntdll!ZwClose` at `0x1800191e2`
- `ntdll!ZwClose` at `0x18001921d`
- `ntdll!RtlInitUnicodeString` at `0x1800190df`
- `ntdll!RtlInitUnicodeString` at `0x180019147`
- `ntdll!RtlInitUnicodeString` at `0x1800190df`
- `ntdll!RtlInitUnicodeString` at `0x180019147`
- `ntdll!ZwOpenKey` at `0x180019118`
- `ntdll!ZwOpenKey` at `0x180019180`
- `ntdll!ZwOpenKey` at `0x180019118`
- `ntdll!ZwOpenKey` at `0x180019180`

## string_xrefs

- `0x18001912c`: `\Registry\Machine\Software\Classes\Interface\{00020400-0000-0000-C000-000000000046}`
- `0x1800190c4`: `\Registry\Machine\Software\Classes\Interface`

## pseudocode

```c
__int64 __fastcall DISABLED_FEATURES::INIT_DISABLED_FEATURES(_RTL_RUN_ONCE *__formal, void *a2, void **a3)
{
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  HREG hkey; // [rsp+88h] [rbp+28h] BYREF

  hkey.h = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Classes\\Interface");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenKey(&hkey.h, 0x20019u, &ObjectAttributes);
  if ( !HrNt(v3) )
  {
    DISABLED_FEATURES::s_fDisableAll = FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableAll");
    DISABLED_FEATURES::s_fDisableAllForOle32 = FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableAllForOle32");
    DISABLED_FEATURES::s_fDisableTypelibs = FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableTypeLib");
    ZwClose(hkey.h);
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Classes\\Interface\\{00020400-0000-0000-C000-000000000046}");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&hkey.h, 0x20019u, &ObjectAttributes);
  if ( !HrNt(v4) )
  {
    DISABLED_FEATURES::s_fDisableDispatch = FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableAll");
    DISABLED_FEATURES::s_fDisableDispatchForOle32 = FDisableAssociatedInterceptor(
                                                      hkey,
                                                      L"InterfaceHelperDisableAllForOle32");
    ZwClose(hkey.h);
  }
  return 1;
}

```

## disassembly

```asm
0x1800190b0  push    rbp
0x1800190b2  mov     rbp, rsp
0x1800190b5  sub     rsp, 60h
0x1800190b9  xorps   xmm0, xmm0
0x1800190bc  mov     [rbp+hkey.h], 0
0x1800190c4  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\Software\\Classes"...
0x1800190cb  lea     __formal, [rbp+DestinationString]; DestinationString
0x1800190cf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800190d3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800190d7  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800190db  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800190df  call    cs:__imp_RtlInitUnicodeString
0x1800190e5  lea     rax, [rbp+DestinationString]
0x1800190e9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800190f0  xorps   xmm0, xmm0
0x1800190f3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800190f7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800190fb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180019103  mov     edx, 20019h; DesiredAccess
0x180019108  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001910f  lea     __formal, [rbp+hkey]; KeyHandle
0x180019113  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180019118  call    cs:__imp_ZwOpenKey
0x18001911e  mov     ecx, eax; status
0x180019120  call    HrNt
0x180019125  test    eax, eax
0x180019127  jz      short loc_18001919C
0x180019129  xorps   xmm0, xmm0
0x18001912c  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Classes"...
0x180019133  lea     __formal, [rbp+DestinationString]; DestinationString
0x180019137  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001913b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001913f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180019143  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180019147  call    cs:__imp_RtlInitUnicodeString
0x18001914d  lea     rax, [rbp+DestinationString]
0x180019151  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180019158  xorps   xmm0, xmm0
0x18001915b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001915f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180019163  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001916b  mov     edx, 20019h; DesiredAccess
0x180019170  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180019177  lea     __formal, [rbp+hkey]; KeyHandle
0x18001917b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180019180  call    cs:__imp_ZwOpenKey
0x180019186  mov     ecx, eax; status
0x180019188  call    HrNt
0x18001918d  test    eax, eax
0x18001918f  jz      short loc_1800191ED
0x180019191  mov     eax, 1
0x180019196  add     rsp, 60h
0x18001919a  pop     rbp
0x18001919b  retn
0x18001919c  mov     __formal, [rbp+hkey.h]; hkey
0x1800191a0  lea     rdx, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x1800191a7  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800191ac  mov     __formal, [rbp+hkey.h]; hkey
0x1800191b0  lea     rdx, aInterfacehelpe_0; "InterfaceHelperDisableAllForOle32"
0x1800191b7  mov     cs:?s_fDisableAll@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableAll
0x1800191bd  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800191c2  mov     __formal, [rbp+hkey.h]; hkey
0x1800191c6  lea     rdx, aInterfacehelpe; "InterfaceHelperDisableTypeLib"
0x1800191cd  mov     cs:?s_fDisableAllForOle32@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableAllForOle32
0x1800191d3  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800191d8  mov     __formal, [rbp+hkey.h]; Handle
0x1800191dc  mov     cs:?s_fDisableTypelibs@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableTypelibs
0x1800191e2  call    cs:__imp_ZwClose
0x1800191e8  jmp     loc_180019129
0x1800191ed  mov     __formal, [rbp+hkey.h]; hkey
0x1800191f1  lea     rdx, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x1800191f8  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800191fd  mov     __formal, [rbp+hkey.h]; hkey
0x180019201  lea     rdx, aInterfacehelpe_0; "InterfaceHelperDisableAllForOle32"
0x180019208  mov     cs:?s_fDisableDispatch@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableDispatch
0x18001920e  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180019213  mov     __formal, [rbp+hkey.h]; Handle
0x180019217  mov     cs:?s_fDisableDispatchForOle32@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableDispatchForOle32
0x18001921d  call    cs:__imp_ZwClose
0x180019223  jmp     loc_180019191
```
