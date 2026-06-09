# DISABLED_FEATURES::INIT_DISABLED_FEATURES(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800206e0`
- end: `0x18002086c`
- name: `?INIT_DISABLED_FEATURES@DISABLED_FEATURES@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `396`
- prototype: `int __fastcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800206e0`
- `0x180020874`
- `0x180020b10`

## import_xrefs

- `ntdll!ZwClose` at `0x18002081a`
- `ntdll!ZwClose` at `0x18002085b`
- `ntdll!ZwClose` at `0x18002081a`
- `ntdll!ZwClose` at `0x18002085b`
- `ntdll!RtlInitUnicodeString` at `0x180020708`
- `ntdll!RtlInitUnicodeString` at `0x180020775`
- `ntdll!RtlInitUnicodeString` at `0x180020708`
- `ntdll!RtlInitUnicodeString` at `0x180020775`
- `ntdll!ZwOpenKey` at `0x180020744`
- `ntdll!ZwOpenKey` at `0x1800207b1`
- `ntdll!ZwOpenKey` at `0x180020744`
- `ntdll!ZwOpenKey` at `0x1800207b1`

## string_xrefs

- `0x18002075f`: `\Registry\Machine\Software\Classes\Interface\{00020400-0000-0000-C000-000000000046}`
- `0x1800206ee`: `\Registry\Machine\Software\Classes\Interface`

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
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Classes\\Interface");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
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
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Classes\\Interface\\{00020400-0000-0000-C000-000000000046}");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
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
0x1800206e0  push    rbp
0x1800206e2  mov     rbp, rsp
0x1800206e5  sub     rsp, 60h
0x1800206e9  and     [rbp+hkey.h], 0
0x1800206ee  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\Software\\Classes"...
0x1800206f5  and     dword ptr [rbp+ObjectAttributes+4], 0
0x1800206f9  lea     __formal, [rbp+DestinationString]; DestinationString
0x1800206fd  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x180020701  xorps   xmm0, xmm0
0x180020704  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180020708  call    cs:__imp_RtlInitUnicodeString
0x18002070f  nop     dword ptr [rax+rax+00h]
0x180020714  and     [rbp+ObjectAttributes.RootDirectory], 0
0x180020719  lea     rax, [rbp+DestinationString]
0x18002071d  xorps   xmm0, xmm0
0x180020720  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180020724  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020728  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002072f  mov     edx, 20019h; DesiredAccess
0x180020734  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002073b  lea     __formal, [rbp+hkey]; KeyHandle
0x18002073f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180020744  call    cs:__imp_ZwOpenKey
0x18002074b  nop     dword ptr [rax+rax+00h]
0x180020750  mov     ecx, eax; status
0x180020752  call    HrNt
0x180020757  test    eax, eax
0x180020759  jz      short loc_1800207D4
0x18002075b  and     dword ptr [rbp+ObjectAttributes+4], 0
0x18002075f  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Classes"...
0x180020766  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x18002076a  lea     __formal, [rbp+DestinationString]; DestinationString
0x18002076e  xorps   xmm0, xmm0
0x180020771  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180020775  call    cs:__imp_RtlInitUnicodeString
0x18002077c  nop     dword ptr [rax+rax+00h]
0x180020781  and     [rbp+ObjectAttributes.RootDirectory], 0
0x180020786  lea     rax, [rbp+DestinationString]
0x18002078a  xorps   xmm0, xmm0
0x18002078d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180020791  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020795  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002079c  mov     edx, 20019h; DesiredAccess
0x1800207a1  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800207a8  lea     __formal, [rbp+hkey]; KeyHandle
0x1800207ac  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800207b1  call    cs:__imp_ZwOpenKey
0x1800207b8  nop     dword ptr [rax+rax+00h]
0x1800207bd  mov     ecx, eax; status
0x1800207bf  call    HrNt
0x1800207c4  test    eax, eax
0x1800207c6  jz      short loc_18002082B
0x1800207c8  mov     eax, 1
0x1800207cd  add     rsp, 60h
0x1800207d1  pop     rbp
0x1800207d2  retn
0x1800207d4  mov     __formal, [rbp+hkey.h]; hkey
0x1800207d8  lea     rdx, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x1800207df  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800207e4  mov     __formal, [rbp+hkey.h]; hkey
0x1800207e8  lea     rdx, aInterfacehelpe_0; "InterfaceHelperDisableAllForOle32"
0x1800207ef  mov     cs:?s_fDisableAll@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableAll
0x1800207f5  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x1800207fa  mov     __formal, [rbp+hkey.h]; hkey
0x1800207fe  lea     rdx, aInterfacehelpe; "InterfaceHelperDisableTypeLib"
0x180020805  mov     cs:?s_fDisableAllForOle32@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableAllForOle32
0x18002080b  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180020810  mov     __formal, [rbp+hkey.h]; Handle
0x180020814  mov     cs:?s_fDisableTypelibs@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableTypelibs
0x18002081a  call    cs:__imp_ZwClose
0x180020821  nop     dword ptr [rax+rax+00h]
0x180020826  jmp     loc_18002075B
0x18002082b  mov     __formal, [rbp+hkey.h]; hkey
0x18002082f  lea     rdx, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x180020836  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x18002083b  mov     __formal, [rbp+hkey.h]; hkey
0x18002083f  lea     rdx, aInterfacehelpe_0; "InterfaceHelperDisableAllForOle32"
0x180020846  mov     cs:?s_fDisableDispatch@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableDispatch
0x18002084c  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180020851  mov     __formal, [rbp+hkey.h]; Handle
0x180020855  mov     cs:?s_fDisableDispatchForOle32@DISABLED_FEATURES@@0HA, eax; int DISABLED_FEATURES::s_fDisableDispatchForOle32
0x18002085b  call    cs:__imp_ZwClose
0x180020862  nop     dword ptr [rax+rax+00h]
0x180020867  jmp     loc_1800207C8
```
