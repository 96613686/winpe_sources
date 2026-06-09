# ObjectContextUrlFromInfoAccess

- ea: `0x180015bb8`
- end: `0x180015c59`
- name: `ObjectContextUrlFromInfoAccess`
- size: `161`
- prototype: `__int64 __fastcall(char *, __int64, __int64, char *, int, __int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800257f0`
- `0x180025980`
- `0x1800259e0`

## callees

- `0x180014df0`
- `0x180015590`
- `0x180015610`
- `0x180015bb8`

## pseudocode

```c
__int64 __fastcall ObjectContextUrlFromInfoAccess(
        char *a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int a11)
{
  unsigned int RawUrlData; // ebx
  _BYTE v13[72]; // [rsp+40h] [rbp-48h] BYREF

  a11 = 4;
  RawUrlData = ObjectContextGetRawUrlData(a1, a4, v13, (__int64)&a11);
  if ( RawUrlData == 1 )
  {
    RawUrlData = GetUrlArrayAndInfoFromInfoAccess(a11, (unsigned int)v13, a6, a7, a8, a9, a10);
    ObjectContextFreeRawUrlData(a11, v13);
  }
  return RawUrlData;
}

```

## disassembly

```asm
0x180015bb8  mov     r11, rsp
0x180015bbb  push    rbx
0x180015bbc  sub     rsp, 80h
0x180015bc3  lea     rax, [r11+58h]
0x180015bc7  mov     dword ptr [r11+58h], 4
0x180015bcf  mov     [r11-58h], rax
0x180015bd3  lea     rax, [r11-48h]
0x180015bd7  mov     [r11-60h], rax
0x180015bdb  mov     [r11-68h], r9
0x180015bdf  mov     r9d, [rsp+88h+arg_20]
0x180015be7  call    ObjectContextGetRawUrlData
0x180015bec  mov     ebx, eax
0x180015bee  cmp     eax, 1
0x180015bf1  jnz     short loc_180015C4E
0x180015bf3  mov     rax, [rsp+88h+arg_48]
0x180015bfb  lea     rdx, [rsp+88h+var_48]
0x180015c00  mov     r9, [rsp+88h+arg_30]
0x180015c08  mov     r8, [rsp+88h+arg_28]
0x180015c10  mov     ecx, [rsp+88h+arg_50]
0x180015c17  mov     [rsp+88h+var_58], rax
0x180015c1c  mov     rax, [rsp+88h+arg_40]
0x180015c24  mov     [rsp+88h+var_60], rax
0x180015c29  mov     rax, [rsp+88h+arg_38]
0x180015c31  mov     [rsp+88h+var_68], rax
0x180015c36  call    GetUrlArrayAndInfoFromInfoAccess
0x180015c3b  mov     ecx, [rsp+88h+arg_50]
0x180015c42  lea     rdx, [rsp+88h+var_48]
0x180015c47  mov     ebx, eax
0x180015c49  call    ObjectContextFreeRawUrlData
0x180015c4e  mov     eax, ebx
0x180015c50  add     rsp, 80h
0x180015c57  pop     rbx
0x180015c58  retn
```
