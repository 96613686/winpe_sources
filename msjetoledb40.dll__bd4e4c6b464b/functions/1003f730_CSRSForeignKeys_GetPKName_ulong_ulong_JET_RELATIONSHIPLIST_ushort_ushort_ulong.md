# CSRSForeignKeys::GetPKName(ulong,ulong,JET_RELATIONSHIPLIST *,ushort *,ushort *,ulong)

- ea: `0x1003f730`
- end: `0x1003fcc7`
- name: `?GetPKName@CSRSForeignKeys@@QAGJKKPAUJET_RELATIONSHIPLIST@@PAG1K@Z`
- size: `1431`
- prototype: `int __userpurge@<eax>(JET_SESID@<edx>, CSRSForeignKeys *this, JET_TABLEID *, unsigned int, struct JET_RELATIONSHIPLIST *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1003eda0`

## callees

- `0x1000d4a0`
- `0x1003f730`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003f966`
- `msvcrt!_wcsicmp` at `0x1003fb67`
- `msvcrt!_wcsicmp` at `0x1003f966`
- `msvcrt!_wcsicmp` at `0x1003fb67`
- `msjet40!__imp__JetCloseTable@8` at `0x1003fc37`
- `msjet40!__imp__JetCloseTable@8` at `0x1003fc37`
- `msjet40!__imp__JetGetBookmark@20` at `0x1003f7b6`
- `msjet40!__imp__JetGetBookmark@20` at `0x1003f7b6`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003f789`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003f789`
- `msjet40!__imp__JetGotoBookmark@16` at `0x1003fbb9`
- `msjet40!__imp__JetGotoBookmark@16` at `0x1003fc54`
- `msjet40!__imp__JetGotoBookmark@16` at `0x1003fbb9`
- `msjet40!__imp__JetGotoBookmark@16` at `0x1003fc54`
- `msjet40!__imp__JetMove@16` at `0x1003fa6e`
- `msjet40!__imp__JetMove@16` at `0x1003fa8c`
- `msjet40!__imp__JetMove@16` at `0x1003fbe0`
- `msjet40!__imp__JetMove@16` at `0x1003fc7a`
- `msjet40!__imp__JetMove@16` at `0x1003fa6e`
- `msjet40!__imp__JetMove@16` at `0x1003fa8c`
- `msjet40!__imp__JetMove@16` at `0x1003fbe0`
- `msjet40!__imp__JetMove@16` at `0x1003fc7a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f7e7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f81b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f868`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f8a6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f8e4`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f92a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f996`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f9c7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fa1a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fac0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fb06`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fb49`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f7e7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f81b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f868`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f8a6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f8e4`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f92a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f996`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f9c7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fa1a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fac0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fb06`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003fb49`

## pseudocode

