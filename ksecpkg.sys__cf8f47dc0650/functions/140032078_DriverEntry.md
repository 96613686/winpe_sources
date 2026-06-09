# DriverEntry

- ea: `0x140032078`
- end: `0x14003217e`
- name: `DriverEntry`
- size: `262`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140032010`

## callees

- `0x140007008`
- `0x14000faf0`
- `0x14002025c`
- `0x1400206f8`
- `0x1400217e0`
- `0x140021cfc`
- `0x140032078`
- `0x140032184`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x1400320da`
- `ntoskrnl!RtlInitAnsiString` at `0x1400320da`

## string_xrefs

- `0x140032143`: `KsecExRegisterExtensions failed: 0x%lx\n`
- `0x140032164`: `Security device driver extensions loaded\n`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v2; // eax
  NTSTATUS v3; // ebx
  int v5; // eax
  struct _STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _STRING v7; // [rsp+30h] [rbp-18h] BYREF

  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)KsecDispatch;
  wil_InitializeFeatureStaging();
  DestinationString = 0;
  if ( !_InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    RtlInitAnsiString(&DestinationString, "ksecpkg.sys");
    v7 = DestinationString;
    InitializeTelemetryAssertsKMWorkerInternal(&v7);
  }
  v2 = InitializeKernelSsl();
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(4, "The driver failed the algorithm self test: 0x%x\n", v2);
LABEL_6:
    wil_UninitializeFeatureStaging();
    return v3;
  }
  v5 = KsecExRegisterExtensions();
  v3 = v5;
  if ( v5 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "KsecExRegisterExtensions failed: 0x%lx\n", v5);
    UninitializeKernelSsl();
    goto LABEL_6;
  }
  if ( KsecInfoLevel )
    KsecDebugOut(4, "Security device driver extensions loaded\n");
  return 0;
}

```

## disassembly

```asm
0x140032078  push    rbx
0x14003207a  sub     rsp, 40h
0x14003207e  lea     rax, KsecDispatch
0x140032085  mov     [rcx+70h], rax
0x140032089  mov     [rcx+80h], rax
0x140032090  mov     [rcx+88h], rax
0x140032097  mov     [rcx+90h], rax
0x14003209e  mov     [rcx+98h], rax
0x1400320a5  mov     [rcx+0C0h], rax
0x1400320ac  mov     [rcx+0E0h], rax
0x1400320b3  call    wil_InitializeFeatureStaging
0x1400320b8  xorps   xmm0, xmm0
0x1400320bb  xor     eax, eax
0x1400320bd  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1400320c2  lock xadd cs:g_AssertsOperational, eax
0x1400320ca  test    eax, eax
0x1400320cc  jnz     short loc_1400320FB
0x1400320ce  lea     rdx, aKsecpkgSys; "ksecpkg.sys"
0x1400320d5  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400320da  call    cs:__imp_RtlInitAnsiString
0x1400320e1  nop     dword ptr [rax+rax+00h]
0x1400320e6  movaps  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x1400320eb  lea     rcx, [rsp+48h+var_18]
0x1400320f0  movdqa  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x1400320f6  call    InitializeTelemetryAssertsKMWorkerInternal
0x1400320fb  call    InitializeKernelSsl
0x140032100  mov     ebx, eax
0x140032102  test    eax, eax
0x140032104  jns     short loc_14003212C
0x140032106  cmp     cs:KsecInfoLevel, 0
0x14003210d  jz      short loc_140032123
0x14003210f  mov     r8d, eax
0x140032112  lea     rdx, aTheDriverFaile; "The driver failed the algorithm self te"...
0x140032119  mov     ecx, 4
0x14003211e  call    KsecDebugOut
0x140032123  call    wil_UninitializeFeatureStaging
0x140032128  mov     eax, ebx
0x14003212a  jmp     short loc_140032177
0x14003212c  call    KsecExRegisterExtensions
0x140032131  mov     ebx, eax
0x140032133  test    eax, eax
0x140032135  jns     short loc_14003215B
0x140032137  cmp     cs:KsecInfoLevel, 0
0x14003213e  jz      short loc_140032154
0x140032140  mov     r8d, eax
0x140032143  lea     rdx, aKsecexregister; "KsecExRegisterExtensions failed: 0x%lx"...
0x14003214a  mov     ecx, 1
0x14003214f  call    KsecDebugOut
0x140032154  call    UninitializeKernelSsl
0x140032159  jmp     short loc_140032123
0x14003215b  cmp     cs:KsecInfoLevel, 0
0x140032162  jz      short loc_140032175
0x140032164  lea     rdx, aSecurityDevice; "Security device driver extensions loade"...
0x14003216b  mov     ecx, 4
0x140032170  call    KsecDebugOut
0x140032175  xor     eax, eax
0x140032177  add     rsp, 40h
0x14003217b  pop     rbx
0x14003217c  retn
```
