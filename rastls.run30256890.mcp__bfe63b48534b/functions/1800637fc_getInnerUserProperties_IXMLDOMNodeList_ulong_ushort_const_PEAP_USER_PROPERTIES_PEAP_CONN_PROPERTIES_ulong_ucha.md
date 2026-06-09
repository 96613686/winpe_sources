# getInnerUserProperties(IXMLDOMNodeList *,ulong,ushort const *,_PEAP_USER_PROPERTIES *,_PEAP_CONN_PROPERTIES *,ulong *,uchar * *,ulong *)

- ea: `0x1800637fc`
- end: `0x180063dea`
- name: `?getInnerUserProperties@@YAKPEAUIXMLDOMNodeList@@KPEBGPEAU_PEAP_USER_PROPERTIES@@PEAU_PEAP_CONN_PROPERTIES@@PEAKPEAPEAE4@Z`
- size: `1518`
- prototype: `unsigned int __fastcall(struct IXMLDOMNodeList *, unsigned int, const unsigned __int16 *, struct _PEAP_USER_PROPERTIES *, struct _PEAP_CONN_PROPERTIES *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063df0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x1800104b0`
- `0x180013330`
- `0x180018670`
- `0x18001f9bc`
- `0x1800201a0`
- `0x180020d80`
- `0x180021e74`
- `0x1800244ec`
- `0x1800637fc`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltow` at `0x180063969`
- `api-ms-win-crt-private-l1-1-0!_o__ltow` at `0x180063969`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063aae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063aae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063b5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063b5e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063d72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063d72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800638fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063992`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063c8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800638fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063992`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063c8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063db3`

## string_xrefs

