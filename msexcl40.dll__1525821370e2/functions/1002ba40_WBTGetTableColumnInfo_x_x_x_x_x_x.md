# WBTGetTableColumnInfo(x,x,x,x,x,x)

- ea: `0x1002ba40`
- end: `0x1002bed9`
- name: `_WBTGetTableColumnInfo@24`
- size: `1177`
- prototype: `int __stdcall(int, int, wchar_t *String2, void *, size_t Size, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task`

## callers

- `0x1002bee0`

## callees

- `0x10006400`
- `0x1001a630`
- `0x1001cf30`
- `0x1001e4b0`
- `0x100243dc`
- `0x100246ef`
- `0x1002580a`
- `0x1002a7de`
- `0x1002a869`
- `0x1002acaf`
- `0x1002aea1`
- `0x1002aecf`
- `0x1002af20`
- `0x1002ba40`
- `0x10035510`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002bc16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002bc16`

## pseudocode

```c
int __stdcall WBTGetTableColumnInfo(int a1, int a2, wchar_t *String2, void *a4, size_t Size, unsigned int a6)
{
  int v6; // eax
  int v7; // ebx
  int v9; // edi
  int v10; // ecx
  int *v11; // ecx
  int v12; // esi
  _DWORD *v13; // edx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // ebx
  int v17; // eax
  int v18; // esi
  DWORD CurrentProcessId; // eax
  int v20; // eax
  int v21; // ecx
  size_t v22; // esi
  unsigned int v23; // edi
  size_t v24; // eax
  size_t v25; // eax
  _DWORD *v26; // eax
  bool v27; // zf
  int v28; // eax
  size_t v29; // eax
  size_t v30; // eax
  int v31; // eax
  size_t v32; // eax
  size_t v33; // eax
  size_t v34; // eax
  size_t v35; // eax
  UINT CodePage; // [esp+10h] [ebp-8A8h] BYREF
  int v37; // [esp+14h] [ebp-8A4h]
  int *v38; // [esp+18h] [ebp-8A0h]
  void *v39; // [esp+1Ch] [ebp-89Ch]
  int v40; // [esp+20h] [ebp-898h]
  int v41; // [esp+24h] [ebp-894h]
  int *v42; // [esp+28h] [ebp-890h]
  int v43; // [esp+2Ch] [ebp-88Ch]
  int v44; // [esp+30h] [ebp-888h] BYREF
  int v45; // [esp+34h] [ebp-884h]
  int v46; // [esp+38h] [ebp-880h]
  int v47; // [esp+3Ch] [ebp-87Ch]
  _DWORD v48[6]; // [esp+40h] [ebp-878h] BYREF
  _DWORD Src[14]; // [esp+58h] [ebp-860h] BYREF
  _DWORD v50[2]; // [esp+90h] [ebp-828h] BYREF
  _WORD v51[256]; // [esp+98h] [ebp-820h] BYREF
  _DWORD v52[6]; // [esp+298h] [ebp-620h] BYREF
  WCHAR v53[256]; // [esp+2B0h] [ebp-608h] BYREF
  wchar_t String1[258]; // [esp+6B0h] [ebp-208h] BYREF

  v39 = a4;
  v43 = a1;
  if ( a6 > 2 )
  {
    if ( a6 == 3 )
      return -1001;
    if ( a6 - 4 > 1 )
      return -1003;
  }
  v6 = ISAMDBFindCursor();
  v7 = v6;
  if ( !v6 )
    return -1310;
  v37 = *(_DWORD *)(v6 + 4);
  v47 = *(_DWORD *)(v6 + 8);
  v45 = *(_DWORD *)(v47 + 4);
  WorkbookCodePage(*(_DWORD *)(v45 + 12), &CodePage);
  if ( a6 && a6 != 4 && a6 != 5 )
  {
    v46 = ISAMDBFindSession(v43);
    v9 = ISAMDBAddVTDef(v46, 1);
    if ( !v9 )
      return -1011;
    v10 = v37;
    *(_DWORD *)(v9 + 40) = 0;
    *(_DWORD *)(v9 + 28) = a6;
    *(_DWORD *)(v9 + 32) = 0;
    v11 = *(int **)(v10 + 40);
    v42 = 0;
    v38 = v11;
    v41 = 0;
    if ( v11 )
    {
      do
      {
        v12 = MemAllocate(288);
        if ( !v12 )
        {
          v18 = -1011;
          goto LABEL_25;
        }
        v13 = v38;
        v14 = v41;
        *(_DWORD *)(v12 + 4) = v41;
        v40 = ++v14;
        *(_DWORD *)(v12 + 8) = v13[3];
        v41 = v14;
        *(_DWORD *)(v12 + 12) = v13[4];
        *(_DWORD *)(v12 + 20) = v13[5];
        *(_DWORD *)(v12 + 16) = v13[6];
        v15 = v13[2] & 0xFFFFFFDF;
        if ( *(_BYTE *)(v7 + 28) != 1 )
          v15 = v13[2];
        *(_DWORD *)(v12 + 24) = v15;
        WorkbookCodePage(*(_DWORD *)(v45 + 12), &CodePage);
        MakeValidJetName((const unsigned __int16 *)v38 + 21, (WCHAR *)(v12 + 28), 65, CodePage);
        MakeValidJetName((const unsigned __int16 *)(v37 + 104), (WCHAR *)(v12 + 158), 65, CodePage);
        if ( *(_DWORD *)(v9 + 40) )
          *v42 = v12;
        else
          *(_DWORD *)(v9 + 40) = v12;
        v42 = (int *)v12;
        v38 = (int *)*v38;
      }
      while ( v38 );
      v16 = v40;
      if ( v40 > 0 )
      {
        v17 = *(_DWORD *)(v9 + 40);
        *(_DWORD *)(v9 + 32) = v40;
        *(_BYTE *)(v9 + 36) = 2;
        *(_DWORD *)(v9 + 44) = v17;
      }
    }
    else
    {
      v16 = 0;
    }
    CurrentProcessId = GetCurrentProcessId();
    v20 = ISAMDBFindTask(CurrentProcessId);
    v18 = (*(int (__thiscall **)(_DWORD, int, int *, _DWORD, int *))(*(_DWORD *)(v20 + 28) + 36))(
            *(_DWORD *)(*(_DWORD *)(v20 + 28) + 36),
            v43,
            &v44,
            *(_DWORD *)(v9 + 12),
            &VTEntryPoints);
    if ( v18 )
    {
LABEL_25:
      ISAMDBDeleteVTDef(v46, v9);
      return v18;
    }
    v21 = v47;
    v22 = Size;
    *(_DWORD *)(v9 + 16) = v44;
    *(_DWORD *)(v9 + 20) = *(_DWORD *)(v21 + 12);
    *(_DWORD *)(v9 + 24) = *(_DWORD *)(v21 + 16);
    Src[1] = v44;
    Src[2] = v16;
    v23 = 56;
    Src[4] = 1;
    Src[13] = 1;
    v24 = Size;
    if ( Size > 0x38 )
      v24 = 56;
    Src[3] = 0;
    Src[0] = v24;
    v25 = 56;
    if ( Size < 0x38 )
      v25 = Size;
    Src[5] = 2;
    Src[6] = 3;
    Src[7] = 4;
    Src[8] = 5;
    Src[9] = 6;
    Src[10] = 7;
    Src[11] = 8;
    Src[12] = 9;
    memcpy(v39, Src, v25);
    return v22 < v23 ? 0x3EE : 0;
  }
  if ( !String2 )
    return -1003;
  if ( !WorkbookMakeValidColumnName(String2, String1, 256, CodePage) )
  {
    ErrorSetExtendedInfoSz1(1);
    return -1002;
  }
  v26 = (_DWORD *)ISAMDBLocateColumn(v37, String1);
  if ( !v26 )
    return -1507;
  if ( a6 )
  {
    if ( a6 == 4 )
    {
      v52[1] = v26[3];
      v52[2] = v26[4];
      v52[3] = v26[6];
      v52[4] = v26[5];
      v31 = v26[2];
      if ( *(_BYTE *)(v7 + 28) == 1 )
        v31 &= ~0x20u;
      v52[5] = v31;
      MakeValidJetName((const unsigned __int16 *)(v37 + 104), v53, 256, CodePage);
      WCSCPY2(256);
      v22 = Size;
      v23 = 1048;
      v32 = Size;
      if ( Size > 0x418 )
        v32 = 1048;
      v52[0] = v32;
      v33 = 1048;
      if ( Size < 0x418 )
        v33 = Size;
      memcpy(v39, v52, v33);
    }
    else
    {
      v50[1] = 0;
      v51[0] = 0;
      if ( WorkbookFormatString(v51, *(_DWORD *)(v37 + 4), v26[4], *(_DWORD *)(v37 + 4)) )
        v51[0] = 0;
      v22 = Size;
      v23 = 520;
      v34 = Size;
      if ( Size > 0x208 )
        v34 = 520;
      v50[0] = v34;
      v35 = 520;
      if ( Size < 0x208 )
        v35 = Size;
      memcpy(v39, v50, v35);
    }
  }
  else
  {
    v27 = *(_BYTE *)(v7 + 28) == 1;
    v48[1] = v26[3];
    v48[2] = v26[4];
    v48[4] = v26[5];
    v48[3] = v26[6];
    v28 = v26[2];
    if ( v27 )
      v28 &= ~0x20u;
    v22 = Size;
    v23 = 24;
    v48[5] = v28;
    v29 = Size;
    if ( Size > 0x18 )
      v29 = 24;
    v48[0] = v29;
    v30 = 24;
    if ( Size < 0x18 )
      v30 = Size;
    memcpy(v39, v48, v30);
  }
  return v22 < v23 ? 0x3EE : 0;
}

