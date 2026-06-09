# CSRSTypes::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x10037c60`
- end: `0x100382ef`
- name: `?FInit@CSRSTypes@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1679`
- prototype: `int __stdcall(CSRSTypes *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x10013100`
- `0x1001c6d0`
- `0x1001fc50`
- `0x10028340`
- `0x10035e60`
- `0x10037c60`
- `0x1004ce5d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10037efe`
- `msvcrt!_wcsicmp` at `0x10037efe`
- `msjet40!__imp__JetCloseTable@8` at `0x100382de`
- `msjet40!__imp__JetCloseTable@8` at `0x100382de`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10037e43`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10037e43`
- `msjet40!__imp__JetSetColumn@28` at `0x10037e84`
- `msjet40!__imp__JetSetColumn@28` at `0x10037ea4`
- `msjet40!__imp__JetSetColumn@28` at `0x10037f26`
- `msjet40!__imp__JetSetColumn@28` at `0x10037f6f`
- `msjet40!__imp__JetSetColumn@28` at `0x10037fb0`
- `msjet40!__imp__JetSetColumn@28` at `0x10037ff1`
- `msjet40!__imp__JetSetColumn@28` at `0x1003801d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003803e`
- `msjet40!__imp__JetSetColumn@28` at `0x10038064`
- `msjet40!__imp__JetSetColumn@28` at `0x1003808a`
- `msjet40!__imp__JetSetColumn@28` at `0x100380b0`
- `msjet40!__imp__JetSetColumn@28` at `0x100380d6`
- `msjet40!__imp__JetSetColumn@28` at `0x10038110`
- `msjet40!__imp__JetSetColumn@28` at `0x10038136`
- `msjet40!__imp__JetSetColumn@28` at `0x1003815c`
- `msjet40!__imp__JetSetColumn@28` at `0x1003818b`
- `msjet40!__imp__JetSetColumn@28` at `0x100381ae`
- `msjet40!__imp__JetSetColumn@28` at `0x10037e84`
- `msjet40!__imp__JetSetColumn@28` at `0x10037ea4`
- `msjet40!__imp__JetSetColumn@28` at `0x10037f26`
- `msjet40!__imp__JetSetColumn@28` at `0x10037f6f`
- `msjet40!__imp__JetSetColumn@28` at `0x10037fb0`
- `msjet40!__imp__JetSetColumn@28` at `0x10037ff1`
- `msjet40!__imp__JetSetColumn@28` at `0x1003801d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003803e`
- `msjet40!__imp__JetSetColumn@28` at `0x10038064`
- `msjet40!__imp__JetSetColumn@28` at `0x1003808a`
- `msjet40!__imp__JetSetColumn@28` at `0x100380b0`
- `msjet40!__imp__JetSetColumn@28` at `0x100380d6`
- `msjet40!__imp__JetSetColumn@28` at `0x10038110`
- `msjet40!__imp__JetSetColumn@28` at `0x10038136`
- `msjet40!__imp__JetSetColumn@28` at `0x1003815c`
- `msjet40!__imp__JetSetColumn@28` at `0x1003818b`
- `msjet40!__imp__JetSetColumn@28` at `0x100381ae`
- `msjet40!__imp__JetUpdate@20` at `0x100381c1`
- `msjet40!__imp__JetUpdate@20` at `0x100381c1`

## pseudocode

