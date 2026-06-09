# CopyConfigToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_STORE_TYPE,ICF_PROFILE_ *)

- ea: `0x180033af8`
- end: `0x180033f0a`
- name: `?CopyConfigToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@W4_tag_FW_STORE_TYPE@@PEAUICF_PROFILE_@@@Z`
- size: `1042`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180035500`

## callees

- `0x1800090d0`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x1800333a0`
- `0x180033af8`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180033ece`
- `fwbase!FwHResultToWindowsError` at `0x180033ece`
- `fwbase!FwReportErrorAsWinError` at `0x180033c19`
- `fwbase!FwReportErrorAsWinError` at `0x180033c19`
- `fwbase!FwReportReturnError` at `0x180033bad`
- `fwbase!FwReportReturnError` at `0x180033bad`
- `fwbase!FwStringCopy` at `0x180033ebc`
- `fwbase!FwStringCopy` at `0x180033ebc`

## string_xrefs

- `0x180033c0b`: `FWGetConfig`
- `0x180033ba4`: `CopyConfigToProfile`
- `0x180033c12`: `CopyConfigToProfile`

## pseudocode

```c
__int64 __fastcall CopyConfigToProfile(__int64 a1, unsigned int a2, int a3, __int64 a4)
{
  unsigned int v5; // esi
  BOOL v8; // r14d
  int CurrentProfile; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v23[1040]; // [rsp+50h] [rbp-B0h] BYREF

  v20 = a2;
  v5 = a2;
  v21 = 0;
  v22 = 4;
  memset_0(v23, 0, sizeof(v23));
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v8 = a3 == 5;
  if ( v5 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v20);
    if ( CurrentProfile < 0 )
    {
      v10 = 0;
      FwReportReturnError("CopyConfigToProfile", (unsigned int)CurrentProfile);
      return v10;
    }
    v5 = v20;
  }
  v20 = 0;
  v11 = FWGetConfig2(a1, 1u, v5, a3 == 5, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v12 = 0;
  }
  else
  {
    if ( v11 )
    {
LABEL_10:
      FwReportErrorAsWinError("CopyConfigToProfile", "FWGetConfig", v11);
      return v10;
    }
    v12 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 8) = v12;
  v20 = 0;
  v11 = FWGetConfig2(a1, 3u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v13 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v13 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 12) = v13;
  v20 = 0;
  v11 = FWGetConfig2(a1, 0xAu, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v14 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v14 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 16) = v14;
  v20 = 0;
  v11 = FWGetConfig2(a1, 4u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v15 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v15 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 20) = v15;
  v20 = 0;
  v11 = FWGetConfig2(a1, 5u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v16 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v16 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 124) = v16;
  v20 = 0;
  v11 = FWGetConfig2(a1, 6u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v17 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v17 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 128) = v17;
  v20 = 0;
  v11 = FWGetConfig2(a1, 8u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    *(_DWORD *)(a4 + 120) = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    *(_DWORD *)(a4 + 120) = v21;
  }
  v22 = 1040;
  v20 = 0;
  v11 = FWGetConfig2(a1, 9u, v5, v8, (__int64)v23, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    *(_QWORD *)(a4 + 112) = 0;
    return 0;
  }
  if ( v11 )
    goto LABEL_10;
  v18 = FwStringCopy(v23, a4 + 112);
  if ( v18 < 0 )
    return FwHResultToWindowsError((unsigned int)v18);
  return v10;
}

