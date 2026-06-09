# COleSite::CreateObjectSecurityChecks(_GUID const &,CDoc *,CMarkup *,int,int,ushort const *,COleSite *,ulong *,int *)

- ea: `0x180e60998`
- end: `0x180e61075`
- name: `?CreateObjectSecurityChecks@COleSite@@SAJAEBU_GUID@@PEAVCDoc@@PEAVCMarkup@@HHPEBGPEAV1@PEAKPEAH@Z`
- size: `1757`
- prototype: `__int64 __fastcall(const struct _GUID *, struct CDoc *, struct CMarkup *, int, int, const unsigned __int16 *, struct COleSite *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180e60420`
- `0x180f64454`

## callees

- `0x180051c00`
- `0x1800e7be0`
- `0x1800f9604`
- `0x180138ce4`
- `0x180139080`
- `0x180149610`
- `0x180306fdc`
- `0x1803e13d4`
- `0x1803e41f0`
- `0x18076663c`
- `0x18077b900`
- `0x1807adf24`
- `0x180e5a8a8`
- `0x180e5f714`
- `0x180e60998`
- `0x180e63eac`
- `0x180e6737c`
- `0x18108be78`
- `0x181096438`
- `0x1810c6aa8`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180e60afc`
- `KERNEL32!GetLastError` at `0x180e60afc`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e60cef`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e60cef`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e60dfe`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e60dfe`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e60bd5`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e60bd5`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180e60f2a`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180e60f2a`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e60a82`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e60f70`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e60a82`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x180e60f70`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e60d6a`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e60d6a`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e60ae3`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e60ae3`
- `urlmon!__imp_GetVersionManager` at `0x180e60b75`
- `urlmon!__imp_GetVersionManager` at `0x180e60b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60e9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60eb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60f81`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60e9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60eb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60f81`
- `OLEAUT32!__imp_SysFreeString` at `0x180e60f9a`

## pseudocode

