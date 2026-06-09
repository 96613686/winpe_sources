# SaveInheritedOnly(CWriter *,CMDBaseObject *,BUFFER *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *)

- ea: `0x1800246a4`
- end: `0x1800249a8`
- name: `?SaveInheritedOnly@@YAJPEAVCWriter@@PEAVCMDBaseObject@@PEAVBUFFER@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(struct CWriter *this@<rcx>, struct CMDBaseObject *@<rdx>, struct BUFFER *@<r8>, struct IIS_CRYPTO_STORAGE *@<r9>, struct _IIS_CRYPTO_BLOB *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180024e90`

## callees

- `0x180006204`
- `0x180006dc4`
- `0x1800074e4`
- `0x180007810`
- `0x180008a08`
- `0x180008a14`
- `0x180009b58`
- `0x180014ffc`
- `0x180023a74`
- `0x1800246a4`
- `0x18003098e`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180024739`
- `IisRTL!PuDbgPrint` at `0x180024856`
- `IisRTL!PuDbgPrint` at `0x18002497a`
- `IisRTL!PuDbgPrint` at `0x180024739`
- `IisRTL!PuDbgPrint` at `0x180024856`
- `IisRTL!PuDbgPrint` at `0x18002497a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800246c8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800247c1`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800246c8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800247c1`

## string_xrefs

- `0x180024844`: `GetLocationWriter failed [0x%x]\n`
- `0x18002493d`: `WriteLocation failed [0x%x]\n`

## pseudocode

```c
__int64 __fastcall SaveInheritedOnly(
        struct CWriter *this,
        struct CMDBaseObject *a2,
        struct BUFFER *a3,
        struct IIS_CRYPTO_STORAGE *a4,
        struct _IIS_CRYPTO_BLOB *a5)
{
  _WORD *Ptr; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // r15
  CLocationWriter *v11; // rdi
  unsigned int v12; // edx
  unsigned int v13; // ebx
  __int64 v14; // r8
  char *Name; // rax
  __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  char *v18; // rdi
  size_t v19; // rbx
  const void *v20; // rax
  char *v21; // rdi
  char *v22; // rax
  int LocationWriter; // eax
  int v24; // eax
  int i; // esi
  int v26; // eax
  struct _IIS_CRYPTO_BLOB *v27; // r9
  int v28; // eax
  int v29; // eax
  struct CMDBaseData **v31; // [rsp+28h] [rbp-20h]
  struct CMDBaseData *v32; // [rsp+30h] [rbp-18h] BYREF
  struct CMDBaseObject *v33; // [rsp+38h] [rbp-10h] BYREF

  Ptr = BUFFER::QueryPtr(a3);
  v9 = -1;
  v10 = 0;
  do
    ++v9;
  while ( Ptr[v9] );
  a5 = 0;
  v32 = 0;
  v11 = 0;
  if ( !CMDBaseObject::GetName(a2, 1, 0) )
  {
    v13 = -2147024882;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_34;
    v14 = 11650;
    goto LABEL_6;
  }
  Name = CMDBaseObject::GetName(a2, 1, 0);
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&Name[2 * v16] );
  v17 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v16 + v9 + 12), 2u));
  v10 = v17;
  if ( v17 )
  {
    v18 = (char *)(v17 + 10);
    *(_OWORD *)v17 = *(_OWORD *)L"inherited:";
    *((_DWORD *)v17 + 4) = *(_DWORD *)L"d:";
    v19 = 2LL * (unsigned int)v9;
    v20 = BUFFER::QueryPtr(a3);
    memcpy_0(v10 + 10, v20, v19);
    v21 = &v18[v19];
    if ( a2 != g_pboMasterRoot )
    {
      v22 = CMDBaseObject::GetName(a2, 1, 0);
      memcpy_0(v21, v22, 2LL * (unsigned int)v16);
      v21 += 2 * (unsigned int)v16;
    }
    *(_DWORD *)v21 = 47;
    LocationWriter = CWriter::GetLocationWriter(this, &a5, v10);
    v13 = LocationWriter;
    if ( LocationWriter >= 0 )
    {
      v11 = a5;
      v24 = CLocationWriter::AssignKeyType(a5, L"IIsInheritedProperties");
      v13 = v24;
      if ( v24 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          LODWORD(a5) = i;
          v33 = 0;
          v26 = CMDBaseObject::EnumInheritableDataObject(a2, (unsigned int *)&a5, 0, 0, &v33, &v32);
          v13 = v26;
          if ( v26 < 0 )
            break;
          if ( !v32 )
          {
            v29 = CLocationWriter::WriteLocation(v11, v12);
            v13 = v29;
            if ( v29 < 0 && (g_dwDebugFlags & 0xF) != 0 )
            {
              LODWORD(v31) = v29;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                11753,
                "SaveInheritedOnly",
                "WriteLocation failed [0x%x]\n",
                v31);
            }
            goto LABEL_34;
          }
          if ( v33 != a2 )
          {
            v28 = SaveDataObject(v32, v11, a4, v27);
            v13 = v28;
            if ( v28 < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                LODWORD(v31) = v28;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                  11744,
                  "SaveInheritedOnly",
                  "SaveDataObject failed [0x%x]\n",
                  v31);
              }
              goto LABEL_34;
            }
          }
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          LODWORD(v31) = v26;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            11720,
            "SaveInheritedOnly",
            "EnumInheritableDataObject failed [0x%x]\n",
            v31);
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          11703,
          "SaveInheritedOnly",
          "InitializeKeyTypeAsInherited failed [0x%x]\n",
          v24);
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          11696,
          "SaveInheritedOnly",
          "GetLocationWriter failed [0x%x]\n",
          LocationWriter);
      v11 = a5;
    }
  }
  else
  {
    v13 = -2147024882;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v14 = 11664;
LABEL_6:
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", v14, "SaveInheritedOnly", "Out of memory\n");
    }
  }
LABEL_34:
  if ( v11 )
    CLocationWriter::`scalar deleting destructor'(v11, v12);
  operator delete(v10);
  return v13;
}

