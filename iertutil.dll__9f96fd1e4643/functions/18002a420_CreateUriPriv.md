# CreateUriPriv

- ea: `0x18002a420`
- end: `0x18002aa4e`
- name: `CreateUriPriv`
- size: `1582`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64, int, int, __int64)`
- caller_count: `14`
- callee_count: `13`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002844c`
- `0x180028690`
- `0x180028940`
- `0x180029ef0`
- `0x18002a070`
- `0x18002a1d0`
- `0x18002a2e0`
- `0x18002a3a0`
- `0x18002a3e0`
- `0x18002ac04`
- `0x18002b740`
- `0x18002ca30`
- `0x18004c170`
- `0x18007e6ac`

## callees

- `0x180015f88`
- `0x1800170d0`
- `0x1800173a0`
- `0x180018410`
- `0x180028610`
- `0x18002a420`
- `0x18002bed8`
- `0x18002dc00`
- `0x18002e0e0`
- `0x18003d840`
- `0x1800488a4`
- `0x180049c98`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a7cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a9d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a9f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a7cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a9d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a9f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a6b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a7dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a9e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a9ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aa17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aa2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a6b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a7dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a9e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a9ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aa17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aa2f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18002a99c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18002a99c`

## pseudocode

```c
__int64 __fastcall CreateUriPriv(
        unsigned __int16 *a1,
        WCHAR *a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        int a6,
        int a7,
        struct IUri **a8)
{
  const WCHAR *v8; // rsi
  __int64 v9; // r12
  WCHAR *v10; // r13
  __int64 v11; // rbx
  __int64 v12; // r15
  __int64 v13; // r14
  signed int UriPrivNoCache; // edi
  int v15; // r8d
  const WCHAR *v16; // rdx
  const WCHAR *v17; // r9
  unsigned int v18; // edi
  unsigned __int64 v19; // kr00_8
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  void *v22; // rax
  unsigned __int16 *v23; // r10
  int v24; // edi
  unsigned int v25; // r15d
  struct IUri **v26; // r14
  void *v27; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v29; // rax
  bool v30; // zf
  int v31; // eax
  void *v32; // rbx
  HANDLE v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  int v36; // r12d
  ULONG v37; // ebx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  void *v41; // rbx
  HANDLE v42; // rax
  void *v43; // rbx
  HANDLE v44; // rax
  int ActivityId; // [rsp+20h] [rbp-E0h]
  int RelatedActivityId; // [rsp+28h] [rbp-D8h]
  int v48; // [rsp+48h] [rbp-B8h]
  char v49; // [rsp+50h] [rbp-B0h]
  unsigned int v50; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v51; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+64h] [rbp-9Ch] BYREF
  struct IUri **v53; // [rsp+68h] [rbp-98h]
  LPVOID v54; // [rsp+70h] [rbp-90h]
  unsigned __int64 v55; // [rsp+78h] [rbp-88h]
  void **v56; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+88h] [rbp-78h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  unsigned int v59; // [rsp+98h] [rbp-68h]
  int v60; // [rsp+9Ch] [rbp-64h]
  char v61; // [rsp+A0h] [rbp-60h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v63; // [rsp+B8h] [rbp-48h] BYREF
  int v64; // [rsp+C0h] [rbp-40h]
  LPVOID v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+D0h] [rbp-30h]
  LPVOID v67; // [rsp+D8h] [rbp-28h]
  int v68; // [rsp+E0h] [rbp-20h]
  char v69; // [rsp+E4h] [rbp-1Ch]
  unsigned int v70; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  char *v72; // [rsp+100h] [rbp+0h]
  int v73; // [rsp+108h] [rbp+8h]
  int v74; // [rsp+10Ch] [rbp+Ch]
  unsigned int *v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+118h] [rbp+18h]
  const WCHAR *v77; // [rsp+120h] [rbp+20h]
  int v78; // [rsp+128h] [rbp+28h]
  int v79; // [rsp+12Ch] [rbp+2Ch]
  WCHAR *v80; // [rsp+130h] [rbp+30h]
  int v81; // [rsp+138h] [rbp+38h]
  int v82; // [rsp+13Ch] [rbp+3Ch]
  int *v83; // [rsp+140h] [rbp+40h]
  __int64 v84; // [rsp+148h] [rbp+48h]

  v8 = a1;
  v9 = -1;
  v53 = a8;
  v10 = a2;
  v52 = a4;
  v50 = a3;
  *(_QWORD *)&EventDescriptor.Id = a5;
  if ( a1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
  }
  else
  {
    LODWORD(v11) = 0;
  }
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
  }
  else
  {
    LODWORD(v12) = 0;
  }
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a5 + 2 * v13) );
  }
  else
  {
    LODWORD(v13) = 0;
  }
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v49 = 0;
  v54 = a1;
  UriPrivNoCache = NormalizeUriCreateFlags(a3, &v50);
  if ( UriPrivNoCache >= 0 )
  {
    if ( !v8 || (v50 & 0x1000) != 0 || !(_DWORD)v11 )
      goto LABEL_37;
    if ( *v8 <= 0x20u || v8[(unsigned int)(v11 - 1)] <= 0x20u )
    {
      v55 = (unsigned int)v11;
    }
    else
    {
      v15 = 0;
      v16 = v8;
      v55 = (unsigned int)v11;
      v17 = &v8[(unsigned int)v11];
      if ( v8 >= v17 )
      {
LABEL_37:
        v24 = *(_DWORD *)&EventDescriptor.Id;
        v63 = v54;
        v56 = &CCreateUriHashMapKey<CUrlStringContainer<unsigned short>>::`vftable';
        lpMem = &v63;
        v66 = v12;
        v25 = v50;
        v60 = v52;
        v70 = v50;
        v68 = v13;
        v64 = v11;
        v69 = 0;
        v65 = v10;
        v67 = *(LPVOID *)&EventDescriptor.Id;
        v57 = 0;
        v59 = v50;
        v61 = 0;
        CCreateUriHashMapKeyBase::UpdateHash((CCreateUriHashMapKeyBase *)&v56);
        v26 = v53;
        if ( !v53 )
        {
          UriPrivNoCache = -2147024809;
          v56 = &CCreateUriHashMapKey<CUrlStringContainer<unsigned short>>::`vftable';
          if ( v61 )
          {
            v27 = lpMem;
            if ( lpMem )
            {
              CUrlStringContainer<unsigned short>::~CUrlStringContainer<unsigned short>(lpMem);
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v27);
            }
          }
          goto LABEL_78;
        }
        *v53 = 0;
        if ( v8 && (int)GetUriFromCache((struct CHashMapKey *)&v56, v26) >= 0 )
        {
          UriPrivNoCache = 0;
LABEL_64:
          v56 = &CCreateUriHashMapKey<CUrlStringContainer<unsigned short>>::`vftable';
          if ( v61 )
          {
            v34 = lpMem;
            if ( lpMem )
            {
              CUrlStringContainer<unsigned short>::~CUrlStringContainer<unsigned short>(lpMem);
              v35 = GetProcessHeap();
              HeapFree(v35, 0, v34);
            }
          }
          v56 = &CHashMapKey::`vftable';
          goto LABEL_78;
        }
        RelatedActivityId = v24;
        UriPrivNoCache = CreateUriPrivNoCache((unsigned __int16 *)v54, v11, v10, v25);
        if ( UriPrivNoCache >= 0 )
        {
          if ( v8
            && (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_URI_DISABLECACHE) )
          {
            AddUriToCache(*v26, ActivityId, RelatedActivityId, v25, v52, (int)v26, v48);
          }
          goto LABEL_64;
        }
        v56 = &CCreateUriHashMapKey<CUrlStringContainer<unsigned short>>::`vftable';
        if ( v61 )
        {
          v32 = lpMem;
          if ( lpMem )
          {
            CUrlStringContainer<unsigned short>::~CUrlStringContainer<unsigned short>(lpMem);
            v33 = GetProcessHeap();
            HeapFree(v33, 0, v32);
          }
        }
        v56 = &CHashMapKey::`vftable';
        goto LABEL_43;
      }
      while ( !v15 )
      {
        if ( *v16 == 9 || *v16 == 10 || *v16 == 13 )
          v15 = 1;
        if ( ++v16 >= v17 )
        {
          if ( !v15 )
            goto LABEL_37;
          v55 = (unsigned int)v11;
          break;
        }
      }
    }
    v51 = v11 + 1;
    v18 = v11 + 1;
    v19 = (unsigned int)(v11 + 1);
    v20 = 2 * v19;
    if ( !is_mul_ok(v19, 2u) )
      v20 = -1;
    v21 = GetProcessHeap();
    v22 = HeapAlloc(v21, 8u, v20);
    v54 = v22;
    if ( v22 )
    {
      v49 = 1;
      UriPrivNoCache = StringCchCopyNW((unsigned __int16 *)v22, v18, v8, v55);
      if ( UriPrivNoCache >= 0 )
      {
        PreProcessHTMLURI(v23, &v51, v50);
        LODWORD(v11) = v51;
        goto LABEL_37;
      }
    }
    else
    {
      UriPrivNoCache = -2147024882;
    }
  }
  v25 = v50;
  v26 = v53;
  if ( v53 )
