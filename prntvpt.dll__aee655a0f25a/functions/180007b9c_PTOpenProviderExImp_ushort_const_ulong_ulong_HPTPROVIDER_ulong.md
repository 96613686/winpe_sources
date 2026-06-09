# PTOpenProviderExImp(ushort const *,ulong,ulong,HPTPROVIDER__ * *,ulong *)

- ea: `0x180007b9c`
- end: `0x180008077`
- name: `?PTOpenProviderExImp@@YAJPEBGKKPEAPEAUHPTPROVIDER__@@PEAK@Z`
- size: `1243`
- prototype: `__int64 __fastcall(OLECHAR *strIn, int, int, HPTPROVIDER *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007b28`
- `0x18000c9f0`

## callees

- `0x180005e70`
- `0x180005ea0`
- `0x180007b9c`
- `0x180008080`
- `0x18000bb9c`
- `0x18000bd18`
- `0x18000f53c`
- `0x18001bc9c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007c26`
- `KERNEL32!GetLastError` at `0x180007c26`
- `KERNEL32!GetProcAddress` at `0x180007cbf`
- `KERNEL32!GetProcAddress` at `0x180007cbf`
- `KERNEL32!LoadLibraryExW` at `0x180007c9a`
- `KERNEL32!LoadLibraryExW` at `0x180007c9a`
- `KERNEL32!FreeLibrary` at `0x180007ec8`
- `KERNEL32!FreeLibrary` at `0x180007ec8`
- `KERNEL32!GetProcessHeap` at `0x180007ed3`
- `KERNEL32!GetProcessHeap` at `0x180007ed3`
- `KERNEL32!HeapFree` at `0x180007ee1`
- `KERNEL32!HeapFree` at `0x180007ee1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007f6e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007f6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f1b`
- `WINSPOOL!OpenPrinterW` at `0x180007c1c`
- `WINSPOOL!OpenPrinterW` at `0x180007c1c`
- `WINSPOOL!ClosePrinter` at `0x180007eba`
- `WINSPOOL!ClosePrinter` at `0x180007eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e5c`

## string_xrefs

