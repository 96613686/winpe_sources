# CTSClientPrintDriver::InitializePrinter(ulong)

- ea: `0x180435df0`
- end: `0x18043647e`
- name: `?InitializePrinter@CTSClientPrintDriver@@UEAAJK@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CTSClientPrintDriver *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180085e50`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x180174b04`
- `0x180435df0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180435ea3`
- `KERNEL32!GetLastError` at `0x180435f3b`
- `KERNEL32!GetLastError` at `0x180435f4b`
- `KERNEL32!GetLastError` at `0x18043602e`
- `KERNEL32!GetLastError` at `0x1804360b3`
- `KERNEL32!GetLastError` at `0x1804360b9`
- `KERNEL32!GetLastError` at `0x180436145`
- `KERNEL32!GetLastError` at `0x1804361c2`
- `KERNEL32!GetLastError` at `0x180436326`
- `KERNEL32!GetLastError` at `0x18043638e`
- `KERNEL32!GetLastError` at `0x1804363f6`
- `KERNEL32!GetLastError` at `0x180436422`
- `KERNEL32!GetLastError` at `0x180435ea3`
- `KERNEL32!GetLastError` at `0x180435f3b`
- `KERNEL32!GetLastError` at `0x180435f4b`
- `KERNEL32!GetLastError` at `0x18043602e`
- `KERNEL32!GetLastError` at `0x1804360b3`
- `KERNEL32!GetLastError` at `0x1804360b9`
- `KERNEL32!GetLastError` at `0x180436145`
- `KERNEL32!GetLastError` at `0x1804361c2`
- `KERNEL32!GetLastError` at `0x180436326`
- `KERNEL32!GetLastError` at `0x18043638e`
- `KERNEL32!GetLastError` at `0x1804363f6`
- `KERNEL32!GetLastError` at `0x180436422`
- `KERNEL32!LoadLibraryExW` at `0x1804361a5`
- `KERNEL32!LoadLibraryExW` at `0x1804362dc`
- `KERNEL32!LoadLibraryExW` at `0x1804361a5`
- `KERNEL32!LoadLibraryExW` at `0x1804362dc`
- `KERNEL32!GetProcAddress` at `0x1804362c0`
- `KERNEL32!GetProcAddress` at `0x1804362fc`
- `KERNEL32!GetProcAddress` at `0x180436364`
- `KERNEL32!GetProcAddress` at `0x1804363cc`
- `KERNEL32!GetProcAddress` at `0x1804362c0`
- `KERNEL32!GetProcAddress` at `0x1804362fc`
- `KERNEL32!GetProcAddress` at `0x180436364`
- `KERNEL32!GetProcAddress` at `0x1804363cc`
- `WINSPOOL!OpenPrinterW` at `0x180435e99`
- `WINSPOOL!OpenPrinterW` at `0x180435e99`
- `WINSPOOL!GetPrinterDriverW` at `0x1804360ad`
- `WINSPOOL!GetPrinterDriverW` at `0x18043613b`
- `WINSPOOL!GetPrinterDriverW` at `0x1804360ad`
- `WINSPOOL!GetPrinterDriverW` at `0x18043613b`
- `WINSPOOL!ClosePrinter` at `0x18043628e`
- `WINSPOOL!ClosePrinter` at `0x18043628e`
- `WINSPOOL!GetPrinterW` at `0x180435f35`
- `WINSPOOL!GetPrinterW` at `0x180436024`
- `WINSPOOL!GetPrinterW` at `0x180435f35`
- `WINSPOOL!GetPrinterW` at `0x180436024`

## string_xrefs

- `0x180436242`: `LoadLibraryEx`

## pseudocode

```c
__int64 __fastcall CTSClientPrintDriver::InitializePrinter(CTSClientPrintDriver *this, __int64 a2)
{
  int v3; // ebx
  void *v4; // r13
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE *v7; // rsi
  WCHAR *v8; // rcx
  unsigned int v9; // eax
  bool v10; // sf
  HANDLE v11; // rcx
  signed int v12; // eax
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  BYTE *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  signed int v20; // eax
  HMODULE Library; // rax
  signed int v22; // eax
  HKEY v23; // rax
  __int64 v24; // rbx
  void *v25; // rcx
  HMODULE v26; // rax
  FARPROC ProcAddress; // rax
  DWORD v28; // ebx
  unsigned int v29; // eax
  FARPROC v30; // rax
  DWORD v31; // ebx
  unsigned int v32; // eax
  FARPROC v33; // rax
  DWORD v34; // ebx
  unsigned int v35; // eax
  __int64 v36; // rdx
  LPDWORD v38; // [rsp+28h] [rbp-30h]
  signed int v39; // [rsp+28h] [rbp-30h]
  LPDWORD v40; // [rsp+28h] [rbp-30h]
  DWORD cbBuf; // [rsp+60h] [rbp+8h] BYREF

  v3 = a2;
  v4 = 0;
  LastError = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 8) + 24LL))(
                *((_QWORD *)this + 8),
                a2,
                (char *)this + 88);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v39 = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"_ptrCollection->GetPrinterName",
        v39);
    }
    v7 = (HANDLE *)((char *)this + 96);
    goto LABEL_64;
  }
  v8 = (WCHAR *)*((_QWORD *)this + 11);
  v7 = (HANDLE *)((char *)this + 96);
  *((_DWORD *)this + 28) = v3;
  if ( !OpenPrinterW(v8, (LPHANDLE)this + 12, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids, v9, LastError);
    }
    v10 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_15;
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
    v10 = LastError < 0;
