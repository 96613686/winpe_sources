# TdiNotifyAddDevice

- ea: `0x140033b90`
- end: `0x140033cfe`
- name: `TdiNotifyAddDevice`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400060c4`

## callees

- `0x140003cb4`
- `0x14000c004`
- `0x14001fc70`
- `0x14001fd40`
- `0x140033b90`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x140033c35`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140033ca9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140033ca9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140033c12`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140033c12`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033c02`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033c02`

## string_xrefs

- `0x140033bc7`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 TdiNotifyAddDevice()
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const wchar_t *, _QWORD *); // rax
  __int64 result; // rax
  int v2; // edx
  int v3; // r8d
  int v4; // r9d
  int v5; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v7[14]; // [rsp+50h] [rbp-19h] BYREF
  char v8; // [rsp+D0h] [rbp+67h] BYREF

  v8 = 0;
  memset(v7, 0, sizeof(v7));
  LODWORD(v7[1]) = 260;
  v7[0] = TdiTransportsValueQueryCallback;
  LODWORD(v7[4]) = 117440512;
  v7[2] = L"Transports";
  v7[5] = 0;
  v7[3] = &v8;
  LODWORD(v7[6]) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD *))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD *))RtlQueryRegistryValues;
  result = SystemRoutineAddress(1, L"Winsock\\Parameters", v7);
  if ( (int)result < 0 || !v8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_ld(WPP_GLOBAL_Control->DeviceExtension, v2, v3, v4, 0, v8, result);
    result = ZwUpdateWnfStateData(&WNF_NDIS_ADAPTER_ARRIVAL, 0, 0, 0, 0, 0, 0);
    if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v5,
               2,
               19,
               (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
               result);
  }
  return result;
}

```

## disassembly

```asm
0x140033b90  mov     [rsp-8+arg_8], rdi
0x140033b95  push    rbp
0x140033b96  lea     rbp, [rsp-57h]
0x140033b9b  sub     rsp, 0C0h
0x140033ba2  xor     edx, edx; Val
0x140033ba4  mov     [rbp+57h+arg_0], 0
0x140033ba8  lea     rcx, [rbp+57h+var_70]; void *
0x140033bac  lea     r8d, [rdx+70h]; Size
0x140033bb0  call    memset
0x140033bb5  lea     rax, TdiTransportsValueQueryCallback
0x140033bbc  mov     [rbp+57h+var_68], 104h
0x140033bc3  mov     [rbp+57h+var_70], rax
0x140033bc7  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140033bce  lea     rax, aTransports; "Transports"
0x140033bd5  mov     [rbp+57h+var_50], 7000000h
0x140033bdc  mov     [rbp+57h+var_60], rax
0x140033be0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140033be4  lea     rax, [rbp+57h+arg_0]
0x140033be8  mov     [rbp+57h+var_48], 0
0x140033bf0  xorps   xmm0, xmm0
0x140033bf3  mov     [rbp+57h+var_58], rax
0x140033bf7  mov     [rbp+57h+var_40], 0
0x140033bfe  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140033c02  call    cs:__imp_RtlInitUnicodeString
0x140033c09  nop     dword ptr [rax+rax+00h]
0x140033c0e  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140033c12  call    cs:__imp_MmGetSystemRoutineAddress
0x140033c19  nop     dword ptr [rax+rax+00h]
0x140033c1e  lea     r8, [rbp+57h+var_70]
0x140033c22  mov     [rsp+0C0h+var_A0], 0
0x140033c2b  test    rax, rax
0x140033c2e  lea     rdx, aWinsockParamet; "Winsock\\Parameters"
0x140033c35  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140033c3d  xor     r9d, r9d
0x140033c40  lea     ecx, [r9+1]
0x140033c44  call    _guard_dispatch_icall
0x140033c49  movzx   ecx, [rbp+57h+arg_0]
0x140033c4d  test    eax, eax
0x140033c4f  js      short loc_140033C59
0x140033c51  test    cl, cl
0x140033c53  jnz     loc_140033CEC
0x140033c59  lea     rdi, WPP_RECORDER_INITIALIZED
0x140033c60  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033c67  jz      short loc_140033C81
0x140033c69  mov     [rsp+0C0h+var_90], eax
0x140033c6d  mov     [rsp+0C0h+var_98], ecx
0x140033c71  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c78  mov     rcx, [rcx+40h]
0x140033c7c  call    WPP_RECORDER_SF_ld
0x140033c81  mov     [rsp+0C0h+var_90], 0
0x140033c89  lea     rcx, WNF_NDIS_ADAPTER_ARRIVAL
0x140033c90  mov     [rsp+0C0h+var_98], 0
0x140033c98  xor     r9d, r9d
0x140033c9b  xor     r8d, r8d
0x140033c9e  mov     [rsp+0C0h+var_A0], 0
0x140033ca7  xor     edx, edx
0x140033ca9  call    cs:__imp_ZwUpdateWnfStateData
0x140033cb0  nop     dword ptr [rax+rax+00h]
0x140033cb5  test    eax, eax
0x140033cb7  jns     short loc_140033CEC
0x140033cb9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033cc0  jz      short loc_140033CEC
0x140033cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140033cc9  mov     r9d, 13h
0x140033ccf  mov     [rsp+0C0h+var_98], eax
0x140033cd3  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140033cda  mov     [rsp+0C0h+var_A0], rax
0x140033cdf  mov     rcx, [rcx+40h]
0x140033ce3  lea     r8d, [r9-11h]
0x140033ce7  call    WPP_RECORDER_SF_d
0x140033cec  mov     rdi, [rsp+0C0h+arg_8]
0x140033cf4  add     rsp, 0C0h
0x140033cfb  pop     rbp
0x140033cfc  retn
```
