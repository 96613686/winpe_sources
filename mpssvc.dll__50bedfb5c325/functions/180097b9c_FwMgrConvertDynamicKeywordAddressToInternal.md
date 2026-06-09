# FwMgrConvertDynamicKeywordAddressToInternal

- ea: `0x180097b9c`
- end: `0x180097d77`
- name: `FwMgrConvertDynamicKeywordAddressToInternal`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009bf94`

## callees

- `0x18000a66c`
- `0x18000a710`
- `0x180096fd0`
- `0x180097b9c`

## import_xrefs

- `fwbase!FwStringCopy` at `0x180097cb5`
- `fwbase!FwStringCopy` at `0x180097cb5`
- `fwbase!FwAlloc` at `0x180097c3b`
- `fwbase!FwAlloc` at `0x180097c3b`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressesInternal` at `0x180097d4d`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressesInternal` at `0x180097d4d`
- `FWPolicyIOMgr!FwGetDynamicKeywordOriginFromStoreType` at `0x180097c99`
- `FWPolicyIOMgr!FwGetDynamicKeywordOriginFromStoreType` at `0x180097c99`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180097cfb`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180097cfb`

## string_xrefs

- `0x180097ce5`: `FwStringCopy:keyword`
- `0x180097d2b`: `StringtoOpenPortOrAuthAppAddress`

## pseudocode

```c
__int64 __fastcall FwMgrConvertDynamicKeywordAddressToInternal(__int16 a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rdi
  __int64 v9; // r9
  int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // edx
  const char *v17; // rax
  __int64 v18; // rcx

  v4 = 0;
  if ( !a3 )
  {
    v9 = 2147942487LL;
    v10 = -2147024809;
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_25;
    v12 = 26;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v9 = 2147942487LL;
    v10 = -2147024809;
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_25;
    v12 = 27;
    goto LABEL_5;
  }
  *a4 = 0;
  v13 = FwAlloc(128);
  v4 = v13;
  if ( v13 )
  {
    *(_WORD *)(v13 + 8) = a1;
    v10 = 0;
    *(_OWORD *)(v13 + 12) = *(_OWORD *)a3;
    *(_DWORD *)(v13 + 40) = *(_DWORD *)(a3 + 24);
    *(_DWORD *)(v13 + 120) = FwGetDynamicKeywordOriginFromStoreType(a2);
    v14 = *(_QWORD *)(a3 + 16);
    if ( v14 )
    {
      v10 = FwStringCopy(v14, v4 + 32);
      if ( v10 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_25;
        v16 = 29;
        v17 = "FwStringCopy:keyword";
        goto LABEL_24;
      }
    }
    v18 = *(_QWORD *)(a3 + 32);
    if ( v18 )
    {
      v10 = StringToOpenPortOrAuthAppAddress(v18, v4 + 48);
      if ( v10 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_25;
        v16 = 30;
        v17 = "StringtoOpenPortOrAuthAppAddress";
LABEL_24:
        WPP_SF_Ds(
          *(_QWORD *)(v15 + 16),
          v16,
          (unsigned int)WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids,
          v10,
          (__int64)v17);
        goto LABEL_25;
      }
      FwDynamicKeywordMgrFormatAddresses(v4 + 48);
    }
    *a4 = v4;
    return (unsigned int)v10;
  }
  v10 = -2147024882;
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    goto LABEL_25;
  v12 = 28;
  v9 = 2147942414LL;
LABEL_5:
  WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids, v9);
