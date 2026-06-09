# EtwEx_tidActivityInfo

- ea: `0x14000f54c`
- end: `0x14000f5d1`
- name: `EtwEx_tidActivityInfo`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000adf8`
- `0x14000bd90`

## callees

- `0x14000f54c`
- `0x140013110`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000f5b2`
- `ntoskrnl!EtwWrite` at `0x14000f5b2`

## pseudocode

```c
NTSTATUS __fastcall EtwEx_tidActivityInfo(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  int v4; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-30h] BYREF
  int *v6; // [rsp+48h] [rbp-20h]
  __int64 v7; // [rsp+50h] [rbp-18h]

  v4 = 0;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, a2, a3, 0, 0);
  *(_QWORD *)&UserData.Size = 16;
  UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v7 = 4;
  v6 = &v4;
  return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, a2, a3, 2u, &UserData);
}

```

## disassembly

```asm
0x14000f54c  mov     r11, rsp
0x14000f54f  sub     rsp, 68h
0x14000f553  mov     rax, cs:__security_cookie
0x14000f55a  xor     rax, rsp
0x14000f55d  mov     [rsp+68h+var_10], rax
0x14000f562  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000f568  xor     r9d, r9d; UserDataCount
0x14000f56b  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000f572  mov     [r11-38h], r9d
0x14000f576  test    eax, eax
0x14000f578  jz      short loc_14000F5AD
0x14000f57a  lea     rax, Microsoft_Windows_Networking_ProviderId
0x14000f581  mov     qword ptr [r11-28h], 10h
0x14000f589  mov     [r11-30h], rax
0x14000f58d  mov     r9d, 2
0x14000f593  lea     rax, [r11-38h]
0x14000f597  mov     qword ptr [r11-18h], 4
0x14000f59f  mov     [r11-20h], rax
0x14000f5a3  lea     rax, [r11-30h]
0x14000f5a7  mov     [r11-48h], rax
0x14000f5ab  jmp     short loc_14000F5B2
0x14000f5ad  mov     [rsp+68h+UserData], r9; UserData
0x14000f5b2  call    cs:__imp_EtwWrite
0x14000f5b9  nop     dword ptr [rax+rax+00h]
0x14000f5be  mov     rcx, [rsp+68h+var_10]
0x14000f5c3  xor     rcx, rsp; StackCookie
0x14000f5c6  call    __security_check_cookie
0x14000f5cb  add     rsp, 68h
0x14000f5cf  retn
```
