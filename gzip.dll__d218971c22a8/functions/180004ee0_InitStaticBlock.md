# InitStaticBlock

- ea: `0x180004ee0`
- end: `0x180004fa3`
- name: `InitStaticBlock`
- size: `195`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x180004ee0`

## pseudocode

```c
void InitStaticBlock()
{
  if ( !g_InitialisedStaticBlock )
  {
    g_StaticLiteralTreeLength = (__int128)_mm_load_si128((const __m128i *)&_xmm);
    g_InitialisedStaticBlock = 1;
    xmmword_18000AE30 = g_StaticLiteralTreeLength;
    dword_18000AF38 = 134744072;
    xmmword_18000AE40 = g_StaticLiteralTreeLength;
    dword_18000AF3C = 134744072;
    xmmword_18000AE50 = g_StaticLiteralTreeLength;
    xmmword_18000AE60 = g_StaticLiteralTreeLength;
    xmmword_18000AE70 = g_StaticLiteralTreeLength;
    xmmword_18000AE80 = g_StaticLiteralTreeLength;
    xmmword_18000AE90 = g_StaticLiteralTreeLength;
    xmmword_18000AEA0 = g_StaticLiteralTreeLength;
    xmmword_18000AEB0 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
    xmmword_18000AEC0 = xmmword_18000AEB0;
    xmmword_18000AED0 = xmmword_18000AEB0;
    xmmword_18000AEE0 = xmmword_18000AEB0;
    xmmword_18000AEF0 = xmmword_18000AEB0;
    xmmword_18000AF00 = xmmword_18000AEB0;
    xmmword_18000AF10 = xmmword_18000AEB0;
    xmmword_18000AF20 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
    qword_18000AF30 = xmmword_18000AF20;
  }
}

```

## disassembly

```asm
0x180004ee0  cmp     cs:g_InitialisedStaticBlock, 0
0x180004ee7  jnz     locret_180004FA2
0x180004eed  movdqa  xmm0, cs:__xmm@08080808080808080808080808080808
0x180004ef5  movups  cs:g_StaticLiteralTreeLength, xmm0
0x180004efc  mov     cs:g_InitialisedStaticBlock, 1
0x180004f06  movups  cs:xmmword_18000AE30, xmm0
0x180004f0d  mov     cs:dword_18000AF38, 8080808h
0x180004f17  movups  cs:xmmword_18000AE40, xmm0
0x180004f1e  mov     cs:dword_18000AF3C, 8080808h
0x180004f28  movups  cs:xmmword_18000AE50, xmm0
0x180004f2f  movups  cs:xmmword_18000AE60, xmm0
0x180004f36  movups  cs:xmmword_18000AE70, xmm0
0x180004f3d  movups  cs:xmmword_18000AE80, xmm0
0x180004f44  movups  cs:xmmword_18000AE90, xmm0
0x180004f4b  movups  cs:xmmword_18000AEA0, xmm0
0x180004f52  movdqa  xmm0, cs:__xmm@09090909090909090909090909090909
0x180004f5a  movups  cs:xmmword_18000AEB0, xmm0
0x180004f61  movups  cs:xmmword_18000AEC0, xmm0
0x180004f68  movups  cs:xmmword_18000AED0, xmm0
0x180004f6f  movups  cs:xmmword_18000AEE0, xmm0
0x180004f76  movups  cs:xmmword_18000AEF0, xmm0
0x180004f7d  movups  cs:xmmword_18000AF00, xmm0
0x180004f84  movups  cs:xmmword_18000AF10, xmm0
0x180004f8b  movdqa  xmm0, cs:__xmm@07070707070707070707070707070707
0x180004f93  movups  cs:xmmword_18000AF20, xmm0
0x180004f9a  movq    cs:qword_18000AF30, xmm0
0x180004fa2  retn
```