LABEL_15:
    if ( !v10 )
      LastError = -2147467259;
    goto LABEL_64;
  }
  v11 = *v7;
  cbBuf = 0;
  GetPrinterW(v11, 2u, 0, 0, &cbBuf);
  if ( GetLastError() == 122 )
    goto LABEL_25;
  v12 = GetLastError();
  LastError = v12;
  if ( v12 > 0 )
    LastError = (unsigned __int16)v12 | 0x80070000;
  if ( LastError >= 0 )
  {
LABEL_25:
    v16 = (BYTE *)operator new(cbBuf);
    *((_QWORD *)this + 13) = v16;
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v17,
          (__int64)"BYTE[]");
      }
      LastError = -2147024882;
      goto LABEL_64;
    }
    if ( !GetPrinterW(*v7, 2u, v16, cbBuf, &cbBuf) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v18,
          LastError);
      }
      v10 = LastError < 0;
      if ( LastError <= 0 )
        goto LABEL_15;
      LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
    GetPrinterDriverW(*v7, 0, 3u, 0, 0, &cbBuf);
    GetLastError();
    if ( GetLastError() != 122 )
    {
      LastError = -2147418113;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v40) = -2147418113;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v19,
          (__int64)"GetPrinterDriver",
          v40);
      }
      goto LABEL_64;
    }
    v4 = operator new(cbBuf);
    if ( !GetPrinterDriverW(*v7, 0, 3u, (LPBYTE)v4, cbBuf, &cbBuf) )
    {
      v20 = GetLastError();
      LastError = v20;
      if ( v20 > 0 )
        LastError = (unsigned __int16)v20 | 0x80070000;
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_64;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 20;
        v15 = "GetPrinterDriver";
        goto LABEL_63;
      }
    }
    Library = LoadLibraryExW(*((LPCWSTR *)v4 + 5), 0, 8u);
    *((_QWORD *)this + 19) = Library;
    if ( !Library )
    {
      v22 = GetLastError();
      LastError = v22;
      if ( v22 > 0 )
        LastError = (unsigned __int16)v22 | 0x80070000;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = *((_QWORD *)v4 + 5);
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, LastError);
        v23 = WPP_GLOBAL_Control;
      }
      if ( LastError < 0 )
      {
        if ( v23 == (HKEY)&WPP_GLOBAL_Control || ((_BYTE)v23[7] & 8) == 0 || *((_BYTE *)v23 + 25) < 2u )
          goto LABEL_64;
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 22;
        v15 = "LoadLibraryEx";
        goto LABEL_63;
      }
    }
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() && !*((_DWORD *)this + 50) )
      *((_QWORD *)this + 20) = GetProcAddress(*((HMODULE *)this + 19), "MxdcGetPDEVAdjustment");
    v26 = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
    *((_QWORD *)this + 21) = v26;
    if ( v26 )
    {
      ProcAddress = GetProcAddress(v26, "PrinterProperties");
      *((_QWORD *)this + 22) = ProcAddress;
      if ( !ProcAddress
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = GetLastError();
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids, v29, v28);
      }
      v30 = GetProcAddress(*((HMODULE *)this + 21), "GetFormW");
      *((_QWORD *)this + 23) = v30;
      if ( !v30
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = GetLastError();
        v32 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids, v32, v31);
      }
      v33 = GetProcAddress(*((HMODULE *)this + 21), "EnumFormsW");
      *((_QWORD *)this + 24) = v33;
      if ( v33
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_92;
      }
      v34 = GetLastError();
      v35 = RdpWppGetCurrentThreadActivityIdPrefix();
      v36 = 25;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_92;
      }
      v34 = GetLastError();
      v35 = RdpWppGetCurrentThreadActivityIdPrefix();
      v36 = 26;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids, v35, v34);