- `0x180063af4`: `RasEapCreateUserProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall getInnerUserProperties(
        struct IXMLDOMNodeList *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _PEAP_USER_PROPERTIES *a4,
        struct _PEAP_CONN_PROPERTIES *a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  unsigned int FirstEntryConnProp; // ebx
  WCHAR *v9; // r14
  struct _EAPTLS_CONTROL_BLOCK *v10; // rcx
  __int64 v11; // rdx
  int v12; // ebx
  wchar_t *v13; // rax
  unsigned __int16 *v14; // r13
  DWORD LastError; // eax
  HMODULE v16; // rsi
  void (*v17)(void); // r15
  __int64 v18; // rax
  SIZE_T v19; // rbx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r12
  DWORD v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r9
  struct _EAPTLS_CONTROL_BLOCK *v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  HMODULE Library; // rax
  DWORD v30; // eax
  FARPROC ProcAddress; // rbx
  struct _EAPTLS_CONTROL_BLOCK *v32; // rcx
  __int64 v33; // rdx
  unsigned int FirstEntryUserProp; // eax
  unsigned int v35; // eax
  unsigned __int8 *v36; // rax
  unsigned int v38; // [rsp+68h] [rbp-41h]
  struct IXMLDOMNode *v39; // [rsp+70h] [rbp-39h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v40; // [rsp+78h] [rbp-31h] BYREF
  void *Source; // [rsp+80h] [rbp-29h] BYREF
  LPCWSTR lpLibFileName; // [rsp+88h] [rbp-21h] BYREF
  struct _PEAP_ENTRY_USER_PROPERTIES *v43; // [rsp+90h] [rbp-19h] BYREF
  struct IXMLDOMNode *v44[10]; // [rsp+98h] [rbp-11h] BYREF
  SIZE_T uBytes; // [rsp+F8h] [rbp+4Fh] BYREF
  unsigned int v46; // [rsp+100h] [rbp+57h]
  const unsigned __int16 *v47; // [rsp+108h] [rbp+5Fh]
  struct _PEAP_USER_PROPERTIES *v48; // [rsp+110h] [rbp+67h]

  v48 = a4;
  v47 = a3;
  v46 = a2;
  FirstEntryConnProp = 0;
  v9 = 0;
  lpLibFileName = 0;
  v40 = 0;
  v43 = 0;
  Source = 0;
  LODWORD(uBytes) = 0;
  v39 = 0;
  v44[0] = 0;
  *a8 = 0;
  *a7 = 0;
  *a6 = 0;
  ((void (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMNode **))a1->lpVtbl->nextNode)(a1, &v39);
  if ( v39 )
  {
    if ( !*((_DWORD *)a5 + 2) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_66;
      v11 = 214;
      goto LABEL_4;
    }
    FirstEntryConnProp = PeapGetFirstEntryConnProp(a5, &v40);
    if ( FirstEntryConnProp || !v40 )
    {
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_66;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        FirstEntryConnProp);
      goto LABEL_64;
    }
    v12 = *((_DWORD *)v40 + 2);
    v38 = v12;
    v13 = (wchar_t *)LocalAlloc(0x40u, 0x42u);
    v14 = v13;
    if ( !v13 )
    {
      FirstEntryConnProp = 14;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, LastError);
      }
      goto LABEL_66;
    }
    v16 = 0;
    v17 = 0;
    _ltow(v12, v13, 10);
    v18 = -1;
    do
      ++v18;
    while ( v14[v18] );
    v19 = (unsigned int)(2 * v18 + 70);
    v20 = (unsigned __int16 *)LocalAlloc(0x40u, v19);
    v21 = v20;
    if ( !v20 )
    {
      FirstEntryConnProp = 14;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v22 = GetLastError();
        v23 = 217;
        v24 = v22;
        v25 = WPP_GLOBAL_Control;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v25 + 2), v23, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v24);
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    v26 = StringCbCopyW(v20, v19, L"baseeapuserpropertiesv1:Type[. = ");
    v24 = (unsigned int)v26;
    if ( v26 < 0
      || (v27 = StringCbCatW(v21, v19, v14), v24 = (unsigned int)v27, v27 < 0)
      || (v28 = StringCbCatW(v21, v19, L"]"), v24 = (unsigned int)v28, v28 < 0) )
    {
      FirstEntryConnProp = (unsigned __int16)v24;
      if ( (v24 & 0x1FFF0000) != 0x70000 )
        FirstEntryConnProp = v24;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_55;
      v23 = 218;
      goto LABEL_54;
    }
    FirstEntryConnProp = getSingleNode(v39, v21, v44);
    if ( FirstEntryConnProp )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v38);
      if ( (FirstEntryConnProp & 0x1FFF0000) == 0x70000 )
        FirstEntryConnProp = (unsigned __int16)FirstEntryConnProp;
      goto LABEL_55;
    }
    FirstEntryConnProp = getLibraryPathForEapTypeId(v14, (unsigned __int16 **)&lpLibFileName);
    v9 = (WCHAR *)lpLibFileName;
    if ( FirstEntryConnProp )
      goto LABEL_55;
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    v16 = Library;
    if ( !Library )
    {
      v30 = GetLastError();
      FirstEntryConnProp = v30;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v23 = 220;
        v24 = v30;
        goto LABEL_54;
      }
LABEL_55:
      LocalFree(v14);
      if ( v21 )
        LocalFree(v21);
      if ( v17 && Source )
        v17();
      if ( v16 )
        FreeLibrary(v16);
LABEL_64:
      if ( v9 )
        LocalFree(v9);
      goto LABEL_66;
    }
    ProcAddress = GetProcAddress(Library, "RasEapCreateUserProperties");
    if ( !ProcAddress )
    {
      FirstEntryConnProp = GetLastError();
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_55;
      v33 = 221;
LABEL_33:
      WPP_SF_S(*((_QWORD *)v32 + 2), v33, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v9);
      goto LABEL_55;
    }
    v17 = (void (*)(void))GetProcAddress(v16, "RasEapFreeMemory");
    if ( !v17 )
    {
      FirstEntryConnProp = GetLastError();
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_55;
      v33 = 222;
      goto LABEL_33;
    }
    if ( v48 )
    {
      FirstEntryUserProp = PeapGetFirstEntryUserProp(v48, &v43);
      if ( !FirstEntryUserProp && v43 )
      {
        v35 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const unsigned __int16 *, struct IXMLDOMNode *, char *, int, char *, int, void **, SIZE_T *))ProcAddress)(
                v38,
                v46,
                v47,
                v39,
                (char *)v40 + 12,
                *((_DWORD *)v40 + 1) - 15,
                (char *)v43 + 16,
                *((_DWORD *)v43 + 1) - 19,
                &Source,
                &uBytes);
LABEL_44:
        FirstEntryConnProp = v35;
        if ( !v35 && (_DWORD)uBytes )
        {
          v36 = (unsigned __int8 *)LocalAlloc(v35 + 64, (unsigned int)uBytes);
          *a7 = v36;
          if ( v36 )
          {
            memcpy_s_0(v36, (unsigned int)uBytes, Source, (unsigned int)uBytes);
            *a8 = uBytes;
            *a6 = v38;
          }
          else
          {
            FirstEntryConnProp = 14;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
          }
        }
        goto LABEL_55;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          223,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          FirstEntryUserProp);
    }
    v35 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const unsigned __int16 *, struct IXMLDOMNode *, char *, int, _QWORD, _DWORD, void **, SIZE_T *))ProcAddress)(
            v38,
            v46,
            v47,
            v39,
            (char *)v40 + 12,
            *((_DWORD *)v40 + 1) - 15,
            0,
            0,
            &Source,
            &uBytes);
    goto LABEL_44;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v11 = 213;
LABEL_4:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  }
LABEL_66:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v44);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v39);
  return FirstEntryConnProp;
}

```

