# details::IpsecSaMonitor::IpsecSaMonitor(void)

- ea: `0x1800620b0`
- end: `0x18006239a`
- name: `??0IpsecSaMonitor@details@@QEAA@XZ`
- size: `746`
- prototype: `HANDLE *__fastcall(HANDLE *engineHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004317c`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180013e48`
- `0x180047240`
- `0x1800620b0`
- `0x180062550`

## import_xrefs

- `fwpuclnt!IPsecSaContextSubscribe0` at `0x1800621b9`
- `fwpuclnt!IPsecSaContextSubscribe0` at `0x1800621b9`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18006220f`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18006220f`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800620ff`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800620ff`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180062369`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180062369`
- `fwpuclnt!FwpmFreeMemory0` at `0x180062319`
- `fwpuclnt!FwpmFreeMemory0` at `0x180062319`
- `fwpuclnt!IPsecSaEnum0` at `0x18006229d`
- `fwpuclnt!IPsecSaEnum0` at `0x18006229d`

## pseudocode

```c
HANDLE *__fastcall details::IpsecSaMonitor::IpsecSaMonitor(HANDLE *engineHandle)
{
  HANDLE *v2; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rcx
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  __int64 v9; // rdi
  UINT32 i; // edx
  IPSEC_SA_DETAILS0 *v11; // rcx
  HANDLE enumHandle; // [rsp+38h] [rbp-48h] BYREF
  IPSEC_SA_DETAILS0 **entries; // [rsp+40h] [rbp-40h] BYREF
  UINT32 numEntriesReturned; // [rsp+48h] [rbp-38h] BYREF
  _OWORD v16[2]; // [rsp+50h] [rbp-30h] BYREF

  *engineHandle = 0;
  v2 = engineHandle + 1;
  engineHandle[1] = 0;
  v3 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, engineHandle);
  v4 = v3;
  if ( !v3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_77da375421113a5acb694f369a925659_Traceguids);
    }
    memset(v16, 0, sizeof(v16));
    v6 = IPsecSaContextSubscribe0(
           *engineHandle,
           v16,
           details::IpsecSaMonitor::IpsecSaContextCallbackThunk,
           engineHandle,
           v2);
    v4 = v6;
    v5 = WPP_GLOBAL_Control;
    if ( v6
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_77da375421113a5acb694f369a925659_Traceguids, v6);
      enumHandle = 0;
    }
    else
    {
      enumHandle = 0;
      if ( v6 )
        goto LABEL_23;
      v7 = IPsecSaCreateEnumHandle0(*engineHandle, 0, &enumHandle);
      v4 = v7;
      if ( v7 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) == 0
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 3u )
        {
          goto LABEL_23;
        }
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_77da375421113a5acb694f369a925659_Traceguids, v7);
      }
    }
    v5 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_77da375421113a5acb694f369a925659_Traceguids, v3);
    v5 = WPP_GLOBAL_Control;
  }
  enumHandle = 0;
LABEL_23:
  while ( !v4 )
  {
    if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && (*(_DWORD *)(v5 + 28) & 0x100) != 0 && *(_BYTE *)(v5 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v5 + 16), 18, WPP_77da375421113a5acb694f369a925659_Traceguids);
    numEntriesReturned = 0;
    entries = 0;
    v8 = IPsecSaEnum0(*engineHandle, enumHandle, 0x40u, &entries, &numEntriesReturned);
    v4 = v8;
    if ( v8 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 3u )
      {
        goto LABEL_43;
      }
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_77da375421113a5acb694f369a925659_Traceguids, v8);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x100) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_dd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v8 + 19,
          WPP_77da375421113a5acb694f369a925659_Traceguids,
          numEntriesReturned,
          64);
      }
      v9 = 0;
      for ( i = numEntriesReturned; (unsigned int)v9 < i; v9 = (unsigned int)(v9 + 1) )
      {
        v11 = entries[v9];
        if ( v11->ipVersion == FWP_IP_VERSION_V6 )
        {
          details::OnIpsecSaAddedCallback(v11->saBundle.mmSaId, v11->saDirection, &v11->traffic);
          i = numEntriesReturned;
        }
      }
      FwpmFreeMemory0((void **)&entries);
    }
    v5 = WPP_GLOBAL_Control;
