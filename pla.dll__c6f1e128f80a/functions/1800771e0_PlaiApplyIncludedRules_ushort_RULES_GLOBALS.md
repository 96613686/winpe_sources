# PlaiApplyIncludedRules(ushort *,_RULES_GLOBALS *)

- ea: `0x1800771e0`
- end: `0x180077b2d`
- name: `?PlaiApplyIncludedRules@@YAJPEAGPEAU_RULES_GLOBALS@@@Z`
- size: `2381`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _RULES_GLOBALS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c9adc`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x1800182a4`
- `0x180022eb8`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x18002f920`
- `0x180040dcc`
- `0x1800642a4`
- `0x1800771e0`
- `0x18009a170`
- `0x1800db7c0`
- `0x180139544`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180077497`
- `msvcrt!wcschr` at `0x180077497`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077ad3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800775bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800775bc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800775aa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800775aa`

## string_xrefs

- `0x1800778fc`: `Loading string table from own XML.`

## pseudocode

```c
__int64 __fastcall PlaiApplyIncludedRules(unsigned __int16 *a1, struct _RULES_GLOBALS *a2)
{
  HMODULE v3; // r12
  struct IXMLDOMDocument *v4; // r14
  __int128 v6; // xmm6
  unsigned int v7; // ecx
  unsigned __int16 *v8; // r15
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  int *v12; // rcx
  int HashTable; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const char *v17; // r8
  int v18; // r9d
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // edi
  unsigned __int64 v23; // rdx
  wchar_t *v24; // rsi
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  __int64 v30; // rax
  int StreamFromResource; // eax
  __int64 v32; // rax
  int XmlDocument; // eax
  __int64 v34; // rax
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  void (*v43)(struct _PLA_HASH_ENTRY *); // rdx
  __int64 result; // rax
  int v45; // [rsp+28h] [rbp-E0h]
  int v46; // [rsp+78h] [rbp-90h] BYREF
  int v47; // [rsp+80h] [rbp-88h] BYREF
  __int16 v48; // [rsp+88h] [rbp-80h] BYREF
  struct IXMLDOMDocument *v49; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v51; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 v52[64]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 v53[64]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v54[64]; // [rsp+1D8h] [rbp+D0h] BYREF
  unsigned __int16 v55[64]; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int16 v56[64]; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int16 v57[64]; // [rsp+358h] [rbp+250h] BYREF
  unsigned __int16 v58[64]; // [rsp+3D8h] [rbp+2D0h] BYREF
  unsigned __int16 v59[64]; // [rsp+458h] [rbp+350h] BYREF
  unsigned __int16 v60[64]; // [rsp+4D8h] [rbp+3D0h] BYREF
  unsigned __int16 v61[64]; // [rsp+558h] [rbp+450h] BYREF
  unsigned __int16 v62[64]; // [rsp+5D8h] [rbp+4D0h] BYREF
  unsigned __int16 v63[64]; // [rsp+658h] [rbp+550h] BYREF
  unsigned __int16 v64[64]; // [rsp+6D8h] [rbp+5D0h] BYREF

  v48 = 0;
  v49 = 0;
  v3 = 0;
  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  PlaiVariantInit(&pvarg);
  v6 = *((_OWORD *)a2 + 1);
  *((_OWORD *)a2 + 1) = 0;
  v8 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v45);
  if ( v8 )
  {
    HashTable = PlaiCreateHashTable(v7, (struct _RULES_GLOBALS *)((char *)a2 + 16));
    v9 = HashTable;
    if ( HashTable < 0 )
    {
      v47 = 0;
      v46 = HashTable;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_98;
      }
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v53[v15] );
      goto LABEL_96;
    }
    if ( *a1 == 64 )
    {
      v24 = wcschr(a1, 0x2Cu);
      if ( !v24 )
      {
        v9 = -2147467259;
        v46 = -2147467259;
        v47 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v56, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v56[v25] );
        goto LABEL_96;
      }
      *v24 = 0;
      v26 = PlaiExpandVariables(v8, v23, a1 + 1);
      v9 = v26;
      if ( v26 < 0 )
      {
        v46 = v26;
        v47 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v57, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v57[v27] );
        goto LABEL_96;
      }
      LibraryW = LoadLibraryW(v8);
      v3 = LibraryW;
      if ( !LibraryW )
      {
        LastError = GetLastError();
        v46 = PlaiHResultFromWin32(LastError);
        v9 = v46;
        v47 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v58, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v58[v30] );
        goto LABEL_96;
      }
      StreamFromResource = PlaiCreateStreamFromResource(LibraryW, v24 + 1, L"XML", (struct IStream **)&pvarg.llVal);
      v9 = StreamFromResource;
      if ( StreamFromResource < 0 )
      {
        v47 = 0;
        v46 = StreamFromResource;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        v32 = -1;
        do
          ++v32;
        while ( v59[v32] );
        goto LABEL_96;
      }
      v22 = 1;
      pvarg.vt = 13;
    }
    else
    {
      v16 = PlaiExpandVariables(v8, v14, a1);
      v9 = v16;
      if ( v16 < 0 )
      {
        v47 = 0;
        v46 = v16;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v54, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v54[v19] );
        goto LABEL_96;
      }
      v20 = PlaiSetVariantEx(v8, &pvarg, v17, v18);
      v9 = v20;
      if ( v20 < 0 )
      {
        v47 = 0;
        v46 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v55, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v55[v21] );
        goto LABEL_96;
      }
      v22 = (unsigned int)PlaiLoadStringTableFromMUIFile(v8, a2) >> 31;
    }
    XmlDocument = PlaiCreateXmlDocument((LPVOID *)&v49);
    v9 = XmlDocument;
    if ( XmlDocument < 0 )
    {
      v47 = 0;
      v46 = XmlDocument;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v60, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v60[v34] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v46,
          4,
          qword_180147320,
          1,
          &v47,
          4,
          "PlaiApplyIncludedRules",
          23);
      }
      v4 = v49;
      goto LABEL_98;
    }
    v4 = v49;
    lpVtbl = v49->lpVtbl;
    v51 = pvarg;
    v36 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, __int16 *))lpVtbl->load)(v49, &v51, &v48);
    v9 = v36;
    if ( v36 >= 0 )
    {
      if ( v48 )
      {
        if ( v22
          && (PlaiWriteRMLog(a2, 5, L"Loading string table from own XML."),
              v39 = PlaiForEachElement<_RULES_GLOBALS *,long (*)(IXMLDOMElement *,_RULES_GLOBALS *)>(
                      (__int64)v4,
                      L"Rules/StringTable/String",
                      (__int64 (__fastcall *)(__int64, __int64))PlaiAddStringToTable,
                      (__int64)a2),
              v9 = v39,
              v39 < 0) )
        {
          v47 = 0;
          v46 = v39;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_98;
          }
          PlaiWhoAmI(v63, 0x4000000000000800uLL);
          v40 = -1;
          do
            ++v40;
          while ( v63[v40] );
        }
        else
        {
          v41 = PlaiForEachElement<_RULES_GLOBALS *,long (*)(IXMLDOMElement *,_RULES_GLOBALS *)>(
                  (__int64)v4,
                  L"Rules/Group",
                  (__int64 (__fastcall *)(__int64, __int64))PlaiHandleGroup,
                  (__int64)a2);
          v9 = v41;
          if ( v41 >= 0 )
            goto LABEL_98;
          v47 = 0;
          v46 = v41;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_98;
          }
          PlaiWhoAmI(v64, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v64[v42] );
        }
      }
      else
      {
        v9 = -2147467259;
        v46 = -2147467259;
        v47 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_98;
        }
        PlaiWhoAmI(v62, 0x4000000000000800uLL);
        v38 = -1;
        do
          ++v38;
        while ( v62[v38] );
      }
    }
    else
    {
      v47 = 0;
      v46 = v36;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_98;
      }
      PlaiWhoAmI(v61, 0x4000000000000800uLL);
      v37 = -1;
      do
        ++v37;
      while ( v61[v37] );
    }