## disassembly

```asm
0x1800637fc  mov     rax, rsp
0x1800637ff  mov     [rax+20h], r9
0x180063803  mov     [rax+18h], r8
0x180063807  mov     [rax+10h], edx
0x18006380a  push    rbp
0x18006380b  push    rbx
0x18006380c  push    rsi
0x18006380d  push    rdi
0x18006380e  push    r12
0x180063810  push    r13
0x180063812  push    r14
0x180063814  push    r15
0x180063816  lea     rbp, [rax-47h]
0x18006381a  sub     rsp, 0A8h
0x180063821  xor     r12d, r12d
0x180063824  mov     ebx, r12d
0x180063827  mov     r14d, r12d
0x18006382a  mov     [rbp+3Fh+lpLibFileName], r12
0x18006382e  mov     [rbp+3Fh+var_70], r12
0x180063832  mov     [rbp+3Fh+var_58], r12
0x180063836  mov     [rbp+3Fh+Source], r12
0x18006383a  mov     dword ptr [rbp+3Fh+uBytes], r12d
0x18006383e  mov     [rbp+3Fh+var_78], r12
0x180063842  mov     [rbp+3Fh+var_50], r12
0x180063846  mov     rax, [rbp+3Fh+arg_38]
0x18006384d  mov     [rax], r12d
0x180063850  mov     rax, [rbp+3Fh+arg_30]
0x180063854  mov     [rax], r12
0x180063857  mov     rax, [rbp+3Fh+arg_28]
0x18006385b  mov     [rax], r12d
0x18006385e  mov     rax, [rcx]
0x180063861  lea     rdx, [rbp+3Fh+var_78]
0x180063865  mov     rax, [rax+48h]
0x180063869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006386e  cmp     [rbp+3Fh+var_78], r12
0x180063872  jnz     short loc_1800638A5
0x180063874  lea     rdi, WPP_GLOBAL_Control
0x18006387b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063882  cmp     rcx, rdi
0x180063885  jz      loc_180063DC0
0x18006388b  mov     edx, 0D5h
0x180063890  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063897  mov     rcx, [rcx+10h]
0x18006389b  call    WPP_SF_
0x1800638a0  jmp     loc_180063DC0
0x1800638a5  mov     rcx, [rbp+3Fh+arg_20]; struct _PEAP_CONN_PROPERTIES *
0x1800638a9  cmp     [rcx+8], r12d
0x1800638ad  jnz     short loc_1800638CD
0x1800638af  lea     rdi, WPP_GLOBAL_Control
0x1800638b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800638bd  cmp     rcx, rdi
0x1800638c0  jz      loc_180063DC0
0x1800638c6  mov     edx, 0D6h
0x1800638cb  jmp     short loc_180063890
0x1800638cd  lea     rdx, [rbp+3Fh+var_70]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x1800638d1  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x1800638d6  mov     ebx, eax
0x1800638d8  test    eax, eax
0x1800638da  jnz     loc_180063D80
0x1800638e0  mov     rax, [rbp+3Fh+var_70]
0x1800638e4  test    rax, rax
0x1800638e7  jz      loc_180063D80
0x1800638ed  mov     ebx, [rax+8]
0x1800638f0  mov     [rbp+3Fh+var_80], ebx
0x1800638f3  mov     edx, 42h ; 'B'; uBytes
0x1800638f8  lea     edi, [rdx-2]
0x1800638fb  mov     ecx, edi; uFlags
0x1800638fd  call    cs:__imp_LocalAlloc
0x180063904  nop     dword ptr [rax+rax+00h]
0x180063909  mov     r13, rax
0x18006390c  test    rax, rax
0x18006390f  jnz     short loc_180063958
0x180063911  lea     ebx, [rdi-32h]
0x180063914  lea     rdi, WPP_GLOBAL_Control
0x18006391b  cmp     cs:WPP_GLOBAL_Control, rdi
0x180063922  jz      loc_180063DC0
0x180063928  call    cs:__imp_GetLastError
0x18006392f  nop     dword ptr [rax+rax+00h]
0x180063934  mov     edx, 0D8h
0x180063939  mov     r9d, eax
0x18006393c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063943  mov     rcx, cs:WPP_GLOBAL_Control
0x18006394a  mov     rcx, [rcx+10h]
0x18006394e  call    WPP_SF_d
0x180063953  jmp     loc_180063DC0
0x180063958  mov     rsi, r12
0x18006395b  mov     r15, r12
0x18006395e  mov     r8d, 0Ah; Radix
0x180063964  mov     rdx, r13; Buffer
0x180063967  mov     ecx, ebx; Value
0x180063969  call    cs:__imp__ltow
0x180063970  nop     dword ptr [rax+rax+00h]
0x180063975  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063979  inc     rax
0x18006397c  cmp     [r13+rax*2+0], r12w
0x180063982  jnz     short loc_180063979
0x180063984  lea     rax, ds:46h[rax*2]
0x18006398c  mov     ebx, eax
0x18006398e  mov     edx, eax; uBytes
0x180063990  mov     ecx, edi; uFlags
0x180063992  call    cs:__imp_LocalAlloc
0x180063999  nop     dword ptr [rax+rax+00h]
0x18006399e  mov     r12, rax
0x1800639a1  test    rax, rax
0x1800639a4  jnz     short loc_1800639DD
0x1800639a6  lea     ebx, [rax+0Eh]
0x1800639a9  lea     rdi, WPP_GLOBAL_Control
0x1800639b0  cmp     cs:WPP_GLOBAL_Control, rdi
0x1800639b7  jz      loc_180063D31
0x1800639bd  call    cs:__imp_GetLastError
0x1800639c4  nop     dword ptr [rax+rax+00h]
0x1800639c9  mov     edx, 0D9h
0x1800639ce  mov     r9d, eax
0x1800639d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800639d8  jmp     loc_180063D21
0x1800639dd  lea     r8, aBaseeapuserpro_2; "baseeapuserpropertiesv1:Type[. = "
0x1800639e4  mov     rdx, rbx; unsigned __int64
0x1800639e7  mov     rcx, r12; unsigned __int16 *
0x1800639ea  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800639ef  mov     r9d, eax
0x1800639f2  test    eax, eax
0x1800639f4  js      loc_180063CF4
0x1800639fa  mov     r8, r13; unsigned __int16 *
0x1800639fd  mov     rdx, rbx; unsigned __int64
0x180063a00  mov     rcx, r12; unsigned __int16 *
0x180063a03  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180063a08  mov     r9d, eax
0x180063a0b  test    eax, eax
0x180063a0d  js      loc_180063CF4
0x180063a13  lea     r8, asc_18008C524; "]"
0x180063a1a  mov     rdx, rbx; unsigned __int64
0x180063a1d  mov     rcx, r12; unsigned __int16 *
0x180063a20  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180063a25  mov     r9d, eax
0x180063a28  test    eax, eax
0x180063a2a  js      loc_180063CF4
0x180063a30  lea     r8, [rbp+3Fh+var_50]; struct IXMLDOMNode **
0x180063a34  mov     rdx, r12; unsigned __int16 *
0x180063a37  mov     rcx, [rbp+3Fh+var_78]; struct IXMLDOMNode *
0x180063a3b  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180063a40  mov     ebx, eax
0x180063a42  test    eax, eax
0x180063a44  jz      short loc_180063A8C
0x180063a46  lea     rdi, WPP_GLOBAL_Control
0x180063a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a54  cmp     rcx, rdi
0x180063a57  jz      short loc_180063A72
0x180063a59  mov     edx, 0DBh
0x180063a5e  mov     r9d, [rbp+3Fh+var_80]
0x180063a62  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063a69  mov     rcx, [rcx+10h]
0x180063a6d  call    WPP_SF_d
0x180063a72  mov     eax, ebx
0x180063a74  and     eax, 1FFF0000h
0x180063a79  cmp     eax, 70000h
0x180063a7e  jnz     loc_180063D31
0x180063a84  movzx   ebx, bx
0x180063a87  jmp     loc_180063D31
0x180063a8c  lea     rdx, [rbp+3Fh+lpLibFileName]; unsigned __int16 **
0x180063a90  mov     rcx, r13; unsigned __int16 *
0x180063a93  call    ?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z; getLibraryPathForEapTypeId(ushort const *,ushort * *)
0x180063a98  mov     ebx, eax
0x180063a9a  mov     r14, [rbp+3Fh+lpLibFileName]
0x180063a9e  test    eax, eax
0x180063aa0  jnz     loc_180063D31
0x180063aa6  xor     r8d, r8d; dwFlags
0x180063aa9  xor     edx, edx; hFile
0x180063aab  mov     rcx, r14; lpLibFileName
0x180063aae  call    cs:__imp_LoadLibraryExW
0x180063ab5  nop     dword ptr [rax+rax+00h]
0x180063aba  mov     rsi, rax
0x180063abd  test    rax, rax
0x180063ac0  jnz     short loc_180063AF4
0x180063ac2  call    cs:__imp_GetLastError
0x180063ac9  nop     dword ptr [rax+rax+00h]
0x180063ace  mov     ebx, eax
0x180063ad0  lea     rdi, WPP_GLOBAL_Control
0x180063ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ade  cmp     rcx, rdi
0x180063ae1  jz      loc_180063D31
0x180063ae7  mov     edx, 0DCh
0x180063aec  mov     r9d, eax
0x180063aef  jmp     loc_180063D21
0x180063af4  lea     rdx, aRaseapcreateus_1; "RasEapCreateUserProperties"
0x180063afb  mov     rcx, rsi; hModule
0x180063afe  call    cs:__imp_GetProcAddress
0x180063b05  nop     dword ptr [rax+rax+00h]
0x180063b0a  mov     rbx, rax
0x180063b0d  test    rax, rax
0x180063b10  jnz     short loc_180063B54
0x180063b12  call    cs:__imp_GetLastError
0x180063b19  nop     dword ptr [rax+rax+00h]
0x180063b1e  mov     ebx, eax
0x180063b20  lea     rdi, WPP_GLOBAL_Control
0x180063b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b2e  cmp     rcx, rdi
0x180063b31  jz      loc_180063D31
0x180063b37  mov     edx, 0DDh
0x180063b3c  mov     r9, r14
0x180063b3f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063b46  mov     rcx, [rcx+10h]
0x180063b4a  call    WPP_SF_S
0x180063b4f  jmp     loc_180063D31
0x180063b54  lea     rdx, ProcName; "RasEapFreeMemory"
0x180063b5b  mov     rcx, rsi; hModule
0x180063b5e  call    cs:__imp_GetProcAddress
0x180063b65  nop     dword ptr [rax+rax+00h]
0x180063b6a  mov     r15, rax
0x180063b6d  test    rax, rax
0x180063b70  jnz     short loc_180063B9E
0x180063b72  call    cs:__imp_GetLastError
0x180063b79  nop     dword ptr [rax+rax+00h]
0x180063b7e  mov     ebx, eax
0x180063b80  lea     rdi, WPP_GLOBAL_Control
0x180063b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b8e  cmp     rcx, rdi
0x180063b91  jz      loc_180063D31
0x180063b97  mov     edx, 0DEh
0x180063b9c  jmp     short loc_180063B3C
0x180063b9e  lea     rdi, WPP_GLOBAL_Control
0x180063ba5  mov     rax, [rbp+3Fh+arg_18]
0x180063ba9  test    rax, rax
0x180063bac  jz      short loc_180063C23
0x180063bae  lea     rdx, [rbp+3Fh+var_58]; struct _PEAP_ENTRY_USER_PROPERTIES **
0x180063bb2  mov     rcx, rax; struct _PEAP_USER_PROPERTIES *
0x180063bb5  call    ?PeapGetFirstEntryUserProp@@YAKPEAU_PEAP_USER_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_USER_PROPERTIES@@@Z; PeapGetFirstEntryUserProp(_PEAP_USER_PROPERTIES *,_PEAP_ENTRY_USER_PROPERTIES * *)
0x180063bba  test    eax, eax
0x180063bbc  jnz     short loc_180063BFF
0x180063bbe  mov     rcx, [rbp+3Fh+var_58]
0x180063bc2  test    rcx, rcx
0x180063bc5  jz      short loc_180063BFF
0x180063bc7  mov     r8d, [rcx+4]
0x180063bcb  sub     r8d, 13h
0x180063bcf  add     rcx, 10h
0x180063bd3  mov     rax, [rbp+3Fh+var_70]
0x180063bd7  mov     edx, [rax+4]
0x180063bda  sub     edx, 0Fh
0x180063bdd  lea     r9, [rbp+3Fh+uBytes]
0x180063be1  mov     [rsp+48h], r9
0x180063be6  lea     r9, [rbp+3Fh+Source]
0x180063bea  mov     [rsp+0E0h+var_A0], r9
0x180063bef  mov     dword ptr [rsp+0E0h+var_A8], r8d
0x180063bf4  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180063bf9  mov     dword ptr [rsp+0E0h+var_B8], edx
0x180063bfd  jmp     short loc_180063C54
0x180063bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c06  cmp     rcx, rdi
0x180063c09  jz      short loc_180063C23
0x180063c0b  mov     edx, 0DFh
0x180063c10  mov     r9d, eax
0x180063c13  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063c1a  mov     rcx, [rcx+10h]
0x180063c1e  call    WPP_SF_d
0x180063c23  mov     rax, [rbp+3Fh+var_70]
0x180063c27  mov     ecx, [rax+4]
0x180063c2a  sub     ecx, 0Fh
0x180063c2d  lea     rdx, [rbp+3Fh+uBytes]
0x180063c31  mov     [rsp+48h], rdx
0x180063c36  lea     rdx, [rbp+3Fh+Source]
0x180063c3a  mov     [rsp+0E0h+var_A0], rdx
0x180063c3f  mov     dword ptr [rsp+0E0h+var_A8], 0
0x180063c47  mov     qword ptr [rsp+0E0h+var_B0], 0
0x180063c50  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x180063c54  add     rax, 0Ch
0x180063c58  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180063c5d  mov     r9, [rbp+3Fh+var_78]
0x180063c61  mov     r8, [rbp+3Fh+arg_10]
0x180063c65  mov     edx, [rbp+3Fh+arg_8]
0x180063c68  mov     ecx, [rbp+3Fh+var_80]
0x180063c6b  mov     rax, rbx
0x180063c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c73  mov     ebx, eax
0x180063c75  test    eax, eax
0x180063c77  jnz     loc_180063D31
0x180063c7d  mov     eax, dword ptr [rbp+3Fh+uBytes]
0x180063c80  test    eax, eax
0x180063c82  jz      loc_180063D31
0x180063c88  mov     edx, eax; uBytes
0x180063c8a  lea     ecx, [rbx+40h]; uFlags
0x180063c8d  call    cs:__imp_LocalAlloc
0x180063c94  nop     dword ptr [rax+rax+00h]
0x180063c99  mov     rcx, [rbp+3Fh+arg_30]
0x180063c9d  mov     [rcx], rax
0x180063ca0  test    rax, rax
0x180063ca3  jnz     short loc_180063CCB
0x180063ca5  lea     ebx, [rax+0Eh]
0x180063ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180063caf  cmp     rcx, rdi
0x180063cb2  jz      short loc_180063D31
0x180063cb4  mov     edx, 0E0h
0x180063cb9  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063cc0  mov     rcx, [rcx+10h]
0x180063cc4  call    WPP_SF_
0x180063cc9  jmp     short loc_180063D31
0x180063ccb  mov     edx, dword ptr [rbp+3Fh+uBytes]; DestinationSize
0x180063cce  mov     r9d, edx; SourceSize
0x180063cd1  mov     r8, [rbp+3Fh+Source]; Source
0x180063cd5  mov     rcx, rax; Destination
0x180063cd8  call    memcpy_s_0
0x180063cdd  mov     eax, dword ptr [rbp+3Fh+uBytes]
  ... truncated ...
```
