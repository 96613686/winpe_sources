# DriverEntry

- ea: `0x140045000`
- end: `0x1400450ec`
- name: `DriverEntry`
- size: `236`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140045580`

## callees

- `0x140029df0`
- `0x140029fc8`
- `0x14002a44c`
- `0x14002a8e0`
- `0x14002aeb0`
- `0x14002b33c`
- `0x14003df4c`
- `0x140045000`
- `0x1400450ec`
- `0x1400451e0`

## import_xrefs

- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400450cf`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400450cf`
- `ntoskrnl!InitSafeBootMode` at `0x140045021`
- `ntoskrnl!EtwUnregister` at `0x140045053`
- `ntoskrnl!EtwUnregister` at `0x140045053`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS DeviceObject; // ebx
  REGHANDLE v5; // rcx

  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14001B040);
  if ( InitSafeBootMode )
  {
    DeviceObject = -1073740961;
  }
  else
  {
    SecInitializeRuntime();
    DeviceObject = SecInitializeGlobals((__int64)DriverObject, (const void **)RegistryPath);
    if ( DeviceObject >= 0 )
    {
      if ( (unsigned __int8)SecIsServiceProtectionDisabled()
        || (DeviceObject = SecSetProviderSecurity(&Microsoft_Windows_Sec_Provider, qword_140013360), DeviceObject >= 0) )
      {
        _mm_lfence();
        DeviceObject = SecCreateDeviceObject(DriverObject);
        if ( DeviceObject >= 0 )
        {
          _mm_lfence();
          SecInitializeBootConfig();
          IoRegisterDriverReinitialization(DriverObject, SecDriverReinitialize, 0);
          SecKdpProtectSection(&SecRuntime);
          return DeviceObject;
        }
      }
    }
  }
  SecFreeGlobals();
  v5 = RegHandle;
  RegHandle = 0;
  dword_14001B040 = 0;
  EtwUnregister(v5);
  return DeviceObject;
}

```

## disassembly

```asm
0x140045000  mov     [rsp+arg_0], rbx
0x140045005  push    rdi
0x140045006  sub     rsp, 20h
0x14004500a  mov     rbx, rdx
0x14004500d  mov     rdi, rcx
0x140045010  xor     edx, edx
0x140045012  lea     rcx, dword_14001B040; CallbackContext
0x140045019  xor     r8d, r8d
0x14004501c  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140045021  mov     rax, cs:__imp_InitSafeBootMode
0x140045028  cmp     dword ptr [rax], 0
0x14004502b  jbe     short loc_14004506D
0x14004502d  mov     ebx, 0C000035Fh
0x140045032  call    SecFreeGlobals
0x140045037  mov     rcx, cs:RegHandle; RegHandle
0x14004503e  mov     cs:RegHandle, 0
0x140045049  mov     cs:dword_14001B040, 0
0x140045053  call    cs:__imp_EtwUnregister
0x14004505a  nop     dword ptr [rax+rax+00h]
0x14004505f  mov     eax, ebx
0x140045061  mov     rbx, [rsp+28h+arg_0]
0x140045066  add     rsp, 20h
0x14004506a  pop     rdi
0x14004506b  retn
0x14004506d  call    SecInitializeRuntime
0x140045072  mov     rdx, rbx
0x140045075  mov     rcx, rdi
0x140045078  call    SecInitializeGlobals
0x14004507d  mov     ebx, eax
0x14004507f  test    eax, eax
0x140045081  js      short loc_140045032
0x140045083  call    SecIsServiceProtectionDisabled
0x140045088  test    al, al
0x14004508a  jnz     short loc_1400450A5
0x14004508c  lea     rdx, qword_140013360
0x140045093  lea     rcx, Microsoft_Windows_Sec_Provider
0x14004509a  call    SecSetProviderSecurity
0x14004509f  mov     ebx, eax
0x1400450a1  test    eax, eax
0x1400450a3  js      short loc_140045032
0x1400450a5  lfence
0x1400450a8  mov     rcx, rdi
0x1400450ab  call    SecCreateDeviceObject
0x1400450b0  mov     ebx, eax
0x1400450b2  test    eax, eax
0x1400450b4  js      loc_140045032
0x1400450ba  lfence
0x1400450bd  call    SecInitializeBootConfig
0x1400450c2  xor     r8d, r8d; Context
0x1400450c5  lea     rdx, SecDriverReinitialize; DriverReinitializationRoutine
0x1400450cc  mov     rcx, rdi; DriverObject
0x1400450cf  call    cs:__imp_IoRegisterDriverReinitialization
0x1400450d6  nop     dword ptr [rax+rax+00h]
0x1400450db  lea     rcx, SecRuntime
0x1400450e2  call    SecKdpProtectSection
0x1400450e7  jmp     loc_14004505F
```
