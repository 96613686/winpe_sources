# getInnerUserProperties(IXMLDOMNodeList *,ulong,ushort const *,_PEAP_USER_PROPERTIES *,_PEAP_CONN_PROPERTIES *,ulong *,uchar * *,ulong *)

- ea: `0x18005ff50`
- end: `0x1800604dd`
- name: `?getInnerUserProperties@@YAKPEAUIXMLDOMNodeList@@KPEBGPEAU_PEAP_USER_PROPERTIES@@PEAU_PEAP_CONN_PROPERTIES@@PEAKPEAPEAE4@Z`
- size: `1421`
- prototype: `unsigned int __fastcall(struct IXMLDOMNodeList *, unsigned int, const unsigned __int16 *, struct _PEAP_USER_PROPERTIES *, struct _PEAP_CONN_PROPERTIES *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800604e4`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x18000f690`
- `0x180012130`
- `0x180017330`
- `0x18001de48`
- `0x18001e530`
- `0x18001f020`
- `0x1800200b4`
- `0x180021abc`
- `0x18005ff50`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltow` at `0x1800600b1`
- `api-ms-win-crt-private-l1-1-0!_o__ltow` at `0x1800600b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800601e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800601e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006027c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006027c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060472`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800600f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800601f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006028a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800600f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800601f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006028a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060051`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800600d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006039f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060051`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800600d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006039f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060440`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006044e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800604ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060440`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006044e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800604ad`

## string_xrefs

- `0x18006021e`: `RasEapCreateUserProperties`

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
0x18005ff50  mov     rax, rsp
0x18005ff53  mov     [rax+20h], r9
0x18005ff57  mov     [rax+18h], r8
0x18005ff5b  mov     [rax+10h], edx
0x18005ff5e  push    rbp
0x18005ff5f  push    rbx
0x18005ff60  push    rsi
0x18005ff61  push    rdi
0x18005ff62  push    r12
0x18005ff64  push    r13
0x18005ff66  push    r14
0x18005ff68  push    r15
0x18005ff6a  lea     rbp, [rax-47h]
0x18005ff6e  sub     rsp, 0A8h
0x18005ff75  xor     r12d, r12d
0x18005ff78  mov     ebx, r12d
0x18005ff7b  mov     r14d, r12d
0x18005ff7e  mov     [rbp+3Fh+lpLibFileName], r12
0x18005ff82  mov     [rbp+3Fh+var_70], r12
0x18005ff86  mov     [rbp+3Fh+var_58], r12
0x18005ff8a  mov     [rbp+3Fh+Source], r12
0x18005ff8e  mov     dword ptr [rbp+3Fh+uBytes], r12d
0x18005ff92  mov     [rbp+3Fh+var_78], r12
0x18005ff96  mov     [rbp+3Fh+var_50], r12
0x18005ff9a  mov     rax, [rbp+3Fh+arg_38]
0x18005ffa1  mov     [rax], r12d
0x18005ffa4  mov     rax, [rbp+3Fh+arg_30]
0x18005ffa8  mov     [rax], r12
0x18005ffab  mov     rax, [rbp+3Fh+arg_28]
0x18005ffaf  mov     [rax], r12d
0x18005ffb2  mov     rax, [rcx]
0x18005ffb5  lea     rdx, [rbp+3Fh+var_78]
0x18005ffb9  mov     rax, [rax+48h]
0x18005ffbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffc2  cmp     [rbp+3Fh+var_78], r12
0x18005ffc6  jnz     short loc_18005FFF9
0x18005ffc8  lea     rdi, WPP_GLOBAL_Control
0x18005ffcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ffd6  cmp     rcx, rdi
0x18005ffd9  jz      loc_1800604B4
0x18005ffdf  mov     edx, 0D5h
0x18005ffe4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005ffeb  mov     rcx, [rcx+10h]
0x18005ffef  call    WPP_SF_
0x18005fff4  jmp     loc_1800604B4
0x18005fff9  mov     rcx, [rbp+3Fh+arg_20]; struct _PEAP_CONN_PROPERTIES *
0x18005fffd  cmp     [rcx+8], r12d
0x180060001  jnz     short loc_180060021
0x180060003  lea     rdi, WPP_GLOBAL_Control
0x18006000a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060011  cmp     rcx, rdi
0x180060014  jz      loc_1800604B4
0x18006001a  mov     edx, 0D6h
0x18006001f  jmp     short loc_18005FFE4
0x180060021  lea     rdx, [rbp+3Fh+var_70]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x180060025  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x18006002a  mov     ebx, eax
0x18006002c  test    eax, eax
0x18006002e  jnz     loc_18006047A
0x180060034  mov     rax, [rbp+3Fh+var_70]
0x180060038  test    rax, rax
0x18006003b  jz      loc_18006047A
0x180060041  mov     ebx, [rax+8]
0x180060044  mov     [rbp+3Fh+var_80], ebx
0x180060047  mov     edx, 42h ; 'B'; uBytes
0x18006004c  lea     edi, [rdx-2]
0x18006004f  mov     ecx, edi; uFlags
0x180060051  call    cs:__imp_LocalAlloc
0x180060057  mov     r13, rax
0x18006005a  test    rax, rax
0x18006005d  jnz     short loc_1800600A0
0x18006005f  lea     ebx, [rdi-32h]
0x180060062  lea     rdi, WPP_GLOBAL_Control
0x180060069  cmp     cs:WPP_GLOBAL_Control, rdi
0x180060070  jz      loc_1800604B4
0x180060076  call    cs:__imp_GetLastError
0x18006007c  mov     edx, 0D8h
0x180060081  mov     r9d, eax
0x180060084  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006008b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060092  mov     rcx, [rcx+10h]
0x180060096  call    WPP_SF_d
0x18006009b  jmp     loc_1800604B4
0x1800600a0  mov     rsi, r12
0x1800600a3  mov     r15, r12
0x1800600a6  mov     r8d, 0Ah; Radix
0x1800600ac  mov     rdx, r13; Buffer
0x1800600af  mov     ecx, ebx; Value
0x1800600b1  call    cs:__imp__ltow
0x1800600b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800600bb  inc     rax
0x1800600be  cmp     [r13+rax*2+0], r12w
0x1800600c4  jnz     short loc_1800600BB
0x1800600c6  lea     rax, ds:46h[rax*2]
0x1800600ce  mov     ebx, eax
0x1800600d0  mov     edx, eax; uBytes
0x1800600d2  mov     ecx, edi; uFlags
0x1800600d4  call    cs:__imp_LocalAlloc
0x1800600da  mov     r12, rax
0x1800600dd  test    rax, rax
0x1800600e0  jnz     short loc_180060113
0x1800600e2  lea     ebx, [rax+0Eh]
0x1800600e5  lea     rdi, WPP_GLOBAL_Control
0x1800600ec  cmp     cs:WPP_GLOBAL_Control, rdi
0x1800600f3  jz      loc_18006043D
0x1800600f9  call    cs:__imp_GetLastError
0x1800600ff  mov     edx, 0D9h
0x180060104  mov     r9d, eax
0x180060107  mov     rcx, cs:WPP_GLOBAL_Control
0x18006010e  jmp     loc_18006042D
0x180060113  lea     r8, aBaseeapuserpro_2; "baseeapuserpropertiesv1:Type[. = "
0x18006011a  mov     rdx, rbx; unsigned __int64
0x18006011d  mov     rcx, r12; unsigned __int16 *
0x180060120  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180060125  mov     r9d, eax
0x180060128  test    eax, eax
0x18006012a  js      loc_180060400
0x180060130  mov     r8, r13; unsigned __int16 *
0x180060133  mov     rdx, rbx; unsigned __int64
0x180060136  mov     rcx, r12; unsigned __int16 *
0x180060139  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18006013e  mov     r9d, eax
0x180060141  test    eax, eax
0x180060143  js      loc_180060400
0x180060149  lea     r8, asc_180086514; "]"
0x180060150  mov     rdx, rbx; unsigned __int64
0x180060153  mov     rcx, r12; unsigned __int16 *
0x180060156  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18006015b  mov     r9d, eax
0x18006015e  test    eax, eax
0x180060160  js      loc_180060400
0x180060166  lea     r8, [rbp+3Fh+var_50]; struct IXMLDOMNode **
0x18006016a  mov     rdx, r12; unsigned __int16 *
0x18006016d  mov     rcx, [rbp+3Fh+var_78]; struct IXMLDOMNode *
0x180060171  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180060176  mov     ebx, eax
0x180060178  test    eax, eax
0x18006017a  jz      short loc_1800601C2
0x18006017c  lea     rdi, WPP_GLOBAL_Control
0x180060183  mov     rcx, cs:WPP_GLOBAL_Control
0x18006018a  cmp     rcx, rdi
0x18006018d  jz      short loc_1800601A8
0x18006018f  mov     edx, 0DBh
0x180060194  mov     r9d, [rbp+3Fh+var_80]
0x180060198  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006019f  mov     rcx, [rcx+10h]
0x1800601a3  call    WPP_SF_d
0x1800601a8  mov     eax, ebx
0x1800601aa  and     eax, 1FFF0000h
0x1800601af  cmp     eax, 70000h
0x1800601b4  jnz     loc_18006043D
0x1800601ba  movzx   ebx, bx
0x1800601bd  jmp     loc_18006043D
0x1800601c2  lea     rdx, [rbp+3Fh+lpLibFileName]; unsigned __int16 **
0x1800601c6  mov     rcx, r13; unsigned __int16 *
0x1800601c9  call    ?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z; getLibraryPathForEapTypeId(ushort const *,ushort * *)
0x1800601ce  mov     ebx, eax
0x1800601d0  mov     r14, [rbp+3Fh+lpLibFileName]
0x1800601d4  test    eax, eax
0x1800601d6  jnz     loc_18006043D
0x1800601dc  xor     r8d, r8d; dwFlags
0x1800601df  xor     edx, edx; hFile
0x1800601e1  mov     rcx, r14; lpLibFileName
0x1800601e4  call    cs:__imp_LoadLibraryExW
0x1800601ea  mov     rsi, rax
0x1800601ed  test    rax, rax
0x1800601f0  jnz     short loc_18006021E
0x1800601f2  call    cs:__imp_GetLastError
0x1800601f8  mov     ebx, eax
0x1800601fa  lea     rdi, WPP_GLOBAL_Control
0x180060201  mov     rcx, cs:WPP_GLOBAL_Control
0x180060208  cmp     rcx, rdi
0x18006020b  jz      loc_18006043D
0x180060211  mov     edx, 0DCh
0x180060216  mov     r9d, eax
0x180060219  jmp     loc_18006042D
0x18006021e  lea     rdx, aRaseapcreateus_1; "RasEapCreateUserProperties"
0x180060225  mov     rcx, rsi; hModule
0x180060228  call    cs:__imp_GetProcAddress
0x18006022e  mov     rbx, rax
0x180060231  test    rax, rax
0x180060234  jnz     short loc_180060272
0x180060236  call    cs:__imp_GetLastError
0x18006023c  mov     ebx, eax
0x18006023e  lea     rdi, WPP_GLOBAL_Control
0x180060245  mov     rcx, cs:WPP_GLOBAL_Control
0x18006024c  cmp     rcx, rdi
0x18006024f  jz      loc_18006043D
0x180060255  mov     edx, 0DDh
0x18006025a  mov     r9, r14
0x18006025d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180060264  mov     rcx, [rcx+10h]
0x180060268  call    WPP_SF_S
0x18006026d  jmp     loc_18006043D
0x180060272  lea     rdx, ProcName; "RasEapFreeMemory"
0x180060279  mov     rcx, rsi; hModule
0x18006027c  call    cs:__imp_GetProcAddress
0x180060282  mov     r15, rax
0x180060285  test    rax, rax
0x180060288  jnz     short loc_1800602B0
0x18006028a  call    cs:__imp_GetLastError
0x180060290  mov     ebx, eax
0x180060292  lea     rdi, WPP_GLOBAL_Control
0x180060299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800602a0  cmp     rcx, rdi
0x1800602a3  jz      loc_18006043D
0x1800602a9  mov     edx, 0DEh
0x1800602ae  jmp     short loc_18006025A
0x1800602b0  lea     rdi, WPP_GLOBAL_Control
0x1800602b7  mov     rax, [rbp+3Fh+arg_18]
0x1800602bb  test    rax, rax
0x1800602be  jz      short loc_180060335
0x1800602c0  lea     rdx, [rbp+3Fh+var_58]; struct _PEAP_ENTRY_USER_PROPERTIES **
0x1800602c4  mov     rcx, rax; struct _PEAP_USER_PROPERTIES *
0x1800602c7  call    ?PeapGetFirstEntryUserProp@@YAKPEAU_PEAP_USER_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_USER_PROPERTIES@@@Z; PeapGetFirstEntryUserProp(_PEAP_USER_PROPERTIES *,_PEAP_ENTRY_USER_PROPERTIES * *)
0x1800602cc  test    eax, eax
0x1800602ce  jnz     short loc_180060311
0x1800602d0  mov     rcx, [rbp+3Fh+var_58]
0x1800602d4  test    rcx, rcx
0x1800602d7  jz      short loc_180060311
0x1800602d9  mov     r8d, [rcx+4]
0x1800602dd  sub     r8d, 13h
0x1800602e1  add     rcx, 10h
0x1800602e5  mov     rax, [rbp+3Fh+var_70]
0x1800602e9  mov     edx, [rax+4]
0x1800602ec  sub     edx, 0Fh
0x1800602ef  lea     r9, [rbp+3Fh+uBytes]
0x1800602f3  mov     [rsp+48h], r9
0x1800602f8  lea     r9, [rbp+3Fh+Source]
0x1800602fc  mov     [rsp+0E0h+var_A0], r9
0x180060301  mov     dword ptr [rsp+0E0h+var_A8], r8d
0x180060306  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x18006030b  mov     dword ptr [rsp+0E0h+var_B8], edx
0x18006030f  jmp     short loc_180060366
0x180060311  mov     rcx, cs:WPP_GLOBAL_Control
0x180060318  cmp     rcx, rdi
0x18006031b  jz      short loc_180060335
0x18006031d  mov     edx, 0DFh
0x180060322  mov     r9d, eax
0x180060325  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006032c  mov     rcx, [rcx+10h]
0x180060330  call    WPP_SF_d
0x180060335  mov     rax, [rbp+3Fh+var_70]
0x180060339  mov     ecx, [rax+4]
0x18006033c  sub     ecx, 0Fh
0x18006033f  lea     rdx, [rbp+3Fh+uBytes]
0x180060343  mov     [rsp+48h], rdx
0x180060348  lea     rdx, [rbp+3Fh+Source]
0x18006034c  mov     [rsp+0E0h+var_A0], rdx
0x180060351  mov     dword ptr [rsp+0E0h+var_A8], 0
0x180060359  mov     qword ptr [rsp+0E0h+var_B0], 0
0x180060362  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x180060366  add     rax, 0Ch
0x18006036a  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18006036f  mov     r9, [rbp+3Fh+var_78]
0x180060373  mov     r8, [rbp+3Fh+arg_10]
0x180060377  mov     edx, [rbp+3Fh+arg_8]
0x18006037a  mov     ecx, [rbp+3Fh+var_80]
0x18006037d  mov     rax, rbx
0x180060380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060385  mov     ebx, eax
0x180060387  test    eax, eax
0x180060389  jnz     loc_18006043D
0x18006038f  mov     eax, dword ptr [rbp+3Fh+uBytes]
0x180060392  test    eax, eax
0x180060394  jz      loc_18006043D
0x18006039a  mov     edx, eax; uBytes
0x18006039c  lea     ecx, [rbx+40h]; uFlags
0x18006039f  call    cs:__imp_LocalAlloc
0x1800603a5  mov     rcx, [rbp+3Fh+arg_30]
0x1800603a9  mov     [rcx], rax
0x1800603ac  test    rax, rax
0x1800603af  jnz     short loc_1800603D7
0x1800603b1  lea     ebx, [rax+0Eh]
0x1800603b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800603bb  cmp     rcx, rdi
0x1800603be  jz      short loc_18006043D
0x1800603c0  mov     edx, 0E0h
0x1800603c5  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800603cc  mov     rcx, [rcx+10h]
0x1800603d0  call    WPP_SF_
0x1800603d5  jmp     short loc_18006043D
0x1800603d7  mov     edx, dword ptr [rbp+3Fh+uBytes]; DestinationSize
0x1800603da  mov     r9d, edx; SourceSize
0x1800603dd  mov     r8, [rbp+3Fh+Source]; Source
0x1800603e1  mov     rcx, rax; Destination
0x1800603e4  call    memcpy_s_0
0x1800603e9  mov     eax, dword ptr [rbp+3Fh+uBytes]
0x1800603ec  mov     rcx, [rbp+3Fh+arg_38]
0x1800603f3  mov     [rcx], eax
0x1800603f5  mov     eax, [rbp+3Fh+var_80]
0x1800603f8  mov     rcx, [rbp+3Fh+arg_28]
0x1800603fc  mov     [rcx], eax
0x1800603fe  jmp     short loc_18006043D
0x180060400  mov     eax, r9d
0x180060403  and     eax, 1FFF0000h
0x180060408  movzx   ebx, r9w
0x18006040c  cmp     eax, 70000h
0x180060411  cmovnz  ebx, r9d
0x180060415  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