LABEL_43:
    *v26 = 0;
  if ( UriPrivNoCache != -2147024809
    && UriPrivNoCache != -2147024882
    && (unsigned int)dword_180293010 > 5
    && (qword_180293020 & 0x20) != 0
    && (qword_180293028 & 0x20) == qword_180293028 )
  {
    v52 = v25;
    v51 = UriPrivNoCache;
    v83 = &v52;
    v84 = 4;
    if ( v10 )
    {
      v29 = -1;
      do
        v30 = v10[++v29] == 0;
      while ( !v30 );
      v31 = 2 * v29 + 2;
    }
    else
    {
      v10 = (WCHAR *)&word_1801758E4;
      v31 = 2;
    }
    v80 = v10;
    v81 = v31;
    v82 = 0;
    if ( v8 )
    {
      do
        v30 = v8[++v9] == 0;
      while ( !v30 );
      v36 = 2 * v9 + 2;
    }
    else
    {
      v8 = &word_1801758E4;
      v36 = 2;
    }
    v77 = v8;
    v75 = &v51;
    v37 = 0;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_180293018;
    v78 = v36;
    v79 = 0;
    v76 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 32;
    UserData.Size = (unsigned __int16)*off_180293018;
    v72 = byte_180286541;
    UserData.Reserved = 2;
    v73 = 52;
    v74 = 1;
    v50 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL)
      && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
    {
      v37 = 2;
    }
    EventWriteEx(RegHandle, &EventDescriptor, 0, v37, 0, 0, 6u, &UserData);
  }
