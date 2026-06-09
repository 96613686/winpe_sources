# ReadClass(void * *,ulong *,IIS_CRYPTO_STORAGE *,_FILETIME *)

- ea: `0x18000ff10`
- end: `0x180010314`
- name: `?ReadClass@@YAJPEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@PEAU_FILETIME@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(void **, unsigned int *, struct IIS_CRYPTO_STORAGE *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001031c`

## callees

- `0x180007d90`
- `0x180008a08`
- `0x180008a14`
- `0x18000ff10`
- `0x18002267c`
- `0x180022ab8`
- `0x18003098e`
- `0x1800309d0`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x1800100be`
- `IisRTL!PuDbgPrintW` at `0x1800100be`

## string_xrefs

- `0x1800100b2`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x180010098`: `[ReadClasses] ReadMetaObject for class: %s failed with hr=0x%x.\n`
- `0x1800100a6`: `ReadClass`
- `0x18001015f`: `[ReadClasses] ReadDataObject for class: %s, property: Container failed with hr=0x%x.\n`

## pseudocode

```c
__int64 __fastcall ReadClass(void **a1, unsigned int *a2, struct IIS_CRYPTO_STORAGE *a3, struct _FILETIME *a4)
{
  _WORD *v4; // rax
  __int64 v5; // r15
  __int64 v6; // r13
  unsigned int v7; // edx
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // r14
  unsigned int v11; // ecx
  unsigned int v12; // eax
  int v13; // ebx
  unsigned __int16 *v14; // r12
  size_t v15; // rbx
  unsigned __int16 *v16; // rdi
  unsigned __int16 *v17; // rcx
  size_t v18; // rbx
  __int64 v19; // rax
  unsigned __int16 *v20; // rdi
  void **v21; // r13
  __int64 v22; // rbx
  struct _FILETIME *v23; // r8
  int v24; // r9d
  int v25; // eax
  _DWORD *v26; // rax
  struct CMDBaseObject *v27; // rdi
  int v28; // ecx
  int DataObject; // eax
  unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int Properties; // eax
  __int64 v33; // rax
  struct IIS_CRYPTO_STORAGE *v34; // r13
  int v35; // eax
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h] BYREF
  int v41; // [rsp+5Ch] [rbp-A4h] BYREF
  struct IIS_CRYPTO_STORAGE *v42; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v43; // [rsp+68h] [rbp-98h] BYREF
  struct CMDBaseObject *v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45[3]; // [rsp+78h] [rbp-88h] BYREF
  int v46; // [rsp+84h] [rbp-7Ch]
  void *v47[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v48; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v49; // [rsp+C0h] [rbp-40h]
  int *v50; // [rsp+C8h] [rbp-38h]
  int *v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+D8h] [rbp-28h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  void **v54; // [rsp+F0h] [rbp-10h]
  struct _FILETIME *v55; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v56[264]; // [rsp+100h] [rbp+0h] BYREF

  v4 = a1[1];
  v5 = -1;
  v55 = a4;
  v6 = -1;
  v42 = a3;
  v54 = a1;
  v44 = 0;
  do
    ++v6;
  while ( v4[v6] );
  v7 = g_cchSlashSchemaSlashClasses;
  v8 = 0;
  v37 = 1;
  v9 = 0;
  v41 = 1;
  v36 = 0;
  v40 = 0;
  v38 = 0;
  v52 = 0;
  v53 = 0;
  v39 = 0;
  v43 = 0;
  if ( (unsigned int)v6 > -2 - g_cchSlash - g_cchSlashSchemaSlashClasses )
    return 2147942487LL;
  v11 = v6 + g_cchSlashSchemaSlashClasses + g_cchSlash;
  v12 = v11 + 1;
  if ( v11 + 1 >= v11 )
  {
    v14 = v56;
    if ( v12 > 0x104 )
    {
      v14 = (unsigned __int16 *)operator new[](saturated_mul(v12, 2u));
      if ( !v14 )
      {
        v13 = -2147024882;
LABEL_38:
        operator delete(v14);
LABEL_39:
        if ( v8 )
          operator delete(v8);
        if ( v9 )
          operator delete(v9);
        return (unsigned int)v13;
      }
      v7 = g_cchSlashSchemaSlashClasses;
    }
    v15 = v7;
    memcpy_0(v14, L"/Schema/Classes", v15 * 2);
    v16 = &v14[v15];
    v17 = &v14[v15];
    v18 = g_cchSlash;
    memcpy_0(v17, L"/", v18 * 2);
    v19 = (unsigned int)v6;
    v20 = &v16[v18];
    v21 = v54;
    v22 = v19;
    memcpy_0(v20, v54[1], 2 * v19);
    v23 = v55;
    v20[v22] = 0;
    v25 = ReadMetaObject(&v44, v14, v23, v24);
    v13 = v25;
    if ( v25 >= 0 )
    {
      v50 = &v36;
      v36 = 6351;
      v47[2] = &v40;
      v37 = 1;
      v51 = &v41;
      v47[1] = &v37;
      v26 = v21[10];
      v47[0] = 0;
      v27 = v44;
      v49 = v14;
      v28 = (*v26 >> 6) & 1;
      v48 = (unsigned __int16 *)&v38;
      v38 = v28;
      v46 = 4;
      DataObject = ReadDataObject(v44, (unsigned __int16 **)v47, v45, v42);
      v13 = DataObject;
      if ( DataObject >= 0 )
      {
        v30 = (unsigned __int16 *)v21[14];
        v36 = 6350;
        v37 = 2;
        if ( v30 )
        {
          v48 = v30;
          v31 = -1;
          do
            ++v31;
          while ( v30[v31] );
          v46 = 2 * v31 + 2;
        }
        else
        {
          v48 = (unsigned __int16 *)&qword_18003A6B0;
          v46 = 2;
        }
        v13 = ReadDataObject(v27, (unsigned __int16 **)v47, v45, v42);
        if ( v13 >= 0 )
        {
          Properties = GetProperties((const unsigned __int16 *)v21[1], &v43, &v39);
          v9 = v43;
          v13 = Properties;
          if ( Properties < 0 )
          {
            v8 = v39;
          }
          else
          {
            v36 = 6355;
            v37 = 2;
            if ( v43 )
            {
              v48 = v43;
              v33 = -1;
              do
                ++v33;
              while ( v43[v33] );
              v46 = 2 * v33 + 2;
            }
            else
            {
              v46 = 2;
              v48 = (unsigned __int16 *)&qword_18003A6B0;
            }
            v34 = v42;
            v35 = ReadDataObject(v27, (unsigned __int16 **)v47, v45, v42);
            v8 = v39;
            v13 = v35;
            if ( v35 >= 0 )
            {
              v36 = 6356;
              v37 = 2;
              if ( v39 )
              {
                v48 = v39;
                do
                  ++v5;
                while ( v39[v5] );
                v46 = 2 * v5 + 2;
              }
              else
              {
                v46 = 2;
                v48 = (unsigned __int16 *)&qword_18003A6B0;
              }
              v13 = ReadDataObject(v27, (unsigned __int16 **)v47, v45, v34);
            }
          }
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
          1654,
          "ReadClass",
          L"[ReadClasses] ReadDataObject for class: %s, property: Container failed with hr=0x%x.\n",
          v14,
          DataObject);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        1618,
        "ReadClass",
        L"[ReadClasses] ReadMetaObject for class: %s failed with hr=0x%x.\n",
        v14,
        v25);
    }
    if ( v56 == v14 )
      goto LABEL_39;
    goto LABEL_38;
  }
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x18000ff10  mov     [rsp-8+arg_8], rbx
0x18000ff15  push    rbp
0x18000ff16  push    rsi
0x18000ff17  push    rdi
0x18000ff18  push    r12
0x18000ff1a  push    r13
0x18000ff1c  push    r14
0x18000ff1e  push    r15
0x18000ff20  lea     rbp, [rsp-220h]
0x18000ff28  sub     rsp, 320h
0x18000ff2f  mov     rax, cs:__security_cookie
0x18000ff36  xor     rax, rsp
0x18000ff39  mov     [rbp+250h+var_40], rax
0x18000ff40  mov     rax, [rcx+8]
0x18000ff44  xor     edi, edi
0x18000ff46  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000ff4a  mov     [rbp+250h+var_258], r9
0x18000ff4e  mov     r13, r15
0x18000ff51  mov     [rsp+350h+var_2F0], r8
0x18000ff56  mov     [rbp+250h+var_260], rcx
0x18000ff5a  mov     [rsp+350h+var_2E0], rdi
0x18000ff5f  inc     r13
0x18000ff62  cmp     [rax+r13*2], di
0x18000ff67  jnz     short loc_18000FF5F
0x18000ff69  mov     ecx, cs:?g_cchSlash@@3KA; ulong g_cchSlash
0x18000ff6f  mov     eax, 1
0x18000ff74  mov     edx, cs:?g_cchSlashSchemaSlashClasses@@3KA; ulong g_cchSlashSchemaSlashClasses
0x18000ff7a  mov     rsi, rdi
0x18000ff7d  mov     [rsp+350h+var_30C], eax
0x18000ff81  mov     r14, rdi
0x18000ff84  mov     [rsp+350h+var_2F4], eax
0x18000ff88  mov     eax, 0FFFFFFFEh
0x18000ff8d  sub     eax, ecx
0x18000ff8f  mov     [rsp+350h+var_310], edi
0x18000ff93  sub     eax, edx
0x18000ff95  mov     [rsp+350h+var_2F8], edi
0x18000ff99  mov     [rsp+350h+var_308], edi
0x18000ff9d  mov     [rbp+250h+var_278], rdi
0x18000ffa1  mov     [rbp+250h+var_270], rdi
0x18000ffa5  mov     [rsp+350h+var_300], rdi
0x18000ffaa  mov     [rsp+350h+var_2E8], rdi
0x18000ffaf  cmp     r13d, eax
0x18000ffb2  jbe     short loc_18000FFBE
0x18000ffb4  mov     eax, 80070057h
0x18000ffb9  jmp     loc_1800102EA
0x18000ffbe  add     ecx, edx
0x18000ffc0  add     ecx, r13d
0x18000ffc3  lea     eax, [rcx+1]
0x18000ffc6  cmp     eax, ecx
0x18000ffc8  jnb     short loc_18000FFD4
0x18000ffca  mov     ebx, 80070216h
0x18000ffcf  jmp     loc_1800102E8
0x18000ffd4  lea     r12, [rbp+250h+var_250]
0x18000ffd8  cmp     eax, 104h
0x18000ffdd  jbe     short loc_18001000D
0x18000ffdf  mov     ecx, eax
0x18000ffe1  mov     eax, 2
0x18000ffe6  mul     rcx
0x18000ffe9  cmovb   rax, r15
0x18000ffed  mov     rcx, rax; unsigned __int64
0x18000fff0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fff5  mov     r12, rax
0x18000fff8  test    rax, rax
0x18000fffb  jnz     short loc_180010007
0x18000fffd  mov     ebx, 8007000Eh
0x180010002  jmp     loc_1800102C6
0x180010007  mov     edx, cs:?g_cchSlashSchemaSlashClasses@@3KA; ulong g_cchSlashSchemaSlashClasses
0x18001000d  mov     eax, edx
0x18001000f  mov     rcx, r12; void *
0x180010012  lea     rdx, aSchemaClasses; "/Schema/Classes"
0x180010019  lea     rbx, [rax+rax]
0x18001001d  mov     r8, rbx; Size
0x180010020  call    memcpy_0
0x180010025  mov     eax, cs:?g_cchSlash@@3KA; ulong g_cchSlash
0x18001002b  lea     rdi, [rbx+r12]
0x18001002f  lea     rdx, asc_180033DAC; "/"
0x180010036  mov     rcx, rdi; void *
0x180010039  lea     rbx, [rax+rax]
0x18001003d  mov     r8, rbx; Size
0x180010040  call    memcpy_0
0x180010045  mov     eax, r13d
0x180010048  add     rdi, rbx
0x18001004b  mov     r13, [rbp+250h+var_260]
0x18001004f  mov     rcx, rdi; void *
0x180010052  lea     rbx, [rax+rax]
0x180010056  mov     rdx, [r13+8]; Src
0x18001005a  mov     r8, rbx; Size
0x18001005d  call    memcpy_0
0x180010062  mov     r8, [rbp+250h+var_258]; struct _FILETIME *
0x180010066  xor     ecx, ecx
0x180010068  mov     [rbx+rdi], cx
0x18001006c  mov     rdx, r12; unsigned __int16 *
0x18001006f  lea     rcx, [rsp+350h+var_2E0]; struct CMDBaseObject **
0x180010074  call    ?ReadMetaObject@@YAJAEAPEAVCMDBaseObject@@PEAGPEAU_FILETIME@@H@Z; ReadMetaObject(CMDBaseObject * &,ushort *,_FILETIME *,int)
0x180010079  xor     edi, edi
0x18001007b  mov     ebx, eax
0x18001007d  test    eax, eax
0x18001007f  jns     short loc_1800100C9
0x180010081  test    byte ptr cs:g_dwDebugFlags, 3
0x180010088  jz      loc_1800102BD
0x18001008e  mov     [rsp+350h+var_320], eax
0x180010092  mov     r8d, 652h
0x180010098  lea     rax, aReadclassesRea; "[ReadClasses] ReadMetaObject for class:"...
0x18001009f  mov     rcx, cs:g_pDebug
0x1800100a6  lea     r9, aReadclass; "ReadClass"
0x1800100ad  mov     [rsp+350h+var_328], r12
0x1800100b2  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x1800100b9  mov     [rsp+350h+var_330], rax
0x1800100be  call    cs:__imp_PuDbgPrintW
0x1800100c4  jmp     loc_1800102BD
0x1800100c9  mov     r9, [rsp+350h+var_2F0]; struct IIS_CRYPTO_STORAGE *
0x1800100ce  lea     rax, [rsp+350h+var_310]
0x1800100d3  mov     [rbp+250h+var_288], rax
0x1800100d7  lea     r8, [rsp+350h+var_2D8]; unsigned int *
0x1800100dc  lea     rax, [rsp+350h+var_2F8]
0x1800100e1  mov     [rsp+350h+var_310], 18CFh
0x1800100e9  mov     [rbp+250h+var_2A0], rax
0x1800100ed  lea     rdx, [rbp+250h+var_2B0]; void **
0x1800100f1  lea     rax, [rsp+350h+var_2F4]
0x1800100f6  mov     [rsp+350h+var_30C], 1
0x1800100fe  mov     [rbp+250h+var_280], rax
0x180010102  lea     rax, [rsp+350h+var_30C]
0x180010107  mov     [rbp+250h+var_2A8], rax
0x18001010b  mov     rax, [r13+50h]
0x18001010f  mov     [rbp+250h+var_2B0], rdi
0x180010113  mov     rdi, [rsp+350h+var_2E0]
0x180010118  mov     [rbp+250h+var_290], r12
0x18001011c  mov     ecx, [rax]
0x18001011e  lea     rax, [rsp+350h+var_308]
0x180010123  shr     ecx, 6
0x180010126  and     ecx, 1
0x180010129  mov     [rbp+250h+var_298], rax
0x18001012d  mov     [rsp+350h+var_308], ecx
0x180010131  mov     rcx, rdi; this
0x180010134  mov     [rbp+250h+var_2CC], 4
0x18001013b  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x180010140  xor     edx, edx
0x180010142  mov     ebx, eax
0x180010144  test    eax, eax
0x180010146  jns     short loc_18001016B
0x180010148  test    byte ptr cs:g_dwDebugFlags, 3
0x18001014f  jz      loc_1800102BD
0x180010155  mov     [rsp+350h+var_320], eax
0x180010159  mov     r8d, 676h
0x18001015f  lea     rax, aReadclassesRea_0; "[ReadClasses] ReadDataObject for class:"...
0x180010166  jmp     loc_18001009F
0x18001016b  mov     rcx, [r13+70h]
0x18001016f  lea     rax, qword_18003A6B0
0x180010176  mov     [rsp+350h+var_310], 18CEh
0x18001017e  mov     [rsp+350h+var_30C], 2
0x180010186  test    rcx, rcx
0x180010189  jnz     short loc_180010198
0x18001018b  mov     [rbp+250h+var_298], rax
0x18001018f  mov     [rbp+250h+var_2CC], 2
0x180010196  jmp     short loc_1800101B2
0x180010198  mov     [rbp+250h+var_298], rcx
0x18001019c  mov     rax, r15
0x18001019f  inc     rax
0x1800101a2  cmp     [rcx+rax*2], dx
0x1800101a6  jnz     short loc_18001019F
0x1800101a8  lea     eax, ds:2[rax*2]
0x1800101af  mov     [rbp+250h+var_2CC], eax
0x1800101b2  mov     r9, [rsp+350h+var_2F0]; struct IIS_CRYPTO_STORAGE *
0x1800101b7  lea     r8, [rsp+350h+var_2D8]; unsigned int *
0x1800101bc  lea     rdx, [rbp+250h+var_2B0]; void **
0x1800101c0  mov     rcx, rdi; this
0x1800101c3  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x1800101c8  mov     ebx, eax
0x1800101ca  test    eax, eax
0x1800101cc  js      loc_1800102BD
0x1800101d2  mov     rcx, [r13+8]; unsigned __int16 *
0x1800101d6  lea     r8, [rsp+350h+var_300]; unsigned __int16 **
0x1800101db  lea     rdx, [rsp+350h+var_2E8]; unsigned __int16 **
0x1800101e0  call    ?GetProperties@@YAJPEBGPEAPEAG1@Z; GetProperties(ushort const *,ushort * *,ushort * *)
0x1800101e5  mov     r14, [rsp+350h+var_2E8]
0x1800101ea  mov     ebx, eax
0x1800101ec  test    eax, eax
0x1800101ee  js      loc_1800102B8
0x1800101f4  mov     [rsp+350h+var_310], 18D3h
0x1800101fc  mov     [rsp+350h+var_30C], 2
0x180010204  test    r14, r14
0x180010207  jnz     short loc_18001021D
0x180010209  lea     rax, qword_18003A6B0
0x180010210  mov     [rbp+250h+var_2CC], 2
0x180010217  mov     [rbp+250h+var_298], rax
0x18001021b  jmp     short loc_180010238
0x18001021d  mov     [rbp+250h+var_298], r14
0x180010221  mov     rax, r15
0x180010224  inc     rax
0x180010227  cmp     [r14+rax*2], si
0x18001022c  jnz     short loc_180010224
0x18001022e  lea     eax, ds:2[rax*2]
0x180010235  mov     [rbp+250h+var_2CC], eax
0x180010238  mov     r13, [rsp+350h+var_2F0]
0x18001023d  lea     r8, [rsp+350h+var_2D8]; unsigned int *
0x180010242  mov     r9, r13; struct IIS_CRYPTO_STORAGE *
0x180010245  lea     rdx, [rbp+250h+var_2B0]; void **
0x180010249  mov     rcx, rdi; this
0x18001024c  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x180010251  mov     rsi, [rsp+350h+var_300]
0x180010256  mov     ebx, eax
0x180010258  test    eax, eax
0x18001025a  js      short loc_1800102BD
0x18001025c  xor     ecx, ecx
0x18001025e  mov     [rsp+350h+var_310], 18D4h
0x180010266  mov     [rsp+350h+var_30C], 2
0x18001026e  test    rsi, rsi
0x180010271  jnz     short loc_180010287
0x180010273  lea     rax, qword_18003A6B0
0x18001027a  mov     [rbp+250h+var_2CC], 2
0x180010281  mov     [rbp+250h+var_298], rax
0x180010285  jmp     short loc_1800102A0
0x180010287  mov     [rbp+250h+var_298], rsi
0x18001028b  inc     r15
0x18001028e  cmp     [rsi+r15*2], cx
0x180010293  jnz     short loc_18001028B
0x180010295  lea     eax, ds:2[r15*2]
0x18001029d  mov     [rbp+250h+var_2CC], eax
0x1800102a0  mov     r9, r13; struct IIS_CRYPTO_STORAGE *
0x1800102a3  lea     r8, [rsp+350h+var_2D8]; unsigned int *
0x1800102a8  lea     rdx, [rbp+250h+var_2B0]; void **
0x1800102ac  mov     rcx, rdi; this
0x1800102af  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x1800102b4  mov     ebx, eax
0x1800102b6  jmp     short loc_1800102BD
0x1800102b8  mov     rsi, [rsp+350h+var_300]
0x1800102bd  lea     rax, [rbp+250h+var_250]
0x1800102c1  cmp     rax, r12
0x1800102c4  jz      short loc_1800102CE
0x1800102c6  mov     rcx, r12; Block
0x1800102c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102ce  test    rsi, rsi
0x1800102d1  jz      short loc_1800102DB
0x1800102d3  mov     rcx, rsi; Block
0x1800102d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102db  test    r14, r14
0x1800102de  jz      short loc_1800102E8
0x1800102e0  mov     rcx, r14; Block
0x1800102e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102e8  mov     eax, ebx
0x1800102ea  mov     rcx, [rbp+250h+var_40]
0x1800102f1  xor     rcx, rsp; StackCookie
0x1800102f4  call    __security_check_cookie
0x1800102f9  mov     rbx, [rsp+350h+arg_8]
0x180010301  add     rsp, 320h
0x180010308  pop     r15
0x18001030a  pop     r14
0x18001030c  pop     r13
0x18001030e  pop     r12
0x180010310  pop     rdi
0x180010311  pop     rsi
0x180010312  pop     rbp
0x180010313  retn
```
