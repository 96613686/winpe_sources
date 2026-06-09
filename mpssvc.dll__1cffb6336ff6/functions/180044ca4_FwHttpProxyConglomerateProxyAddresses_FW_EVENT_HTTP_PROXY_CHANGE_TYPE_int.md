# FwHttpProxyConglomerateProxyAddresses(FW_EVENT_HTTP_PROXY_CHANGE_TYPE_,int *)

- ea: `0x180044ca4`
- end: `0x18004511e`
- name: `?FwHttpProxyConglomerateProxyAddresses@@YAKW4FW_EVENT_HTTP_PROXY_CHANGE_TYPE_@@PEAH@Z`
- size: `1146`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044840`
- `0x180054bb8`
- `0x1800a66b4`

## callees

- `0x18000af3c`
- `0x180044ca4`
- `0x180045124`
- `0x180067c5c`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `fwbase!FwSortAddresses` at `0x180044d71`
- `fwbase!FwSortAddresses` at `0x180044f09`
- `fwbase!FwSortAddresses` at `0x180044f41`
- `fwbase!FwSortAddresses` at `0x180044d71`
- `fwbase!FwSortAddresses` at `0x180044f09`
- `fwbase!FwSortAddresses` at `0x180044f41`
- `fwbase!FwHResultToWindowsError` at `0x180044e69`
- `fwbase!FwHResultToWindowsError` at `0x180044ef5`
- `fwbase!FwHResultToWindowsError` at `0x180044fc6`
- `fwbase!FwHResultToWindowsError` at `0x180044e69`
- `fwbase!FwHResultToWindowsError` at `0x180044ef5`
- `fwbase!FwHResultToWindowsError` at `0x180044fc6`
- `fwbase!FwCriticalSectionEnter` at `0x180044d15`
- `fwbase!FwCriticalSectionEnter` at `0x180044d15`
- `fwbase!FwCriticalSectionLeave` at `0x180044e1a`
- `fwbase!FwCriticalSectionLeave` at `0x180044e1a`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x180044d8e`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x180044d8e`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180044d7c`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180044f13`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180044d7c`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180044f13`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x180044f55`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x180044f55`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180044e61`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180044fbe`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180044e61`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180044fbe`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180044eed`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180044eed`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044d22`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044da5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044e7e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044f5f`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045005`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044d22`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044da5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044e7e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044f5f`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045005`

## pseudocode

```c
__int64 __fastcall FwHttpProxyConglomerateProxyAddresses(int a1, int *a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // r12d
  unsigned int v4; // edi
  int v5; // r15d
  unsigned int v6; // r13d
  __int64 v7; // rcx
  _BYTE *v8; // r14
  _BYTE *v9; // rsi
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v25; // [rsp+B0h] [rbp-50h]
  __int128 v26; // [rsp+C0h] [rbp-40h]
  __int128 v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+E0h] [rbp-20h]
  _BYTE v29[80]; // [rsp+F0h] [rbp-10h] BYREF

  v2 = 0;
  memset_0(&v19, 0, 0x48u);
  memset_0(&v24, 0, 0x48u);
  memset_0(v29, 0, 0x48u);
  v3 = dword_18012C528;
  FwCriticalSectionEnter(qword_18012C538);
  FwPolioEmptyWFAddresses(&xmmword_18012C5B0);
  v4 = 0;
  v5 = 1;
  v6 = v3;
  while ( 1 )
  {
    if ( v4 >= dword_18012C528 )
    {
      v8 = v29;
      v9 = v29;
      FwSortAddresses(&v19);
      FwRemoveDuplicateAddresses(&v19);
      if ( (unsigned int)IsEqualAddresses(&xmmword_18012C568, &v19) == 1 )
      {
        v5 = 0;
        FwPolioEmptyWFAddresses(&v19);
        v19 = xmmword_18012C568;
        v20 = *(_OWORD *)&qword_18012C578;
        v21 = xmmword_18012C588;
        v23 = qword_18012C5A8;
        v22 = *(_OWORD *)&qword_18012C598;
      }
      else
      {
        FwPolioEmptyWFAddresses(&xmmword_18012C568);
        xmmword_18012C568 = v19;
        xmmword_18012C588 = v21;
        *(_OWORD *)&qword_18012C578 = v20;
        qword_18012C5A8 = v23;
        *(_OWORD *)&qword_18012C598 = v22;
      }
      if ( v3 == v4 )
        goto LABEL_10;
      v12 = 120LL * v3;
      v8 = (_BYTE *)(v12 + qword_18012C530 + 32);
      if ( dword_18012C524 == 1 )
      {
        v13 = FwPolioCopyWFAddressesContents(v12 + qword_18012C530 + 32, &v24);
        v2 = FwHResultToWindowsError(v13);
        if ( v2 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v15 = 52;
            goto LABEL_26;
          }
          goto LABEL_14;
        }
      }
      else
      {
        v16 = FwUniteWFAddressesContents(&v19, v12 + qword_18012C530 + 32, &v24);
        v2 = FwHResultToWindowsError(v16);
        if ( v2 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_14;
          v15 = 53;
          goto LABEL_26;
        }
      }
      FwSortAddresses(&v24);
      FwRemoveDuplicateAddresses(&v24);
      if ( v6 == v4 )
      {
        xmmword_18012C5B0 = v24;
        xmmword_18012C5D0 = v26;
        *(_OWORD *)byte_18012C5C0 = v25;
        qword_18012C5F0 = v28;
        *(_OWORD *)byte_18012C5E0 = v27;
      }
      else
      {
        v9 = (_BYTE *)(120LL * v6 + qword_18012C530 + 32);
        qword_18012C648 = (__int64)v9;
        FwSortAddresses(v9);
        FwSubtractAddresses(&v24, v9, &xmmword_18012C5B0);
        FwPolioEmptyWFAddresses(&v24);
      }
      v2 = FwHttpComputeDaNat64Proxies();
      if ( !v2 )
      {
LABEL_10:
        if ( a2 )
          *a2 = v5;
        if ( v5 || !a1 )
          FwEventHttpProxyChanged(
            a1,
            (__int64)&xmmword_18012C568,
            (__int64)&xmmword_18012C5B0,
            (__int64)v8,
            (__int64)v9,
            (__int64)qword_18012C5F8,
            dword_18012C524);
        goto LABEL_14;
      }
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v15 = 54;
LABEL_26:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids, v2);
      goto LABEL_14;
    }
    v7 = 120LL * v4;
    if ( (*(_BYTE *)(v7 + qword_18012C530 + 104) & 8) != 0 )
    {
      v3 = v4;
      goto LABEL_6;
    }
    if ( (*(_BYTE *)(v7 + qword_18012C530 + 104) & 0x10) != 0 )
    {
      v6 = v4;
      goto LABEL_6;
    }
    v11 = FwUniteWFAddressesContents(&v19, v7 + qword_18012C530 + 32, &v24);
    v2 = FwHResultToWindowsError(v11);
    if ( v2 )
      break;
    FwPolioEmptyWFAddresses(&v19);
    v19 = v24;
    v21 = v26;
    v20 = v25;
    v23 = v28;
    v22 = v27;
    memset_0(&v24, 0, 0x48u);