LABEL_92:
    *((_DWORD *)this + 11) |= 2u;
    LastError = 0;
    goto LABEL_93;
  }
  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_64;
  }
  v13 = RdpWppGetCurrentThreadActivityIdPrefix();
  v14 = 16;
  v15 = "GetPrinter";
LABEL_63:
  LODWORD(v38) = LastError;
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v14,
    (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
    v13,
    (__int64)v15,
    v38);
LABEL_64:
  v25 = (void *)*((_QWORD *)this + 13);
  if ( v25 )
  {
    operator delete(v25);
    *((_QWORD *)this + 13) = 0;
  }
  if ( *v7 )
  {
    ClosePrinter(*v7);
    *v7 = 0;
  }
LABEL_93:
  if ( v4 )
    operator delete(v4);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180435df0  mov     [rsp+arg_8], rbx
0x180435df5  mov     [rsp+arg_10], rbp
0x180435dfa  push    rsi
0x180435dfb  push    rdi
0x180435dfc  push    r13
0x180435dfe  push    r14
0x180435e00  push    r15
0x180435e02  sub     rsp, 30h
0x180435e06  mov     r15, rcx
0x180435e09  mov     ebx, edx
0x180435e0b  mov     rcx, [rcx+40h]
0x180435e0f  xor     r13d, r13d
0x180435e12  lea     r8, [r15+58h]
0x180435e16  mov     rax, [rcx]
0x180435e19  mov     rax, [rax+18h]
0x180435e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180435e22  mov     edi, eax
0x180435e24  test    eax, eax
0x180435e26  jns     short loc_180435E87
0x180435e28  mov     rax, cs:WPP_GLOBAL_Control
0x180435e2f  lea     rbp, WPP_GLOBAL_Control
0x180435e36  cmp     rax, rbp
0x180435e39  jz      short loc_180435E7E
0x180435e3b  test    byte ptr [rax+1Ch], 8
0x180435e3f  jz      short loc_180435E7E
0x180435e41  lea     r14d, [r13+2]
0x180435e45  cmp     [rax+19h], r14b
0x180435e49  jb      short loc_180435E7E
0x180435e4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180435e50  lea     rcx, aPtrcollectionG; "_ptrCollection->GetPrinterName"
0x180435e57  mov     dword ptr [rsp+58h+var_30], edi
0x180435e5b  mov     [rsp+58h+pcbNeeded], rcx
0x180435e60  lea     edx, [r13+0Eh]
0x180435e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180435e6b  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180435e72  mov     r9d, eax
0x180435e75  mov     rcx, [rcx+10h]
0x180435e79  call    WPP_SF_DsD
0x180435e7e  lea     rsi, [r15+60h]
0x180435e82  jmp     loc_18043626C
0x180435e87  mov     rcx, [r15+58h]; pPrinterName
0x180435e8b  lea     rsi, [r15+60h]
0x180435e8f  mov     rdx, rsi; phPrinter
0x180435e92  mov     [r15+70h], ebx
0x180435e96  xor     r8d, r8d; pDefault
0x180435e99  call    cs:__imp_OpenPrinterW
0x180435e9f  test    eax, eax
0x180435ea1  jnz     short loc_180435F16
0x180435ea3  call    cs:__imp_GetLastError
0x180435ea9  mov     edi, eax
0x180435eab  mov     rax, cs:WPP_GLOBAL_Control
0x180435eb2  lea     rbp, WPP_GLOBAL_Control
0x180435eb9  cmp     rax, rbp
0x180435ebc  jz      short loc_180435EF7
0x180435ebe  test    byte ptr [rax+1Ch], 8
0x180435ec2  jz      short loc_180435EF7
0x180435ec4  mov     r14d, 2
0x180435eca  cmp     [rax+19h], r14b
0x180435ece  jb      short loc_180435EF7
0x180435ed0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180435ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180435edc  lea     edx, [r14+0Dh]
0x180435ee0  mov     r9d, eax
0x180435ee3  mov     dword ptr [rsp+58h+pcbNeeded], edi
0x180435ee7  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180435eee  mov     rcx, [rcx+10h]
0x180435ef2  call    WPP_SF_Dd
0x180435ef7  test    edi, edi
0x180435ef9  jle     short loc_180435F06
0x180435efb  movzx   edi, di
0x180435efe  or      edi, 80070000h
0x180435f04  test    edi, edi
0x180435f06  js      loc_18043626C
0x180435f0c  mov     edi, 80004005h
0x180435f11  jmp     loc_18043626C
0x180435f16  mov     rcx, [rsi]; hPrinter
0x180435f19  lea     rax, [rsp+58h+cbBuf]
0x180435f1e  xor     r9d, r9d; cbBuf
0x180435f21  mov     [rsp+58h+cbBuf], r13d
0x180435f26  xor     r8d, r8d; pPrinter
0x180435f29  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180435f2e  lea     r14d, [r9+2]
0x180435f32  mov     edx, r14d; Level
0x180435f35  call    cs:__imp_GetPrinterW
0x180435f3b  call    cs:__imp_GetLastError
0x180435f41  mov     ebx, 80070000h
0x180435f46  cmp     eax, 7Ah ; 'z'
0x180435f49  jz      short loc_180435FA1
0x180435f4b  call    cs:__imp_GetLastError
0x180435f51  mov     edi, eax
0x180435f53  test    eax, eax
0x180435f55  jle     short loc_180435F5C
0x180435f57  movzx   edi, ax
0x180435f5a  or      edi, ebx
0x180435f5c  test    edi, edi
0x180435f5e  jns     short loc_180435FA1
0x180435f60  mov     rax, cs:WPP_GLOBAL_Control
0x180435f67  lea     rbp, WPP_GLOBAL_Control
0x180435f6e  cmp     rax, rbp
0x180435f71  jz      loc_18043626C
0x180435f77  test    byte ptr [rax+1Ch], 8
0x180435f7b  jz      loc_18043626C
0x180435f81  cmp     [rax+19h], r14b
0x180435f85  jb      loc_18043626C
0x180435f8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180435f90  mov     edx, 10h
0x180435f95  lea     rcx, aGetprinter; "GetPrinter"
0x180435f9c  jmp     loc_180436249
0x180435fa1  mov     ecx, [rsp+58h+cbBuf]; Size
0x180435fa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180435faa  mov     [r15+68h], rax
0x180435fae  test    rax, rax
0x180435fb1  jnz     short loc_18043600C
0x180435fb3  mov     rax, cs:WPP_GLOBAL_Control
0x180435fba  lea     rbp, WPP_GLOBAL_Control
0x180435fc1  cmp     rax, rbp
0x180435fc4  jz      short loc_180436002
0x180435fc6  test    byte ptr [rax+1Ch], 8
0x180435fca  jz      short loc_180436002
0x180435fcc  cmp     [rax+19h], r14b
0x180435fd0  jb      short loc_180436002
0x180435fd2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180435fd7  lea     rcx, aByte_1; "BYTE[]"
0x180435fde  mov     edx, 11h
0x180435fe3  mov     [rsp+58h+pcbNeeded], rcx
0x180435fe8  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180435fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180435ff6  mov     r9d, eax
0x180435ff9  mov     rcx, [rcx+10h]
0x180435ffd  call    WPP_SF_Ds
0x180436002  mov     edi, 8007000Eh
0x180436007  jmp     loc_18043626C
0x18043600c  mov     r9d, [rsp+58h+cbBuf]; cbBuf
0x180436011  lea     rcx, [rsp+58h+cbBuf]
0x180436016  mov     [rsp+58h+pcbNeeded], rcx; pcbNeeded
0x18043601b  mov     r8, rax; pPrinter
0x18043601e  mov     rcx, [rsi]; hPrinter
0x180436021  mov     edx, r14d; Level
0x180436024  call    cs:__imp_GetPrinterW
0x18043602a  test    eax, eax
0x18043602c  jnz     short loc_18043608F
0x18043602e  call    cs:__imp_GetLastError
0x180436034  mov     edi, eax
0x180436036  mov     rax, cs:WPP_GLOBAL_Control
0x18043603d  lea     rbp, WPP_GLOBAL_Control
0x180436044  cmp     rax, rbp
0x180436047  jz      short loc_18043607D
0x180436049  test    byte ptr [rax+1Ch], 8
0x18043604d  jz      short loc_18043607D
0x18043604f  cmp     [rax+19h], r14b
0x180436053  jb      short loc_18043607D
0x180436055  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18043605a  mov     rcx, cs:WPP_GLOBAL_Control
0x180436061  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436068  mov     edx, 12h
0x18043606d  mov     dword ptr [rsp+58h+pcbNeeded], edi
0x180436071  mov     r9d, eax
0x180436074  mov     rcx, [rcx+10h]
0x180436078  call    WPP_SF_Dd
0x18043607d  test    edi, edi
0x18043607f  jle     loc_180435F06
0x180436085  movzx   edi, di
0x180436088  or      edi, ebx
0x18043608a  jmp     loc_180435F04
0x18043608f  mov     rcx, [rsi]; hPrinter
0x180436092  lea     rax, [rsp+58h+cbBuf]
0x180436097  xor     r9d, r9d; pDriverInfo
0x18043609a  mov     [rsp+58h+var_30], rax; pcbNeeded
0x18043609f  xor     edx, edx; pEnvironment
0x1804360a1  mov     dword ptr [rsp+58h+pcbNeeded], r13d; cbBuf
0x1804360a6  lea     edi, [r9+3]
0x1804360aa  mov     r8d, edi; Level
0x1804360ad  call    cs:__imp_GetPrinterDriverW
0x1804360b3  call    cs:__imp_GetLastError
0x1804360b9  call    cs:__imp_GetLastError
0x1804360bf  cmp     eax, 7Ah ; 'z'
0x1804360c2  jz      short loc_180436112
0x1804360c4  mov     edi, 8000FFFFh
0x1804360c9  mov     rax, cs:WPP_GLOBAL_Control
0x1804360d0  lea     rbp, WPP_GLOBAL_Control
0x1804360d7  cmp     rax, rbp
0x1804360da  jz      loc_18043626C
0x1804360e0  test    byte ptr [rax+1Ch], 8
0x1804360e4  jz      loc_18043626C
0x1804360ea  cmp     [rax+19h], r14b
0x1804360ee  jb      loc_18043626C
0x1804360f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804360f9  mov     edx, 13h
0x1804360fe  mov     dword ptr [rsp+58h+var_30], 8000FFFFh
0x180436106  lea     rcx, aGetprinterdriv_0; "GetPrinterDriver"
0x18043610d  jmp     loc_18043624D
0x180436112  mov     ecx, [rsp+58h+cbBuf]; Size
0x180436116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18043611b  mov     ecx, [rsp+58h+cbBuf]
0x18043611f  mov     r13, rax
0x180436122  lea     rax, [rsp+58h+cbBuf]
0x180436127  mov     r9, r13; pDriverInfo
0x18043612a  mov     [rsp+58h+var_30], rax; pcbNeeded
0x18043612f  mov     r8d, edi; Level
0x180436132  mov     dword ptr [rsp+58h+pcbNeeded], ecx; cbBuf
0x180436136  xor     edx, edx; pEnvironment
0x180436138  mov     rcx, [rsi]; hPrinter
0x18043613b  call    cs:__imp_GetPrinterDriverW
0x180436141  test    eax, eax
0x180436143  jnz     short loc_18043619B
0x180436145  call    cs:__imp_GetLastError
0x18043614b  mov     edi, eax
0x18043614d  test    eax, eax
0x18043614f  jle     short loc_180436156
0x180436151  movzx   edi, ax
0x180436154  or      edi, ebx
0x180436156  test    edi, edi
0x180436158  jns     short loc_18043619B
0x18043615a  mov     rax, cs:WPP_GLOBAL_Control
0x180436161  lea     rbp, WPP_GLOBAL_Control
0x180436168  cmp     rax, rbp
0x18043616b  jz      loc_18043626C
0x180436171  test    byte ptr [rax+1Ch], 8
0x180436175  jz      loc_18043626C
0x18043617b  cmp     [rax+19h], r14b
0x18043617f  jb      loc_18043626C
0x180436185  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18043618a  mov     edx, 14h
0x18043618f  lea     rcx, aGetprinterdriv_0; "GetPrinterDriver"
0x180436196  jmp     loc_180436249
0x18043619b  mov     rcx, [r13+28h]; lpLibFileName
0x18043619f  xor     edx, edx; hFile
0x1804361a1  lea     r8d, [rdx+8]; dwFlags
0x1804361a5  call    cs:__imp_LoadLibraryExW
0x1804361ab  mov     [r15+98h], rax
0x1804361b2  lea     rbp, WPP_GLOBAL_Control
0x1804361b9  test    rax, rax
0x1804361bc  jnz     loc_1804362A0
0x1804361c2  call    cs:__imp_GetLastError
0x1804361c8  mov     edi, eax
0x1804361ca  test    eax, eax
0x1804361cc  jle     short loc_1804361D3
0x1804361ce  movzx   edi, ax
0x1804361d1  or      edi, ebx
0x1804361d3  mov     rax, cs:WPP_GLOBAL_Control
0x1804361da  cmp     rax, rbp
0x1804361dd  jz      short loc_180436223
0x1804361df  test    byte ptr [rax+1Ch], 1
0x1804361e3  jz      short loc_180436223
0x1804361e5  cmp     [rax+19h], r14b
0x1804361e9  jb      short loc_180436223
0x1804361eb  mov     rbx, [r13+28h]
0x1804361ef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804361f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1804361fb  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436202  mov     edx, 15h
0x180436207  mov     dword ptr [rsp+58h+var_30], edi; char
0x18043620b  mov     r9d, eax
0x18043620e  mov     [rsp+58h+pcbNeeded], rbx; __int64
0x180436213  mov     rcx, [rcx+10h]; LoggerHandle
0x180436217  call    WPP_SF_DSd
0x18043621c  mov     rax, cs:WPP_GLOBAL_Control
0x180436223  test    edi, edi
0x180436225  jns     short loc_1804362A0
0x180436227  cmp     rax, rbp
0x18043622a  jz      short loc_18043626C
0x18043622c  test    byte ptr [rax+1Ch], 8
0x180436230  jz      short loc_18043626C
0x180436232  cmp     [rax+19h], r14b
0x180436236  jb      short loc_18043626C
0x180436238  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18043623d  mov     edx, 16h
0x180436242  lea     rcx, aLoadlibraryex; "LoadLibraryEx"
0x180436249  mov     dword ptr [rsp+58h+var_30], edi
0x18043624d  mov     [rsp+58h+pcbNeeded], rcx
0x180436252  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436259  mov     rcx, cs:WPP_GLOBAL_Control
0x180436260  mov     r9d, eax
0x180436263  mov     rcx, [rcx+10h]
0x180436267  call    WPP_SF_DsD
0x18043626c  mov     rcx, [r15+68h]; Block
0x180436270  test    rcx, rcx
0x180436273  jz      short loc_180436282
0x180436275  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18043627a  mov     qword ptr [r15+68h], 0
0x180436282  mov     rcx, [rsi]; hPrinter
0x180436285  test    rcx, rcx
0x180436288  jz      loc_180436458
0x18043628e  call    cs:__imp_ClosePrinter
0x180436294  mov     qword ptr [rsi], 0
0x18043629b  jmp     loc_180436458
0x1804362a0  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1804362a5  test    eax, eax
0x1804362a7  jnz     short loc_1804362CD
0x1804362a9  cmp     [r15+0C8h], eax
0x1804362b0  jnz     short loc_1804362CD
0x1804362b2  mov     rcx, [r15+98h]; hModule
0x1804362b9  lea     rdx, aMxdcgetpdevadj; "MxdcGetPDEVAdjustment"
0x1804362c0  call    cs:__imp_GetProcAddress
0x1804362c6  mov     [r15+0A0h], rax
0x1804362cd  xor     edx, edx; hFile
0x1804362cf  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1804362d6  mov     r8d, 800h; dwFlags
0x1804362dc  call    cs:__imp_LoadLibraryExW
0x1804362e2  mov     [r15+0A8h], rax
  ... truncated ...
```
