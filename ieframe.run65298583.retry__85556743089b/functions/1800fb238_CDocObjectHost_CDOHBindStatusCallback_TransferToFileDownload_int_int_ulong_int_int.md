# CDocObjectHost::CDOHBindStatusCallback::_TransferToFileDownload(int,int,ulong,int *,int *)

- ea: `0x1800fb238`
- end: `0x1800fb9fa`
- name: `?_TransferToFileDownload@CDOHBindStatusCallback@CDocObjectHost@@AEAA_NHHKPEAH0@Z`
- size: `1986`
- prototype: `char __fastcall(const WCHAR **this, int, int, int, int *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180066380`

## callees

- `0x18000b9e0`
- `0x180044b10`
- `0x180064c38`
- `0x180090e88`
- `0x1800e5eac`
- `0x1800ea5d8`
- `0x1800eab68`
- `0x1800f6ee0`
- `0x1800f6ff0`
- `0x1800f8340`
- `0x1800fb238`
- `0x1801d8538`
- `0x1801d858c`
- `0x1801de7dc`
- `0x180550010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800fb444`
- `KERNEL32!LocalAlloc` at `0x1800fb444`
- `KERNEL32!LocalFree` at `0x1800fb6ff`
- `KERNEL32!LocalFree` at `0x1800fb6ff`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb6df`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb7c0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb9d2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb6df`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb7c0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800fb9d2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb7fa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb804`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb80e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb818`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb7fa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb804`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb80e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800fb818`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb285`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb2ca`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb6a7`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb99e`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb285`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb2ca`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb6a7`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800fb99e`
- `urlmon!ReleaseBindInfo` at `0x1800fb6f6`
- `urlmon!ReleaseBindInfo` at `0x1800fb6f6`

## pseudocode

