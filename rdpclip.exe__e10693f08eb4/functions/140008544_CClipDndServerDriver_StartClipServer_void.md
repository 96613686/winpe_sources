# CClipDndServerDriver::StartClipServer(void)

- ea: `0x140008544`
- end: `0x140008a83`
- name: `?StartClipServer@CClipDndServerDriver@@IEAAJXZ`
- size: `1343`
- prototype: `__int64 __fastcall(CClipDndServerDriver *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140006568`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x140007ddc`
- `0x1400081d0`
- `0x140008544`
- `0x1400096d8`
- `0x1400099ac`
- `0x14003f2e4`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400088d6`
- `USER32!LoadStringW` at `0x1400088d6`
- `WINSTA!WinStationFreePropertyValue` at `0x140008679`
- `WINSTA!WinStationFreePropertyValue` at `0x140008741`
- `WINSTA!WinStationFreePropertyValue` at `0x140008679`
- `WINSTA!WinStationFreePropertyValue` at `0x140008741`
- `WINSTA!WinStationQueryInformationW` at `0x140008621`
- `WINSTA!WinStationQueryInformationW` at `0x140008621`
- `WINSTA!WinStationGetConnectionProperty` at `0x14000865b`
- `WINSTA!WinStationGetConnectionProperty` at `0x140008693`
- `WINSTA!WinStationGetConnectionProperty` at `0x14000865b`
- `WINSTA!WinStationGetConnectionProperty` at `0x140008693`

## string_xrefs

- `0x140008810`: `CServerDynamicVirtualChannel::CreateInstance failed!`
- `0x140008855`: `CServerStaticVirtualChannel::CreateInstance failed!`
- `0x1400088a1`: `CClipServer::CreateInstance failed!`

## pseudocode

```c
__int64 __fastcall CClipDndServerDriver::StartClipServer(CClipDndServerDriver *this)
{
  _QWORD *v1; // r13
  PVOID *v3; // rax
  int Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // r12d
  BOOL v7; // ebx
  unsigned int v8; // r14d
  CClipDndServerDriver *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  const char *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // r9
  HINSTANCE v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v27[7]; // [rsp+51h] [rbp-AFh] BYREF
  struct IRDPVirtualChannel *v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v33; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[124]; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+10Ch] [rbp+Ch]
  unsigned int v36; // [rsp+110h] [rbp+10h]
  WCHAR Buffer[128]; // [rsp+B00h] [rbp+A00h] BYREF

  v1 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    Instance = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)Instance;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_67;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids,
      CurrentThreadActivityIdPrefix);
LABEL_66:
    v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_67:
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v22);
    }
    return (unsigned int)Instance;
  }
  memset_0(v34, 0, 0xA68u);
  v31 = 0;
  v27[0] = -1;
  v26 = -1;
  v6 = 0;
  v33 = 0;
  if ( (unsigned __int8)WinStationQueryInformationW(0, 0xFFFFFFFFLL, 1, v34, 2664, &v31) )
  {
    v7 = ((v36 >> 1) & 1) == 0;
    if ( (v35 & 0x40000000) == 0 )
    {
      v8 = 1;
      goto LABEL_11;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = 0;
LABEL_11:
  v32 = 0;
  if ( (unsigned __int8)WinStationGetConnectionProperty(0xFFFFFFFFLL, PROPERTY_TYPE_CORRELATIONID_GUID, &v32) )
  {
    if ( *(_WORD *)v32 == 4 )
      v33 = *(struct _GUID *)(v32 + 8);
    WinStationFreePropertyValue();
  }
  v30 = 0;
  if ( (unsigned __int8)WinStationGetConnectionProperty(0xFFFFFFFFLL, PROPERTY_TYPE_GET_STACK_REPLACE_SVC, &v30) )
  {
    if ( *(_WORD *)v30 == 1 )
    {
      v6 = *(_DWORD *)(v30 + 8);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v10, v6);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v11);
    }
    WinStationFreePropertyValue();
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v12);
  }
  CClipDndServerDriver::QueryClipboardRestrictionLevels(v9, &v33, v27, &v26);
  if ( !v7 )
  {
    Instance = 1;
    goto LABEL_66;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  v28 = 0;
  v29 = 0;
  if ( v6 )
  {
    Instance = CServerDynamicVirtualChannel::CreateInstance(v13, &v28);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 39;
      v17 = "CServerDynamicVirtualChannel::CreateInstance failed!";
LABEL_58:
      LODWORD(v25) = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids,
        v15,
        (__int64)v17,
        v25);
LABEL_59:
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v29);
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v28);
      return (unsigned int)Instance;
    }
  }
  else
  {
    Instance = CServerStaticVirtualChannel::CreateInstance(v13, &v28);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 40;
      v17 = "CServerStaticVirtualChannel::CreateInstance failed!";
      goto LABEL_58;
    }
  }
  Instance = CRDPClipboardSharer_CreateInstance(*((_QWORD *)this + 9), v14, v1);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 41;
    v17 = "CClipServer::CreateInstance failed!";
    goto LABEL_58;
  }
  if ( v8 )
  {
    v19 = (HINSTANCE)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 48LL))(*((_QWORD *)this + 9));
    if ( !LoadStringW(v19, 0x64u, Buffer, 128)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v20);
    }
  }
  LOBYTE(v24) = v26;
  LOBYTE(v18) = v27[0];
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct IRDPVirtualChannel *, _QWORD, __int64, int, struct _GUID *, WCHAR *, _QWORD))(*(_QWORD *)*v1 + 24LL))(
               *v1,
               v28,
               v8,
               v18,
               v24,
               &v33,
               Buffer,
               0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 43;
    v17 = "CClipServer::InitializeInstance failed!";
    goto LABEL_58;
  }
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v29);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v28);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids, v21);
  }
  return 0;
}

```

