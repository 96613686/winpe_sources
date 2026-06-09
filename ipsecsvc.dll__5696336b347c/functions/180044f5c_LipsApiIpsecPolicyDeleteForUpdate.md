# LipsApiIpsecPolicyDeleteForUpdate

- ea: `0x180044f5c`
- end: `0x18004505c`
- name: `LipsApiIpsecPolicyDeleteForUpdate`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180019424`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044f5c`
- `0x1800452d0`
- `0x18004606c`
- `0x180047094`

## string_xrefs

- `0x180044f8f`: `LipsApiIpsecPolicyDeleteForUpdate`
- `0x180045035`: `LipsApiIpsecPolicyDeleteForUpdate`

## pseudocode

```c
__int64 __fastcall LipsApiIpsecPolicyDeleteForUpdate(__int64 a1, __int64 a2, _OWORD *a3)
{
  LPVOID v3; // rsi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _OWORD v11[3]; // [rsp+30h] [rbp-38h] BYREF

  v3 = gpIniTxSFilter;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIpsecPolicyDeleteForUpdate");
  v11[0] = *(_OWORD *)*(_QWORD *)(a1 + 56);
  *a3 = v11[0];
  v6 = LipsDeleteQMIpsecFiltersForPolicy(v3, v11);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_13;
    v9 = 59;
    goto LABEL_12;
  }
  v6 = LipsStateIpsecPolicyDelete(a1);
  v7 = v6;
  if ( !v6 )
    return v7;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v9 = 60;
LABEL_12:
    WPP_SF_d(v8[2], v9, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v6);
    v8 = WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    WPP_SF_sD(
      v8[2],
      61,
      (unsigned int)WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      (unsigned int)"LipsApiIpsecPolicyDeleteForUpdate",
      v7);
  return v7;
}

```

## disassembly

```asm
0x180044f5c  push    rbx
0x180044f5e  push    rbp
0x180044f5f  push    rsi
0x180044f60  push    rdi
0x180044f61  sub     rsp, 48h
0x180044f65  mov     rsi, cs:gpIniTxSFilter
0x180044f6c  mov     rbx, r8
0x180044f6f  mov     rdi, rcx
0x180044f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f79  lea     rbp, WPP_GLOBAL_Control
0x180044f80  cmp     rcx, rbp
0x180044f83  jz      short loc_180044FA7
0x180044f85  test    byte ptr [rcx+1Ch], 4
0x180044f89  jz      short loc_180044FA7
0x180044f8b  mov     rcx, [rcx+10h]
0x180044f8f  lea     r9, aLipsapiipsecpo; "LipsApiIpsecPolicyDeleteForUpdate"
0x180044f96  mov     edx, 39h ; '9'
0x180044f9b  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044fa2  call    WPP_SF_s
0x180044fa7  mov     rax, [rdi+38h]
0x180044fab  lea     rdx, [rsp+68h+var_38]
0x180044fb0  mov     rcx, rsi
0x180044fb3  movups  xmm0, xmmword ptr [rax]
0x180044fb6  movdqu  [rsp+68h+var_38], xmm0
0x180044fbc  movdqu  xmmword ptr [rbx], xmm0
0x180044fc0  call    LipsDeleteQMIpsecFiltersForPolicy
0x180044fc5  mov     ebx, eax
0x180044fc7  mov     sil, 10h
0x180044fca  test    eax, eax
0x180044fcc  jz      short loc_180044FE7
0x180044fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180044fd5  cmp     rcx, rbp
0x180044fd8  jz      short loc_180045051
0x180044fda  test    [rcx+1Ch], sil
0x180044fde  jz      short loc_180045026
0x180044fe0  mov     edx, 3Bh ; ';'
0x180044fe5  jmp     short loc_18004500C
0x180044fe7  mov     rcx, rdi
0x180044fea  call    LipsStateIpsecPolicyDelete
0x180044fef  mov     ebx, eax
0x180044ff1  test    eax, eax
0x180044ff3  jz      short loc_180045051
0x180044ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ffc  cmp     rcx, rbp
0x180044fff  jz      short loc_180045051
0x180045001  test    [rcx+1Ch], sil
0x180045005  jz      short loc_180045026
0x180045007  mov     edx, 3Ch ; '<'
0x18004500c  mov     rcx, [rcx+10h]
0x180045010  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180045017  mov     r9d, eax
0x18004501a  call    WPP_SF_d
0x18004501f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045026  cmp     rcx, rbp
0x180045029  jz      short loc_180045051
0x18004502b  test    [rcx+1Ch], sil
0x18004502f  jz      short loc_180045051
0x180045031  mov     rcx, [rcx+10h]
0x180045035  lea     r9, aLipsapiipsecpo; "LipsApiIpsecPolicyDeleteForUpdate"
0x18004503c  mov     edx, 3Dh ; '='
0x180045041  mov     [rsp+68h+var_48], ebx
0x180045045  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x18004504c  call    WPP_SF_sD
0x180045051  mov     eax, ebx
0x180045053  add     rsp, 48h
0x180045057  pop     rdi
0x180045058  pop     rsi
0x180045059  pop     rbp
0x18004505a  pop     rbx
0x18004505b  retn
```
