# MyAdd_NL_Header

- ea: `0x180017cf4`
- end: `0x180017e6b`
- name: `MyAdd_NL_Header`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800178f8`
- `0x18001e1ec`

## callees

- `0x18003d040`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180017d25`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180017d25`

## pseudocode

```c
__int64 __fastcall MyAdd_NL_Header(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned __int16 v10; // cx
  __int16 v11; // ax
  __int16 v12; // cx
  __int16 v13; // ax
  __int16 v14; // cx
  __int16 v15; // ax
  __int16 v16; // cx
  __int16 v17; // ax
  __int16 v18; // cx
  __int16 v19; // ax
  __int16 v20; // cx
  __int64 result; // rax
  _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-48h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  *(_DWORD *)(a2 + 16) = _byteswap_ulong(a5);
  *(_DWORD *)(a2 + 20) = _byteswap_ulong(a6);
  v10 = _byteswap_ushort(SystemTime.wYear);
  *(_DWORD *)(a2 + 4) = 544106839;
  v11 = (__int16)SystemTime.wMonth >> 8;
  *(_WORD *)(a2 + 24) = v10;
  v12 = (LOBYTE(SystemTime.wMonth) << 8) | (unsigned __int8)v11;
  *(_DWORD *)(a2 + 8) = 4098;
  v13 = (__int16)SystemTime.wDay >> 8;
  *(_WORD *)(a2 + 26) = v12;
  v14 = (LOBYTE(SystemTime.wDay) << 8) | (unsigned __int8)v13;
  strcpy((char *)(a2 + 36), "acspMSFT");
  v15 = (__int16)SystemTime.wHour >> 8;
  *(_WORD *)(a2 + 28) = v14;
  v16 = (LOBYTE(SystemTime.wHour) << 8) | (unsigned __int8)v15;
  *(_BYTE *)(a2 + 45) = 0;
  *(_WORD *)(a2 + 46) = 0;
  v17 = (__int16)SystemTime.wMinute >> 8;
  *(_WORD *)(a2 + 30) = v16;
  v18 = (LOBYTE(SystemTime.wMinute) << 8) | (unsigned __int8)v17;
  *(_QWORD *)(a2 + 48) = 1413894989;
  v19 = (__int16)SystemTime.wSecond >> 8;
  *(_WORD *)(a2 + 32) = v18;
  v20 = (LOBYTE(SystemTime.wSecond) << 8) | (unsigned __int8)v19;
  *(_DWORD *)(a2 + 68) = -705298432;
  *(_WORD *)(a2 + 34) = v20;
  *(_QWORD *)(a2 + 56) = 0;
  result = 0;
  *(_DWORD *)a2 = _byteswap_ulong(a1);
  *(_DWORD *)(a2 + 12) = _byteswap_ulong(a4);
  *(_DWORD *)(a2 + 64) = _byteswap_ulong(a3);
  *(_DWORD *)(a2 + 72) = 256;
  *(_DWORD *)(a2 + 76) = 752025600;
  *(_DWORD *)(a2 + 80) = 541805141;
  return result;
}

