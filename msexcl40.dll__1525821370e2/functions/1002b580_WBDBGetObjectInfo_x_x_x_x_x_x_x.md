# WBDBGetObjectInfo(x,x,x,x,x,x,x)

- ea: `0x1002b580`
- end: `0x1002ba1c`
- name: `_WBDBGetObjectInfo@28`
- size: `1180`
- prototype: `int __stdcall(int, int, unsigned int, int, int, int, int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, service_task`

## callees

- `0x10006390`
- `0x10006400`
- `0x10018b80`
- `0x1001b8e0`
- `0x1001d7d0`
- `0x1001d820`
- `0x1001dce0`
- `0x10025775`
- `0x10026772`
- `0x10026821`
- `0x10027e33`
- `0x1002a7de`
- `0x1002a869`
- `0x1002aaa4`
- `0x1002aecf`
- `0x1002af20`
- `0x1002b3b3`
- `0x1002b480`
- `0x1002b527`
- `0x1002b580`
- `0x10035510`
- `0x10035530`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b8a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b8a5`

## pseudocode

```c
int __stdcall WBDBGetObjectInfo(int a1, int a2, unsigned int a3, int a4, int a5, int a6, int a7)
{
  int v7; // eax
  int v8; // ecx
  int result; // eax
  _DWORD *v10; // ebx
  _DWORD *v11; // eax
  _DWORD *v12; // edi
  int v13; // ecx
  int MatchingFile; // eax
  int v15; // ebx
  unsigned int v16; // ecx
  int v17; // ecx
  int *i; // esi
  __int16 v19; // dx
  int v20; // ecx
  int j; // eax
  int v22; // esi
  _DWORD *k; // eax
  int v24; // eax
  DWORD CurrentProcessId; // eax
  int v26; // eax
  int v27; // esi
  size_t v28; // esi
  bool v29; // cf
  int v30; // eax
  void *v31; // [esp-Ch] [ebp-89Ch]
  int v32; // [esp+10h] [ebp-880h] BYREF
  int v33; // [esp+14h] [ebp-87Ch]
  _DWORD *v34; // [esp+18h] [ebp-878h] BYREF
  int v35; // [esp+1Ch] [ebp-874h] BYREF
  int v36; // [esp+20h] [ebp-870h]
  int v37; // [esp+24h] [ebp-86Ch] BYREF
  int v38; // [esp+28h] [ebp-868h] BYREF
  int v39; // [esp+2Ch] [ebp-864h]
  int v40; // [esp+30h] [ebp-860h] BYREF
  int v41; // [esp+34h] [ebp-85Ch]
  _DWORD Src[16]; // [esp+38h] [ebp-858h] BYREF
  unsigned __int16 v43[256]; // [esp+78h] [ebp-818h] BYREF
  wchar_t FullPath[264]; // [esp+278h] [ebp-618h] BYREF
  wchar_t v45[514]; // [esp+488h] [ebp-408h] BYREF

  v35 = a4;
  v36 = a1;
  v37 = a2;
  v39 = a6;
  v32 = 0;
  switch ( a7 )
  {
    case 0:
    case 1:
    case 2:
    case 5:
      if ( a3 > 1 )
        return -1001;
      v7 = ISAMDBFindDatabaseUser(a1, a2);
      v8 = v7;
      v33 = v7;
      if ( !v7 )
        return -1010;
      v10 = *(_DWORD **)(v7 + 4);
      if ( a7 == 5 || !a7 )
      {
        if ( !a5 )
          return -1003;
        if ( v35 )
        {
          if ( WCSICMP(v35, L"Tables") )
            return -1003;
          v8 = v33;
        }
        v30 = 0;
        v34 = 0;
        if ( !v10[2] )
        {
          result = LocateTableInDatabase(&v34, &v35, 2);
          if ( result )
            return result;
          v30 = (int)v34;
        }
        return WBDBGetTableInfo(v36, v30, a5, *(_DWORD *)(v39 + 12), *(_DWORD *)v39, v8);
      }
      v35 = ISAMDBFindSession(v36);
      v11 = (_DWORD *)ISAMDBAddVTDef(v35, 2);
      v12 = v11;
      if ( !v11 )
        return -1011;
      v11[7] = a7;
      v11[10] = 0;
      v11[8] = 0;
      if ( v10[2] == 1 )
      {
        WCSCPY2(261);
        WCSCAT2(261);
        WCSCAT2(261);
        MatchingFile = DOSFindFirstMatchingFile(FullPath, v13, (int)Src, (int)&v32);
        v15 = v33;
        if ( MatchingFile )
        {
          result = v32;
          while ( !result )
          {
            v16 = 2 * wcslen(v43) - 8;
            if ( v16 >= 0x200 )
              __report_rangecheckfailure();
            *(unsigned __int16 *)((char *)v43 + v16) = 0;
            if ( !AddObject(0, 3, v15) )
              return -1011;
            v17 = DOSFindNextMatchingFile(Src, &v32);
            result = v32;
            if ( v32 )
              return result;
            if ( !v17 )
              goto LABEL_44;
          }
          return result;
        }
      }
      else
      {
        for ( i = (int *)v10[7]; ; i = (int *)*i )
        {
          v20 = v10[3];
          if ( !i )
            break;
          if ( *(_DWORD *)(v20 + 4) != 3 && *(_DWORD *)(v20 + 4) != 4 && *((_BYTE *)i + 12) == 1
            || WorkbookOneSheetPerFile()
            && (*((_WORD *)i + 2) != v19
             || *((_WORD *)i + 4) != v19
             || *((_WORD *)i + 3) != v19
             || *((_WORD *)i + 5) != v19) )
          {
            WorkbookNameAssemble((int)i + 14, (const unsigned __int16 *)&dword_100015E4, v45, 0x1FEu, 1);
            if ( !AddToObjectList(v45, i[1], i[2]) )
            {
LABEL_48:
              v27 = -1011;
              goto LABEL_47;
            }
          }
        }
        for ( j = WorkbookNameFirst(v20, v45, 510, &v37, &v40, &v32);
              !j;
              j = WorkbookNameNext(v10[3], v45, 510, &v37, &v40, &v32) )
        {
          v22 = 0;
          if ( (*((_BYTE *)&ISAMLimits + 2 * v10[4]) & 0x10) != 0 )
          {
            v22 = (unsigned __int16)(v32 & 0x8000) >> 15;
          }
          else
          {
            for ( k = (_DWORD *)v10[13]; ; k = (_DWORD *)*v34 )
            {
              v34 = k;
              if ( !k )
                break;
              if ( !DBlstrcmpi(k + 3, v45) )
              {
                v22 = 1;
                break;
              }
            }
          }
          if ( (v32 & 1) != 0 && !v22 && !AddToObjectList(v45, v40, v41) )
            goto LABEL_48;
        }
        v15 = v33;
      }
LABEL_44:
      if ( (int)v12[8] > 0 )
      {
        v24 = v12[10];
        *((_BYTE *)v12 + 36) = 2;
        v12[11] = v24;
      }
      CurrentProcessId = GetCurrentProcessId();
      v26 = ISAMDBFindTask(CurrentProcessId);
      v27 = (*(int (__thiscall **)(_DWORD, int, int *, _DWORD, int *))(*(_DWORD *)(v26 + 28) + 36))(
              *(_DWORD *)(*(_DWORD *)(v26 + 28) + 36),
              v36,
              &v38,
              v12[3],
              &VTEntryPoints);
      if ( v27 )
      {
LABEL_47:
        ISAMDBDeleteVTDef(v35, v12);
        return v27;
      }
      else
      {
        v12[4] = v38;
        v12[5] = *(_DWORD *)(v15 + 12);
        v12[6] = *(_DWORD *)(v15 + 16);
        Src[1] = v38;
        Src[2] = v12[8];
        v28 = 48;
        Src[3] = 0;
        v29 = *(_DWORD *)v39 < 0x30u;
        Src[4] = 1;
        if ( v29 )
          v28 = *(_DWORD *)v39;
        v31 = *(void **)(v39 + 12);
        Src[5] = 2;
        Src[6] = 3;
        Src[7] = 4;
        Src[10] = 5;
        Src[11] = 6;
        Src[8] = 7;
        Src[9] = 8;
        Src[0] = 48;
        memcpy(v31, Src, v28);
        return v28 < 0x30 ? 0x3EE : 0;
      }
    case 3:
    case 4:
    case 6:
    case 7:
      return -1001;
    default:
      return -1003;
  }
}