## disassembly

```asm
0x140008544  push    rbp
0x140008546  push    rbx
0x140008547  push    rsi
0x140008548  push    rdi
0x140008549  push    r12
0x14000854b  push    r13
0x14000854d  push    r14
0x14000854f  push    r15
0x140008551  lea     rbp, [rsp-0B18h]
0x140008559  sub     rsp, 0C18h
0x140008560  mov     rax, cs:__security_cookie
0x140008567  xor     rax, rsp
0x14000856a  mov     [rbp+0B50h+var_50], rax
0x140008571  lea     r13, [rcx+50h]
0x140008575  xor     edi, edi
0x140008577  mov     r15, rcx
0x14000857a  cmp     [r13+0], rdi
0x14000857e  jz      short loc_1400085D7
0x140008580  mov     rax, cs:WPP_GLOBAL_Control
0x140008587  lea     esi, [rdi+1]
0x14000858a  lea     rdi, WPP_GLOBAL_Control
0x140008591  mov     ebx, esi
0x140008593  cmp     rax, rdi
0x140008596  jz      loc_140008A5E
0x14000859c  test    [rax+1Ch], sil
0x1400085a0  jz      loc_140008A29
0x1400085a6  cmp     byte ptr [rax+19h], 3
0x1400085aa  jb      loc_140008A29
0x1400085b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400085b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085bc  lea     edx, [rsi+2Bh]
0x1400085bf  mov     r9d, eax
0x1400085c2  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x1400085c9  mov     rcx, [rcx+10h]
0x1400085cd  call    WPP_SF_d
0x1400085d2  jmp     loc_140008A22
0x1400085d7  mov     ebx, 0A68h
0x1400085dc  lea     rcx, [rbp+0B50h+var_BC0]; void *
0x1400085e0  mov     r8d, ebx; Size
0x1400085e3  xor     edx, edx; Val
0x1400085e5  call    memset_0
0x1400085ea  lea     rax, [rsp+0C50h+var_BE0]
0x1400085ef  mov     [rsp+0C50h+var_BE0], edi
0x1400085f3  xorps   xmm0, xmm0
0x1400085f6  mov     [rsp+0C50h+var_C28], rax
0x1400085fb  mov     esi, 1
0x140008600  mov     dword ptr [rsp+0C50h+var_C30], ebx
0x140008604  lea     r9, [rbp+0B50h+var_BC0]
0x140008608  mov     [rsp+0C50h+var_BFF], 0FFh
0x14000860d  mov     r8d, esi
0x140008610  mov     [rsp+0C50h+var_C00], 0FFh
0x140008615  or      edx, 0FFFFFFFFh
0x140008618  xor     ecx, ecx
0x14000861a  mov     r12d, edi
0x14000861d  movups  xmmword ptr [rbp+0B50h+var_BD0.Data1], xmm0
0x140008621  call    cs:__imp_WinStationQueryInformationW
0x140008627  test    al, al
0x140008629  jz      short loc_140008642
0x14000862b  mov     ebx, [rbp+0B50h+var_B40]
0x14000862e  shr     ebx, 1
0x140008630  not     ebx
0x140008632  and     ebx, esi
0x140008634  test    [rbp+0B50h+var_B44], 40000000h
0x14000863b  jnz     short loc_140008644
0x14000863d  mov     r14d, esi
0x140008640  jmp     short loc_140008647
0x140008642  mov     ebx, edi
0x140008644  mov     r14d, edi
0x140008647  lea     r8, [rsp+0C50h+var_BD8]
0x14000864c  mov     [rsp+0C50h+var_BD8], rdi
0x140008651  lea     rdx, PROPERTY_TYPE_CORRELATIONID_GUID
0x140008658  or      ecx, 0FFFFFFFFh
0x14000865b  call    cs:__imp_WinStationGetConnectionProperty
0x140008661  test    al, al
0x140008663  jz      short loc_14000867F
0x140008665  mov     rcx, [rsp+0C50h+var_BD8]
0x14000866a  cmp     word ptr [rcx], 4
0x14000866e  jnz     short loc_140008679
0x140008670  movups  xmm0, xmmword ptr [rcx+8]
0x140008674  movdqu  xmmword ptr [rbp+0B50h+var_BD0.Data1], xmm0
0x140008679  call    cs:__imp_WinStationFreePropertyValue
0x14000867f  lea     r8, [rsp+0C50h+var_BE8]
0x140008684  mov     [rsp+0C50h+var_BE8], rdi
0x140008689  lea     rdx, PROPERTY_TYPE_GET_STACK_REPLACE_SVC
0x140008690  or      ecx, 0FFFFFFFFh
0x140008693  call    cs:__imp_WinStationGetConnectionProperty
0x140008699  test    al, al
0x14000869b  jz      loc_140008749
0x1400086a1  mov     rcx, [rsp+0C50h+var_BE8]
0x1400086a6  cmp     [rcx], si
0x1400086a9  jnz     short loc_1400086F9
0x1400086ab  mov     r12d, [rcx+8]
0x1400086af  mov     rax, cs:WPP_GLOBAL_Control
0x1400086b6  lea     rdi, WPP_GLOBAL_Control
0x1400086bd  cmp     rax, rdi
0x1400086c0  jz      short loc_140008741
0x1400086c2  test    [rax+1Ch], sil
0x1400086c6  jz      short loc_140008741
0x1400086c8  cmp     byte ptr [rax+19h], 4
0x1400086cc  jb      short loc_140008741
0x1400086ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400086d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086da  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x1400086e1  mov     edx, 24h ; '$'
0x1400086e6  mov     dword ptr [rsp+0C50h+var_C30], r12d
0x1400086eb  mov     r9d, eax
0x1400086ee  mov     rcx, [rcx+10h]
0x1400086f2  call    WPP_SF_Dd
0x1400086f7  jmp     short loc_14000873C
0x1400086f9  mov     rax, cs:WPP_GLOBAL_Control
0x140008700  lea     rdi, WPP_GLOBAL_Control
0x140008707  cmp     rax, rdi
0x14000870a  jz      short loc_140008741
0x14000870c  test    [rax+1Ch], sil
0x140008710  jz      short loc_140008741
0x140008712  cmp     byte ptr [rax+19h], 4
0x140008716  jb      short loc_140008741
0x140008718  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000871d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008724  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x14000872b  mov     edx, 25h ; '%'
0x140008730  mov     r9d, eax
0x140008733  mov     rcx, [rcx+10h]
0x140008737  call    WPP_SF_d
0x14000873c  mov     rcx, [rsp+0C50h+var_BE8]
0x140008741  call    cs:__imp_WinStationFreePropertyValue
0x140008747  jmp     short loc_14000878C
0x140008749  mov     rax, cs:WPP_GLOBAL_Control
0x140008750  lea     rdi, WPP_GLOBAL_Control
0x140008757  cmp     rax, rdi
0x14000875a  jz      short loc_14000878C
0x14000875c  test    [rax+1Ch], sil
0x140008760  jz      short loc_14000878C
0x140008762  cmp     byte ptr [rax+19h], 4
0x140008766  jb      short loc_14000878C
0x140008768  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000876d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008774  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x14000877b  mov     edx, 26h ; '&'
0x140008780  mov     r9d, eax
0x140008783  mov     rcx, [rcx+10h]
0x140008787  call    WPP_SF_d
0x14000878c  lea     r9, [rsp+0C50h+var_C00]; unsigned __int8 *
0x140008791  lea     r8, [rsp+0C50h+var_BFF]; unsigned __int8 *
0x140008796  lea     rdx, [rbp+0B50h+var_BD0]; struct _GUID *
0x14000879a  call    ?QueryClipboardRestrictionLevels@CClipDndServerDriver@@IEAAXAEBU_GUID@@PEAE1@Z; CClipDndServerDriver::QueryClipboardRestrictionLevels(_GUID const &,uchar *,uchar *)
0x14000879f  test    ebx, ebx
0x1400087a1  jz      loc_140008A20
0x1400087a7  xor     edx, edx; Val
0x1400087a9  lea     rcx, [rbp+0B50h+Buffer]; void *
0x1400087b0  mov     r8d, 100h; Size
0x1400087b6  call    memset_0
0x1400087bb  mov     [rsp+0C50h+var_BF8], 0
0x1400087c4  lea     rdx, [rsp+0C50h+var_BF8]; struct IRDPVirtualChannel **
0x1400087c9  mov     [rsp+0C50h+var_BF0], 0
0x1400087d2  test    r12d, r12d
0x1400087d5  jz      short loc_14000881C
0x1400087d7  call    ?CreateInstance@CServerDynamicVirtualChannel@@SAJPEBDPEAPEAUIRDPVirtualChannel@@@Z; CServerDynamicVirtualChannel::CreateInstance(char const *,IRDPVirtualChannel * *)
0x1400087dc  mov     ebx, eax
0x1400087de  test    eax, eax
0x1400087e0  jns     short loc_140008861
0x1400087e2  mov     rax, cs:WPP_GLOBAL_Control
0x1400087e9  cmp     rax, rdi
0x1400087ec  jz      loc_1400089B3
0x1400087f2  test    byte ptr [rax+1Ch], 8
0x1400087f6  jz      loc_1400089B3
0x1400087fc  cmp     byte ptr [rax+19h], 2
0x140008800  jb      loc_1400089B3
0x140008806  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000880b  mov     edx, 27h ; '''
0x140008810  lea     rcx, aCserverdynamic_0; "CServerDynamicVirtualChannel::CreateIns"...
0x140008817  jmp     loc_140008990
0x14000881c  call    ?CreateInstance@CServerStaticVirtualChannel@@SAJPEBDPEAPEAUIRDPVirtualChannel@@@Z; CServerStaticVirtualChannel::CreateInstance(char const *,IRDPVirtualChannel * *)
0x140008821  mov     ebx, eax
0x140008823  test    eax, eax
0x140008825  jns     short loc_140008861
0x140008827  mov     rax, cs:WPP_GLOBAL_Control
0x14000882e  cmp     rax, rdi
0x140008831  jz      loc_1400089B3
0x140008837  test    byte ptr [rax+1Ch], 8
0x14000883b  jz      loc_1400089B3
0x140008841  cmp     byte ptr [rax+19h], 2
0x140008845  jb      loc_1400089B3
0x14000884b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140008850  mov     edx, 28h ; '('
0x140008855  lea     rcx, aCserverstaticv_0; "CServerStaticVirtualChannel::CreateInst"...
0x14000885c  jmp     loc_140008990
0x140008861  mov     rcx, [r15+48h]
0x140008865  mov     r8, r13
0x140008868  call    CRDPClipboardSharer_CreateInstance
0x14000886d  mov     ebx, eax
0x14000886f  test    eax, eax
0x140008871  jns     short loc_1400088AD
0x140008873  mov     rax, cs:WPP_GLOBAL_Control
0x14000887a  cmp     rax, rdi
0x14000887d  jz      loc_1400089B3
0x140008883  test    byte ptr [rax+1Ch], 8
0x140008887  jz      loc_1400089B3
0x14000888d  cmp     byte ptr [rax+19h], 2
0x140008891  jb      loc_1400089B3
0x140008897  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000889c  mov     edx, 29h ; ')'
0x1400088a1  lea     rcx, aCclipserverCre; "CClipServer::CreateInstance failed!"
0x1400088a8  jmp     loc_140008990
0x1400088ad  test    r14d, r14d
0x1400088b0  jz      short loc_14000891C
0x1400088b2  mov     rcx, [r15+48h]
0x1400088b6  mov     rax, [rcx]
0x1400088b9  mov     rax, [rax+30h]
0x1400088bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088c2  mov     r9d, 80h; cchBufferMax
0x1400088c8  lea     r8, [rbp+0B50h+Buffer]; lpBuffer
0x1400088cf  mov     rcx, rax; hInstance
0x1400088d2  lea     edx, [r9-1Ch]; uID
0x1400088d6  call    cs:__imp_LoadStringW
0x1400088dc  test    eax, eax
0x1400088de  jnz     short loc_14000891C
0x1400088e0  mov     rax, cs:WPP_GLOBAL_Control
0x1400088e7  cmp     rax, rdi
0x1400088ea  jz      short loc_14000891C
0x1400088ec  test    [rax+1Ch], sil
0x1400088f0  jz      short loc_14000891C
0x1400088f2  cmp     byte ptr [rax+19h], 2
0x1400088f6  jb      short loc_14000891C
0x1400088f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400088fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008904  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x14000890b  mov     edx, 2Ah ; '*'
0x140008910  mov     r9d, eax
0x140008913  mov     rcx, [rcx+10h]
0x140008917  call    WPP_SF_d
0x14000891c  mov     r9b, [rsp+0C50h+var_C00]
0x140008921  lea     rdx, [rbp+0B50h+Buffer]
0x140008928  mov     rcx, [r13+0]
0x14000892c  mov     r8d, r14d
0x14000892f  mov     [rsp+0C50h+var_C18], 0
0x140008938  mov     [rsp+0C50h+var_C20], rdx
0x14000893d  lea     rdx, [rbp+0B50h+var_BD0]
0x140008941  mov     [rsp+0C50h+var_C28], rdx
0x140008946  mov     rax, [rcx]
0x140008949  mov     rdx, [rsp+0C50h+var_BF8]
0x14000894e  mov     byte ptr [rsp+0C50h+var_C30], r9b
0x140008953  mov     r9b, [rsp+0C50h+var_BFF]
0x140008958  mov     rax, [rax+18h]
0x14000895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008961  mov     ebx, eax
0x140008963  test    eax, eax
0x140008965  jns     short loc_1400089CC
0x140008967  mov     rax, cs:WPP_GLOBAL_Control
0x14000896e  cmp     rax, rdi
0x140008971  jz      short loc_1400089B3
0x140008973  test    byte ptr [rax+1Ch], 8
0x140008977  jz      short loc_1400089B3
0x140008979  cmp     byte ptr [rax+19h], 2
0x14000897d  jb      short loc_1400089B3
0x14000897f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140008984  mov     edx, 2Bh ; '+'
0x140008989  lea     rcx, aCclipserverIni; "CClipServer::InitializeInstance failed!"
0x140008990  mov     dword ptr [rsp+0C50h+var_C28], ebx
0x140008994  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x14000899b  mov     [rsp+0C50h+var_C30], rcx
0x1400089a0  mov     r9d, eax
0x1400089a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089aa  mov     rcx, [rcx+10h]
0x1400089ae  call    WPP_SF_DsD
0x1400089b3  lea     rcx, [rsp+0C50h+var_BF0]
0x1400089b8  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400089bd  lea     rcx, [rsp+0C50h+var_BF8]
0x1400089c2  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400089c7  jmp     loc_140008A5E
0x1400089cc  lea     rcx, [rsp+0C50h+var_BF0]
0x1400089d1  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400089d6  lea     rcx, [rsp+0C50h+var_BF8]
0x1400089db  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400089e0  mov     rax, cs:WPP_GLOBAL_Control
0x1400089e7  cmp     rax, rdi
0x1400089ea  jz      short loc_140008A1C
0x1400089ec  test    [rax+1Ch], sil
0x1400089f0  jz      short loc_140008A1C
0x1400089f2  cmp     byte ptr [rax+19h], 2
0x1400089f6  jb      short loc_140008A1C
0x1400089f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400089fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a04  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x140008a0b  mov     edx, 2Dh ; '-'
0x140008a10  mov     r9d, eax
0x140008a13  mov     rcx, [rcx+10h]
0x140008a17  call    WPP_SF_d
0x140008a1c  xor     ebx, ebx
0x140008a1e  jmp     short loc_140008A5E
0x140008a20  mov     ebx, esi
0x140008a22  mov     rax, cs:WPP_GLOBAL_Control
0x140008a29  cmp     rax, rdi
0x140008a2c  jz      short loc_140008A5E
0x140008a2e  test    [rax+1Ch], sil
0x140008a32  jz      short loc_140008A5E
0x140008a34  cmp     byte ptr [rax+19h], 2
0x140008a38  jb      short loc_140008A5E
0x140008a3a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140008a3f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