```

## disassembly

```asm
0x180033af8  push    rbp
0x180033afa  push    rbx
0x180033afb  push    rsi
0x180033afc  push    rdi
0x180033afd  push    r12
0x180033aff  push    r14
0x180033b01  push    r15
0x180033b03  lea     rbp, [rsp-370h]
0x180033b0b  sub     rsp, 470h
0x180033b12  mov     rax, cs:__security_cookie
0x180033b19  xor     rax, rsp
0x180033b1c  mov     [rbp+3A0h+var_40], rax
0x180033b23  mov     ebx, r8d
0x180033b26  mov     [rsp+4A0h+var_460], edx
0x180033b2a  mov     esi, edx
0x180033b2c  mov     [rsp+4A0h+var_458], 0
0x180033b34  mov     r12, rcx
0x180033b37  mov     [rsp+4A0h+var_454], 4
0x180033b3f  xor     edx, edx; Val
0x180033b41  lea     rcx, [rsp+4A0h+var_450]; void *
0x180033b46  mov     r8d, 410h; Size
0x180033b4c  mov     r15, r9
0x180033b4f  call    memset_0
0x180033b54  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b5b  lea     rax, WPP_GLOBAL_Control
0x180033b62  cmp     rcx, rax
0x180033b65  jz      short loc_180033B82
0x180033b67  test    byte ptr [rcx+1Ch], 8
0x180033b6b  jz      short loc_180033B82
0x180033b6d  mov     rcx, [rcx+10h]
0x180033b71  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180033b78  mov     edx, 24h ; '$'
0x180033b7d  call    WPP_SF_
0x180033b82  xor     r14d, r14d
0x180033b85  cmp     ebx, 5
0x180033b88  setz    r14b
0x180033b8c  cmp     esi, 80000000h
0x180033b92  jnz     short loc_180033BC2
0x180033b94  lea     rcx, [rsp+4A0h+var_460]; enum _tag_FW_PROFILE_TYPE *
0x180033b99  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x180033b9e  test    eax, eax
0x180033ba0  jns     short loc_180033BBE
0x180033ba2  xor     ebx, ebx
0x180033ba4  lea     rcx, aCopyconfigtopr; "CopyConfigToProfile"
0x180033bab  mov     edx, eax
0x180033bad  call    cs:__imp_FwReportReturnError
0x180033bb4  nop     dword ptr [rax+rax+00h]
0x180033bb9  jmp     loc_180033EE6
0x180033bbe  mov     esi, [rsp+4A0h+var_460]
0x180033bc2  lea     rax, [rsp+4A0h+var_460]
0x180033bc7  mov     [rsp+4A0h+var_460], 0
0x180033bcf  mov     [rsp+4A0h+var_470], rax
0x180033bd4  mov     edi, 1
0x180033bd9  lea     rax, [rsp+4A0h+var_454]
0x180033bde  mov     r9d, r14d
0x180033be1  mov     [rsp+4A0h+var_478], rax
0x180033be6  mov     r8d, esi
0x180033be9  lea     rax, [rsp+4A0h+var_458]
0x180033bee  mov     edx, edi
0x180033bf0  mov     rcx, r12
0x180033bf3  mov     [rsp+4A0h+var_480], rax
0x180033bf8  call    FWGetConfig2
0x180033bfd  mov     ebx, eax
0x180033bff  cmp     eax, 2
0x180033c02  jz      short loc_180033C38
0x180033c04  test    eax, eax
0x180033c06  jz      short loc_180033C2A
0x180033c08  mov     r8d, eax
0x180033c0b  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x180033c12  lea     rcx, aCopyconfigtopr; "CopyConfigToProfile"
0x180033c19  call    cs:__imp_FwReportErrorAsWinError
0x180033c20  nop     dword ptr [rax+rax+00h]
0x180033c25  jmp     loc_180033EE6
0x180033c2a  mov     eax, [rsp+4A0h+var_458]
0x180033c2e  neg     eax
0x180033c30  sbb     ecx, ecx
0x180033c32  neg     ecx
0x180033c34  add     ecx, edi
0x180033c36  jmp     short loc_180033C3A
0x180033c38  xor     ecx, ecx
0x180033c3a  mov     [r15+8], ecx
0x180033c3e  lea     rax, [rsp+4A0h+var_460]
0x180033c43  mov     [rsp+4A0h+var_470], rax
0x180033c48  mov     r9d, r14d
0x180033c4b  lea     rax, [rsp+4A0h+var_454]
0x180033c50  mov     [rsp+4A0h+var_460], 0
0x180033c58  mov     [rsp+4A0h+var_478], rax
0x180033c5d  mov     r8d, esi
0x180033c60  lea     rax, [rsp+4A0h+var_458]
0x180033c65  mov     edx, 3
0x180033c6a  mov     rcx, r12
0x180033c6d  mov     [rsp+4A0h+var_480], rax
0x180033c72  call    FWGetConfig2
0x180033c77  mov     ebx, eax
0x180033c79  cmp     eax, 2
0x180033c7c  jz      short loc_180033C90
0x180033c7e  test    eax, eax
0x180033c80  jnz     short loc_180033C08
0x180033c82  mov     eax, [rsp+4A0h+var_458]
0x180033c86  neg     eax
0x180033c88  sbb     ecx, ecx
0x180033c8a  neg     ecx
0x180033c8c  add     ecx, edi
0x180033c8e  jmp     short loc_180033C92
0x180033c90  xor     ecx, ecx
0x180033c92  mov     [r15+0Ch], ecx
0x180033c96  lea     rax, [rsp+4A0h+var_460]
0x180033c9b  mov     [rsp+4A0h+var_470], rax
0x180033ca0  mov     r9d, r14d
0x180033ca3  lea     rax, [rsp+4A0h+var_454]
0x180033ca8  mov     [rsp+4A0h+var_460], 0
0x180033cb0  mov     [rsp+4A0h+var_478], rax
0x180033cb5  mov     r8d, esi
0x180033cb8  lea     rax, [rsp+4A0h+var_458]
0x180033cbd  mov     edx, 0Ah
0x180033cc2  mov     rcx, r12
0x180033cc5  mov     [rsp+4A0h+var_480], rax
0x180033cca  call    FWGetConfig2
0x180033ccf  mov     ebx, eax
0x180033cd1  cmp     eax, 2
0x180033cd4  jz      short loc_180033CEC
0x180033cd6  test    eax, eax
0x180033cd8  jnz     loc_180033C08
0x180033cde  mov     eax, [rsp+4A0h+var_458]
0x180033ce2  neg     eax
0x180033ce4  sbb     ecx, ecx
0x180033ce6  neg     ecx
0x180033ce8  add     ecx, edi
0x180033cea  jmp     short loc_180033CEE
0x180033cec  xor     ecx, ecx
0x180033cee  mov     [r15+10h], ecx
0x180033cf2  lea     rax, [rsp+4A0h+var_460]
0x180033cf7  mov     [rsp+4A0h+var_470], rax
0x180033cfc  mov     r9d, r14d
0x180033cff  lea     rax, [rsp+4A0h+var_454]
0x180033d04  mov     [rsp+4A0h+var_460], 0
0x180033d0c  mov     [rsp+4A0h+var_478], rax
0x180033d11  mov     r8d, esi
0x180033d14  lea     rax, [rsp+4A0h+var_458]
0x180033d19  mov     edx, 4
0x180033d1e  mov     rcx, r12
0x180033d21  mov     [rsp+4A0h+var_480], rax
0x180033d26  call    FWGetConfig2
0x180033d2b  mov     ebx, eax
0x180033d2d  cmp     eax, 2
0x180033d30  jz      short loc_180033D48
0x180033d32  test    eax, eax
0x180033d34  jnz     loc_180033C08
0x180033d3a  mov     eax, [rsp+4A0h+var_458]
0x180033d3e  neg     eax
0x180033d40  sbb     ecx, ecx
0x180033d42  neg     ecx
0x180033d44  add     ecx, edi
0x180033d46  jmp     short loc_180033D4A
0x180033d48  xor     ecx, ecx
0x180033d4a  mov     [r15+14h], ecx
0x180033d4e  lea     rax, [rsp+4A0h+var_460]
0x180033d53  mov     [rsp+4A0h+var_470], rax
0x180033d58  mov     r9d, r14d
0x180033d5b  lea     rax, [rsp+4A0h+var_454]
0x180033d60  mov     [rsp+4A0h+var_460], 0
0x180033d68  mov     [rsp+4A0h+var_478], rax
0x180033d6d  mov     r8d, esi
0x180033d70  lea     rax, [rsp+4A0h+var_458]
0x180033d75  mov     edx, 5
0x180033d7a  mov     rcx, r12
0x180033d7d  mov     [rsp+4A0h+var_480], rax
0x180033d82  call    FWGetConfig2
0x180033d87  mov     ebx, eax
0x180033d89  cmp     eax, 2
0x180033d8c  jz      short loc_180033DA4
0x180033d8e  test    eax, eax
0x180033d90  jnz     loc_180033C08
0x180033d96  mov     eax, [rsp+4A0h+var_458]
0x180033d9a  neg     eax
0x180033d9c  sbb     ecx, ecx
0x180033d9e  neg     ecx
0x180033da0  add     ecx, edi
0x180033da2  jmp     short loc_180033DA6
0x180033da4  xor     ecx, ecx
0x180033da6  mov     [r15+7Ch], ecx
0x180033daa  lea     rax, [rsp+4A0h+var_460]
0x180033daf  mov     [rsp+4A0h+var_470], rax
0x180033db4  mov     r9d, r14d
0x180033db7  lea     rax, [rsp+4A0h+var_454]
0x180033dbc  mov     [rsp+4A0h+var_460], 0
0x180033dc4  mov     [rsp+4A0h+var_478], rax
0x180033dc9  mov     r8d, esi
0x180033dcc  lea     rax, [rsp+4A0h+var_458]
0x180033dd1  mov     edx, 6
0x180033dd6  mov     rcx, r12
0x180033dd9  mov     [rsp+4A0h+var_480], rax
0x180033dde  call    FWGetConfig2
0x180033de3  mov     ebx, eax
0x180033de5  cmp     eax, 2
0x180033de8  jz      short loc_180033E00
0x180033dea  test    eax, eax
0x180033dec  jnz     loc_180033C08
0x180033df2  mov     eax, [rsp+4A0h+var_458]
0x180033df6  neg     eax
0x180033df8  sbb     ecx, ecx
0x180033dfa  neg     ecx
0x180033dfc  inc     ecx
0x180033dfe  jmp     short loc_180033E02
0x180033e00  xor     ecx, ecx
0x180033e02  mov     [r15+80h], ecx
0x180033e09  lea     rax, [rsp+4A0h+var_460]
0x180033e0e  mov     [rsp+4A0h+var_470], rax
0x180033e13  mov     r9d, r14d
0x180033e16  lea     rax, [rsp+4A0h+var_454]
0x180033e1b  mov     [rsp+4A0h+var_460], 0
0x180033e23  mov     [rsp+4A0h+var_478], rax
0x180033e28  mov     r8d, esi
0x180033e2b  lea     rax, [rsp+4A0h+var_458]
0x180033e30  mov     edx, 8
0x180033e35  mov     rcx, r12
0x180033e38  mov     [rsp+4A0h+var_480], rax
0x180033e3d  call    FWGetConfig2
0x180033e42  mov     ebx, eax
0x180033e44  cmp     eax, 2
0x180033e47  jz      short loc_180033E5B
0x180033e49  test    eax, eax
0x180033e4b  jnz     loc_180033C08
0x180033e51  mov     eax, [rsp+4A0h+var_458]
0x180033e55  mov     [r15+78h], eax
0x180033e59  jmp     short loc_180033E63
0x180033e5b  mov     dword ptr [r15+78h], 0
0x180033e63  lea     rax, [rsp+4A0h+var_460]
0x180033e68  mov     [rsp+4A0h+var_454], 410h
0x180033e70  mov     [rsp+4A0h+var_470], rax
0x180033e75  mov     r9d, r14d
0x180033e78  lea     rax, [rsp+4A0h+var_454]
0x180033e7d  mov     [rsp+4A0h+var_460], 0
0x180033e85  mov     [rsp+4A0h+var_478], rax
0x180033e8a  mov     r8d, esi
0x180033e8d  lea     rax, [rsp+4A0h+var_450]
0x180033e92  mov     edx, 9
0x180033e97  mov     rcx, r12
0x180033e9a  mov     [rsp+4A0h+var_480], rax
0x180033e9f  call    FWGetConfig2
0x180033ea4  mov     ebx, eax
0x180033ea6  cmp     eax, 2
0x180033ea9  jz      short loc_180033EDC
0x180033eab  test    eax, eax
0x180033ead  jnz     loc_180033C08
0x180033eb3  lea     rdx, [r15+70h]
0x180033eb7  lea     rcx, [rsp+4A0h+var_450]
0x180033ebc  call    cs:__imp_FwStringCopy
0x180033ec3  nop     dword ptr [rax+rax+00h]
0x180033ec8  test    eax, eax
0x180033eca  jns     short loc_180033EE6
0x180033ecc  mov     ecx, eax
0x180033ece  call    cs:__imp_FwHResultToWindowsError
0x180033ed5  nop     dword ptr [rax+rax+00h]
0x180033eda  jmp     short loc_180033EE8
0x180033edc  mov     qword ptr [r15+70h], 0
0x180033ee4  xor     ebx, ebx
0x180033ee6  mov     eax, ebx
0x180033ee8  mov     rcx, [rbp+3A0h+var_40]
0x180033eef  xor     rcx, rsp; StackCookie
0x180033ef2  call    __security_check_cookie
0x180033ef7  add     rsp, 470h
0x180033efe  pop     r15
0x180033f00  pop     r14
0x180033f02  pop     r12
0x180033f04  pop     rdi
0x180033f05  pop     rsi
0x180033f06  pop     rbx
0x180033f07  pop     rbp
0x180033f08  retn
```