```c
char __fastcall CDocObjectHost::CDOHBindStatusCallback::_TransferToFileDownload(
        const WCHAR **this,
        int a2,
        int a3,
        int a4,
        int *a5,
        int *a6)
{
  char v8; // r15
  char v9; // r13
  bool v10; // di
  char v11; // al
  _DWORD *v12; // rdi
  int v13; // edx
  int v14; // ecx
  int v15; // r12d
  int v16; // esi
  int v17; // r11d
  bool v18; // cf
  int v19; // r8d
  int v20; // r9d
  int v21; // edx
  int v22; // r10d
  bool v23; // zf
  BINDINFO *v24; // rbx
  int v25; // esi
  __int64 v26; // rcx
  const struct DOWNLOADSECPARAM *v27; // rax
  BINDINFO *v28; // r9
  DOWNLOADSECPARAM *v29; // rax
  int v30; // r11d
  int v31; // r9d
  unsigned int v32; // r9d
  IBindCtx *v33; // rdx
  CInterThreadMarshal *v34; // r10
  unsigned __int16 *v35; // r10
  __int64 v36; // rcx
  __int64 v37; // rcx
  bool v38; // al
  __int64 v40; // rcx
  void *v41; // rsi
  unsigned __int16 *v42; // rbx
  unsigned int v43; // edi
  DOWNLOADSECPARAM *v44; // rax
  CInterThreadMarshal *v45; // r8
  HWND v46; // r9
  IUnknown *v47; // r10
  int v48; // r11d
  _DWORD *v49; // rax
  int v50; // [rsp+78h] [rbp-98h]
  void *v51; // [rsp+80h] [rbp-90h]
  CInterThreadMarshal *v52; // [rsp+88h] [rbp-88h]
  bool v53; // [rsp+90h] [rbp-80h] BYREF
  bool v54; // [rsp+91h] [rbp-7Fh] BYREF
  int v55; // [rsp+94h] [rbp-7Ch] BYREF
  void *ppv; // [rsp+98h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-70h] BYREF
  unsigned int v58[2]; // [rsp+A8h] [rbp-68h] BYREF
  HWND v59; // [rsp+B0h] [rbp-60h] BYREF
  __int128 v60; // [rsp+B8h] [rbp-58h]
  __int64 v61; // [rsp+C8h] [rbp-48h]
  int v62; // [rsp+D0h] [rbp-40h]
  unsigned __int16 *v63; // [rsp+D8h] [rbp-38h] BYREF
  unsigned __int16 *v64; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int16 *v65; // [rsp+E8h] [rbp-28h] BYREF
  _DWORD v66[8]; // [rsp+F0h] [rbp-20h] BYREF
  const WCHAR *v67; // [rsp+110h] [rbp+0h]
  const WCHAR *v68; // [rsp+118h] [rbp+8h]
  unsigned __int16 *v69; // [rsp+120h] [rbp+10h]
  unsigned __int16 *v70; // [rsp+128h] [rbp+18h]
  unsigned __int16 *v71; // [rsp+130h] [rbp+20h]
  int v72; // [rsp+138h] [rbp+28h]
  _BYTE v73[128]; // [rsp+140h] [rbp+30h] BYREF
  char v76; // [rsp+1F8h] [rbp+E8h]

  pv = 0;
  *a6 = 0;
  if ( !(unsigned int)IsIExploreProcess() || (v8 = 0, LCIEIsComponentSharedFlagValueSet_FromComponentThread(0x1000000u)) )
  {
    v8 = 1;
    CDocObjectHost::CDOHBindStatusCallback::BeginningTransaction(
      (CDocObjectHost::CDOHBindStatusCallback *)(this + 3),
      0,
      0,
      0,
      (unsigned __int16 **)&pv);
    v55 = 0;
    v59 = 0;
    v54 = 0;
    v76 = 0;
    v53 = 0;
    v62 = LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u);
    v9 = 0;
    v63 = 0;
    v10 = v62 == 0;
    v64 = 0;
    v65 = 0;
    ppv = 0;
    if ( (int)CDocObjectHost::QueryInterface(
                (CDocObjectHost *)(this - 244),
                &GUID_00000000_0000_0000_c000_000000000046,
                &ppv) < 0 )
      ATL::AtlComPtrAssign((struct IUnknown **)&ppv, 0);
    CDocObjectHost::CDOHBindStatusCallback::_GetDownloadContextInfo(
      (CDocObjectHost::CDOHBindStatusCallback *)this,
      v10,
      (struct IUnknown *)ppv,
      &v53,
      &v54,
      &v55,
      &v59,
      &v63,
      &v64,
      &v65);
    v11 = *((_BYTE *)this + 208);
    v12 = (_DWORD *)this + 47;
    v13 = *((_DWORD *)this - 326);
    v14 = 0;
    v15 = *((_DWORD *)this - 303);
    v16 = 0;
    *(_QWORD *)v58 = (char *)this + 188;
    v17 = (8 * v13) >> 31;
    if ( !v11 )
    {
      v16 = a2;
      v18 = __CFSHR__(*v12, 11);
      *(_QWORD *)v58 = (char *)this + 188;
      v14 = -v18;
    }
    v19 = -__CFSHR__(*v12, 10);
    v20 = -__CFSHR__(v13, 6);
    v21 = -__CFSHR__(v13, 10);
    if ( v11 )
      v22 = *((unsigned __int8 *)this + 209);
    else
      v22 = 0;
    v23 = *((_BYTE *)this + 210) == 0;
    v66[1] = v22;
    v66[2] = v21;
    v66[0] = !v23;
    v67 = this[17];
    v68 = this[19];
    v69 = v63;
    v70 = v64;
    v71 = v65;
    v66[3] = v20;
    v66[4] = v19;
    v66[5] = v14;
    v66[6] = v16;
    v66[7] = v17;
    v72 = v15;
    if ( *((_DWORD *)this + 43) != 1 )
    {
      if ( !*(this - 136) )
        goto LABEL_48;
      v25 = v55;
      if ( ppv )
      {
        v40 = (__int64)*(this - 195);
        if ( v40 )
        {
          v61 = 0;
          v60 = 0;
          (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v40 + 32LL))(v40, &CGID_ShellDocView, 69);
          if ( (_WORD)v60 != 11 || !WORD4(v60) )
          {
            if ( !a3 )
            {
              v41 = pv;
              if ( *((_BYTE *)this + 208) )
                v41 = 0;
              v42 = (unsigned __int16 *)this[16];
              v43 = *((_DWORD *)this + 44);
              v44 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v73, (const struct DOWNLOADSECPARAM *)v66);
              CDownloadUtilities::OpenUI(
                (__int64)*(this - 136),
                (IBindCtx *)*(this - 135),
                (__int64)v44,
                0,
                v41,
                0,
                v43,
                0,
                v42,
                v48,
                v47,
                0,
                a4,
                v46,
                v55,
                v50,
                v51,
                v45);
              v76 = 1;
              if ( !*((_BYTE *)this + 208) )
                pv = 0;
              v49 = *(_DWORD **)v58;
              v25 = v55;
              this[27] = 0;
              *v49 &= ~0x400u;
            }
            if ( (*(_DWORD *)(this - 163) & 0x40000) != 0 || LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
            {
              if ( *(this - 195) && (*(_DWORD *)(this - 163) & 0x4000000) != 0 )
                v9 = 1;
            }
            else
            {
              VirtualTab_NewTabShouldExit(0);
            }
            if ( (*(_DWORD *)(this - 163) & 0x40000) == 0 && IsDualEngineProcess() )
            {
              if ( v9 )
                DualEngineNavigationToDownload();
              DualEngineNavigationFailed();
            }
          }
        }
      }
      *a5 = 1;
LABEL_35:
      if ( v76 )
      {
        v36 = (__int64)*(this - 195);
        if ( v36 )
        {
          if ( (*(_DWORD *)(this - 163) & 0x40000) == 0 && (!v62 && !v53 || v54) )
            (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v36 + 32LL))(v36, &CGID_Explorer, 104);
        }
      }
      if ( v9 )
      {
        if ( this != (const WCHAR **)1952 )
        {
          v37 = (__int64)*(this - 195);
          if ( v37 )
          {
            if ( v25 )
            {
              v61 = 0;
              v60 = 0;
              DWORD2(v60) = v25;
              LOWORD(v60) = 3;
              (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v37 + 32LL))(v37, &CGID_Explorer, 105);
            }
            v38 = IsDualEngineProcess();
            (*(void (__fastcall **)(_QWORD, const GUID *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*(this - 195)
                                                                                         + 32LL))(
              *(this - 195),
              &CGID_Explorer,
              v38 ? 138 : 98,
              0,
              0,
              0);
          }
        }
      }
      goto LABEL_48;
    }
    v58[0] = 0;
    v24 = (BINDINFO *)LocalAlloc(0x40u, 0x80u);
    if ( !v24 )
    {
      v8 = 0;
LABEL_48:
      CoTaskMemFree(pv);
      CoTaskMemFree(v63);
      CoTaskMemFree(v64);
      CoTaskMemFree(v65);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppv);
      return v8;
    }
    v24->cbSize = 128;
    CDocObjectHost::CDOHBindStatusCallback::GetBindInfo((CDocObjectHost::CDOHBindStatusCallback *)this, v58, v24);
    v25 = v55;
    if ( !ppv
      || (v26 = (__int64)*(this - 195)) == 0
      || (v61 = 0,
          v60 = 0,
          (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v26 + 32LL))(v26, &CGID_ShellDocView, 69),
          (_WORD)v60 == 11)
      && WORD4(v60)
      || a3 )
    {
LABEL_34:
      ReleaseBindInfo(v24);
      LocalFree(v24);
      goto LABEL_35;
    }
    if ( v24->dwBindVerb )
    {
      v29 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v73, (const struct DOWNLOADSECPARAM *)v66);
      v32 = v58[0] | v31;
      v33 = (IBindCtx *)this[8];
      v52 = v34;
      v35 = (unsigned __int16 *)this[16];
      if ( *((_BYTE *)this + 208) )
      {
        CDownloadUtilities::OpenUI(
          (__int64)*(this - 136),
          v33,
          (__int64)v29,
          0,
          0,
          0,
          v32,
          0,
          v35,
          v30,
          (IUnknown *)ppv,
          0,
          a4,
          v59,
          v25,
          v50,
          v51,
          v52);
LABEL_24:
        this[27] = 0;
        *v12 &= ~0x400u;
        v76 = 1;
        if ( (*(_DWORD *)(this - 163) & 0x40000) != 0 || LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
        {
          if ( *(this - 195) && (*(_DWORD *)(this - 163) & 0x4000000) != 0 )
            v9 = 1;
        }
        else
        {
          VirtualTab_NewTabShouldExit(0);
        }
        if ( (*(_DWORD *)(this - 163) & 0x40000) == 0 && IsDualEngineProcess() )
          DualEngineNavigationFailed();
        if ( !v24 )
          goto LABEL_35;
        goto LABEL_34;
      }
      CDownloadUtilities::OpenUI(
        (__int64)*(this - 136),
        v33,
        (__int64)v29,
        0,
        pv,
        1u,
        v32,
        v24,
        v35,
        v30,
        (IUnknown *)ppv,
        0,
        a4,
        v59,
        v25,
        v50,
        v51,
        v52);
      v24 = 0;
    }
    else
    {
      v27 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v73, (const struct DOWNLOADSECPARAM *)v66);
      CDownloadUtilities::OpenUIURL(
        this[16],
        0,
        v27,
        0,
        pv,
        (int)v28,
        (_DWORD)this[22] & 0x800000,
        v28,
        (__int64)this[16],
        *((_DWORD *)this - 332),
        (__int64)ppv,
        (int)v28,
        a4,
        (__int64)v59,
        v25);
    }
    pv = 0;
    goto LABEL_24;
  }
  return v8;
}

```

