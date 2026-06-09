# MakePathFrom(STRU *,STRU *,ushort const *,ushort const *)

- ea: `0x180020940`
- end: `0x1800209e1`
- name: `?MakePathFrom@@YAJPEAVSTRU@@0PEBG1@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct STRU *, struct STRU *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c244`
- `0x18001d6d4`
- `0x18002620c`

## callees

- `0x180020940`

## import_xrefs

- `IisRTL!?QueryCCH@STRU@@QEBAKXZ` at `0x18002096e`
- `IisRTL!?QueryCCH@STRU@@QEBAKXZ` at `0x180020987`
- `IisRTL!?QueryCCH@STRU@@QEBAKXZ` at `0x18002096e`
- `IisRTL!?QueryCCH@STRU@@QEBAKXZ` at `0x180020987`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209a0`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209b0`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209c5`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209a0`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209b0`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800209c5`
- `IisRTL!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180020961`
- `IisRTL!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180020961`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002097b`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002097b`

## pseudocode

```c
int __fastcall MakePathFrom(struct STRU *a1, struct STRU *a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  int result; // eax
  unsigned __int16 *Str; // rbx

  if ( !a1 || !a2 || !a3 )
    return -2147024809;
  result = STRU::Copy(a1, a2);
  if ( result >= 0 )
  {
    if ( !STRU::QueryCCH(a1)
      || (Str = STRU::QueryStr(a1), Str[STRU::QueryCCH(a1) - 1] == 92)
      || (result = STRU::Append(a1, L"\\"), result >= 0) )
    {
      result = STRU::Append(a1, a3);
      if ( result >= 0 )
      {
        if ( !a4 )
          return 0;
        result = STRU::Append(a1, a4);
        if ( result >= 0 )
          return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020940  push    rbx
0x180020942  push    rbp
0x180020943  push    rsi
0x180020944  push    rdi
0x180020945  sub     rsp, 28h
0x180020949  mov     rsi, r9
0x18002094c  mov     rbp, r8
0x18002094f  mov     rdi, rcx
0x180020952  test    rcx, rcx
0x180020955  jz      short loc_1800209D3
0x180020957  test    rdx, rdx
0x18002095a  jz      short loc_1800209D3
0x18002095c  test    r8, r8
0x18002095f  jz      short loc_1800209D3
0x180020961  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x180020967  test    eax, eax
0x180020969  js      short loc_1800209D8
0x18002096b  mov     rcx, rdi
0x18002096e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180020974  test    eax, eax
0x180020976  jz      short loc_1800209AA
0x180020978  mov     rcx, rdi
0x18002097b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180020981  mov     rcx, rdi
0x180020984  mov     rbx, rax
0x180020987  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002098d  dec     eax
0x18002098f  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180020994  jz      short loc_1800209AA
0x180020996  lea     rdx, asc_180033DA8; "\\"
0x18002099d  mov     rcx, rdi
0x1800209a0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800209a6  test    eax, eax
0x1800209a8  js      short loc_1800209D8
0x1800209aa  mov     rdx, rbp
0x1800209ad  mov     rcx, rdi
0x1800209b0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800209b6  test    eax, eax
0x1800209b8  js      short loc_1800209D8
0x1800209ba  test    rsi, rsi
0x1800209bd  jz      short loc_1800209CF
0x1800209bf  mov     rdx, rsi
0x1800209c2  mov     rcx, rdi
0x1800209c5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800209cb  test    eax, eax
0x1800209cd  js      short loc_1800209D8
0x1800209cf  xor     eax, eax
0x1800209d1  jmp     short loc_1800209D8
0x1800209d3  mov     eax, 80070057h
0x1800209d8  add     rsp, 28h
0x1800209dc  pop     rdi
0x1800209dd  pop     rsi
0x1800209de  pop     rbp
0x1800209df  pop     rbx
0x1800209e0  retn
```