```

## disassembly

```asm
0x1002b580  mov     edi, edi
0x1002b582  push    ebp
0x1002b583  mov     ebp, esp
0x1002b585  and     esp, 0FFFFFFF8h
0x1002b588  sub     esp, 884h
0x1002b58e  mov     eax, ___security_cookie
0x1002b593  xor     eax, esp
0x1002b595  mov     [esp+884h+var_4], eax
0x1002b59c  mov     eax, [ebp+arg_C]
0x1002b59f  mov     ecx, [ebp+arg_4]
0x1002b5a2  push    ebx
0x1002b5a3  mov     ebx, [ebp+arg_0]
0x1002b5a6  push    esi
0x1002b5a7  mov     esi, [ebp+arg_18]
0x1002b5aa  mov     [esp+88Ch+var_874], eax
0x1002b5ae  mov     eax, [ebp+arg_14]
0x1002b5b1  mov     [esp+88Ch+var_870], ebx
0x1002b5b5  mov     [esp+88Ch+var_86C], ecx
0x1002b5b9  mov     [esp+88Ch+var_864], eax
0x1002b5bd  mov     [esp+88Ch+var_880], 0
0x1002b5c5  push    edi
0x1002b5c6  mov     edi, [ebp+arg_10]
0x1002b5c9  cmp     esi, 7; switch 8 cases
0x1002b5cc  ja      def_1002B5D9; jumptable 1002B5D9 default case
0x1002b5d2  movzx   eax, ds:byte_1002BA24[esi]
0x1002b5d9  jmp     ds:jpt_1002B5D9[eax*4]; switch jump
0x1002b5e0  cmp     [ebp+arg_8], 1; jumptable 1002B5D9 cases 0-2,5
0x1002b5e4  jz      short loc_1002B5F0
0x1002b5e6  cmp     [ebp+arg_8], 0
0x1002b5ea  jnz     loc_1002B9F4; jumptable 1002B5D9 cases 3,4,6,7
0x1002b5f0  mov     edx, ecx
0x1002b5f2  mov     ecx, ebx
0x1002b5f4  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x1002b5f9  mov     ecx, eax
0x1002b5fb  mov     [esp+890h+var_87C], ecx
0x1002b5ff  test    ecx, ecx
0x1002b601  jnz     short loc_1002B60D
0x1002b603  mov     eax, 0FFFFFC0Eh
0x1002b608  jmp     loc_1002BA00
0x1002b60d  mov     ebx, [ecx+4]
0x1002b610  cmp     esi, 5
0x1002b613  jz      loc_1002B991
0x1002b619  test    esi, esi
0x1002b61b  jz      loc_1002B991
0x1002b621  mov     ecx, [esp+890h+var_870]
0x1002b625  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002b62a  push    2
0x1002b62c  pop     edx
0x1002b62d  mov     ecx, eax
0x1002b62f  mov     [esp+890h+var_874], eax
0x1002b633  call    _ISAMDBAddVTDef@8; ISAMDBAddVTDef(x,x)
0x1002b638  mov     edi, eax
0x1002b63a  test    edi, edi
0x1002b63c  jz      loc_1002B98A
0x1002b642  xor     edx, edx
0x1002b644  mov     [edi+1Ch], esi
0x1002b647  mov     [edi+28h], edx
0x1002b64a  mov     [edi+20h], edx
0x1002b64d  cmp     dword ptr [ebx+8], 1
0x1002b651  jnz     loc_1002B74A
0x1002b657  mov     esi, 105h
0x1002b65c  lea     edx, [ebx+252h]
0x1002b662  push    esi
0x1002b663  lea     ecx, [esp+894h+FullPath]
0x1002b66a  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002b66f  push    esi
0x1002b670  mov     edx, offset asc_1000560C; "*"
0x1002b675  lea     ecx, [esp+894h+FullPath]
0x1002b67c  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002b681  imul    edx, [ebx+10h], 0Ah
0x1002b685  lea     ecx, [esp+890h+FullPath]
0x1002b68c  push    esi
0x1002b68d  add     edx, offset dword_1003C328
0x1002b693  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002b698  lea     eax, [esp+890h+var_880]
0x1002b69c  push    eax; int
0x1002b69d  lea     eax, [esp+894h+Src]
0x1002b6a1  push    eax; int
0x1002b6a2  push    ecx; int
0x1002b6a3  lea     edx, [esp+89Ch+var_818]
0x1002b6aa  lea     ecx, [esp+89Ch+FullPath]; FullPath
0x1002b6b1  call    _DOSFindFirstMatchingFile@20; DOSFindFirstMatchingFile(x,x,x,x,x)
0x1002b6b6  mov     ebx, [esp+890h+var_87C]
0x1002b6ba  test    eax, eax
0x1002b6bc  jz      loc_1002B895
0x1002b6c2  mov     eax, [esp+890h+var_880]
0x1002b6c6  xor     esi, esi
0x1002b6c8  test    eax, eax
0x1002b6ca  jnz     loc_1002BA00
0x1002b6d0  lea     ecx, [esp+890h+var_818]
0x1002b6d4  lea     edx, [ecx+2]
0x1002b6d7  mov     ax, [ecx]
0x1002b6da  add     ecx, 2
0x1002b6dd  cmp     ax, si
0x1002b6e0  jnz     short loc_1002B6D7
0x1002b6e2  sub     ecx, edx
0x1002b6e4  sar     ecx, 1
0x1002b6e6  lea     ecx, ds:0FFFFFFF8h[ecx*2]
0x1002b6ed  cmp     ecx, 200h
0x1002b6f3  jnb     loc_1002BA17
0x1002b6f9  push    ebx
0x1002b6fa  xor     eax, eax
0x1002b6fc  lea     edx, [esp+894h+var_818]
0x1002b700  push    3
0x1002b702  mov     [esp+ecx+898h+var_818], ax
0x1002b70a  xorps   xmm3, xmm3
0x1002b70d  push    esi
0x1002b70e  mov     ecx, edi
0x1002b710  call    AddObject
0x1002b715  test    eax, eax
0x1002b717  jz      loc_1002B98A
0x1002b71d  lea     eax, [esp+890h+var_880]
0x1002b721  push    eax
0x1002b722  lea     eax, [esp+894h+Src]
0x1002b726  push    eax
0x1002b727  lea     ecx, [esp+898h+var_818]
0x1002b72e  call    _DOSFindNextMatchingFile@16; DOSFindNextMatchingFile(x,x,x,x)
0x1002b733  mov     ecx, eax
0x1002b735  mov     eax, [esp+890h+var_880]
0x1002b739  test    eax, eax
0x1002b73b  jnz     loc_1002BA00
0x1002b741  test    ecx, ecx
0x1002b743  jnz     short loc_1002B6C8
0x1002b745  jmp     loc_1002B895
0x1002b74a  mov     esi, [ebx+1Ch]
0x1002b74d  jmp     short loc_1002B7C3
0x1002b74f  cmp     dword ptr [ecx+4], 3
0x1002b753  jz      short loc_1002B761
0x1002b755  cmp     dword ptr [ecx+4], 4
0x1002b759  jz      short loc_1002B761
0x1002b75b  cmp     byte ptr [esi+0Ch], 1
0x1002b75f  jz      short loc_1002B782
0x1002b761  call    _WorkbookOneSheetPerFile@4; WorkbookOneSheetPerFile(x)
0x1002b766  test    eax, eax
0x1002b768  jz      short loc_1002B7C1
0x1002b76a  cmp     [esi+4], dx
0x1002b76e  jnz     short loc_1002B782
0x1002b770  cmp     [esi+8], dx
0x1002b774  jnz     short loc_1002B782
0x1002b776  cmp     [esi+6], dx
0x1002b77a  jnz     short loc_1002B782
0x1002b77c  cmp     [esi+0Ah], dx
0x1002b780  jz      short loc_1002B7C1
0x1002b782  push    1
0x1002b784  push    1FEh
0x1002b789  lea     eax, [esp+898h+var_408]
0x1002b790  mov     edx, offset dword_100015E4
0x1002b795  push    eax
0x1002b796  lea     ecx, [esi+0Eh]
0x1002b799  call    _WorkbookNameAssemble@20; WorkbookNameAssemble(x,x,x,x,x)
0x1002b79e  push    dword ptr [esi+8]
0x1002b7a1  mov     edx, [esp+894h+var_87C]
0x1002b7a5  lea     eax, [esp+894h+var_408]
0x1002b7ac  push    dword ptr [esi+4]
0x1002b7af  mov     ecx, edi
0x1002b7b1  push    eax
0x1002b7b2  call    AddToObjectList
0x1002b7b7  test    eax, eax
0x1002b7b9  jz      loc_1002B8EB
0x1002b7bf  xor     edx, edx
0x1002b7c1  mov     esi, [esi]
0x1002b7c3  mov     ecx, [ebx+0Ch]
0x1002b7c6  test    esi, esi
0x1002b7c8  jnz     short loc_1002B74F
0x1002b7ca  lea     eax, [esp+890h+var_880]
0x1002b7ce  push    eax
0x1002b7cf  lea     eax, [esp+894h+var_860]
0x1002b7d3  push    eax
0x1002b7d4  lea     eax, [esp+898h+var_86C]
0x1002b7d8  push    eax
0x1002b7d9  push    1FEh
0x1002b7de  lea     edx, [esp+8A0h+var_408]
0x1002b7e5  call    _WorkbookNameFirst@24; WorkbookNameFirst(x,x,x,x,x,x)
0x1002b7ea  jmp     loc_1002B889
0x1002b7ef  mov     eax, [ebx+10h]
0x1002b7f2  xor     esi, esi
0x1002b7f4  test    byte ptr _ISAMLimits[eax*2], 10h
0x1002b7fc  jnz     short loc_1002B82B
0x1002b7fe  mov     eax, [ebx+34h]
0x1002b801  jmp     short loc_1002B81C
0x1002b803  lea     ecx, [eax+0Ch]
0x1002b806  lea     edx, [esp+890h+var_408]
0x1002b80d  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x1002b812  test    eax, eax
0x1002b814  jz      short loc_1002B826
0x1002b816  mov     eax, [esp+890h+var_878]
0x1002b81a  mov     eax, [eax]
0x1002b81c  mov     [esp+890h+var_878], eax
0x1002b820  test    eax, eax
0x1002b822  jnz     short loc_1002B803
0x1002b824  jmp     short loc_1002B838
0x1002b826  xor     esi, esi
0x1002b828  inc     esi
0x1002b829  jmp     short loc_1002B838
0x1002b82b  mov     esi, [esp+890h+var_880]
0x1002b82f  and     esi, 8000h
0x1002b835  shr     esi, 0Fh
0x1002b838  test    byte ptr [esp+890h+var_880], 1
0x1002b83d  jz      short loc_1002B866
0x1002b83f  test    esi, esi
0x1002b841  jnz     short loc_1002B866
0x1002b843  push    [esp+890h+var_85C]
0x1002b847  mov     edx, [esp+894h+var_87C]
0x1002b84b  lea     eax, [esp+894h+var_408]
0x1002b852  push    [esp+894h+var_860]
0x1002b856  mov     ecx, edi
0x1002b858  push    eax
0x1002b859  call    AddToObjectList
0x1002b85e  test    eax, eax
0x1002b860  jz      loc_1002B8EB
0x1002b866  mov     ecx, [ebx+0Ch]
0x1002b869  lea     eax, [esp+890h+var_880]
0x1002b86d  push    eax
0x1002b86e  lea     eax, [esp+894h+var_860]
0x1002b872  push    eax
0x1002b873  lea     eax, [esp+898h+var_86C]
0x1002b877  push    eax
0x1002b878  push    1FEh
0x1002b87d  lea     edx, [esp+8A0h+var_408]
0x1002b884  call    _WorkbookNameNext@24; WorkbookNameNext(x,x,x,x,x,x)
0x1002b889  test    eax, eax
0x1002b88b  jz      loc_1002B7EF
0x1002b891  mov     ebx, [esp+890h+var_87C]
0x1002b895  cmp     dword ptr [edi+20h], 0
0x1002b899  jle     short loc_1002B8A5
0x1002b89b  mov     eax, [edi+28h]
0x1002b89e  mov     byte ptr [edi+24h], 2
0x1002b8a2  mov     [edi+2Ch], eax
0x1002b8a5  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002b8ab  mov     ecx, eax
0x1002b8ad  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002b8b2  push    offset _VTEntryPoints
0x1002b8b7  push    dword ptr [edi+0Ch]
0x1002b8ba  mov     esi, [eax+1Ch]
0x1002b8bd  lea     eax, [esp+898h+var_868]
0x1002b8c1  push    eax
0x1002b8c2  push    [esp+89Ch+var_870]
0x1002b8c6  mov     esi, [esi+24h]
0x1002b8c9  mov     ecx, esi
0x1002b8cb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002b8d1  call    esi
0x1002b8d3  mov     esi, eax
0x1002b8d5  test    esi, esi
0x1002b8d7  jz      short loc_1002B8F2
0x1002b8d9  mov     ecx, [esp+890h+var_874]
0x1002b8dd  mov     edx, edi
0x1002b8df  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x1002b8e4  mov     eax, esi
0x1002b8e6  jmp     loc_1002BA00
0x1002b8eb  mov     esi, 0FFFFFC0Dh
0x1002b8f0  jmp     short loc_1002B8D9
0x1002b8f2  mov     eax, [esp+890h+var_868]
0x1002b8f6  lea     ecx, [esp+890h+Src]
0x1002b8fa  mov     [edi+10h], eax
0x1002b8fd  mov     eax, [ebx+0Ch]
0x1002b900  mov     [edi+14h], eax
0x1002b903  mov     eax, [ebx+10h]
0x1002b906  mov     [edi+18h], eax
0x1002b909  mov     eax, [esp+890h+var_868]
0x1002b90d  mov     [esp+890h+var_854], eax
0x1002b911  mov     eax, [edi+20h]
0x1002b914  mov     [esp+890h+var_850], eax
0x1002b918  mov     eax, [esp+890h+var_864]
0x1002b91c  push    30h ; '0'
0x1002b91e  pop     edi
0x1002b91f  mov     esi, edi
0x1002b921  mov     [esp+890h+var_84C], 0
0x1002b929  cmp     [eax], edi
0x1002b92b  mov     [esp+890h+var_848], 1
0x1002b933  cmovb   esi, [eax]
0x1002b936  push    esi; Size
0x1002b937  push    ecx; Src
0x1002b938  push    dword ptr [eax+0Ch]; void *
0x1002b93b  mov     [esp+89Ch+var_844], 2
0x1002b943  mov     [esp+89Ch+var_840], 3
0x1002b94b  mov     [esp+89Ch+var_83C], 4
0x1002b953  mov     [esp+89Ch+var_830], 5
0x1002b95b  mov     [esp+89Ch+var_82C], 6
0x1002b963  mov     [esp+89Ch+var_838], 7
0x1002b96b  mov     [esp+89Ch+var_834], 8
0x1002b973  mov     [esp+89Ch+Src], edi
0x1002b977  call    _memcpy
0x1002b97c  add     esp, 0Ch
0x1002b97f  cmp     esi, edi
0x1002b981  sbb     eax, eax
0x1002b983  and     eax, 3EEh
0x1002b988  jmp     short loc_1002BA00
0x1002b98a  mov     eax, 0FFFFFC0Dh
0x1002b98f  jmp     short loc_1002BA00
0x1002b991  test    edi, edi
0x1002b993  jz      short def_1002B5D9; jumptable 1002B5D9 default case
0x1002b995  mov     eax, [esp+890h+var_874]
0x1002b999  test    eax, eax
0x1002b99b  jz      short loc_1002B9B1
0x1002b99d  mov     edx, offset aTables; "Tables"
0x1002b9a2  mov     ecx, eax
0x1002b9a4  call    _WCSICMP@8; WCSICMP(x,x)
0x1002b9a9  test    eax, eax
0x1002b9ab  jnz     short def_1002B5D9; jumptable 1002B5D9 default case
0x1002b9ad  mov     ecx, [esp+890h+var_87C]
  ... truncated ...
```