LABEL_96:
    v11 = &v46;
    v12 = &v47;
LABEL_97:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      v11,
      4,
      qword_180147320,
      1,
      v12,
      4,
      "PlaiApplyIncludedRules",
      23);
    goto LABEL_98;
  }
  v9 = -2147024882;
  v47 = -2147024882;
  v46 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v52, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v52[v10] );
    v11 = &v47;
    v12 = &v46;
    goto LABEL_97;
  }
LABEL_98:
  PlaiVariantClear(&pvarg);
  if ( v8 )
    PlaiFree(v8, 1);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v4->lpVtbl->Release)(v4);
  if ( v3 )
    FreeLibrary(v3);
  PlaiWriteRMLog(a2, 15, L"Destroying string table.");
  PlaiDestroyHashTable((struct _RULES_GLOBALS *)((char *)a2 + 16), v43);
  result = v9;
  *((_OWORD *)a2 + 1) = v6;
  return result;
}

```

## disassembly

```asm
0x1800771e0  mov     rax, rsp
0x1800771e3  mov     [rax+18h], rbx
0x1800771e7  push    rbp
0x1800771e8  push    rsi
0x1800771e9  push    rdi
0x1800771ea  push    r12
0x1800771ec  push    r13
0x1800771ee  push    r14
0x1800771f0  push    r15
0x1800771f2  lea     rbp, [rax-6A8h]
0x1800771f9  sub     rsp, 770h
0x180077200  movaps  xmmword ptr [rax-48h], xmm6
0x180077204  mov     rax, cs:__security_cookie
0x18007720b  xor     rax, rsp
0x18007720e  mov     [rbp+6A0h+var_50], rax
0x180077215  xor     esi, esi
0x180077217  mov     rdi, rcx
0x18007721a  xorps   xmm0, xmm0
0x18007721d  mov     [rbp+6A0h+var_720], si
0x180077221  xor     eax, eax
0x180077223  mov     [rbp+6A0h+var_718], rsi
0x180077227  lea     rcx, [rbp+6A0h+pvarg]; struct tagVARIANT *
0x18007722b  mov     qword ptr [rbp+6A0h+pvarg+10h], rax
0x18007722f  mov     r12d, esi
0x180077232  mov     r14d, esi
0x180077235  movups  xmmword ptr [rbp+6A0h+pvarg], xmm0
0x180077239  mov     r13, rdx
0x18007723c  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x180077241  lea     rbx, [r13+10h]
0x180077245  xorps   xmm0, xmm0
0x180077248  movups  xmm6, xmmword ptr [rbx]
0x18007724b  lea     r9, qword_180147320; char *
0x180077252  xor     r8d, r8d; int
0x180077255  lea     edx, [rsi+1]; int
0x180077258  mov     ecx, 800h; dwBytes
0x18007725d  movups  xmmword ptr [rbx], xmm0
0x180077260  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180077265  mov     r15, rax
0x180077268  test    rax, rax
0x18007726b  jnz     loc_1800772F1
0x180077271  cmp     dword ptr cs:xmmword_180169738, esi
0x180077277  mov     ebx, 8007000Eh
0x18007727c  mov     [rsp+7A0h+var_728], ebx
0x180077280  mov     [rsp+7A0h+var_730], esi
0x180077284  jz      loc_180077A9C
0x18007728a  mov     rdx, 4000000000000800h; unsigned __int64
0x180077294  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007729b  jz      loc_180077A9C
0x1800772a1  mov     rax, cs:qword_180169748
0x1800772a8  and     rax, rdx
0x1800772ab  cmp     cs:qword_180169748, rax
0x1800772b2  jnz     loc_180077A9C
0x1800772b8  lea     rcx, [rbp+6A0h+var_6D0]; unsigned __int16 *
0x1800772bc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800772c1  lea     rcx, [rbp+6A0h+var_6D0]
0x1800772c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800772c9  inc     rax
0x1800772cc  cmp     [rcx+rax*2], si
0x1800772d0  jnz     short loc_1800772C9
0x1800772d2  lea     ecx, [rax+rax]
0x1800772d5  add     rcx, 2
0x1800772d9  lea     rax, [rbp+6A0h+var_6D0]
0x1800772dd  mov     [rsp+7A0h+var_740], rcx
0x1800772e2  lea     r9, [rsp+7A0h+var_728]
0x1800772e7  lea     rcx, [rsp+7A0h+var_730]
0x1800772ec  jmp     loc_180077A42
0x1800772f1  mov     rdx, rbx; struct _PLA_HASH_TABLE *
0x1800772f4  call    ?PlaiCreateHashTable@@YAJKPEAU_PLA_HASH_TABLE@@@Z; PlaiCreateHashTable(ulong,_PLA_HASH_TABLE *)
0x1800772f9  mov     ebx, eax
0x1800772fb  test    eax, eax
0x1800772fd  jns     short loc_180077367
0x1800772ff  cmp     dword ptr cs:xmmword_180169738, esi
0x180077305  mov     [rsp+7A0h+var_728], esi
0x180077309  mov     [rsp+7A0h+var_730], eax
0x18007730d  jz      loc_180077A9C
0x180077313  mov     rdx, 4000000000000800h; unsigned __int64
0x18007731d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180077324  jz      loc_180077A9C
0x18007732a  mov     rax, cs:qword_180169748
0x180077331  and     rax, rdx
0x180077334  cmp     cs:qword_180169748, rax
0x18007733b  jnz     loc_180077A9C
0x180077341  lea     rcx, [rbp+6A0h+var_650]; unsigned __int16 *
0x180077345  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007734a  lea     rcx, [rbp+6A0h+var_650]
0x18007734e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077352  inc     rax
0x180077355  cmp     [rcx+rax*2], si
0x180077359  jnz     short loc_180077352
0x18007735b  lea     ecx, [rax+rax]
0x18007735e  lea     rax, [rbp+6A0h+var_650]
0x180077362  jmp     loc_180077A2F
0x180077367  mov     eax, 40h ; '@'
0x18007736c  cmp     ax, [rdi]
0x18007736f  jz      loc_18007748F
0x180077375  mov     r8, rdi; unsigned __int16 *
0x180077378  mov     rcx, r15; unsigned __int16 *
0x18007737b  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x180077380  mov     ebx, eax
0x180077382  test    eax, eax
0x180077384  jns     short loc_1800773F7
0x180077386  cmp     dword ptr cs:xmmword_180169738, esi
0x18007738c  mov     [rsp+7A0h+var_728], esi
0x180077390  mov     [rsp+7A0h+var_730], eax
0x180077394  jz      loc_180077A9C
0x18007739a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800773a4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800773ab  jz      loc_180077A9C
0x1800773b1  mov     rax, cs:qword_180169748
0x1800773b8  and     rax, rdx
0x1800773bb  cmp     cs:qword_180169748, rax
0x1800773c2  jnz     loc_180077A9C
0x1800773c8  lea     rcx, [rbp+6A0h+var_5D0]; unsigned __int16 *
0x1800773cf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800773d4  lea     rcx, [rbp+6A0h+var_5D0]
0x1800773db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800773df  inc     rax
0x1800773e2  cmp     [rcx+rax*2], si
0x1800773e6  jnz     short loc_1800773DF
0x1800773e8  lea     ecx, [rax+rax]
0x1800773eb  lea     rax, [rbp+6A0h+var_5D0]
0x1800773f2  jmp     loc_180077A2F
0x1800773f7  lea     rdx, [rbp+6A0h+pvarg]; pvarg
0x1800773fb  mov     rcx, r15; unsigned __int16 *
0x1800773fe  call    ?PlaiSetVariantEx@@YAJPEBGPEAUtagVARIANT@@PEBDH@Z; PlaiSetVariantEx(ushort const *,tagVARIANT *,char const *,int)
0x180077403  mov     ebx, eax
0x180077405  test    eax, eax
0x180077407  jns     short loc_18007747A
0x180077409  cmp     dword ptr cs:xmmword_180169738, esi
0x18007740f  mov     [rsp+7A0h+var_728], esi
0x180077413  mov     [rsp+7A0h+var_730], eax
0x180077417  jz      loc_180077A9C
0x18007741d  mov     rdx, 4000000000000800h; unsigned __int64
0x180077427  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007742e  jz      loc_180077A9C
0x180077434  mov     rax, cs:qword_180169748
0x18007743b  and     rax, rdx
0x18007743e  cmp     cs:qword_180169748, rax
0x180077445  jnz     loc_180077A9C
0x18007744b  lea     rcx, [rbp+6A0h+var_550]; unsigned __int16 *
0x180077452  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180077457  lea     rcx, [rbp+6A0h+var_550]
0x18007745e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077462  inc     rax
0x180077465  cmp     [rcx+rax*2], si
0x180077469  jnz     short loc_180077462
0x18007746b  lea     ecx, [rax+rax]
0x18007746e  lea     rax, [rbp+6A0h+var_550]
0x180077475  jmp     loc_180077A2F
0x18007747a  mov     rdx, r13; struct _RULES_GLOBALS *
0x18007747d  mov     rcx, r15; pcwszFilePath
0x180077480  call    ?PlaiLoadStringTableFromMUIFile@@YAJPEBGPEAU_RULES_GLOBALS@@@Z; PlaiLoadStringTableFromMUIFile(ushort const *,_RULES_GLOBALS *)
0x180077485  mov     edi, eax
0x180077487  shr     edi, 1Fh
0x18007748a  jmp     loc_1800776DA
0x18007748f  mov     edx, 2Ch ; ','; Ch
0x180077494  mov     rcx, rdi; Str
0x180077497  call    cs:__imp_wcschr
0x18007749d  mov     rsi, rax
0x1800774a0  xor     eax, eax
0x1800774a2  test    rsi, rsi
0x1800774a5  jnz     short loc_18007751F
0x1800774a7  cmp     dword ptr cs:xmmword_180169738, esi
0x1800774ad  mov     eax, 80004005h
0x1800774b2  mov     ebx, eax
0x1800774b4  mov     [rsp+7A0h+var_730], eax
0x1800774b8  mov     [rsp+7A0h+var_728], esi
0x1800774bc  jz      loc_180077A9C
0x1800774c2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800774cc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800774d3  jz      loc_180077A9C
0x1800774d9  mov     rax, cs:qword_180169748
0x1800774e0  and     rax, rdx
0x1800774e3  cmp     cs:qword_180169748, rax
0x1800774ea  jnz     loc_180077A9C
0x1800774f0  lea     rcx, [rbp+6A0h+var_4D0]; unsigned __int16 *
0x1800774f7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800774fc  lea     rcx, [rbp+6A0h+var_4D0]
0x180077503  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077507  inc     rax
0x18007750a  cmp     [rcx+rax*2], si
0x18007750e  jnz     short loc_180077507
0x180077510  lea     ecx, [rax+rax]
0x180077513  lea     rax, [rbp+6A0h+var_4D0]
0x18007751a  jmp     loc_180077A2F
0x18007751f  lea     r8, [rdi+2]; unsigned __int16 *
0x180077523  mov     [rsi], ax
0x180077526  mov     rcx, r15; unsigned __int16 *
0x180077529  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x18007752e  mov     ebx, eax
0x180077530  test    eax, eax
0x180077532  jns     short loc_1800775A7
0x180077534  xor     esi, esi
0x180077536  mov     [rsp+7A0h+var_730], eax
0x18007753a  cmp     dword ptr cs:xmmword_180169738, esi
0x180077540  mov     [rsp+7A0h+var_728], esi
0x180077544  jz      loc_180077A9C
0x18007754a  mov     rdx, 4000000000000800h; unsigned __int64
0x180077554  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007755b  jz      loc_180077A9C
0x180077561  mov     rax, cs:qword_180169748
0x180077568  and     rax, rdx
0x18007756b  cmp     cs:qword_180169748, rax
0x180077572  jnz     loc_180077A9C
0x180077578  lea     rcx, [rbp+6A0h+var_450]; unsigned __int16 *
0x18007757f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180077584  lea     rcx, [rbp+6A0h+var_450]
0x18007758b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007758f  inc     rax
0x180077592  cmp     [rcx+rax*2], si
0x180077596  jnz     short loc_18007758F
0x180077598  lea     ecx, [rax+rax]
0x18007759b  lea     rax, [rbp+6A0h+var_450]
0x1800775a2  jmp     loc_180077A2F
0x1800775a7  mov     rcx, r15; lpLibFileName
0x1800775aa  call    cs:__imp_LoadLibraryW
0x1800775b0  mov     r12, rax
0x1800775b3  test    rax, rax
0x1800775b6  jnz     loc_18007763E
0x1800775bc  call    cs:__imp_GetLastError
0x1800775c2  mov     ecx, eax; unsigned int
0x1800775c4  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800775c9  xor     esi, esi
0x1800775cb  mov     [rsp+7A0h+var_730], eax
0x1800775cf  cmp     dword ptr cs:xmmword_180169738, esi
0x1800775d5  mov     ebx, eax
0x1800775d7  mov     [rsp+7A0h+var_728], esi
0x1800775db  jz      loc_180077A9C
0x1800775e1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800775eb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800775f2  jz      loc_180077A9C
0x1800775f8  mov     rax, cs:qword_180169748
0x1800775ff  and     rax, rdx
0x180077602  cmp     cs:qword_180169748, rax
0x180077609  jnz     loc_180077A9C
0x18007760f  lea     rcx, [rbp+6A0h+var_3D0]; unsigned __int16 *
0x180077616  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007761b  lea     rcx, [rbp+6A0h+var_3D0]
0x180077622  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077626  inc     rax
0x180077629  cmp     [rcx+rax*2], si
0x18007762d  jnz     short loc_180077626
0x18007762f  lea     ecx, [rax+rax]
0x180077632  lea     rax, [rbp+6A0h+var_3D0]
0x180077639  jmp     loc_180077A2F
0x18007763e  lea     rdx, [rsi+2]; unsigned __int16 *
0x180077642  mov     rcx, rax; hModule
0x180077645  lea     r9, [rbp+6A0h+pvarg+8]; struct IStream **
0x180077649  lea     r8, aXml_0; "XML"
0x180077650  call    ?PlaiCreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z; PlaiCreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)
0x180077655  xor     esi, esi
0x180077657  mov     ebx, eax
0x180077659  test    eax, eax
0x18007765b  jns     short loc_1800776CE
0x18007765d  cmp     dword ptr cs:xmmword_180169738, esi
0x180077663  mov     [rsp+7A0h+var_728], esi
0x180077667  mov     [rsp+7A0h+var_730], eax
0x18007766b  jz      loc_180077A9C
0x180077671  mov     rdx, 4000000000000800h; unsigned __int64
0x18007767b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180077682  jz      loc_180077A9C
0x180077688  mov     rax, cs:qword_180169748
0x18007768f  and     rax, rdx
0x180077692  cmp     cs:qword_180169748, rax
0x180077699  jnz     loc_180077A9C
0x18007769f  lea     rcx, [rbp+6A0h+var_350]; unsigned __int16 *
0x1800776a6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800776ab  lea     rcx, [rbp+6A0h+var_350]
0x1800776b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800776b6  inc     rax
0x1800776b9  cmp     [rcx+rax*2], si
0x1800776bd  jnz     short loc_1800776B6
0x1800776bf  lea     ecx, [rax+rax]
0x1800776c2  lea     rax, [rbp+6A0h+var_350]
0x1800776c9  jmp     loc_180077A2F
0x1800776ce  mov     edi, 1
0x1800776d3  lea     eax, [rdi+0Ch]
0x1800776d6  mov     word ptr [rbp+6A0h+pvarg], ax
0x1800776da  lea     rcx, [rbp+6A0h+var_718]; struct IXMLDOMDocument **
0x1800776de  call    ?PlaiCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@@Z; PlaiCreateXmlDocument(IXMLDOMDocument * *)
0x1800776e3  mov     ebx, eax
0x1800776e5  test    eax, eax
0x1800776e7  jns     loc_1800777CF
0x1800776ed  cmp     dword ptr cs:xmmword_180169738, esi
0x1800776f3  mov     [rsp+7A0h+var_728], esi
0x1800776f7  mov     [rsp+7A0h+var_730], eax
0x1800776fb  jz      loc_1800777C6
0x180077701  mov     rdx, 4000000000000800h; unsigned __int64
0x18007770b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180077712  jz      loc_1800777C6
0x180077718  mov     rax, cs:qword_180169748
0x18007771f  and     rax, rdx
0x180077722  cmp     cs:qword_180169748, rax
0x180077729  jnz     loc_1800777C6
0x18007772f  lea     rcx, [rbp+6A0h+var_2D0]; unsigned __int16 *
0x180077736  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007773b  lea     rcx, [rbp+6A0h+var_2D0]
0x180077742  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077746  inc     rax
0x180077749  cmp     [rcx+rax*2], si
  ... truncated ...
```
