# CmsGetNetworkId

- ea: `0x1800081c0`
- end: `0x18000820d`
- name: `CmsGetNetworkId`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800066e4`
- `0x1800081c0`

## string_xrefs

- `0x1800081cd`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsGetNetworkId(int a1, _DWORD *a2)
{
  __int64 result; // rax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x80070057LL,
      v3);
    return 2147942487LL;
  }
  else
  {
    *a2 = -1064519752;
    result = 0;
    a2[1] = 1083087676;
    a2[2] = 375271566;
    a2[3] = 1152691875;
  }
  return result;
}

```

## disassembly

```asm
0x1800081c0  sub     rsp, 28h
0x1800081c4  test    ecx, ecx
0x1800081c6  jz      short loc_1800081EB
0x1800081c8  mov     rcx, [rsp+28h]; this
0x1800081cd  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800081d4  mov     r9d, 80070057h; char *
0x1800081da  mov     edx, 431h; void *
0x1800081df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081e4  mov     eax, 80070057h
0x1800081e9  jmp     short loc_180008208
0x1800081eb  mov     dword ptr [rdx], 0C08CB7B8h
0x1800081f1  xor     eax, eax
0x1800081f3  mov     dword ptr [rdx+4], 408E9B3Ch
0x1800081fa  mov     dword ptr [rdx+8], 165E308Eh
0x180008201  mov     dword ptr [rdx+0Ch], 44B4AEA3h
0x180008208  add     rsp, 28h
0x18000820c  retn
```