```c
int __userpurge CSRSForeignKeys::GetPKName@<eax>(
        JET_SESID a1@<edx>,
        CSRSForeignKeys *this,
        JET_TABLEID *a3,
        unsigned int a4,
        struct JET_RELATIONSHIPLIST *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8)
{
  int v9; // edi
  JET_ERR IndexInfo; // esi
  int v11; // edi
  int v12; // eax
  int v13; // esi
  JET_ERR v15; // eax
  const unsigned __int16 *v16; // [esp+0h] [ebp-388h]
  unsigned int v17; // [esp+4h] [ebp-384h]
  int v18; // [esp+10h] [ebp-378h] BYREF
  int v19; // [esp+14h] [ebp-374h] BYREF
  int pvData; // [esp+18h] [ebp-370h] BYREF
  _BYTE v21[4]; // [esp+1Ch] [ebp-36Ch] BYREF
  unsigned int pcbActual; // [esp+20h] [ebp-368h] BYREF
  int v23; // [esp+24h] [ebp-364h] BYREF
  int v24; // [esp+28h] [ebp-360h] BYREF
  JET_TABLEID *v25; // [esp+2Ch] [ebp-35Ch]
  int v26; // [esp+30h] [ebp-358h]
  unsigned int v27; // [esp+34h] [ebp-354h] BYREF
  _BYTE v28[4]; // [esp+38h] [ebp-350h] BYREF
  JET_TABLEID tableid; // [esp+3Ch] [ebp-34Ch]
  int v30; // [esp+40h] [ebp-348h]
  JET_COLUMNID v31; // [esp+44h] [ebp-344h]
  JET_COLUMNID columnid; // [esp+48h] [ebp-340h]
  JET_COLUMNID v33; // [esp+58h] [ebp-330h]
  JET_COLUMNID v34; // [esp+5Ch] [ebp-32Ch]
  JET_COLUMNID v35; // [esp+6Ch] [ebp-31Ch]
  JET_COLUMNID v36; // [esp+70h] [ebp-318h]
  _BYTE pvBookmark[256]; // [esp+74h] [ebp-314h] BYREF
  wchar_t v38[66]; // [esp+174h] [ebp-214h] BYREF
  wchar_t v39[66]; // [esp+1F8h] [ebp-190h] BYREF
  wchar_t String2[66]; // [esp+27Ch] [ebp-10Ch] BYREF
  wchar_t String1[66]; // [esp+300h] [ebp-88h] BYREF

  v9 = 1;
  v25 = a3;
  *(_WORD *)a5 = 0;
  pcbActual = 0;
  v26 = 1;
  IndexInfo = JetGetIndexInfo(a1, this, a4, 0, v28, 60, 1);
  if ( IndexInfo < 0 )
    goto LABEL_37;
  IndexInfo = JetGetBookmark(a1, v25[1], pvBookmark, 0xFFu, &pcbActual);
  if ( IndexInfo < 0 )
    goto LABEL_37;
  IndexInfo = JetRetrieveColumn(a1, v25[1], v25[5], &pvData, 4u, &v27, 0, 0);
  if ( IndexInfo < 0 )
    goto LABEL_37;
  IndexInfo = JetRetrieveColumn(a1, v25[1], v25[10], String2, 0x80u, &v27, 0, 0);
  if ( IndexInfo < 0 )
    goto LABEL_37;
  if ( (v27 & 0xFFFFFFFE) >= 0x82 )
LABEL_46:
    __report_rangecheckfailure();
  *(wchar_t *)((char *)String2 + (v27 & 0xFFFFFFFE)) = 0;
  IndexInfo = JetRetrieveColumn(a1, v25[1], v25[6], &v18, 4u, &v27, 0, 0);
  if ( IndexInfo < 0 || !v30 )
    goto LABEL_37;
  do
  {
    IndexInfo = JetRetrieveColumn(a1, tableid, columnid, v21, 4u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    if ( (v21[0] & 3) == 0 )
      goto LABEL_40;
    IndexInfo = JetRetrieveColumn(a1, tableid, v33, &v24, 4u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    if ( v24 != pvData )
      goto LABEL_40;
    IndexInfo = JetRetrieveColumn(a1, tableid, v36, String1, 0x80u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    if ( (v27 & 0xFFFFFFFE) >= 0x82 )
      goto LABEL_46;
    *(wchar_t *)((char *)String1 + (v27 & 0xFFFFFFFE)) = 0;
    if ( __wcsicmp(String1, String2) )
      goto LABEL_40;
    IndexInfo = JetRetrieveColumn(a1, tableid, v34, &v19, 4u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    IndexInfo = JetRetrieveColumn(a1, tableid, v35, &v23, 4u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    if ( v19 != v18 || v23 )
    {
LABEL_40:
      IndexInfo = JetMove(a1, tableid, 1, 0);
      continue;
    }
    IndexInfo = JetRetrieveColumn(a1, tableid, v31, v38, 0x80u, &v27, 0, 0);
    if ( IndexInfo < 0 )
      goto LABEL_37;
    if ( (v27 & 0xFFFFFFFE) >= 0x82 )
      goto LABEL_46;
    v26 = 1;
    v11 = 1;
    *(wchar_t *)((char *)v38 + (v27 & 0xFFFFFFFE)) = 0;
    if ( v24 <= 1 )
      goto LABEL_43;
    while ( 1 )
    {
      IndexInfo = JetMove(a1, tableid, 1, 0);
      if ( IndexInfo < 0 || (IndexInfo = JetMove(a1, v25[1], 1, 0), IndexInfo < 0) )
      {
        v26 = 1;
LABEL_43:
        WCSCPY((unsigned __int16 *)0x41, v16, v17);
        v15 = 0;
        if ( IndexInfo != -1603 )
          v15 = IndexInfo;
        IndexInfo = v15;
        goto LABEL_37;
      }
      JetRetrieveColumn(a1, tableid, v36, String1, 0x80u, &v27, 0, 0);
      if ( (v27 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_46;
      *(wchar_t *)((char *)String1 + (v27 & 0xFFFFFFFE)) = 0;
      JetRetrieveColumn(a1, v25[1], v25[10], v39, 0x80u, &v27, 0, 0);
      if ( (v27 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_46;
      *(wchar_t *)((char *)v39 + (v27 & 0xFFFFFFFE)) = 0;
      IndexInfo = JetRetrieveColumn(a1, tableid, v35, &v23, 4u, &v27, 0, 0);
      if ( IndexInfo < 0 )
      {
        v26 = 1;
        goto LABEL_37;
      }
      if ( __wcsicmp(String1, v39) || v23 )
        break;
      ++v11;
      v26 = 1;
      if ( v11 >= v24 )
        goto LABEL_43;
    }
    v26 = 0;
    for ( IndexInfo = JetGotoBookmark(a1, v25[1], pvBookmark, pcbActual); v11 < v24; IndexInfo = JetMove(
                                                                                                   a1,
                                                                                                   tableid,
                                                                                                   1,
                                                                                                   0) )
      ++v11;
    v9 = v26;
  }
  while ( IndexInfo >= 0 );
  v26 = v9;
  if ( IndexInfo == -1603 )
  {
    IndexInfo = 0;
    v26 = v9;
  }
LABEL_37:
  v12 = -2147467259;
  if ( IndexInfo >= 0 )
    v12 = 0;
  v13 = v26 != 1 ? v12 : 0;
  JetCloseTable(a1, tableid);
  JetGotoBookmark(a1, v25[1], pvBookmark, pcbActual);
  return v13;
}

```