LABEL_6:
    ++v4;
  }
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v15 = 51;
    goto LABEL_26;
  }
LABEL_14:
  FwCriticalSectionLeave(qword_18012C538);
  return v2;
}

```

## disassembly

```asm
0x180044ca4  mov     [rsp-8+arg_10], rbx
0x180044ca9  push    rbp
0x180044caa  push    rsi
0x180044cab  push    rdi
0x180044cac  push    r12
0x180044cae  push    r13
0x180044cb0  push    r14
0x180044cb2  push    r15
0x180044cb4  lea     rbp, [rsp-50h]
0x180044cb9  sub     rsp, 150h
0x180044cc0  mov     rax, cs:__security_cookie
0x180044cc7  xor     rax, rsp
0x180044cca  mov     [rbp+80h+var_40], rax
0x180044cce  mov     [rsp+180h+var_138], rdx
0x180044cd3  xor     ebx, ebx
0x180044cd5  mov     [rsp+180h+var_140], ecx
0x180044cd9  xor     edx, edx; Val
0x180044cdb  lea     rcx, [rsp+180h+var_130]; void *
0x180044ce0  lea     esi, [rbx+48h]
0x180044ce3  mov     r8d, esi; Size
0x180044ce6  call    memset_0
0x180044ceb  mov     r8d, esi; Size
0x180044cee  lea     rcx, [rbp+80h+var_E0]; void *
0x180044cf2  xor     edx, edx; Val
0x180044cf4  call    memset_0
0x180044cf9  mov     r8d, esi; Size
0x180044cfc  lea     rcx, [rbp+80h+var_90]; void *
0x180044d00  xor     edx, edx; Val
0x180044d02  call    memset_0
0x180044d07  mov     r12d, cs:dword_18012C528
0x180044d0e  lea     rcx, qword_18012C538
0x180044d15  call    cs:__imp_FwCriticalSectionEnter
0x180044d1b  lea     rcx, xmmword_18012C5B0
0x180044d22  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044d28  xor     edi, edi
0x180044d2a  lea     r15d, [rbx+1]
0x180044d2e  mov     r13d, r12d
0x180044d31  cmp     edi, cs:dword_18012C528
0x180044d37  jnb     short loc_180044D64
0x180044d39  mov     eax, edi
0x180044d3b  imul    rcx, rax, 78h ; 'x'
0x180044d3f  mov     rax, cs:qword_18012C530
0x180044d46  test    byte ptr [rcx+rax+68h], 8
0x180044d4b  jnz     loc_180044E49
0x180044d51  test    byte ptr [rcx+rax+68h], 10h
0x180044d56  jz      loc_180044E51
0x180044d5c  mov     r13d, edi
0x180044d5f  add     edi, r15d
0x180044d62  jmp     short loc_180044D31
0x180044d64  lea     rcx, [rsp+180h+var_130]
0x180044d69  lea     r14, [rbp+80h+var_90]
0x180044d6d  lea     rsi, [rbp+80h+var_90]
0x180044d71  call    cs:__imp_FwSortAddresses
0x180044d77  lea     rcx, [rsp+180h+var_130]
0x180044d7c  call    cs:__imp_FwRemoveDuplicateAddresses
0x180044d82  lea     rdx, [rsp+180h+var_130]
0x180044d87  lea     rcx, xmmword_18012C568
0x180044d8e  call    cs:__imp_IsEqualAddresses
0x180044d94  cmp     eax, r15d
0x180044d97  jnz     loc_180044FFE
0x180044d9d  xor     r15d, r15d
0x180044da0  lea     rcx, [rsp+180h+var_130]
0x180044da5  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044dab  movups  xmm0, cs:xmmword_18012C568
0x180044db2  movups  xmm1, xmmword ptr cs:qword_18012C578
0x180044db9  movaps  [rsp+180h+var_130], xmm0
0x180044dbe  movups  xmm0, cs:xmmword_18012C588
0x180044dc5  movaps  [rsp+180h+var_120], xmm1
0x180044dca  movups  xmm1, xmmword ptr cs:qword_18012C598
0x180044dd1  movaps  [rsp+180h+var_110], xmm0
0x180044dd6  movsd   xmm0, cs:qword_18012C5A8
0x180044dde  movsd   [rbp+80h+var_F0], xmm0
0x180044de3  movaps  [rbp+80h+var_100], xmm1
0x180044de7  cmp     r12d, edi
0x180044dea  jnz     loc_180044EC4
0x180044df0  mov     rax, [rsp+180h+var_138]
0x180044df5  test    rax, rax
0x180044df8  jnz     loc_1800450E0
0x180044dfe  mov     ecx, [rsp+180h+var_140]
0x180044e02  test    r15d, r15d
0x180044e05  jnz     loc_1800450E8
0x180044e0b  test    ecx, ecx
0x180044e0d  jz      loc_1800450E8
0x180044e13  lea     rcx, qword_18012C538
0x180044e1a  call    cs:__imp_FwCriticalSectionLeave
0x180044e20  mov     eax, ebx
0x180044e22  mov     rcx, [rbp+80h+var_40]
0x180044e26  xor     rcx, rsp; StackCookie
0x180044e29  call    __security_check_cookie
0x180044e2e  mov     rbx, [rsp+180h+arg_10]
0x180044e36  add     rsp, 150h
0x180044e3d  pop     r15
0x180044e3f  pop     r14
0x180044e41  pop     r13
0x180044e43  pop     r12
0x180044e45  pop     rdi
0x180044e46  pop     rsi
0x180044e47  pop     rbp
0x180044e48  retn
0x180044e49  mov     r12d, edi
0x180044e4c  jmp     loc_180044D5F
0x180044e51  lea     rdx, [rax+20h]
0x180044e55  add     rdx, rcx
0x180044e58  lea     r8, [rbp+80h+var_E0]
0x180044e5c  lea     rcx, [rsp+180h+var_130]
0x180044e61  call    cs:__imp_FwUniteWFAddressesContents
0x180044e67  mov     ecx, eax
0x180044e69  call    cs:__imp_FwHResultToWindowsError
0x180044e6f  mov     ebx, eax
0x180044e71  test    eax, eax
0x180044e73  jnz     loc_18004508A
0x180044e79  lea     rcx, [rsp+180h+var_130]
0x180044e7e  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044e84  movaps  xmm0, [rbp+80h+var_E0]
0x180044e88  lea     rcx, [rbp+80h+var_E0]; void *
0x180044e8c  movaps  xmm1, [rbp+80h+var_D0]
0x180044e90  mov     r8, rsi; Size
0x180044e93  movaps  [rsp+180h+var_130], xmm0
0x180044e98  xor     edx, edx; Val
0x180044e9a  movaps  xmm0, [rbp+80h+var_C0]
0x180044e9e  movaps  [rsp+180h+var_110], xmm0
0x180044ea3  movsd   xmm0, [rbp+80h+var_A0]
0x180044ea8  movaps  [rsp+180h+var_120], xmm1
0x180044ead  movaps  xmm1, [rbp+80h+var_B0]
0x180044eb1  movsd   [rbp+80h+var_F0], xmm0
0x180044eb6  movaps  [rbp+80h+var_100], xmm1
0x180044eba  call    memset_0
0x180044ebf  jmp     loc_180044D5F
0x180044ec4  mov     r14, cs:qword_18012C530
0x180044ecb  add     r14, 20h ; ' '
0x180044ecf  mov     eax, r12d
0x180044ed2  imul    rcx, rax, 78h ; 'x'
0x180044ed6  add     r14, rcx
0x180044ed9  cmp     cs:dword_18012C524, 1
0x180044ee0  jnz     loc_180044FB2
0x180044ee6  lea     rdx, [rbp+80h+var_E0]
0x180044eea  mov     rcx, r14
0x180044eed  call    cs:__imp_FwPolioCopyWFAddressesContents
0x180044ef3  mov     ecx, eax
0x180044ef5  call    cs:__imp_FwHResultToWindowsError
0x180044efb  mov     ebx, eax
0x180044efd  test    eax, eax
0x180044eff  jnz     loc_1800450B5
0x180044f05  lea     rcx, [rbp+80h+var_E0]
0x180044f09  call    cs:__imp_FwSortAddresses
0x180044f0f  lea     rcx, [rbp+80h+var_E0]
0x180044f13  call    cs:__imp_FwRemoveDuplicateAddresses
0x180044f19  cmp     r13d, edi
0x180044f1c  jz      loc_18004504C
0x180044f22  mov     rsi, cs:qword_18012C530
0x180044f29  mov     eax, r13d
0x180044f2c  add     rsi, 20h ; ' '
0x180044f30  imul    rcx, rax, 78h ; 'x'
0x180044f34  add     rsi, rcx
0x180044f37  mov     rcx, rsi
0x180044f3a  mov     cs:qword_18012C648, rsi
0x180044f41  call    cs:__imp_FwSortAddresses
0x180044f47  lea     r8, xmmword_18012C5B0
0x180044f4e  mov     rdx, rsi
0x180044f51  lea     rcx, [rbp+80h+var_E0]
0x180044f55  call    cs:__imp_FwSubtractAddresses
0x180044f5b  lea     rcx, [rbp+80h+var_E0]
0x180044f5f  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044f65  call    ?FwHttpComputeDaNat64Proxies@@YAKXZ; FwHttpComputeDaNat64Proxies(void)
0x180044f6a  mov     ebx, eax
0x180044f6c  test    eax, eax
0x180044f6e  jz      loc_180044DF0
0x180044f74  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f7b  lea     rax, WPP_GLOBAL_Control
0x180044f82  cmp     rcx, rax
0x180044f85  jz      loc_180044E13
0x180044f8b  test    byte ptr [rcx+1Ch], 1
0x180044f8f  jz      loc_180044E13
0x180044f95  mov     edx, 36h ; '6'
0x180044f9a  mov     rcx, [rcx+10h]
0x180044f9e  lea     r8, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids
0x180044fa5  mov     r9d, ebx
0x180044fa8  call    WPP_SF_d
0x180044fad  jmp     loc_180044E13
0x180044fb2  lea     r8, [rbp+80h+var_E0]
0x180044fb6  mov     rdx, r14
0x180044fb9  lea     rcx, [rsp+180h+var_130]
0x180044fbe  call    cs:__imp_FwUniteWFAddressesContents
0x180044fc4  mov     ecx, eax
0x180044fc6  call    cs:__imp_FwHResultToWindowsError
0x180044fcc  mov     ebx, eax
0x180044fce  test    eax, eax
0x180044fd0  jz      loc_180044F05
0x180044fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180044fdd  lea     rax, WPP_GLOBAL_Control
0x180044fe4  cmp     rcx, rax
0x180044fe7  jz      loc_180044E13
0x180044fed  test    byte ptr [rcx+1Ch], 1
0x180044ff1  jz      loc_180044E13
0x180044ff7  mov     edx, 35h ; '5'
0x180044ffc  jmp     short loc_180044F9A
0x180044ffe  lea     rcx, xmmword_18012C568
0x180045005  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004500b  movaps  xmm0, [rsp+180h+var_130]
0x180045010  movaps  xmm1, [rsp+180h+var_120]
0x180045015  movups  cs:xmmword_18012C568, xmm0
0x18004501c  movaps  xmm0, [rsp+180h+var_110]
0x180045021  movups  cs:xmmword_18012C588, xmm0
0x180045028  movsd   xmm0, [rbp+80h+var_F0]
0x18004502d  movups  xmmword ptr cs:qword_18012C578, xmm1
0x180045034  movaps  xmm1, [rbp+80h+var_100]
0x180045038  movsd   cs:qword_18012C5A8, xmm0
0x180045040  movups  xmmword ptr cs:qword_18012C598, xmm1
0x180045047  jmp     loc_180044DE7
0x18004504c  movaps  xmm0, [rbp+80h+var_E0]
0x180045050  movaps  xmm1, [rbp+80h+var_D0]
0x180045054  movaps  cs:xmmword_18012C5B0, xmm0
0x18004505b  movaps  xmm0, [rbp+80h+var_C0]
0x18004505f  movaps  cs:xmmword_18012C5D0, xmm0
0x180045066  movsd   xmm0, [rbp+80h+var_A0]
0x18004506b  movaps  xmmword ptr cs:byte_18012C5C0, xmm1
0x180045072  movaps  xmm1, [rbp+80h+var_B0]
0x180045076  movsd   cs:qword_18012C5F0, xmm0
0x18004507e  movaps  xmmword ptr cs:byte_18012C5E0, xmm1
0x180045085  jmp     loc_180044F65
0x18004508a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045091  lea     rax, WPP_GLOBAL_Control
0x180045098  cmp     rcx, rax
0x18004509b  jz      loc_180044E13
0x1800450a1  test    [rcx+1Ch], r15b
0x1800450a5  jz      loc_180044E13
0x1800450ab  mov     edx, 33h ; '3'
0x1800450b0  jmp     loc_180044F9A
0x1800450b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800450bc  lea     rax, WPP_GLOBAL_Control
0x1800450c3  cmp     rcx, rax
0x1800450c6  jz      loc_180044E13
0x1800450cc  test    byte ptr [rcx+1Ch], 1
0x1800450d0  jz      loc_180044E13
0x1800450d6  mov     edx, 34h ; '4'
0x1800450db  jmp     loc_180044F9A
0x1800450e0  mov     [rax], r15d
0x1800450e3  jmp     loc_180044DFE
0x1800450e8  mov     eax, cs:dword_18012C524
0x1800450ee  lea     r8, xmmword_18012C5B0
0x1800450f5  mov     [rsp+180h+var_150], eax
0x1800450f9  lea     rdx, xmmword_18012C568
0x180045100  lea     rax, qword_18012C5F8
0x180045107  mov     r9, r14
0x18004510a  mov     [rsp+180h+var_158], rax
0x18004510f  mov     [rsp+180h+var_160], rsi
0x180045114  call    FwEventHttpProxyChanged
0x180045119  jmp     loc_180044E13
```