LABEL_25:
  FwFreeDynamicKeywordAddressesInternal(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180097b9c  push    rbx
0x180097b9e  push    rbp
0x180097b9f  push    rsi
0x180097ba0  push    rdi
0x180097ba1  push    r14
0x180097ba3  push    r15
0x180097ba5  sub     rsp, 38h
0x180097ba9  xor     edi, edi
0x180097bab  mov     rsi, r9
0x180097bae  mov     rbp, r8
0x180097bb1  mov     r14d, edx
0x180097bb4  movzx   r15d, cx
0x180097bb8  test    r8, r8
0x180097bbb  jnz     short loc_180097BFF
0x180097bbd  mov     r9d, 80070057h
0x180097bc3  mov     ebx, r9d
0x180097bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180097bcd  lea     rax, WPP_GLOBAL_Control
0x180097bd4  cmp     rcx, rax
0x180097bd7  jz      loc_180097D4A
0x180097bdd  test    byte ptr [rcx+1Ch], 1
0x180097be1  jz      loc_180097D4A
0x180097be7  lea     edx, [rdi+1Ah]
0x180097bea  mov     rcx, [rcx+10h]
0x180097bee  lea     r8, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids
0x180097bf5  call    WPP_SF_d
0x180097bfa  jmp     loc_180097D4A
0x180097bff  test    rsi, rsi
0x180097c02  jnz     short loc_180097C33
0x180097c04  mov     r9d, 80070057h
0x180097c0a  mov     ebx, r9d
0x180097c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c14  lea     rax, WPP_GLOBAL_Control
0x180097c1b  cmp     rcx, rax
0x180097c1e  jz      loc_180097D4A
0x180097c24  test    byte ptr [rcx+1Ch], 1
0x180097c28  jz      loc_180097D4A
0x180097c2e  lea     edx, [rsi+1Bh]
0x180097c31  jmp     short loc_180097BEA
0x180097c33  mov     ecx, 80h
0x180097c38  mov     [r9], rdi
0x180097c3b  call    cs:__imp_FwAlloc
0x180097c42  nop     dword ptr [rax+rax+00h]
0x180097c47  mov     rdi, rax
0x180097c4a  test    rax, rax
0x180097c4d  jnz     short loc_180097C80
0x180097c4f  mov     ebx, 8007000Eh
0x180097c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c5b  lea     rax, WPP_GLOBAL_Control
0x180097c62  cmp     rcx, rax
0x180097c65  jz      loc_180097D4A
0x180097c6b  test    byte ptr [rcx+1Ch], 1
0x180097c6f  jz      loc_180097D4A
0x180097c75  lea     edx, [rdi+1Ch]
0x180097c78  mov     r9d, ebx
0x180097c7b  jmp     loc_180097BEA
0x180097c80  mov     [rax+8], r15w
0x180097c85  mov     ecx, r14d
0x180097c88  movups  xmm0, xmmword ptr [rbp+0]
0x180097c8c  xor     ebx, ebx
0x180097c8e  movdqu  xmmword ptr [rax+0Ch], xmm0
0x180097c93  mov     eax, [rbp+18h]
0x180097c96  mov     [rdi+28h], eax
0x180097c99  call    cs:__imp_FwGetDynamicKeywordOriginFromStoreType
0x180097ca0  nop     dword ptr [rax+rax+00h]
0x180097ca5  mov     [rdi+78h], eax
0x180097ca8  mov     rcx, [rbp+10h]
0x180097cac  test    rcx, rcx
0x180097caf  jz      short loc_180097CEE
0x180097cb1  lea     rdx, [rdi+20h]
0x180097cb5  call    cs:__imp_FwStringCopy
0x180097cbc  nop     dword ptr [rax+rax+00h]
0x180097cc1  mov     ebx, eax
0x180097cc3  test    eax, eax
0x180097cc5  jns     short loc_180097CEE
0x180097cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180097cce  lea     rax, WPP_GLOBAL_Control
0x180097cd5  cmp     rcx, rax
0x180097cd8  jz      short loc_180097D4A
0x180097cda  test    byte ptr [rcx+1Ch], 1
0x180097cde  jz      short loc_180097D4A
0x180097ce0  mov     edx, 1Dh
0x180097ce5  lea     rax, aFwstringcopyKe; "FwStringCopy:keyword"
0x180097cec  jmp     short loc_180097D32
0x180097cee  mov     rcx, [rbp+20h]
0x180097cf2  test    rcx, rcx
0x180097cf5  jz      short loc_180097D64
0x180097cf7  lea     rdx, [rdi+30h]
0x180097cfb  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180097d02  nop     dword ptr [rax+rax+00h]
0x180097d07  mov     ebx, eax
0x180097d09  test    eax, eax
0x180097d0b  jns     short loc_180097D5B
0x180097d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d14  lea     rax, WPP_GLOBAL_Control
0x180097d1b  cmp     rcx, rax
0x180097d1e  jz      short loc_180097D4A
0x180097d20  test    byte ptr [rcx+1Ch], 1
0x180097d24  jz      short loc_180097D4A
0x180097d26  mov     edx, 1Eh
0x180097d2b  lea     rax, aStringtoopenpo_1; "StringtoOpenPortOrAuthAppAddress"
0x180097d32  mov     rcx, [rcx+10h]
0x180097d36  lea     r8, WPP_b491ccf3c5393b06ed16b5e1d7bfa269_Traceguids
0x180097d3d  mov     r9d, ebx
0x180097d40  mov     [rsp+68h+var_48], rax
0x180097d45  call    WPP_SF_Ds
0x180097d4a  mov     rcx, rdi
0x180097d4d  call    cs:__imp_FwFreeDynamicKeywordAddressesInternal
0x180097d54  nop     dword ptr [rax+rax+00h]
0x180097d59  jmp     short loc_180097D67
0x180097d5b  lea     rcx, [rdi+30h]
0x180097d5f  call    FwDynamicKeywordMgrFormatAddresses
0x180097d64  mov     [rsi], rdi
0x180097d67  mov     eax, ebx
0x180097d69  add     rsp, 38h
0x180097d6d  pop     r15
0x180097d6f  pop     r14
0x180097d71  pop     rdi
0x180097d72  pop     rsi
0x180097d73  pop     rbp
0x180097d74  pop     rbx
0x180097d75  retn
```