```

## disassembly

```asm
0x180017cf4  push    rbx
0x180017cf6  push    rsi
0x180017cf7  push    rdi
0x180017cf8  push    r14
0x180017cfa  sub     rsp, 48h
0x180017cfe  mov     rax, cs:__security_cookie
0x180017d05  xor     rax, rsp
0x180017d08  mov     [rsp+68h+var_38], rax
0x180017d0d  mov     ebx, ecx
0x180017d0f  xorps   xmm0, xmm0
0x180017d12  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180017d17  mov     edi, r9d
0x180017d1a  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180017d1f  mov     esi, r8d
0x180017d22  mov     r14, rdx
0x180017d25  call    cs:__imp_GetLocalTime
0x180017d2b  mov     eax, [rsp+68h+arg_20]
0x180017d32  bswap   eax
0x180017d34  mov     [r14+10h], eax
0x180017d38  mov     eax, [rsp+68h+arg_28]
0x180017d3f  bswap   eax
0x180017d41  mov     [r14+14h], eax
0x180017d45  movzx   eax, [rsp+68h+SystemTime.wYear]
0x180017d4a  sar     ax, 8
0x180017d4e  movzx   ecx, al
0x180017d51  movzx   eax, byte ptr [rsp+68h+SystemTime.wYear]
0x180017d56  shl     ax, 8
0x180017d5a  or      cx, ax
0x180017d5d  mov     dword ptr [r14+4], 206E6957h
0x180017d65  movzx   eax, [rsp+68h+SystemTime.wMonth]
0x180017d6a  sar     ax, 8
0x180017d6e  mov     [r14+18h], cx
0x180017d73  movzx   ecx, al
0x180017d76  movzx   eax, byte ptr [rsp+68h+SystemTime.wMonth]
0x180017d7b  shl     ax, 8
0x180017d7f  or      cx, ax
0x180017d82  mov     dword ptr [r14+8], 1002h
0x180017d8a  movzx   eax, [rsp+68h+SystemTime.wDay]
0x180017d8f  sar     ax, 8
0x180017d93  mov     [r14+1Ah], cx
0x180017d98  movzx   ecx, al
0x180017d9b  movzx   eax, byte ptr [rsp+68h+SystemTime.wDay]
0x180017da0  shl     ax, 8
0x180017da4  or      cx, ax
0x180017da7  mov     dword ptr [r14+24h], 70736361h
0x180017daf  movzx   eax, [rsp+68h+SystemTime.wHour]
0x180017db4  sar     ax, 8
0x180017db8  mov     [r14+1Ch], cx
0x180017dbd  movzx   ecx, al
0x180017dc0  movzx   eax, byte ptr [rsp+68h+SystemTime.wHour]
0x180017dc5  shl     ax, 8
0x180017dc9  or      cx, ax
0x180017dcc  mov     qword ptr [r14+28h], 5446534Dh
0x180017dd4  movzx   eax, [rsp+68h+SystemTime.wMinute]
0x180017dd9  sar     ax, 8
0x180017ddd  mov     [r14+1Eh], cx
0x180017de2  movzx   ecx, al
0x180017de5  movzx   eax, byte ptr [rsp+68h+SystemTime.wMinute]
0x180017dea  shl     ax, 8
0x180017dee  or      cx, ax
0x180017df1  mov     qword ptr [r14+30h], 5446534Dh
0x180017df9  movzx   eax, [rsp+68h+SystemTime.wSecond]
0x180017dfe  sar     ax, 8
0x180017e02  mov     [r14+20h], cx
0x180017e07  movzx   ecx, al
0x180017e0a  movzx   eax, byte ptr [rsp+68h+SystemTime.wSecond]
0x180017e0f  shl     ax, 8
0x180017e13  or      cx, ax
0x180017e16  mov     dword ptr [r14+44h], 0D5F60000h
0x180017e1e  mov     [r14+22h], cx
0x180017e23  xor     ecx, ecx
0x180017e25  bswap   ebx
0x180017e27  bswap   edi
0x180017e29  bswap   esi
0x180017e2b  mov     [r14+38h], rcx
0x180017e2f  xor     eax, eax
0x180017e31  mov     [r14], ebx
0x180017e34  mov     [r14+0Ch], edi
0x180017e38  mov     [r14+40h], esi
0x180017e3c  mov     dword ptr [r14+48h], 100h
0x180017e44  mov     dword ptr [r14+4Ch], 2CD30000h
0x180017e4c  mov     dword ptr [r14+50h], 204B4A55h
0x180017e54  mov     rcx, [rsp+68h+var_38]
0x180017e59  xor     rcx, rsp; StackCookie
0x180017e5c  call    __security_check_cookie
0x180017e61  add     rsp, 48h
0x180017e65  pop     r14
0x180017e67  pop     rdi
0x180017e68  pop     rsi
0x180017e69  pop     rbx
0x180017e6a  retn
```
