# CDocObjectHost::CDOHBindStatusCallback::_TransferToFileDownload(int,int,ulong,int *,int *)

- ea: `0x1801063a4`
- end: `0x180106bbb`
- name: `?_TransferToFileDownload@CDOHBindStatusCallback@CDocObjectHost@@AEAA_NHHKPEAH0@Z`
- size: `2071`
- prototype: `bool __usercall@<al>(CDocObjectHost::CDOHBindStatusCallback *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, int *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006b200`

## callees

- `0x180005030`
- `0x180046a50`
- `0x180069118`
- `0x180097dfc`
- `0x1800ef620`
- `0x1800f431c`
- `0x1800f4928`
- `0x180101c60`
- `0x180101d70`
- `0x18010321c`
- `0x1801063a4`
- `0x1801f0ea0`
- `0x1801f0f00`
- `0x1801f7694`
- `0x180594010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1801065bc`
- `KERNEL32!LocalAlloc` at `0x1801065bc`
- `KERNEL32!LocalFree` at `0x18010688f`
- `KERNEL32!LocalFree` at `0x18010688f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106863`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106956`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106b8d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106863`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106956`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180106b8d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180106996`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069a6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069c6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180106996`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069a6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801069c6`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1801063f1`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18010643c`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180106825`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180106b53`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1801063f1`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18010643c`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180106825`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180106b53`
- `urlmon!ReleaseBindInfo` at `0x180106880`
- `urlmon!ReleaseBindInfo` at `0x180106880`

## pseudocode