- `0x180007cb2`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall PTOpenProviderExImp(OLECHAR *strIn, int a2, int a3, HPTPROVIDER *a4, unsigned int *a5)
{
  NCoreLibrary::TReferenceCount *v6; // r14
  struct _DRIVER_INFO_3W *v7; // r13
  unsigned int *v8; // r15
  unsigned __int16 *v9; // rbx
  HMODULE v10; // rsi
  signed int LastError; // eax
  signed int v12; // edi
  int DriverInfo; // eax
  const WCHAR *v14; // rcx
  HMODULE Library; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  FARPROC ProcAddress; // rax
  int v19; // eax
  BOOL v20; // ecx
  int v21; // r8d
  void *v22; // rdx
  signed int v23; // eax
  BSTR *v24; // rcx
  int v25; // edx
  int i; // r15d
  struct IPrintTicketProvider *v27; // rcx
  HANDLE ProcessHeap; // rax
  HPTPROVIDER v29; // rax
  __int64 v31; // rdx
  struct IPrintTicketProvider *v32; // rcx
  int v33; // eax
  TProviderInfo *v34; // rax
  int v35; // [rsp+50h] [rbp-61h] BYREF
  struct IPrintTicketProvider *v36; // [rsp+58h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-49h] BYREF
  enum tagSHIMOPTS v39; // [rsp+70h] [rbp-41h] BYREF
  HANDLE phPrinter; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-31h] BYREF
  __int64 v42; // [rsp+88h] [rbp-29h] BYREF
  __int64 v43; // [rsp+90h] [rbp-21h] BYREF
  GUID v44; // [rsp+A0h] [rbp-11h] BYREF
  GUID v45; // [rsp+B0h] [rbp-1h] BYREF

  v36 = 0;
  v6 = 0;
  v43 = 0;
  v7 = 0;
  bstrString = 0;
  phPrinter = 0;
  v39 = PTSHIM_DEFAULT;
  v41 = 0;
  pv = 0;
  if ( !a4 || (v8 = a5) == 0 || !a2 || !a3 || !strIn )
  {
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v36);
    return 2147942487LL;
  }
  *a4 = 0;
  v9 = 0;
  v10 = 0;
  if ( !OpenPrinterW(strIn, &phPrinter, 0) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    goto LABEL_48;
  }
  DriverInfo = MyGetDriverInfo(phPrinter, (struct _DRIVER_INFO_3W **)&pv);
  v7 = (struct _DRIVER_INFO_3W *)pv;
  v12 = DriverInfo;
  if ( DriverInfo < 0 )
    goto LABEL_48;
  v14 = (const WCHAR *)*((_QWORD *)pv + 5);
  if ( v14 )
  {
    v42 = 0;
    v45 = IID_IPrintTicketProvider;
    v44 = CLSID_PTPROVIDER;
    Library = LoadLibraryExW(v14, 0, 8u);
    v10 = Library;
    if ( Library )
    {
      v12 = 0;
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress
        && ((int (__fastcall *)(GUID *, GUID *, __int64 *, _QWORD))ProcAddress)(&v44, &IID_IClassFactory, &v42, 0) >= 0 )
      {
        if ( v42 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IPrintTicketProvider **))(*(_QWORD *)v42 + 24LL))(
                  v42,
                  0,
                  &v45,
                  &v36);
          if ( v19 == -2147467262 || v19 == -2147221231 )
          {
            v36 = 0;
          }
          else if ( v19 < 0 )
          {
            v12 = v19;
          }
        }
        else
        {
          v12 = -2147467259;
        }
      }
    }
    else
    {
      v12 = -2147418113;
    }
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v42 + 16LL))(v42, v16, v17, 0);
      v42 = 0;
    }
    if ( v12 < 0 )
      goto LABEL_48;
  }
  if ( v36 )
  {
    pv = 0;
    v35 = 0;
    v12 = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, HANDLE, LPVOID *, int *))v36->lpVtbl->GetSupportedVersions)(
            v36,
            phPrinter,
            &pv,
            &v35);
    if ( v12 < 0 || (v20 = 0, v21 = 0, v35 <= 0) )
    {
LABEL_35:
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v36);
      v22 = pv;
    }
    else
    {
      v22 = pv;
      while ( !v20 )
      {
        v20 = *((_DWORD *)pv + v21++) == 1;
        if ( v21 >= v35 )
        {
          if ( v20 )
            break;
          goto LABEL_35;
        }
      }
    }
    CoTaskMemFree(v22);
    if ( v12 < 0 )
      goto LABEL_48;
  }
  if ( !v36 )
    goto LABEL_70;
  pv = 0;
  v35 = 0;
  v23 = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, HANDLE, __int64, enum tagSHIMOPTS *, unsigned int *, int *, LPVOID *))v36->lpVtbl->BindPrinter)(
          v36,
          phPrinter,
          1,
          &v39,
          &v41,
          &v35,
          &pv);
  v24 = (BSTR *)pv;
  v12 = v23;
  if ( pv )
  {
    v25 = v35;
    for ( i = 0; i < v25; ++i )
    {
      if ( v24[i] )
      {
        SysFreeString(v24[i]);
        v24 = (BSTR *)pv;
        v25 = v35;
      }
    }
    CoTaskMemFree(v24);
    v24 = (BSTR *)pv;
    v8 = a5;
  }
  if ( (unsigned int)v39 > PTSHIM_NOSNAPSHOT || v35 && !v24 )
  {
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v36);
    v12 = -2147221502;
    goto LABEL_48;
  }
  if ( v12 >= 0 )
  {
LABEL_70:
    v31 = -1;
    do
      ++v31;
    while ( strIn[v31] );
    v9 = SysAllocStringLen(strIn, v31);
    if ( v9 )
    {
      v32 = v36;
      if ( !v36
        || (v33 = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, BSTR *))v36->lpVtbl->QueryDeviceNamespace)(
                    v36,
                    &bstrString),
            v33 >= 0)
        || v33 == -2147467263 )
      {
        if ( bstrString || (v12 = CreateDriverUniqueUri(v32, v7, &bstrString), v12 >= 0) )
        {
          v34 = (TProviderInfo *)operator new(0x70u);
          if ( v34 )
            v6 = TProviderInfo::TProviderInfo(v34, phPrinter, v7, v10, v9, bstrString, v39, v41, v36);
          NCoreLibrary::TGenericSP<TProviderInfo,NCoreLibrary::TAutoPtrCOM<TProviderInfo>,TProviderInfo *,0,TProviderInfo const *>::Reset(&v43);
          if ( v6 )
          {
            v9 = 0;
            if ( bstrString )
              bstrString = 0;
            phPrinter = 0;
            v10 = 0;
          }
          else
          {
            v12 = -2147024882;
          }
        }
      }
      else
      {
        v12 = v33;
      }
    }
    else
    {
      v12 = -2147024882;
      v9 = 0;
    }
  }