```

## disassembly

```asm
0x1800246a4  mov     [rsp-40h+arg_18], r9
0x1800246a9  push    rbp
0x1800246aa  push    rbx
0x1800246ab  push    rsi
0x1800246ac  push    rdi
0x1800246ad  push    r12
0x1800246af  push    r13
0x1800246b1  push    r14
0x1800246b3  push    r15
0x1800246b5  mov     rbp, rsp
0x1800246b8  sub     rsp, 48h
0x1800246bc  mov     r13, rcx
0x1800246bf  mov     r12, r8
0x1800246c2  mov     rcx, r8
0x1800246c5  mov     r14, rdx
0x1800246c8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800246ce  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800246d2  xor     r15d, r15d
0x1800246d5  inc     rbx
0x1800246d8  cmp     [rax+rbx*2], r15w
0x1800246dd  jnz     short loc_1800246D5
0x1800246df  xor     r8d, r8d; unsigned int *
0x1800246e2  mov     [rbp+arg_20], r15
0x1800246e6  mov     rcx, r14; this
0x1800246e9  mov     [rbp+var_18], r15
0x1800246ed  mov     rdi, r15
0x1800246f0  lea     esi, [r8+1]
0x1800246f4  mov     edx, esi; int
0x1800246f6  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800246fb  test    rax, rax
0x1800246fe  jnz     short loc_180024744
0x180024700  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024707  mov     ebx, 8007000Eh
0x18002470c  jz      loc_180024980
0x180024712  mov     r8d, 2D82h
0x180024718  mov     rcx, cs:g_pDebug
0x18002471f  lea     rax, aOutOfMemory; "Out of memory\n"
0x180024726  lea     r9, aSaveinheritedo; "SaveInheritedOnly"
0x18002472d  mov     [rsp+48h+var_28], rax
0x180024732  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024739  call    cs:__imp_PuDbgPrint
0x18002473f  jmp     loc_180024980
0x180024744  xor     r8d, r8d; unsigned int *
0x180024747  mov     edx, esi; int
0x180024749  mov     rcx, r14; this
0x18002474c  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x180024751  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024755  mov     rsi, r8
0x180024758  inc     rsi
0x18002475b  cmp     [rax+rsi*2], r15w
0x180024760  jnz     short loc_180024758
0x180024762  lea     ecx, [rbx+0Ch]
0x180024765  mov     eax, 2
0x18002476a  add     ecx, esi
0x18002476c  mul     rcx
0x18002476f  cmovb   rax, r8
0x180024773  mov     rcx, rax; unsigned __int64
0x180024776  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002477b  mov     r15, rax
0x18002477e  test    rax, rax
0x180024781  jnz     short loc_1800247A0
0x180024783  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002478a  mov     ebx, 8007000Eh
0x18002478f  jz      loc_180024980
0x180024795  mov     r8d, 2D90h
0x18002479b  jmp     loc_180024718
0x1800247a0  movups  xmm0, xmmword ptr cs:?sm_wszInheritedPropertiesLocationPrefix@CImporter@@2QBGB; "inherited:"
0x1800247a7  mov     rcx, r12
0x1800247aa  lea     rdi, [r15+14h]
0x1800247ae  movups  xmmword ptr [rax], xmm0
0x1800247b1  mov     eax, dword ptr cs:?sm_wszInheritedPropertiesLocationPrefix@CImporter@@2QBGB+10h; "d:"
0x1800247b7  mov     [r15+10h], eax
0x1800247bb  mov     eax, ebx
0x1800247bd  lea     rbx, [rax+rax]
0x1800247c1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800247c7  mov     r8, rbx; Size
0x1800247ca  mov     rcx, rdi; void *
0x1800247cd  mov     rdx, rax; Src
0x1800247d0  call    memcpy_0
0x1800247d5  add     rdi, rbx
0x1800247d8  cmp     r14, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x1800247df  jz      short loc_180024807
0x1800247e1  xor     r8d, r8d; unsigned int *
0x1800247e4  mov     eax, esi
0x1800247e6  mov     rcx, r14; this
0x1800247e9  lea     edx, [r8+1]; int
0x1800247ed  lea     rbx, [rax+rax]
0x1800247f1  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800247f6  mov     rdx, rax; Src
0x1800247f9  mov     r8, rbx; Size
0x1800247fc  mov     rcx, rdi; void *
0x1800247ff  call    memcpy_0
0x180024804  add     rdi, rbx
0x180024807  mov     r8, r15; unsigned __int16 *
0x18002480a  mov     dword ptr [rdi], 2Fh ; '/'
0x180024810  lea     rdx, [rbp+arg_20]; struct CLocationWriter **
0x180024814  mov     rcx, r13; this
0x180024817  call    ?GetLocationWriter@CWriter@@QEAAJPEAPEAVCLocationWriter@@PEBG@Z; CWriter::GetLocationWriter(CLocationWriter * *,ushort const *)
0x18002481c  mov     ebx, eax
0x18002481e  test    eax, eax
0x180024820  jns     short loc_180024865
0x180024822  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024829  jz      short loc_18002485C
0x18002482b  mov     rcx, cs:g_pDebug
0x180024832  lea     r9, aSaveinheritedo; "SaveInheritedOnly"
0x180024839  mov     dword ptr [rsp+48h+var_20], eax
0x18002483d  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024844  lea     rax, aGetlocationwri; "GetLocationWriter failed [0x%x]\n"
0x18002484b  mov     r8d, 2DB0h
0x180024851  mov     [rsp+48h+var_28], rax
0x180024856  call    cs:__imp_PuDbgPrint
0x18002485c  mov     rdi, [rbp+arg_20]
0x180024860  jmp     loc_180024980
0x180024865  mov     rdi, [rbp+arg_20]
0x180024869  lea     rdx, aIisinheritedpr; "IIsInheritedProperties"
0x180024870  mov     rcx, rdi; this
0x180024873  call    ?AssignKeyType@CLocationWriter@@AEAAJPEAG@Z; CLocationWriter::AssignKeyType(ushort *)
0x180024878  mov     ebx, eax
0x18002487a  test    eax, eax
0x18002487c  jns     short loc_1800248A1
0x18002487e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024885  jz      loc_180024980
0x18002488b  mov     dword ptr [rsp+48h+var_20], eax
0x18002488f  mov     r8d, 2DB7h
0x180024895  lea     rax, aInitializekeyt; "InitializeKeyTypeAsInherited failed [0x"...
0x18002489c  jmp     loc_180024960
0x1800248a1  mov     r12, [rbp+arg_18]
0x1800248a5  xor     esi, esi
0x1800248a7  lea     rax, [rbp+var_18]
0x1800248ab  mov     dword ptr [rbp+arg_20], esi
0x1800248ae  mov     [rsp+48h+var_20], rax; struct CMDBaseData **
0x1800248b3  lea     rdx, [rbp+arg_20]; unsigned int *
0x1800248b7  lea     rax, [rbp+var_10]
0x1800248bb  mov     [rbp+var_10], 0
0x1800248c3  xor     r9d, r9d; unsigned int
0x1800248c6  mov     [rsp+48h+var_28], rax; struct CMDBaseObject **
0x1800248cb  xor     r8d, r8d; unsigned int
0x1800248ce  mov     rcx, r14; this
0x1800248d1  call    ?EnumInheritableDataObject@CMDBaseObject@@QEAAJAEAKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumInheritableDataObject(ulong &,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x1800248d6  mov     ebx, eax
0x1800248d8  test    eax, eax
0x1800248da  js      short loc_180024946
0x1800248dc  mov     rcx, [rbp+var_18]; struct CMDBaseData *
0x1800248e0  test    rcx, rcx
0x1800248e3  jz      short loc_18002491C
0x1800248e5  cmp     [rbp+var_10], r14
0x1800248e9  jz      short loc_1800248FC
0x1800248eb  mov     r8, r12; struct IIS_CRYPTO_STORAGE *
0x1800248ee  mov     rdx, rdi; struct CLocationWriter *
0x1800248f1  call    ?SaveDataObject@@YAJPEAVCMDBaseData@@PEAVCLocationWriter@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@@Z; SaveDataObject(CMDBaseData *,CLocationWriter *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *)
0x1800248f6  mov     ebx, eax
0x1800248f8  test    eax, eax
0x1800248fa  js      short loc_180024900
0x1800248fc  inc     esi
0x1800248fe  jmp     short loc_1800248A7
0x180024900  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024907  jz      short loc_180024980
0x180024909  mov     dword ptr [rsp+48h+var_20], eax
0x18002490d  mov     r8d, 2DE0h
0x180024913  lea     rax, aSavedataobject_1; "SaveDataObject failed [0x%x]\n"
0x18002491a  jmp     short loc_180024960
0x18002491c  mov     rcx, rdi; this
0x18002491f  call    ?WriteLocation@CLocationWriter@@QEAAJH@Z; CLocationWriter::WriteLocation(int)
0x180024924  mov     ebx, eax
0x180024926  test    eax, eax
0x180024928  jns     short loc_180024980
0x18002492a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024931  jz      short loc_180024980
0x180024933  mov     dword ptr [rsp+48h+var_20], eax
0x180024937  mov     r8d, 2DE9h
0x18002493d  lea     rax, aWritelocationF; "WriteLocation failed [0x%x]\n"
0x180024944  jmp     short loc_180024960
0x180024946  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002494d  jz      short loc_180024980
0x18002494f  mov     dword ptr [rsp+48h+var_20], eax
0x180024953  mov     r8d, 2DC8h
0x180024959  lea     rax, aEnuminheritabl; "EnumInheritableDataObject failed [0x%x]"...
0x180024960  mov     rcx, cs:g_pDebug
0x180024967  lea     r9, aSaveinheritedo; "SaveInheritedOnly"
0x18002496e  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024975  mov     [rsp+48h+var_28], rax
0x18002497a  call    cs:__imp_PuDbgPrint
0x180024980  test    rdi, rdi
0x180024983  jz      short loc_18002498D
0x180024985  mov     rcx, rdi; this
0x180024988  call    ??_GCLocationWriter@@QEAAPEAXI@Z; CLocationWriter::`scalar deleting destructor'(uint)
0x18002498d  mov     rcx, r15; Block
0x180024990  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024995  mov     eax, ebx
0x180024997  add     rsp, 48h
0x18002499b  pop     r15
0x18002499d  pop     r14
0x18002499f  pop     r13
0x1800249a1  pop     r12
0x1800249a3  pop     rdi
0x1800249a4  pop     rsi
0x1800249a5  pop     rbx
0x1800249a6  pop     rbp
0x1800249a7  retn
```