## disassembly

```asm
0x1003f730  mov     edi, edi
0x1003f732  push    ebp
0x1003f733  mov     ebp, esp
0x1003f735  sub     esp, 37Ch
0x1003f73b  mov     eax, ___security_cookie
0x1003f740  xor     eax, ebp
0x1003f742  mov     [ebp+var_4], eax
0x1003f745  mov     ecx, [ebp+arg_C]
0x1003f748  mov     eax, [ebp+arg_4]
0x1003f74b  push    ebx
0x1003f74c  push    esi; unsigned int
0x1003f74d  push    edi; unsigned __int16 *
0x1003f74e  mov     ebx, edx
0x1003f750  mov     [ebp+var_37C], ecx
0x1003f756  mov     edi, 1
0x1003f75b  mov     [ebp+var_35C], eax
0x1003f761  mov     eax, [ebp+arg_8]
0x1003f764  xor     edx, edx
0x1003f766  push    edi
0x1003f767  push    3Ch ; '<'
0x1003f769  mov     [ecx], dx
0x1003f76c  lea     ecx, [ebp+var_350]
0x1003f772  push    ecx
0x1003f773  push    edx
0x1003f774  push    eax
0x1003f775  push    [ebp+this]
0x1003f778  mov     [ebp+pcbActual], 0
0x1003f782  push    ebx
0x1003f783  mov     [ebp+var_358], edi
0x1003f789  call    ds:__imp__JetGetIndexInfo@28; JetGetIndexInfo(x,x,x,x,x,x,x)
0x1003f78f  mov     esi, eax
0x1003f791  test    esi, esi
0x1003f793  js      loc_1003FC17
0x1003f799  lea     eax, [ebp+pcbActual]
0x1003f79f  push    eax; pcbActual
0x1003f7a0  push    0FFh; cbMax
0x1003f7a5  lea     eax, [ebp+pvBookmark]
0x1003f7ab  push    eax; pvBookmark
0x1003f7ac  mov     eax, [ebp+var_35C]
0x1003f7b2  push    dword ptr [eax+4]; tableid
0x1003f7b5  push    ebx; sesid
0x1003f7b6  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x1003f7bc  mov     esi, eax
0x1003f7be  test    esi, esi
0x1003f7c0  js      loc_1003FC17
0x1003f7c6  push    0; pretinfo
0x1003f7c8  push    0; grbit
0x1003f7ca  lea     eax, [ebp+var_354]
0x1003f7d0  push    eax; pcbActual
0x1003f7d1  push    4; cbData
0x1003f7d3  lea     eax, [ebp+pvData]
0x1003f7d9  push    eax; pvData
0x1003f7da  mov     eax, [ebp+var_35C]
0x1003f7e0  push    dword ptr [eax+14h]; columnid
0x1003f7e3  push    dword ptr [eax+4]; tableid
0x1003f7e6  push    ebx; sesid
0x1003f7e7  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f7ed  mov     esi, eax
0x1003f7ef  test    esi, esi
0x1003f7f1  js      loc_1003FC17
0x1003f7f7  push    0; pretinfo
0x1003f7f9  push    0; grbit
0x1003f7fb  lea     eax, [ebp+var_354]
0x1003f801  push    eax; pcbActual
0x1003f802  push    80h; cbData
0x1003f807  lea     eax, [ebp+String2]
0x1003f80d  push    eax; pvData
0x1003f80e  mov     eax, [ebp+var_35C]
0x1003f814  push    dword ptr [eax+28h]; columnid
0x1003f817  push    dword ptr [eax+4]; tableid
0x1003f81a  push    ebx; sesid
0x1003f81b  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f821  mov     esi, eax
0x1003f823  test    esi, esi
0x1003f825  js      loc_1003FC17
0x1003f82b  mov     eax, [ebp+var_354]
0x1003f831  and     eax, 0FFFFFFFEh
0x1003f834  cmp     eax, 82h
0x1003f839  jnb     loc_1003FCC2
0x1003f83f  xor     ecx, ecx
0x1003f841  push    ecx; pretinfo
0x1003f842  push    ecx; grbit
0x1003f843  mov     [ebp+eax+String2], cx
0x1003f84b  lea     eax, [ebp+var_354]
0x1003f851  push    eax; pcbActual
0x1003f852  push    4; cbData
0x1003f854  lea     eax, [ebp+var_378]
0x1003f85a  push    eax; pvData
0x1003f85b  mov     eax, [ebp+var_35C]
0x1003f861  push    dword ptr [eax+18h]; columnid
0x1003f864  push    dword ptr [eax+4]; tableid
0x1003f867  push    ebx; sesid
0x1003f868  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f86e  mov     esi, eax
0x1003f870  test    esi, esi
0x1003f872  js      loc_1003FC17
0x1003f878  cmp     [ebp+var_348], 0
0x1003f87f  jbe     loc_1003FC17
0x1003f885  push    0; pretinfo
0x1003f887  push    0; grbit
0x1003f889  lea     eax, [ebp+var_354]
0x1003f88f  push    eax; pcbActual
0x1003f890  push    4; cbData
0x1003f892  lea     eax, [ebp+var_36C]
0x1003f898  push    eax; pvData
0x1003f899  push    [ebp+columnid]; columnid
0x1003f89f  push    [ebp+tableid]; tableid
0x1003f8a5  push    ebx; sesid
0x1003f8a6  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f8ac  mov     esi, eax
0x1003f8ae  test    esi, esi
0x1003f8b0  js      loc_1003FC17
0x1003f8b6  test    [ebp+var_36C], 3
0x1003f8bd  jz      loc_1003FC6F
0x1003f8c3  push    0; pretinfo
0x1003f8c5  push    0; grbit
0x1003f8c7  lea     eax, [ebp+var_354]
0x1003f8cd  push    eax; pcbActual
0x1003f8ce  push    4; cbData
0x1003f8d0  lea     eax, [ebp+var_360]
0x1003f8d6  push    eax; pvData
0x1003f8d7  push    [ebp+var_330]; columnid
0x1003f8dd  push    [ebp+tableid]; tableid
0x1003f8e3  push    ebx; sesid
0x1003f8e4  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f8ea  mov     esi, eax
0x1003f8ec  test    esi, esi
0x1003f8ee  js      loc_1003FC17
0x1003f8f4  mov     eax, [ebp+var_360]
0x1003f8fa  cmp     eax, [ebp+pvData]
0x1003f900  jnz     loc_1003FC6F
0x1003f906  push    0; pretinfo
0x1003f908  push    0; grbit
0x1003f90a  lea     eax, [ebp+var_354]
0x1003f910  push    eax; pcbActual
0x1003f911  push    80h; cbData
0x1003f916  lea     eax, [ebp+String1]
0x1003f91c  push    eax; pvData
0x1003f91d  push    [ebp+var_318]; columnid
0x1003f923  push    [ebp+tableid]; tableid
0x1003f929  push    ebx; sesid
0x1003f92a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f930  mov     esi, eax
0x1003f932  test    esi, esi
0x1003f934  js      loc_1003FC17
0x1003f93a  mov     eax, [ebp+var_354]
0x1003f940  and     eax, 0FFFFFFFEh
0x1003f943  cmp     eax, 82h
0x1003f948  jnb     loc_1003FCC2
0x1003f94e  xor     ecx, ecx
0x1003f950  mov     [ebp+eax+String1], cx
0x1003f958  lea     eax, [ebp+String2]
0x1003f95e  push    eax; String2
0x1003f95f  lea     eax, [ebp+String1]
0x1003f965  push    eax; String1
0x1003f966  call    ds:__imp___wcsicmp
0x1003f96c  add     esp, 8
0x1003f96f  test    eax, eax
0x1003f971  jnz     loc_1003FC6F
0x1003f977  push    eax; pretinfo
0x1003f978  push    eax; grbit
0x1003f979  lea     eax, [ebp+var_354]
0x1003f97f  push    eax; pcbActual
0x1003f980  push    4; cbData
0x1003f982  lea     eax, [ebp+var_374]
0x1003f988  push    eax; pvData
0x1003f989  push    [ebp+var_32C]; columnid
0x1003f98f  push    [ebp+tableid]; tableid
0x1003f995  push    ebx; sesid
0x1003f996  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f99c  mov     esi, eax
0x1003f99e  test    esi, esi
0x1003f9a0  js      loc_1003FC17
0x1003f9a6  push    0; pretinfo
0x1003f9a8  push    0; grbit
0x1003f9aa  lea     eax, [ebp+var_354]
0x1003f9b0  push    eax; pcbActual
0x1003f9b1  push    4; cbData
0x1003f9b3  lea     eax, [ebp+var_364]
0x1003f9b9  push    eax; pvData
0x1003f9ba  push    [ebp+var_31C]; columnid
0x1003f9c0  push    [ebp+tableid]; tableid
0x1003f9c6  push    ebx; sesid
0x1003f9c7  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f9cd  mov     esi, eax
0x1003f9cf  test    esi, esi
0x1003f9d1  js      loc_1003FC17
0x1003f9d7  mov     eax, [ebp+var_374]
0x1003f9dd  cmp     eax, [ebp+var_378]
0x1003f9e3  jnz     loc_1003FC6F
0x1003f9e9  cmp     [ebp+var_364], 0
0x1003f9f0  jnz     loc_1003FC6F
0x1003f9f6  push    0; pretinfo
0x1003f9f8  push    0; grbit
0x1003f9fa  lea     eax, [ebp+var_354]
0x1003fa00  push    eax; pcbActual
0x1003fa01  push    80h; cbData
0x1003fa06  lea     eax, [ebp+var_214]
0x1003fa0c  push    eax; pvData
0x1003fa0d  push    [ebp+var_344]; columnid
0x1003fa13  push    [ebp+tableid]; tableid
0x1003fa19  push    ebx; sesid
0x1003fa1a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003fa20  mov     esi, eax
0x1003fa22  test    esi, esi
0x1003fa24  js      loc_1003FC17
0x1003fa2a  mov     eax, [ebp+var_354]
0x1003fa30  and     eax, 0FFFFFFFEh
0x1003fa33  cmp     eax, 82h
0x1003fa38  jnb     loc_1003FCC2
0x1003fa3e  xor     ecx, ecx
0x1003fa40  mov     [ebp+var_358], 1
0x1003fa4a  mov     edi, 1
0x1003fa4f  mov     [ebp+eax+var_214], cx
0x1003fa57  cmp     [ebp+var_360], edi
0x1003fa5d  jle     loc_1003FC9D
0x1003fa63  push    0; grbit
0x1003fa65  push    1; cRow
0x1003fa67  push    [ebp+tableid]; tableid
0x1003fa6d  push    ebx; sesid
0x1003fa6e  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003fa74  mov     esi, eax
0x1003fa76  test    esi, esi
0x1003fa78  js      loc_1003FC93
0x1003fa7e  mov     eax, [ebp+var_35C]
0x1003fa84  push    0; grbit
0x1003fa86  push    1; cRow
0x1003fa88  push    dword ptr [eax+4]; tableid
0x1003fa8b  push    ebx; sesid
0x1003fa8c  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003fa92  mov     esi, eax
0x1003fa94  test    esi, esi
0x1003fa96  js      loc_1003FC93
0x1003fa9c  push    0; pretinfo
0x1003fa9e  push    0; grbit
0x1003faa0  lea     eax, [ebp+var_354]
0x1003faa6  push    eax; pcbActual
0x1003faa7  push    80h; cbData
0x1003faac  lea     eax, [ebp+String1]
0x1003fab2  push    eax; pvData
0x1003fab3  push    [ebp+var_318]; columnid
0x1003fab9  push    [ebp+tableid]; tableid
0x1003fabf  push    ebx; sesid
0x1003fac0  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003fac6  mov     eax, [ebp+var_354]
0x1003facc  and     eax, 0FFFFFFFEh
0x1003facf  cmp     eax, 82h
0x1003fad4  jnb     loc_1003FCC2
0x1003fada  xor     ecx, ecx
0x1003fadc  push    ecx; pretinfo
0x1003fadd  push    ecx; grbit
0x1003fade  mov     [ebp+eax+String1], cx
0x1003fae6  lea     eax, [ebp+var_354]
0x1003faec  push    eax; pcbActual
0x1003faed  push    80h; cbData
0x1003faf2  lea     eax, [ebp+var_190]
0x1003faf8  push    eax; pvData
0x1003faf9  mov     eax, [ebp+var_35C]
0x1003faff  push    dword ptr [eax+28h]; columnid
0x1003fb02  push    dword ptr [eax+4]; tableid
0x1003fb05  push    ebx; sesid
0x1003fb06  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003fb0c  mov     eax, [ebp+var_354]
0x1003fb12  and     eax, 0FFFFFFFEh
0x1003fb15  cmp     eax, 82h
0x1003fb1a  jnb     loc_1003FCC2
0x1003fb20  xor     ecx, ecx
0x1003fb22  push    ecx; pretinfo
0x1003fb23  push    ecx; grbit
0x1003fb24  mov     [ebp+eax+var_190], cx
0x1003fb2c  lea     eax, [ebp+var_354]
0x1003fb32  push    eax; pcbActual
0x1003fb33  push    4; cbData
0x1003fb35  lea     eax, [ebp+var_364]
0x1003fb3b  push    eax; pvData
0x1003fb3c  push    [ebp+var_31C]; columnid
0x1003fb42  push    [ebp+tableid]; tableid
0x1003fb48  push    ebx; sesid
0x1003fb49  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003fb4f  mov     esi, eax
0x1003fb51  test    esi, esi
0x1003fb53  js      loc_1003FC87
0x1003fb59  lea     eax, [ebp+var_190]
0x1003fb5f  push    eax; String2
0x1003fb60  lea     eax, [ebp+String1]
0x1003fb66  push    eax; String1
0x1003fb67  call    ds:__imp___wcsicmp
0x1003fb6d  add     esp, 8
0x1003fb70  test    eax, eax
0x1003fb72  jnz     short loc_1003FB98
0x1003fb74  cmp     [ebp+var_364], eax
0x1003fb7a  jnz     short loc_1003FB98
0x1003fb7c  inc     edi
0x1003fb7d  mov     [ebp+var_358], 1
0x1003fb87  cmp     edi, [ebp+var_360]
0x1003fb8d  jl      loc_1003FA63
0x1003fb93  jmp     loc_1003FC9D
0x1003fb98  push    [ebp+pcbActual]; cbBookmark
0x1003fb9e  lea     eax, [ebp+pvBookmark]
0x1003fba4  mov     [ebp+var_358], 0
  ... truncated ...
```
