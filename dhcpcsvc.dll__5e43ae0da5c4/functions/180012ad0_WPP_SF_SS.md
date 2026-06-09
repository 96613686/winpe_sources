# WPP_SF_SS

- ea: `0x180012ad0`
- end: `0x180012b6c`
- name: `WPP_SF_SS`
- size: `156`
- prototype: ``
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001240`
- `0x180001490`
- `0x180004170`
- `0x180005be0`
- `0x180005d30`
- `0x180006300`
- `0x180006c90`
- `0x180006e10`
- `0x180007010`
- `0x180007480`
- `0x180007950`
- `0x180007c00`
- `0x180008210`
- `0x18000847c`
- `0x180008aa0`
- `0x180008dd4`
- `0x18000a180`
- `0x18000a950`
- `0x18000ac50`
- `0x18000b180`
- `0x18000b360`
- `0x18000b590`
- `0x18000b7c0`
- `0x18000b9d0`
- `0x18000bd64`
- `0x18000beb0`
- `0x18000bf80`
- `0x18000c110`
- `0x18000d660`
- `0x18000fc0c`

## callees

- `0x180003e70`
- `0x180012ad0`

## pseudocode

```c
ULONG __fastcall WPP_SF_SS(__int64 a1, USHORT a2, ULONGLONG a3, const wchar_t *a4, const wchar_t *a5)
{
  const wchar_t *v5; // r10
  __int64 v6; // rcx
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      v10 = a5[++v8] == 0;
    while ( !v10 );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      v10 = a4[++v6] == 0;
    while ( !v10 );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return FastWppTraceMessage(1028, a2, a3, a4, v7, v5, v9, 0);
}

```

## disassembly

```asm
0x180012ad0  push    rbx
0x180012ad2  sub     rsp, 40h
0x180012ad6  mov     r10, [rsp+48h+arg_20]
0x180012adb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012ae2  mov     r11d, 0Ah
0x180012ae8  test    r10, r10
0x180012aeb  jz      short loc_180012B67
0x180012aed  mov     rax, rcx
0x180012af0  cmp     word ptr [r10+rax*2+2], 0
0x180012af7  lea     rax, [rax+1]
0x180012afb  jnz     short loc_180012AF0
0x180012afd  lea     rax, ds:2[rax*2]
0x180012b05  test    r10, r10
0x180012b08  lea     rbx, aNull; "NULL"
0x180012b0f  cmovz   r10, rbx
0x180012b13  test    r9, r9
0x180012b16  jz      short loc_180012B38
0x180012b18  nop     dword ptr [rax+rax+00000000h]
0x180012b20  cmp     word ptr [r9+rcx*2+2], 0
0x180012b27  lea     rcx, [rcx+1]
0x180012b2b  jnz     short loc_180012B20
0x180012b2d  lea     r11, ds:2[rcx*2]
0x180012b35  test    r9, r9
0x180012b38  mov     [rsp+48h+var_10], 0
0x180012b41  cmovz   r9, rbx
0x180012b45  mov     [rsp+48h+var_18], rax
0x180012b4a  mov     ecx, 404h
0x180012b4f  mov     [rsp+48h+var_20], r10
0x180012b54  movzx   edx, dx
0x180012b57  mov     [rsp+48h+var_28], r11
0x180012b5c  call    FastWppTraceMessage
0x180012b61  add     rsp, 40h
0x180012b65  pop     rbx
0x180012b66  retn
0x180012b67  mov     rax, r11
0x180012b6a  jmp     short loc_180012B05
```