## disassembly

```asm
0x1800fb238  mov     [rsp-8+arg_0], rbx
0x1800fb23d  mov     [rsp-8+arg_18], r9d
0x1800fb242  mov     [rsp-8+arg_10], r8d
0x1800fb247  push    rbp
0x1800fb248  push    rsi
0x1800fb249  push    rdi
0x1800fb24a  push    r12
0x1800fb24c  push    r13
0x1800fb24e  push    r14
0x1800fb250  push    r15
0x1800fb252  lea     rbp, [rsp-80h]
0x1800fb257  sub     rsp, 190h
0x1800fb25e  mov     rax, [rbp+0B0h+arg_28]
0x1800fb265  xor     r12d, r12d
0x1800fb268  mov     ebx, edx
0x1800fb26a  mov     [rbp+0B0h+pv], r12
0x1800fb26e  mov     r14, rcx
0x1800fb271  mov     [rax], r12d
0x1800fb274  call    ?IsIExploreProcess@@YAHXZ; IsIExploreProcess(void)
0x1800fb279  test    eax, eax
0x1800fb27b  jz      short loc_1800FB293
0x1800fb27d  mov     ecx, 1000000h
0x1800fb282  mov     r15b, r12b
0x1800fb285  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x1800fb28b  test    eax, eax
0x1800fb28d  jz      loc_1800FB827
0x1800fb293  lea     rax, [rbp+0B0h+pv]
0x1800fb297  xor     r9d, r9d; unsigned int
0x1800fb29a  lea     rcx, [r14+18h]; this
0x1800fb29e  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 **
0x1800fb2a3  xor     r8d, r8d; unsigned __int16 *
0x1800fb2a6  xor     edx, edx; unsigned __int16 *
0x1800fb2a8  mov     r15d, 1
0x1800fb2ae  call    ?BeginningTransaction@CDOHBindStatusCallback@CDocObjectHost@@MEAAJPEBG0KPEAPEAG@Z; CDocObjectHost::CDOHBindStatusCallback::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)
0x1800fb2b3  lea     ecx, [r15+3]
0x1800fb2b7  mov     [rbp+0B0h+var_12C], r12d
0x1800fb2bb  mov     [rbp+0B0h+var_110], r12
0x1800fb2bf  mov     [rbp+0B0h+var_12F], r12b
0x1800fb2c3  mov     byte ptr [rbp+0B0h+arg_28], r12b
0x1800fb2ca  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x1800fb2d0  lea     r8, [rbp+0B0h+ppv]; ppv
0x1800fb2d4  mov     [rbp+0B0h+var_130], r12b
0x1800fb2d8  test    eax, eax
0x1800fb2da  mov     [rbp+0B0h+var_F0], eax
0x1800fb2dd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800fb2e4  movzx   r13d, r12b
0x1800fb2e8  lea     rcx, [r14-7A0h]; this
0x1800fb2ef  mov     [rbp+0B0h+var_E8], r12
0x1800fb2f3  setz    dil
0x1800fb2f7  mov     [rbp+0B0h+var_E0], r12
0x1800fb2fb  mov     [rbp+0B0h+var_D8], r12
0x1800fb2ff  mov     [rbp+0B0h+ppv], r12
0x1800fb303  call    ?QueryInterface@CDocObjectHost@@UEAAJAEBU_GUID@@PEAPEAX@Z; CDocObjectHost::QueryInterface(_GUID const &,void * *)
0x1800fb308  test    eax, eax
0x1800fb30a  jns     short loc_1800FB317
0x1800fb30c  xor     edx, edx; struct IUnknown *
0x1800fb30e  lea     rcx, [rbp+0B0h+ppv]; struct IUnknown **
0x1800fb312  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800fb317  mov     r8, [rbp+0B0h+ppv]; struct IUnknown *
0x1800fb31b  lea     rax, [rbp+0B0h+var_D8]
0x1800fb31f  mov     [rsp+1C0h+var_178], rax; unsigned __int16 **
0x1800fb324  lea     r9, [rbp+0B0h+var_130]; bool *
0x1800fb328  lea     rax, [rbp+0B0h+var_E0]
0x1800fb32c  mov     dl, dil; bool
0x1800fb32f  mov     [rsp+1C0h+var_180], rax; unsigned __int16 **
0x1800fb334  mov     rcx, r14; this
0x1800fb337  lea     rax, [rbp+0B0h+var_E8]
0x1800fb33b  mov     [rsp+1C0h+var_188], rax; unsigned __int16 **
0x1800fb340  lea     rax, [rbp+0B0h+var_110]
0x1800fb344  mov     [rsp+1C0h+var_190], rax; HWND *
0x1800fb349  lea     rax, [rbp+0B0h+var_12C]
0x1800fb34d  mov     [rsp+1C0h+var_198], rax; int *
0x1800fb352  lea     rax, [rbp+0B0h+var_12F]
0x1800fb356  mov     [rsp+1C0h+var_1A0], rax; bool *
0x1800fb35b  call    ?_GetDownloadContextInfo@CDOHBindStatusCallback@CDocObjectHost@@AEAAX_NPEAUIUnknown@@PEA_N2PEAJPEAPEAUHWND__@@PEAPEAG55@Z; CDocObjectHost::CDOHBindStatusCallback::_GetDownloadContextInfo(bool,IUnknown *,bool *,bool *,long *,HWND__ * *,ushort * *,ushort * *,ushort * *)
0x1800fb360  mov     al, [r14+0D0h]
0x1800fb367  lea     rdi, [r14+0BCh]
0x1800fb36e  mov     edx, [r14-518h]
0x1800fb375  xor     ecx, ecx
0x1800fb377  mov     r12d, [r14-4BCh]
0x1800fb37e  mov     esi, ecx
0x1800fb380  mov     qword ptr [rbp+0B0h+var_118], rdi
0x1800fb384  lea     r11d, ds:0[rdx*8]
0x1800fb38c  sar     r11d, 1Fh
0x1800fb390  test    al, al
0x1800fb392  cmovz   esi, ebx
0x1800fb395  xor     ebx, ebx
0x1800fb397  test    al, al
0x1800fb399  jnz     short loc_1800FB3A6
0x1800fb39b  mov     ecx, [rdi]
0x1800fb39d  shr     ecx, 0Bh
0x1800fb3a0  mov     qword ptr [rbp+0B0h+var_118], rdi
0x1800fb3a4  sbb     ecx, ecx
0x1800fb3a6  mov     r8d, [rdi]
0x1800fb3a9  mov     r9d, edx
0x1800fb3ac  shr     r8d, 0Ah
0x1800fb3b0  sbb     r8d, r8d
0x1800fb3b3  shr     r9d, 6
0x1800fb3b7  sbb     r9d, r9d
0x1800fb3ba  shr     edx, 0Ah
0x1800fb3bd  sbb     edx, edx
0x1800fb3bf  test    al, al
0x1800fb3c1  jz      short loc_1800FB3CD
0x1800fb3c3  movzx   r10d, byte ptr [r14+0D1h]
0x1800fb3cb  jmp     short loc_1800FB3D0
0x1800fb3cd  mov     r10d, ebx
0x1800fb3d0  cmp     [r14+0D2h], bl
0x1800fb3d7  mov     eax, ebx
0x1800fb3d9  mov     [rbp+0B0h+var_CC], r10d
0x1800fb3dd  setnz   al
0x1800fb3e0  mov     [rbp+0B0h+var_C8], edx
0x1800fb3e3  mov     [rbp+0B0h+var_D0], eax
0x1800fb3e6  mov     rax, [r14+88h]
0x1800fb3ed  mov     [rbp+0B0h+var_B0], rax
0x1800fb3f1  mov     rax, [r14+98h]
0x1800fb3f8  mov     [rbp+0B0h+var_A8], rax
0x1800fb3fc  mov     rax, [rbp+0B0h+var_E8]
0x1800fb400  mov     [rbp+0B0h+var_A0], rax
0x1800fb404  mov     rax, [rbp+0B0h+var_E0]
0x1800fb408  mov     [rbp+0B0h+var_98], rax
0x1800fb40c  mov     rax, [rbp+0B0h+var_D8]
0x1800fb410  mov     [rbp+0B0h+var_90], rax
0x1800fb414  mov     [rbp+0B0h+var_C4], r9d
0x1800fb418  mov     [rbp+0B0h+var_C0], r8d
0x1800fb41c  mov     [rbp+0B0h+var_BC], ecx
0x1800fb41f  mov     [rbp+0B0h+var_B8], esi
0x1800fb422  mov     [rbp+0B0h+var_B4], r11d
0x1800fb426  mov     [rbp+0B0h+var_88], r12d
0x1800fb42a  cmp     [r14+0ACh], r15d
0x1800fb431  jnz     loc_1800FB845
0x1800fb437  mov     esi, 80h
0x1800fb43c  mov     [rbp+0B0h+var_118], ebx
0x1800fb43f  mov     edx, esi; uBytes
0x1800fb441  lea     ecx, [rsi-40h]; uFlags
0x1800fb444  call    cs:__imp_LocalAlloc
0x1800fb44a  mov     rbx, rax
0x1800fb44d  xor     eax, eax
0x1800fb44f  test    rbx, rbx
0x1800fb452  jnz     short loc_1800FB45C
0x1800fb454  mov     r15b, al
0x1800fb457  jmp     loc_1800FB7F6
0x1800fb45c  mov     r8, rbx; struct _tagBINDINFO *
0x1800fb45f  mov     [rbx], esi
0x1800fb461  lea     rdx, [rbp+0B0h+var_118]; unsigned int *
0x1800fb465  mov     rcx, r14; this
0x1800fb468  call    ?GetBindInfo@CDOHBindStatusCallback@CDocObjectHost@@MEAAJPEAKPEAU_tagBINDINFO@@@Z; CDocObjectHost::CDOHBindStatusCallback::GetBindInfo(ulong *,_tagBINDINFO *)
0x1800fb46d  mov     esi, [rbp+0B0h+var_12C]
0x1800fb470  xor     r8d, r8d
0x1800fb473  mov     r12d, 40000h
0x1800fb479  cmp     [rbp+0B0h+ppv], r8
0x1800fb47d  jz      loc_1800FB6F3
0x1800fb483  mov     rcx, [r14-618h]
0x1800fb48a  test    rcx, rcx
0x1800fb48d  jz      loc_1800FB6F3
0x1800fb493  xor     eax, eax
0x1800fb495  lea     rdx, [rbp+0B0h+var_108]
0x1800fb499  mov     [rbp+0B0h+var_F8], rax
0x1800fb49d  xorps   xmm0, xmm0
0x1800fb4a0  mov     [rsp+1C0h+var_198], rdx
0x1800fb4a5  xor     r9d, r9d
0x1800fb4a8  movups  [rbp+0B0h+var_108], xmm0
0x1800fb4ac  mov     rax, [rcx]
0x1800fb4af  lea     rdx, CGID_ShellDocView
0x1800fb4b6  mov     [rsp+1C0h+var_1A0], r8
0x1800fb4bb  lea     r8d, [r9+45h]
0x1800fb4bf  mov     rax, [rax+20h]
0x1800fb4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb4c8  xor     r9d, r9d
0x1800fb4cb  cmp     word ptr [rbp+0B0h+var_108], 0Bh
0x1800fb4d0  jnz     short loc_1800FB4DD
0x1800fb4d2  cmp     word ptr [rbp+0B0h+var_108+8], r9w
0x1800fb4d7  jnz     loc_1800FB6F3
0x1800fb4dd  cmp     [rbp+0B0h+arg_10], r9d
0x1800fb4e4  jnz     loc_1800FB6F3
0x1800fb4ea  lea     rdx, [rbp+0B0h+var_D0]; struct DOWNLOADSECPARAM *
0x1800fb4ee  mov     r10, [r14+0D8h]
0x1800fb4f5  lea     rcx, [rbp+0B0h+var_80]; this
0x1800fb4f9  cmp     [rbx+2Ch], r9d
0x1800fb4fd  jnz     loc_1800FB593
0x1800fb503  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800fb508  mov     rcx, [rbp+0B0h+var_110]
0x1800fb50c  mov     r10, rax
0x1800fb50f  mov     rdx, [rbp+0B0h+ppv]
0x1800fb513  mov     rax, [r14+0D8h]
0x1800fb51a  mov     r11, [r14+80h]
0x1800fb521  mov     r8d, [r14+0B0h]
0x1800fb528  mov     [rsp+1C0h+var_138], rax
0x1800fb530  and     r8d, 800000h
0x1800fb537  mov     rax, [rbp+0B0h+pv]
0x1800fb53b  mov     [rsp+1C0h+var_150], esi
0x1800fb53f  mov     [rsp+1C0h+var_158], rcx
0x1800fb544  mov     ecx, [rbp+0B0h+arg_18]
0x1800fb54a  mov     [rsp+1C0h+var_160], ecx
0x1800fb54e  mov     rcx, r11
0x1800fb551  mov     [rsp+1C0h+var_168], r9d
0x1800fb556  mov     [rsp+1C0h+var_170], rdx
0x1800fb55b  mov     edx, [r14-530h]
0x1800fb562  mov     dword ptr [rsp+1C0h+var_178], edx
0x1800fb566  xor     edx, edx
0x1800fb568  mov     [rsp+1C0h+var_180], r11
0x1800fb56d  mov     [rsp+1C0h+var_188], r9
0x1800fb572  mov     dword ptr [rsp+1C0h+var_190], r8d
0x1800fb577  mov     r8, r10
0x1800fb57a  mov     dword ptr [rsp+1C0h+var_198], r9d
0x1800fb57f  xor     r9d, r9d
0x1800fb582  mov     [rsp+1C0h+var_1A0], rax
0x1800fb587  call    ?OpenUIURL@CDownloadUtilities@@SAJPEBGPEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@0IPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@0PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUIURL(ushort const *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x1800fb58c  xor     eax, eax
0x1800fb58e  jmp     loc_1800FB683
0x1800fb593  mov     r9d, [r14+0B0h]
0x1800fb59a  mov     r11d, [r14-530h]
0x1800fb5a1  and     r9d, 800000h
0x1800fb5a8  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800fb5ad  or      r9d, [rbp+0B0h+var_118]
0x1800fb5b1  cmp     byte ptr [r14+0D0h], 0
0x1800fb5b9  mov     rdx, [r14+40h]
0x1800fb5bd  mov     [rsp+1C0h+var_138], r10
0x1800fb5c5  mov     r10, [r14+80h]
0x1800fb5cc  mov     [rsp+1C0h+var_150], esi
0x1800fb5d0  jz      short loc_1800FB627
0x1800fb5d2  mov     r8, [rbp+0B0h+var_110]
0x1800fb5d6  mov     ecx, [rbp+0B0h+arg_18]
0x1800fb5dc  mov     [rsp+1C0h+var_158], r8
0x1800fb5e1  mov     r8, [rbp+0B0h+ppv]
0x1800fb5e5  mov     [rsp+1C0h+var_160], ecx
0x1800fb5e9  xor     ecx, ecx
0x1800fb5eb  mov     [rsp+1C0h+var_168], ecx
0x1800fb5ef  mov     [rsp+1C0h+var_170], r8
0x1800fb5f4  mov     r8, rax
0x1800fb5f7  mov     dword ptr [rsp+1C0h+var_178], r11d
0x1800fb5fc  mov     [rsp+1C0h+var_180], r10
0x1800fb601  mov     [rsp+1C0h+var_188], rcx
0x1800fb606  mov     dword ptr [rsp+1C0h+var_190], r9d
0x1800fb60b  xor     r9d, r9d
0x1800fb60e  mov     dword ptr [rsp+1C0h+var_198], ecx
0x1800fb612  mov     [rsp+1C0h+var_1A0], rcx
0x1800fb617  mov     rcx, [r14-440h]
0x1800fb61e  call    ?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x1800fb623  xor     eax, eax
0x1800fb625  jmp     short loc_1800FB687
0x1800fb627  mov     rcx, [rbp+0B0h+var_110]
0x1800fb62b  mov     r8, rax
0x1800fb62e  mov     rax, [rbp+0B0h+pv]
0x1800fb632  mov     [rsp+1C0h+var_158], rcx
0x1800fb637  mov     ecx, [rbp+0B0h+arg_18]
0x1800fb63d  mov     [rsp+1C0h+var_160], ecx
0x1800fb641  mov     rcx, [rbp+0B0h+ppv]
0x1800fb645  mov     [rsp+1C0h+var_168], 0
0x1800fb64d  mov     [rsp+1C0h+var_170], rcx
0x1800fb652  mov     rcx, [r14-440h]
0x1800fb659  mov     dword ptr [rsp+1C0h+var_178], r11d
0x1800fb65e  mov     [rsp+1C0h+var_180], r10
0x1800fb663  mov     [rsp+1C0h+var_188], rbx
0x1800fb668  mov     dword ptr [rsp+1C0h+var_190], r9d
0x1800fb66d  xor     r9d, r9d
0x1800fb670  mov     dword ptr [rsp+1C0h+var_198], r15d
0x1800fb675  mov     [rsp+1C0h+var_1A0], rax
0x1800fb67a  call    ?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x1800fb67f  xor     eax, eax
0x1800fb681  mov     ebx, eax
0x1800fb683  mov     [rbp+0B0h+pv], rax
0x1800fb687  mov     [r14+0D8h], rax
0x1800fb68e  btr     dword ptr [rdi], 0Ah
0x1800fb692  mov     byte ptr [rbp+0B0h+arg_28], r15b
0x1800fb699  test    [r14-518h], r12d
0x1800fb6a0  jnz     short loc_1800FB6BC
0x1800fb6a2  mov     ecx, 4
0x1800fb6a7  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x1800fb6ad  xor     edi, edi
0x1800fb6af  test    eax, eax
0x1800fb6b1  jnz     short loc_1800FB6BE
0x1800fb6b3  xor     ecx, ecx; unsigned __int16 *
0x1800fb6b5  call    ?VirtualTab_NewTabShouldExit@@YAXPEBG@Z; VirtualTab_NewTabShouldExit(ushort const *)
0x1800fb6ba  jmp     short loc_1800FB6D6
0x1800fb6bc  xor     edi, edi
0x1800fb6be  cmp     [r14-618h], rdi
0x1800fb6c5  jz      short loc_1800FB6D6
0x1800fb6c7  test    dword ptr [r14-518h], 4000000h
0x1800fb6d2  cmovnz  r13d, r15d
0x1800fb6d6  test    [r14-518h], r12d
0x1800fb6dd  jnz     short loc_1800FB6EE
0x1800fb6df  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800fb6e5  test    al, al
0x1800fb6e7  jz      short loc_1800FB6EE
0x1800fb6e9  call    ?DualEngineNavigationFailed@@YAXXZ; DualEngineNavigationFailed(void)
0x1800fb6ee  test    rbx, rbx
0x1800fb6f1  jz      short loc_1800FB705
0x1800fb6f3  mov     rcx, rbx; pbindinfo
0x1800fb6f6  call    cs:__imp_ReleaseBindInfo
0x1800fb6fc  mov     rcx, rbx; hMem
0x1800fb6ff  call    cs:__imp_LocalFree
0x1800fb705  xor     ebx, ebx
0x1800fb707  lea     rdi, CGID_Explorer
0x1800fb70e  cmp     byte ptr [rbp+0B0h+arg_28], bl
0x1800fb714  jz      short loc_1800FB75A
0x1800fb716  mov     rcx, [r14-618h]
0x1800fb71d  test    rcx, rcx
0x1800fb720  jz      short loc_1800FB75A
0x1800fb722  test    [r14-518h], r12d
0x1800fb729  jnz     short loc_1800FB75A
  ... truncated ...
```
