# EtwEx_tidActivityInfo

- ea: `0x140001240`
- end: `0x1400012c5`
- name: `EtwEx_tidActivityInfo`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400027b0`

## callees

- `0x140001240`
- `0x140025c20`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000129f`
- `ntoskrnl!EtwWrite` at `0x14000129f`

## pseudocode

```c
NTSTATUS __fastcall EtwEx_tidActivityInfo(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  int v4; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-30h] BYREF
  int *v6; // [rsp+48h] [rbp-20h]
  __int64 v7; // [rsp+50h] [rbp-18h]

  v4 = 0;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, a2, a3, 0, 0);
  *(_QWORD *)&v5.Size = 16;
  v5.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v7 = 4;
  v6 = &v4;
  return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, a2, a3, 2u, &v5);
}

```

## disassembly

```asm
0x140001240  mov     r11, rsp
0x140001243  sub     rsp, 68h
0x140001247  mov     rax, cs:__security_cookie
0x14000124e  xor     rax, rsp
0x140001251  mov     [rsp+68h+var_10], rax
0x140001256  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000125c  xor     r9d, r9d
0x14000125f  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140001266  mov     [r11-38h], r9d
0x14000126a  test    eax, eax
0x14000126c  jz      short loc_1400012BE
0x14000126e  lea     rax, Microsoft_Windows_Networking_ProviderId
0x140001275  mov     qword ptr [r11-28h], 10h
0x14000127d  mov     [r11-30h], rax
0x140001281  mov     r9d, 2; UserDataCount
0x140001287  lea     rax, [r11-38h]
0x14000128b  mov     qword ptr [r11-18h], 4
0x140001293  mov     [r11-20h], rax
0x140001297  lea     rax, [r11-30h]
0x14000129b  mov     [r11-48h], rax
0x14000129f  call    cs:__imp_EtwWrite
0x1400012a6  nop     dword ptr [rax+rax+00h]
0x1400012ab  mov     rcx, [rsp+68h+var_10]
0x1400012b0  xor     rcx, rsp; StackCookie
0x1400012b3  call    __security_check_cookie
0x1400012b8  add     rsp, 68h
0x1400012bc  retn
0x1400012be  mov     [rsp+68h+var_48], r9
0x1400012c3  jmp     short loc_14000129F
```
