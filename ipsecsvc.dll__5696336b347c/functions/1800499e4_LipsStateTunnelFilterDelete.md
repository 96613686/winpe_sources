# LipsStateTunnelFilterDelete

- ea: `0x1800499e4`
- end: `0x180049b1f`
- name: `LipsStateTunnelFilterDelete`
- size: `315`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800451b8`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x1800452d0`
- `0x180048478`
- `0x180048570`
- `0x1800486b0`
- `0x1800499e4`
- `0x180049d30`

## string_xrefs

- `0x180049ae7`: `LipsStateTunnelFilterDelete`
- `0x180049b03`: `LipsStateTunnelFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsStateTunnelFilterDelete(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  v2 = 0;
  if ( !a1 || !a2 )
    return v2;
  v5 = LipsBfeTransactionBegin();
  v2 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v5);
    goto LABEL_17;
  }
  v6 = LipsStateTunnelFilterEnum(a1, 0, a2, LipsStateTunnelFilterDeleteCb);
  v2 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_16;
    v8 = 17;
    goto LABEL_15;
  }
  v6 = LipsBfeTransactionCommit();
  v2 = v6;
  if ( !v6 )
    goto LABEL_17;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = 18;
LABEL_15:
    WPP_SF_d(v7[2], v8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v6);
  }
LABEL_16:
  LipsBfeTransactionAbort();
LABEL_17:
  LipsStateTunnelFilterEnum(a1, 0, a2, LipsStateTunnelFilterDestroyLegacyCb);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_4259805821ae3eb6062dce0997567f8e_Traceguids,
        (unsigned int)"LipsStateTunnelFilterDelete",
        v2);
    return (unsigned int)LipsReportError(v2, (int)"LipsStateTunnelFilterDelete");
  }
  return v2;
}

```

## disassembly

```asm
0x1800499e4  push    rbx
0x1800499e6  push    rsi
0x1800499e7  push    rdi
0x1800499e8  push    r14
0x1800499ea  sub     rsp, 38h
0x1800499ee  xor     ebx, ebx
0x1800499f0  mov     edi, edx
0x1800499f2  mov     rsi, rcx
0x1800499f5  test    rcx, rcx
0x1800499f8  jz      loc_180049B13
0x1800499fe  test    edx, edx
0x180049a00  jz      loc_180049B13
0x180049a06  call    LipsBfeTransactionBegin
0x180049a0b  lea     r14, WPP_GLOBAL_Control
0x180049a12  mov     ebx, eax
0x180049a14  test    eax, eax
0x180049a16  jz      short loc_180049A4C
0x180049a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a1f  cmp     rcx, r14
0x180049a22  jz      loc_180049AB9
0x180049a28  test    byte ptr [rcx+1Ch], 10h
0x180049a2c  jz      loc_180049AB9
0x180049a32  mov     rcx, [rcx+10h]
0x180049a36  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049a3d  mov     edx, 10h
0x180049a42  mov     r9d, eax
0x180049a45  call    WPP_SF_d
0x180049a4a  jmp     short loc_180049AB9
0x180049a4c  lea     r9, LipsStateTunnelFilterDeleteCb
0x180049a53  mov     r8d, edi
0x180049a56  xor     edx, edx
0x180049a58  mov     rcx, rsi
0x180049a5b  call    LipsStateTunnelFilterEnum
0x180049a60  mov     ebx, eax
0x180049a62  test    eax, eax
0x180049a64  jz      short loc_180049A7F
0x180049a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a6d  cmp     rcx, r14
0x180049a70  jz      short loc_180049AB4
0x180049a72  test    byte ptr [rcx+1Ch], 10h
0x180049a76  jz      short loc_180049AB4
0x180049a78  mov     edx, 11h
0x180049a7d  jmp     short loc_180049AA1
0x180049a7f  call    LipsBfeTransactionCommit
0x180049a84  mov     ebx, eax
0x180049a86  test    eax, eax
0x180049a88  jz      short loc_180049AB9
0x180049a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a91  cmp     rcx, r14
0x180049a94  jz      short loc_180049AB4
0x180049a96  test    byte ptr [rcx+1Ch], 10h
0x180049a9a  jz      short loc_180049AB4
0x180049a9c  mov     edx, 12h
0x180049aa1  mov     rcx, [rcx+10h]
0x180049aa5  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049aac  mov     r9d, eax
0x180049aaf  call    WPP_SF_d
0x180049ab4  call    LipsBfeTransactionAbort
0x180049ab9  lea     r9, LipsStateTunnelFilterDestroyLegacyCb
0x180049ac0  mov     r8d, edi
0x180049ac3  xor     edx, edx
0x180049ac5  mov     rcx, rsi
0x180049ac8  call    LipsStateTunnelFilterEnum
0x180049acd  test    ebx, ebx
0x180049acf  jz      short loc_180049B13
0x180049ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ad8  cmp     rcx, r14
0x180049adb  jz      short loc_180049B03
0x180049add  test    byte ptr [rcx+1Ch], 10h
0x180049ae1  jz      short loc_180049B03
0x180049ae3  mov     rcx, [rcx+10h]
0x180049ae7  lea     r9, aLipsstatetunne_2; "LipsStateTunnelFilterDelete"
0x180049aee  mov     edx, 13h
0x180049af3  mov     [rsp+58h+var_38], ebx
0x180049af7  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049afe  call    WPP_SF_sD
0x180049b03  lea     rdx, aLipsstatetunne_2; "LipsStateTunnelFilterDelete"
0x180049b0a  mov     ecx, ebx
0x180049b0c  call    LipsReportError
0x180049b11  mov     ebx, eax
0x180049b13  mov     eax, ebx
0x180049b15  add     rsp, 38h
0x180049b19  pop     r14
0x180049b1b  pop     rdi
0x180049b1c  pop     rsi
0x180049b1d  pop     rbx
0x180049b1e  retn
```
