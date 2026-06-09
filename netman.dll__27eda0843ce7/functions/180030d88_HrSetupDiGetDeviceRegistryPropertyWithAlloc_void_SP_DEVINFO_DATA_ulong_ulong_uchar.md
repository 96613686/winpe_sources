# HrSetupDiGetDeviceRegistryPropertyWithAlloc(void *,_SP_DEVINFO_DATA *,ulong,ulong *,uchar * *)

- ea: `0x180030d88`
- end: `0x180030e5e`
- name: `?HrSetupDiGetDeviceRegistryPropertyWithAlloc@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KPEAKPEAPEAE@Z`
- size: `214`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, DWORD Property, PDWORD PropertyRegDataType, void **RequiredSize)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180030d20`

## callees

- `0x180019c68`
- `0x180019c9c`
- `0x18003060c`
- `0x180030d88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180030ddf`
- `KERNEL32!GetLastError` at `0x180030ddf`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180030dd5`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180030e21`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180030dd5`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180030e21`

## pseudocode

```c
__int64 __fastcall HrSetupDiGetDeviceRegistryPropertyWithAlloc(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        DWORD Property,
        PDWORD PropertyRegDataType,
        void **RequiredSize)
{
  void **v5; // rdi
  BYTE *PropertyBuffer; // rax
  unsigned int v11; // ebx

  v5 = RequiredSize;
  LODWORD(RequiredSize) = 0;
  *v5 = 0;
  if ( SetupDiGetDeviceRegistryPropertyW(DeviceInfoSet, DeviceInfoData, Property, 0, 0, 0, (PDWORD)&RequiredSize) )
    return (unsigned int)-2147467259;
  if ( GetLastError() != 122 )
    goto LABEL_5;
  PropertyBuffer = (BYTE *)MemAlloc((unsigned int)RequiredSize);
  *v5 = PropertyBuffer;
  if ( !PropertyBuffer )
    return (unsigned int)-2147024882;
  v11 = 0;
  if ( !SetupDiGetDeviceRegistryPropertyW(
          DeviceInfoSet,
          DeviceInfoData,
          Property,
          PropertyRegDataType,
          PropertyBuffer,
          (DWORD)RequiredSize,
          0) )
  {
LABEL_5:
    MemFree(*v5);
    *v5 = 0;
    return (unsigned int)HrFromLastWin32Error();
  }
  return v11;
}

```

## disassembly

```asm
0x180030d88  mov     r11, rsp
0x180030d8b  push    rbx
0x180030d8c  push    rbp
0x180030d8d  push    rsi
0x180030d8e  push    rdi
0x180030d8f  push    r14
0x180030d91  push    r15
0x180030d93  sub     rsp, 48h
0x180030d97  mov     rdi, [rsp+78h+arg_20]
0x180030d9f  lea     rax, [r11+28h]
0x180030da3  mov     [r11-48h], rax
0x180030da7  mov     r15, r9
0x180030daa  mov     [rsp+78h+PropertyBufferSize], 0; PropertyBufferSize
0x180030db2  xor     r9d, r9d; PropertyRegDataType
0x180030db5  mov     esi, r8d
0x180030db8  mov     dword ptr [r11+28h], 0
0x180030dc0  mov     qword ptr [rdi], 0
0x180030dc7  mov     rbp, rdx
0x180030dca  mov     r14, rcx
0x180030dcd  mov     qword ptr [r11-58h], 0
0x180030dd5  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180030ddb  test    eax, eax
0x180030ddd  jnz     short loc_180030E4A
0x180030ddf  call    cs:__imp_GetLastError
0x180030de5  cmp     eax, 7Ah ; 'z'
0x180030de8  jnz     short loc_180030E2B
0x180030dea  mov     ecx, dword ptr [rsp+78h+arg_20]; unsigned __int64
0x180030df1  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180030df6  mov     [rdi], rax
0x180030df9  test    rax, rax
0x180030dfc  jz      short loc_180030E43
0x180030dfe  mov     ecx, dword ptr [rsp+78h+arg_20]
0x180030e05  xor     ebx, ebx
0x180030e07  mov     [rsp+78h+RequiredSize], rbx; RequiredSize
0x180030e0c  mov     r9, r15; PropertyRegDataType
0x180030e0f  mov     [rsp+78h+PropertyBufferSize], ecx; PropertyBufferSize
0x180030e13  mov     r8d, esi; Property
0x180030e16  mov     rcx, r14; DeviceInfoSet
0x180030e19  mov     [rsp+78h+PropertyBuffer], rax; PropertyBuffer
0x180030e1e  mov     rdx, rbp; DeviceInfoData
0x180030e21  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180030e27  test    eax, eax
0x180030e29  jnz     short loc_180030E4F
0x180030e2b  mov     rcx, [rdi]; lpMem
0x180030e2e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180030e33  mov     qword ptr [rdi], 0
0x180030e3a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030e3f  mov     ebx, eax
0x180030e41  jmp     short loc_180030E4F
0x180030e43  mov     ebx, 8007000Eh
0x180030e48  jmp     short loc_180030E4F
0x180030e4a  mov     ebx, 80004005h
0x180030e4f  mov     eax, ebx
0x180030e51  add     rsp, 48h
0x180030e55  pop     r15
0x180030e57  pop     r14
0x180030e59  pop     rdi
0x180030e5a  pop     rsi
0x180030e5b  pop     rbp
0x180030e5c  pop     rbx
0x180030e5d  retn
```
