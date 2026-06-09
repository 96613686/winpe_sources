# CmsOpenContainerByMemoryHostingProcess

- ea: `0x1800086b0`
- end: `0x180008726`
- name: `CmsOpenContainerByMemoryHostingProcess`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800066e4`
- `0x1800086b0`
- `0x180009a94`

## string_xrefs

- `0x180008706`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenContainerByMemoryHostingProcess(__int64 a1, int a2, int a3, _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  char v9; // [rsp+38h] [rbp-20h]
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = a1;
  v9 = 1;
  v10 = 0;
  v4 = OpenContainer((__int128 **)&v10, (__int64)&v8, a2, a3, a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x137,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x1800086b0  mov     r11, rsp
0x1800086b3  push    rbx
0x1800086b4  sub     rsp, 50h
0x1800086b8  mov     [r11-28h], rcx
0x1800086bc  xorps   xmm0, xmm0
0x1800086bf  mov     eax, [rsp+58h+var_1F]
0x1800086c3  lea     rcx, [r11-18h]
0x1800086c7  mov     [rsp+58h+var_1F], eax
0x1800086cb  movzx   eax, [rsp+58h+var_1B]
0x1800086d0  mov     [r11-38h], r9
0x1800086d4  mov     r9d, r8d
0x1800086d7  mov     [rsp+58h+var_1B], ax
0x1800086dc  mov     r8d, edx
0x1800086df  mov     al, [rsp+58h+var_19]
0x1800086e3  lea     rdx, [r11-28h]
0x1800086e7  mov     [rsp+58h+var_19], al
0x1800086eb  mov     [rsp+58h+var_20], 1
0x1800086f0  movdqa  [rsp+58h+var_18], xmm0
0x1800086f6  call    OpenContainer
0x1800086fb  mov     ebx, eax
0x1800086fd  test    eax, eax
0x1800086ff  jns     short loc_18000871E
0x180008701  mov     rcx, [rsp+58h]; this
0x180008706  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000870d  mov     r9d, eax; char *
0x180008710  mov     edx, 137h; void *
0x180008715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000871a  mov     eax, ebx
0x18000871c  jmp     short loc_180008720
0x18000871e  xor     eax, eax
0x180008720  add     rsp, 50h
0x180008724  pop     rbx
0x180008725  retn
```
