# TSMM_AddRectToRdpRegion(tagRECT *,_RDPGFX_REGION *)

- ea: `0x14005a2f0`
- end: `0x14005a3e6`
- name: `?TSMM_AddRectToRdpRegion@@YAJPEAUtagRECT@@PEAU_RDPGFX_REGION@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(RECT *lprcSrc2, struct _RDPGFX_REGION *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140032ee0`

## callees

- `0x140004b1c`
- `0x140011054`
- `0x14005a2f0`

## import_xrefs

- `USER32!CopyRect` at `0x14005a3aa`
- `USER32!CopyRect` at `0x14005a3aa`
- `USER32!UnionRect` at `0x14005a3be`
- `USER32!UnionRect` at `0x14005a3ce`
- `USER32!UnionRect` at `0x14005a3be`
- `USER32!UnionRect` at `0x14005a3ce`

## pseudocode

```c
__int64 __fastcall TSMM_AddRectToRdpRegion(RECT *lprcSrc2, struct _RDPGFX_REGION *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  unsigned int v7; // ebx

  if ( !lprcSrc2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 80;
    v6 = "prc";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_2b9efb4e65de3739c4887646ec83aab4_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6);
    return (unsigned int)-2147467261;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 81;
    v6 = "rgn";
    goto LABEL_6;
  }
  v7 = 0;
  if ( *(_DWORD *)a2 >= 0x40u )
  {
    UnionRect((LPRECT)((char *)a2 + 24), (const RECT *)((char *)a2 + 24), lprcSrc2);
  }
  else
  {
    CopyRect((LPRECT)((char *)a2 + 16 * *(unsigned int *)a2 + 24), lprcSrc2);
    ++*(_DWORD *)a2;
  }
  UnionRect((LPRECT)((char *)a2 + 8), (const RECT *)((char *)a2 + 8), lprcSrc2);
  return v7;
}

```

## disassembly

```asm
0x14005a2f0  mov     [rsp+arg_0], rbx
0x14005a2f5  mov     [rsp+arg_8], rsi
0x14005a2fa  push    rdi
0x14005a2fb  sub     rsp, 30h
0x14005a2ff  mov     rdi, rdx
0x14005a302  mov     rsi, rcx
0x14005a305  test    rcx, rcx
0x14005a308  jnz     short loc_14005A35E
0x14005a30a  mov     rax, cs:WPP_GLOBAL_Control
0x14005a311  lea     rcx, WPP_GLOBAL_Control
0x14005a318  cmp     rax, rcx
0x14005a31b  jz      short loc_14005A357
0x14005a31d  test    byte ptr [rax+1Ch], 8
0x14005a321  jz      short loc_14005A357
0x14005a323  cmp     byte ptr [rax+19h], 2
0x14005a327  jb      short loc_14005A357
0x14005a329  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a32e  lea     edx, [rsi+50h]
0x14005a331  lea     rcx, aPrc; "prc"
0x14005a338  mov     [rsp+38h+var_18], rcx
0x14005a33d  lea     r8, WPP_2b9efb4e65de3739c4887646ec83aab4_Traceguids
0x14005a344  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a34b  mov     r9d, eax
0x14005a34e  mov     rcx, [rcx+10h]
0x14005a352  call    WPP_SF_Ds
0x14005a357  mov     ebx, 80004003h
0x14005a35c  jmp     short loc_14005A3D4
0x14005a35e  test    rdi, rdi
0x14005a361  jnz     short loc_14005A393
0x14005a363  mov     rax, cs:WPP_GLOBAL_Control
0x14005a36a  lea     rcx, WPP_GLOBAL_Control
0x14005a371  cmp     rax, rcx
0x14005a374  jz      short loc_14005A357
0x14005a376  test    byte ptr [rax+1Ch], 8
0x14005a37a  jz      short loc_14005A357
0x14005a37c  cmp     byte ptr [rax+19h], 2
0x14005a380  jb      short loc_14005A357
0x14005a382  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a387  lea     edx, [rdi+51h]
0x14005a38a  lea     rcx, aRgn; "rgn"
0x14005a391  jmp     short loc_14005A338
0x14005a393  xor     ebx, ebx
0x14005a395  cmp     dword ptr [rdx], 40h ; '@'
0x14005a398  jnb     short loc_14005A3B4
0x14005a39a  mov     ecx, [rdx]
0x14005a39c  mov     rdx, rsi; lprcSrc
0x14005a39f  shl     rcx, 4
0x14005a3a3  add     rcx, 18h
0x14005a3a7  add     rcx, rdi; lprcDst
0x14005a3aa  call    cs:__imp_CopyRect
0x14005a3b0  inc     dword ptr [rdi]
0x14005a3b2  jmp     short loc_14005A3C4
0x14005a3b4  lea     rcx, [rdx+18h]; lprcDst
0x14005a3b8  mov     r8, rsi; lprcSrc2
0x14005a3bb  mov     rdx, rcx; lprcSrc1
0x14005a3be  call    cs:__imp_UnionRect
0x14005a3c4  lea     rcx, [rdi+8]; lprcDst
0x14005a3c8  mov     r8, rsi; lprcSrc2
0x14005a3cb  mov     rdx, rcx; lprcSrc1
0x14005a3ce  call    cs:__imp_UnionRect
0x14005a3d4  mov     rsi, [rsp+38h+arg_8]
0x14005a3d9  mov     eax, ebx
0x14005a3db  mov     rbx, [rsp+38h+arg_0]
0x14005a3e0  add     rsp, 30h
0x14005a3e4  pop     rdi
0x14005a3e5  retn
```