```c
int __userpurge CSRSTypes::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSTypes *this,
        struct CDBSession *a4,
        struct CSettableProperties *a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  int v7; // esi
  unsigned int v8; // ecx
  JET_SESID v9; // edi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  JET_COLUMNID *v14; // ebx
  unsigned int v15; // ecx
  unsigned int v16; // esi
  __int16 v17; // cx
  int v18; // eax
  bool v19; // zf
  wchar_t *v20; // edx
  wchar_t *v21; // ecx
  JET_ERR v23; // eax
  __int16 v24; // cx
  int v25; // eax
  unsigned __int8 v26; // al
  const void *v27; // edx
  unsigned int v28; // ecx
  _WORD *v29; // ecx
  const void *v31; // edx
  unsigned int v32; // ecx
  _WORD *v33; // ecx
  const void *v35; // edx
  unsigned int v36; // ecx
  _WORD *v37; // ecx
  ColumnData *v39; // eax
  int v40; // ecx
  int v41; // esi
  int v44; // [esp+10h] [ebp-38h] BYREF
  int v45; // [esp+14h] [ebp-34h]
  unsigned int v46; // [esp+18h] [ebp-30h] BYREF
  int v47; // [esp+1Ch] [ebp-2Ch]
  _DWORD *v48; // [esp+20h] [ebp-28h]
  int v49; // [esp+24h] [ebp-24h]
  int v50; // [esp+28h] [ebp-20h]
  int v51; // [esp+2Ch] [ebp-1Ch]
  int pvData; // [esp+30h] [ebp-18h] BYREF
  JET_COLUMNID *v53; // [esp+34h] [ebp-14h]
  int v54; // [esp+38h] [ebp-10h] BYREF
  int v55; // [esp+3Ch] [ebp-Ch] BYREF
  JET_TABLEID tableid; // [esp+40h] [ebp-8h] BYREF
  __int16 v57; // [esp+44h] [ebp-4h] BYREF

  v7 = 0;
  v8 = 0;
  v48 = a1;
  v55 = 0;
  tableid = 0;
  v47 = 1;
  v50 = 0;
  v51 = 0;
  v9 = a1[4];
  if ( this )
  {
    do
    {
      v10 = *((unsigned __int16 *)a4 + 8 * v8);
      if ( (_WORD)v10 && v10 != 1 )
        ++v7;
      ++v8;
    }
    while ( v8 < (unsigned int)this );
    v11 = *(unsigned __int16 *)a4;
    v49 = v7;
    if ( !(_WORD)v11 || (v50 = 1, v11 == 1) )
      v50 = 0;
    if ( (unsigned int)this > 1 )
    {
      v12 = *((unsigned __int16 *)a4 + 8);
      if ( !(_WORD)v12 || (v51 = 1, v12 == 1) )
        v51 = 0;
      if ( (unsigned int)this > 2 )
        goto LABEL_22;
    }
  }
  else
  {
    v49 = 0;
  }
  if ( this && !a4 || v50 && *(_WORD *)a4 != 18 || v51 && *((_WORD *)a4 + 8) != 11 )
  {
LABEL_22:
    v13 = -2147024809;
LABEL_86:
    JetCloseTable(v9, tableid);
    return v13;
  }
  v14 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          84);
  v53 = v14;
  if ( !v14 )
  {
    v13 = -2147024882;
    goto LABEL_86;
  }
  pvData = SRSCreateTempTable(2, v48, &tableid, v14, 0);
  if ( !pvData )
  {
    if ( this && *(_WORD *)a4 == 1 || (unsigned int)this >= 2 && *((_WORD *)a4 + 8) == 1 )
      v47 = 0;
    JoltProperties::GetIntValue(*(JoltProperties **)(v48[21] + 164), 0x103u, &v46);
    v15 = 15;
    v45 = 15;
    switch ( v46 )
    {
      case 1u:
      case 2u:
      case 3u:
      case 4u:
        v15 = 13;
        v45 = 13;
        break;
      default:
        break;
    }
    v16 = 0;
    if ( v47 == 1 )
    {
      while ( v16 < v15 )
      {
        if ( v51
          && ((v17 = *((_WORD *)a4 + 12), v18 = 0, !dword_10003470[13 * v16]) ? (v19 = v17 == 0) : (v19 = v17 == -1),
              LOBYTE(v18) = v19,
              !v18)
          || v49 && v50 && *((unsigned __int16 *)a4 + 4) != word_10003454[26 * v16] )
        {
          v14 = v53;
        }
        else
        {
          v55 = JetPrepareUpdate(v9, tableid, 0);
          if ( v55 )
          {
            v14 = v53;
            pvData = -2147467259;
            goto LABEL_83;
          }
          v20 = (&off_10003450)[13 * v16];
          v21 = v20;
          v47 = (int)(v20 + 1);
          while ( *v21++ )
            ;
          v55 = JetSetColumn(v9, tableid, *v53, v20, 2 * (((int)v21 - v47) >> 1), 0, 0);
          v23 = JetSetColumn(v9, tableid, v53[1], &word_10003454[26 * v16], 2u, 0, 0);
          v24 = word_10003454[26 * v16];
          v55 = v23;
          v25 = 0;
          while ( word_10004700[2 * v25] != v24 )
          {
            if ( (unsigned int)++v25 >= 8 )
            {
              v26 = -1;
              goto LABEL_51;
            }
          }
          v26 = byte_10004702[4 * v25];
LABEL_51:
          pvData = v26;
          if ( v26 == 255 )
          {
            pvData = dword_10003464[13 * v16];
            if ( v46 != 5 && !__wcsicmp(L"VarBinary", (&off_10003450)[13 * v16]) )
              pvData = 255;
          }
          v14 = v53;
          v55 = JetSetColumn(v9, tableid, v53[2], &pvData, 4u, 0, 0);
          v27 = (const void *)dword_10003474[13 * v16];
          if ( v27 )
          {
            v29 = (_WORD *)dword_10003474[13 * v16];
            v47 = (int)v27 + 2;
            while ( *v29++ )
              ;
            v28 = 2 * (((int)v29 - v47) >> 1);
          }
          else
          {
            v28 = 0;
          }
          v55 = JetSetColumn(v9, tableid, v14[3], v27, v28, 0, 0);
          v31 = (const void *)dword_10003478[13 * v16];
          if ( v31 )
          {
            v33 = (_WORD *)dword_10003478[13 * v16];
            v47 = (int)v31 + 2;
            while ( *v33++ )
              ;
            v32 = 2 * (((int)v33 - v47) >> 1);
          }
          else
          {
            v32 = 0;
          }
          v55 = JetSetColumn(v9, tableid, v14[4], v31, v32, 0, 0);
          v35 = (const void *)dword_1000347C[13 * v16];
          if ( v35 )
          {
            v37 = (_WORD *)dword_1000347C[13 * v16];
            v47 = (int)v35 + 2;
            while ( *v37++ )
              ;
            v36 = 2 * (((int)v37 - v47) >> 1);
          }
          else
          {
            v36 = 0;
          }
          v55 = JetSetColumn(v9, tableid, v14[5], v35, v36, 0, 0);
          v54 = word_10003456[26 * v16] != 0;
          v55 = JetSetColumn(v9, tableid, v14[6], &v54, 4u, 0, 0);
          v54 = 0;
          v55 = JetSetColumn(v9, tableid, v14[7], &v54, 4u, 0, 0);
          v44 = dword_10003458[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[8], &v44, 4u, 0, 0);
          v54 = dword_1000345C[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[9], &v54, 4u, 0, 0);
          v54 = dword_10003460[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[10], &v54, 4u, 0, 0);
          v54 = dword_1000346C[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[11], &v54, 4u, 0, 0);
          if ( (unsigned __int16)word_10003480[26 * v16] <= 1u )
            v55 = JetSetColumn(v9, tableid, v14[20], &word_10003480[26 * v16], 2u, 0, 0);
          v54 = dword_10003468[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[18], &v54, 4u, 0, 0);
          v54 = dword_10003470[13 * v16];
          v55 = JetSetColumn(v9, tableid, v14[19], &v54, 4u, 0, 0);
          if ( word_10003454[26 * v16] == 131 )
          {
            v57 = 0;
            v55 = JetSetColumn(v9, tableid, v14[13], &v57, 2u, 0, 0);
            v57 = 28;
            v55 = JetSetColumn(v9, tableid, v14[14], &v57, 2u, 0, 0);
          }
          v55 = JetUpdate(v9, tableid, 0, 0, 0);
          if ( v55 )
          {
            pvData = -2147467259;
            goto LABEL_83;
          }
        }
        v15 = v45;
        ++v16;
      }
    }
    v39 = (ColumnData *)operator new(0x20u);
    v41 = (int)v39;
    v45 = (int)v39;
    if ( v39 )
    {
      *((_DWORD *)v39 + 1) = 0;
      *((_DWORD *)v39 + 2) = 0;
      *((_DWORD *)v39 + 3) = 0;
      *(_DWORD *)v39 = &ColumnDataWithFakeNamesAndDBTYPES::`vftable';
      *((_DWORD *)v39 + 4) = 0;
      *((_DWORD *)v39 + 5) = 0;
      *((_DWORD *)v39 + 6) = 0;
      *((_DWORD *)v39 + 7) = 0;
      *((_DWORD *)v39 + 4) = dword_10008078;
      *((_DWORD *)v39 + 5) = &SRSTypesDefNames;
      *((_DWORD *)v39 + 7) = 0;
      pvData = ColumnData::FInit(v39, v9, v48[5], tableid, &v55, 0, v40);
      if ( pvData >= 0 )
      {
        *(_DWORD *)(v41 + 4) = 21;
        pvData = CRowset::FInit(a2, (int)v48, 0, 0, 0, tableid, a5, 1, 0, 0, v41, 1, 0, 0, &GUID_NULL);
      }
    }
    else
    {
      pvData = -2147024882;
    }
  }
