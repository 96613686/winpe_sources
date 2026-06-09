# SaveTree(CWriter *,CMDBaseObject *,BUFFER *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,int,int,int)

- ea: `0x180005cd8`
- end: `0x1800061fc`
- name: `?SaveTree@@YAJPEAVCWriter@@PEAVCMDBaseObject@@PEAVBUFFER@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@HHH@Z`
- size: `1316`
- prototype: `__int64 __fastcall(struct CWriter *, struct CMDBaseObject *, struct BUFFER *, struct IIS_CRYPTO_STORAGE *, struct _IIS_CRYPTO_BLOB *, int, int, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005cd8`
- `0x180023df4`
- `0x180024e90`

## callees

- `0x1800052b0`
- `0x1800053b0`
- `0x180005cd8`
- `0x180006204`
- `0x1800074e4`
- `0x180007810`
- `0x180007bd0`
- `0x1800083f4`
- `0x180008a08`
- `0x180008a14`
- `0x180009b58`
- `0x180023a74`
- `0x1800242ac`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180005de2`
- `msvcrt!wcscat_s` at `0x180005de2`
- `msvcrt!_wcsicmp` at `0x180006150`
- `msvcrt!_wcsicmp` at `0x180006150`
- `msvcrt!qsort` at `0x180006113`
- `msvcrt!qsort` at `0x180006113`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180005d5b`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180005d6d`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180005d5b`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180005d6d`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005d8f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005d8f`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005dd1`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005dd1`
- `IisRTL!PuDbgPrintW` at `0x180006033`
- `IisRTL!PuDbgPrintW` at `0x180006033`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005d33`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005daa`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800061a2`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005d33`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005daa`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800061a2`

## pseudocode

