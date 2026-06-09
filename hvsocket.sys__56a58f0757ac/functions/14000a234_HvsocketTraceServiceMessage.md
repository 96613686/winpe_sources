# HvsocketTraceServiceMessage

- ea: `0x14000a234`
- end: `0x14000a2c2`
- name: `HvsocketTraceServiceMessage`
- size: `142`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140021da4`

## callees

- `0x140001008`
- `0x14000a234`
- `0x14000bfa0`

## string_xrefs

- `0x14000a25b`: `Transient service created.`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceServiceMessage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-68h] BYREF
  const char *v6; // [rsp+50h] [rbp-48h]
  __int64 v7; // [rsp+58h] [rbp-40h]
  __int64 v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  __int64 v10; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    v8 = a2;
    v6 = "Transient service created.";
    v7 = 27;
    v9 = 16;
    v10 = a3;
    v11 = 16;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&dword_14001175C,
             a3,
             a4,
             5u,
             &v5);
  }
  return result;
}

```

## disassembly

```asm
0x14000a234  mov     r11, rsp
0x14000a237  sub     rsp, 98h
0x14000a23e  mov     rax, cs:__security_cookie
0x14000a245  xor     rax, rsp
0x14000a248  mov     [rsp+98h+var_18], rax
0x14000a250  mov     eax, cs:dword_140013058
0x14000a256  cmp     eax, 4
0x14000a259  jbe     short loc_14000A2A9
0x14000a25b  lea     rax, aTransientServi; "Transient service created."
0x14000a262  mov     [r11-38h], rdx
0x14000a266  mov     [r11-48h], rax
0x14000a26a  lea     rdx, dword_14001175C; int
0x14000a271  lea     rax, [r11-68h]
0x14000a275  mov     qword ptr [r11-40h], 1Bh
0x14000a27d  mov     [r11-70h], rax
0x14000a281  lea     rcx, dword_140013058; int
0x14000a288  mov     [rsp+98h+var_78], 5; ULONG
0x14000a290  mov     qword ptr [r11-30h], 10h
0x14000a298  mov     [r11-28h], r8
0x14000a29c  mov     qword ptr [r11-20h], 10h
0x14000a2a4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a2a9  mov     rcx, [rsp+98h+var_18]
0x14000a2b1  xor     rcx, rsp; StackCookie
0x14000a2b4  call    __security_check_cookie
0x14000a2b9  add     rsp, 98h
0x14000a2c0  retn
```
