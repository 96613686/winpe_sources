# FwHttpProxyConglomerateProxyAddresses(FW_EVENT_HTTP_PROXY_CHANGE_TYPE_,int *)

- ea: `0x180045e40`
- end: `0x180046333`
- name: `?FwHttpProxyConglomerateProxyAddresses@@YAKW4FW_EVENT_HTTP_PROXY_CHANGE_TYPE_@@PEAH@Z`
- size: `1267`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045970`
- `0x180059c08`
- `0x1800ac24c`

## callees

- `0x18000a710`
- `0x180045e40`
- `0x18004633c`
- `0x18006b578`
- `0x1800729c0`
- `0x180073488`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180046036`
- `fwbase!FwHResultToWindowsError` at `0x1800460d4`
- `fwbase!FwHResultToWindowsError` at `0x1800461cf`
- `fwbase!FwHResultToWindowsError` at `0x180046036`
- `fwbase!FwHResultToWindowsError` at `0x1800460d4`
- `fwbase!FwHResultToWindowsError` at `0x1800461cf`
- `fwbase!FwSortAddresses` at `0x180045f19`
- `fwbase!FwSortAddresses` at `0x1800460ee`
- `fwbase!FwSortAddresses` at `0x180046132`
- `fwbase!FwSortAddresses` at `0x180045f19`
- `fwbase!FwSortAddresses` at `0x1800460ee`
- `fwbase!FwSortAddresses` at `0x180046132`
- `fwbase!FwCriticalSectionEnter` at `0x180045eb1`
- `fwbase!FwCriticalSectionEnter` at `0x180045eb1`
- `fwbase!FwCriticalSectionLeave` at `0x180045fda`
- `fwbase!FwCriticalSectionLeave` at `0x180045fda`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x180045f42`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x180045f42`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180045f2a`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x1800460fe`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x180045f2a`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x1800460fe`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18004614c`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18004614c`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180046028`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x1800461c1`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180046028`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x1800461c1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045ec4`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045f5f`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046051`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004615c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046214`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045ec4`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180045f5f`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046051`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004615c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046214`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800460c6`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800460c6`

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
  v3 = dword_1801326F8;
  FwCriticalSectionEnter(qword_180132708);
  FwPolioEmptyWFAddresses(&xmmword_180132780);
  v4 = 0;
  v5 = 1;
  v6 = v3;
  while ( 1 )
  {
    if ( v4 >= dword_1801326F8 )
    {
      v8 = v29;
      v9 = v29;
      FwSortAddresses(&v19);
      FwRemoveDuplicateAddresses(&v19);
      if ( (unsigned int)IsEqualAddresses(&xmmword_180132738, &v19) == 1 )
      {
        v5 = 0;
        FwPolioEmptyWFAddresses(&v19);
        v19 = xmmword_180132738;
        v20 = *(_OWORD *)&qword_180132748;
        v21 = xmmword_180132758;
        v23 = qword_180132778;
        v22 = *(_OWORD *)&qword_180132768;
      }
      else
      {
        FwPolioEmptyWFAddresses(&xmmword_180132738);
        xmmword_180132738 = v19;
        xmmword_180132758 = v21;
        *(_OWORD *)&qword_180132748 = v20;
        qword_180132778 = v23;
        *(_OWORD *)&qword_180132768 = v22;
      }
      if ( v3 == v4 )
        goto LABEL_10;
      v12 = 120LL * v3;
      v8 = (_BYTE *)(v12 + qword_180132700 + 32);
      if ( dword_1801326F4 == 1 )
      {
        v13 = FwPolioCopyWFAddressesContents(v12 + qword_180132700 + 32, &v24);
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
        v16 = FwUniteWFAddressesContents(&v19, v12 + qword_180132700 + 32, &v24);
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
        xmmword_180132780 = v24;
        xmmword_1801327A0 = v26;
        *(_OWORD *)byte_180132790 = v25;
        qword_1801327C0 = v28;
        *(_OWORD *)byte_1801327B0 = v27;
      }
      else
      {
        v9 = (_BYTE *)(120LL * v6 + qword_180132700 + 32);
        qword_180132818 = (__int64)v9;
        FwSortAddresses(v9);
        FwSubtractAddresses(&v24, v9, &xmmword_180132780);
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
            (__int64)&xmmword_180132738,
            (__int64)&xmmword_180132780,
            (__int64)v8,
            (__int64)v9,
            (__int64)qword_1801327C8,
            dword_1801326F4);
        goto LABEL_14;
      }
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v15 = 54;
LABEL_26:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids, v2);
      goto LABEL_14;
    }
    v7 = 120LL * v4;
    if ( (*(_BYTE *)(v7 + qword_180132700 + 104) & 8) != 0 )
    {
      v3 = v4;
      goto LABEL_6;
    }
    if ( (*(_BYTE *)(v7 + qword_180132700 + 104) & 0x10) != 0 )
    {
      v6 = v4;
      goto LABEL_6;
    }
    v11 = FwUniteWFAddressesContents(&v19, v7 + qword_180132700 + 32, &v24);
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
  FwCriticalSectionLeave(qword_180132708);
  return v2;
}

```

