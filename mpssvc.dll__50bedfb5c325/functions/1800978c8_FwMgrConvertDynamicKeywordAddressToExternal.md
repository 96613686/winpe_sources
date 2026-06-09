# FwMgrConvertDynamicKeywordAddressToExternal

- ea: `0x1800978c8`
- end: `0x180097b96`
- name: `FwMgrConvertDynamicKeywordAddressToExternal`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f1cc`

## callees

- `0x18000a66c`
- `0x18000a710`
- `0x1800729c0`
- `0x1800978c8`

## import_xrefs

- `fwbase!IsAddressesEmpty` at `0x180097a46`
- `fwbase!IsAddressesEmpty` at `0x180097a46`
- `fwbase!FwStringCopy` at `0x1800979ed`
- `fwbase!FwStringCopy` at `0x1800979ed`
- `fwbase!FwAlloc` at `0x18009797b`
- `fwbase!FwAlloc` at `0x180097a6f`
- `fwbase!FwAlloc` at `0x18009797b`
- `fwbase!FwAlloc` at `0x180097a6f`
- `fwbase!FwFree` at `0x180097b56`
- `fwbase!FwFree` at `0x180097b65`
- `fwbase!FwFree` at `0x180097b56`
- `fwbase!FwFree` at `0x180097b65`
- `FWPolicyIOMgr!OpenPortOrAuthAppAddrToStringInt3` at `0x180097ae3`
- `FWPolicyIOMgr!OpenPortOrAuthAppAddrToStringInt3` at `0x180097ae3`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressDataBySchemaVersion` at `0x180097b3a`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressDataBySchemaVersion` at `0x180097b3a`
- `FWPolicyIOMgr!CalculateOpenPortOrAuthAppAddrStringSize` at `0x180097a5d`
- `FWPolicyIOMgr!CalculateOpenPortOrAuthAppAddrStringSize` at `0x180097a5d`

## string_xrefs

- `0x180097a25`: `FwStringCopy:wszKeyword`
- `0x180097b13`: `OpenPortOrAuthAppAddrToStringInt3`

## pseudocode

```c
__int64 __fastcall FwMgrConvertDynamicKeywordAddressToExternal(__int64 a1, __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  v3 = 0;
  v19 = 0;
  if ( !a2 )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_30;
    v9 = 31;
    goto LABEL_5;
  }
  if ( !a1 )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_30;
    v9 = 32;
    goto LABEL_5;
  }
  *a2 = 0;
  v10 = FwAlloc(56);
  v2 = v10;
  if ( !v10 )
  {
    v6 = 2147942414LL;
    v7 = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_30;
    v9 = 33;
    goto LABEL_5;
  }
  v7 = 0;
  *(_WORD *)(v10 + 48) = *(_WORD *)(a1 + 8);
  *(_DWORD *)(v10 + 52) = *(_DWORD *)(a1 + 120);
  *(_OWORD *)v10 = *(_OWORD *)(a1 + 12);
  *(_DWORD *)(v10 + 24) = *(_DWORD *)(a1 + 40);
  v11 = *(_QWORD *)(a1 + 32);
  if ( v11 )
  {
    v7 = FwStringCopy(v11, &v19);
    if ( v7 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_30;
      v13 = 34;
      v14 = "FwStringCopy:wszKeyword";
      goto LABEL_29;
    }
    *(_QWORD *)(v2 + 16) = v19;
    v19 = 0;
  }
  v15 = a1 + 48;
  if ( (unsigned int)IsAddressesEmpty(v15) )
  {
LABEL_32:
    *a2 = v2;
    v3 = 0;
    goto LABEL_33;
  }
  v16 = (unsigned int)CalculateOpenPortOrAuthAppAddrStringSize(v15);
  v17 = FwAlloc(2 * v16);
  v3 = v17;
  if ( v17 )
  {
    v7 = OpenPortOrAuthAppAddrToStringInt3(v15, v17, v16, 0, 545, 0, 0, 0);
    if ( v7 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_30;
      v13 = 36;
      v14 = "OpenPortOrAuthAppAddrToStringInt3";
LABEL_29:
      WPP_SF_Ds(
        *(_QWORD *)(v12 + 16),
        v13,
        (unsigned int)WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids,
        v7,
        (__int64)v14);
      goto LABEL_30;
    }
    *(_QWORD *)(v2 + 32) = v3;
    goto LABEL_32;
  }
  v6 = 2147942414LL;
  v7 = -2147024882;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    goto LABEL_30;
  v9 = 35;
LABEL_5:
  WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids, v6);