```c
char __fastcall CDocObjectHost::CDOHBindStatusCallback::_TransferToFileDownload(
        CDocObjectHost::CDOHBindStatusCallback *this,
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
  DOWNLOADSECPARAM *v27; // rax
  __int64 v28; // r9
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
  int *v50; // [rsp+28h] [rbp-E8h]
  int v51; // [rsp+78h] [rbp-98h]
  void *v52; // [rsp+80h] [rbp-90h]
  CInterThreadMarshal *v53; // [rsp+88h] [rbp-88h]
  bool v54; // [rsp+90h] [rbp-80h] BYREF
  bool v55; // [rsp+91h] [rbp-7Fh] BYREF
  int v56; // [rsp+94h] [rbp-7Ch] BYREF
  void *ppv; // [rsp+98h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-70h] BYREF
  unsigned int v59[2]; // [rsp+A8h] [rbp-68h] BYREF
  HWND v60; // [rsp+B0h] [rbp-60h] BYREF
  __int128 v61; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-48h]
  int v63; // [rsp+D0h] [rbp-40h]
  unsigned __int16 *v64; // [rsp+D8h] [rbp-38h] BYREF
  unsigned __int16 *v65; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int16 *v66; // [rsp+E8h] [rbp-28h] BYREF
  _DWORD v67[8]; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v68; // [rsp+110h] [rbp+0h]
  __int64 v69; // [rsp+118h] [rbp+8h]
  unsigned __int16 *v70; // [rsp+120h] [rbp+10h]
  unsigned __int16 *v71; // [rsp+128h] [rbp+18h]
  unsigned __int16 *v72; // [rsp+130h] [rbp+20h]
  int v73; // [rsp+138h] [rbp+28h]
  _BYTE v74[128]; // [rsp+140h] [rbp+30h] BYREF
  char v77; // [rsp+1F8h] [rbp+E8h]

  pv = 0;
  *a6 = 0;
  if ( !(unsigned int)IsIExploreProcess() || (v8 = 0, LCIEIsComponentSharedFlagValueSet_FromComponentThread(0x1000000u)) )
  {
    v8 = 1;
    CDocObjectHost::CDOHBindStatusCallback::BeginningTransaction(
      (CDocObjectHost::CDOHBindStatusCallback *)((char *)this + 24),
      0,
      0,
      0,
      (unsigned __int16 **)&pv);
    v56 = 0;
    v60 = 0;
    v55 = 0;
    v77 = 0;
    v54 = 0;
    v63 = LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u);
    v9 = 0;
    v64 = 0;
    v10 = v63 == 0;
    v65 = 0;
    v66 = 0;
    ppv = 0;
    if ( (int)CDocObjectHost::QueryInterface(
                (CDocObjectHost::CDOHBindStatusCallback *)((char *)this - 1952),
                &GUID_00000000_0000_0000_c000_000000000046,
                &ppv) < 0 )
      ATL::AtlComPtrAssign((struct IUnknown **)&ppv, 0);
    CDocObjectHost::CDOHBindStatusCallback::_GetDownloadContextInfo(
      this,
      v10,
      (struct IUnknown *)ppv,
      &v54,
      &v55,
      &v56,
      &v60,
      &v64,
      &v65,
      &v66);
    v11 = *((_BYTE *)this + 208);
    v12 = (_DWORD *)((char *)this + 188);
    v13 = *((_DWORD *)this - 326);
    v14 = 0;
    v15 = *((_DWORD *)this - 303);
    v16 = 0;
    *(_QWORD *)v59 = (char *)this + 188;
    v17 = (8 * v13) >> 31;
    if ( !v11 )
    {
      v16 = a2;
      v18 = __CFSHR__(*v12, 11);
      *(_QWORD *)v59 = (char *)this + 188;
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
    v67[1] = v22;
    v67[2] = v21;
    v67[0] = !v23;
    v68 = *((_QWORD *)this + 17);
    v69 = *((_QWORD *)this + 19);
    v70 = v64;
    v71 = v65;
    v72 = v66;
    v67[3] = v20;
    v67[4] = v19;
    v67[5] = v14;
    v67[6] = v16;
    v67[7] = v17;
    v73 = v15;
    if ( *((_DWORD *)this + 43) != 1 )
    {
      if ( !*((_QWORD *)this - 136) )
        goto LABEL_48;
      v25 = v56;
      if ( ppv )
      {
        v40 = *((_QWORD *)this - 195);
        if ( v40 )
        {
          v62 = 0;
          v61 = 0;
          (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v40 + 32LL))(v40, &CGID_ShellDocView, 69);
          if ( (_WORD)v61 != 11 || !WORD4(v61) )
          {
            if ( !a3 )
            {
              v41 = pv;
              if ( *((_BYTE *)this + 208) )
                v41 = 0;
              v42 = (unsigned __int16 *)*((_QWORD *)this + 16);
              v43 = *((_DWORD *)this + 44);
              v44 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v74, (const struct DOWNLOADSECPARAM *)v67);
              CDownloadUtilities::OpenUI(
                *((_QWORD *)this - 136),
                *((IBindCtx **)this - 135),
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
                v56,
                v51,
                v52,
                v45);
              v77 = 1;
              if ( !*((_BYTE *)this + 208) )
                pv = 0;
              v49 = *(_DWORD **)v59;
              v25 = v56;
              *((_QWORD *)this + 27) = 0;
              *v49 &= ~0x400u;
            }
            if ( (*((_DWORD *)this - 326) & 0x40000) != 0 || LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
            {
              if ( *((_QWORD *)this - 195) && (*((_DWORD *)this - 326) & 0x4000000) != 0 )
                v9 = 1;
            }
            else
            {
              VirtualTab_NewTabShouldExit(0);
            }
            if ( (*((_DWORD *)this - 326) & 0x40000) == 0 && IsDualEngineProcess() )
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
      if ( v77 )
      {
        v36 = *((_QWORD *)this - 195);
        if ( v36 )
        {
          if ( (*((_DWORD *)this - 326) & 0x40000) == 0 && (!v63 && !v54 || v55) )
            (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v36 + 32LL))(v36, &CGID_Explorer, 104);
        }
      }
      if ( v9 )
      {
        if ( this != (CDocObjectHost::CDOHBindStatusCallback *)1952 )
        {
          v37 = *((_QWORD *)this - 195);
          if ( v37 )
          {
            if ( v25 )
            {
              v62 = 0;
              v61 = 0;
              DWORD2(v61) = v25;
              LOWORD(v61) = 3;
              (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v37 + 32LL))(v37, &CGID_Explorer, 105);
            }
            v38 = IsDualEngineProcess();
            (*(void (__fastcall **)(_QWORD, const GUID *, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this - 195)
                                                                                         + 32LL))(
              *((_QWORD *)this - 195),
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
    v59[0] = 0;
    v24 = (BINDINFO *)LocalAlloc(0x40u, 0x80u);
    if ( !v24 )
    {
      v8 = 0;
LABEL_48:
      CoTaskMemFree(pv);
      CoTaskMemFree(v64);
      CoTaskMemFree(v65);
      CoTaskMemFree(v66);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppv);
      return v8;
    }
    v24->cbSize = 128;
    CDocObjectHost::CDOHBindStatusCallback::GetBindInfo(this, v59, v24);
    v25 = v56;
    if ( !ppv
      || (v26 = *((_QWORD *)this - 195)) == 0
      || (v62 = 0,
          v50 = (int *)&v61,
          v61 = 0,
          (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v26 + 32LL))(v26, &CGID_ShellDocView, 69),
          (_WORD)v61 == 11)
      && WORD4(v61)
      || a3 )
    {
LABEL_34:
      ReleaseBindInfo(v24);
      LocalFree(v24);
      goto LABEL_35;
    }
    if ( v24->dwBindVerb )
    {
      v29 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v74, (const struct DOWNLOADSECPARAM *)v67);
      v32 = v59[0] | v31;
      v33 = (IBindCtx *)*((_QWORD *)this + 8);
      v53 = v34;
      v35 = (unsigned __int16 *)*((_QWORD *)this + 16);
      if ( *((_BYTE *)this + 208) )
      {
        CDownloadUtilities::OpenUI(
          *((_QWORD *)this - 136),
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
          v60,
          v25,
          v51,
          v52,
          v53);
LABEL_24:
        *((_QWORD *)this + 27) = 0;
        *v12 &= ~0x400u;
        v77 = 1;
        if ( (*((_DWORD *)this - 326) & 0x40000) != 0 || LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
        {
          if ( *((_QWORD *)this - 195) && (*((_DWORD *)this - 326) & 0x4000000) != 0 )
            v9 = 1;
        }
        else
        {
          VirtualTab_NewTabShouldExit(0);
        }
        if ( (*((_DWORD *)this - 326) & 0x40000) == 0 && IsDualEngineProcess() )
          DualEngineNavigationFailed();
        if ( !v24 )
          goto LABEL_35;
        goto LABEL_34;
      }
      CDownloadUtilities::OpenUI(
        *((_QWORD *)this - 136),
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
        v60,
        v25,
        v51,
        v52,
        v53);
      v24 = 0;
    }
    else
    {
      v27 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v74, (const struct DOWNLOADSECPARAM *)v67);
      LODWORD(v50) = v28;
      CDownloadUtilities::OpenUIURL(
        *((_QWORD *)this + 16),
        0,
        v27,
        0,
        pv,
        v50,
        *((_DWORD *)this + 44) & 0x800000,
        v28,
        *((_QWORD *)this + 16),
        *((_DWORD *)this - 332),
        ppv,
        v28,
        a4,
        v60,
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
0x1801063a4  mov     [rsp-8+arg_0], rbx
0x1801063a9  mov     [rsp-8+arg_18], r9d
0x1801063ae  mov     [rsp-8+arg_10], r8d
0x1801063b3  push    rbp
0x1801063b4  push    rsi
0x1801063b5  push    rdi
0x1801063b6  push    r12
0x1801063b8  push    r13
0x1801063ba  push    r14
0x1801063bc  push    r15
0x1801063be  lea     rbp, [rsp-80h]
0x1801063c3  sub     rsp, 190h
0x1801063ca  mov     rax, [rbp+0B0h+arg_28]
0x1801063d1  xor     r12d, r12d
0x1801063d4  mov     ebx, edx
0x1801063d6  mov     [rbp+0B0h+pv], r12
0x1801063da  mov     r14, rcx
0x1801063dd  mov     [rax], r12d
0x1801063e0  call    ?IsIExploreProcess@@YAHXZ; IsIExploreProcess(void)
0x1801063e5  test    eax, eax
0x1801063e7  jz      short loc_180106405
0x1801063e9  mov     ecx, 1000000h
0x1801063ee  mov     r15b, r12b
0x1801063f1  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x1801063f8  nop     dword ptr [rax+rax+00h]
0x1801063fd  test    eax, eax
0x1801063ff  jz      loc_1801069DB
0x180106405  lea     rax, [rbp+0B0h+pv]
0x180106409  xor     r9d, r9d; unsigned int
0x18010640c  lea     rcx, [r14+18h]; this
0x180106410  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 **
0x180106415  xor     r8d, r8d; unsigned __int16 *
0x180106418  xor     edx, edx; unsigned __int16 *
0x18010641a  mov     r15d, 1
0x180106420  call    ?BeginningTransaction@CDOHBindStatusCallback@CDocObjectHost@@MEAAJPEBG0KPEAPEAG@Z; CDocObjectHost::CDOHBindStatusCallback::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)
0x180106425  lea     ecx, [r15+3]
0x180106429  mov     [rbp+0B0h+var_12C], r12d
0x18010642d  mov     [rbp+0B0h+var_110], r12
0x180106431  mov     [rbp+0B0h+var_12F], r12b
0x180106435  mov     byte ptr [rbp+0B0h+arg_28], r12b
0x18010643c  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x180106443  nop     dword ptr [rax+rax+00h]
0x180106448  lea     r8, [rbp+0B0h+ppv]; ppv
0x18010644c  mov     [rbp+0B0h+var_130], r12b
0x180106450  test    eax, eax
0x180106452  mov     [rbp+0B0h+var_F0], eax
0x180106455  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18010645c  movzx   r13d, r12b
0x180106460  lea     rcx, [r14-7A0h]; this
0x180106467  mov     [rbp+0B0h+var_E8], r12
0x18010646b  setz    dil
0x18010646f  mov     [rbp+0B0h+var_E0], r12
0x180106473  mov     [rbp+0B0h+var_D8], r12
0x180106477  mov     [rbp+0B0h+ppv], r12
0x18010647b  call    ?QueryInterface@CDocObjectHost@@UEAAJAEBU_GUID@@PEAPEAX@Z; CDocObjectHost::QueryInterface(_GUID const &,void * *)
0x180106480  test    eax, eax
0x180106482  jns     short loc_18010648F
0x180106484  xor     edx, edx; struct IUnknown *
0x180106486  lea     rcx, [rbp+0B0h+ppv]; struct IUnknown **
0x18010648a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18010648f  mov     r8, [rbp+0B0h+ppv]; struct IUnknown *
0x180106493  lea     rax, [rbp+0B0h+var_D8]
0x180106497  mov     [rsp+1C0h+var_178], rax; unsigned __int16 **
0x18010649c  lea     r9, [rbp+0B0h+var_130]; bool *
0x1801064a0  lea     rax, [rbp+0B0h+var_E0]
0x1801064a4  mov     dl, dil; bool
0x1801064a7  mov     [rsp+1C0h+var_180], rax; unsigned __int16 **
0x1801064ac  mov     rcx, r14; this
0x1801064af  lea     rax, [rbp+0B0h+var_E8]
0x1801064b3  mov     [rsp+1C0h+var_188], rax; unsigned __int16 **
0x1801064b8  lea     rax, [rbp+0B0h+var_110]
0x1801064bc  mov     [rsp+1C0h+var_190], rax; HWND *
0x1801064c1  lea     rax, [rbp+0B0h+var_12C]
0x1801064c5  mov     [rsp+1C0h+var_198], rax; int *
0x1801064ca  lea     rax, [rbp+0B0h+var_12F]
0x1801064ce  mov     [rsp+1C0h+var_1A0], rax; bool *
0x1801064d3  call    ?_GetDownloadContextInfo@CDOHBindStatusCallback@CDocObjectHost@@AEAAX_NPEAUIUnknown@@PEA_N2PEAJPEAPEAUHWND__@@PEAPEAG55@Z; CDocObjectHost::CDOHBindStatusCallback::_GetDownloadContextInfo(bool,IUnknown *,bool *,bool *,long *,HWND__ * *,ushort * *,ushort * *,ushort * *)
0x1801064d8  mov     al, [r14+0D0h]
0x1801064df  lea     rdi, [r14+0BCh]
0x1801064e6  mov     edx, [r14-518h]
0x1801064ed  xor     ecx, ecx
0x1801064ef  mov     r12d, [r14-4BCh]
0x1801064f6  mov     esi, ecx
0x1801064f8  mov     qword ptr [rbp+0B0h+var_118], rdi
0x1801064fc  lea     r11d, ds:0[rdx*8]
0x180106504  sar     r11d, 1Fh
0x180106508  test    al, al
0x18010650a  cmovz   esi, ebx
0x18010650d  xor     ebx, ebx
0x18010650f  test    al, al
0x180106511  jnz     short loc_18010651E
0x180106513  mov     ecx, [rdi]
0x180106515  shr     ecx, 0Bh
0x180106518  mov     qword ptr [rbp+0B0h+var_118], rdi
0x18010651c  sbb     ecx, ecx
0x18010651e  mov     r8d, [rdi]
0x180106521  mov     r9d, edx
0x180106524  shr     r8d, 0Ah
0x180106528  sbb     r8d, r8d
0x18010652b  shr     r9d, 6
0x18010652f  sbb     r9d, r9d
0x180106532  shr     edx, 0Ah
0x180106535  sbb     edx, edx
0x180106537  test    al, al
0x180106539  jz      short loc_180106545
0x18010653b  movzx   r10d, byte ptr [r14+0D1h]
0x180106543  jmp     short loc_180106548
0x180106545  mov     r10d, ebx
0x180106548  cmp     [r14+0D2h], bl
0x18010654f  mov     eax, ebx
0x180106551  mov     [rbp+0B0h+var_CC], r10d
0x180106555  setnz   al
0x180106558  mov     [rbp+0B0h+var_C8], edx
0x18010655b  mov     [rbp+0B0h+var_D0], eax
0x18010655e  mov     rax, [r14+88h]
0x180106565  mov     [rbp+0B0h+var_B0], rax
0x180106569  mov     rax, [r14+98h]
0x180106570  mov     [rbp+0B0h+var_A8], rax
0x180106574  mov     rax, [rbp+0B0h+var_E8]
0x180106578  mov     [rbp+0B0h+var_A0], rax
0x18010657c  mov     rax, [rbp+0B0h+var_E0]
0x180106580  mov     [rbp+0B0h+var_98], rax
0x180106584  mov     rax, [rbp+0B0h+var_D8]
0x180106588  mov     [rbp+0B0h+var_90], rax
0x18010658c  mov     [rbp+0B0h+var_C4], r9d
0x180106590  mov     [rbp+0B0h+var_C0], r8d
0x180106594  mov     [rbp+0B0h+var_BC], ecx
0x180106597  mov     [rbp+0B0h+var_B8], esi
0x18010659a  mov     [rbp+0B0h+var_B4], r11d
0x18010659e  mov     [rbp+0B0h+var_88], r12d
0x1801065a2  cmp     [r14+0ACh], r15d
0x1801065a9  jnz     loc_1801069FA
0x1801065af  mov     esi, 80h
0x1801065b4  mov     [rbp+0B0h+var_118], ebx
0x1801065b7  mov     edx, esi; uBytes
0x1801065b9  lea     ecx, [rsi-40h]; uFlags
0x1801065bc  call    cs:__imp_LocalAlloc
0x1801065c3  nop     dword ptr [rax+rax+00h]
0x1801065c8  mov     rbx, rax
0x1801065cb  xor     eax, eax
0x1801065cd  test    rbx, rbx
0x1801065d0  jnz     short loc_1801065DA
0x1801065d2  mov     r15b, al
0x1801065d5  jmp     loc_180106992
0x1801065da  mov     r8, rbx; struct _tagBINDINFO *
0x1801065dd  mov     [rbx], esi
0x1801065df  lea     rdx, [rbp+0B0h+var_118]; unsigned int *
0x1801065e3  mov     rcx, r14; this
0x1801065e6  call    ?GetBindInfo@CDOHBindStatusCallback@CDocObjectHost@@MEAAJPEAKPEAU_tagBINDINFO@@@Z; CDocObjectHost::CDOHBindStatusCallback::GetBindInfo(ulong *,_tagBINDINFO *)
0x1801065eb  mov     esi, [rbp+0B0h+var_12C]
0x1801065ee  xor     r8d, r8d
0x1801065f1  mov     r12d, 40000h
0x1801065f7  cmp     [rbp+0B0h+ppv], r8
0x1801065fb  jz      loc_18010687D
0x180106601  mov     rcx, [r14-618h]
0x180106608  test    rcx, rcx
0x18010660b  jz      loc_18010687D
0x180106611  xor     eax, eax
0x180106613  lea     rdx, [rbp+0B0h+var_108]
0x180106617  mov     [rbp+0B0h+var_F8], rax
0x18010661b  xorps   xmm0, xmm0
0x18010661e  mov     [rsp+1C0h+var_198], rdx
0x180106623  xor     r9d, r9d
0x180106626  movups  [rbp+0B0h+var_108], xmm0
0x18010662a  mov     rax, [rcx]
0x18010662d  lea     rdx, CGID_ShellDocView
0x180106634  mov     [rsp+1C0h+var_1A0], r8
0x180106639  lea     r8d, [r9+45h]
0x18010663d  mov     rax, [rax+20h]
0x180106641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106646  xor     r9d, r9d
0x180106649  cmp     word ptr [rbp+0B0h+var_108], 0Bh
0x18010664e  jnz     short loc_18010665B
0x180106650  cmp     word ptr [rbp+0B0h+var_108+8], r9w
0x180106655  jnz     loc_18010687D
0x18010665b  cmp     [rbp+0B0h+arg_10], r9d
0x180106662  jnz     loc_18010687D
0x180106668  lea     rdx, [rbp+0B0h+var_D0]; struct DOWNLOADSECPARAM *
0x18010666c  mov     r10, [r14+0D8h]
0x180106673  lea     rcx, [rbp+0B0h+var_80]; this
0x180106677  cmp     [rbx+2Ch], r9d
0x18010667b  jnz     loc_180106711
0x180106681  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x180106686  mov     rcx, [rbp+0B0h+var_110]
0x18010668a  mov     r10, rax
0x18010668d  mov     rdx, [rbp+0B0h+ppv]
0x180106691  mov     rax, [r14+0D8h]
0x180106698  mov     r11, [r14+80h]
0x18010669f  mov     r8d, [r14+0B0h]
0x1801066a6  mov     [rsp+1C0h+var_138], rax
0x1801066ae  and     r8d, 800000h
0x1801066b5  mov     rax, [rbp+0B0h+pv]
0x1801066b9  mov     [rsp+1C0h+var_150], esi
0x1801066bd  mov     [rsp+1C0h+var_158], rcx
0x1801066c2  mov     ecx, [rbp+0B0h+arg_18]
0x1801066c8  mov     [rsp+1C0h+var_160], ecx
0x1801066cc  mov     rcx, r11
0x1801066cf  mov     [rsp+1C0h+var_168], r9d
0x1801066d4  mov     [rsp+1C0h+var_170], rdx
0x1801066d9  mov     edx, [r14-530h]
0x1801066e0  mov     dword ptr [rsp+1C0h+var_178], edx
0x1801066e4  xor     edx, edx
0x1801066e6  mov     [rsp+1C0h+var_180], r11
0x1801066eb  mov     [rsp+1C0h+var_188], r9
0x1801066f0  mov     dword ptr [rsp+1C0h+var_190], r8d
0x1801066f5  mov     r8, r10
0x1801066f8  mov     dword ptr [rsp+1C0h+var_198], r9d
0x1801066fd  xor     r9d, r9d
0x180106700  mov     [rsp+1C0h+var_1A0], rax
0x180106705  call    ?OpenUIURL@CDownloadUtilities@@SAJPEBGPEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@0IPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@0PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUIURL(ushort const *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x18010670a  xor     eax, eax
0x18010670c  jmp     loc_180106801
0x180106711  mov     r9d, [r14+0B0h]
0x180106718  mov     r11d, [r14-530h]
0x18010671f  and     r9d, 800000h
0x180106726  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x18010672b  or      r9d, [rbp+0B0h+var_118]
0x18010672f  cmp     byte ptr [r14+0D0h], 0
0x180106737  mov     rdx, [r14+40h]
0x18010673b  mov     [rsp+1C0h+var_138], r10
0x180106743  mov     r10, [r14+80h]
0x18010674a  mov     [rsp+1C0h+var_150], esi
0x18010674e  jz      short loc_1801067A5
0x180106750  mov     r8, [rbp+0B0h+var_110]
0x180106754  mov     ecx, [rbp+0B0h+arg_18]
0x18010675a  mov     [rsp+1C0h+var_158], r8
0x18010675f  mov     r8, [rbp+0B0h+ppv]
0x180106763  mov     [rsp+1C0h+var_160], ecx
0x180106767  xor     ecx, ecx
0x180106769  mov     [rsp+1C0h+var_168], ecx
0x18010676d  mov     [rsp+1C0h+var_170], r8
0x180106772  mov     r8, rax
0x180106775  mov     dword ptr [rsp+1C0h+var_178], r11d
0x18010677a  mov     [rsp+1C0h+var_180], r10
0x18010677f  mov     [rsp+1C0h+var_188], rcx
0x180106784  mov     dword ptr [rsp+1C0h+var_190], r9d
0x180106789  xor     r9d, r9d
0x18010678c  mov     dword ptr [rsp+1C0h+var_198], ecx
0x180106790  mov     [rsp+1C0h+var_1A0], rcx
0x180106795  mov     rcx, [r14-440h]
0x18010679c  call    ?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x1801067a1  xor     eax, eax
0x1801067a3  jmp     short loc_180106805
0x1801067a5  mov     rcx, [rbp+0B0h+var_110]
0x1801067a9  mov     r8, rax
0x1801067ac  mov     rax, [rbp+0B0h+pv]
0x1801067b0  mov     [rsp+1C0h+var_158], rcx
0x1801067b5  mov     ecx, [rbp+0B0h+arg_18]
0x1801067bb  mov     [rsp+1C0h+var_160], ecx
0x1801067bf  mov     rcx, [rbp+0B0h+ppv]
0x1801067c3  mov     [rsp+1C0h+var_168], 0
0x1801067cb  mov     [rsp+1C0h+var_170], rcx
0x1801067d0  mov     rcx, [r14-440h]
0x1801067d7  mov     dword ptr [rsp+1C0h+var_178], r11d
0x1801067dc  mov     [rsp+1C0h+var_180], r10
0x1801067e1  mov     [rsp+1C0h+var_188], rbx
0x1801067e6  mov     dword ptr [rsp+1C0h+var_190], r9d
0x1801067eb  xor     r9d, r9d
0x1801067ee  mov     dword ptr [rsp+1C0h+var_198], r15d
0x1801067f3  mov     [rsp+1C0h+var_1A0], rax
0x1801067f8  call    ?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z; CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)
0x1801067fd  xor     eax, eax
0x1801067ff  mov     ebx, eax
0x180106801  mov     [rbp+0B0h+pv], rax
0x180106805  mov     [r14+0D8h], rax
0x18010680c  btr     dword ptr [rdi], 0Ah
0x180106810  mov     byte ptr [rbp+0B0h+arg_28], r15b
0x180106817  test    [r14-518h], r12d
0x18010681e  jnz     short loc_180106840
0x180106820  mov     ecx, 4
0x180106825  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x18010682c  nop     dword ptr [rax+rax+00h]
0x180106831  xor     edi, edi
0x180106833  test    eax, eax
0x180106835  jnz     short loc_180106842
0x180106837  xor     ecx, ecx; unsigned __int16 *
0x180106839  call    ?VirtualTab_NewTabShouldExit@@YAXPEBG@Z; VirtualTab_NewTabShouldExit(ushort const *)
0x18010683e  jmp     short loc_18010685A
0x180106840  xor     edi, edi
0x180106842  cmp     [r14-618h], rdi
0x180106849  jz      short loc_18010685A
0x18010684b  test    dword ptr [r14-518h], 4000000h
0x180106856  cmovnz  r13d, r15d
0x18010685a  test    [r14-518h], r12d
0x180106861  jnz     short loc_180106878
0x180106863  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18010686a  nop     dword ptr [rax+rax+00h]
0x18010686f  test    al, al
0x180106871  jz      short loc_180106878
0x180106873  call    ?DualEngineNavigationFailed@@YAXXZ; DualEngineNavigationFailed(void)
0x180106878  test    rbx, rbx
0x18010687b  jz      short loc_18010689B
0x18010687d  mov     rcx, rbx; pbindinfo
0x180106880  call    cs:__imp_ReleaseBindInfo
0x180106887  nop     dword ptr [rax+rax+00h]
0x18010688c  mov     rcx, rbx; hMem
0x18010688f  call    cs:__imp_LocalFree
0x180106896  nop     dword ptr [rax+rax+00h]
0x18010689b  xor     ebx, ebx
0x18010689d  lea     rdi, CGID_Explorer
  ... truncated ...
```
