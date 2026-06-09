# COleSite::CreateObjectSecurityChecks(_GUID const &,CDoc *,CMarkup *,int,int,ushort const *,COleSite *,ulong *,int *)

- ea: `0x180e3bab4`
- end: `0x180e3c12c`
- name: `?CreateObjectSecurityChecks@COleSite@@SAJAEBU_GUID@@PEAVCDoc@@PEAVCMarkup@@HHPEBGPEAV1@PEAKPEAH@Z`
- size: `1656`
- prototype: `__int64 __fastcall(const struct _GUID *, struct CDoc *, struct CMarkup *, unsigned int, int, unsigned __int16 *, struct COleSite *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180e3b54c`
- `0x180f3abdc`

## callees

- `0x1800148b0`
- `0x1800e45d8`
- `0x1800e4964`
- `0x1800f5454`
- `0x18021f9bc`
- `0x18034a080`
- `0x180439b78`
- `0x1804dc5f4`
- `0x1804e223c`
- `0x18075cd3c`
- `0x180771400`
- `0x1807aa7f8`
- `0x180e35af8`
- `0x180e3a858`
- `0x180e3bab4`
- `0x180e3ee58`
- `0x180e421b8`
- `0x18105c03c`
- `0x181065a94`
- `0x18109455c`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180e3bc0c`
- `KERNEL32!GetLastError` at `0x180e3bc0c`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e3bde1`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e3bde1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e3bee4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e3bee4`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e3bcd9`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e3bcd9`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180e3bffa`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180e3bffa`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e3bb9e`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e3c03a`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e3bb9e`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e3c03a`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e3be56`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e3be56`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e3bbf9`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e3bbf9`
- `urlmon!__imp_GetVersionManager` at `0x180e3bc7f`
- `urlmon!__imp_GetVersionManager` at `0x180e3bc7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bdbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bdcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bf7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bf89`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3c045`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3c058`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bdbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bdcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bf7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3bf89`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3c045`
- `OLEAUT32!__imp_SysFreeString` at `0x180e3c058`

## pseudocode

```c
__int64 __fastcall COleSite::CreateObjectSecurityChecks(
        const struct _GUID *a1,
        struct CDoc *a2,
        struct CMarkup *a3,
        unsigned int a4,
        int a5,
        unsigned __int16 *a6,
        struct COleSite *a7,
        unsigned int *a8,
        int *a9)
{
  bool v11; // zf
  unsigned int (__fastcall *IEFrameProcAddress)(const struct _GUID *); // rax
  struct IUri *v16; // rax
  unsigned int v17; // edi
  DWORD LastError; // r13d
  struct CMarkup *v19; // rax
  CDoc *v20; // rcx
  struct IUri *v21; // rax
  int (__fastcall *v22)(__int64, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, BSTR *, int *, int *); // rbx
  bool v23; // al
  int v24; // ebx
  int v25; // eax
  int v26; // r9d
  int v27; // ecx
  struct BLOCKED_ACTION_DETAILS *v28; // r9
  unsigned int v29; // r8d
  OLECHAR *v30; // rbx
  struct _GUID v31; // xmm0
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  CScriptCollection *ScriptCollection; // rax
  unsigned int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  BOOL v39; // [rsp+70h] [rbp-90h]
  unsigned int v40; // [rsp+74h] [rbp-8Ch]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  BSTR v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v44[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v45; // [rsp+98h] [rbp-68h]
  int *v46; // [rsp+A0h] [rbp-60h]
  _QWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v48; // [rsp+B8h] [rbp-48h]
  __int128 v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[8]; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v52; // [rsp+F0h] [rbp-10h]
  int v53; // [rsp+124h] [rbp+24h]
  BSTR v54; // [rsp+128h] [rbp+28h]
  BSTR v55; // [rsp+130h] [rbp+30h]

  v11 = *((_BYTE *)a2 + 4868) >= 0;
  v45 = a6;
  v46 = a9;
  if ( !v11
    && !CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)a2 + 1260))
    || (EnsureIEFrame(), (IEFrameProcAddress = (unsigned int (__fastcall *)(const struct _GUID *))qword_181592838) == 0)
    && (IEFrameProcAddress = (unsigned int (__fastcall *)(const struct _GUID *))GetIEFrameProcAddress(233),
        (qword_181592838 = (__int64)IEFrameProcAddress) == 0)
    || IEFrameProcAddress(a1) != -2146762748 )
  {
    v40 = 0;
    v16 = CMarkup::Uri(a3);
    v17 = CoInternetExtensionAllowedForUri(a1, 1, v16, a4);
    if ( v17 )
      LastError = 0;
    else
      LastError = GetLastError();
    v36 = 0;
    v44[0] = 0;
    v42 = 0;
    if ( a5 )
    {
      if ( LastError == 8 )
      {
        v17 = 1;
LABEL_75:
        v34 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&CLSID_TDC.Data1;
        if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&CLSID_TDC.Data1 )
          v34 = *(_QWORD *)a1->Data4 - *(_QWORD *)CLSID_TDC.Data4;
        if ( !v34 )
        {
          if ( a3 )
          {
            v36 = 0;
            if ( (int)CMarkup::ProcessURLAction(a3, 4620, &v36, 0) >= 0 )
              v17 = v36;
            goto LABEL_84;
          }
          goto LABEL_88;
        }
LABEL_83:
        if ( a3 )
        {
LABEL_84:
          v36 = 0;
          ScriptCollection = CMarkup::GetScriptCollection(a3, 1);
          if ( ScriptCollection
            && ((int)CScriptCollection::IsClassAllowed(ScriptCollection, a1, (int *)&v36) < 0 || !v36) )
          {
            v17 = 0;
          }
        }
LABEL_88:
        *v46 = v17;
        return v40;
      }
LABEL_74:
      if ( !v17 )
        goto LABEL_83;
      goto LABEL_75;
    }
    v39 = 0;
    v43 = 0;
    bstrString = 0;
    if ( !v17 )
      goto LABEL_92;
    v19 = CMarkup::IsPendingRoot(a3) ? CDoc::PendingPrimaryMarkup(a2) : CDoc::PrimaryMarkup(a2);
    if ( CDoc::IsPageActionAllowed(v20, v19, 0x40u) )
      goto LABEL_92;
    v38 = 0;
    if ( (int)GetVersionManager(&v38) < 0 )
      goto LABEL_92;
    v47[1] = 0;
    v50 = 0;
    v47[0] = &CUString::`vftable';
    v49 = 0;
    v48 = 11;
    v21 = CMarkup::Uri(a3);
    if ( v21 )
      CUString::Set((CUString *)v47, v21, Uri_PROPERTY_ABSOLUTE_URI);
    if ( StringFromGUID2(a1, sz, 39) )
    {
      v37 = 1;
      v22 = *(int (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, BSTR *, int *, int *))(*(_QWORD *)v38 + 24LL);
      v23 = IsOs_Wow6432();
      if ( v22(v38, sz, 0, *((_QWORD *)&v49 + 1), v23, 0, &v43, &bstrString, &v37, &v42) >= 0 )
      {
        v17 = v37;
        v39 = v37 == 0;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
    v47[0] = &CUString::`vftable';
    CUString::Set((CUString *)v47, 0, Uri_PROPERTY_RAW_URI);
    if ( !v39 )
    {
LABEL_92:
      if ( LastError - 7 > 1 )
      {
        v40 = COleSite::CheckPendingApproval(a1, a3, a7, v45);
        if ( v40 )
        {
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v43);
          return v40;
        }
      }
    }
    v24 = 1;
    v37 = 1;
    v25 = IsProtectedModeProcess();
    LODWORD(v38) = v25;
    v27 = v25;
    if ( v17 )
    {
      if ( v25 )
      {
        Ext_IsIEExtCompatible(a1, 0, v44, v26);
        goto LABEL_42;
      }
      if ( (unsigned int)Ext_IsIEExtCompatible(a1, &v36, v44, v26) != 1 )
      {
        v17 = 1;
LABEL_40:
        v24 = v17;
        v37 = v17;
LABEL_42:
        if ( v17 || !a7 )
          goto LABEL_73;
        goto LABEL_49;
      }
      v17 = 0;
      if ( a7 )
      {
        v24 = 0;
        v37 = 0;
        if ( g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled()
          && g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled() )
        {
          IECompatLogUIPIBlockedExtension(1u, a1, 0);
          goto LABEL_40;
        }
LABEL_49:
        v27 = v38;
LABEL_50:
        *((_DWORD *)a7 + 108) &= ~0x1000u;
        if ( LastError == 8 )
        {
          memset_0(sz, 0, 0x58u);
          v52 = *a1;
          if ( !(unsigned __int8)IEConfiguration_GetBool(268435477) )
          {
            v28 = (struct BLOCKED_ACTION_DETAILS *)sz;
            v29 = 0x1000000;
LABEL_71:
            NotifyHaveProtectedUserFromUnsafeContent(a3, 0, v29, v28);
          }
        }
        else
        {
          if ( v39 && !v42 )
          {
            v30 = v43;
            if ( v43 )
            {
              *(_QWORD *)v44 = bstrString;
              if ( bstrString )
              {
                memset_0(sz, 0, 0x58u);
                v31 = *a1;
                v54 = v30;
                v43 = 0;
                bstrString = 0;
                v55 = *(BSTR *)v44;
                v52 = v31;
                v53 = 64;
                NotifyHaveProtectedUserFromUnsafeContent(a3, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)sz);
                SysFreeString(v54);
                v54 = 0;
                SysFreeString(v55);
                goto LABEL_72;
              }
            }
            v24 = v37;
          }
          if ( v27 || v24 )
          {
            if ( !(unsigned int)CoInternetIsExtensionsOff() )
            {
              if ( LastError == 7 )
              {
                if ( (Microsoft_IEEnableBits & 8) != 0 )
                  McTemplateU0jz_EventWriteTransfer(v33, v32, a1, v45);
                goto LABEL_72;
              }
              v28 = 0;
              v29 = 8;
              goto LABEL_71;
            }
          }
          else if ( (v36 & 2) != 0 )
          {
            if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
              COleSite::LogControlBlock(a7, 14, 0, a1, v45);
            memset_0(sz, 0, 0x58u);
            v28 = (struct BLOCKED_ACTION_DETAILS *)sz;
            v29 = 0x10000000;
            v52 = *a1;
            goto LABEL_71;
          }
        }
LABEL_72:
        CoInternetExtensionCollectStats(a1, 0, 1);
      }
    }
    else if ( a7 )
    {
      if ( g_cmptlgs == 1 )
        goto LABEL_50;
      if ( (unsigned int)IECompatLoggingEnabled() )
        COleSite::LogControlBlock(a7, 11, 0, a1, v45);
      goto LABEL_49;
    }
