# WBISAMTerm()

- ea: `0x10007090`
- end: `0x10007313`
- name: `_WBISAMTerm@0`
- size: `643`
- prototype: `_DWORD __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x10006a60`
- `0x10007090`
- `0x10025ab7`
- `0x1002a907`
- `0x10035b40`

## import_xrefs

- `ole32!OleUninitialize` at `0x100072c2`
- `ole32!OleUninitialize` at `0x100072c2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100071fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100071fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100070a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100070a0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x100072e9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x100072e9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x100072e2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x100072e2`

## pseudocode

```c
int __stdcall WBISAMTerm()
{
  DWORD CurrentProcessId; // eax
  _DWORD *v1; // ebx
  _DWORD *v2; // ecx
  _DWORD *v5; // eax
  _DWORD **v6; // edi
  _DWORD *v7; // esi
  _DWORD *v8; // eax
  _DWORD *v9; // esi
  _DWORD *v10; // edx
  _DWORD *v11; // edi
  _DWORD *v12; // ecx
  _DWORD *v13; // edi
  int v14; // eax
  _DWORD *v15; // edx
  _DWORD *v16; // esi
  int i; // esi
  int j; // esi
  int v19; // esi
  int v20; // edi
  void *v21; // esi
  _DWORD *v22; // [esp+4h] [ebp-14h]
  int v23; // [esp+8h] [ebp-10h]
  _DWORD *v24; // [esp+Ch] [ebp-Ch]
  _DWORD *v25; // [esp+10h] [ebp-8h]
  int v26; // [esp+14h] [ebp-4h]

  v23 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v1 = (_DWORD *)dword_1003AE68;
  v2 = (_DWORD *)dword_1003AE68;
  v26 = dword_1003AE68;
  if ( !dword_1003AE68 )
    return -1029;
  while ( v2[4] != CurrentProcessId )
  {
    v2 = (_DWORD *)*v2;
    v26 = (int)v2;
    if ( !v2 )
      return -1029;
  }
  if ( !v2 )
    return -1029;
  --dword_1003A74C;
  if ( v2[3]-- == 1 )
  {
    v5 = (_DWORD *)v2[1];
    v6 = (_DWORD **)(v2 + 1);
    if ( v5 )
    {
      v26 = (int)v2;
      do
      {
        v7 = (_DWORD *)*v5;
        v23 = WBISAMEndSession(v5[3], 0);
        v5 = v7;
      }
      while ( v7 );
      v1 = (_DWORD *)dword_1003AE68;
      v2 = (_DWORD *)v26;
    }
    v24 = 0;
    if ( v1 )
    {
      while ( v1 != v2 )
      {
        v24 = v1;
        v1 = (_DWORD *)*v1;
        if ( !v1 )
          goto LABEL_35;
      }
      v8 = *v6;
      if ( *v6 )
      {
        do
        {
          v9 = (_DWORD *)v1[1];
          v10 = 0;
          v11 = (_DWORD *)*v8;
          v22 = (_DWORD *)*v8;
          v25 = 0;
          if ( v9 )
          {
            while ( v9 != v8 )
            {
              v10 = v9;
              v9 = (_DWORD *)*v9;
              v25 = v10;
              if ( !v9 )
                goto LABEL_27;
            }
            v12 = (_DWORD *)v9[2];
            if ( v12 )
            {
              do
              {
                v13 = (_DWORD *)*v12;
                MemFree(v12);
                v12 = v13;
              }
              while ( v13 );
              v10 = v25;
              v11 = v22;
            }
            v14 = *v9;
            if ( v10 )
              *v10 = v14;
            else
              v1[1] = v14;
            MemFree(v9);
          }
LABEL_27:
          v8 = v11;
        }
        while ( v11 );
        v2 = (_DWORD *)v26;
      }
      v15 = (_DWORD *)v2[2];
      if ( v15 )
      {
        do
        {
          v16 = (_DWORD *)*v15;
          ISAMDBDeleteDatabase(v1, v15);
          v15 = v16;
        }
        while ( v16 );
      }
      if ( v24 )
        *v24 = *v1;
      else
        dword_1003AE68 = *v1;
      MemFree(v1);
    }
LABEL_35:
    if ( !dword_1003A74C )
    {
      if ( hLibModule )
      {
        InternetCloseHandle((HINTERNET)dword_1003AE18);
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
      if ( dword_1003BAB0 == 1 )
      {
        for ( i = 0; i < 7; ++i )
        {
          MemFree((_DWORD *)dword_1003B9E8[i]);
          MemFree((_DWORD *)dword_1003B9CC[i]);
        }
        for ( j = 0; j < 12; ++j )
        {
          MemFree((_DWORD *)dword_1003BA50[j]);
          MemFree((_DWORD *)dword_1003BA20[j]);
        }
      }
      MemFree((_DWORD *)StandardFormats);
      MemFree((_DWORD *)DWORD1(StandardFormats));
      MemFree((_DWORD *)DWORD2(StandardFormats));
      MemFree((_DWORD *)HIDWORD(StandardFormats));
      MemFree((_DWORD *)qword_1003B8D0);
      MemFree((_DWORD *)HIDWORD(qword_1003B8D0));
      if ( pExcelRecordBuffer )
      {
        MemFree(pExcelRecordBuffer);
        pExcelRecordBuffer = 0;
      }
      if ( dword_1003A75C )
      {
        OleUninitialize();
        --dword_1003A75C;
      }
      v19 = dword_1003AE60;
      if ( dword_1003AE60 )
      {
        do
        {
          v20 = *(_DWORD *)(v19 + 8);
          v21 = *(void **)v19;
          if ( v21 )
          {
            GlobalUnlock(v21);
            GlobalFree(v21);
          }
          v19 = v20;
        }
        while ( v20 );
      }
      dword_1003AE60 = 0;
      dword_1003AE64 = 0;
    }
  }
  return v23;
}

```