LABEL_48:
  v27 = v36;
  *v8 = 1;
  if ( v27 )
  {
    ((void (__fastcall *)(struct IPrintTicketProvider *))v27->lpVtbl->Release)(v27);
    v36 = 0;
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( v10 )
    FreeLibrary(v10);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  if ( v12 >= 0 )
  {
    v29 = 0;
    if ( v6 )
    {
      v29 = (HPTPROVIDER)v6;
      v6 = 0;
    }
    *a4 = v29;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v9 )
    SysFreeString(v9);
  if ( v6 )
    NCoreLibrary::TReferenceCount::Release(v6);
  if ( v36 )
    ((void (__fastcall *)(struct IPrintTicketProvider *))v36->lpVtbl->Release)(v36);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007b9c  mov     [rsp-8+arg_18], r9
0x180007ba1  push    rbp
0x180007ba2  push    rbx
0x180007ba3  push    rsi
0x180007ba4  push    rdi
0x180007ba5  push    r12
0x180007ba7  push    r13
0x180007ba9  push    r14
0x180007bab  push    r15
0x180007bad  lea     rbp, [rsp-17h]
0x180007bb2  sub     rsp, 0C8h
0x180007bb9  xor     edi, edi
0x180007bbb  mov     r12, rcx
0x180007bbe  mov     [rbp+4Fh+var_A8], rdi
0x180007bc2  mov     r14d, edi
0x180007bc5  mov     [rbp+4Fh+var_70], rdi
0x180007bc9  mov     r13d, edi
0x180007bcc  mov     [rbp+4Fh+bstrString], rdi
0x180007bd0  mov     [rbp+4Fh+phPrinter], rdi
0x180007bd4  mov     [rbp+4Fh+var_90], edi
0x180007bd7  mov     [rbp+4Fh+var_80], edi
0x180007bda  mov     [rbp+4Fh+pv], rdi
0x180007bde  test    r9, r9
0x180007be1  jz      loc_180008055
0x180007be7  mov     r15, [rbp+4Fh+arg_20]
0x180007beb  test    r15, r15
0x180007bee  jz      loc_180008055
0x180007bf4  test    edx, edx
0x180007bf6  jz      loc_180008055
0x180007bfc  test    r8d, r8d
0x180007bff  jz      loc_180008055
0x180007c05  test    rcx, rcx
0x180007c08  jz      loc_180008055
0x180007c0e  xor     r8d, r8d; pDefault
0x180007c11  mov     [r9], rdi
0x180007c14  lea     rdx, [rbp+4Fh+phPrinter]; phPrinter
0x180007c18  mov     ebx, edi
0x180007c1a  mov     esi, edi
0x180007c1c  call    cs:__imp_OpenPrinterW
0x180007c22  test    eax, eax
0x180007c24  jnz     short loc_180007C4D
0x180007c26  call    cs:__imp_GetLastError
0x180007c2c  xor     r12d, r12d
0x180007c2f  mov     edi, eax
0x180007c31  test    eax, eax
0x180007c33  jle     short loc_180007C3E
0x180007c35  movzx   edi, ax
0x180007c38  or      edi, 80070000h
0x180007c3e  test    edi, edi
0x180007c40  mov     eax, 80004005h
0x180007c45  cmovns  edi, eax
0x180007c48  jmp     loc_180007E91
0x180007c4d  mov     rcx, [rbp+4Fh+phPrinter]; hPrinter
0x180007c51  lea     rdx, [rbp+4Fh+pv]; struct _DRIVER_INFO_3W **
0x180007c55  call    ?MyGetDriverInfo@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; MyGetDriverInfo(void *,_DRIVER_INFO_3W * *)
0x180007c5a  mov     r13, [rbp+4Fh+pv]
0x180007c5e  xor     r9d, r9d
0x180007c61  mov     edi, eax
0x180007c63  test    eax, eax
0x180007c65  js      loc_180007E8E
0x180007c6b  mov     rcx, [r13+28h]; lpLibFileName
0x180007c6f  test    rcx, rcx
0x180007c72  jz      loc_180007D52
0x180007c78  movups  xmm0, xmmword ptr cs:IID_IPrintTicketProvider.Data1
0x180007c7f  xor     edx, edx; hFile
0x180007c81  lea     r8d, [r9+8]; dwFlags
0x180007c85  movups  xmm1, xmmword ptr cs:CLSID_PTPROVIDER.Data1
0x180007c8c  mov     [rbp+4Fh+var_78], r9
0x180007c90  movdqu  [rbp+4Fh+var_50], xmm0
0x180007c95  movdqu  [rbp+4Fh+var_60], xmm1
0x180007c9a  call    cs:__imp_LoadLibraryExW
0x180007ca0  xor     r9d, r9d
0x180007ca3  mov     rsi, rax
0x180007ca6  test    rax, rax
0x180007ca9  jnz     short loc_180007CB2
0x180007cab  mov     edi, 8000FFFFh
0x180007cb0  jmp     short loc_180007D2E
0x180007cb2  lea     rdx, ProcName; "DllGetClassObject"
0x180007cb9  mov     rcx, rax; hModule
0x180007cbc  mov     edi, r9d
0x180007cbf  call    cs:__imp_GetProcAddress
0x180007cc5  xor     r9d, r9d
0x180007cc8  test    rax, rax
0x180007ccb  jz      short loc_180007D2E
0x180007ccd  lea     r8, [rbp+4Fh+var_78]
0x180007cd1  lea     rdx, IID_IClassFactory
0x180007cd8  lea     rcx, [rbp+4Fh+var_60]
0x180007cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce1  xor     r9d, r9d
0x180007ce4  test    eax, eax
0x180007ce6  js      short loc_180007D2E
0x180007ce8  mov     rcx, [rbp+4Fh+var_78]
0x180007cec  test    rcx, rcx
0x180007cef  jz      short loc_180007D29
0x180007cf1  mov     rax, [rcx]
0x180007cf4  lea     r9, [rbp+4Fh+var_A8]
0x180007cf8  lea     r8, [rbp+4Fh+var_50]
0x180007cfc  xor     edx, edx
0x180007cfe  mov     rax, [rax+18h]
0x180007d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d07  cmp     eax, 80004002h
0x180007d0c  jz      short loc_180007D20
0x180007d0e  cmp     eax, 80040111h
0x180007d13  jz      short loc_180007D20
0x180007d15  xor     r9d, r9d
0x180007d18  test    eax, eax
0x180007d1a  jns     short loc_180007D2E
0x180007d1c  mov     edi, eax
0x180007d1e  jmp     short loc_180007D2E
0x180007d20  xor     r9d, r9d
0x180007d23  mov     [rbp+4Fh+var_A8], r9
0x180007d27  jmp     short loc_180007D2E
0x180007d29  mov     edi, 80004005h
0x180007d2e  mov     rcx, [rbp+4Fh+var_78]
0x180007d32  test    rcx, rcx
0x180007d35  jz      short loc_180007D4A
0x180007d37  mov     rax, [rcx]
0x180007d3a  mov     rax, [rax+10h]
0x180007d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d43  xor     r9d, r9d
0x180007d46  mov     [rbp+4Fh+var_78], r9
0x180007d4a  test    edi, edi
0x180007d4c  js      loc_180007E8E
0x180007d52  mov     rcx, [rbp+4Fh+var_A8]
0x180007d56  test    rcx, rcx
0x180007d59  jz      short loc_180007DD3
0x180007d5b  mov     rdx, [rbp+4Fh+phPrinter]
0x180007d5f  lea     r8, [rbp+4Fh+pv]
0x180007d63  mov     [rbp+4Fh+pv], r9
0x180007d67  mov     [rbp+4Fh+var_B0], r9d
0x180007d6b  lea     r9, [rbp+4Fh+var_B0]
0x180007d6f  mov     rax, [rcx]
0x180007d72  mov     rax, [rax+18h]
0x180007d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7b  mov     edi, eax
0x180007d7d  test    eax, eax
0x180007d7f  js      short loc_180007DB2
0x180007d81  mov     r9d, [rbp+4Fh+var_B0]
0x180007d85  xor     ecx, ecx
0x180007d87  xor     r8d, r8d
0x180007d8a  test    r9d, r9d
0x180007d8d  jle     short loc_180007DB2
0x180007d8f  mov     rdx, [rbp+4Fh+pv]
0x180007d93  lea     r10d, [rcx+1]
0x180007d97  test    ecx, ecx
0x180007d99  jnz     short loc_180007DBF
0x180007d9b  movsxd  rax, r8d
0x180007d9e  cmp     [rdx+rax*4], r10d
0x180007da2  cmovz   ecx, r10d
0x180007da6  add     r8d, r10d
0x180007da9  cmp     r8d, r9d
0x180007dac  jl      short loc_180007D97
0x180007dae  test    ecx, ecx
0x180007db0  jnz     short loc_180007DBF
0x180007db2  lea     rcx, [rbp+4Fh+var_A8]
0x180007db6  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180007dbb  mov     rdx, [rbp+4Fh+pv]
0x180007dbf  mov     rcx, rdx; pv
0x180007dc2  call    cs:__imp_CoTaskMemFree
0x180007dc8  xor     r9d, r9d
0x180007dcb  test    edi, edi
0x180007dcd  js      loc_180007E8E
0x180007dd3  mov     rcx, [rbp+4Fh+var_A8]
0x180007dd7  test    rcx, rcx
0x180007dda  jz      loc_180007F5D
0x180007de0  mov     [rbp+4Fh+pv], r9
0x180007de4  lea     rdx, [rbp+4Fh+pv]
0x180007de8  mov     qword ptr [rsp+100h+var_D0], rdx
0x180007ded  mov     r8d, 1
0x180007df3  mov     [rbp+4Fh+var_B0], r9d
0x180007df7  lea     rdx, [rbp+4Fh+var_B0]
0x180007dfb  mov     rax, [rcx]
0x180007dfe  lea     r9, [rbp+4Fh+var_90]
0x180007e02  mov     [rsp+100h+var_D8], rdx
0x180007e07  lea     rdx, [rbp+4Fh+var_80]
0x180007e0b  mov     [rsp+100h+var_E0], rdx
0x180007e10  mov     rdx, [rbp+4Fh+phPrinter]
0x180007e14  mov     rax, [rax+20h]
0x180007e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1d  mov     rcx, [rbp+4Fh+pv]
0x180007e21  xor     r9d, r9d
0x180007e24  mov     edi, eax
0x180007e26  test    rcx, rcx
0x180007e29  jz      short loc_180007E6D
0x180007e2b  mov     edx, [rbp+4Fh+var_B0]
0x180007e2e  mov     r15d, r9d
0x180007e31  test    edx, edx
0x180007e33  jle     short loc_180007E5C
0x180007e35  movsxd  rax, r15d
0x180007e38  mov     r8, [rcx+rax*8]
0x180007e3c  test    r8, r8
0x180007e3f  jz      short loc_180007E54
0x180007e41  mov     rcx, r8; bstrString
0x180007e44  call    cs:__imp_SysFreeString
0x180007e4a  mov     rcx, [rbp+4Fh+pv]; pv
0x180007e4e  xor     r9d, r9d
0x180007e51  mov     edx, [rbp+4Fh+var_B0]
0x180007e54  inc     r15d
0x180007e57  cmp     r15d, edx
0x180007e5a  jl      short loc_180007E35
0x180007e5c  call    cs:__imp_CoTaskMemFree
0x180007e62  mov     rcx, [rbp+4Fh+pv]
0x180007e66  xor     r9d, r9d
0x180007e69  mov     r15, [rbp+4Fh+arg_20]
0x180007e6d  cmp     [rbp+4Fh+var_90], 1
0x180007e71  ja      loc_180007F4A
0x180007e77  cmp     [rbp+4Fh+var_B0], r9d
0x180007e7b  jz      short loc_180007E86
0x180007e7d  test    rcx, rcx
0x180007e80  jz      loc_180007F4A
0x180007e86  test    edi, edi
0x180007e88  jns     loc_180007F5D
0x180007e8e  xor     r12d, r12d
0x180007e91  mov     rcx, [rbp+4Fh+var_A8]
0x180007e95  mov     dword ptr [r15], 1
0x180007e9c  test    rcx, rcx
0x180007e9f  jz      short loc_180007EB1
0x180007ea1  mov     rax, [rcx]
0x180007ea4  mov     rax, [rax+10h]
0x180007ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ead  mov     [rbp+4Fh+var_A8], r12
0x180007eb1  mov     rcx, [rbp+4Fh+phPrinter]; hPrinter
0x180007eb5  test    rcx, rcx
0x180007eb8  jz      short loc_180007EC0
0x180007eba  call    cs:__imp_ClosePrinter
0x180007ec0  test    rsi, rsi
0x180007ec3  jz      short loc_180007ECE
0x180007ec5  mov     rcx, rsi; hLibModule
0x180007ec8  call    cs:__imp_FreeLibrary
0x180007ece  test    r13, r13
0x180007ed1  jz      short loc_180007EE7
0x180007ed3  call    cs:__imp_GetProcessHeap
0x180007ed9  mov     r8, r13; lpMem
0x180007edc  xor     edx, edx; dwFlags
0x180007ede  mov     rcx, rax; hHeap
0x180007ee1  call    cs:__imp_HeapFree
0x180007ee7  test    edi, edi
0x180007ee9  js      short loc_180007F00
0x180007eeb  mov     rax, r12
0x180007eee  test    r14, r14
0x180007ef1  jz      short loc_180007EF9
0x180007ef3  mov     rax, r14
0x180007ef6  mov     r14, r12
0x180007ef9  mov     rcx, [rbp+4Fh+arg_18]
0x180007efd  mov     [rcx], rax
0x180007f00  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180007f04  test    rcx, rcx
0x180007f07  jz      short loc_180007F13
0x180007f09  call    cs:__imp_SysFreeString
0x180007f0f  mov     [rbp+4Fh+bstrString], r12
0x180007f13  test    rbx, rbx
0x180007f16  jz      short loc_180007F21
0x180007f18  mov     rcx, rbx; bstrString
0x180007f1b  call    cs:__imp_SysFreeString
0x180007f21  test    r14, r14
0x180007f24  jz      short loc_180007F2E
0x180007f26  mov     rcx, r14; this
0x180007f29  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x180007f2e  mov     rcx, [rbp+4Fh+var_A8]
0x180007f32  test    rcx, rcx
0x180007f35  jz      short loc_180007F43
0x180007f37  mov     rax, [rcx]
0x180007f3a  mov     rax, [rax+10h]
0x180007f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f43  mov     eax, edi
0x180007f45  jmp     loc_180008063
0x180007f4a  lea     rcx, [rbp+4Fh+var_A8]
0x180007f4e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180007f53  mov     edi, 80040002h
0x180007f58  jmp     loc_180007E8E
0x180007f5d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007f61  inc     rdx; ui
0x180007f64  cmp     [r12+rdx*2], r9w
0x180007f69  jnz     short loc_180007F61
0x180007f6b  mov     rcx, r12; strIn
0x180007f6e  call    cs:__imp_SysAllocStringLen
0x180007f74  xor     r12d, r12d
0x180007f77  mov     rbx, rax
0x180007f7a  test    rax, rax
0x180007f7d  jz      loc_180008048
0x180007f83  mov     rcx, [rbp+4Fh+var_A8]; void *
0x180007f87  test    rcx, rcx
0x180007f8a  jz      short loc_180007FAE
0x180007f8c  mov     rax, [rcx]
0x180007f8f  lea     rdx, [rbp+4Fh+bstrString]
0x180007f93  mov     rax, [rax+28h]
0x180007f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9c  test    eax, eax
0x180007f9e  jns     short loc_180007FAE
0x180007fa0  cmp     eax, 80004001h
0x180007fa5  jz      short loc_180007FAE
0x180007fa7  mov     edi, eax
0x180007fa9  jmp     loc_180007E91
0x180007fae  cmp     [rbp+4Fh+bstrString], r12
0x180007fb2  jnz     short loc_180007FCA
0x180007fb4  lea     r8, [rbp+4Fh+bstrString]; unsigned __int16 **
0x180007fb8  mov     rdx, r13; struct _DRIVER_INFO_3W *
0x180007fbb  call    ?CreateDriverUniqueUri@@YAJPEAXPEAU_DRIVER_INFO_3W@@PEAPEAG@Z; CreateDriverUniqueUri(void *,_DRIVER_INFO_3W *,ushort * *)
0x180007fc0  mov     edi, eax
0x180007fc2  test    eax, eax
  ... truncated ...
```
