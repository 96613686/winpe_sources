# HalpMcGetRollbackRequest

- ea: `0x1405a2b58`
- end: `0x1405a2c11`
- name: `HalpMcGetRollbackRequest`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14074b2a0`

## callees

- `0x140403380`
- `0x1405a2b58`
- `0x140696db4`
- `0x1406eb0e0`
- `0x1406f7380`
- `0x140a2d350`

## string_xrefs

- `0x1405a2b8e`: `RtlQueryRegistryValuesEx`
- `0x1405a2bd4`: `McUpdate`
- `0x1405a2b7c`: `RollbackRequest`

## pseudocode

```c
__int64 HalpMcGetRollbackRequest()
{
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v2[8]; // [rsp+40h] [rbp-19h] BYREF
  int v3; // [rsp+48h] [rbp-11h]
  const wchar_t *v4; // [rsp+50h] [rbp-9h]
  int *v5; // [rsp+58h] [rbp-1h]
  int v6; // [rsp+60h] [rbp+7h]
  int v7; // [rsp+C0h] [rbp+67h] BYREF

  v7 = 0;
  memset_0(v2, 0, 0x70u);
  v3 = 288;
  v4 = L"RollbackRequest";
  v6 = 0x4000000;
  v5 = &v7;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  MmGetSystemRoutineAddress(&DestinationString);
  if ( (int)guard_dispatch_icall_no_overrides(2) >= 0 )
    v7 &= 1u;
  return PrExtControlOperations(11, &v7, 1);
}

```

## disassembly

```asm
0x1405a2b58  push    rbp
0x1405a2b5a  lea     rbp, [rsp-57h]
0x1405a2b5f  sub     rsp, 0B0h
0x1405a2b66  xor     edx, edx; Val
0x1405a2b68  mov     [rbp+57h+arg_0], 0
0x1405a2b6f  lea     rcx, [rbp+57h+var_70]; void *
0x1405a2b73  lea     r8d, [rdx+70h]; Size
0x1405a2b77  call    memset_0
0x1405a2b7c  lea     rax, aRollbackreques; "RollbackRequest"
0x1405a2b83  mov     [rbp+57h+var_68], 120h
0x1405a2b8a  mov     [rbp+57h+var_60], rax
0x1405a2b8e  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1405a2b95  lea     rax, [rbp+57h+arg_0]
0x1405a2b99  mov     [rbp+57h+var_50], 4000000h
0x1405a2ba0  xorps   xmm0, xmm0
0x1405a2ba3  mov     [rbp+57h+var_58], rax
0x1405a2ba7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1405a2bab  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1405a2baf  call    RtlInitUnicodeString
0x1405a2bb4  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1405a2bb8  call    MmGetSystemRoutineAddress
0x1405a2bbd  lea     rcx, RtlQueryRegistryValues
0x1405a2bc4  mov     [rsp+0B0h+var_90], 0
0x1405a2bcd  test    rax, rax
0x1405a2bd0  lea     r8, [rbp+57h+var_70]
0x1405a2bd4  lea     rdx, aMcupdate; "McUpdate"
0x1405a2bdb  cmovz   rax, rcx
0x1405a2bdf  xor     r9d, r9d
0x1405a2be2  lea     ecx, [r9+2]
0x1405a2be6  call    _guard_dispatch_icall_no_overrides
0x1405a2beb  mov     r8d, 1
0x1405a2bf1  test    eax, eax
0x1405a2bf3  js      short loc_1405A2BF9
0x1405a2bf5  and     [rbp+57h+arg_0], r8d
0x1405a2bf9  lea     rdx, [rbp+57h+arg_0]
0x1405a2bfd  mov     ecx, 0Bh
0x1405a2c02  call    PrExtControlOperations
0x1405a2c07  add     rsp, 0B0h
0x1405a2c0e  pop     rbp
0x1405a2c0f  retn
```
