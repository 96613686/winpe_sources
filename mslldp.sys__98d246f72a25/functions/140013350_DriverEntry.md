# DriverEntry

- ea: `0x140013350`
- end: `0x1400133d5`
- name: `DriverEntry`
- size: `133`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005144`

## callees

- `0x14000e008`
- `0x14000e670`
- `0x14000e6e0`
- `0x140013008`
- `0x140013350`
- `0x1400133dc`
- `0x1400134c8`
- `0x140013674`
- `0x140013798`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS DriverWdf; // ebx

  wil_InitializeFeatureStaging();
  DriverWdf = lldpInitializeDriverCore(DriverObject);
  if ( DriverWdf >= 0 )
  {
    DriverWdf = lldpCreateDriverWdf(DriverObject, RegistryPath);
    if ( DriverWdf >= 0 )
    {
      DriverWdf = lldpRegisterProtocol();
      if ( DriverWdf )
        goto LABEL_6;
      DriverWdf = lldpNmrRegisterProvider();
      if ( DriverWdf >= 0 )
      {
        DriverWdf = lldpInitializeControlDevice();
LABEL_6:
        if ( DriverWdf >= 0 )
          return DriverWdf;
      }
    }
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount )
    lldpDriverUnloadWdf(*(__int64 *)&WPP_MAIN_CB.ActiveThreadCount);
  else
    wil_UninitializeFeatureStaging();
  return DriverWdf;
}

```

## disassembly

```asm
0x140013350  mov     [rsp+arg_0], rbx
0x140013355  mov     [rsp+arg_8], rsi
0x14001335a  push    rdi
0x14001335b  sub     rsp, 20h
0x14001335f  mov     rsi, rdx
0x140013362  mov     rdi, rcx
0x140013365  call    wil_InitializeFeatureStaging
0x14001336a  mov     rcx, rdi
0x14001336d  call    lldpInitializeDriverCore
0x140013372  mov     ebx, eax
0x140013374  test    eax, eax
0x140013376  js      short loc_1400133AA
0x140013378  mov     rdx, rsi
0x14001337b  mov     rcx, rdi
0x14001337e  call    lldpCreateDriverWdf
0x140013383  mov     ebx, eax
0x140013385  test    eax, eax
0x140013387  js      short loc_1400133AA
0x140013389  call    lldpRegisterProtocol
0x14001338e  mov     ebx, eax
0x140013390  test    eax, eax
0x140013392  jnz     short loc_1400133A6
0x140013394  call    lldpNmrRegisterProvider
0x140013399  mov     ebx, eax
0x14001339b  test    eax, eax
0x14001339d  js      short loc_1400133AA
0x14001339f  call    lldpInitializeControlDevice
0x1400133a4  mov     ebx, eax
0x1400133a6  test    ebx, ebx
0x1400133a8  jns     short loc_1400133C2
0x1400133aa  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x1400133b1  test    rcx, rcx
0x1400133b4  jz      short loc_1400133BD
0x1400133b6  call    lldpDriverUnloadWdf
0x1400133bb  jmp     short loc_1400133C2
0x1400133bd  call    wil_UninitializeFeatureStaging
0x1400133c2  mov     rsi, [rsp+28h+arg_8]
0x1400133c7  mov     eax, ebx
0x1400133c9  mov     rbx, [rsp+28h+arg_0]
0x1400133ce  add     rsp, 20h
0x1400133d2  pop     rdi
0x1400133d3  retn
```
