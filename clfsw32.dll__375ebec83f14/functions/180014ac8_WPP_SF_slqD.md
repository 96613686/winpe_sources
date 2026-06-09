# WPP_SF_slqD

- ea: `0x180014ac8`
- end: `0x180014b47`
- name: `WPP_SF_slqD`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180011cfc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180014b32`
- `ntdll!EtwTraceMessage` at `0x180014b32`

## string_xrefs

- `0x180014b1f`: `CClfsMarshallingContext::ReadMarshalledLogRecord`

## pseudocode

```c
__int64 WPP_SF_slqD(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, ...)
{
  int v6[6]; // [rsp+70h] [rbp-18h] BYREF
  __int64 v7; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v7 = va_arg(va1, _QWORD);
  v6[0] = 4798;
  return EtwTraceMessage(
           a1,
           43,
           WPP_80b3afe238ac3962112c483aa44eeada_Traceguids,
           10,
           "CClfsMarshallingContext::ReadMarshalledLogRecord",
           49,
           v6,
           4,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x180014ac8  mov     r11, rsp
0x180014acb  sub     rsp, 88h
0x180014ad2  mov     qword ptr [r11-28h], 0
0x180014ada  lea     rax, [r11+38h]
0x180014ade  mov     r9d, 0Ah
0x180014ae4  mov     [rsp+88h+var_18], 12BEh
0x180014aec  lea     r8, WPP_80b3afe238ac3962112c483aa44eeada_Traceguids
0x180014af3  lea     edx, [r9-6]
0x180014af7  mov     [r11-30h], rdx
0x180014afb  mov     [r11-38h], rax
0x180014aff  lea     rax, [r11+30h]
0x180014b03  mov     qword ptr [r11-40h], 8
0x180014b0b  mov     [r11-48h], rax
0x180014b0f  lea     rax, [r11-18h]
0x180014b13  mov     [r11-50h], rdx
0x180014b17  lea     edx, [r9+21h]
0x180014b1b  mov     [r11-58h], rax
0x180014b1f  lea     rax, aCclfsmarshalli_2; "CClfsMarshallingContext::ReadMarshalled"...
0x180014b26  mov     qword ptr [r11-60h], 31h ; '1'
0x180014b2e  mov     [r11-68h], rax
0x180014b32  call    cs:__imp_EtwTraceMessage
0x180014b39  nop     dword ptr [rax+rax+00h]
0x180014b3e  add     rsp, 88h
0x180014b45  retn
```
