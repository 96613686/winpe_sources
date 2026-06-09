# FwMgrConvertDynamicKeywordAddressToInternal

- ea: `0x180092eac`
- end: `0x180093068`
- name: `FwMgrConvertDynamicKeywordAddressToInternal`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180096f28`

## callees

- `0x18000ae9c`
- `0x18000af3c`
- `0x180092368`
- `0x180092eac`

## import_xrefs

- `fwbase!FwStringCopy` at `0x180092fb9`
- `fwbase!FwStringCopy` at `0x180092fb9`
- `fwbase!FwAlloc` at `0x180092f4b`
- `fwbase!FwAlloc` at `0x180092f4b`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressesInternal` at `0x180093045`
- `FWPolicyIOMgr!FwFreeDynamicKeywordAddressesInternal` at `0x180093045`
- `FWPolicyIOMgr!FwGetDynamicKeywordOriginFromStoreType` at `0x180092fa3`
- `FWPolicyIOMgr!FwGetDynamicKeywordOriginFromStoreType` at `0x180092fa3`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180092ff9`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180092ff9`

## string_xrefs

- `0x180092fe3`: `FwStringCopy:keyword`
- `0x180093023`: `StringtoOpenPortOrAuthAppAddress`

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
          (unsigned int)WPP_69b4ffd36c543342139ff27524f05d89_Traceguids,
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
  WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids, v9);
LABEL_25:
  FwFreeDynamicKeywordAddressesInternal(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180092eac  push    rbx
0x180092eae  push    rbp
0x180092eaf  push    rsi
0x180092eb0  push    rdi
0x180092eb1  push    r14
0x180092eb3  push    r15
0x180092eb5  sub     rsp, 38h
0x180092eb9  xor     edi, edi
0x180092ebb  mov     rsi, r9
0x180092ebe  mov     rbp, r8
0x180092ec1  mov     r14d, edx
0x180092ec4  movzx   r15d, cx
0x180092ec8  test    r8, r8
0x180092ecb  jnz     short loc_180092F0F
0x180092ecd  mov     r9d, 80070057h
0x180092ed3  mov     ebx, r9d
0x180092ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180092edd  lea     rax, WPP_GLOBAL_Control
0x180092ee4  cmp     rcx, rax
0x180092ee7  jz      loc_180093042
0x180092eed  test    byte ptr [rcx+1Ch], 1
0x180092ef1  jz      loc_180093042
0x180092ef7  lea     edx, [rdi+1Ah]
0x180092efa  mov     rcx, [rcx+10h]
0x180092efe  lea     r8, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids
0x180092f05  call    WPP_SF_d
0x180092f0a  jmp     loc_180093042
0x180092f0f  test    rsi, rsi
0x180092f12  jnz     short loc_180092F43
0x180092f14  mov     r9d, 80070057h
0x180092f1a  mov     ebx, r9d
0x180092f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180092f24  lea     rax, WPP_GLOBAL_Control
0x180092f2b  cmp     rcx, rax
0x180092f2e  jz      loc_180093042
0x180092f34  test    byte ptr [rcx+1Ch], 1
0x180092f38  jz      loc_180093042
0x180092f3e  lea     edx, [rsi+1Bh]
0x180092f41  jmp     short loc_180092EFA
0x180092f43  mov     ecx, 80h
0x180092f48  mov     [r9], rdi
0x180092f4b  call    cs:__imp_FwAlloc
0x180092f51  mov     rdi, rax
0x180092f54  test    rax, rax
0x180092f57  jnz     short loc_180092F8A
0x180092f59  mov     ebx, 8007000Eh
0x180092f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092f65  lea     rax, WPP_GLOBAL_Control
0x180092f6c  cmp     rcx, rax
0x180092f6f  jz      loc_180093042
0x180092f75  test    byte ptr [rcx+1Ch], 1
0x180092f79  jz      loc_180093042
0x180092f7f  lea     edx, [rdi+1Ch]
0x180092f82  mov     r9d, ebx
0x180092f85  jmp     loc_180092EFA
0x180092f8a  mov     [rax+8], r15w
0x180092f8f  mov     ecx, r14d
0x180092f92  movups  xmm0, xmmword ptr [rbp+0]
0x180092f96  xor     ebx, ebx
0x180092f98  movdqu  xmmword ptr [rax+0Ch], xmm0
0x180092f9d  mov     eax, [rbp+18h]
0x180092fa0  mov     [rdi+28h], eax
0x180092fa3  call    cs:__imp_FwGetDynamicKeywordOriginFromStoreType
0x180092fa9  mov     [rdi+78h], eax
0x180092fac  mov     rcx, [rbp+10h]
0x180092fb0  test    rcx, rcx
0x180092fb3  jz      short loc_180092FEC
0x180092fb5  lea     rdx, [rdi+20h]
0x180092fb9  call    cs:__imp_FwStringCopy
0x180092fbf  mov     ebx, eax
0x180092fc1  test    eax, eax
0x180092fc3  jns     short loc_180092FEC
0x180092fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180092fcc  lea     rax, WPP_GLOBAL_Control
0x180092fd3  cmp     rcx, rax
0x180092fd6  jz      short loc_180093042
0x180092fd8  test    byte ptr [rcx+1Ch], 1
0x180092fdc  jz      short loc_180093042
0x180092fde  mov     edx, 1Dh
0x180092fe3  lea     rax, aFwstringcopyKe; "FwStringCopy:keyword"
0x180092fea  jmp     short loc_18009302A
0x180092fec  mov     rcx, [rbp+20h]
0x180092ff0  test    rcx, rcx
0x180092ff3  jz      short loc_180093056
0x180092ff5  lea     rdx, [rdi+30h]
0x180092ff9  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180092fff  mov     ebx, eax
0x180093001  test    eax, eax
0x180093003  jns     short loc_18009304D
0x180093005  mov     rcx, cs:WPP_GLOBAL_Control
0x18009300c  lea     rax, WPP_GLOBAL_Control
0x180093013  cmp     rcx, rax
0x180093016  jz      short loc_180093042
0x180093018  test    byte ptr [rcx+1Ch], 1
0x18009301c  jz      short loc_180093042
0x18009301e  mov     edx, 1Eh
0x180093023  lea     rax, aStringtoopenpo_1; "StringtoOpenPortOrAuthAppAddress"
0x18009302a  mov     rcx, [rcx+10h]
0x18009302e  lea     r8, WPP_69b4ffd36c543342139ff27524f05d89_Traceguids
0x180093035  mov     r9d, ebx
0x180093038  mov     [rsp+68h+var_48], rax
0x18009303d  call    WPP_SF_Ds
0x180093042  mov     rcx, rdi
0x180093045  call    cs:__imp_FwFreeDynamicKeywordAddressesInternal
0x18009304b  jmp     short loc_180093059
0x18009304d  lea     rcx, [rdi+30h]
0x180093051  call    FwDynamicKeywordMgrFormatAddresses
0x180093056  mov     [rsi], rdi
0x180093059  mov     eax, ebx
0x18009305b  add     rsp, 38h
0x18009305f  pop     r15
0x180093061  pop     r14
0x180093063  pop     rdi
0x180093064  pop     rsi
0x180093065  pop     rbp
0x180093066  pop     rbx
0x180093067  retn
```