LABEL_43:
    if ( numEntriesReturned < 0x40 )
      break;
  }
  if ( enumHandle )
    IPsecSaDestroyEnumHandle0(*engineHandle, enumHandle);
  return engineHandle;
}

```

## disassembly

```asm
0x1800620b0  mov     [rsp-28h+arg_8], rbx
0x1800620b5  mov     [rsp-28h+arg_10], rsi
0x1800620ba  push    rbp
0x1800620bb  push    rdi
0x1800620bc  push    r12
0x1800620be  push    r14
0x1800620c0  push    r15
0x1800620c2  mov     rbp, rsp
0x1800620c5  sub     rsp, 80h
0x1800620cc  mov     rax, cs:__security_cookie
0x1800620d3  xor     rax, rsp
0x1800620d6  mov     [rbp+var_10], rax
0x1800620da  mov     r15, rcx
0x1800620dd  mov     qword ptr [rcx], 0
0x1800620e4  lea     rdi, [rcx+8]
0x1800620e8  mov     qword ptr [rdi], 0
0x1800620ef  mov     [rsp+80h+engineHandle], rcx; engineHandle
0x1800620f4  xor     r9d, r9d; session
0x1800620f7  xor     r8d, r8d; authIdentity
0x1800620fa  or      edx, 0FFFFFFFFh; authnService
0x1800620fd  xor     ecx, ecx; serverName
0x1800620ff  call    cs:__imp_FwpmEngineOpen0
0x180062105  mov     ebx, eax
0x180062107  test    eax, eax
0x180062109  jz      short loc_18006215D
0x18006210b  lea     r14, WPP_GLOBAL_Control
0x180062112  lea     r12, WPP_77da375421113a5acb694f369a925659_Traceguids
0x180062119  mov     esi, 100h
0x18006211e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062125  cmp     rcx, r14
0x180062128  jz      short loc_180062150
0x18006212a  test    [rcx+1Ch], esi
0x18006212d  jz      short loc_180062150
0x18006212f  cmp     byte ptr [rcx+19h], 3
0x180062133  jb      short loc_180062150
0x180062135  mov     edx, 0Eh
0x18006213a  mov     r9d, eax
0x18006213d  mov     r8, r12
0x180062140  mov     rcx, [rcx+10h]
0x180062144  call    WPP_SF_d
0x180062149  mov     rcx, cs:WPP_GLOBAL_Control
0x180062150  mov     [rbp+enumHandle], 0
0x180062158  jmp     loc_18006224D
0x18006215d  lea     r14, WPP_GLOBAL_Control
0x180062164  lea     r12, WPP_77da375421113a5acb694f369a925659_Traceguids
0x18006216b  mov     esi, 100h
0x180062170  mov     rcx, cs:WPP_GLOBAL_Control
0x180062177  cmp     rcx, r14
0x18006217a  jz      short loc_180062198
0x18006217c  test    [rcx+1Ch], esi
0x18006217f  jz      short loc_180062198
0x180062181  cmp     byte ptr [rcx+19h], 5
0x180062185  jb      short loc_180062198
0x180062187  mov     edx, 0Fh
0x18006218c  mov     r8, r12
0x18006218f  mov     rcx, [rcx+10h]
0x180062193  call    WPP_SF_
0x180062198  xorps   xmm0, xmm0
0x18006219b  movups  [rbp+var_30], xmm0
0x18006219f  movups  [rbp+var_20], xmm0
0x1800621a3  mov     [rsp+80h+engineHandle], rdi
0x1800621a8  mov     r9, r15
0x1800621ab  lea     r8, ?IpsecSaContextCallbackThunk@IpsecSaMonitor@details@@CAXPEAXPEBUIPSEC_SA_CONTEXT_CHANGE0_@@@Z; details::IpsecSaMonitor::IpsecSaContextCallbackThunk(void *,IPSEC_SA_CONTEXT_CHANGE0_ const *)
0x1800621b2  lea     rdx, [rbp+var_30]
0x1800621b6  mov     rcx, [r15]
0x1800621b9  call    cs:__imp_IPsecSaContextSubscribe0
0x1800621bf  mov     ebx, eax
0x1800621c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621c8  test    eax, eax
0x1800621ca  jz      short loc_1800621FA
0x1800621cc  cmp     rcx, r14
0x1800621cf  jz      short loc_1800621FA
0x1800621d1  test    [rcx+1Ch], esi
0x1800621d4  jz      short loc_1800621FA
0x1800621d6  cmp     byte ptr [rcx+19h], 3
0x1800621da  jb      short loc_1800621FA
0x1800621dc  mov     edx, 10h
0x1800621e1  mov     r9d, eax
0x1800621e4  mov     r8, r12
0x1800621e7  mov     rcx, [rcx+10h]
0x1800621eb  call    WPP_SF_d
0x1800621f0  mov     [rbp+enumHandle], 0
0x1800621f8  jmp     short loc_180062246
0x1800621fa  mov     [rbp+enumHandle], 0
0x180062202  test    eax, eax
0x180062204  jnz     short loc_18006224D
0x180062206  lea     r8, [rbp+enumHandle]; enumHandle
0x18006220a  xor     edx, edx; enumTemplate
0x18006220c  mov     rcx, [r15]; engineHandle
0x18006220f  call    cs:__imp_IPsecSaCreateEnumHandle0
0x180062215  mov     ebx, eax
0x180062217  test    eax, eax
0x180062219  jz      short loc_180062246
0x18006221b  mov     rcx, cs:WPP_GLOBAL_Control
0x180062222  cmp     rcx, r14
0x180062225  jz      short loc_18006224D
0x180062227  test    [rcx+1Ch], esi
0x18006222a  jz      short loc_18006224D
0x18006222c  cmp     byte ptr [rcx+19h], 3
0x180062230  jb      short loc_18006224D
0x180062232  mov     edx, 11h
0x180062237  mov     r9d, eax
0x18006223a  mov     r8, r12
0x18006223d  mov     rcx, [rcx+10h]
0x180062241  call    WPP_SF_d
0x180062246  mov     rcx, cs:WPP_GLOBAL_Control
0x18006224d  test    ebx, ebx
0x18006224f  jnz     loc_18006235D
0x180062255  cmp     rcx, r14
0x180062258  jz      short loc_180062274
0x18006225a  test    [rcx+1Ch], esi
0x18006225d  jz      short loc_180062274
0x18006225f  cmp     byte ptr [rcx+19h], 5
0x180062263  jb      short loc_180062274
0x180062265  lea     edx, [rbx+12h]
0x180062268  mov     r8, r12
0x18006226b  mov     rcx, [rcx+10h]
0x18006226f  call    WPP_SF_
0x180062274  mov     [rbp+numEntriesReturned], 0
0x18006227b  mov     [rbp+entries], 0
0x180062283  lea     rax, [rbp+numEntriesReturned]
0x180062287  mov     [rsp+80h+engineHandle], rax; numEntriesReturned
0x18006228c  lea     r9, [rbp+entries]; entries
0x180062290  mov     r8d, 40h ; '@'; numEntriesRequested
0x180062296  mov     rdx, [rbp+enumHandle]; enumHandle
0x18006229a  mov     rcx, [r15]; engineHandle
0x18006229d  call    cs:__imp_IPsecSaEnum0
0x1800622a3  mov     ebx, eax
0x1800622a5  test    eax, eax
0x1800622a7  jnz     short loc_180062321
0x1800622a9  lea     rax, [rbp+entries]
0x1800622ad  mov     [rbp+var_50], rax
0x1800622b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800622b8  cmp     rcx, r14
0x1800622bb  jz      short loc_1800622E3
0x1800622bd  test    [rcx+1Ch], esi
0x1800622c0  jz      short loc_1800622E3
0x1800622c2  cmp     byte ptr [rcx+19h], 5
0x1800622c6  jb      short loc_1800622E3
0x1800622c8  lea     edx, [rbx+13h]
0x1800622cb  mov     dword ptr [rsp+80h+engineHandle], 40h ; '@'
0x1800622d3  mov     r9d, [rbp+numEntriesReturned]
0x1800622d7  mov     r8, r12
0x1800622da  mov     rcx, [rcx+10h]
0x1800622de  call    WPP_SF_dd
0x1800622e3  xor     edi, edi
0x1800622e5  mov     edx, [rbp+numEntriesReturned]
0x1800622e8  test    edx, edx
0x1800622ea  jz      short loc_180062315
0x1800622ec  mov     rax, [rbp+entries]
0x1800622f0  mov     rcx, [rax+rdi*8]
0x1800622f4  cmp     dword ptr [rcx], 1
0x1800622f7  jnz     short loc_18006230F
0x1800622f9  lea     r8, [rcx+8]; struct IPSEC_TRAFFIC0_ *
0x1800622fd  mov     edx, [rcx+4]; enum FWP_DIRECTION_
0x180062300  mov     rcx, [rcx+88h]; unsigned __int64
0x180062307  call    ?OnIpsecSaAddedCallback@details@@YAX_KW4FWP_DIRECTION_@@AEBUIPSEC_TRAFFIC0_@@@Z; details::OnIpsecSaAddedCallback(unsigned __int64,FWP_DIRECTION_,IPSEC_TRAFFIC0_ const &)
0x18006230c  mov     edx, [rbp+numEntriesReturned]
0x18006230f  inc     edi
0x180062311  cmp     edi, edx
0x180062313  jb      short loc_1800622EC
0x180062315  lea     rcx, [rbp+entries]; p
0x180062319  call    cs:__imp_FwpmFreeMemory0
0x18006231f  jmp     short loc_18006234C
0x180062321  mov     rcx, cs:WPP_GLOBAL_Control
0x180062328  cmp     rcx, r14
0x18006232b  jz      short loc_180062353
0x18006232d  test    [rcx+1Ch], esi
0x180062330  jz      short loc_180062353
0x180062332  cmp     byte ptr [rcx+19h], 3
0x180062336  jb      short loc_180062353
0x180062338  mov     edx, 14h
0x18006233d  mov     r9d, eax
0x180062340  mov     r8, r12
0x180062343  mov     rcx, [rcx+10h]
0x180062347  call    WPP_SF_d
0x18006234c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062353  cmp     [rbp+numEntriesReturned], 40h ; '@'
0x180062357  jnb     loc_18006224D
0x18006235d  mov     rdx, [rbp+enumHandle]; enumHandle
0x180062361  test    rdx, rdx
0x180062364  jz      short loc_18006236F
0x180062366  mov     rcx, [r15]; engineHandle
0x180062369  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18006236f  mov     rax, r15
0x180062372  mov     rcx, [rbp+var_10]
0x180062376  xor     rcx, rsp; StackCookie
0x180062379  call    __security_check_cookie
0x18006237e  lea     r11, [rsp+80h+var_s0]
0x180062386  mov     rbx, [r11+38h]
0x18006238a  mov     rsi, [r11+40h]
0x18006238e  mov     rsp, r11
0x180062391  pop     r15
0x180062393  pop     r14
0x180062395  pop     r12
0x180062397  pop     rdi
0x180062398  pop     rbp
0x180062399  retn
```
