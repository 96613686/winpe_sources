# CreateSharedDragFormats(IDataObject *,ushort * *)

- ea: `0x1800220b8`
- end: `0x180022494`
- name: `?CreateSharedDragFormats@@YAPEAXPEAUIDataObject@@PEAPEAG@Z`
- size: `988`
- prototype: `void *__fastcall(IDataObject *pIDataObject, wchar_t **pszDataFormats)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800404b0`

## callees

- `0x180010fac`
- `0x18001a3bc`
- `0x1800220b8`
- `0x18002249c`
- `0x180022524`
- `0x1800225a0`
- `0x180022b70`
- `0x180046460`
- `0x180094eb8`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002243b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002243b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800221d7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800221d7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022206`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022206`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180022475`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180022475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002234d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002239f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002234d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002239f`

## pseudocode

```c
wchar_t *__fastcall CreateSharedDragFormats(IDataObject *pIDataObject, wchar_t **pszDataFormats)
{
  wchar_t *v3; // r12
  char *v4; // r14
  int v5; // esi
  int v6; // r13d
  wchar_t *pszStringData; // rdi
  unsigned __int64 cchStringData; // rbx
  HRESULT EnumFormatEtc; // eax
  const wchar_t *v10; // rcx
  int v11; // eax
  DWORD dwMaximumSizeLow; // esi
  DWORD CurrentThreadId; // eax
  wchar_t *FileMappingW; // rax
  _DWORD *v15; // r12
  char *v16; // r13
  unsigned int v17; // r8d
  unsigned int *v18; // rdx
  unsigned __int64 v19; // rsi
  int v20; // eax
  wchar_t *v22; // rax
  IEnumFORMATETC *penum; // [rsp+30h] [rbp-D0h] BYREF
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short> > dataFormatsBuffer; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-B0h]
  tagFORMATETC FormatEtc; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t szSharedMemoryName[32]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t currentFormatName[264]; // [rsp+C0h] [rbp-40h] BYREF

  if ( pszDataFormats )
    *pszDataFormats = 0;
  v25 = 0;
  v3 = 0;
  memset(&dataFormatsBuffer, 0, sizeof(dataFormatsBuffer));
  v4 = 0;
  v5 = 0;
  v6 = 0;
  penum = 0;
  pszStringData = 0;
  cchStringData = 0;
  EnumFormatEtc = wGetEnumFormatEtc(pIDataObject, (unsigned int)pszDataFormats, &penum);
  memset(&FormatEtc, 0, sizeof(FormatEtc));
  if ( !EnumFormatEtc )
  {
    while ( 1 )
    {
      v11 = ((__int64 (__fastcall *)(IEnumFORMATETC *, __int64, tagFORMATETC *))penum->lpVtbl[1].QueryInterface)(
              penum,
              1,
              &FormatEtc);
      if ( v11 )
        break;
      ++v6;
      v5 += 48;
      if ( FormatEtc.ptd )
      {
        v5 += FormatEtc.ptd->tdSize;
        CoTaskMemFree(FormatEtc.ptd);
      }
    }
    pszStringData = v25;
    if ( v11 == 1 )
    {
      if ( v5 )
      {
        dwMaximumSizeLow = v5 + 72;
        CurrentThreadId = GetCurrentThreadId();
        StringCchPrintfW(szSharedMemoryName, 0x20u, szSharedMemoryTemplate, CurrentThreadId);
        FileMappingW = (wchar_t *)CreateFileMappingW(
                                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                    0,
                                    4u,
                                    0,
                                    dwMaximumSizeLow,
                                    szSharedMemoryName);
        v25 = FileMappingW;
        v3 = FileMappingW;
        if ( FileMappingW )
        {
          v4 = (char *)MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
          if ( v4 )
          {
            *(_DWORD *)v4 = 0;
            *((_DWORD *)v4 + 1) = dwMaximumSizeLow;
            *((_DWORD *)v4 + 3) = v6;
            *((_DWORD *)v4 + 2) = 1;
            *((_DWORD *)v4 + 5) = 1;
            ((void (__fastcall *)(IEnumFORMATETC *))penum->lpVtbl[1].Release)(penum);
            v15 = v4 + 24;
            v16 = &v4[48 * (v6 + 1) + 24];
            while ( ((unsigned int (__fastcall *)(IEnumFORMATETC *, __int64, _DWORD *))penum->lpVtbl[1].QueryInterface)(
                      penum,
                      1,
                      v15) != 1 )
            {
              v18 = (unsigned int *)*((_QWORD *)v15 + 1);
              if ( v18 )
              {
                memcpy_0(v16, v18, *v18);
                CoTaskMemFree(*((LPVOID *)v15 + 1));
                *((_QWORD *)v15 + 1) = v16 - v4;
                v16 += *(unsigned int *)v16;
              }
              if ( pszDataFormats && GetDataObjectFormatName(*(_WORD *)v15, currentFormatName, v17) >= 0 )
              {
                if ( cchStringData == -1 )
                {
                  if ( pszStringData )
                  {
                    cchStringData = -1;
                    do
                      ++cchStringData;
                    while ( pszStringData[cchStringData] );
                    dataFormatsBuffer._cchStringData = cchStringData;
                  }
                  else
                  {
                    cchStringData = 0;
                    dataFormatsBuffer._cchStringData = 0;
                  }
                }
                if ( cchStringData )
                {
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                    &dataFormatsBuffer,
                    L";");
                  cchStringData = dataFormatsBuffer._cchStringData;
                  pszStringData = dataFormatsBuffer._pszStringData;
                }
                v19 = -1;
                do
                  ++v19;
                while ( currentFormatName[v19] );
                if ( cchStringData == -1 )
                {
                  if ( pszStringData )
                  {
                    cchStringData = -1;
                    do
                      ++cchStringData;
                    while ( pszStringData[cchStringData] );
                    dataFormatsBuffer._cchStringData = cchStringData;
                  }
                  else
                  {
                    cchStringData = 0;
                    dataFormatsBuffer._cchStringData = 0;
                  }
                }
                v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                        &dataFormatsBuffer,
                        v19 + cchStringData);
                pszStringData = dataFormatsBuffer._pszStringData;
                cchStringData = dataFormatsBuffer._cchStringData;
                if ( v20 >= 0 )
                {
                  StringCchCopyNW(
                    &dataFormatsBuffer._pszStringData[dataFormatsBuffer._cchStringData],
                    v19 + 1,
                    currentFormatName,
                    v19);
                  cchStringData += v19;
                  dataFormatsBuffer._cchStringData = cchStringData;
                }
              }
              v15 += 12;
            }
            v3 = v25;
          }
          else
          {
            CloseHandle(v3);
            v3 = 0;
          }
        }
      }
    }
  }
  if ( penum && !IsTaskName(v10) )
    ((void (__fastcall *)(IEnumFORMATETC *))penum->lpVtbl->Release)(penum);
  if ( v4 )
    UnmapViewOfFile(v4);
  if ( pszDataFormats )
  {
    v22 = pszStringData;
    pszStringData = 0;
    *pszDataFormats = v22;
  }
  if ( pszStringData )
    CoTaskMemFree(pszStringData);
  return v3;
}

```