## disassembly

```asm
0x180045e40  mov     [rsp-8+arg_10], rbx
0x180045e45  push    rbp
0x180045e46  push    rsi
0x180045e47  push    rdi
0x180045e48  push    r12
0x180045e4a  push    r13
0x180045e4c  push    r14
0x180045e4e  push    r15
0x180045e50  lea     rbp, [rsp-50h]
0x180045e55  sub     rsp, 150h
0x180045e5c  mov     rax, cs:__security_cookie
0x180045e63  xor     rax, rsp
0x180045e66  mov     [rbp+80h+var_40], rax
0x180045e6a  mov     [rsp+180h+var_138], rdx
0x180045e6f  xor     ebx, ebx
0x180045e71  mov     [rsp+180h+var_140], ecx
0x180045e75  xor     edx, edx; Val
0x180045e77  lea     rcx, [rsp+180h+var_130]; void *
0x180045e7c  lea     esi, [rbx+48h]
0x180045e7f  mov     r8d, esi; Size
0x180045e82  call    memset_0
0x180045e87  mov     r8d, esi; Size
0x180045e8a  lea     rcx, [rbp+80h+var_E0]; void *
0x180045e8e  xor     edx, edx; Val
0x180045e90  call    memset_0
0x180045e95  mov     r8d, esi; Size
0x180045e98  lea     rcx, [rbp+80h+var_90]; void *
0x180045e9c  xor     edx, edx; Val
0x180045e9e  call    memset_0
0x180045ea3  mov     r12d, cs:dword_1801326F8
0x180045eaa  lea     rcx, qword_180132708
0x180045eb1  call    cs:__imp_FwCriticalSectionEnter
0x180045eb8  nop     dword ptr [rax+rax+00h]
0x180045ebd  lea     rcx, xmmword_180132780
0x180045ec4  call    cs:__imp_FwPolioEmptyWFAddresses
0x180045ecb  nop     dword ptr [rax+rax+00h]
0x180045ed0  xor     edi, edi
0x180045ed2  lea     r15d, [rbx+1]
0x180045ed6  mov     r13d, r12d
0x180045ed9  cmp     edi, cs:dword_1801326F8
0x180045edf  jnb     short loc_180045F0C
0x180045ee1  mov     eax, edi
0x180045ee3  imul    rcx, rax, 78h ; 'x'
0x180045ee7  mov     rax, cs:qword_180132700
0x180045eee  test    byte ptr [rcx+rax+68h], 8
0x180045ef3  jnz     loc_180046010
0x180045ef9  test    byte ptr [rcx+rax+68h], 10h
0x180045efe  jz      loc_180046018
0x180045f04  mov     r13d, edi
0x180045f07  add     edi, r15d
0x180045f0a  jmp     short loc_180045ED9
0x180045f0c  lea     rcx, [rsp+180h+var_130]
0x180045f11  lea     r14, [rbp+80h+var_90]
0x180045f15  lea     rsi, [rbp+80h+var_90]
0x180045f19  call    cs:__imp_FwSortAddresses
0x180045f20  nop     dword ptr [rax+rax+00h]
0x180045f25  lea     rcx, [rsp+180h+var_130]
0x180045f2a  call    cs:__imp_FwRemoveDuplicateAddresses
0x180045f31  nop     dword ptr [rax+rax+00h]
0x180045f36  lea     rdx, [rsp+180h+var_130]
0x180045f3b  lea     rcx, xmmword_180132738
0x180045f42  call    cs:__imp_IsEqualAddresses
0x180045f49  nop     dword ptr [rax+rax+00h]
0x180045f4e  cmp     eax, r15d
0x180045f51  jnz     loc_18004620D
0x180045f57  xor     r15d, r15d
0x180045f5a  lea     rcx, [rsp+180h+var_130]
0x180045f5f  call    cs:__imp_FwPolioEmptyWFAddresses
0x180045f66  nop     dword ptr [rax+rax+00h]
0x180045f6b  movups  xmm0, cs:xmmword_180132738
0x180045f72  movups  xmm1, xmmword ptr cs:qword_180132748
0x180045f79  movaps  [rsp+180h+var_130], xmm0
0x180045f7e  movups  xmm0, cs:xmmword_180132758
0x180045f85  movaps  [rsp+180h+var_120], xmm1
0x180045f8a  movups  xmm1, xmmword ptr cs:qword_180132768
0x180045f91  movaps  [rsp+180h+var_110], xmm0
0x180045f96  movsd   xmm0, cs:qword_180132778
0x180045f9e  movsd   [rbp+80h+var_F0], xmm0
0x180045fa3  movaps  [rbp+80h+var_100], xmm1
0x180045fa7  cmp     r12d, edi
0x180045faa  jnz     loc_18004609D
0x180045fb0  mov     rax, [rsp+180h+var_138]
0x180045fb5  test    rax, rax
0x180045fb8  jnz     loc_1800462F5
0x180045fbe  mov     ecx, [rsp+180h+var_140]
0x180045fc2  test    r15d, r15d
0x180045fc5  jnz     loc_1800462FD
0x180045fcb  test    ecx, ecx
0x180045fcd  jz      loc_1800462FD
0x180045fd3  lea     rcx, qword_180132708
0x180045fda  call    cs:__imp_FwCriticalSectionLeave
0x180045fe1  nop     dword ptr [rax+rax+00h]
0x180045fe6  mov     eax, ebx
0x180045fe8  mov     rcx, [rbp+80h+var_40]
0x180045fec  xor     rcx, rsp; StackCookie
0x180045fef  call    __security_check_cookie
0x180045ff4  mov     rbx, [rsp+180h+arg_10]
0x180045ffc  add     rsp, 150h
0x180046003  pop     r15
0x180046005  pop     r14
0x180046007  pop     r13
0x180046009  pop     r12
0x18004600b  pop     rdi
0x18004600c  pop     rsi
0x18004600d  pop     rbp
0x18004600e  retn
0x180046010  mov     r12d, edi
0x180046013  jmp     loc_180045F07
0x180046018  lea     rdx, [rax+20h]
0x18004601c  add     rdx, rcx
0x18004601f  lea     r8, [rbp+80h+var_E0]
0x180046023  lea     rcx, [rsp+180h+var_130]
0x180046028  call    cs:__imp_FwUniteWFAddressesContents
0x18004602f  nop     dword ptr [rax+rax+00h]
0x180046034  mov     ecx, eax
0x180046036  call    cs:__imp_FwHResultToWindowsError
0x18004603d  nop     dword ptr [rax+rax+00h]
0x180046042  mov     ebx, eax
0x180046044  test    eax, eax
0x180046046  jnz     loc_18004629F
0x18004604c  lea     rcx, [rsp+180h+var_130]
0x180046051  call    cs:__imp_FwPolioEmptyWFAddresses
0x180046058  nop     dword ptr [rax+rax+00h]
0x18004605d  movaps  xmm0, [rbp+80h+var_E0]
0x180046061  lea     rcx, [rbp+80h+var_E0]; void *
0x180046065  movaps  xmm1, [rbp+80h+var_D0]
0x180046069  mov     r8, rsi; Size
0x18004606c  movaps  [rsp+180h+var_130], xmm0
0x180046071  xor     edx, edx; Val
0x180046073  movaps  xmm0, [rbp+80h+var_C0]
0x180046077  movaps  [rsp+180h+var_110], xmm0
0x18004607c  movsd   xmm0, [rbp+80h+var_A0]
0x180046081  movaps  [rsp+180h+var_120], xmm1
0x180046086  movaps  xmm1, [rbp+80h+var_B0]
0x18004608a  movsd   [rbp+80h+var_F0], xmm0
0x18004608f  movaps  [rbp+80h+var_100], xmm1
0x180046093  call    memset_0
0x180046098  jmp     loc_180045F07
0x18004609d  mov     r14, cs:qword_180132700
0x1800460a4  add     r14, 20h ; ' '
0x1800460a8  mov     eax, r12d
0x1800460ab  imul    rcx, rax, 78h ; 'x'
0x1800460af  add     r14, rcx
0x1800460b2  cmp     cs:dword_1801326F4, 1
0x1800460b9  jnz     loc_1800461B5
0x1800460bf  lea     rdx, [rbp+80h+var_E0]
0x1800460c3  mov     rcx, r14
0x1800460c6  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800460cd  nop     dword ptr [rax+rax+00h]
0x1800460d2  mov     ecx, eax
0x1800460d4  call    cs:__imp_FwHResultToWindowsError
0x1800460db  nop     dword ptr [rax+rax+00h]
0x1800460e0  mov     ebx, eax
0x1800460e2  test    eax, eax
0x1800460e4  jnz     loc_1800462CA
0x1800460ea  lea     rcx, [rbp+80h+var_E0]
0x1800460ee  call    cs:__imp_FwSortAddresses
0x1800460f5  nop     dword ptr [rax+rax+00h]
0x1800460fa  lea     rcx, [rbp+80h+var_E0]
0x1800460fe  call    cs:__imp_FwRemoveDuplicateAddresses
0x180046105  nop     dword ptr [rax+rax+00h]
0x18004610a  cmp     r13d, edi
0x18004610d  jz      loc_180046261
0x180046113  mov     rsi, cs:qword_180132700
0x18004611a  mov     eax, r13d
0x18004611d  add     rsi, 20h ; ' '
0x180046121  imul    rcx, rax, 78h ; 'x'
0x180046125  add     rsi, rcx
0x180046128  mov     rcx, rsi
0x18004612b  mov     cs:qword_180132818, rsi
0x180046132  call    cs:__imp_FwSortAddresses
0x180046139  nop     dword ptr [rax+rax+00h]
0x18004613e  lea     r8, xmmword_180132780
0x180046145  mov     rdx, rsi
0x180046148  lea     rcx, [rbp+80h+var_E0]
0x18004614c  call    cs:__imp_FwSubtractAddresses
0x180046153  nop     dword ptr [rax+rax+00h]
0x180046158  lea     rcx, [rbp+80h+var_E0]
0x18004615c  call    cs:__imp_FwPolioEmptyWFAddresses
0x180046163  nop     dword ptr [rax+rax+00h]
0x180046168  call    ?FwHttpComputeDaNat64Proxies@@YAKXZ; FwHttpComputeDaNat64Proxies(void)
0x18004616d  mov     ebx, eax
0x18004616f  test    eax, eax
0x180046171  jz      loc_180045FB0
0x180046177  mov     rcx, cs:WPP_GLOBAL_Control
0x18004617e  lea     rax, WPP_GLOBAL_Control
0x180046185  cmp     rcx, rax
0x180046188  jz      loc_180045FD3
0x18004618e  test    byte ptr [rcx+1Ch], 1
0x180046192  jz      loc_180045FD3
0x180046198  mov     edx, 36h ; '6'
0x18004619d  mov     rcx, [rcx+10h]
0x1800461a1  lea     r8, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids
0x1800461a8  mov     r9d, ebx
0x1800461ab  call    WPP_SF_d
0x1800461b0  jmp     loc_180045FD3
0x1800461b5  lea     r8, [rbp+80h+var_E0]
0x1800461b9  mov     rdx, r14
0x1800461bc  lea     rcx, [rsp+180h+var_130]
0x1800461c1  call    cs:__imp_FwUniteWFAddressesContents
0x1800461c8  nop     dword ptr [rax+rax+00h]
0x1800461cd  mov     ecx, eax
0x1800461cf  call    cs:__imp_FwHResultToWindowsError
0x1800461d6  nop     dword ptr [rax+rax+00h]
0x1800461db  mov     ebx, eax
0x1800461dd  test    eax, eax
0x1800461df  jz      loc_1800460EA
0x1800461e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461ec  lea     rax, WPP_GLOBAL_Control
0x1800461f3  cmp     rcx, rax
0x1800461f6  jz      loc_180045FD3
0x1800461fc  test    byte ptr [rcx+1Ch], 1
0x180046200  jz      loc_180045FD3
0x180046206  mov     edx, 35h ; '5'
0x18004620b  jmp     short loc_18004619D
0x18004620d  lea     rcx, xmmword_180132738
0x180046214  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004621b  nop     dword ptr [rax+rax+00h]
0x180046220  movaps  xmm0, [rsp+180h+var_130]
0x180046225  movaps  xmm1, [rsp+180h+var_120]
0x18004622a  movups  cs:xmmword_180132738, xmm0
0x180046231  movaps  xmm0, [rsp+180h+var_110]
0x180046236  movups  cs:xmmword_180132758, xmm0
0x18004623d  movsd   xmm0, [rbp+80h+var_F0]
0x180046242  movups  xmmword ptr cs:qword_180132748, xmm1
0x180046249  movaps  xmm1, [rbp+80h+var_100]
0x18004624d  movsd   cs:qword_180132778, xmm0
0x180046255  movups  xmmword ptr cs:qword_180132768, xmm1
0x18004625c  jmp     loc_180045FA7
0x180046261  movaps  xmm0, [rbp+80h+var_E0]
0x180046265  movaps  xmm1, [rbp+80h+var_D0]
0x180046269  movaps  cs:xmmword_180132780, xmm0
0x180046270  movaps  xmm0, [rbp+80h+var_C0]
0x180046274  movaps  cs:xmmword_1801327A0, xmm0
0x18004627b  movsd   xmm0, [rbp+80h+var_A0]
0x180046280  movaps  xmmword ptr cs:byte_180132790, xmm1
0x180046287  movaps  xmm1, [rbp+80h+var_B0]
0x18004628b  movsd   cs:qword_1801327C0, xmm0
0x180046293  movaps  xmmword ptr cs:byte_1801327B0, xmm1
0x18004629a  jmp     loc_180046168
0x18004629f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462a6  lea     rax, WPP_GLOBAL_Control
0x1800462ad  cmp     rcx, rax
0x1800462b0  jz      loc_180045FD3
0x1800462b6  test    [rcx+1Ch], r15b
0x1800462ba  jz      loc_180045FD3
0x1800462c0  mov     edx, 33h ; '3'
0x1800462c5  jmp     loc_18004619D
0x1800462ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462d1  lea     rax, WPP_GLOBAL_Control
0x1800462d8  cmp     rcx, rax
0x1800462db  jz      loc_180045FD3
0x1800462e1  test    byte ptr [rcx+1Ch], 1
0x1800462e5  jz      loc_180045FD3
0x1800462eb  mov     edx, 34h ; '4'
0x1800462f0  jmp     loc_18004619D
0x1800462f5  mov     [rax], r15d
0x1800462f8  jmp     loc_180045FBE
0x1800462fd  mov     eax, cs:dword_1801326F4
0x180046303  lea     r8, xmmword_180132780
0x18004630a  mov     [rsp+180h+var_150], eax
0x18004630e  lea     rdx, xmmword_180132738
0x180046315  lea     rax, qword_1801327C8
0x18004631c  mov     r9, r14
0x18004631f  mov     [rsp+180h+var_158], rax
0x180046324  mov     [rsp+180h+var_160], rsi
0x180046329  call    FwEventHttpProxyChanged
0x18004632e  jmp     loc_180045FD3
```
