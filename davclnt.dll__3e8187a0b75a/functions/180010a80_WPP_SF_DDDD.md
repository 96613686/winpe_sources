# WPP_SF_DDDD

- ea: `0x180010a80`
- end: `0x180010ae5`
- name: `WPP_SF_DDDD`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001600`
- `0x180002970`
- `0x180004340`
- `0x180006c50`
- `0x1800070c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010ada`
- `ntdll!EtwTraceMessage` at `0x180010ada`

## pseudocode

```c
__int64 __fastcall WPP_SF_DDDD(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // [rsp+98h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 236, &v5);
}

```

## disassembly

```asm
0x180010a80  mov     r11, rsp
0x180010a83  mov     [r11+20h], r9d
0x180010a87  sub     rsp, 78h
0x180010a8b  mov     qword ptr [r11-18h], 0
0x180010a93  lea     rax, [r11+38h]
0x180010a97  mov     edx, 4
0x180010a9c  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010aa3  mov     [r11-20h], rdx
0x180010aa7  mov     r9d, 0ECh
0x180010aad  mov     [r11-28h], rax
0x180010ab1  lea     rax, [r11+30h]
0x180010ab5  mov     [r11-30h], rdx
0x180010ab9  mov     [r11-38h], rax
0x180010abd  lea     rax, [r11+28h]
0x180010ac1  mov     [r11-40h], rdx
0x180010ac5  mov     [r11-48h], rax
0x180010ac9  lea     rax, [r11+20h]
0x180010acd  mov     [r11-50h], rdx
0x180010ad1  mov     edx, 2Bh ; '+'
0x180010ad6  mov     [r11-58h], rax
0x180010ada  call    cs:__imp_EtwTraceMessage
0x180010ae0  add     rsp, 78h
0x180010ae4  retn
```