LABEL_73:
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v43);
    goto LABEL_74;
  }
  if ( a7 )
  {
    CoInternetExtensionCollectStats(a1, 0, 1);
    if ( g_cmptlgs != 1 )
    {
      if ( (unsigned int)IECompatLoggingEnabled() )
        COleSite::LogControlBlock(a7, 10, 0, a1, a6);
    }
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x180e3bab4  mov     rax, rsp
0x180e3bab7  mov     [rax+20h], r9d
0x180e3babb  mov     [rax+18h], r8
0x180e3babf  mov     [rax+10h], rdx
0x180e3bac3  mov     [rax+8], rcx
0x180e3bac7  push    rbp
0x180e3bac8  push    rbx
0x180e3bac9  push    rsi
0x180e3baca  push    rdi
0x180e3bacb  push    r12
0x180e3bacd  push    r13
0x180e3bacf  push    r14
0x180e3bad1  push    r15
0x180e3bad3  lea     rbp, [rsp-58h]
0x180e3bad8  sub     rsp, 158h
0x180e3badf  mov     rax, cs:__security_cookie
0x180e3bae6  xor     rax, rsp
0x180e3bae9  mov     [rbp+90h+var_50], rax
0x180e3baed  mov     rbx, [rbp+90h+arg_8]
0x180e3baf4  mov     r13, [rbp+90h+arg_28]
0x180e3bafb  mov     rax, [rbp+90h+arg_40]
0x180e3bb02  mov     rsi, [rbp+90h+rguid]
0x180e3bb09  test    byte ptr [rbx+1304h], 80h
0x180e3bb10  mov     r15, [rbp+90h+arg_10]
0x180e3bb17  mov     edi, [rbp+90h+arg_18]
0x180e3bb1d  mov     r12, [rbp+90h+arg_30]
0x180e3bb24  mov     [rbp+90h+var_F8], r13
0x180e3bb28  mov     [rbp+90h+var_F0], rax
0x180e3bb2c  jz      short loc_180E3BB55
0x180e3bb2e  mov     r9d, [rbx+13B8h]
0x180e3bb35  mov     r8d, [rbx+13BCh]
0x180e3bb3c  mov     edx, [rbx+13B4h]
0x180e3bb42  mov     ecx, [rbx+13B0h]; this
0x180e3bb48  call    ?IsIndependent@CDXDependentSurfacePresenterFlip@@UEAA_NXZ; CDXDependentSurfacePresenterFlip::IsIndependent(void)
0x180e3bb4d  test    al, al
0x180e3bb4f  jz      loc_180E3BBD7
0x180e3bb55  call    ?EnsureIEFrame@@YAXXZ; EnsureIEFrame(void)
0x180e3bb5a  mov     rax, cs:qword_181592838
0x180e3bb61  test    rax, rax
0x180e3bb64  jnz     short loc_180E3BB7C
0x180e3bb66  mov     ecx, 0E9h
0x180e3bb6b  call    GetIEFrameProcAddress
0x180e3bb70  mov     cs:qword_181592838, rax
0x180e3bb77  test    rax, rax
0x180e3bb7a  jz      short loc_180E3BBD7
0x180e3bb7c  mov     rcx, rsi
0x180e3bb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e3bb84  cmp     eax, 800B0004h
0x180e3bb89  jnz     short loc_180E3BBD7
0x180e3bb8b  test    r12, r12
0x180e3bb8e  jz      short loc_180E3BBCD
0x180e3bb90  mov     r14d, 1
0x180e3bb96  xor     edx, edx
0x180e3bb98  mov     r8d, r14d
0x180e3bb9b  mov     rcx, rsi
0x180e3bb9e  call    cs:__imp_CoInternetExtensionCollectStats
0x180e3bba4  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e3bbab  jz      short loc_180E3BBCD
0x180e3bbad  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e3bbb2  test    eax, eax
0x180e3bbb4  jz      short loc_180E3BBCD
0x180e3bbb6  mov     r9, rsi
0x180e3bbb9  mov     [rsp+190h+var_170], r13
0x180e3bbbe  xor     r8d, r8d
0x180e3bbc1  lea     edx, [r14+9]
0x180e3bbc5  mov     rcx, r12
0x180e3bbc8  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e3bbcd  mov     eax, 80070005h
0x180e3bbd2  jmp     loc_180E3C10C
0x180e3bbd7  mov     rcx, r15; this
0x180e3bbda  mov     [rsp+190h+var_11C], 0
0x180e3bbe2  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e3bbe7  mov     r14d, 1
0x180e3bbed  mov     r8, rax
0x180e3bbf0  mov     edx, r14d
0x180e3bbf3  mov     r9d, edi
0x180e3bbf6  mov     rcx, rsi
0x180e3bbf9  call    cs:__imp_CoInternetExtensionAllowedForUri
0x180e3bbff  xor     ecx, ecx
0x180e3bc01  mov     edi, eax
0x180e3bc03  test    eax, eax
0x180e3bc05  jz      short loc_180E3BC0C
0x180e3bc07  mov     r13d, ecx
0x180e3bc0a  jmp     short loc_180E3BC17
0x180e3bc0c  call    cs:__imp_GetLastError
0x180e3bc12  mov     r13d, eax
0x180e3bc15  xor     ecx, ecx
0x180e3bc17  mov     [rsp+190h+var_130], ecx
0x180e3bc1b  mov     [rbp+90h+var_100], ecx
0x180e3bc1e  mov     [rbp+90h+var_110], ecx
0x180e3bc21  cmp     [rbp+90h+arg_20], ecx
0x180e3bc27  jnz     loc_180E3C0C1
0x180e3bc2d  mov     [rsp+190h+var_120], ecx
0x180e3bc31  mov     [rbp+90h+var_108], rcx
0x180e3bc35  mov     [rsp+190h+bstrString], rcx
0x180e3bc3a  test    edi, edi
0x180e3bc3c  jz      loc_180E3BD94
0x180e3bc42  mov     rcx, r15; this
0x180e3bc45  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180e3bc4a  mov     rcx, rbx; this
0x180e3bc4d  test    al, al
0x180e3bc4f  jz      short loc_180E3BC58
0x180e3bc51  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x180e3bc56  jmp     short loc_180E3BC5D
0x180e3bc58  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180e3bc5d  mov     r8d, 40h ; '@'; unsigned int
0x180e3bc63  mov     rdx, rax; struct CMarkup *
0x180e3bc66  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e3bc6b  xor     ecx, ecx
0x180e3bc6d  test    eax, eax
0x180e3bc6f  jnz     loc_180E3BD94
0x180e3bc75  mov     [rsp+190h+var_128], rcx
0x180e3bc7a  lea     rcx, [rsp+190h+var_128]
0x180e3bc7f  call    cs:__imp_GetVersionManager
0x180e3bc85  xor     ecx, ecx
0x180e3bc87  test    eax, eax
0x180e3bc89  js      loc_180E3BD94
0x180e3bc8f  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180e3bc96  mov     [rbp+90h+var_E0], rcx
0x180e3bc9a  xorps   xmm0, xmm0
0x180e3bc9d  mov     [rbp+90h+var_C0], ecx
0x180e3bca0  mov     rcx, r15; this
0x180e3bca3  mov     [rbp+90h+var_E8], rax
0x180e3bca7  movdqu  [rbp+90h+var_D0], xmm0
0x180e3bcac  mov     [rbp+90h+var_D8], 0Bh
0x180e3bcb3  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e3bcb8  test    rax, rax
0x180e3bcbb  jz      short loc_180E3BCCC
0x180e3bcbd  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e3bcc0  lea     rcx, [rbp+90h+var_E8]; this
0x180e3bcc4  mov     rdx, rax; struct IUri *
0x180e3bcc7  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e3bccc  mov     r8d, 27h ; '''; cchMax
0x180e3bcd2  lea     rdx, [rbp+90h+sz]; lpsz
0x180e3bcd6  mov     rcx, rsi; rguid
0x180e3bcd9  call    cs:__imp_StringFromGUID2
0x180e3bcdf  test    eax, eax
0x180e3bce1  jz      short loc_180E3BD59
0x180e3bce3  mov     rax, [rsp+190h+var_128]
0x180e3bce8  mov     [rsp+190h+var_12C], r14d
0x180e3bced  mov     rcx, [rax]
0x180e3bcf0  mov     rbx, [rcx+18h]
0x180e3bcf4  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180e3bcf9  mov     r9, qword ptr [rbp+90h+var_D0+8]
0x180e3bcfd  lea     rdx, [rbp+90h+sz]
0x180e3bd01  movzx   ecx, al
0x180e3bd04  xor     r8d, r8d
0x180e3bd07  lea     rax, [rbp+90h+var_110]
0x180e3bd0b  mov     [rsp+190h+var_148], rax
0x180e3bd10  lea     rax, [rsp+190h+var_12C]
0x180e3bd15  mov     [rsp+190h+var_150], rax
0x180e3bd1a  lea     rax, [rsp+190h+bstrString]
0x180e3bd1f  mov     [rsp+190h+var_158], rax
0x180e3bd24  lea     rax, [rbp+90h+var_108]
0x180e3bd28  mov     [rsp+190h+var_160], rax
0x180e3bd2d  mov     rax, rbx
0x180e3bd30  mov     dword ptr [rsp+190h+var_168], 0
0x180e3bd38  mov     dword ptr [rsp+190h+var_170], ecx
0x180e3bd3c  mov     rcx, [rsp+190h+var_128]
0x180e3bd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e3bd46  test    eax, eax
0x180e3bd48  js      short loc_180E3BD59
0x180e3bd4a  mov     edi, [rsp+190h+var_12C]
0x180e3bd4e  xor     eax, eax
0x180e3bd50  test    edi, edi
0x180e3bd52  setz    al
0x180e3bd55  mov     [rsp+190h+var_120], eax
0x180e3bd59  mov     rcx, [rsp+190h+var_128]
0x180e3bd5e  mov     rax, [rcx]
0x180e3bd61  mov     rax, [rax+10h]
0x180e3bd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e3bd6a  xor     edx, edx; struct IUri *
0x180e3bd6c  mov     [rsp+190h+var_128], 0
0x180e3bd75  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180e3bd7c  lea     rcx, [rbp+90h+var_E8]; this
0x180e3bd80  mov     [rbp+90h+var_E8], rax
0x180e3bd84  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180e3bd88  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e3bd8d  cmp     [rsp+190h+var_120], 0
0x180e3bd92  jnz     short loc_180E3BDDA
0x180e3bd94  lea     eax, [r13-7]
0x180e3bd98  cmp     eax, r14d
0x180e3bd9b  jbe     short loc_180E3BDDA
0x180e3bd9d  mov     r9, [rbp+90h+var_F8]; unsigned __int16 *
0x180e3bda1  mov     r8, r12; struct COleSite *
0x180e3bda4  mov     rdx, r15; struct CMarkup *
0x180e3bda7  mov     rcx, rsi; struct _GUID *
0x180e3bdaa  call    ?CheckPendingApproval@COleSite@@SAJAEBU_GUID@@PEAVCMarkup@@PEAV1@PEBG@Z; COleSite::CheckPendingApproval(_GUID const &,CMarkup *,COleSite *,ushort const *)
0x180e3bdaf  mov     [rsp+190h+var_11C], eax
0x180e3bdb3  test    eax, eax
0x180e3bdb5  jz      short loc_180E3BDDA
0x180e3bdb7  mov     rcx, [rsp+190h+bstrString]; bstrString
0x180e3bdbc  call    cs:__imp_SysFreeString
0x180e3bdc2  mov     rcx, [rbp+90h+var_108]; bstrString
0x180e3bdc6  mov     [rsp+190h+bstrString], 0
0x180e3bdcf  call    cs:__imp_SysFreeString
0x180e3bdd5  jmp     loc_180E3C108
0x180e3bdda  mov     ebx, r14d
0x180e3bddd  mov     [rsp+190h+var_12C], ebx
0x180e3bde1  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180e3bde7  mov     dword ptr [rsp+190h+var_128], eax
0x180e3bdeb  mov     ecx, eax
0x180e3bded  test    edi, edi
0x180e3bdef  jz      loc_180E3BE7E
0x180e3bdf5  lea     r8, [rbp+90h+var_100]; unsigned int *
0x180e3bdf9  mov     rcx, rsi; struct _GUID *
0x180e3bdfc  test    eax, eax
0x180e3bdfe  jnz     short loc_180E3BE64
0x180e3be00  lea     rdx, [rsp+190h+var_130]; unsigned int *
0x180e3be05  call    ?Ext_IsIEExtCompatible@@YAJAEBU_GUID@@PEAK1H@Z; Ext_IsIEExtCompatible(_GUID const &,ulong *,ulong *,int)
0x180e3be0a  cmp     eax, r14d
0x180e3be0d  jz      short loc_180E3BE14
0x180e3be0f  mov     edi, r14d
0x180e3be12  jmp     short loc_180E3BE5C
0x180e3be14  xor     edi, edi
0x180e3be16  test    r12, r12
0x180e3be19  jz      loc_180E3C040
0x180e3be1f  xor     ebx, ebx
0x180e3be21  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e3be28  mov     [rsp+190h+var_12C], ebx
0x180e3be2c  jz      loc_180E3BEB4
0x180e3be32  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e3be37  test    eax, eax
0x180e3be39  jz      short loc_180E3BEB4
0x180e3be3b  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e3be42  jz      short loc_180E3BEB4
0x180e3be44  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e3be49  test    eax, eax
0x180e3be4b  jz      short loc_180E3BEB4
0x180e3be4d  xor     r8d, r8d
0x180e3be50  mov     rdx, rsi
0x180e3be53  mov     ecx, r14d
0x180e3be56  call    cs:__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z; IECompatLogUIPIBlockedExtension(ulong,_GUID const &,ushort const *)
0x180e3be5c  mov     ebx, edi
0x180e3be5e  mov     [rsp+190h+var_12C], ebx
0x180e3be62  jmp     short loc_180E3BE6B
0x180e3be64  xor     edx, edx; unsigned int *
0x180e3be66  call    ?Ext_IsIEExtCompatible@@YAJAEBU_GUID@@PEAK1H@Z; Ext_IsIEExtCompatible(_GUID const &,ulong *,ulong *,int)
0x180e3be6b  test    edi, edi
0x180e3be6d  jnz     loc_180E3C040
0x180e3be73  test    r12, r12
0x180e3be76  jz      loc_180E3C040
0x180e3be7c  jmp     short loc_180E3BEB4
0x180e3be7e  test    r12, r12
0x180e3be81  jz      loc_180E3C040
0x180e3be87  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e3be8e  jz      short loc_180E3BEB8
0x180e3be90  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e3be95  test    eax, eax
0x180e3be97  jz      short loc_180E3BEB4
0x180e3be99  mov     rax, [rbp+90h+var_F8]
0x180e3be9d  xor     r8d, r8d
0x180e3bea0  mov     r9, rsi
0x180e3bea3  mov     [rsp+190h+var_170], rax
0x180e3bea8  mov     rcx, r12
0x180e3beab  lea     edx, [r8+0Bh]
0x180e3beaf  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e3beb4  mov     ecx, dword ptr [rsp+190h+var_128]
0x180e3beb8  btr     dword ptr [r12+1B0h], 0Ch
0x180e3bec2  cmp     r13d, 8
0x180e3bec6  jnz     short loc_180E3BF01
0x180e3bec8  xor     edx, edx; Val
0x180e3beca  lea     r8d, [r13+50h]; Size
0x180e3bece  lea     rcx, [rbp+90h+sz]; void *
0x180e3bed2  call    memset_0
0x180e3bed7  movups  xmm0, xmmword ptr [rsi]
0x180e3beda  mov     ecx, 10000015h
0x180e3bedf  movdqu  [rbp+90h+var_A0], xmm0
0x180e3bee4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180e3beea  test    al, al
0x180e3beec  jnz     loc_180E3C032
0x180e3bef2  lea     r9, [rbp+90h+sz]
0x180e3bef6  mov     r8d, 1000000h
0x180e3befc  jmp     loc_180E3C028
0x180e3bf01  cmp     [rsp+190h+var_120], 0
0x180e3bf06  jz      loc_180E3BF98
0x180e3bf0c  cmp     [rbp+90h+var_110], 0
0x180e3bf10  jnz     loc_180E3BF98
0x180e3bf16  mov     rbx, [rbp+90h+var_108]
0x180e3bf1a  test    rbx, rbx
0x180e3bf1d  jz      short loc_180E3BF94
0x180e3bf1f  mov     rax, [rsp+190h+bstrString]
0x180e3bf24  mov     qword ptr [rbp+90h+var_100], rax
0x180e3bf28  test    rax, rax
0x180e3bf2b  jz      short loc_180E3BF94
0x180e3bf2d  xor     edx, edx; Val
0x180e3bf2f  lea     rcx, [rbp+90h+sz]; void *
0x180e3bf33  lea     r8d, [rdx+58h]; Size
0x180e3bf37  call    memset_0
0x180e3bf3c  movups  xmm0, xmmword ptr [rsi]
0x180e3bf3f  mov     rax, qword ptr [rbp+90h+var_100]
0x180e3bf43  lea     r9, [rbp+90h+sz]; struct BLOCKED_ACTION_DETAILS *
0x180e3bf47  xor     r12d, r12d
0x180e3bf4a  mov     [rbp+90h+var_68], rbx
0x180e3bf4e  xor     edx, edx; unsigned int
0x180e3bf50  mov     [rbp+90h+var_108], r12
0x180e3bf54  mov     r8d, 40000000h; unsigned int
0x180e3bf5a  mov     [rsp+190h+bstrString], r12
0x180e3bf5f  mov     rcx, r15; this
0x180e3bf62  mov     [rbp+90h+var_60], rax
  ... truncated ...
```
