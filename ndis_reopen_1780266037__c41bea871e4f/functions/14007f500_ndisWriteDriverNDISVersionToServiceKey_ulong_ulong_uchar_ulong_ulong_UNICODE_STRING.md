# ndisWriteDriverNDISVersionToServiceKey(ulong,ulong,uchar,ulong,ulong,_UNICODE_STRING *)

- ea: `0x14007f500`
- end: `0x14007f658`
- name: `?ndisWriteDriverNDISVersionToServiceKey@@YAXKKEKKPEAU_UNICODE_STRING@@@Z`
- size: `344`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int8, unsigned int, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14007d1e0`
- `0x14007f810`
- `0x14009c0c0`
- `0x1400bcb60`
- `0x1400bcf90`

## callees

- `0x14007f500`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f564`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f59c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f5d9`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f618`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f564`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f59c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f5d9`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14007f618`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14007f51c`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14007f51c`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14007f626`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14007f642`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14007f626`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14007f642`

## pseudocode

```c
void __fastcall ndisWriteDriverNDISVersionToServiceKey(
        int a1,
        int a2,
        char a3,
        int a4,
        unsigned int a5,
        struct _UNICODE_STRING *a6)
{
  wchar_t *Buffer; // rdx
  wchar_t *v11; // rdx
  wchar_t *v12; // rdx
  _DWORD ValueData[14]; // [rsp+30h] [rbp-38h] BYREF

  ValueData[0] = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    ValueData[0] = a1;
    RtlWriteRegistryValue(1u, a6->Buffer, L"NdisMajorVersion", 4u, ValueData, 4u);
    Buffer = a6->Buffer;
    ValueData[0] = a2;
    RtlWriteRegistryValue(1u, Buffer, L"NdisMinorVersion", 4u, ValueData, 4u);
    v11 = a6->Buffer;
    if ( a3 )
    {
      ValueData[0] = a4;
      RtlWriteRegistryValue(1u, v11, L"DriverMajorVersion", 4u, ValueData, 4u);
      v12 = a6->Buffer;
      ValueData[0] = a5;
      RtlWriteRegistryValue(1u, v12, L"DriverMinorVersion", 4u, ValueData, 4u);
    }
    else
    {
      RtlDeleteRegistryValue(1u, v11, L"DriverMajorVersion");
      RtlDeleteRegistryValue(1u, a6->Buffer, L"DriverMinorVersion");
    }
  }
}

```

## disassembly

```asm
0x14007f500  push    rbx
0x14007f502  push    rbp
0x14007f503  push    rsi
0x14007f504  push    rdi
0x14007f505  sub     rsp, 48h
0x14007f509  mov     ebp, r9d
0x14007f50c  mov     [rsp+68h+var_38], 0
0x14007f514  movzx   edi, r8b
0x14007f518  mov     esi, edx
0x14007f51a  mov     ebx, ecx
0x14007f51c  call    cs:__imp_RtlIsStateSeparationEnabled
0x14007f523  nop     dword ptr [rax+rax+00h]
0x14007f528  test    al, al
0x14007f52a  jnz     loc_14007F64E
0x14007f530  mov     [rsp+68h+var_38], ebx
0x14007f534  lea     rax, [rsp+68h+var_38]
0x14007f539  mov     rbx, [rsp+68h+arg_28]
0x14007f541  lea     r8, aNdismajorversi; "NdisMajorVersion"
0x14007f548  mov     [rsp+68h+ValueLength], 4; ValueLength
0x14007f550  mov     r9d, 4; ValueType
0x14007f556  mov     ecx, 1; RelativeTo
0x14007f55b  mov     [rsp+68h+ValueData], rax; ValueData
0x14007f560  mov     rdx, [rbx+8]; Path
0x14007f564  call    cs:__imp_RtlWriteRegistryValue
0x14007f56b  nop     dword ptr [rax+rax+00h]
0x14007f570  mov     rdx, [rbx+8]; Path
0x14007f574  lea     rax, [rsp+68h+var_38]
0x14007f579  mov     [rsp+68h+ValueLength], 4; ValueLength
0x14007f581  lea     r8, aNdisminorversi; "NdisMinorVersion"
0x14007f588  mov     r9d, 4; ValueType
0x14007f58e  mov     [rsp+68h+ValueData], rax; ValueData
0x14007f593  mov     ecx, 1; RelativeTo
0x14007f598  mov     [rsp+68h+var_38], esi
0x14007f59c  call    cs:__imp_RtlWriteRegistryValue
0x14007f5a3  nop     dword ptr [rax+rax+00h]
0x14007f5a8  mov     rdx, [rbx+8]; Path
0x14007f5ac  lea     r8, aDrivermajorver; "DriverMajorVersion"
0x14007f5b3  mov     ecx, 1; RelativeTo
0x14007f5b8  test    dil, dil
0x14007f5bb  jz      short loc_14007F626
0x14007f5bd  lea     rax, [rsp+68h+var_38]
0x14007f5c2  mov     [rsp+68h+ValueLength], 4; ValueLength
0x14007f5ca  mov     r9d, 4; ValueType
0x14007f5d0  mov     [rsp+68h+ValueData], rax; ValueData
0x14007f5d5  mov     [rsp+68h+var_38], ebp
0x14007f5d9  call    cs:__imp_RtlWriteRegistryValue
0x14007f5e0  nop     dword ptr [rax+rax+00h]
0x14007f5e5  mov     eax, [rsp+68h+arg_20]
0x14007f5ec  lea     r8, aDriverminorver; "DriverMinorVersion"
0x14007f5f3  mov     rdx, [rbx+8]; Path
0x14007f5f7  mov     r9d, 4; ValueType
0x14007f5fd  mov     [rsp+68h+var_38], eax
0x14007f601  mov     ecx, 1; RelativeTo
0x14007f606  lea     rax, [rsp+68h+var_38]
0x14007f60b  mov     [rsp+68h+ValueLength], 4; ValueLength
0x14007f613  mov     [rsp+68h+ValueData], rax; ValueData
0x14007f618  call    cs:__imp_RtlWriteRegistryValue
0x14007f61f  nop     dword ptr [rax+rax+00h]
0x14007f624  jmp     short loc_14007F64E
0x14007f626  call    cs:__imp_RtlDeleteRegistryValue
0x14007f62d  nop     dword ptr [rax+rax+00h]
0x14007f632  mov     rdx, [rbx+8]; Path
0x14007f636  lea     r8, aDriverminorver; "DriverMinorVersion"
0x14007f63d  mov     ecx, 1; RelativeTo
0x14007f642  call    cs:__imp_RtlDeleteRegistryValue
0x14007f649  nop     dword ptr [rax+rax+00h]
0x14007f64e  add     rsp, 48h
0x14007f652  pop     rdi
0x14007f653  pop     rsi
0x14007f654  pop     rbp
0x14007f655  pop     rbx
0x14007f656  retn
```
