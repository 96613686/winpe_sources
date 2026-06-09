# CreateSharedDragFormats(IDataObject *,ushort * *)

- ea: `0x18001b3cc`
- end: `0x18001b777`
- name: `?CreateSharedDragFormats@@YAPEAXPEAUIDataObject@@PEAPEAG@Z`
- size: `939`
- prototype: `void *__fastcall(IDataObject *pIDataObject, wchar_t **pszDataFormats)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ca70`

## callees

- `0x18001775c`
- `0x18001b3cc`
- `0x18001b780`
- `0x18001b884`
- `0x18001b8f8`
- `0x18001b97c`
- `0x18001bf18`
- `0x180052390`
- `0x180096188`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b4a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b72a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b72a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b508`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b508`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b75e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b75e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001b4df`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001b4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b694`

## pseudocode

```c
wchar_t *__fastcall CreateSharedDragFormats(IDataObject *pIDataObject, wchar_t **pszDataFormats)
{
  wchar_t *v3; // r12
  char *v4; // r15
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
0x18001b3cc  mov     [rsp-8+arg_10], rbx
0x18001b3d1  push    rbp
0x18001b3d2  push    rsi
0x18001b3d3  push    rdi
0x18001b3d4  push    r12
0x18001b3d6  push    r13
0x18001b3d8  push    r14
0x18001b3da  push    r15
0x18001b3dc  lea     rbp, [rsp-1E0h]
0x18001b3e4  sub     rsp, 2E0h
0x18001b3eb  mov     rax, cs:__security_cookie
0x18001b3f2  xor     rax, rsp
0x18001b3f5  mov     [rbp+210h+var_40], rax
0x18001b3fc  xor     eax, eax
0x18001b3fe  mov     r14, pszDataFormats
0x18001b401  test    pszDataFormats, pszDataFormats
0x18001b404  jnz     loc_18001B67C
0x18001b40a  lea     r8, [rsp+310h+penum]; pDataObj
0x18001b40f  mov     [rsp+310h+var_2C0], rax
0x18001b414  mov     r12, rax
0x18001b417  mov     [rsp+310h+dataFormatsBuffer._pszStringData], rax
0x18001b41c  mov     r15, rax
0x18001b41f  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rax
0x18001b424  mov     esi, eax
0x18001b426  mov     [rsp+310h+dataFormatsBuffer._cchStringDataCapacity], rax
0x18001b42b  mov     r13d, eax
0x18001b42e  mov     [rsp+310h+penum], rax
0x18001b433  mov     rdi, rax
0x18001b436  mov     rbx, rax
0x18001b439  call    ?wGetEnumFormatEtc@@YAJPEAUIDataObject@@KPEAPEAUIEnumFORMATETC@@@Z; wGetEnumFormatEtc(IDataObject *,ulong,IEnumFORMATETC * *)
0x18001b43e  xorps   xmm0, xmm0
0x18001b441  movups  xmmword ptr [rsp+310h+FormatEtc.cfFormat], xmm0
0x18001b446  movups  xmmword ptr [rsp+310h+FormatEtc.dwAspect], xmm0
0x18001b44b  test    eax, eax
0x18001b44d  jnz     $exitRtn
0x18001b453  mov     pIDataObject, [rsp+310h+penum]
0x18001b458  lea     r8, [rsp+310h+FormatEtc]
0x18001b45d  xor     r9d, r9d
0x18001b460  mov     rax, [pIDataObject]
0x18001b463  lea     edx, [r9+1]
0x18001b467  mov     rax, [rax+18h]
0x18001b46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b470  test    eax, eax
0x18001b472  jnz     short loc_18001B48E
0x18001b474  mov     pIDataObject, [rsp+310h+FormatEtc.ptd]; pv
0x18001b479  inc     r13d
0x18001b47c  add     esi, 30h ; '0'
0x18001b47f  test    pIDataObject, pIDataObject
0x18001b482  jz      short loc_18001B453
0x18001b484  add     esi, [pIDataObject]
0x18001b486  call    cs:__imp_CoTaskMemFree
0x18001b48c  jmp     short loc_18001B453
0x18001b48e  mov     rdi, [rsp+310h+var_2C0]
0x18001b493  cmp     eax, 1
0x18001b496  jnz     $exitRtn
0x18001b49c  test    esi, esi
0x18001b49e  jz      $exitRtn
0x18001b4a4  add     esi, 48h ; 'H'
0x18001b4a7  call    cs:__imp_GetCurrentThreadId
0x18001b4ad  lea     r8, szSharedMemoryTemplate; pszFormat
0x18001b4b4  mov     edx, 20h ; ' '; cchDest
0x18001b4b9  mov     r9d, eax
0x18001b4bc  lea     pIDataObject, [rbp+210h+szSharedMemoryName]; pszDest
0x18001b4c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b4c5  xor     r9d, r9d; dwMaximumSizeHigh
0x18001b4c8  lea     rax, [rbp+210h+szSharedMemoryName]
0x18001b4cc  mov     [rsp+310h+lpName], rax; lpName
0x18001b4d1  xor     edx, edx; lpFileMappingAttributes
0x18001b4d3  or      pIDataObject, 0FFFFFFFFFFFFFFFFh; hFile
0x18001b4d7  mov     [rsp+310h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18001b4db  lea     r8d, [r9+4]; flProtect
0x18001b4df  call    cs:__imp_CreateFileMappingW
0x18001b4e5  mov     [rsp+310h+var_2C0], rax
0x18001b4ea  mov     r12, rax
0x18001b4ed  test    rax, rax
0x18001b4f0  jz      $exitRtn
0x18001b4f6  xor     r9d, r9d; dwFileOffsetLow
0x18001b4f9  mov     qword ptr [rsp+310h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18001b4fe  xor     r8d, r8d; dwFileOffsetHigh
0x18001b501  mov     pIDataObject, rax; hFileMappingObject
0x18001b504  lea     edx, [r9+2]; dwDesiredAccess
0x18001b508  call    cs:__imp_MapViewOfFile
0x18001b50e  mov     r15, rax
0x18001b511  xor     eax, eax
0x18001b513  test    r15, r15
0x18001b516  jz      $errRtn_11
0x18001b51c  mov     [r15], eax
0x18001b51f  mov     [r15+4], esi
0x18001b523  mov     [r15+0Ch], r13d
0x18001b527  mov     dword ptr [r15+8], 1
0x18001b52f  mov     dword ptr [r15+14h], 1
0x18001b537  mov     pIDataObject, [rsp+310h+penum]
0x18001b53c  mov     rax, [pIDataObject]
0x18001b53f  mov     rax, [rax+28h]
0x18001b543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b548  lea     eax, [r13+1]
0x18001b54c  lea     r12, [r15+18h]
0x18001b550  lea     r13, [rax+rax*2]
0x18001b554  shl     r13, 4
0x18001b558  add     r13, 18h
0x18001b55c  add     r13, r15
0x18001b55f  mov     pIDataObject, [rsp+310h+penum]
0x18001b564  xor     r9d, r9d
0x18001b567  mov     r8, r12
0x18001b56a  mov     rax, [pIDataObject]
0x18001b56d  lea     edx, [r9+1]
0x18001b571  mov     rax, [rax+18h]
0x18001b575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b57a  cmp     eax, 1
0x18001b57d  jz      loc_18001B61A
0x18001b583  mov     pszDataFormats, [r12+8]; Src
0x18001b588  test    pszDataFormats, pszDataFormats
0x18001b58b  jnz     loc_18001B684
0x18001b591  test    r14, r14
0x18001b594  jz      short loc_18001B611
0x18001b596  movzx   ecx, word ptr [r12]; clipboardFormat
0x18001b59b  lea     pszDataFormats, [rbp+210h+currentFormatName]; formatName
0x18001b59f  call    ?GetDataObjectFormatName@@YAJGPEAGI@Z; GetDataObjectFormatName(ushort,ushort *,uint)
0x18001b5a4  xor     ecx, ecx
0x18001b5a6  test    eax, eax
0x18001b5a8  js      short loc_18001B611
0x18001b5aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b5ae  cmp     rbx, rax
0x18001b5b1  jz      loc_18001B6B1
0x18001b5b7  test    rbx, rbx
0x18001b5ba  jnz     loc_18001B6D9
0x18001b5c0  lea     pszDataFormats, [rbp+210h+currentFormatName]
0x18001b5c4  mov     rsi, rax
0x18001b5c7  inc     rsi
0x18001b5ca  cmp     [pszDataFormats+rsi*2], cx
0x18001b5ce  jnz     short loc_18001B5C7
0x18001b5d0  cmp     rbx, rax
0x18001b5d3  jz      loc_18001B6FF
0x18001b5d9  lea     pszDataFormats, [rsi+rbx]; cchDesired
0x18001b5dd  lea     pIDataObject, [rsp+310h+dataFormatsBuffer]; this
0x18001b5e2  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18001b5e7  mov     rdi, [rsp+310h+dataFormatsBuffer._pszStringData]
0x18001b5ec  mov     rbx, [rsp+310h+dataFormatsBuffer._cchStringData]
0x18001b5f1  test    eax, eax
0x18001b5f3  js      short loc_18001B611
0x18001b5f5  lea     pszDataFormats, [rsi+1]; cchDest
0x18001b5f9  mov     r9, rsi; cchToCopy
0x18001b5fc  lea     pIDataObject, [rdi+rbx*2]; pszDest
0x18001b600  lea     r8, [rbp+210h+currentFormatName]; pszSrc
0x18001b604  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001b609  add     rbx, rsi
0x18001b60c  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x18001b611  add     r12, 30h ; '0'
0x18001b615  jmp     loc_18001B55F
0x18001b61a  mov     r12, [rsp+310h+var_2C0]
0x18001b61f  xor     ebx, ebx
0x18001b621  cmp     [rsp+310h+penum], rbx
0x18001b626  jnz     loc_18001B738
0x18001b62c  test    r15, r15
0x18001b62f  jnz     loc_18001B75B
0x18001b635  xor     r15d, r15d
0x18001b638  test    r14, r14
0x18001b63b  jnz     loc_18001B769
0x18001b641  test    rdi, rdi
0x18001b644  jz      short loc_18001B64F
0x18001b646  mov     pIDataObject, rdi; pv
0x18001b649  call    cs:__imp_CoTaskMemFree
0x18001b64f  mov     rax, r12
0x18001b652  mov     pIDataObject, [rbp+210h+var_40]
0x18001b659  xor     pIDataObject, rsp; StackCookie
0x18001b65c  call    __security_check_cookie
0x18001b661  mov     rbx, [rsp+310h+arg_10]
0x18001b669  add     rsp, 2E0h
0x18001b670  pop     r15
0x18001b672  pop     r14
0x18001b674  pop     r13
0x18001b676  pop     r12
0x18001b678  pop     rdi
0x18001b679  pop     rsi
0x18001b67a  pop     rbp
0x18001b67b  retn
0x18001b67c  mov     [pszDataFormats], rax
0x18001b67f  jmp     loc_18001B40A
0x18001b684  mov     r8d, [pszDataFormats]; Size
0x18001b687  mov     pIDataObject, r13; void *
0x18001b68a  call    memcpy_0
0x18001b68f  mov     pIDataObject, [r12+8]; pv
0x18001b694  call    cs:__imp_CoTaskMemFree
0x18001b69a  mov     rax, r13
0x18001b69d  sub     rax, r15
0x18001b6a0  mov     [r12+8], rax
0x18001b6a5  mov     eax, [r13+0]
0x18001b6a9  add     r13, rax
0x18001b6ac  jmp     loc_18001B591
0x18001b6b1  test    rdi, rdi
0x18001b6b4  jz      short loc_18001B6CC
0x18001b6b6  mov     rbx, rax
0x18001b6b9  inc     rbx
0x18001b6bc  cmp     [rdi+rbx*2], cx
0x18001b6c0  jnz     short loc_18001B6B9
0x18001b6c2  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x18001b6c7  jmp     loc_18001B5B7
0x18001b6cc  mov     rbx, pIDataObject
0x18001b6cf  mov     [rsp+310h+dataFormatsBuffer._cchStringData], pIDataObject
0x18001b6d4  jmp     loc_18001B5B7
0x18001b6d9  lea     pszDataFormats, psz; ";"
0x18001b6e0  lea     pIDataObject, [rsp+310h+dataFormatsBuffer]; this
0x18001b6e5  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001b6ea  mov     rbx, [rsp+310h+dataFormatsBuffer._cchStringData]
0x18001b6ef  xor     ecx, ecx
0x18001b6f1  mov     rdi, [rsp+310h+dataFormatsBuffer._pszStringData]
0x18001b6f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b6fa  jmp     loc_18001B5C0
0x18001b6ff  test    rdi, rdi
0x18001b702  jz      short loc_18001B71A
0x18001b704  mov     rbx, rax
0x18001b707  inc     rbx
0x18001b70a  cmp     [rdi+rbx*2], cx
0x18001b70e  jnz     short loc_18001B707
0x18001b710  mov     [rsp+310h+dataFormatsBuffer._cchStringData], rbx
0x18001b715  jmp     loc_18001B5D9
0x18001b71a  mov     rbx, pIDataObject
0x18001b71d  mov     [rsp+310h+dataFormatsBuffer._cchStringData], pIDataObject
0x18001b722  jmp     loc_18001B5D9
0x18001b727  mov     pIDataObject, r12; hObject
0x18001b72a  call    cs:__imp_CloseHandle
0x18001b730  xor     r12d, r12d
0x18001b733  jmp     $exitRtn
0x18001b738  call    ?IsTaskName@@YAHPEBG@Z; IsTaskName(ushort const *)
0x18001b73d  test    eax, eax
0x18001b73f  jnz     loc_18001B62C
0x18001b745  mov     pIDataObject, [rsp+310h+penum]
0x18001b74a  mov     rax, [pIDataObject]
0x18001b74d  mov     rax, [rax+10h]
0x18001b751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b756  jmp     loc_18001B62C
0x18001b75b  mov     pIDataObject, r15; lpBaseAddress
0x18001b75e  call    cs:__imp_UnmapViewOfFile
0x18001b764  jmp     loc_18001B635
0x18001b769  mov     rax, rdi
0x18001b76c  mov     rdi, r15
0x18001b76f  mov     [r14], rax
0x18001b772  jmp     loc_18001B641
```
