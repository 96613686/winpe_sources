# WPP_SF_sDsd

- ea: `0x18000d02c`
- end: `0x18000d0ed`
- name: `WPP_SF_sDsd`
- size: `193`
- prototype: ``
- caller_count: `108`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001550`
- `0x180001c08`
- `0x180002280`
- `0x180002400`
- `0x180002550`
- `0x180002790`
- `0x180002c34`
- `0x180002f74`
- `0x180003150`
- `0x180003460`
- `0x18000382c`
- `0x180003a68`
- `0x180003ce4`
- `0x180003f1c`
- `0x18000423c`
- `0x180004310`
- `0x180004454`
- `0x180004c00`
- `0x1800050d0`
- `0x1800053ac`
- `0x180005a18`
- `0x180005fa0`
- `0x180006090`
- `0x180006730`
- `0x180006a70`
- `0x180006c9c`
- `0x180006f40`
- `0x180007024`
- `0x180007098`
- `0x180007274`
- `0x180007420`
- `0x1800077f0`
- `0x180007958`
- `0x1800079cc`
- `0x180007ae0`
- `0x180007b80`
- `0x180007df4`
- `0x1800081e8`
- `0x180008820`
- `0x180008a90`
- `0x180008da0`
- `0x1800090e0`
- `0x18000962c`
- `0x180009830`
- `0x180009aa0`
- `0x180009cf0`
- `0x180009ecc`
- `0x18000a3d0`
- `0x18000a7e0`
- `0x18000aa90`

## callees

- `0x18000d02c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000d0d9`
- `ntdll!EtwTraceMessage` at `0x18000d0d9`

## pseudocode

```c
__int64 WPP_SF_sDsd(__int64 a1, __int64 a2, __int64 a3, const char *a4, ...)
{
  const char *v4; // r8
  __int64 v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // rdx
  bool v9; // zf
  __int64 v11; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  const char *v13; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, const char *);
  v4 = v13;
  v5 = -1;
  v6 = 5;
  if ( v13 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v13[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  if ( !v13 )
    v4 = "NULL";
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = "NULL";
  return EtwTraceMessage(
           a1,
           43,
           WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids,
           10,
           a4,
           v6,
           (__int64 *)va,
           4,
           v4,
           v8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18000d02c  push    rbx
0x18000d02e  sub     rsp, 70h
0x18000d032  mov     r8, [rsp+78h+arg_28]
0x18000d03a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d03e  xor     r11d, r11d
0x18000d041  mov     r10d, 5
0x18000d047  test    r8, r8
0x18000d04a  jz      loc_18000D0E5
0x18000d050  mov     rdx, rax
0x18000d053  inc     rdx
0x18000d056  cmp     [r8+rdx], r11b
0x18000d05a  jnz     short loc_18000D053
0x18000d05c  inc     rdx
0x18000d05f  test    r8, r8
0x18000d062  lea     rbx, aNull; "NULL"
0x18000d069  cmovz   r8, rbx
0x18000d06d  test    r9, r9
0x18000d070  jz      short loc_18000D082
0x18000d072  inc     rax
0x18000d075  cmp     [r9+rax], r11b
0x18000d079  jnz     short loc_18000D072
0x18000d07b  lea     r10, [rax+1]
0x18000d07f  test    r9, r9
0x18000d082  mov     [rsp+78h+var_18], r11
0x18000d087  lea     rax, [rsp+78h+arg_30]
0x18000d08f  cmovz   r9, rbx
0x18000d093  mov     ebx, 0Ah
0x18000d098  lea     r11d, [rbx-6]
0x18000d09c  mov     [rsp+78h+var_20], r11
0x18000d0a1  mov     [rsp+78h+var_28], rax
0x18000d0a6  lea     rax, [rsp+78h+arg_20]
0x18000d0ae  mov     [rsp+78h+var_30], rdx
0x18000d0b3  lea     edx, [rbx+21h]
0x18000d0b6  mov     [rsp+78h+var_38], r8
0x18000d0bb  lea     r8, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids
0x18000d0c2  mov     [rsp+78h+var_40], r11
0x18000d0c7  mov     [rsp+78h+var_48], rax
0x18000d0cc  mov     [rsp+78h+var_50], r10
0x18000d0d1  mov     [rsp+78h+var_58], r9
0x18000d0d6  mov     r9d, ebx
0x18000d0d9  call    cs:__imp_EtwTraceMessage
0x18000d0df  add     rsp, 70h
0x18000d0e3  pop     rbx
0x18000d0e4  retn
0x18000d0e5  mov     rdx, r10
0x18000d0e8  jmp     loc_18000D05F
```
