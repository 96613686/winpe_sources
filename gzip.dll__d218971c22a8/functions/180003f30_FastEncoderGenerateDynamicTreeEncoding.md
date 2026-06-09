# FastEncoderGenerateDynamicTreeEncoding

- ea: `0x180003f30`
- end: `0x180003fde`
- name: `FastEncoderGenerateDynamicTreeEncoding`
- size: `174`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003df0`

## callees

- `0x180004220`

## pseudocode

```c
__int64 FastEncoderGenerateDynamicTreeEncoding()
{
  __int64 result; // rax
  _OWORD v1[2]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v2; // [rsp+40h] [rbp-78h]
  __int64 *v3; // [rsp+48h] [rbp-70h]
  int *v4; // [rsp+50h] [rbp-68h]
  __int64 *v5; // [rsp+58h] [rbp-60h]
  __int128 v6; // [rsp+60h] [rbp-58h]
  __int128 v7; // [rsp+70h] [rbp-48h]
  __int128 v8; // [rsp+80h] [rbp-38h]
  __int128 v9; // [rsp+90h] [rbp-28h]
  __int64 v10; // [rsp+A0h] [rbp-18h]

  memset(v1, 0, sizeof(v1));
  v2 = 0;
  v7 = 0;
  v10 = 0;
  v4 = &g_FastEncoderPostTreeBitbuf;
  v5 = qword_18000A870;
  v8 = 0;
  v3 = g_FastEncoderTreeStructureData;
  v9 = 0;
  v6 = 0x300000005uLL;
  outputTreeStructure((__int64)v1, g_FastEncoderLiteralTreeLength, g_FastEncoderDistanceTreeLength);
  g_FastEncoderTreeLength = (_DWORD)v3 - (unsigned int)g_FastEncoderTreeStructureData;
  g_FastEncoderPostTreeBitbuf = v6;
  result = DWORD1(v6);
  g_FastEncoderPostTreeBitcount = DWORD1(v6);
  return result;
}

```

## disassembly

```asm
0x180003f30  mov     r11, rsp
0x180003f33  push    rbx
0x180003f34  sub     rsp, 0B0h
0x180003f3b  xorps   xmm0, xmm0
0x180003f3e  lea     rbx, g_FastEncoderTreeStructureData
0x180003f45  movups  [rsp+0B8h+var_58], xmm0
0x180003f4a  xor     eax, eax
0x180003f4c  lea     r8, g_FastEncoderDistanceTreeLength
0x180003f53  movups  [rsp+0B8h+var_98], xmm0
0x180003f58  lea     rdx, g_FastEncoderLiteralTreeLength
0x180003f5f  movups  [rsp+0B8h+var_88], xmm0
0x180003f64  lea     rcx, [rsp+0B8h+var_98]
0x180003f69  movups  [rsp+0B8h+var_78], xmm0
0x180003f6e  movups  [rsp+0B8h+var_68], xmm0
0x180003f73  movups  [rsp+0B8h+var_48], xmm0
0x180003f78  mov     [r11-18h], rax
0x180003f7c  lea     rax, g_FastEncoderPostTreeBitbuf
0x180003f83  mov     [r11-68h], rax
0x180003f87  lea     rax, qword_18000A870
0x180003f8e  mov     [r11-60h], rax
0x180003f92  movups  xmmword ptr [r11-38h], xmm0
0x180003f97  mov     [r11-70h], rbx
0x180003f9b  movups  xmmword ptr [r11-28h], xmm0
0x180003fa0  mov     dword ptr [rsp+0B8h+var_58], 5
0x180003fa8  mov     dword ptr [rsp+0B8h+var_58+4], 3
0x180003fb0  call    outputTreeStructure
0x180003fb5  mov     eax, dword ptr [rsp+0B8h+var_78+8]
0x180003fb9  sub     eax, ebx
0x180003fbb  mov     cs:g_FastEncoderTreeLength, eax
0x180003fc1  mov     eax, dword ptr [rsp+0B8h+var_58]
0x180003fc5  mov     cs:g_FastEncoderPostTreeBitbuf, eax
0x180003fcb  mov     eax, dword ptr [rsp+0B8h+var_58+4]
0x180003fcf  mov     cs:g_FastEncoderPostTreeBitcount, eax
0x180003fd5  add     rsp, 0B0h
0x180003fdc  pop     rbx
0x180003fdd  retn
```