LABEL_30:
  FwFreeDynamicKeywordAddressDataBySchemaVersion(v2, 545);
LABEL_33:
  FwFree(v19);
  FwFree(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800978c8  mov     [rsp+arg_10], rbx
0x1800978cd  mov     [rsp+arg_18], rbp
0x1800978d2  push    rsi
0x1800978d3  push    rdi
0x1800978d4  push    r14
0x1800978d6  sub     rsp, 50h
0x1800978da  mov     rax, cs:__security_cookie
0x1800978e1  xor     rax, rsp
0x1800978e4  mov     [rsp+68h+var_20], rax
0x1800978e9  xor     edi, edi
0x1800978eb  xor     ebp, ebp
0x1800978ed  mov     [rsp+68h+var_28], rdi
0x1800978f2  mov     r14, rdx
0x1800978f5  mov     rsi, rcx
0x1800978f8  test    rdx, rdx
0x1800978fb  jnz     short loc_18009793F
0x1800978fd  mov     r9d, 80070057h
0x180097903  mov     ebx, r9d
0x180097906  mov     rcx, cs:WPP_GLOBAL_Control
0x18009790d  lea     rax, WPP_GLOBAL_Control
0x180097914  cmp     rcx, rax
0x180097917  jz      loc_180097B32
0x18009791d  test    byte ptr [rcx+1Ch], 1
0x180097921  jz      loc_180097B32
0x180097927  lea     edx, [rdi+1Fh]
0x18009792a  mov     rcx, [rcx+10h]
0x18009792e  lea     r8, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids
0x180097935  call    WPP_SF_d
0x18009793a  jmp     loc_180097B32
0x18009793f  test    rsi, rsi
0x180097942  jnz     short loc_180097973
0x180097944  mov     r9d, 80070057h
0x18009794a  mov     ebx, r9d
0x18009794d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097954  lea     rax, WPP_GLOBAL_Control
0x18009795b  cmp     rcx, rax
0x18009795e  jz      loc_180097B32
0x180097964  test    byte ptr [rcx+1Ch], 1
0x180097968  jz      loc_180097B32
0x18009796e  lea     edx, [rsi+20h]
0x180097971  jmp     short loc_18009792A
0x180097973  mov     ecx, 38h ; '8'
0x180097978  mov     [rdx], rdi
0x18009797b  call    cs:__imp_FwAlloc
0x180097982  nop     dword ptr [rax+rax+00h]
0x180097987  mov     rdi, rax
0x18009798a  test    rax, rax
0x18009798d  jnz     short loc_1800979C1
0x18009798f  mov     r9d, 8007000Eh
0x180097995  mov     ebx, r9d
0x180097998  mov     rcx, cs:WPP_GLOBAL_Control
0x18009799f  lea     rax, WPP_GLOBAL_Control
0x1800979a6  cmp     rcx, rax
0x1800979a9  jz      loc_180097B32
0x1800979af  test    byte ptr [rcx+1Ch], 1
0x1800979b3  jz      loc_180097B32
0x1800979b9  lea     edx, [rdi+21h]
0x1800979bc  jmp     loc_18009792A
0x1800979c1  movzx   eax, word ptr [rsi+8]
0x1800979c5  xor     ebx, ebx
0x1800979c7  mov     [rdi+30h], ax
0x1800979cb  mov     eax, [rsi+78h]
0x1800979ce  mov     [rdi+34h], eax
0x1800979d1  movups  xmm0, xmmword ptr [rsi+0Ch]
0x1800979d5  movdqu  xmmword ptr [rdi], xmm0
0x1800979d9  mov     eax, [rsi+28h]
0x1800979dc  mov     [rdi+18h], eax
0x1800979df  mov     rcx, [rsi+20h]
0x1800979e3  test    rcx, rcx
0x1800979e6  jz      short loc_180097A3F
0x1800979e8  lea     rdx, [rsp+68h+var_28]
0x1800979ed  call    cs:__imp_FwStringCopy
0x1800979f4  nop     dword ptr [rax+rax+00h]
0x1800979f9  mov     ebx, eax
0x1800979fb  test    eax, eax
0x1800979fd  jns     short loc_180097A31
0x1800979ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180097a06  lea     rax, WPP_GLOBAL_Control
0x180097a0d  cmp     rcx, rax
0x180097a10  jz      loc_180097B32
0x180097a16  test    byte ptr [rcx+1Ch], 1
0x180097a1a  jz      loc_180097B32
0x180097a20  mov     edx, 22h ; '"'
0x180097a25  lea     rax, aFwstringcopyWs; "FwStringCopy:wszKeyword"
0x180097a2c  jmp     loc_180097B1A
0x180097a31  mov     rax, [rsp+68h+var_28]
0x180097a36  mov     [rdi+10h], rax
0x180097a3a  mov     [rsp+68h+var_28], rbp
0x180097a3f  add     rsi, 30h ; '0'
0x180097a43  mov     rcx, rsi
0x180097a46  call    cs:__imp_IsAddressesEmpty
0x180097a4d  nop     dword ptr [rax+rax+00h]
0x180097a52  test    eax, eax
0x180097a54  jnz     loc_180097B4C
0x180097a5a  mov     rcx, rsi
0x180097a5d  call    cs:__imp_CalculateOpenPortOrAuthAppAddrStringSize
0x180097a64  nop     dword ptr [rax+rax+00h]
0x180097a69  mov     ebx, eax
0x180097a6b  lea     rcx, [rbx+rbx]
0x180097a6f  call    cs:__imp_FwAlloc
0x180097a76  nop     dword ptr [rax+rax+00h]
0x180097a7b  mov     rbp, rax
0x180097a7e  test    rax, rax
0x180097a81  jnz     short loc_180097AB5
0x180097a83  mov     r9d, 8007000Eh
0x180097a89  mov     ebx, r9d
0x180097a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180097a93  lea     rax, WPP_GLOBAL_Control
0x180097a9a  cmp     rcx, rax
0x180097a9d  jz      loc_180097B32
0x180097aa3  test    byte ptr [rcx+1Ch], 1
0x180097aa7  jz      loc_180097B32
0x180097aad  lea     edx, [rbp+23h]
0x180097ab0  jmp     loc_18009792A
0x180097ab5  mov     [rsp+68h+var_30], 0
0x180097abe  xor     r9d, r9d
0x180097ac1  mov     [rsp+68h+var_38], 0
0x180097aca  mov     r8, rbx
0x180097acd  mov     [rsp+68h+var_40], 0
0x180097ad5  mov     rdx, rbp
0x180097ad8  mov     rcx, rsi
0x180097adb  mov     dword ptr [rsp+68h+var_48], 221h
0x180097ae3  call    cs:__imp_OpenPortOrAuthAppAddrToStringInt3
0x180097aea  nop     dword ptr [rax+rax+00h]
0x180097aef  mov     ebx, eax
0x180097af1  test    eax, eax
0x180097af3  jns     short loc_180097B48
0x180097af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180097afc  lea     rax, WPP_GLOBAL_Control
0x180097b03  cmp     rcx, rax
0x180097b06  jz      short loc_180097B32
0x180097b08  test    byte ptr [rcx+1Ch], 1
0x180097b0c  jz      short loc_180097B32
0x180097b0e  mov     edx, 24h ; '$'
0x180097b13  lea     rax, aOpenportorauth_0; "OpenPortOrAuthAppAddrToStringInt3"
0x180097b1a  mov     rcx, [rcx+10h]
0x180097b1e  lea     r8, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids
0x180097b25  mov     r9d, ebx
0x180097b28  mov     [rsp+68h+var_48], rax
0x180097b2d  call    WPP_SF_Ds
0x180097b32  mov     edx, 221h
0x180097b37  mov     rcx, rdi
0x180097b3a  call    cs:__imp_FwFreeDynamicKeywordAddressDataBySchemaVersion
0x180097b41  nop     dword ptr [rax+rax+00h]
0x180097b46  jmp     short loc_180097B51
0x180097b48  mov     [rdi+20h], rbp
0x180097b4c  mov     [r14], rdi
0x180097b4f  xor     ebp, ebp
0x180097b51  mov     rcx, [rsp+68h+var_28]
0x180097b56  call    cs:__imp_FwFree
0x180097b5d  nop     dword ptr [rax+rax+00h]
0x180097b62  mov     rcx, rbp
0x180097b65  call    cs:__imp_FwFree
0x180097b6c  nop     dword ptr [rax+rax+00h]
0x180097b71  mov     eax, ebx
0x180097b73  mov     rcx, [rsp+68h+var_20]
0x180097b78  xor     rcx, rsp; StackCookie
0x180097b7b  call    __security_check_cookie
0x180097b80  lea     r11, [rsp+68h+var_18]
0x180097b85  mov     rbx, [r11+30h]
0x180097b89  mov     rbp, [r11+38h]
0x180097b8d  mov     rsp, r11
0x180097b90  pop     r14
0x180097b92  pop     rdi
0x180097b93  pop     rsi
0x180097b94  retn
```
