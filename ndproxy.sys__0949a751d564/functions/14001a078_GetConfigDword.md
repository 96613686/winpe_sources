# GetConfigDword

- ea: `0x14001a078`
- end: `0x14001a0f8`
- name: `GetConfigDword`
- size: `128`
- prototype: `__int64 __fastcall(NDIS_HANDLE ConfigurationHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001a100`

## callees

- `0x14001a078`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a0a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a0a8`
- `NDIS!NdisReadConfiguration` at `0x14001a0ce`
- `NDIS!NdisReadConfiguration` at `0x14001a0ce`

## pseudocode

```c
__int64 __fastcall GetConfigDword(NDIS_HANDLE ConfigurationHandle, const WCHAR *a2, ULONG *a3)
{
  __int64 result; // rax
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+30h] [rbp-28h] BYREF
  UNICODE_STRING Keyword; // [rsp+38h] [rbp-20h] BYREF
  int Status; // [rsp+78h] [rbp+20h] BYREF

  Status = 0;
  ParameterValue = 0;
  Keyword = 0;
  RtlInitUnicodeString(&Keyword, a2);
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  result = (unsigned int)Status;
  if ( !Status )
    *a3 = ParameterValue->ParameterData.IntegerData;
  return result;
}

```

## disassembly

```asm
0x14001a078  mov     rax, rsp
0x14001a07b  mov     [rax+8], rbx
0x14001a07f  mov     [rax+20h], r9d
0x14001a083  push    rdi
0x14001a084  sub     rsp, 50h
0x14001a088  mov     rbx, rcx
0x14001a08b  mov     dword ptr [rax+20h], 0
0x14001a092  xorps   xmm0, xmm0
0x14001a095  mov     qword ptr [rax-28h], 0
0x14001a09d  lea     rcx, [rax-20h]; DestinationString
0x14001a0a1  mov     rdi, r8
0x14001a0a4  movups  xmmword ptr [rax-20h], xmm0
0x14001a0a8  call    cs:__imp_RtlInitUnicodeString
0x14001a0af  nop     dword ptr [rax+rax+00h]
0x14001a0b4  lea     r9, [rsp+58h+Keyword]; Keyword
0x14001a0b9  mov     [rsp+58h+ParameterType], 0; ParameterType
0x14001a0c1  mov     r8, rbx; ConfigurationHandle
0x14001a0c4  lea     rdx, [rsp+58h+ParameterValue]; ParameterValue
0x14001a0c9  lea     rcx, [rsp+58h+Status]; Status
0x14001a0ce  call    cs:__imp_NdisReadConfiguration
0x14001a0d5  nop     dword ptr [rax+rax+00h]
0x14001a0da  mov     eax, [rsp+58h+Status]
0x14001a0de  test    eax, eax
0x14001a0e0  jnz     short loc_14001A0EC
0x14001a0e2  mov     rcx, [rsp+58h+ParameterValue]
0x14001a0e7  mov     edx, [rcx+8]
0x14001a0ea  mov     [rdi], edx
0x14001a0ec  mov     rbx, [rsp+58h+arg_0]
0x14001a0f1  add     rsp, 50h
0x14001a0f5  pop     rdi
0x14001a0f6  retn
```
