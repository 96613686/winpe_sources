# ndisWriteDriverNDISVersionToServiceKey(ulong,ulong,uchar,ulong,ulong,_UNICODE_STRING *)

- ea: `0x140079e30`
- end: `0x140079f88`
- name: `?ndisWriteDriverNDISVersionToServiceKey@@YAXKKEKKPEAU_UNICODE_STRING@@@Z`
- size: `344`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int8, unsigned int, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140077a80`
- `0x14007a070`
- `0x140096e40`
- `0x1400b7730`
- `0x1400b7b60`

## callees

- `0x140079e30`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x140079e94`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079ecc`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079f09`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079f48`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079e94`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079ecc`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079f09`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140079f48`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140079e4c`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140079e4c`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140079f56`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140079f72`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140079f56`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140079f72`

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
0x140079e30  push    rbx
0x140079e32  push    rbp
0x140079e33  push    rsi
0x140079e34  push    rdi
0x140079e35  sub     rsp, 48h
0x140079e39  mov     ebp, r9d
0x140079e3c  mov     [rsp+68h+var_38], 0
0x140079e44  movzx   edi, r8b
0x140079e48  mov     esi, edx
0x140079e4a  mov     ebx, ecx
0x140079e4c  call    cs:__imp_RtlIsStateSeparationEnabled
0x140079e53  nop     dword ptr [rax+rax+00h]
0x140079e58  test    al, al
0x140079e5a  jnz     loc_140079F7E
0x140079e60  mov     [rsp+68h+var_38], ebx
0x140079e64  lea     rax, [rsp+68h+var_38]
0x140079e69  mov     rbx, [rsp+68h+arg_28]
0x140079e71  lea     r8, aNdismajorversi; "NdisMajorVersion"
0x140079e78  mov     [rsp+68h+ValueLength], 4; ValueLength
0x140079e80  mov     r9d, 4; ValueType
0x140079e86  mov     ecx, 1; RelativeTo
0x140079e8b  mov     [rsp+68h+ValueData], rax; ValueData
0x140079e90  mov     rdx, [rbx+8]; Path
0x140079e94  call    cs:__imp_RtlWriteRegistryValue
0x140079e9b  nop     dword ptr [rax+rax+00h]
0x140079ea0  mov     rdx, [rbx+8]; Path
0x140079ea4  lea     rax, [rsp+68h+var_38]
0x140079ea9  mov     [rsp+68h+ValueLength], 4; ValueLength
0x140079eb1  lea     r8, aNdisminorversi; "NdisMinorVersion"
0x140079eb8  mov     r9d, 4; ValueType
0x140079ebe  mov     [rsp+68h+ValueData], rax; ValueData
0x140079ec3  mov     ecx, 1; RelativeTo
0x140079ec8  mov     [rsp+68h+var_38], esi
0x140079ecc  call    cs:__imp_RtlWriteRegistryValue
0x140079ed3  nop     dword ptr [rax+rax+00h]
0x140079ed8  mov     rdx, [rbx+8]; Path
0x140079edc  lea     r8, aDrivermajorver; "DriverMajorVersion"
0x140079ee3  mov     ecx, 1; RelativeTo
0x140079ee8  test    dil, dil
0x140079eeb  jz      short loc_140079F56
0x140079eed  lea     rax, [rsp+68h+var_38]
0x140079ef2  mov     [rsp+68h+ValueLength], 4; ValueLength
0x140079efa  mov     r9d, 4; ValueType
0x140079f00  mov     [rsp+68h+ValueData], rax; ValueData
0x140079f05  mov     [rsp+68h+var_38], ebp
0x140079f09  call    cs:__imp_RtlWriteRegistryValue
0x140079f10  nop     dword ptr [rax+rax+00h]
0x140079f15  mov     eax, [rsp+68h+arg_20]
0x140079f1c  lea     r8, aDriverminorver; "DriverMinorVersion"
0x140079f23  mov     rdx, [rbx+8]; Path
0x140079f27  mov     r9d, 4; ValueType
0x140079f2d  mov     [rsp+68h+var_38], eax
0x140079f31  mov     ecx, 1; RelativeTo
0x140079f36  lea     rax, [rsp+68h+var_38]
0x140079f3b  mov     [rsp+68h+ValueLength], 4; ValueLength
0x140079f43  mov     [rsp+68h+ValueData], rax; ValueData
0x140079f48  call    cs:__imp_RtlWriteRegistryValue
0x140079f4f  nop     dword ptr [rax+rax+00h]
0x140079f54  jmp     short loc_140079F7E
0x140079f56  call    cs:__imp_RtlDeleteRegistryValue
0x140079f5d  nop     dword ptr [rax+rax+00h]
0x140079f62  mov     rdx, [rbx+8]; Path
0x140079f66  lea     r8, aDriverminorver; "DriverMinorVersion"
0x140079f6d  mov     ecx, 1; RelativeTo
0x140079f72  call    cs:__imp_RtlDeleteRegistryValue
0x140079f79  nop     dword ptr [rax+rax+00h]
0x140079f7e  add     rsp, 48h
0x140079f82  pop     rdi
0x140079f83  pop     rsi
0x140079f84  pop     rbp
0x140079f85  pop     rbx
0x140079f86  retn
```