```c
__int64 __fastcall SaveTree(
        struct CWriter *a1,
        struct CMDBaseObject **a2,
        struct BUFFER *a3,
        struct IIS_CRYPTO_STORAGE *a4,
        struct _IIS_CRYPTO_BLOB *a5,
        int a6,
        int a7,
        int a8)
{
  _WORD *Ptr; // rax
  __int64 v11; // rdi
  char *Str; // rax
  __int64 v13; // rcx
  __int64 v14; // r15
  int v15; // ebx
  _BYTE *v16; // r14
  wchar_t *v17; // rdi
  const wchar_t *Name; // rbx
  unsigned int Size; // eax
  int LocationWriter; // eax
  __int64 v21; // rdx
  CLocationWriter *v22; // r12
  _QWORD *v23; // r13
  struct CMDBaseObject *v24; // rcx
  unsigned int v25; // edi
  unsigned __int8 *v26; // r15
  CLocationWriter *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // r15d
  CLocationWriter *v33; // rdi
  unsigned int v34; // edi
  struct CMDBaseObject *v35; // rcx
  char *v36; // rdx
  struct CMDBaseObject *v37; // rcx
  struct CMDBaseObject *ChildObject; // rax
  unsigned int v39; // r9d
  int v40; // r9d
  unsigned int i; // r15d
  const wchar_t *v42; // rax
  _WORD *v43; // rax
  unsigned int v45; // [rsp+30h] [rbp-A1h]
  CLocationWriter *v46; // [rsp+40h] [rbp-91h] BYREF
  unsigned int v47; // [rsp+48h] [rbp-89h]
  unsigned int v48; // [rsp+4Ch] [rbp-85h]
  unsigned int v49; // [rsp+50h] [rbp-81h]
  struct IIS_CRYPTO_STORAGE *v50; // [rsp+58h] [rbp-79h]
  CWriter *v51; // [rsp+60h] [rbp-71h]
  struct BUFFER *v52; // [rsp+68h] [rbp-69h]
  struct _IIS_CRYPTO_BLOB *v53; // [rsp+70h] [rbp-61h]
  __int64 v54; // [rsp+78h] [rbp-59h]
  _BYTE Base[64]; // [rsp+80h] [rbp-51h] BYREF

  v52 = a3;
  v51 = a1;
  v50 = a4;
  v53 = a5;
  v46 = 0;
  memset_0(Base, 0, sizeof(Base));
  Ptr = BUFFER::QueryPtr(a3);
  v11 = -1;
  do
    ++v11;
  while ( Ptr[v11] );
  v54 = v11;
  if ( !STRAU::QueryStr((STRAU *)(a2 + 1), 1) )
    return (unsigned int)-2147024882;
  Str = STRAU::QueryStr((STRAU *)(a2 + 1), 1);
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)&Str[2 * v13] );
  v14 = (unsigned int)(v13 + v11);
  if ( !BUFFER::Resize(a3, 2 * (v14 + 2)) )
    return (unsigned int)-2147024882;
  v16 = Base;
  v17 = (wchar_t *)BUFFER::QueryPtr(a3);
  if ( a2 != (struct CMDBaseObject **)g_pboMasterRoot )
  {
    Name = (const wchar_t *)CMDBaseObject::GetName((CMDBaseObject *)a2, 1, 0);
    Size = BUFFER::QuerySize(a3);
    wcscat_s(v17, (unsigned __int64)Size >> 1, Name);
    v17[v14] = 47;
    v17[(unsigned int)(v14 + 1)] = 0;
  }
  LocationWriter = CWriter::GetLocationWriter(v51, &v46, v17);
  v22 = v46;
  v15 = LocationWriter;
  if ( LocationWriter >= 0 )
  {
    v23 = a2 + 33;
    v49 = 0;
    v24 = a2[33];
    v25 = 1;
    v48 = 0;
    v21 = 0;
    v47 = 0;
    v26 = 0;
    v27 = 0;
    if ( a2 + 33 != (struct CMDBaseObject **)v24 )
      v21 = (__int64)v24 - 40;
    if ( v21 )
      v27 = (CLocationWriter *)v21;
    v46 = v27;
    while ( v27 )
    {
      if ( *((_DWORD *)v27 + 2) == 1002 )
      {
        v28 = (*(__int64 (__fastcall **)(CLocationWriter *, __int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL))(
                v27,
                1,
                0,
                0);
        v29 = *(_QWORD *)v27;
        v26 = (unsigned __int8 *)v28;
        v49 = *((_DWORD *)v27 + 6);
        v48 = *((_DWORD *)v27 + 7);
        v30 = (*(__int64 (__fastcall **)(CLocationWriter *))(v29 + 8))(v27);
        v31 = *(_QWORD *)v27;
        v47 = v30;
        (*(void (__fastcall **)(CLocationWriter *, __int64))(v31 + 32))(v27, 1);
        break;
      }
      v15 = CMDBaseObject::EnumDataObject((CMDBaseObject *)a2, v25, 0, 0, 0, 0, &v46);
      if ( v15 < 0 )
        goto LABEL_62;
      v27 = v46;
      ++v25;
    }
    v15 = CLocationWriter::InitializeKeyType(v22, v21, v49, v48, v47, v26, v45);
    if ( v15 >= 0 )
    {
      v32 = 1;
      v21 = 0;
      v33 = 0;
      if ( v23 != (_QWORD *)*v23 )
        v21 = *v23 - 40LL;
      if ( v21 )
        v33 = (CLocationWriter *)v21;
      v46 = v33;
      while ( v33 )
      {
        v15 = SaveDataObject(v33, v22, v50, 0);
        if ( v15 < 0 )
          goto LABEL_62;
        if ( a8 )
          SaveGlobalsFromLM(v33);
        v15 = CMDBaseObject::EnumDataObject((CMDBaseObject *)a2, v32, 0, 0, 0, 0, &v46);
        if ( v15 < 0 )
          goto LABEL_62;
        v33 = v46;
        ++v32;
      }
      if ( a8 && g_dwEnableEditWhileRunning && !g_dwEnableHistory )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            9412,
            "SaveTree",
            L"[SaveTree] Warning! Edit while running is enabled, while Enable history is disabled. Forcibly enabling history.\n");
        g_dwEnableHistory = 1;
      }
      v15 = CLocationWriter::WriteLocation(v22, v21);
      if ( v15 >= 0 )
      {
        if ( a6 )
        {
          v34 = 0;
          v35 = a2[29];
          v36 = (char *)v35 - 248;
          if ( v35 == (struct CMDBaseObject *)(a2 + 29) )
            v36 = 0;
          if ( v36 )
          {
            do
            {
              v37 = (struct CMDBaseObject *)*((_QWORD *)v36 + 31);
              ++v34;
              v36 = (char *)v37 - 248;
              if ( v37 == (struct CMDBaseObject *)(a2 + 29) )
                v36 = 0;
            }
            while ( v36 );
            if ( v34 > 8 )
            {
              v16 = operator new[](saturated_mul(v34, 8u));
              if ( !v16 )
              {
                v15 = -2147024882;
                goto LABEL_62;
              }
            }
          }
          ChildObject = CMDBaseObject::NextChildObject((CMDBaseObject *)a2, 0);
          while ( ChildObject && v39 < v34 )
          {
            *(_QWORD *)&v16[8 * v39] = ChildObject;
            ChildObject = CMDBaseObject::NextChildObject((CMDBaseObject *)a2, ChildObject);
            v39 = v40 + 1;
          }
          qsort(v16, v34, 8u, (_CoreCrtNonSecureSearchSortCompareFunction)MyComparePBaseObject);
          for ( i = 0; i < v34; ++i )
          {
            if ( !a7 && a2 == (struct CMDBaseObject **)g_pboMasterRoot )
            {
              v42 = (const wchar_t *)CMDBaseObject::GetName(*(CMDBaseObject **)&v16[8 * i], 1, 0);
              if ( !_wcsicmp(v42, L"Schema") )
                continue;
            }
            v15 = SaveTree(v51, *(struct CMDBaseObject **)&v16[8 * i], v52, v50, v53, a6, 1, 0);
            if ( v15 < 0 )
              goto LABEL_62;
          }
        }
        v43 = BUFFER::QueryPtr(v52);
        v15 = 0;
        v43[(unsigned int)v54] = 0;
      }
    }
  }
LABEL_62:
  if ( v22 )
    CLocationWriter::`scalar deleting destructor'(v22, v21);
  if ( v16 && v16 != Base )
    operator delete(v16);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180005cd8  push    rbp