## disassembly

```asm
0x10007090  mov     edi, edi
0x10007092  push    ebp
0x10007093  mov     ebp, esp
0x10007095  sub     esp, 14h
0x10007098  push    ebx
0x10007099  mov     [ebp+var_10], 0
0x100070a0  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x100070a6  mov     ebx, dword_1003AE68
0x100070ac  mov     ecx, ebx
0x100070ae  mov     [ebp+var_4], ebx
0x100070b1  test    ecx, ecx
0x100070b3  jz      short loc_100070C3
0x100070b5  cmp     [ecx+10h], eax
0x100070b8  jz      short loc_100070CD
0x100070ba  mov     ecx, [ecx]
0x100070bc  mov     [ebp+var_4], ecx
0x100070bf  test    ecx, ecx
0x100070c1  jnz     short loc_100070B5
0x100070c3  mov     eax, 0FFFFFBFBh
0x100070c8  pop     ebx
0x100070c9  mov     esp, ebp
0x100070cb  pop     ebp
0x100070cc  retn
0x100070cd  test    ecx, ecx
0x100070cf  jz      short loc_100070C3
0x100070d1  dec     dword_1003A74C
0x100070d7  add     dword ptr [ecx+0Ch], 0FFFFFFFFh
0x100070db  jnz     loc_1000730B
0x100070e1  mov     eax, [ecx+4]
0x100070e4  push    esi
0x100070e5  push    edi
0x100070e6  lea     edi, [ecx+4]
0x100070e9  test    eax, eax
0x100070eb  jz      short loc_1000710E
0x100070ed  mov     [ebp+var_4], ecx
0x100070f0  mov     esi, [eax]
0x100070f2  push    0
0x100070f4  push    dword ptr [eax+0Ch]
0x100070f7  call    _WBISAMEndSession@8; WBISAMEndSession(x,x)
0x100070fc  mov     [ebp+var_10], eax
0x100070ff  mov     eax, esi
0x10007101  test    esi, esi
0x10007103  jnz     short loc_100070F0
0x10007105  mov     ebx, dword_1003AE68
0x1000710b  mov     ecx, [ebp+var_4]
0x1000710e  xor     edx, edx
0x10007110  mov     [ebp+var_C], edx
0x10007113  test    ebx, ebx
0x10007115  jz      loc_100071C8
0x1000711b  nop     dword ptr [eax+eax+00h]
0x10007120  cmp     ebx, ecx
0x10007122  jz      short loc_10007132
0x10007124  mov     [ebp+var_C], ebx
0x10007127  mov     ebx, [ebx]
0x10007129  test    ebx, ebx
0x1000712b  jnz     short loc_10007120
0x1000712d  jmp     loc_100071C8
0x10007132  mov     eax, [edi]
0x10007134  test    eax, eax
0x10007136  jz      short loc_10007198
0x10007138  mov     esi, [ebx+4]
0x1000713b  xor     edx, edx
0x1000713d  mov     edi, [eax]
0x1000713f  mov     [ebp+var_14], edi
0x10007142  mov     [ebp+var_8], edx
0x10007145  test    esi, esi
0x10007147  jz      short loc_1000718F
0x10007149  nop     dword ptr [eax+00000000h]
0x10007150  cmp     esi, eax
0x10007152  jz      short loc_10007161
0x10007154  mov     edx, esi
0x10007156  mov     esi, [esi]
0x10007158  mov     [ebp+var_8], edx
0x1000715b  test    esi, esi
0x1000715d  jnz     short loc_10007150
0x1000715f  jmp     short loc_1000718F
0x10007161  mov     ecx, [esi+8]
0x10007164  test    ecx, ecx
0x10007166  jz      short loc_1000717B
0x10007168  mov     edi, [ecx]
0x1000716a  call    _MemFree@4; MemFree(x)
0x1000716f  mov     ecx, edi
0x10007171  test    edi, edi
0x10007173  jnz     short loc_10007168
0x10007175  mov     edx, [ebp+var_8]
0x10007178  mov     edi, [ebp+var_14]
0x1000717b  mov     eax, [esi]
0x1000717d  test    edx, edx
0x1000717f  jnz     short loc_10007186
0x10007181  mov     [ebx+4], eax
0x10007184  jmp     short loc_10007188
0x10007186  mov     [edx], eax
0x10007188  mov     ecx, esi
0x1000718a  call    _MemFree@4; MemFree(x)
0x1000718f  mov     eax, edi
0x10007191  test    edi, edi
0x10007193  jnz     short loc_10007138
0x10007195  mov     ecx, [ebp+var_4]
0x10007198  mov     edx, [ecx+8]
0x1000719b  test    edx, edx
0x1000719d  jz      short loc_100071AF
0x1000719f  nop
0x100071a0  mov     esi, [edx]
0x100071a2  mov     ecx, ebx
0x100071a4  call    _ISAMDBDeleteDatabase@8; ISAMDBDeleteDatabase(x,x)
0x100071a9  mov     edx, esi
0x100071ab  test    esi, esi
0x100071ad  jnz     short loc_100071A0
0x100071af  mov     edx, [ebp+var_C]
0x100071b2  mov     eax, [ebx]
0x100071b4  test    edx, edx
0x100071b6  jnz     short loc_100071BF
0x100071b8  mov     dword_1003AE68, eax
0x100071bd  jmp     short loc_100071C1
0x100071bf  mov     [edx], eax
0x100071c1  mov     ecx, ebx
0x100071c3  call    _MemFree@4; MemFree(x)
0x100071c8  cmp     dword_1003A74C, 0
0x100071cf  jnz     loc_10007309
0x100071d5  cmp     hLibModule, 0
0x100071dc  jz      short loc_1000720A
0x100071de  push    dword_1003AE18
0x100071e4  mov     esi, InternetCloseHandle
0x100071ea  mov     ecx, esi
0x100071ec  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100071f2  call    esi ; InternetCloseHandle
0x100071f4  push    hLibModule; hLibModule
0x100071fa  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10007200  mov     hLibModule, 0
0x1000720a  cmp     dword_1003BAB0, 1
0x10007211  jnz     short loc_1000725E
0x10007213  xor     esi, esi
0x10007215  nop     word ptr [eax+eax+00000000h]
0x10007220  mov     ecx, dword_1003B9E8[esi*4]
0x10007227  call    _MemFree@4; MemFree(x)
0x1000722c  mov     ecx, dword_1003B9CC[esi*4]
0x10007233  call    _MemFree@4; MemFree(x)
0x10007238  inc     esi
0x10007239  cmp     esi, 7
0x1000723c  jl      short loc_10007220
0x1000723e  xor     esi, esi
0x10007240  mov     ecx, dword_1003BA50[esi*4]
0x10007247  call    _MemFree@4; MemFree(x)
0x1000724c  mov     ecx, dword_1003BA20[esi*4]
0x10007253  call    _MemFree@4; MemFree(x)
0x10007258  inc     esi
0x10007259  cmp     esi, 0Ch
0x1000725c  jl      short loc_10007240
0x1000725e  mov     ecx, dword ptr _StandardFormats
0x10007264  call    _MemFree@4; MemFree(x)
0x10007269  mov     ecx, dword ptr _StandardFormats+4
0x1000726f  call    _MemFree@4; MemFree(x)
0x10007274  mov     ecx, dword ptr _StandardFormats+8
0x1000727a  call    _MemFree@4; MemFree(x)
0x1000727f  mov     ecx, dword ptr _StandardFormats+0Ch
0x10007285  call    _MemFree@4; MemFree(x)
0x1000728a  mov     ecx, dword ptr qword_1003B8D0
0x10007290  call    _MemFree@4; MemFree(x)
0x10007295  mov     ecx, dword ptr qword_1003B8D0+4
0x1000729b  call    _MemFree@4; MemFree(x)
0x100072a0  mov     ecx, _pExcelRecordBuffer
0x100072a6  test    ecx, ecx
0x100072a8  jz      short loc_100072B9
0x100072aa  call    _MemFree@4; MemFree(x)
0x100072af  mov     _pExcelRecordBuffer, 0
0x100072b9  cmp     dword_1003A75C, 0
0x100072c0  jz      short loc_100072CE
0x100072c2  call    ds:__imp__OleUninitialize@0; OleUninitialize()
0x100072c8  dec     dword_1003A75C
0x100072ce  mov     esi, dword_1003AE60
0x100072d4  test    esi, esi
0x100072d6  jz      short loc_100072F5
0x100072d8  mov     edi, [esi+8]
0x100072db  mov     esi, [esi]
0x100072dd  test    esi, esi
0x100072df  jz      short loc_100072EF
0x100072e1  push    esi; hMem
0x100072e2  call    ds:__imp__GlobalUnlock@4; GlobalUnlock(x)
0x100072e8  push    esi; hMem
0x100072e9  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x100072ef  mov     esi, edi
0x100072f1  test    edi, edi
0x100072f3  jnz     short loc_100072D8
0x100072f5  mov     dword_1003AE60, 0
0x100072ff  mov     dword_1003AE64, 0
0x10007309  pop     edi
0x1000730a  pop     esi
0x1000730b  mov     eax, [ebp+var_10]
0x1000730e  pop     ebx
0x1000730f  mov     esp, ebp
0x10007311  pop     ebp
0x10007312  retn
```
