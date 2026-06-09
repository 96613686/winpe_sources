# CContext::LogDroppedAPICall(EMarkerOp)

- ea: `0x1800f125c`
- end: `0x1800f12cc`
- name: `?LogDroppedAPICall@CContext@@QEBAXW4EMarkerOp@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `73`
- callee_count: `1`
- tags: ``

## callers

- `0x180001440`
- `0x1800015a0`
- `0x180001a20`
- `0x1800020d0`
- `0x180002ea0`
- `0x180003fb0`
- `0x180004e10`
- `0x180007500`
- `0x1800079a0`
- `0x1800080c0`
- `0x180008b5c`
- `0x180034720`
- `0x180091f80`
- `0x180092210`
- `0x1800cce20`
- `0x1800cced0`
- `0x1800ccf80`
- `0x1800cd050`
- `0x1800cec00`
- `0x1800cedf0`
- `0x1800cf110`
- `0x1800d0270`
- `0x1800d20b0`
- `0x1800f05f0`
- `0x1800f06d0`
- `0x1800f07a0`
- `0x1800f0870`
- `0x1800f0950`
- `0x1800f0a30`
- `0x1800f0af0`
- `0x1800f0ba0`
- `0x1800f0c60`
- `0x1800f0d20`
- `0x1800f0e00`
- `0x1800f0ec0`
- `0x1800f0f60`
- `0x1800f1040`
- `0x1800f1120`
- `0x1800f11b0`
- `0x180146bf0`
- `0x18014b9d0`
- `0x18014c0e0`
- `0x18014c1b0`
- `0x18014d6c0`
- `0x18014d780`
- `0x18014db40`
- `0x18014dda0`
- `0x18014dea0`
- `0x18014dff0`
- `0x18014f5c0`

## callees

- `0x1800a9d20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800f12b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800f12b4`

## pseudocode

```c
ULONG __fastcall CContext::LogDroppedAPICall(__int64 a1, unsigned __int8 a2)
{
  int v3; // [rsp+20h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+28h] [rbp-30h] BYREF
  int *v5; // [rsp+38h] [rbp-20h]
  __int64 v6; // [rsp+40h] [rbp-18h]

  *(_QWORD *)&v4.Size = 8;
  v4.Ptr = a1 + 168;
  v3 = a2;
  v5 = &v3;
  v6 = 4;
  return EventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11RuntimeDroppedCall, 2u, &v4);
}

```

## disassembly

```asm
0x1800f125c  mov     r11, rsp
0x1800f125f  sub     rsp, 58h
0x1800f1263  mov     rax, cs:__security_cookie
0x1800f126a  xor     rax, rsp
0x1800f126d  mov     [rsp+58h+var_10], rax
0x1800f1272  lea     rax, [rcx+0A8h]
0x1800f1279  mov     qword ptr [r11-28h], 8
0x1800f1281  mov     rcx, cs:Direct3D11EtwProviderGuid_Context; RegHandle
0x1800f1288  lea     r9, [r11-30h]; UserData
0x1800f128c  mov     [r11-30h], rax
0x1800f1290  mov     r8d, 2; UserDataCount
0x1800f1296  movzx   eax, dl
0x1800f1299  lea     rdx, EventD3D11RuntimeDroppedCall; EventDescriptor
0x1800f12a0  mov     [rsp+58h+var_38], eax
0x1800f12a4  lea     rax, [r11-38h]
0x1800f12a8  mov     [r11-20h], rax
0x1800f12ac  mov     qword ptr [r11-18h], 4
0x1800f12b4  call    cs:__imp_EventWrite
0x1800f12ba  mov     rcx, [rsp+58h+var_10]
0x1800f12bf  xor     rcx, rsp; StackCookie
0x1800f12c2  call    __security_check_cookie
0x1800f12c7  add     rsp, 58h
0x1800f12cb  retn
```