0x180005cda  push    rbx
0x180005cdb  push    rsi
0x180005cdc  push    rdi
0x180005cdd  push    r12
0x180005cdf  push    r13
0x180005ce1  push    r14
0x180005ce3  push    r15
0x180005ce5  lea     rbp, [rsp-7]
0x180005cea  sub     rsp, 0D8h
0x180005cf1  mov     rax, cs:__security_cookie
0x180005cf8  xor     rax, rsp
0x180005cfb  mov     [rbp+3Fh+var_50], rax
0x180005cff  mov     rax, [rbp+3Fh+arg_20]
0x180005d03  xor     r14d, r14d
0x180005d06  mov     r13, r8
0x180005d09  mov     [rbp+3Fh+var_A8], r8
0x180005d0d  mov     rsi, rdx
0x180005d10  mov     [rbp+3Fh+var_B0], rcx
0x180005d14  xor     edx, edx; Val
0x180005d16  mov     [rbp+3Fh+var_B8], r9
0x180005d1a  lea     r8d, [r14+40h]; Size
0x180005d1e  mov     [rbp+3Fh+var_A0], rax
0x180005d22  lea     rcx, [rbp+3Fh+Base]; void *
0x180005d26  mov     [rsp+110h+var_D0], r14
0x180005d2b  call    memset_0
0x180005d30  mov     rcx, r13
0x180005d33  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005d39  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005d3d  mov     rdi, r12
0x180005d40  inc     rdi
0x180005d43  cmp     [rax+rdi*2], r14w
0x180005d48  jnz     short loc_180005D40
0x180005d4a  mov     r15d, 1
0x180005d50  mov     [rbp+3Fh+var_98], rdi
0x180005d54  mov     edx, r15d
0x180005d57  lea     rcx, [rsi+8]
0x180005d5b  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180005d61  test    rax, rax
0x180005d64  jz      short loc_180005D99
0x180005d66  mov     edx, r15d
0x180005d69  lea     rcx, [rsi+8]
0x180005d6d  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180005d73  mov     rcx, r12
0x180005d76  inc     rcx
0x180005d79  cmp     [rax+rcx*2], r14w
0x180005d7e  jnz     short loc_180005D76
0x180005d80  lea     r15d, [rcx+rdi]
0x180005d84  mov     rcx, r13
0x180005d87  lea     r12d, [r15+2]
0x180005d8b  lea     edx, [r12+r12]
0x180005d8f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005d95  test    al, al
0x180005d97  jnz     short loc_180005DA3
0x180005d99  mov     ebx, 8007000Eh
0x180005d9e  jmp     loc_1800061DA
0x180005da3  mov     rcx, r13
0x180005da6  lea     r14, [rbp+3Fh+Base]
0x180005daa  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005db0  cmp     rsi, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x180005db7  mov     rdi, rax
0x180005dba  jz      short loc_180005DFA
0x180005dbc  xor     r8d, r8d; unsigned int *
0x180005dbf  mov     rcx, rsi; this
0x180005dc2  lea     edx, [r8+1]; int
0x180005dc6  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x180005dcb  mov     rcx, r13
0x180005dce  mov     rbx, rax
0x180005dd1  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180005dd7  mov     edx, eax
0x180005dd9  mov     r8, rbx; Source
0x180005ddc  shr     rdx, 1; SizeInWords
0x180005ddf  mov     rcx, rdi; Destination
0x180005de2  call    cs:__imp_wcscat_s
0x180005de8  lea     ecx, [r12-1]
0x180005ded  mov     word ptr [rdi+r15*2], 2Fh ; '/'
0x180005df4  xor     eax, eax
0x180005df6  mov     [rdi+rcx*2], ax
0x180005dfa  mov     rcx, [rbp+3Fh+var_B0]; this
0x180005dfe  lea     rdx, [rsp+110h+var_D0]; struct CLocationWriter **
0x180005e03  mov     r8, rdi; unsigned __int16 *
0x180005e06  call    ?GetLocationWriter@CWriter@@QEAAJPEAPEAVCLocationWriter@@PEBG@Z; CWriter::GetLocationWriter(CLocationWriter * *,ushort const *)
0x180005e0b  mov     r12, [rsp+110h+var_D0]
0x180005e10  xor     r9d, r9d
0x180005e13  mov     ebx, eax
0x180005e15  test    eax, eax
0x180005e17  js      loc_1800061B7
0x180005e1d  lea     r13, [rsi+108h]
0x180005e24  mov     [rsp+110h+var_C0], r9d
0x180005e29  mov     rcx, [r13+0]
0x180005e2d  lea     edi, [r9+1]
0x180005e31  cmp     r13, rcx
0x180005e34  mov     [rsp+110h+var_C4], r9d
0x180005e39  mov     edx, r9d
0x180005e3c  mov     [rsp+110h+var_C8], r9d
0x180005e41  mov     r15d, r9d
0x180005e44  mov     ebx, r9d
0x180005e47  lea     rax, [rcx-28h]
0x180005e4b  cmovnz  rdx, rax; struct CMDBaseData *
0x180005e4f  test    rdx, rdx
0x180005e52  jz      short loc_180005E6C
0x180005e54  test    r9d, r9d
0x180005e57  jz      short loc_180005E69
0x180005e59  dec     r9d
0x180005e5c  mov     rcx, rsi; this
0x180005e5f  call    ?GetNextBaseData@CMDBaseObject@@AEAAPEAVCMDBaseData@@PEAV2@@Z; CMDBaseObject::GetNextBaseData(CMDBaseData *)
0x180005e64  mov     rdx, rax
0x180005e67  jmp     short loc_180005E4F
0x180005e69  mov     rbx, rdx
0x180005e6c  mov     [rsp+110h+var_D0], rbx
0x180005e71  xor     r9d, r9d
0x180005e74  test    rbx, rbx
0x180005e77  jz      loc_180005F0E
0x180005e7d  xor     r8d, r8d; unsigned int
0x180005e80  cmp     dword ptr [rbx+8], 3EAh
0x180005e87  jz      short loc_180005EC0
0x180005e89  lea     rax, [rsp+110h+var_D0]
0x180005e8e  mov     edx, edi; unsigned int
0x180005e90  mov     [rsp+110h+var_E0], rax; struct CMDBaseData **
0x180005e95  mov     rcx, rsi; this
0x180005e98  mov     [rsp+110h+var_E8], r9; struct CMDBaseObject **
0x180005e9d  mov     dword ptr [rsp+110h+var_F0], r9d; unsigned int
0x180005ea2  xor     r9d, r9d; unsigned int
0x180005ea5  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180005eaa  xor     r9d, r9d
0x180005ead  mov     ebx, eax
0x180005eaf  test    eax, eax
0x180005eb1  js      loc_1800061B7
0x180005eb7  mov     rbx, [rsp+110h+var_D0]
0x180005ebc  inc     edi
0x180005ebe  jmp     short loc_180005E74
0x180005ec0  mov     rax, [rbx]
0x180005ec3  mov     edx, 1
0x180005ec8  mov     rcx, rbx
0x180005ecb  mov     rax, [rax+18h]
0x180005ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed4  mov     rdx, [rbx]
0x180005ed7  mov     r15, rax
0x180005eda  mov     eax, [rbx+18h]
0x180005edd  mov     rcx, rbx
0x180005ee0  mov     [rsp+110h+var_C0], eax
0x180005ee4  mov     eax, [rbx+1Ch]
0x180005ee7  mov     [rsp+110h+var_C4], eax
0x180005eeb  mov     rax, [rdx+8]
0x180005eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef4  mov     rdx, [rbx]
0x180005ef7  xor     r8d, r8d
0x180005efa  mov     [rsp+110h+var_C8], eax
0x180005efe  mov     rcx, rbx
0x180005f01  mov     rax, [rdx+20h]
0x180005f05  lea     edx, [r8+1]
0x180005f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0e  mov     eax, [rsp+110h+var_C8]
0x180005f12  mov     rcx, r12; this
0x180005f15  mov     r9d, [rsp+110h+var_C4]; unsigned int
0x180005f1a  mov     r8d, [rsp+110h+var_C0]; unsigned int
0x180005f1f  mov     [rsp+110h+var_E8], r15; unsigned __int8 *
0x180005f24  mov     dword ptr [rsp+110h+var_F0], eax; unsigned int
0x180005f28  call    ?InitializeKeyType@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::InitializeKeyType(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180005f2d  xor     r9d, r9d
0x180005f30  mov     ebx, eax
0x180005f32  test    eax, eax
0x180005f34  js      loc_1800061B7
0x180005f3a  mov     rcx, [r13+0]
0x180005f3e  lea     r15d, [r9+1]
0x180005f42  cmp     r13, rcx
0x180005f45  mov     edx, r9d
0x180005f48  mov     edi, r9d
0x180005f4b  lea     rax, [rcx-28h]
0x180005f4f  cmovnz  rdx, rax; struct CMDBaseData *
0x180005f53  test    rdx, rdx
0x180005f56  jz      short loc_180005F70
0x180005f58  test    r9d, r9d
0x180005f5b  jz      short loc_180005F6D
0x180005f5d  dec     r9d
0x180005f60  mov     rcx, rsi; this
0x180005f63  call    ?GetNextBaseData@CMDBaseObject@@AEAAPEAVCMDBaseData@@PEAV2@@Z; CMDBaseObject::GetNextBaseData(CMDBaseData *)
0x180005f68  mov     rdx, rax
0x180005f6b  jmp     short loc_180005F53
0x180005f6d  mov     rdi, rdx
0x180005f70  mov     r13d, [rbp+3Fh+arg_38]
0x180005f77  xor     r9d, r9d; struct _IIS_CRYPTO_BLOB *
0x180005f7a  mov     [rsp+110h+var_D0], rdi
0x180005f7f  test    rdi, rdi
0x180005f82  jz      short loc_180005FEC
0x180005f84  mov     r8, [rbp+3Fh+var_B8]; struct IIS_CRYPTO_STORAGE *
0x180005f88  mov     rdx, r12; struct CLocationWriter *
0x180005f8b  mov     rcx, rdi; struct CMDBaseData *
0x180005f8e  call    ?SaveDataObject@@YAJPEAVCMDBaseData@@PEAVCLocationWriter@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@@Z; SaveDataObject(CMDBaseData *,CLocationWriter *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *)
0x180005f93  xor     r9d, r9d
0x180005f96  mov     ebx, eax
0x180005f98  test    eax, eax
0x180005f9a  js      loc_1800061B7
0x180005fa0  test    r13d, r13d
0x180005fa3  jz      short loc_180005FB0
0x180005fa5  mov     rcx, rdi; struct CMDBaseData *
0x180005fa8  call    ?SaveGlobalsFromLM@@YAXPEAVCMDBaseData@@@Z; SaveGlobalsFromLM(CMDBaseData *)
0x180005fad  xor     r9d, r9d
0x180005fb0  lea     rax, [rsp+110h+var_D0]
0x180005fb5  xor     r8d, r8d; unsigned int
0x180005fb8  mov     [rsp+110h+var_E0], rax; struct CMDBaseData **
0x180005fbd  mov     edx, r15d; unsigned int
0x180005fc0  mov     [rsp+110h+var_E8], r9; struct CMDBaseObject **
0x180005fc5  mov     rcx, rsi; this
0x180005fc8  mov     dword ptr [rsp+110h+var_F0], r9d; unsigned int
0x180005fcd  xor     r9d, r9d; unsigned int
0x180005fd0  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180005fd5  xor     r9d, r9d
0x180005fd8  mov     ebx, eax
0x180005fda  test    eax, eax
0x180005fdc  js      loc_1800061B7
0x180005fe2  mov     rdi, [rsp+110h+var_D0]
0x180005fe7  inc     r15d
0x180005fea  jmp     short loc_180005F7F
0x180005fec  test    r13d, r13d
0x180005fef  jz      short loc_180006043
0x180005ff1  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, r9d; ulong g_dwEnableEditWhileRunning
0x180005ff8  jz      short loc_180006043
0x180005ffa  cmp     cs:?g_dwEnableHistory@@3KA, r9d; ulong g_dwEnableHistory
0x180006001  jnz     short loc_180006043
0x180006003  test    byte ptr cs:g_dwDebugFlags, 3
0x18000600a  jz      short loc_180006039
0x18000600c  mov     rcx, cs:g_pDebug
0x180006013  lea     rax, aSavetreeWarnin; "[SaveTree] Warning! Edit while running "...
0x18000601a  lea     r9, aSavetree; "SaveTree"
0x180006021  mov     [rsp+110h+var_F0], rax
0x180006026  mov     r8d, 24C4h
0x18000602c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180006033  call    cs:__imp_PuDbgPrintW
0x180006039  mov     cs:?g_dwEnableHistory@@3KA, 1; ulong g_dwEnableHistory
0x180006043  mov     rcx, r12; this
0x180006046  call    ?WriteLocation@CLocationWriter@@QEAAJH@Z; CLocationWriter::WriteLocation(int)
0x18000604b  xor     r9d, r9d
0x18000604e  mov     ebx, eax
0x180006050  test    eax, eax
0x180006052  js      loc_1800061B7
0x180006058  mov     r13d, [rbp+3Fh+arg_28]
0x18000605c  test    r13d, r13d
0x18000605f  jz      loc_18000619E
0x180006065  lea     r8, [rsi+0E8h]
0x18000606c  mov     edi, r9d
0x18000606f  mov     rcx, [r8]
0x180006072  lea     ebx, [r9+8]
0x180006076  cmp     rcx, r8
0x180006079  lea     rdx, [rcx-0F8h]
0x180006080  cmovz   rdx, r9
0x180006084  test    rdx, rdx
0x180006087  jz      short loc_1800060D9
0x180006089  mov     rcx, [rdx+0F8h]
0x180006090  inc     edi
0x180006092  cmp     rcx, r8
0x180006095  lea     rdx, [rcx-0F8h]
0x18000609c  cmovz   rdx, r9
0x1800060a0  test    rdx, rdx
0x1800060a3  jnz     short loc_180006089
0x1800060a5  cmp     edi, ebx
0x1800060a7  jbe     short loc_1800060D9
0x1800060a9  mov     ecx, edi
0x1800060ab  mov     rax, rbx
0x1800060ae  mul     rcx
0x1800060b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060b8  cmovb   rax, rcx
0x1800060bc  mov     rcx, rax; unsigned __int64
0x1800060bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800060c4  xor     r9d, r9d
0x1800060c7  mov     r14, rax
0x1800060ca  test    rax, rax
0x1800060cd  jnz     short loc_1800060D9
0x1800060cf  mov     ebx, 8007000Eh
0x1800060d4  jmp     loc_1800061B7
0x1800060d9  xor     edx, edx; struct CMDBaseObject *
0x1800060db  mov     rcx, rsi; this
0x1800060de  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x1800060e3  jmp     short loc_1800060FF
0x1800060e5  cmp     r9d, edi
0x1800060e8  jnb     short loc_180006104
0x1800060ea  mov     ecx, r9d
0x1800060ed  mov     rdx, rax; struct CMDBaseObject *
0x1800060f0  mov     [r14+rcx*8], rax
0x1800060f4  mov     rcx, rsi; this
0x1800060f7  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x1800060fc  inc     r9d
0x1800060ff  test    rax, rax
0x180006102  jnz     short loc_1800060E5
0x180006104  mov     edx, edi; NumOfElements
0x180006106  lea     r9, ?MyComparePBaseObject@@YAHPEBX0@Z; CompareFunction
0x18000610d  mov     r8, rbx; SizeOfElements
0x180006110  mov     rcx, r14; Base
0x180006113  call    cs:__imp_qsort
0x180006119  xor     r9d, r9d
0x18000611c  mov     r15d, r9d
0x18000611f  cmp     r15d, edi
0x180006122  jnb     short loc_18000619E
0x180006124  cmp     [rbp+3Fh+arg_30], r9d
0x180006128  jnz     short loc_18000615D
0x18000612a  cmp     rsi, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x180006131  jnz     short loc_18000615D
0x180006133  xor     r8d, r8d; unsigned int *
0x180006136  mov     ecx, r15d
0x180006139  mov     rcx, [r14+rcx*8]; this
  ... truncated ...
```
