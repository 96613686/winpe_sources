# FreeEapAttributes

- ea: `0x180022000`
- end: `0x1800220fc`
- name: `FreeEapAttributes`
- size: `252`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800084a0`
- `0x18000b330`
- `0x18000ba30`
- `0x180010d40`
- `0x18001ec18`
- `0x180021530`

## callees

- `0x180005440`
- `0x1800214f0`
- `0x180022000`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x18002207f`
- `MobileNetworking!FreeMemory` at `0x1800220a1`
- `MobileNetworking!FreeMemory` at `0x1800220b9`
- `MobileNetworking!FreeMemory` at `0x18002207f`
- `MobileNetworking!FreeMemory` at `0x1800220a1`
- `MobileNetworking!FreeMemory` at `0x1800220b9`

## pseudocode

```c
__int64 __fastcall FreeEapAttributes(__int64 a1)
{
  __int64 result; // rax
  _UNKNOWN **v2; // rcx
  unsigned int v3; // edi
  unsigned int i; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = a1;
  result = a1;
  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x30u, (__int64)WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
    result = v5;
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( result )
  {
    v3 = *(_DWORD *)result;
    for ( i = 0; i < v3; ++i )
    {
      FreeMemory(*(_QWORD *)(result + 8) + 8LL + 16LL * i, "FreeEapAttributes", 910);
      result = v5;
    }
    FreeMemory(result + 8, "FreeEapAttributes", 912);
    result = FreeMemory(&v5, "FreeEapAttributes", 913);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x800) != 0 )
    return WPP_SF_D((__int64)v2[7], 0x31u, (__int64)WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180022000  mov     [rsp+arg_8], rbx
0x180022005  mov     [rsp+arg_10], rbp
0x18002200a  mov     [rsp+arg_0], rcx
0x18002200f  push    rdi
0x180022010  sub     rsp, 20h
0x180022014  mov     rax, rcx
0x180022017  mov     rcx, cs:WPP_GLOBAL_Control
0x18002201e  lea     rbp, WPP_GLOBAL_Control
0x180022025  cmp     rcx, rbp
0x180022028  jz      short loc_180022054
0x18002202a  test    dword ptr [rcx+44h], 800h
0x180022031  jz      short loc_180022054
0x180022033  mov     rcx, [rcx+38h]
0x180022037  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18002203e  mov     edx, 30h ; '0'
0x180022043  call    WPP_SF_
0x180022048  mov     rax, [rsp+28h+arg_0]
0x18002204d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022054  test    rax, rax
0x180022057  jz      short loc_1800220C6
0x180022059  mov     edi, [rax]
0x18002205b  xor     ebx, ebx
0x18002205d  test    edi, edi
0x18002205f  jz      short loc_180022090
0x180022061  mov     rax, [rax+8]
0x180022065  lea     rdx, aFreeeapattribu; "FreeEapAttributes"
0x18002206c  add     rax, 8
0x180022070  mov     ecx, ebx
0x180022072  shl     rcx, 4
0x180022076  mov     r8d, 38Eh
0x18002207c  add     rcx, rax
0x18002207f  call    cs:__imp_FreeMemory
0x180022085  mov     rax, [rsp+28h+arg_0]
0x18002208a  inc     ebx
0x18002208c  cmp     ebx, edi
0x18002208e  jb      short loc_180022061
0x180022090  lea     rcx, [rax+8]
0x180022094  mov     r8d, 390h
0x18002209a  lea     rdx, aFreeeapattribu; "FreeEapAttributes"
0x1800220a1  call    cs:__imp_FreeMemory
0x1800220a7  mov     r8d, 391h
0x1800220ad  lea     rdx, aFreeeapattribu; "FreeEapAttributes"
0x1800220b4  lea     rcx, [rsp+28h+arg_0]
0x1800220b9  call    cs:__imp_FreeMemory
0x1800220bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220c6  cmp     rcx, rbp
0x1800220c9  jz      short loc_1800220EC
0x1800220cb  test    dword ptr [rcx+44h], 800h
0x1800220d2  jz      short loc_1800220EC
0x1800220d4  mov     rcx, [rcx+38h]
0x1800220d8  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x1800220df  mov     edx, 31h ; '1'
0x1800220e4  xor     r9d, r9d
0x1800220e7  call    WPP_SF_D
0x1800220ec  mov     rbx, [rsp+28h+arg_8]
0x1800220f1  mov     rbp, [rsp+28h+arg_10]
0x1800220f6  add     rsp, 20h
0x1800220fa  pop     rdi
0x1800220fb  retn
```
