# IsPathFAT(void *,wil::basic_zstring_view<wchar_t> const &,bool *)

- ea: `0x1800109d4`
- end: `0x180010a2a`
- name: `?IsPathFAT@@YAJPEAXAEBV?$basic_zstring_view@_W@wil@@PEA_N@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010358`

## callees

- `0x18000553c`
- `0x180010014`
- `0x1800109d4`

## string_xrefs

- `0x1800109fb`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
__int64 __fastcall IsPathFAT(__int64 a1, __int64 a2, bool *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v4 = DoesPathSupportFeature(a1, a2, a3, &v9);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a3 = v9 == 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF25,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return v5;
  }
}

```

## disassembly

```asm
0x1800109d4  mov     [rsp+arg_0], rbx
0x1800109d9  push    rdi; int
0x1800109da  sub     rsp, 20h
0x1800109de  lea     r9, [rsp+28h+arg_18]
0x1800109e3  mov     [rsp+28h+arg_18], 0
0x1800109e8  mov     rdi, r8
0x1800109eb  call    DoesPathSupportFeature
0x1800109f0  mov     ebx, eax
0x1800109f2  test    eax, eax
0x1800109f4  jns     short loc_180010A13
0x1800109f6  mov     rcx, [rsp+28h]; this
0x1800109fb  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x180010a02  mov     r9d, eax; char *
0x180010a05  mov     edx, 0F25h; void *
0x180010a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a0f  mov     eax, ebx
0x180010a11  jmp     short loc_180010A1F
0x180010a13  cmp     [rsp+28h+arg_18], 0
0x180010a18  setz    al
0x180010a1b  mov     [rdi], al
0x180010a1d  xor     eax, eax
0x180010a1f  mov     rbx, [rsp+28h+arg_0]
0x180010a24  add     rsp, 20h
0x180010a28  pop     rdi
0x180010a29  retn
```