LABEL_83:
  if ( Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v14);
  v13 = pvData;
  if ( pvData < 0 )
    goto LABEL_86;
  return v13;
}

```

## disassembly

```asm
0x10037c60  mov     edi, edi
0x10037c62  push    ebp
0x10037c63  mov     ebp, esp
0x10037c65  sub     esp, 3Ch
0x10037c68  push    ebx
0x10037c69  mov     ebx, [ebp+arg_4]
0x10037c6c  mov     eax, edx
0x10037c6e  mov     edx, [ebp+this]
0x10037c71  push    esi
0x10037c72  mov     [ebp+var_3C], ecx
0x10037c75  xor     esi, esi
0x10037c77  xor     ecx, ecx
0x10037c79  mov     [ebp+var_28], eax
0x10037c7c  mov     [ebp+var_C], 0
0x10037c83  mov     [ebp+tableid], 0
0x10037c8a  mov     [ebp+var_2C], 1
0x10037c91  mov     [ebp+var_20], 0
0x10037c98  mov     [ebp+var_1C], 0
0x10037c9f  push    edi
0x10037ca0  mov     edi, [eax+10h]
0x10037ca3  test    edx, edx
0x10037ca5  jz      short loc_10037D05
0x10037ca7  mov     eax, ecx
0x10037ca9  add     eax, eax
0x10037cab  movzx   eax, word ptr [ebx+eax*8]
0x10037caf  test    ax, ax
0x10037cb2  jz      short loc_10037CBA
0x10037cb4  cmp     eax, 1
0x10037cb7  jz      short loc_10037CBA
0x10037cb9  inc     esi
0x10037cba  inc     ecx
0x10037cbb  cmp     ecx, edx
0x10037cbd  jb      short loc_10037CA7
0x10037cbf  movzx   eax, word ptr [ebx]
0x10037cc2  mov     [ebp+var_24], esi
0x10037cc5  test    ax, ax
0x10037cc8  jz      short loc_10037CD6
0x10037cca  mov     [ebp+var_20], 1
0x10037cd1  cmp     eax, 1
0x10037cd4  jnz     short loc_10037CDD
0x10037cd6  mov     [ebp+var_20], 0
0x10037cdd  cmp     edx, 1
0x10037ce0  jbe     short loc_10037D08
0x10037ce2  movzx   eax, word ptr [ebx+10h]
0x10037ce6  test    ax, ax
0x10037ce9  jz      short loc_10037CF7
0x10037ceb  mov     [ebp+var_1C], 1
0x10037cf2  cmp     eax, 1
0x10037cf5  jnz     short loc_10037CFE
0x10037cf7  mov     [ebp+var_1C], 0
0x10037cfe  cmp     edx, 2
0x10037d01  ja      short loc_10037D29
0x10037d03  jmp     short loc_10037D08
0x10037d05  mov     [ebp+var_24], ecx
0x10037d08  test    edx, edx
0x10037d0a  jz      short loc_10037D10
0x10037d0c  test    ebx, ebx
0x10037d0e  jz      short loc_10037D29
0x10037d10  cmp     [ebp+var_20], 0
0x10037d14  jz      short loc_10037D1C
0x10037d16  cmp     word ptr [ebx], 12h
0x10037d1a  jnz     short loc_10037D29
0x10037d1c  cmp     [ebp+var_1C], 0
0x10037d20  jz      short loc_10037D33
0x10037d22  cmp     word ptr [ebx+10h], 0Bh
0x10037d27  jz      short loc_10037D33
0x10037d29  mov     ebx, 80070057h
0x10037d2e  jmp     loc_100382DA
0x10037d33  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10037d39  push    54h ; 'T'
0x10037d3b  push    ecx
0x10037d3c  mov     eax, [ecx]
0x10037d3e  mov     esi, [eax+0Ch]
0x10037d41  mov     ecx, esi
0x10037d43  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10037d49  call    esi
0x10037d4b  mov     ebx, eax
0x10037d4d  mov     [ebp+var_14], ebx
0x10037d50  test    ebx, ebx
0x10037d52  jnz     short loc_10037D5E
0x10037d54  mov     ebx, 8007000Eh
0x10037d59  jmp     loc_100382DA
0x10037d5e  mov     esi, [ebp+var_28]
0x10037d61  lea     eax, [ebp+tableid]
0x10037d64  push    0
0x10037d66  push    ebx
0x10037d67  push    eax
0x10037d68  mov     edx, esi
0x10037d6a  mov     ecx, 2
0x10037d6f  call    SRSCreateTempTable
0x10037d74  mov     ecx, eax
0x10037d76  mov     [ebp+pvData], ecx
0x10037d79  test    ecx, ecx
0x10037d7b  jnz     loc_100382B9
0x10037d81  mov     ecx, [ebp+arg_4]
0x10037d84  lea     edx, [eax+1]
0x10037d87  mov     eax, [ebp+this]
0x10037d8a  cmp     eax, edx
0x10037d8c  jb      short loc_10037D93
0x10037d8e  cmp     dx, [ecx]
0x10037d91  jz      short loc_10037D9E
0x10037d93  cmp     eax, 2
0x10037d96  jb      short loc_10037DA5
0x10037d98  cmp     dx, [ecx+10h]
0x10037d9c  jnz     short loc_10037DA5
0x10037d9e  mov     [ebp+var_2C], 0
0x10037da5  mov     ecx, [esi+54h]
0x10037da8  lea     eax, [ebp+var_30]
0x10037dab  push    eax; unsigned int *
0x10037dac  push    103h; unsigned int
0x10037db1  mov     ecx, [ecx+0A4h]; this
0x10037db7  call    ?GetIntValue@JoltProperties@@QBEJKAAK@Z; JoltProperties::GetIntValue(ulong,ulong &)
0x10037dbc  mov     eax, [ebp+var_30]
0x10037dbf  mov     ecx, 0Fh
0x10037dc4  dec     eax; switch 4 cases
0x10037dc5  mov     [ebp+var_34], ecx
0x10037dc8  cmp     eax, 3
0x10037dcb  ja      short def_10037DCD; jumptable 10037DCD default case
0x10037dcd  jmp     ds:jpt_10037DCD[eax*4]; switch jump
0x10037dd4  mov     ecx, 0Dh; jumptable 10037DCD cases 1-4
0x10037dd9  mov     [ebp+var_34], ecx
0x10037ddc  xor     esi, esi; jumptable 10037DCD default case
0x10037dde  cmp     [ebp+var_2C], 1
0x10037de2  jnz     loc_100381F5
0x10037de8  cmp     esi, ecx
0x10037dea  jnb     loc_100381F5
0x10037df0  mov     edx, [ebp+arg_4]
0x10037df3  imul    ebx, esi, 34h ; '4'
0x10037df6  cmp     [ebp+var_1C], 0
0x10037dfa  jz      short loc_10037E1E
0x10037dfc  movzx   ecx, word ptr [edx+18h]
0x10037e00  xor     eax, eax
0x10037e02  cmp     ds:dword_10003470[ebx], eax
0x10037e08  jz      short loc_10037E10
0x10037e0a  cmp     cx, 0FFFFh
0x10037e0e  jmp     short loc_10037E13
0x10037e10  test    cx, cx
0x10037e13  setz    al
0x10037e16  test    eax, eax
0x10037e18  jz      loc_100381DA
0x10037e1e  cmp     [ebp+var_24], 0
0x10037e22  jz      short loc_10037E3D
0x10037e24  cmp     [ebp+var_20], 0
0x10037e28  jz      short loc_10037E3D
0x10037e2a  movsx   ecx, ds:word_10003454[ebx]
0x10037e31  movzx   eax, word ptr [edx+8]
0x10037e35  cmp     eax, ecx
0x10037e37  jnz     loc_100381DA
0x10037e3d  push    0; prep
0x10037e3f  push    [ebp+tableid]; tableid
0x10037e42  push    edi; sesid
0x10037e43  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10037e49  mov     [ebp+var_C], eax
0x10037e4c  test    eax, eax
0x10037e4e  jnz     loc_100381E6
0x10037e54  mov     edx, ds:off_10003450[ebx]; "Bit"
0x10037e5a  mov     ecx, edx
0x10037e5c  lea     eax, [ecx+2]
0x10037e5f  mov     [ebp+var_2C], eax
0x10037e62  mov     ax, [ecx]
0x10037e65  add     ecx, 2
0x10037e68  test    ax, ax
0x10037e6b  jnz     short loc_10037E62
0x10037e6d  sub     ecx, [ebp+var_2C]
0x10037e70  push    0; psetinfo
0x10037e72  sar     ecx, 1
0x10037e74  push    0; grbit
0x10037e76  lea     eax, [ecx+ecx]
0x10037e79  push    eax; cbData
0x10037e7a  mov     eax, [ebp+var_14]
0x10037e7d  push    edx; pvData
0x10037e7e  push    dword ptr [eax]; columnid
0x10037e80  push    [ebp+tableid]; tableid
0x10037e83  push    edi; sesid
0x10037e84  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10037e8a  push    0; psetinfo
0x10037e8c  push    0; grbit
0x10037e8e  mov     [ebp+var_C], eax
0x10037e91  lea     eax, word_10003454[ebx]
0x10037e97  push    2; cbData
0x10037e99  push    eax; pvData
0x10037e9a  mov     eax, [ebp+var_14]
0x10037e9d  push    dword ptr [eax+4]; columnid
0x10037ea0  push    [ebp+tableid]; tableid
0x10037ea3  push    edi; sesid
0x10037ea4  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10037eaa  movzx   ecx, ds:word_10003454[ebx]
0x10037eb1  mov     [ebp+var_C], eax
0x10037eb4  xor     eax, eax
0x10037eb6  cmp     ds:word_10004700[eax*4], cx
0x10037ebe  jz      short loc_10037ECA
0x10037ec0  inc     eax
0x10037ec1  cmp     eax, 8
0x10037ec4  jb      short loc_10037EB6
0x10037ec6  or      al, 0FFh
0x10037ec8  jmp     short loc_10037ED1
0x10037eca  mov     al, ds:byte_10004702[eax*4]
0x10037ed1  movzx   eax, al
0x10037ed4  mov     [ebp+pvData], eax
0x10037ed7  cmp     eax, 0FFh
0x10037edc  jnz     short loc_10037F12
0x10037ede  imul    eax, esi, 34h ; '4'
0x10037ee1  cmp     [ebp+var_30], 5
0x10037ee5  mov     eax, ds:dword_10003464[eax]
0x10037eeb  mov     [ebp+pvData], eax
0x10037eee  jz      short loc_10037F12
0x10037ef0  imul    eax, esi, 34h ; '4'
0x10037ef3  push    ds:off_10003450[eax]; String2
0x10037ef9  push    offset aVarbinary; "VarBinary"
0x10037efe  call    ds:__imp___wcsicmp
0x10037f04  add     esp, 8
0x10037f07  test    eax, eax
0x10037f09  jnz     short loc_10037F12
0x10037f0b  mov     [ebp+pvData], 0FFh
0x10037f12  mov     ebx, [ebp+var_14]
0x10037f15  lea     eax, [ebp+pvData]
0x10037f18  push    0; psetinfo
0x10037f1a  push    0; grbit
0x10037f1c  push    4; cbData
0x10037f1e  push    eax; pvData
0x10037f1f  push    dword ptr [ebx+8]; columnid
0x10037f22  push    [ebp+tableid]; tableid
0x10037f25  push    edi; sesid
0x10037f26  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10037f2c  mov     [ebp+var_C], eax
0x10037f2f  imul    eax, esi, 34h ; '4'
0x10037f32  mov     edx, ds:dword_10003474[eax]
0x10037f38  test    edx, edx
0x10037f3a  jnz     short loc_10037F40
0x10037f3c  xor     ecx, ecx
0x10037f3e  jmp     short loc_10037F62
0x10037f40  mov     ecx, edx
0x10037f42  lea     eax, [ecx+2]
0x10037f45  mov     [ebp+var_2C], eax
0x10037f48  nop     dword ptr [eax+eax+00000000h]
0x10037f50  mov     ax, [ecx]
0x10037f53  add     ecx, 2
0x10037f56  test    ax, ax
0x10037f59  jnz     short loc_10037F50
0x10037f5b  sub     ecx, [ebp+var_2C]
0x10037f5e  sar     ecx, 1
0x10037f60  add     ecx, ecx
0x10037f62  push    0; psetinfo
0x10037f64  push    0; grbit
0x10037f66  push    ecx; cbData
0x10037f67  push    edx; pvData
0x10037f68  push    dword ptr [ebx+0Ch]; columnid
0x10037f6b  push    [ebp+tableid]; tableid
0x10037f6e  push    edi; sesid
0x10037f6f  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10037f75  mov     [ebp+var_C], eax
0x10037f78  imul    eax, esi, 34h ; '4'
0x10037f7b  mov     edx, ds:dword_10003478[eax]
0x10037f81  test    edx, edx
0x10037f83  jnz     short loc_10037F89
0x10037f85  xor     ecx, ecx
0x10037f87  jmp     short loc_10037FA3
0x10037f89  mov     ecx, edx
0x10037f8b  lea     eax, [ecx+2]
0x10037f8e  mov     [ebp+var_2C], eax
0x10037f91  mov     ax, [ecx]
0x10037f94  add     ecx, 2
0x10037f97  test    ax, ax
0x10037f9a  jnz     short loc_10037F91
0x10037f9c  sub     ecx, [ebp+var_2C]
0x10037f9f  sar     ecx, 1
0x10037fa1  add     ecx, ecx
0x10037fa3  push    0; psetinfo
0x10037fa5  push    0; grbit
0x10037fa7  push    ecx; cbData
0x10037fa8  push    edx; pvData
0x10037fa9  push    dword ptr [ebx+10h]; columnid
0x10037fac  push    [ebp+tableid]; tableid
0x10037faf  push    edi; sesid
0x10037fb0  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10037fb6  mov     [ebp+var_C], eax
0x10037fb9  imul    eax, esi, 34h ; '4'
0x10037fbc  mov     edx, ds:dword_1000347C[eax]
0x10037fc2  test    edx, edx
0x10037fc4  jnz     short loc_10037FCA
0x10037fc6  xor     ecx, ecx
0x10037fc8  jmp     short loc_10037FE4
0x10037fca  mov     ecx, edx
0x10037fcc  lea     eax, [ecx+2]
0x10037fcf  mov     [ebp+var_2C], eax
0x10037fd2  mov     ax, [ecx]
0x10037fd5  add     ecx, 2
0x10037fd8  test    ax, ax
0x10037fdb  jnz     short loc_10037FD2
0x10037fdd  sub     ecx, [ebp+var_2C]
0x10037fe0  sar     ecx, 1
0x10037fe2  add     ecx, ecx
0x10037fe4  push    0; psetinfo
0x10037fe6  push    0; grbit
0x10037fe8  push    ecx; cbData
0x10037fe9  push    edx; pvData
0x10037fea  push    dword ptr [ebx+14h]; columnid
0x10037fed  push    [ebp+tableid]; tableid
0x10037ff0  push    edi; sesid
0x10037ff1  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
  ... truncated ...
```
