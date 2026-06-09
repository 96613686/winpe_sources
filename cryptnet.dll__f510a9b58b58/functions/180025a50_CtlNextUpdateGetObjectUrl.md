# CtlNextUpdateGetObjectUrl

- ea: `0x180025a50`
- end: `0x180025afc`
- name: `CtlNextUpdateGetObjectUrl`
- size: `172`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180014df0`
- `0x180015590`
- `0x180025a50`
- `0x180025b04`

## pseudocode

```c
__int64 __fastcall CtlNextUpdateGetObjectUrl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int RawUrlData; // ebx
  _BYTE v10[72]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v11; // [rsp+98h] [rbp+10h] BYREF

  v11 = 4;
  RawUrlData = ObjectContextGetRawUrlData((char *)3, "1.3.6.1.4.1.311.10.2", v10, (__int64)&v11);
  if ( RawUrlData == 1 )
  {
    RawUrlData = GetUrlArrayAndInfoFromNextUpdateLocation(v11, (unsigned int)v10, a4, a5, a6, a7);
    ObjectContextFreeRawUrlData(v11, v10);
  }
  return RawUrlData;
}

```

## disassembly

```asm
0x180025a50  mov     r11, rsp
0x180025a53  mov     [r11+8], rbx
0x180025a57  push    rdi
0x180025a58  sub     rsp, 80h
0x180025a5f  lea     rax, [r11+10h]
0x180025a63  mov     dword ptr [r11+10h], 4
0x180025a6b  mov     [r11-58h], rax
0x180025a6f  mov     rdi, r9
0x180025a72  lea     rax, [r11-48h]
0x180025a76  mov     r9d, r8d
0x180025a79  mov     r8d, [rdx+8]
0x180025a7d  mov     ecx, 3; char *
0x180025a82  mov     rdx, [rdx]
0x180025a85  mov     [r11-60h], rax
0x180025a89  lea     rax, a136141311102; "1.3.6.1.4.1.311.10.2"
0x180025a90  mov     [r11-68h], rax
0x180025a94  call    ObjectContextGetRawUrlData
0x180025a99  mov     ebx, eax
0x180025a9b  cmp     eax, 1
0x180025a9e  jnz     short loc_180025AE9
0x180025aa0  mov     rax, [rsp+88h+arg_30]
0x180025aa8  lea     rdx, [rsp+88h+var_48]
0x180025aad  mov     r9, [rsp+88h+arg_20]
0x180025ab5  mov     r8, rdi
0x180025ab8  mov     ecx, [rsp+88h+arg_8]
0x180025abf  mov     [rsp+88h+var_60], rax
0x180025ac4  mov     rax, [rsp+88h+arg_28]
0x180025acc  mov     [rsp+88h+var_68], rax
0x180025ad1  call    GetUrlArrayAndInfoFromNextUpdateLocation
0x180025ad6  mov     ecx, [rsp+88h+arg_8]
0x180025add  lea     rdx, [rsp+88h+var_48]
0x180025ae2  mov     ebx, eax
0x180025ae4  call    ObjectContextFreeRawUrlData
0x180025ae9  mov     eax, ebx
0x180025aeb  mov     rbx, [rsp+88h+arg_0]
0x180025af3  add     rsp, 80h
0x180025afa  pop     rdi
0x180025afb  retn
```