```c
__int64 __fastcall COleSite::CreateObjectSecurityChecks(
        const struct _GUID *a1,
        struct CDoc *a2,
        struct CMarkup *a3,
        __int64 a4,
        int a5,
        unsigned __int16 *a6,
        struct COleSite *a7,
        unsigned int *a8,
        int *a9)
{
  bool v11; // zf
  unsigned int (__fastcall *IEFrameProcAddress)(const struct _GUID *); // rax
  struct IUri *v15; // rax
  unsigned int v16; // edi
  DWORD LastError; // r13d
  struct CMarkup *v18; // rax
  CDoc *v19; // rcx
  struct IUri *v20; // rax
  int (__fastcall *v21)(__int64, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, BSTR *, int *, int *); // rbx
  bool v22; // al
  int v23; // ebx
  int v24; // eax
  int v25; // r9d
  int v26; // ecx
  struct BLOCKED_ACTION_DETAILS *v27; // r9
  unsigned int v28; // r8d
  OLECHAR *v29; // rbx
  struct _GUID v30; // xmm0
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  CScriptCollection *ScriptCollection; // rax
  unsigned int v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  BOOL v38; // [rsp+70h] [rbp-90h]
  unsigned int v39; // [rsp+74h] [rbp-8Ch]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  BSTR v42; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v43[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v44; // [rsp+98h] [rbp-68h]
  int *v45; // [rsp+A0h] [rbp-60h]
  _QWORD v46[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v47; // [rsp+B8h] [rbp-48h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[8]; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v51; // [rsp+F0h] [rbp-10h]
  int v52; // [rsp+124h] [rbp+24h]
  BSTR v53; // [rsp+128h] [rbp+28h]
  BSTR v54; // [rsp+130h] [rbp+30h]

  v11 = *((_BYTE *)a2 + 4868) >= 0;
  v44 = a6;
  v45 = a9;
  if ( !v11
    && !CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)a2 + 1260))
    || (EnsureIEFrame(), (IEFrameProcAddress = (unsigned int (__fastcall *)(const struct _GUID *))qword_1815C5950) == 0)
    && (IEFrameProcAddress = (unsigned int (__fastcall *)(const struct _GUID *))GetIEFrameProcAddress(233),
        (qword_1815C5950 = (__int64)IEFrameProcAddress) == 0)
    || IEFrameProcAddress(a1) != -2146762748 )
  {
    v39 = 0;
    v15 = CMarkup::Uri(a3);
    v16 = CoInternetExtensionAllowedForUri(a1, 1, v15);
    if ( v16 )
      LastError = 0;
    else
      LastError = GetLastError();
    v35 = 0;
    v43[0] = 0;
    v41 = 0;
    if ( a5 )
    {
      if ( LastError == 8 )
      {
        v16 = 1;
LABEL_75:
        v33 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&CLSID_TDC.Data1;
        if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&CLSID_TDC.Data1 )
          v33 = *(_QWORD *)a1->Data4 - *(_QWORD *)CLSID_TDC.Data4;
        if ( !v33 )
        {
          if ( a3 )
          {
            v35 = 0;
            if ( (int)CMarkup::ProcessURLAction(a3, 4620, &v35, 0, 0, 0, 0, 0, 0) >= 0 )
              v16 = v35;
            goto LABEL_84;
          }
          goto LABEL_88;
        }
LABEL_83:
        if ( a3 )
        {
LABEL_84:
          v35 = 0;
          ScriptCollection = CMarkup::GetScriptCollection(a3, 1);
          if ( ScriptCollection
            && ((int)CScriptCollection::IsClassAllowed(ScriptCollection, a1, (int *)&v35) < 0 || !v35) )
          {
            v16 = 0;
          }
        }
LABEL_88:
        *v45 = v16;
        return v39;
      }
LABEL_74:
      if ( !v16 )
        goto LABEL_83;
      goto LABEL_75;
    }
    v38 = 0;
    v42 = 0;
    bstrString = 0;
    if ( !v16 )
      goto LABEL_92;
    v18 = CMarkup::IsPendingRoot(a3) ? CDoc::PendingPrimaryMarkup(a2) : CDoc::PrimaryMarkup(a2);
    if ( CDoc::IsPageActionAllowed(v19, v18, 0x40u) )
      goto LABEL_92;
    v37 = 0;
    if ( (int)GetVersionManager(&v37) < 0 )
      goto LABEL_92;
    v46[1] = 0;
    v49 = 0;
    v46[0] = &CUString::`vftable';
    v48 = 0;
    v47 = 11;
    v20 = CMarkup::Uri(a3);
    if ( v20 )
      CUString::Set((CUString *)v46, v20, Uri_PROPERTY_ABSOLUTE_URI);
    if ( StringFromGUID2(a1, sz, 39) )
    {
      v36 = 1;
      v21 = *(int (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, BSTR *, int *, int *))(*(_QWORD *)v37 + 24LL);
      v22 = IsOs_Wow6432();
      if ( v21(v37, sz, 0, *((_QWORD *)&v48 + 1), v22, 0, &v42, &bstrString, &v36, &v41) >= 0 )
      {
        v16 = v36;
        v38 = v36 == 0;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v46[0] = &CUString::`vftable';
    CUString::Set((CUString *)v46, 0, Uri_PROPERTY_RAW_URI);
    if ( !v38 )
    {
LABEL_92:
      if ( LastError - 7 > 1 )
      {
        v39 = COleSite::CheckPendingApproval(a1, a3, a7, v44);
        if ( v39 )
        {
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v42);
          return v39;
        }
      }
    }
    v23 = 1;
    v36 = 1;
    v24 = IsProtectedModeProcess();
    LODWORD(v37) = v24;
    v26 = v24;
    if ( v16 )
    {
      if ( v24 )
      {
        Ext_IsIEExtCompatible(a1, 0, v43, v25);
        goto LABEL_42;
      }
      if ( (unsigned int)Ext_IsIEExtCompatible(a1, &v35, v43, v25) != 1 )
      {
        v16 = 1;
LABEL_40:
        v23 = v16;
        v36 = v16;
LABEL_42:
        if ( v16 || !a7 )
          goto LABEL_73;
        goto LABEL_49;
      }
      v16 = 0;
      if ( a7 )
      {
        v23 = 0;
        v36 = 0;
        if ( g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled()
          && g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled() )
        {
          IECompatLogUIPIBlockedExtension(1u, a1, 0);
          goto LABEL_40;
        }
LABEL_49:
        v26 = v37;
LABEL_50:
        *((_DWORD *)a7 + 108) &= ~0x1000u;
        if ( LastError == 8 )
        {
          memset_0(sz, 0, 0x58u);
          v51 = *a1;
          if ( !(unsigned __int8)IEConfiguration_GetBool(268435477) )
          {
            v27 = (struct BLOCKED_ACTION_DETAILS *)sz;
            v28 = 0x1000000;
LABEL_71:
            NotifyHaveProtectedUserFromUnsafeContent(a3, 0, v28, v27);
          }
        }
        else
        {
          if ( v38 && !v41 )
          {
            v29 = v42;
            if ( v42 )
            {
              *(_QWORD *)v43 = bstrString;
              if ( bstrString )
              {
                memset_0(sz, 0, 0x58u);
                v30 = *a1;
                v53 = v29;
                v42 = 0;
                bstrString = 0;
                v54 = *(BSTR *)v43;
                v51 = v30;
                v52 = 64;
                NotifyHaveProtectedUserFromUnsafeContent(a3, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)sz);
                SysFreeString(v53);
                v53 = 0;
                SysFreeString(v54);
                goto LABEL_72;
              }
            }
            v23 = v36;
          }
          if ( v26 || v23 )
          {
            if ( !(unsigned int)CoInternetIsExtensionsOff() )
            {
              if ( LastError == 7 )
              {
                if ( (Microsoft_IEEnableBits & 8) != 0 )
                  McTemplateU0jz_EventWriteTransfer(v32, v31, a1, v44);
                goto LABEL_72;
              }
              v27 = 0;
              v28 = 8;
              goto LABEL_71;
            }
          }
          else if ( (v35 & 2) != 0 )
          {
            if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
              COleSite::LogControlBlock(a7, 14, 0, a1, v44);
            memset_0(sz, 0, 0x58u);
            v27 = (struct BLOCKED_ACTION_DETAILS *)sz;
            v28 = 0x10000000;
            v51 = *a1;
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
        COleSite::LogControlBlock(a7, 11, 0, a1, v44);
      goto LABEL_49;
    }
LABEL_73:
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v42);
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
0x180e60998  mov     rax, rsp
0x180e6099b  mov     [rax+20h], r9d
0x180e6099f  mov     [rax+18h], r8
0x180e609a3  mov     [rax+10h], rdx
0x180e609a7  mov     [rax+8], rcx
0x180e609ab  push    rbp
0x180e609ac  push    rbx
0x180e609ad  push    rsi
0x180e609ae  push    rdi
0x180e609af  push    r12
0x180e609b1  push    r13
0x180e609b3  push    r14
0x180e609b5  push    r15
0x180e609b7  lea     rbp, [rsp-58h]
0x180e609bc  sub     rsp, 158h
0x180e609c3  mov     rax, cs:__security_cookie
0x180e609ca  xor     rax, rsp
0x180e609cd  mov     [rbp+90h+var_50], rax
0x180e609d1  mov     rbx, [rbp+90h+arg_8]
0x180e609d8  mov     r13, [rbp+90h+arg_28]
0x180e609df  mov     rax, [rbp+90h+arg_40]
0x180e609e6  mov     rsi, [rbp+90h+rguid]
0x180e609ed  test    byte ptr [rbx+1304h], 80h
0x180e609f4  mov     r15, [rbp+90h+arg_10]
0x180e609fb  mov     edi, [rbp+90h+arg_18]
0x180e60a01  mov     r12, [rbp+90h+arg_30]
0x180e60a08  mov     [rbp+90h+var_F8], r13
0x180e60a0c  mov     [rbp+90h+var_F0], rax
0x180e60a10  jz      short loc_180E60A39
0x180e60a12  mov     r9d, [rbx+13B8h]
0x180e60a19  mov     r8d, [rbx+13BCh]
0x180e60a20  mov     edx, [rbx+13B4h]
0x180e60a26  mov     ecx, [rbx+13B0h]; this
0x180e60a2c  call    ?IsIndependent@CDXDependentSurfacePresenterFlip@@UEAA_NXZ; CDXDependentSurfacePresenterFlip::IsIndependent(void)
0x180e60a31  test    al, al
0x180e60a33  jz      loc_180E60AC1
0x180e60a39  call    ?EnsureIEFrame@@YAXXZ; EnsureIEFrame(void)
0x180e60a3e  mov     rax, cs:qword_1815C5950
0x180e60a45  test    rax, rax
0x180e60a48  jnz     short loc_180E60A60
0x180e60a4a  mov     ecx, 0E9h
0x180e60a4f  call    GetIEFrameProcAddress
0x180e60a54  mov     cs:qword_1815C5950, rax
0x180e60a5b  test    rax, rax
0x180e60a5e  jz      short loc_180E60AC1
0x180e60a60  mov     rcx, rsi
0x180e60a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e60a68  cmp     eax, 800B0004h
0x180e60a6d  jnz     short loc_180E60AC1
0x180e60a6f  test    r12, r12
0x180e60a72  jz      short loc_180E60AB7
0x180e60a74  mov     r14d, 1
0x180e60a7a  xor     edx, edx
0x180e60a7c  mov     r8d, r14d
0x180e60a7f  mov     rcx, rsi
0x180e60a82  call    cs:__imp_CoInternetExtensionCollectStats
0x180e60a89  nop     dword ptr [rax+rax+00h]
0x180e60a8e  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e60a95  jz      short loc_180E60AB7
0x180e60a97  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e60a9c  test    eax, eax
0x180e60a9e  jz      short loc_180E60AB7
0x180e60aa0  mov     r9, rsi
0x180e60aa3  mov     [rsp+190h+var_170], r13
0x180e60aa8  xor     r8d, r8d
0x180e60aab  lea     edx, [r14+9]
0x180e60aaf  mov     rcx, r12
0x180e60ab2  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e60ab7  mov     eax, 80070005h
0x180e60abc  jmp     loc_180E61054
0x180e60ac1  mov     rcx, r15; this
0x180e60ac4  mov     [rsp+190h+var_11C], 0
0x180e60acc  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e60ad1  mov     r14d, 1
0x180e60ad7  mov     r8, rax
0x180e60ada  mov     edx, r14d
0x180e60add  mov     r9d, edi
0x180e60ae0  mov     rcx, rsi
0x180e60ae3  call    cs:__imp_CoInternetExtensionAllowedForUri
0x180e60aea  nop     dword ptr [rax+rax+00h]
0x180e60aef  xor     ecx, ecx
0x180e60af1  mov     edi, eax
0x180e60af3  test    eax, eax
0x180e60af5  jz      short loc_180E60AFC
0x180e60af7  mov     r13d, ecx
0x180e60afa  jmp     short loc_180E60B0D
0x180e60afc  call    cs:__imp_GetLastError
0x180e60b03  nop     dword ptr [rax+rax+00h]
0x180e60b08  mov     r13d, eax
0x180e60b0b  xor     ecx, ecx
0x180e60b0d  mov     [rsp+190h+var_130], ecx
0x180e60b11  mov     [rbp+90h+var_100], ecx
0x180e60b14  mov     [rbp+90h+var_110], ecx
0x180e60b17  cmp     [rbp+90h+arg_20], ecx
0x180e60b1d  jnz     loc_180E61009
0x180e60b23  mov     [rsp+190h+var_120], ecx
0x180e60b27  mov     [rbp+90h+var_108], rcx
0x180e60b2b  mov     [rsp+190h+bstrString], rcx
0x180e60b30  test    edi, edi
0x180e60b32  jz      loc_180E60C96
0x180e60b38  mov     rcx, r15; this
0x180e60b3b  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180e60b40  mov     rcx, rbx; this
0x180e60b43  test    al, al
0x180e60b45  jz      short loc_180E60B4E
0x180e60b47  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x180e60b4c  jmp     short loc_180E60B53
0x180e60b4e  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180e60b53  mov     r8d, 40h ; '@'; unsigned int
0x180e60b59  mov     rdx, rax; struct CMarkup *
0x180e60b5c  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e60b61  xor     ecx, ecx
0x180e60b63  test    eax, eax
0x180e60b65  jnz     loc_180E60C96
0x180e60b6b  mov     [rsp+190h+var_128], rcx
0x180e60b70  lea     rcx, [rsp+190h+var_128]
0x180e60b75  call    cs:__imp_GetVersionManager
0x180e60b7c  nop     dword ptr [rax+rax+00h]
0x180e60b81  xor     ecx, ecx
0x180e60b83  test    eax, eax
0x180e60b85  js      loc_180E60C96
0x180e60b8b  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180e60b92  mov     [rbp+90h+var_E0], rcx
0x180e60b96  xorps   xmm0, xmm0
0x180e60b99  mov     [rbp+90h+var_C0], ecx
0x180e60b9c  mov     rcx, r15; this
0x180e60b9f  mov     [rbp+90h+var_E8], rax
0x180e60ba3  movdqu  [rbp+90h+var_D0], xmm0
0x180e60ba8  mov     [rbp+90h+var_D8], 0Bh
0x180e60baf  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e60bb4  test    rax, rax
0x180e60bb7  jz      short loc_180E60BC8
0x180e60bb9  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e60bbc  lea     rcx, [rbp+90h+var_E8]; this
0x180e60bc0  mov     rdx, rax; struct IUri *
0x180e60bc3  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e60bc8  mov     r8d, 27h ; '''; cchMax
0x180e60bce  lea     rdx, [rbp+90h+sz]; lpsz
0x180e60bd2  mov     rcx, rsi; rguid
0x180e60bd5  call    cs:__imp_StringFromGUID2
0x180e60bdc  nop     dword ptr [rax+rax+00h]
0x180e60be1  test    eax, eax
0x180e60be3  jz      short loc_180E60C5B
0x180e60be5  mov     rax, [rsp+190h+var_128]
0x180e60bea  mov     [rsp+190h+var_12C], r14d
0x180e60bef  mov     rcx, [rax]
0x180e60bf2  mov     rbx, [rcx+18h]
0x180e60bf6  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180e60bfb  mov     r9, qword ptr [rbp+90h+var_D0+8]
0x180e60bff  lea     rdx, [rbp+90h+sz]
0x180e60c03  movzx   ecx, al
0x180e60c06  xor     r8d, r8d
0x180e60c09  lea     rax, [rbp+90h+var_110]
0x180e60c0d  mov     [rsp+190h+var_148], rax
0x180e60c12  lea     rax, [rsp+190h+var_12C]
0x180e60c17  mov     [rsp+190h+var_150], rax
0x180e60c1c  lea     rax, [rsp+190h+bstrString]
0x180e60c21  mov     [rsp+190h+var_158], rax
0x180e60c26  lea     rax, [rbp+90h+var_108]
0x180e60c2a  mov     [rsp+190h+var_160], rax
0x180e60c2f  mov     rax, rbx
0x180e60c32  mov     dword ptr [rsp+190h+var_168], 0
0x180e60c3a  mov     dword ptr [rsp+190h+var_170], ecx
0x180e60c3e  mov     rcx, [rsp+190h+var_128]
0x180e60c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e60c48  test    eax, eax
0x180e60c4a  js      short loc_180E60C5B
0x180e60c4c  mov     edi, [rsp+190h+var_12C]
0x180e60c50  xor     eax, eax
0x180e60c52  test    edi, edi
0x180e60c54  setz    al
0x180e60c57  mov     [rsp+190h+var_120], eax
0x180e60c5b  mov     rcx, [rsp+190h+var_128]
0x180e60c60  mov     rax, [rcx]
0x180e60c63  mov     rax, [rax+10h]
0x180e60c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e60c6c  xor     edx, edx; struct IUri *
0x180e60c6e  mov     [rsp+190h+var_128], 0
0x180e60c77  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180e60c7e  lea     rcx, [rbp+90h+var_E8]; this
0x180e60c82  mov     [rbp+90h+var_E8], rax
0x180e60c86  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180e60c8a  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e60c8f  cmp     [rsp+190h+var_120], 0
0x180e60c94  jnz     short loc_180E60CE8
0x180e60c96  lea     eax, [r13-7]
0x180e60c9a  cmp     eax, r14d
0x180e60c9d  jbe     short loc_180E60CE8
0x180e60c9f  mov     r9, [rbp+90h+var_F8]; unsigned __int16 *
0x180e60ca3  mov     r8, r12; struct COleSite *
0x180e60ca6  mov     rdx, r15; struct CMarkup *
0x180e60ca9  mov     rcx, rsi; struct _GUID *
0x180e60cac  call    ?CheckPendingApproval@COleSite@@SAJAEBU_GUID@@PEAVCMarkup@@PEAV1@PEBG@Z; COleSite::CheckPendingApproval(_GUID const &,CMarkup *,COleSite *,ushort const *)
0x180e60cb1  mov     [rsp+190h+var_11C], eax
0x180e60cb5  test    eax, eax
0x180e60cb7  jz      short loc_180E60CE8
0x180e60cb9  mov     rcx, [rsp+190h+bstrString]; bstrString
0x180e60cbe  call    cs:__imp_SysFreeString
0x180e60cc5  nop     dword ptr [rax+rax+00h]
0x180e60cca  mov     rcx, [rbp+90h+var_108]; bstrString
0x180e60cce  mov     [rsp+190h+bstrString], 0
0x180e60cd7  call    cs:__imp_SysFreeString
0x180e60cde  nop     dword ptr [rax+rax+00h]
0x180e60ce3  jmp     loc_180E61050
0x180e60ce8  mov     ebx, r14d
0x180e60ceb  mov     [rsp+190h+var_12C], ebx
0x180e60cef  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180e60cf6  nop     dword ptr [rax+rax+00h]
0x180e60cfb  mov     dword ptr [rsp+190h+var_128], eax
0x180e60cff  mov     ecx, eax
0x180e60d01  test    edi, edi
0x180e60d03  jz      loc_180E60D98
0x180e60d09  lea     r8, [rbp+90h+var_100]; unsigned int *
0x180e60d0d  mov     rcx, rsi; struct _GUID *
0x180e60d10  test    eax, eax
0x180e60d12  jnz     short loc_180E60D7E
0x180e60d14  lea     rdx, [rsp+190h+var_130]; unsigned int *
0x180e60d19  call    ?Ext_IsIEExtCompatible@@YAJAEBU_GUID@@PEAK1H@Z; Ext_IsIEExtCompatible(_GUID const &,ulong *,ulong *,int)
0x180e60d1e  cmp     eax, r14d
0x180e60d21  jz      short loc_180E60D28
0x180e60d23  mov     edi, r14d
0x180e60d26  jmp     short loc_180E60D76
0x180e60d28  xor     edi, edi
0x180e60d2a  test    r12, r12
0x180e60d2d  jz      loc_180E60F7C
0x180e60d33  xor     ebx, ebx
0x180e60d35  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e60d3c  mov     [rsp+190h+var_12C], ebx
0x180e60d40  jz      loc_180E60DCE
0x180e60d46  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e60d4b  test    eax, eax
0x180e60d4d  jz      short loc_180E60DCE
0x180e60d4f  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e60d56  jz      short loc_180E60DCE
0x180e60d58  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e60d5d  test    eax, eax
0x180e60d5f  jz      short loc_180E60DCE
0x180e60d61  xor     r8d, r8d
0x180e60d64  mov     rdx, rsi
0x180e60d67  mov     ecx, r14d
0x180e60d6a  call    cs:__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z; IECompatLogUIPIBlockedExtension(ulong,_GUID const &,ushort const *)
0x180e60d71  nop     dword ptr [rax+rax+00h]
0x180e60d76  mov     ebx, edi
0x180e60d78  mov     [rsp+190h+var_12C], ebx
0x180e60d7c  jmp     short loc_180E60D85
0x180e60d7e  xor     edx, edx; unsigned int *
0x180e60d80  call    ?Ext_IsIEExtCompatible@@YAJAEBU_GUID@@PEAK1H@Z; Ext_IsIEExtCompatible(_GUID const &,ulong *,ulong *,int)
0x180e60d85  test    edi, edi
0x180e60d87  jnz     loc_180E60F7C
0x180e60d8d  test    r12, r12
0x180e60d90  jz      loc_180E60F7C
0x180e60d96  jmp     short loc_180E60DCE
0x180e60d98  test    r12, r12
0x180e60d9b  jz      loc_180E60F7C
0x180e60da1  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r14d; CMPTLGS g_cmptlgs
0x180e60da8  jz      short loc_180E60DD2
0x180e60daa  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e60daf  test    eax, eax
0x180e60db1  jz      short loc_180E60DCE
0x180e60db3  mov     rax, [rbp+90h+var_F8]
0x180e60db7  xor     r8d, r8d
0x180e60dba  mov     r9, rsi
0x180e60dbd  mov     [rsp+190h+var_170], rax
0x180e60dc2  mov     rcx, r12
0x180e60dc5  lea     edx, [r8+0Bh]
0x180e60dc9  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e60dce  mov     ecx, dword ptr [rsp+190h+var_128]
0x180e60dd2  btr     dword ptr [r12+1B0h], 0Ch
0x180e60ddc  cmp     r13d, 8
0x180e60de0  jnz     short loc_180E60E21
0x180e60de2  xor     edx, edx; Val
0x180e60de4  lea     r8d, [r13+50h]; Size
0x180e60de8  lea     rcx, [rbp+90h+sz]; void *
0x180e60dec  call    memset_0
0x180e60df1  movups  xmm0, xmmword ptr [rsi]
0x180e60df4  mov     ecx, 10000015h
0x180e60df9  movdqu  [rbp+90h+var_A0], xmm0
0x180e60dfe  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180e60e05  nop     dword ptr [rax+rax+00h]
0x180e60e0a  test    al, al
0x180e60e0c  jnz     loc_180E60F68
0x180e60e12  lea     r9, [rbp+90h+sz]
0x180e60e16  mov     r8d, 1000000h
0x180e60e1c  jmp     loc_180E60F5E
0x180e60e21  cmp     [rsp+190h+var_120], 0
0x180e60e26  jz      loc_180E60EC8
0x180e60e2c  cmp     [rbp+90h+var_110], 0
0x180e60e30  jnz     loc_180E60EC8
0x180e60e36  mov     rbx, [rbp+90h+var_108]
0x180e60e3a  test    rbx, rbx
0x180e60e3d  jz      loc_180E60EC4
0x180e60e43  mov     rax, [rsp+190h+bstrString]
0x180e60e48  mov     qword ptr [rbp+90h+var_100], rax
0x180e60e4c  test    rax, rax
0x180e60e4f  jz      short loc_180E60EC4
0x180e60e51  xor     edx, edx; Val
0x180e60e53  lea     rcx, [rbp+90h+sz]; void *
0x180e60e57  lea     r8d, [rdx+58h]; Size
0x180e60e5b  call    memset_0
0x180e60e60  movups  xmm0, xmmword ptr [rsi]
  ... truncated ...
```
