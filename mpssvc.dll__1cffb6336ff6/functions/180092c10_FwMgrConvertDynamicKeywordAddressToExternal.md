# FwMgrConvertDynamicKeywordAddressToExternal

- ea: `0x180092c10`
- end: `0x180092ea3`
- name: `FwMgrConvertDynamicKeywordAddressToExternal`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a17c`

## callees

- `0x18000ae9c`
- `0x18000af3c`
- `0x18006f520`
- `0x180092c10`

## import_xrefs

- `fwbase!IsAddressesEmpty` at `0x180092d82`
- `fwbase!IsAddressesEmpty` at `0x180092d82`
- `fwbase!FwStringCopy` at `0x180092d2f`
- `fwbase!FwStringCopy` at `0x180092d2f`
- `fwbase!FwAlloc` at `0x180092cc3`
- `fwbase!FwAlloc` at `0x180092d9f`
- `fwbase!FwAlloc` at `0x180092cc3`
- `fwbase!FwAlloc` at `0x180092d9f`
- `fwbase!FwFree` at `0x180092e70`
- `fwbase!FwFree` at `0x180092e79`
- `fwbase!FwFree` at `0x180092e70`
- `fwbase!FwFree` at `0x180092e79`
- `FWPolicyIOMgr!OpenPortOrAuthAppAddrToStringInt3` at `0x180092e09`
- `FWPolicyIOMgr!OpenPortOrAuthAppAddrToStringInt3` at `0x180092e09`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressDataBySchemaVersion` at `0x180092e5a`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressDataBySchemaVersion` at `0x180092e5a`
- `FWPolicyIOMgr!CalculateOpenPortOrAuthAppAddrStringSize` at `0x180092d93`
- `FWPolicyIOMgr!CalculateOpenPortOrAuthAppAddrStringSize` at `0x180092d93`

## string_xrefs

- `0x180092d61`: `FwStringCopy:wszKeyword`
- `0x180092e33`: `OpenPortOrAuthAppAddrToStringInt3`

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
        (unsigned int)WPP_69b4ffd36c543342139ff27524f05d89_Traceguids,
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
  WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids, v6);
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
0x180092c10  mov     [rsp+arg_10], rbx
0x180092c15  mov     [rsp+arg_18], rbp
0x180092c1a  push    rsi
0x180092c1b  push    rdi
0x180092c1c  push    r14
0x180092c1e  sub     rsp, 50h
0x180092c22  mov     rax, cs:__security_cookie
0x180092c29  xor     rax, rsp
0x180092c2c  mov     [rsp+68h+var_20], rax
0x180092c31  xor     edi, edi
0x180092c33  xor     ebp, ebp
0x180092c35  mov     [rsp+68h+var_28], rdi
0x180092c3a  mov     r14, rdx
0x180092c3d  mov     rsi, rcx
0x180092c40  test    rdx, rdx
0x180092c43  jnz     short loc_180092C87
0x180092c45  mov     r9d, 80070057h
0x180092c4b  mov     ebx, r9d
0x180092c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092c55  lea     rax, WPP_GLOBAL_Control
0x180092c5c  cmp     rcx, rax
0x180092c5f  jz      loc_180092E52
0x180092c65  test    byte ptr [rcx+1Ch], 1
0x180092c69  jz      loc_180092E52
0x180092c6f  lea     edx, [rdi+1Fh]
0x180092c72  mov     rcx, [rcx+10h]
0x180092c76  lea     r8, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids
0x180092c7d  call    WPP_SF_d
0x180092c82  jmp     loc_180092E52
0x180092c87  test    rsi, rsi
0x180092c8a  jnz     short loc_180092CBB
0x180092c8c  mov     r9d, 80070057h
0x180092c92  mov     ebx, r9d
0x180092c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180092c9c  lea     rax, WPP_GLOBAL_Control
0x180092ca3  cmp     rcx, rax
0x180092ca6  jz      loc_180092E52
0x180092cac  test    byte ptr [rcx+1Ch], 1
0x180092cb0  jz      loc_180092E52
0x180092cb6  lea     edx, [rsi+20h]
0x180092cb9  jmp     short loc_180092C72
0x180092cbb  mov     ecx, 38h ; '8'
0x180092cc0  mov     [rdx], rdi
0x180092cc3  call    cs:__imp_FwAlloc
0x180092cc9  mov     rdi, rax
0x180092ccc  test    rax, rax
0x180092ccf  jnz     short loc_180092D03
0x180092cd1  mov     r9d, 8007000Eh
0x180092cd7  mov     ebx, r9d
0x180092cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180092ce1  lea     rax, WPP_GLOBAL_Control
0x180092ce8  cmp     rcx, rax
0x180092ceb  jz      loc_180092E52
0x180092cf1  test    byte ptr [rcx+1Ch], 1
0x180092cf5  jz      loc_180092E52
0x180092cfb  lea     edx, [rdi+21h]
0x180092cfe  jmp     loc_180092C72
0x180092d03  movzx   eax, word ptr [rsi+8]
0x180092d07  xor     ebx, ebx
0x180092d09  mov     [rdi+30h], ax
0x180092d0d  mov     eax, [rsi+78h]
0x180092d10  mov     [rdi+34h], eax
0x180092d13  movups  xmm0, xmmword ptr [rsi+0Ch]
0x180092d17  movdqu  xmmword ptr [rdi], xmm0
0x180092d1b  mov     eax, [rsi+28h]
0x180092d1e  mov     [rdi+18h], eax
0x180092d21  mov     rcx, [rsi+20h]
0x180092d25  test    rcx, rcx
0x180092d28  jz      short loc_180092D7B
0x180092d2a  lea     rdx, [rsp+68h+var_28]
0x180092d2f  call    cs:__imp_FwStringCopy
0x180092d35  mov     ebx, eax
0x180092d37  test    eax, eax
0x180092d39  jns     short loc_180092D6D
0x180092d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092d42  lea     rax, WPP_GLOBAL_Control
0x180092d49  cmp     rcx, rax
0x180092d4c  jz      loc_180092E52
0x180092d52  test    byte ptr [rcx+1Ch], 1
0x180092d56  jz      loc_180092E52
0x180092d5c  mov     edx, 22h ; '"'
0x180092d61  lea     rax, aFwstringcopyWs; "FwStringCopy:wszKeyword"
0x180092d68  jmp     loc_180092E3A
0x180092d6d  mov     rax, [rsp+68h+var_28]
0x180092d72  mov     [rdi+10h], rax
0x180092d76  mov     [rsp+68h+var_28], rbp
0x180092d7b  add     rsi, 30h ; '0'
0x180092d7f  mov     rcx, rsi
0x180092d82  call    cs:__imp_IsAddressesEmpty
0x180092d88  test    eax, eax
0x180092d8a  jnz     loc_180092E66
0x180092d90  mov     rcx, rsi
0x180092d93  call    cs:__imp_CalculateOpenPortOrAuthAppAddrStringSize
0x180092d99  mov     ebx, eax
0x180092d9b  lea     rcx, [rbx+rbx]
0x180092d9f  call    cs:__imp_FwAlloc
0x180092da5  mov     rbp, rax
0x180092da8  test    rax, rax
0x180092dab  jnz     short loc_180092DDB
0x180092dad  mov     r9d, 8007000Eh
0x180092db3  mov     ebx, r9d
0x180092db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180092dbd  lea     rax, WPP_GLOBAL_Control
0x180092dc4  cmp     rcx, rax
0x180092dc7  jz      loc_180092E52
0x180092dcd  test    byte ptr [rcx+1Ch], 1
0x180092dd1  jz      short loc_180092E52
0x180092dd3  lea     edx, [rbp+23h]
0x180092dd6  jmp     loc_180092C72
0x180092ddb  mov     [rsp+68h+var_30], 0
0x180092de4  xor     r9d, r9d
0x180092de7  mov     [rsp+68h+var_38], 0
0x180092df0  mov     r8, rbx
0x180092df3  mov     [rsp+68h+var_40], 0
0x180092dfb  mov     rdx, rbp
0x180092dfe  mov     rcx, rsi
0x180092e01  mov     dword ptr [rsp+68h+var_48], 221h
0x180092e09  call    cs:__imp_OpenPortOrAuthAppAddrToStringInt3
0x180092e0f  mov     ebx, eax
0x180092e11  test    eax, eax
0x180092e13  jns     short loc_180092E62
0x180092e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180092e1c  lea     rax, WPP_GLOBAL_Control
0x180092e23  cmp     rcx, rax
0x180092e26  jz      short loc_180092E52
0x180092e28  test    byte ptr [rcx+1Ch], 1
0x180092e2c  jz      short loc_180092E52
0x180092e2e  mov     edx, 24h ; '$'
0x180092e33  lea     rax, aOpenportorauth_0; "OpenPortOrAuthAppAddrToStringInt3"
0x180092e3a  mov     rcx, [rcx+10h]
0x180092e3e  lea     r8, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids
0x180092e45  mov     r9d, ebx
0x180092e48  mov     [rsp+68h+var_48], rax
0x180092e4d  call    WPP_SF_Ds
0x180092e52  mov     edx, 221h
0x180092e57  mov     rcx, rdi
0x180092e5a  call    cs:__imp_FwFreeDynamicKeywordAddressDataBySchemaVersion
0x180092e60  jmp     short loc_180092E6B
0x180092e62  mov     [rdi+20h], rbp
0x180092e66  mov     [r14], rdi
0x180092e69  xor     ebp, ebp
0x180092e6b  mov     rcx, [rsp+68h+var_28]
0x180092e70  call    cs:__imp_FwFree
0x180092e76  mov     rcx, rbp
0x180092e79  call    cs:__imp_FwFree
0x180092e7f  mov     eax, ebx
0x180092e81  mov     rcx, [rsp+68h+var_20]
0x180092e86  xor     rcx, rsp; StackCookie
0x180092e89  call    __security_check_cookie
0x180092e8e  lea     r11, [rsp+68h+var_18]
0x180092e93  mov     rbx, [r11+30h]
0x180092e97  mov     rbp, [r11+38h]
0x180092e9b  mov     rsp, r11
0x180092e9e  pop     r14
0x180092ea0  pop     rdi
0x180092ea1  pop     rsi
0x180092ea2  retn
```