LABEL_78:
  if ( v49 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v54);
  }
  if ( v69 )
  {
    v39 = v63;
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v39);
    v41 = v65;
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v41);
    v43 = v67;
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v43);
  }
  return (unsigned int)UriPrivNoCache;
}

```

## disassembly

```asm
0x18002a420  mov     r11, rsp
0x18002a423  push    rbp
0x18002a424  push    rbx
0x18002a425  push    rdi
0x18002a426  lea     rbp, [rsp-80h]
0x18002a42b  sub     rsp, 180h
0x18002a432  mov     rax, cs:__security_cookie
0x18002a439  xor     rax, rsp
0x18002a43c  mov     [rbp+90h+var_40], rax
0x18002a440  mov     rax, [rbp+90h+arg_20]
0x18002a447  mov     [r11+20h], rsi
0x18002a44b  mov     rsi, rcx
0x18002a44e  mov     rcx, [rbp+90h+arg_38]
0x18002a455  mov     [r11-20h], r12
0x18002a459  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18002a460  mov     [rsp+190h+var_128], rcx
0x18002a465  xor     ecx, ecx
0x18002a467  mov     [r11-28h], r13
0x18002a46b  mov     r13, rdx
0x18002a46e  mov     [rsp+190h+var_12C], r9d
0x18002a473  mov     [rsp+190h+var_138], r8d
0x18002a478  mov     qword ptr [rbp+90h+EventDescriptor.Id], rax
0x18002a47c  test    rsi, rsi
0x18002a47f  jz      short loc_18002A48F
0x18002a481  mov     rbx, r12
0x18002a484  inc     rbx
0x18002a487  cmp     [rsi+rbx*2], cx
0x18002a48b  jnz     short loc_18002A484
0x18002a48d  jmp     short loc_18002A491
0x18002a48f  mov     ebx, ecx
0x18002a491  mov     [rsp+190h+var_30], r15
0x18002a499  test    r13, r13
0x18002a49c  jz      short loc_18002A4AD
0x18002a49e  mov     r15, r12
0x18002a4a1  inc     r15
0x18002a4a4  cmp     [rdx+r15*2], cx
0x18002a4a9  jnz     short loc_18002A4A1
0x18002a4ab  jmp     short loc_18002A4B0
0x18002a4ad  mov     r15d, ecx
0x18002a4b0  mov     [rsp+190h+var_28], r14
0x18002a4b8  test    rax, rax
0x18002a4bb  jz      short loc_18002A4CC
0x18002a4bd  mov     r14, r12
0x18002a4c0  inc     r14
0x18002a4c3  cmp     [rax+r14*2], cx
0x18002a4c8  jnz     short loc_18002A4C0
0x18002a4ca  jmp     short loc_18002A4CF
0x18002a4cc  mov     r14d, ecx
0x18002a4cf  mov     [rbp+90h+var_D8], rcx
0x18002a4d3  lea     rdx, [rsp+190h+var_138]; unsigned int *
0x18002a4d8  mov     [rbp+90h+var_D0], ecx
0x18002a4db  mov     [rbp+90h+var_C8], rcx
0x18002a4df  mov     [rbp+90h+var_C0], ecx
0x18002a4e2  mov     [rbp+90h+var_B8], rcx
0x18002a4e6  mov     [rbp+90h+var_B0], ecx
0x18002a4e9  mov     [rbp+90h+var_AC], cl
0x18002a4ec  mov     [rbp+90h+var_A8], ecx
0x18002a4ef  mov     [rsp+190h+var_140], cl
0x18002a4f3  mov     ecx, r8d; unsigned int
0x18002a4f6  mov     [rsp+190h+var_120], rsi
0x18002a4fb  call    ?NormalizeUriCreateFlags@@YAJKPEAK@Z; NormalizeUriCreateFlags(ulong,ulong *)
0x18002a500  mov     edi, eax
0x18002a502  test    eax, eax
0x18002a504  js      loc_18002A6C2
0x18002a50a  test    rsi, rsi
0x18002a50d  jz      loc_18002A608
0x18002a513  test    [rsp+190h+var_138], 1000h
0x18002a51b  jnz     loc_18002A608
0x18002a521  test    ebx, ebx
0x18002a523  jz      loc_18002A608
0x18002a529  cmp     word ptr [rsi], 20h ; ' '
0x18002a52d  jbe     short loc_18002A58A
0x18002a52f  lea     eax, [rbx-1]
0x18002a532  cmp     word ptr [rsi+rax*2], 20h ; ' '
0x18002a537  jbe     short loc_18002A58A
0x18002a539  mov     r10d, ebx
0x18002a53c  xor     r8d, r8d
0x18002a53f  mov     rdx, rsi
0x18002a542  mov     [rsp+190h+var_118], r10
0x18002a547  lea     r9, [rsi+r10*2]
0x18002a54b  cmp     rsi, r9
0x18002a54e  jnb     loc_18002A608
0x18002a554  test    r8d, r8d
0x18002a557  jnz     short loc_18002A591
0x18002a559  movzx   ecx, word ptr [rdx]
0x18002a55c  sub     ecx, 9
0x18002a55f  jz      short loc_18002A56B
0x18002a561  sub     ecx, 1
0x18002a564  jz      short loc_18002A56B
0x18002a566  cmp     ecx, 3
0x18002a569  jnz     short loc_18002A571
0x18002a56b  mov     r8d, 1
0x18002a571  add     rdx, 2
0x18002a575  cmp     rdx, r9
0x18002a578  jb      short loc_18002A554
0x18002a57a  test    r8d, r8d
0x18002a57d  jz      loc_18002A608
0x18002a583  mov     [rsp+190h+var_118], r10
0x18002a588  jmp     short loc_18002A591
0x18002a58a  mov     eax, ebx
0x18002a58c  mov     [rsp+190h+var_118], rax
0x18002a591  lea     eax, [rbx+1]
0x18002a594  mov     [rsp+190h+var_130], eax
0x18002a598  mov     edi, eax
0x18002a59a  mov     eax, 2
0x18002a59f  mul     rdi
0x18002a5a2  mov     rbx, rax
0x18002a5a5  cmovb   rbx, r12
0x18002a5a9  call    cs:__imp_GetProcessHeap
0x18002a5af  mov     r8, rbx; dwBytes
0x18002a5b2  mov     edx, 8; dwFlags
0x18002a5b7  mov     rcx, rax; hHeap
0x18002a5ba  call    cs:__imp_HeapAlloc
0x18002a5c0  mov     [rsp+190h+var_120], rax
0x18002a5c5  mov     r10, rax
0x18002a5c8  test    rax, rax
0x18002a5cb  jz      loc_18002A6BD
0x18002a5d1  mov     r9, [rsp+190h+var_118]; unsigned __int64
0x18002a5d6  mov     r8, rsi; unsigned __int16 *
0x18002a5d9  mov     edx, edi; unsigned __int64
0x18002a5db  mov     [rsp+190h+var_140], 1
0x18002a5e0  mov     rcx, rax; unsigned __int16 *
0x18002a5e3  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002a5e8  mov     edi, eax
0x18002a5ea  test    eax, eax
0x18002a5ec  js      loc_18002A6C2
0x18002a5f2  mov     r8d, [rsp+190h+var_138]; unsigned int
0x18002a5f7  lea     rdx, [rsp+190h+var_130]; unsigned int *
0x18002a5fc  mov     rcx, r10; unsigned __int16 *
0x18002a5ff  call    ?PreProcessHTMLURI@@YAXPEAGPEAKK@Z; PreProcessHTMLURI(ushort *,ulong *,ulong)
0x18002a604  mov     ebx, [rsp+190h+var_130]
0x18002a608  mov     rax, [rsp+190h+var_120]
0x18002a60d  lea     rcx, [rbp+90h+var_110]; this
0x18002a611  mov     rdi, qword ptr [rbp+90h+EventDescriptor.Id]
0x18002a615  mov     [rbp+90h+var_D8], rax
0x18002a619  lea     rax, ??_7?$CCreateUriHashMapKey@V?$CUrlStringContainer@G@@@@6B@; const CCreateUriHashMapKey<CUrlStringContainer<ushort>>::`vftable'
0x18002a620  mov     [rbp+90h+var_110], rax
0x18002a624  lea     rax, [rbp+90h+var_D8]
0x18002a628  mov     [rbp+90h+lpMem], rax
0x18002a62c  mov     eax, [rsp+190h+var_12C]
0x18002a630  mov     [rbp+90h+var_C0], r15d
0x18002a634  mov     r15d, [rsp+190h+var_138]
0x18002a639  mov     [rbp+90h+var_F4], eax
0x18002a63c  mov     [rbp+90h+var_A8], r15d
0x18002a640  mov     [rbp+90h+var_B0], r14d
0x18002a644  mov     [rbp+90h+var_D0], ebx
0x18002a647  mov     [rbp+90h+var_AC], 0
0x18002a64b  mov     [rbp+90h+var_C8], r13
0x18002a64f  mov     [rbp+90h+var_B8], rdi
0x18002a653  mov     [rbp+90h+var_108], 0
0x18002a65a  mov     [rbp+90h+var_F8], r15d
0x18002a65e  mov     [rbp+90h+var_F0], 0
0x18002a662  call    ?UpdateHash@CCreateUriHashMapKeyBase@@QEAAXXZ; CCreateUriHashMapKeyBase::UpdateHash(void)
0x18002a667  mov     r14, [rsp+190h+var_128]
0x18002a66c  test    r14, r14
0x18002a66f  jnz     loc_18002A768
0x18002a675  lea     rax, ??_7?$CCreateUriHashMapKey@V?$CUrlStringContainer@G@@@@6B@; const CCreateUriHashMapKey<CUrlStringContainer<ushort>>::`vftable'
0x18002a67c  mov     edi, 80070057h
0x18002a681  mov     [rbp+90h+var_110], rax
0x18002a685  cmp     [rbp+90h+var_F0], r14b
0x18002a689  jz      loc_18002A9A2
0x18002a68f  mov     rbx, [rbp+90h+lpMem]
0x18002a693  test    rbx, rbx
0x18002a696  jz      loc_18002A9A2
0x18002a69c  mov     rcx, rbx
0x18002a69f  call    ??1?$CUrlStringContainer@G@@QEAA@XZ; CUrlStringContainer<ushort>::~CUrlStringContainer<ushort>(void)
0x18002a6a4  call    cs:__imp_GetProcessHeap
0x18002a6aa  mov     r8, rbx; lpMem
0x18002a6ad  xor     edx, edx; dwFlags
0x18002a6af  mov     rcx, rax; hHeap
0x18002a6b2  call    cs:__imp_HeapFree
0x18002a6b8  jmp     loc_18002A9A2
0x18002a6bd  mov     edi, 8007000Eh
0x18002a6c2  mov     r15d, [rsp+190h+var_138]
0x18002a6c7  mov     r14, [rsp+190h+var_128]
0x18002a6cc  test    r14, r14
0x18002a6cf  jz      short loc_18002A6D8
0x18002a6d1  mov     qword ptr [r14], 0
0x18002a6d8  cmp     edi, 80070057h
0x18002a6de  jz      loc_18002A9A2
0x18002a6e4  cmp     edi, 8007000Eh
0x18002a6ea  jz      loc_18002A9A2
0x18002a6f0  mov     eax, cs:dword_180293010
0x18002a6f6  cmp     eax, 5
0x18002a6f9  jbe     loc_18002A9A2
0x18002a6ff  mov     rcx, cs:qword_180293028
0x18002a706  mov     rax, cs:qword_180293020
0x18002a70d  test    al, 20h
0x18002a70f  jz      loc_18002A9A2
0x18002a715  mov     rax, rcx
0x18002a718  and     eax, 20h
0x18002a71b  cmp     rax, rcx
0x18002a71e  jnz     loc_18002A9A2
0x18002a724  xor     r14d, r14d
0x18002a727  mov     [rsp+190h+var_12C], r15d
0x18002a72c  mov     [rsp+190h+var_130], edi
0x18002a730  lea     rax, [rsp+190h+var_12C]
0x18002a735  mov     [rbp+90h+var_50], rax
0x18002a739  mov     [rbp+90h+var_48], 4
0x18002a741  test    r13, r13
0x18002a744  jz      loc_18002A86E
0x18002a74a  mov     rax, r12
0x18002a74d  nop     dword ptr [rax]
0x18002a750  cmp     [r13+rax*2+2], r14w
0x18002a756  lea     rax, [rax+1]
0x18002a75a  jnz     short loc_18002A750
0x18002a75c  lea     eax, ds:2[rax*2]
0x18002a763  jmp     loc_18002A87A
0x18002a768  mov     qword ptr [r14], 0
0x18002a76f  test    rsi, rsi
0x18002a772  jz      short loc_18002A78B
0x18002a774  mov     rdx, r14; struct IUri **
0x18002a777  lea     rcx, [rbp+90h+var_110]; struct CHashMapKey *
0x18002a77b  call    ?GetUriFromCache@@YAJPEAVCHashMapKey@@PEAPEAUIUri@@@Z; GetUriFromCache(CHashMapKey *,IUri * *)
0x18002a780  test    eax, eax
0x18002a782  js      short loc_18002A78B
0x18002a784  xor     edi, edi
0x18002a786  jmp     loc_18002A820
0x18002a78b  mov     rcx, [rsp+190h+var_120]
0x18002a790  mov     r9d, r15d
0x18002a793  mov     qword ptr [rsp+190h+var_150], r14; int
0x18002a798  mov     r8, r13
0x18002a79b  mov     edx, ebx
0x18002a79d  mov     [rsp+190h+RelatedActivityId], rdi; int
0x18002a7a2  call    CreateUriPrivNoCache
0x18002a7a7  mov     edi, eax
0x18002a7a9  test    eax, eax
0x18002a7ab  jns     short loc_18002A7F3
0x18002a7ad  cmp     [rbp+90h+var_F0], 0
0x18002a7b1  lea     rax, ??_7?$CCreateUriHashMapKey@V?$CUrlStringContainer@G@@@@6B@; const CCreateUriHashMapKey<CUrlStringContainer<ushort>>::`vftable'
0x18002a7b8  mov     [rbp+90h+var_110], rax
0x18002a7bc  jz      short loc_18002A7E3
0x18002a7be  mov     rbx, [rbp+90h+lpMem]
0x18002a7c2  test    rbx, rbx
0x18002a7c5  jz      short loc_18002A7E3
0x18002a7c7  mov     rcx, rbx
0x18002a7ca  call    ??1?$CUrlStringContainer@G@@QEAA@XZ; CUrlStringContainer<ushort>::~CUrlStringContainer<ushort>(void)
0x18002a7cf  call    cs:__imp_GetProcessHeap
0x18002a7d5  mov     r8, rbx; lpMem
0x18002a7d8  xor     edx, edx; dwFlags
0x18002a7da  mov     rcx, rax; hHeap
0x18002a7dd  call    cs:__imp_HeapFree
0x18002a7e3  lea     rax, ??_7CHashMapKey@@6B@; const CHashMapKey::`vftable'
0x18002a7ea  mov     [rbp+90h+var_110], rax
0x18002a7ee  jmp     loc_18002A6D1
0x18002a7f3  test    rsi, rsi
0x18002a7f6  jz      short loc_18002A820
0x18002a7f8  lea     rcx, ?FEATURE_URI_DISABLECACHE@FCK@@3VCFeatureControlKey@@A; this
0x18002a7ff  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18002a804  test    eax, eax
0x18002a806  jz      short loc_18002A820
0x18002a808  mov     eax, [rsp+190h+var_12C]
0x18002a80c  mov     edx, [rbp+90h+var_108]
0x18002a80f  mov     rcx, [r14]; struct IUri *
0x18002a812  mov     dword ptr [rsp+190h+UserData], eax; int
0x18002a816  mov     [rsp+190h+UserDataCount], r15d; int
0x18002a81b  call    AddUriToCache
0x18002a820  cmp     [rbp+90h+var_F0], 0
0x18002a824  lea     rax, ??_7?$CCreateUriHashMapKey@V?$CUrlStringContainer@G@@@@6B@; const CCreateUriHashMapKey<CUrlStringContainer<ushort>>::`vftable'
0x18002a82b  mov     [rbp+90h+var_110], rax
0x18002a82f  jz      short loc_18002A856
0x18002a831  mov     rbx, [rbp+90h+lpMem]
0x18002a835  test    rbx, rbx
0x18002a838  jz      short loc_18002A856
0x18002a83a  mov     rcx, rbx
0x18002a83d  call    ??1?$CUrlStringContainer@G@@QEAA@XZ; CUrlStringContainer<ushort>::~CUrlStringContainer<ushort>(void)
0x18002a842  call    cs:__imp_GetProcessHeap
0x18002a848  mov     r8, rbx; lpMem
0x18002a84b  xor     edx, edx; dwFlags
0x18002a84d  mov     rcx, rax; hHeap
0x18002a850  call    cs:__imp_HeapFree
0x18002a856  lea     rax, ??_7CHashMapKey@@6B@; const CHashMapKey::`vftable'
0x18002a85d  mov     [rbp+90h+var_110], rax
0x18002a861  test    edi, edi
0x18002a863  jns     loc_18002A9A2
0x18002a869  jmp     loc_18002A6CC
0x18002a86e  lea     r13, word_1801758E4
0x18002a875  mov     eax, 2
0x18002a87a  mov     [rbp+90h+var_60], r13
0x18002a87e  mov     [rbp+90h+var_58], eax
0x18002a881  mov     [rbp+90h+var_54], r14d
0x18002a885  test    rsi, rsi
0x18002a888  jz      short loc_18002A8A7
0x18002a88a  nop     word ptr [rax+rax+00h]
0x18002a890  cmp     [rsi+r12*2+2], r14w
0x18002a896  lea     r12, [r12+1]
0x18002a89b  jnz     short loc_18002A890
0x18002a89d  lea     r12d, ds:2[r12*2]
0x18002a8a5  jmp     short loc_18002A8B4
0x18002a8a7  lea     rsi, word_1801758E4
0x18002a8ae  mov     r12d, 2
0x18002a8b4  lea     rax, [rsp+190h+var_130]
0x18002a8b9  mov     [rbp+90h+var_70], rsi
0x18002a8bd  mov     [rbp+90h+var_80], rax
0x18002a8c1  lea     rcx, _TraceLoggingMetadata
0x18002a8c8  movzx   eax, cs:word_180286537
0x18002a8cf  mov     ebx, r14d
0x18002a8d2  mov     dword ptr [rbp+90h+EventDescriptor.Level], eax
0x18002a8d5  mov     rax, cs:off_180293018
0x18002a8dc  mov     [rbp+90h+var_A0.Ptr], rax
  ... truncated ...
```