```

## disassembly

```asm
0x1002ba40  mov     edi, edi
0x1002ba42  push    ebp
0x1002ba43  mov     ebp, esp
0x1002ba45  and     esp, 0FFFFFFF8h
0x1002ba48  sub     esp, 8ACh
0x1002ba4e  mov     eax, ___security_cookie
0x1002ba53  xor     eax, esp
0x1002ba55  mov     [esp+8ACh+var_4], eax
0x1002ba5c  mov     eax, [ebp+arg_C]
0x1002ba5f  mov     ecx, [ebp+arg_0]
0x1002ba62  mov     edx, [ebp+arg_4]
0x1002ba65  push    ebx
0x1002ba66  push    esi
0x1002ba67  mov     esi, [ebp+arg_14]
0x1002ba6a  mov     [esp+8B4h+var_89C], eax
0x1002ba6e  mov     eax, esi
0x1002ba70  mov     [esp+8B4h+var_88C], ecx
0x1002ba74  push    edi
0x1002ba75  mov     edi, [ebp+String2]
0x1002ba78  sub     eax, 0
0x1002ba7b  jz      short loc_1002BA9A
0x1002ba7d  sub     eax, 1
0x1002ba80  jz      short loc_1002BA9A
0x1002ba82  sub     eax, 1
0x1002ba85  jz      short loc_1002BA9A
0x1002ba87  sub     eax, 1
0x1002ba8a  jz      short loc_1002BAAF
0x1002ba8c  sub     eax, 1
0x1002ba8f  jz      short loc_1002BA9A
0x1002ba91  sub     eax, 1
0x1002ba94  jnz     loc_1002BD05
0x1002ba9a  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002ba9f  mov     ebx, eax
0x1002baa1  test    ebx, ebx
0x1002baa3  jnz     short loc_1002BAB9
0x1002baa5  mov     eax, 0FFFFFAE2h
0x1002baaa  jmp     loc_1002BEC2
0x1002baaf  mov     eax, 0FFFFFC17h
0x1002bab4  jmp     loc_1002BEC2
0x1002bab9  mov     eax, [ebx+4]
0x1002babc  lea     edx, [esp+8B8h+CodePage]
0x1002bac0  mov     [esp+8B8h+var_8A4], eax
0x1002bac4  mov     eax, [ebx+8]
0x1002bac7  mov     [esp+8B8h+var_87C], eax
0x1002bacb  mov     eax, [eax+4]
0x1002bace  mov     [esp+8B8h+var_884], eax
0x1002bad2  mov     ecx, [eax+0Ch]
0x1002bad5  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002bada  test    esi, esi
0x1002badc  jz      loc_1002BD01
0x1002bae2  cmp     esi, 4
0x1002bae5  jz      loc_1002BD01
0x1002baeb  cmp     esi, 5
0x1002baee  jz      loc_1002BD01
0x1002baf4  mov     ecx, [esp+8B8h+var_88C]
0x1002baf8  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002bafd  xor     edx, edx
0x1002baff  mov     [esp+8B8h+var_880], eax
0x1002bb03  inc     edx
0x1002bb04  mov     ecx, eax
0x1002bb06  call    _ISAMDBAddVTDef@8; ISAMDBAddVTDef(x,x)
0x1002bb0b  mov     edi, eax
0x1002bb0d  test    edi, edi
0x1002bb0f  jnz     short loc_1002BB1B
0x1002bb11  mov     eax, 0FFFFFC0Dh
0x1002bb16  jmp     loc_1002BEC2
0x1002bb1b  mov     ecx, [esp+8B8h+var_8A4]
0x1002bb1f  xor     eax, eax
0x1002bb21  mov     [edi+28h], eax
0x1002bb24  mov     [edi+1Ch], esi
0x1002bb27  mov     [edi+20h], eax
0x1002bb2a  mov     ecx, [ecx+28h]
0x1002bb2d  mov     [esp+8B8h+var_890], eax
0x1002bb31  mov     [esp+8B8h+var_8A0], ecx
0x1002bb35  mov     [esp+8B8h+var_894], eax
0x1002bb39  test    ecx, ecx
0x1002bb3b  jz      loc_1002BC14
0x1002bb41  mov     ecx, 120h
0x1002bb46  call    _MemAllocate@4; MemAllocate(x)
0x1002bb4b  mov     esi, eax
0x1002bb4d  test    esi, esi
0x1002bb4f  jz      loc_1002BC0D
0x1002bb55  mov     edx, [esp+8B8h+var_8A0]
0x1002bb59  mov     eax, [esp+8B8h+var_894]
0x1002bb5d  mov     [esi+4], eax
0x1002bb60  inc     eax
0x1002bb61  mov     [esp+8B8h+var_898], eax
0x1002bb65  mov     ecx, [edx+0Ch]
0x1002bb68  mov     [esi+8], ecx
0x1002bb6b  mov     [esp+8B8h+var_894], eax
0x1002bb6f  mov     eax, [edx+10h]
0x1002bb72  mov     [esi+0Ch], eax
0x1002bb75  mov     eax, [edx+14h]
0x1002bb78  mov     [esi+14h], eax
0x1002bb7b  mov     eax, [edx+18h]
0x1002bb7e  mov     [esi+10h], eax
0x1002bb81  mov     eax, [edx+8]
0x1002bb84  and     eax, 0FFFFFFDFh
0x1002bb87  cmp     byte ptr [ebx+1Ch], 1
0x1002bb8b  cmovnz  eax, [edx+8]
0x1002bb8f  lea     edx, [esp+8B8h+CodePage]
0x1002bb93  mov     [esi+18h], eax
0x1002bb96  mov     eax, [esp+8B8h+var_884]
0x1002bb9a  mov     ecx, [eax+0Ch]
0x1002bb9d  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002bba2  push    [esp+8B8h+CodePage]
0x1002bba6  mov     ecx, [esp+8BCh+var_8A0]
0x1002bbaa  lea     edx, [esi+1Ch]
0x1002bbad  push    41h ; 'A'
0x1002bbaf  add     ecx, 2Ah ; '*'
0x1002bbb2  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1002bbb7  mov     ecx, [esp+8B8h+var_8A4]
0x1002bbbb  lea     edx, [esi+9Eh]
0x1002bbc1  push    [esp+8B8h+CodePage]
0x1002bbc5  push    41h ; 'A'
0x1002bbc7  lea     ecx, [ecx+68h]
0x1002bbca  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1002bbcf  cmp     dword ptr [edi+28h], 0
0x1002bbd3  jnz     short loc_1002BBDA
0x1002bbd5  mov     [edi+28h], esi
0x1002bbd8  jmp     short loc_1002BBE0
0x1002bbda  mov     eax, [esp+8B8h+var_890]
0x1002bbde  mov     [eax], esi
0x1002bbe0  mov     eax, [esp+8B8h+var_8A0]
0x1002bbe4  mov     [esp+8B8h+var_890], esi
0x1002bbe8  mov     eax, [eax]
0x1002bbea  mov     [esp+8B8h+var_8A0], eax
0x1002bbee  test    eax, eax
0x1002bbf0  jnz     loc_1002BB41
0x1002bbf6  mov     ebx, [esp+8B8h+var_898]
0x1002bbfa  test    ebx, ebx
0x1002bbfc  jle     short loc_1002BC16
0x1002bbfe  mov     eax, [edi+28h]
0x1002bc01  mov     [edi+20h], ebx
0x1002bc04  mov     byte ptr [edi+24h], 2
0x1002bc08  mov     [edi+2Ch], eax
0x1002bc0b  jmp     short loc_1002BC16
0x1002bc0d  mov     esi, 0FFFFFC0Dh
0x1002bc12  jmp     short loc_1002BC4A
0x1002bc14  mov     ebx, eax
0x1002bc16  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002bc1c  mov     ecx, eax
0x1002bc1e  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002bc23  push    offset _VTEntryPoints
0x1002bc28  push    dword ptr [edi+0Ch]
0x1002bc2b  mov     esi, [eax+1Ch]
0x1002bc2e  lea     eax, [esp+8C0h+var_888]
0x1002bc32  push    eax
0x1002bc33  push    [esp+8C4h+var_88C]
0x1002bc37  mov     esi, [esi+24h]
0x1002bc3a  mov     ecx, esi
0x1002bc3c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002bc42  call    esi
0x1002bc44  mov     esi, eax
0x1002bc46  test    esi, esi
0x1002bc48  jz      short loc_1002BC5C
0x1002bc4a  mov     ecx, [esp+8B8h+var_880]
0x1002bc4e  mov     edx, edi
0x1002bc50  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x1002bc55  mov     eax, esi
0x1002bc57  jmp     loc_1002BEC2
0x1002bc5c  mov     ecx, [esp+8B8h+var_87C]
0x1002bc60  mov     eax, [esp+8B8h+var_888]
0x1002bc64  mov     esi, [ebp+Size]
0x1002bc67  mov     [edi+10h], eax
0x1002bc6a  mov     eax, [ecx+0Ch]
0x1002bc6d  mov     [edi+14h], eax
0x1002bc70  mov     eax, [ecx+10h]
0x1002bc73  mov     [edi+18h], eax
0x1002bc76  mov     eax, [esp+8B8h+var_888]
0x1002bc7a  mov     [esp+8B8h+var_85C], eax
0x1002bc7e  xor     eax, eax
0x1002bc80  inc     eax
0x1002bc81  mov     [esp+8B8h+var_858], ebx
0x1002bc85  push    38h ; '8'
0x1002bc87  pop     edi
0x1002bc88  mov     [esp+8B8h+var_850], eax
0x1002bc8c  cmp     esi, edi
0x1002bc8e  mov     [esp+8B8h+var_82C], eax
0x1002bc95  mov     eax, esi
0x1002bc97  cmova   eax, edi
0x1002bc9a  mov     [esp+8B8h+var_854], 0
0x1002bca2  mov     [esp+8B8h+Src], eax
0x1002bca6  mov     eax, edi
0x1002bca8  cmovb   eax, esi
0x1002bcab  mov     [esp+8B8h+var_84C], 2
0x1002bcb3  push    eax
0x1002bcb4  mov     [esp+8BCh+var_848], 3
0x1002bcbc  lea     eax, [esp+8BCh+Src]
0x1002bcc0  mov     [esp+8BCh+var_844], 4
0x1002bcc8  mov     [esp+8BCh+var_840], 5
0x1002bcd0  mov     [esp+8BCh+var_83C], 6
0x1002bcdb  mov     [esp+8BCh+var_838], 7
0x1002bce6  mov     [esp+8BCh+var_834], 8
0x1002bcf1  mov     [esp+8BCh+var_830], 9
0x1002bcfc  jmp     loc_1002BEAC
0x1002bd01  test    edi, edi
0x1002bd03  jnz     short loc_1002BD0F
0x1002bd05  mov     eax, 0FFFFFC15h
0x1002bd0a  jmp     loc_1002BEC2
0x1002bd0f  push    [esp+8B8h+CodePage]; CodePage
0x1002bd13  lea     edx, [esp+8BCh+String1]; String1
0x1002bd1a  mov     ecx, edi; String2
0x1002bd1c  push    100h; int
0x1002bd21  call    _WorkbookMakeValidColumnName@16; WorkbookMakeValidColumnName(x,x,x,x)
0x1002bd26  test    eax, eax
0x1002bd28  jnz     short loc_1002BD42
0x1002bd2a  push    1
0x1002bd2c  mov     edx, edi
0x1002bd2e  mov     ecx, 0FFFFDFFAh
0x1002bd33  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1002bd38  mov     eax, 0FFFFFC16h
0x1002bd3d  jmp     loc_1002BEC2
0x1002bd42  mov     ecx, [esp+8B8h+var_8A4]
0x1002bd46  lea     edx, [esp+8B8h+String1]
0x1002bd4d  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1002bd52  mov     edx, eax
0x1002bd54  test    edx, edx
0x1002bd56  jnz     short loc_1002BD62
0x1002bd58  mov     eax, 0FFFFFA1Dh
0x1002bd5d  jmp     loc_1002BEC2
0x1002bd62  test    esi, esi
0x1002bd64  jnz     short loc_1002BDB2
0x1002bd66  cmp     byte ptr [ebx+1Ch], 1
0x1002bd6a  mov     eax, [edx+0Ch]
0x1002bd6d  mov     [esp+8B8h+var_874], eax
0x1002bd71  mov     eax, [edx+10h]
0x1002bd74  mov     [esp+8B8h+var_870], eax
0x1002bd78  mov     eax, [edx+14h]
0x1002bd7b  mov     [esp+8B8h+var_868], eax
0x1002bd7f  mov     eax, [edx+18h]
0x1002bd82  mov     [esp+8B8h+var_86C], eax
0x1002bd86  mov     eax, [edx+8]
0x1002bd89  jnz     short loc_1002BD8E
0x1002bd8b  and     eax, 0FFFFFFDFh
0x1002bd8e  mov     esi, [ebp+Size]
0x1002bd91  push    18h
0x1002bd93  pop     edi
0x1002bd94  mov     [esp+8B8h+var_864], eax
0x1002bd98  cmp     esi, edi
0x1002bd9a  mov     eax, esi
0x1002bd9c  cmova   eax, edi
0x1002bd9f  mov     [esp+8B8h+var_878], eax
0x1002bda3  mov     eax, edi
0x1002bda5  cmovb   eax, esi
0x1002bda8  push    eax
0x1002bda9  lea     eax, [esp+8BCh+var_878]
0x1002bdad  jmp     loc_1002BEAC
0x1002bdb2  cmp     esi, 4
0x1002bdb5  jnz     loc_1002BE47
0x1002bdbb  mov     eax, [edx+0Ch]
0x1002bdbe  mov     [esp+8B8h+var_61C], eax
0x1002bdc5  mov     eax, [edx+10h]
0x1002bdc8  mov     [esp+8B8h+var_618], eax
0x1002bdcf  mov     eax, [edx+18h]
0x1002bdd2  mov     [esp+8B8h+var_614], eax
0x1002bdd9  mov     eax, [edx+14h]
0x1002bddc  mov     [esp+8B8h+var_610], eax
0x1002bde3  cmp     byte ptr [ebx+1Ch], 1
0x1002bde7  mov     eax, [edx+8]
0x1002bdea  jnz     short loc_1002BDEF
0x1002bdec  and     eax, 0FFFFFFDFh
0x1002bdef  mov     ecx, [esp+8B8h+var_8A4]
0x1002bdf3  lea     edx, [esp+8B8h+var_608]
0x1002bdfa  push    [esp+8B8h+CodePage]
0x1002bdfe  mov     esi, 100h
0x1002be03  mov     [esp+8BCh+var_60C], eax
0x1002be0a  push    esi
0x1002be0b  lea     ecx, [ecx+68h]
0x1002be0e  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1002be13  push    esi
0x1002be14  mov     edx, edi
0x1002be16  lea     ecx, [esp+8BCh+var_408]
0x1002be1d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002be22  mov     esi, [ebp+Size]
0x1002be25  mov     edi, 418h
0x1002be2a  cmp     esi, edi
0x1002be2c  mov     eax, esi
0x1002be2e  cmova   eax, edi
0x1002be31  mov     [esp+8B8h+var_620], eax
0x1002be38  mov     eax, edi
0x1002be3a  cmovb   eax, esi
0x1002be3d  push    eax
0x1002be3e  lea     eax, [esp+8BCh+var_620]
0x1002be45  jmp     short loc_1002BEAC
0x1002be47  xor     eax, eax
0x1002be49  mov     [esp+8B8h+var_824], 0
0x1002be54  mov     [esp+8B8h+var_820], ax
0x1002be5c  mov     eax, [esp+8B8h+var_8A4]
0x1002be60  mov     ecx, [eax+4]
0x1002be63  lea     eax, [esp+8B8h+var_820]
0x1002be6a  push    ecx
0x1002be6b  push    dword ptr [edx+10h]
0x1002be6e  mov     edx, [edx+20h]
0x1002be71  push    ecx
0x1002be72  mov     ecx, [ecx+0Ch]
0x1002be75  push    eax
0x1002be76  call    _WorkbookFormatString@24; WorkbookFormatString(x,x,x,x,x,x)
0x1002be7b  test    eax, eax
0x1002be7d  jz      short loc_1002BE89
  ... truncated ...
```