## disassembly

```asm
0x1800220b8  mov     [rsp-8+arg_10], rbx
0x1800220bd  push    rbp
0x1800220be  push    rsi
0x1800220bf  push    rdi
0x1800220c0  push    r12
0x1800220c2  push    r13
0x1800220c4  push    r14
0x1800220c6  push    r15
0x1800220c8  lea     rbp, [rsp-1E0h]
0x1800220d0  sub     rsp, 2E0h
0x1800220d7  mov     rax, cs:__security_cookie
0x1800220de  xor     rax, rsp
0x1800220e1  mov     [rbp+210h+var_40], rax
0x1800220e8  xor     eax, eax
0x1800220ea  mov     r15, pszDataFormats
0x1800220ed  test    pszDataFormats, pszDataFormats
0x1800220f0  jnz     loc_180022387
0x1800220f6  lea     r8, [rsp+310h+penum]; pDataObj
0x1800220fb  mov     [rsp+310h+var_2C0], rax
0x180022100  mov     r12, rax
0x180022103  mov     [rsp+310h+dataFormatsBuffer._pszStringData], rax
0x180022108  mov     r14, rax
0x18002210b  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rax
0x180022110  mov     esi, eax
0x180022112  mov     [rsp+310h+dataFormatsBuffer._cchStringDataCapacity], rax
0x180022117  mov     r13d, eax
0x18002211a  mov     [rsp+310h+penum], rax
0x18002211f  mov     rdi, rax
0x180022122  mov     rbx, rax
0x180022125  call    ?wGetEnumFormatEtc@@YAJPEAUIDataObject@@KPEAPEAUIEnumFORMATETC@@@Z; wGetEnumFormatEtc(IDataObject *,ulong,IEnumFORMATETC * *)
0x18002212a  xorps   xmm0, xmm0
0x18002212d  movups  xmmword ptr [rsp+310h+FormatEtc.cfFormat], xmm0
0x180022132  movups  xmmword ptr [rsp+310h+FormatEtc.dwAspect], xmm0
0x180022137  test    eax, eax
0x180022139  jnz     $exitRtn
0x18002213f  mov     pIDataObject, [rsp+310h+penum]
0x180022144  lea     r8, [rsp+310h+FormatEtc]
0x180022149  xor     r9d, r9d
0x18002214c  mov     rax, [pIDataObject]
0x18002214f  lea     edx, [r9+1]
0x180022153  mov     rax, [rax+18h]
0x180022157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002215c  test    eax, eax
0x18002215e  jnz     short loc_180022180
0x180022160  mov     pIDataObject, [rsp+310h+FormatEtc.ptd]; pv
0x180022165  inc     r13d
0x180022168  add     esi, 30h ; '0'
0x18002216b  test    pIDataObject, pIDataObject
0x18002216e  jz      short loc_18002213F
0x180022170  add     esi, [pIDataObject]
0x180022172  call    cs:__imp_CoTaskMemFree
0x180022179  nop     dword ptr [rax+rax+00h]
0x18002217e  jmp     short loc_18002213F
0x180022180  mov     rdi, [rsp+310h+var_2C0]
0x180022185  cmp     eax, 1
0x180022188  jnz     $exitRtn
0x18002218e  test    esi, esi
0x180022190  jz      $exitRtn
0x180022196  add     esi, 48h ; 'H'
0x180022199  call    cs:__imp_GetCurrentThreadId
0x1800221a0  nop     dword ptr [rax+rax+00h]
0x1800221a5  lea     r8, szSharedMemoryTemplate; pszFormat
0x1800221ac  mov     edx, 20h ; ' '; cchDest
0x1800221b1  mov     r9d, eax
0x1800221b4  lea     pIDataObject, [rbp+210h+szSharedMemoryName]; pszDest
0x1800221b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800221bd  xor     r9d, r9d; dwMaximumSizeHigh
0x1800221c0  lea     rax, [rbp+210h+szSharedMemoryName]
0x1800221c4  mov     [rsp+310h+lpName], rax; lpName
0x1800221c9  xor     edx, edx; lpFileMappingAttributes
0x1800221cb  or      pIDataObject, 0FFFFFFFFFFFFFFFFh; hFile
0x1800221cf  mov     [rsp+310h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x1800221d3  lea     r8d, [r9+4]; flProtect
0x1800221d7  call    cs:__imp_CreateFileMappingW
0x1800221de  nop     dword ptr [rax+rax+00h]
0x1800221e3  mov     [rsp+310h+var_2C0], rax
0x1800221e8  mov     r12, rax
0x1800221eb  test    rax, rax
0x1800221ee  jz      $exitRtn
0x1800221f4  xor     r9d, r9d; dwFileOffsetLow
0x1800221f7  mov     qword ptr [rsp+310h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x1800221fc  xor     r8d, r8d; dwFileOffsetHigh
0x1800221ff  mov     pIDataObject, rax; hFileMappingObject
0x180022202  lea     edx, [r9+2]; dwDesiredAccess
0x180022206  call    cs:__imp_MapViewOfFile
0x18002220d  nop     dword ptr [rax+rax+00h]
0x180022212  mov     r14, rax
0x180022215  xor     eax, eax
0x180022217  test    r14, r14
0x18002221a  jz      $errRtn_13
0x180022220  mov     [r14], eax
0x180022223  mov     [r14+4], esi
0x180022227  mov     [r14+0Ch], r13d
0x18002222b  mov     dword ptr [r14+8], 1
0x180022233  mov     dword ptr [r14+14h], 1
0x18002223b  mov     pIDataObject, [rsp+310h+penum]
0x180022240  mov     pszDataFormats, [pIDataObject]
0x180022243  mov     rax, [pszDataFormats+28h]
0x180022247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002224c  lea     eax, [r13+1]
0x180022250  lea     r12, [r14+18h]
0x180022254  lea     r13, [rax+rax*2]
0x180022258  shl     r13, 4
0x18002225c  add     r13, 18h
0x180022260  add     r13, r14
0x180022263  mov     pIDataObject, [rsp+310h+penum]
0x180022268  xor     r9d, r9d
0x18002226b  mov     r8, r12
0x18002226e  mov     rax, [pIDataObject]
0x180022271  lea     edx, [r9+1]
0x180022275  mov     rax, [rax+18h]
0x180022279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002227e  cmp     eax, 1
0x180022281  jz      loc_18002231E
0x180022287  mov     pszDataFormats, [r12+8]; Src
0x18002228c  test    pszDataFormats, pszDataFormats
0x18002228f  jnz     loc_18002238F
0x180022295  test    r15, r15
0x180022298  jz      short loc_180022315
0x18002229a  movzx   ecx, word ptr [r12]; clipboardFormat
0x18002229f  lea     pszDataFormats, [rbp+210h+currentFormatName]; formatName
0x1800222a3  call    ?GetDataObjectFormatName@@YAJGPEAGI@Z; GetDataObjectFormatName(ushort,ushort *,uint)
0x1800222a8  xor     ecx, ecx
0x1800222aa  test    eax, eax
0x1800222ac  js      short loc_180022315
0x1800222ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800222b2  cmp     rbx, rax
0x1800222b5  jz      loc_1800223C2
0x1800222bb  test    rbx, rbx
0x1800222be  jnz     loc_1800223EA
0x1800222c4  lea     pszDataFormats, [rbp+210h+currentFormatName]
0x1800222c8  mov     rsi, rax
0x1800222cb  inc     rsi
0x1800222ce  cmp     [pszDataFormats+rsi*2], cx
0x1800222d2  jnz     short loc_1800222CB
0x1800222d4  cmp     rbx, rax
0x1800222d7  jz      loc_180022410
0x1800222dd  lea     pszDataFormats, [rsi+rbx]; cchDesired
0x1800222e1  lea     pIDataObject, [rsp+310h+dataFormatsBuffer]; this
0x1800222e6  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800222eb  mov     rdi, [rsp+310h+dataFormatsBuffer._pszStringData]
0x1800222f0  mov     rbx, [rsp+310h+dataFormatsBuffer._cchStringData]
0x1800222f5  test    eax, eax
0x1800222f7  js      short loc_180022315
0x1800222f9  lea     pszDataFormats, [rsi+1]; cchDest
0x1800222fd  mov     r9, rsi; cchToCopy
0x180022300  lea     pIDataObject, [rdi+rbx*2]; pszDest
0x180022304  lea     r8, [rbp+210h+currentFormatName]; pszSrc
0x180022308  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002230d  add     rbx, rsi
0x180022310  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x180022315  add     r12, 30h ; '0'
0x180022319  jmp     loc_180022263
0x18002231e  mov     r12, [rsp+310h+var_2C0]
0x180022323  xor     ebx, ebx
0x180022325  cmp     [rsp+310h+penum], rbx
0x18002232a  jnz     loc_18002244F
0x180022330  test    r14, r14
0x180022333  jnz     loc_180022472
0x180022339  xor     r14d, r14d
0x18002233c  test    r15, r15
0x18002233f  jnz     loc_180022486
0x180022345  test    rdi, rdi
0x180022348  jz      short loc_180022359
0x18002234a  mov     pIDataObject, rdi; pv
0x18002234d  call    cs:__imp_CoTaskMemFree
0x180022354  nop     dword ptr [rax+rax+00h]
0x180022359  mov     rax, r12
0x18002235c  mov     pIDataObject, [rbp+210h+var_40]
0x180022363  xor     pIDataObject, rsp; StackCookie
0x180022366  call    __security_check_cookie
0x18002236b  mov     rbx, [rsp+310h+arg_10]
0x180022373  add     rsp, 2E0h
0x18002237a  pop     r15
0x18002237c  pop     r14
0x18002237e  pop     r13
0x180022380  pop     r12
0x180022382  pop     rdi
0x180022383  pop     rsi
0x180022384  pop     rbp
0x180022385  retn
0x180022387  mov     [pszDataFormats], rax
0x18002238a  jmp     loc_1800220F6
0x18002238f  mov     r8d, [pszDataFormats]; Size
0x180022392  mov     pIDataObject, r13; void *
0x180022395  call    memcpy_0
0x18002239a  mov     pIDataObject, [r12+8]; pv
0x18002239f  call    cs:__imp_CoTaskMemFree
0x1800223a6  nop     dword ptr [rax+rax+00h]
0x1800223ab  mov     rax, r13
0x1800223ae  sub     rax, r14
0x1800223b1  mov     [r12+8], rax
0x1800223b6  mov     eax, [r13+0]
0x1800223ba  add     r13, rax
0x1800223bd  jmp     loc_180022295
0x1800223c2  test    rdi, rdi
0x1800223c5  jz      short loc_1800223DD
0x1800223c7  mov     rbx, rax
0x1800223ca  inc     rbx
0x1800223cd  cmp     [rdi+rbx*2], cx
0x1800223d1  jnz     short loc_1800223CA
0x1800223d3  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x1800223d8  jmp     loc_1800222BB
0x1800223dd  mov     rbx, pIDataObject
0x1800223e0  mov     [rsp+310h+dataFormatsBuffer._cchStringData], pIDataObject
0x1800223e5  jmp     loc_1800222BB
0x1800223ea  lea     pszDataFormats, psz; ";"
0x1800223f1  lea     pIDataObject, [rsp+310h+dataFormatsBuffer]; this
0x1800223f6  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x1800223fb  mov     rbx, [rsp+310h+dataFormatsBuffer._cchStringData]
0x180022400  xor     ecx, ecx
0x180022402  mov     rdi, [rsp+310h+dataFormatsBuffer._pszStringData]
0x180022407  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002240b  jmp     loc_1800222C4
0x180022410  test    rdi, rdi
0x180022413  jz      short loc_18002242B
0x180022415  mov     rbx, rax
0x180022418  inc     rbx
0x18002241b  cmp     [rdi+rbx*2], cx
0x18002241f  jnz     short loc_180022418
0x180022421  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x180022426  jmp     loc_1800222DD
0x18002242b  mov     rbx, pIDataObject
0x18002242e  mov     [rsp+310h+dataFormatsBuffer._cchStringData], pIDataObject
0x180022433  jmp     loc_1800222DD
0x180022438  mov     pIDataObject, r12; hObject
0x18002243b  call    cs:__imp_CloseHandle
0x180022442  nop     dword ptr [rax+rax+00h]
0x180022447  xor     r12d, r12d
0x18002244a  jmp     $exitRtn
0x18002244f  call    ?IsTaskName@@YAHPEBG@Z; IsTaskName(ushort const *)
0x180022454  test    eax, eax
0x180022456  jnz     loc_180022330
0x18002245c  mov     pIDataObject, [rsp+310h+penum]
0x180022461  mov     rax, [pIDataObject]
0x180022464  mov     rax, [rax+10h]
0x180022468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002246d  jmp     loc_180022330
0x180022472  mov     pIDataObject, r14; lpBaseAddress
0x180022475  call    cs:__imp_UnmapViewOfFile
0x18002247c  nop     dword ptr [rax+rax+00h]
0x180022481  jmp     loc_180022339
0x180022486  mov     rax, rdi
0x180022489  mov     rdi, r14
0x18002248c  mov     [r15], rax
0x18002248f  jmp     loc_180022345
```
