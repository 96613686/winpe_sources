# NPackageInstallLocalspl::TLinkedCoreDriver::TLinkedCoreDriver(void *,ushort const *,NPackageInstallLocalspl::TLinkedDriverEnvironment *)

- ea: `0x1800168b4`
- end: `0x180016d41`
- name: `??0TLinkedCoreDriver@NPackageInstallLocalspl@@QEAA@PEAXPEBGPEAVTLinkedDriverEnvironment@1@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(NPackageInstallLocalspl::TLinkedCoreDriver *__hidden this, void *, LPCOLESTR lpsz, struct NPackageInstallLocalspl::TLinkedDriverEnvironment *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800acd3c`

## callees

- `0x1800168b4`
- `0x1800170a0`
- `0x180017ee0`
- `0x180018030`
- `0x180028ec4`
- `0x180031270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cc3`
- `SPOOLSS!DllFreeSplMem` at `0x180016d1a`
- `SPOOLSS!DllFreeSplMem` at `0x180016d28`
- `SPOOLSS!DllFreeSplMem` at `0x180016d36`
- `SPOOLSS!DllFreeSplMem` at `0x180016d1a`
- `SPOOLSS!DllFreeSplMem` at `0x180016d28`
- `SPOOLSS!DllFreeSplMem` at `0x180016d36`
- `SPOOLSS!DllAllocSplMem` at `0x1800169d4`
- `SPOOLSS!DllAllocSplMem` at `0x180016a75`
- `SPOOLSS!DllAllocSplMem` at `0x180016b49`
- `SPOOLSS!DllAllocSplMem` at `0x1800169d4`
- `SPOOLSS!DllAllocSplMem` at `0x180016a75`
- `SPOOLSS!DllAllocSplMem` at `0x180016b49`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180016c29`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180016c29`

## string_xrefs

- `0x1800169a2`: `InfPath`
- `0x1800169fe`: `InfPath`

## pseudocode

```c
NPackageInstallLocalspl::TLinkedCoreDriver *__fastcall NPackageInstallLocalspl::TLinkedCoreDriver::TLinkedCoreDriver(
        NPackageInstallLocalspl::TLinkedCoreDriver *this,
        void *a2,
        LPCOLESTR lpsz,
        struct NPackageInstallLocalspl::TLinkedDriverEnvironment *a4)
{
  const OLECHAR *v6; // r15
  int IsValid; // eax
  unsigned __int16 *v8; // rdx
  int v9; // r8d
  __int64 v10; // r9
  int v11; // eax
  struct _INISPOOLER *v12; // r12
  const unsigned __int16 *v13; // rdi
  unsigned __int8 *v14; // rsi
  unsigned __int8 *v15; // r14
  signed int LastError; // eax
  unsigned __int8 *v17; // r15
  signed int v18; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  HRESULT v23; // eax
  unsigned int v24; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v26; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned int v28[4]; // [rsp+40h] [rbp-10h] BYREF
  int v29; // [rsp+90h] [rbp+40h] BYREF
  LPCOLESTR v30; // [rsp+A0h] [rbp+50h]
  unsigned int v31; // [rsp+A8h] [rbp+58h] BYREF

  v30 = lpsz;
  *((_DWORD *)this + 2) = 1802398836;
  *(_QWORD *)this = &NPackageInstallLocalspl::TLinkedCoreDriver::`vftable';
  *((_QWORD *)this + 2) = this;
  *((_QWORD *)this + 3) = this;
  *((_DWORD *)this + 8) = 1349676867;
  *((_QWORD *)this + 7) = &NCoreLibrary::TString::gszNullState;
  v6 = lpsz;
  *((_QWORD *)this + 10) = 0;
  v29 = 0;
  *((_DWORD *)this + 9) = a4 == 0 ? 0x80070057 : 0;
  if ( a4 )
  {
    *((_QWORD *)this + 10) = a4;
    IsValid = NCoreLibrary::TLink::IsValid(this);
    *((_DWORD *)this + 9) = IsValid;
    if ( IsValid >= 0 )
    {
      if ( a2 == (void *)-1LL || (v11 = (int)v8, !v6) )
        v11 = v9;
      *((_DWORD *)this + 9) = v11;
      if ( v11 >= 0 )
      {
        v12 = *(struct _INISPOOLER **)(*(_QWORD *)(v10 + 192) + 72LL);
        *((_DWORD *)this + 9) = v12 == 0 ? v9 : 0;
        if ( v12 )
        {
          v13 = v8;
          v31 = (unsigned int)v8;
          v14 = (unsigned __int8 *)v8;
          v24 = (unsigned int)v8;
          v15 = (unsigned __int8 *)v8;
          LastError = SplRegQueryValue(a2, L"InfPath", &v31, 0, &v24, v12);
          if ( !LastError )
          {
            if ( (v31 != 1 || v24 <= 2) && (v31 != 7 || v24 <= 4) )
            {
LABEL_30:
              LastError = 0;
              goto LABEL_31;
            }
            v17 = (unsigned __int8 *)DllAllocSplMem(v24);
            if ( v17 )
            {
              LastError = SplRegQueryValue(a2, L"InfPath", &v31, v17, &v24, v12);
              if ( !LastError )
              {
                if ( (v24 & 0xFFFFFFFE) != 0 )
                  v13 = (const unsigned __int16 *)v17;
                v6 = v30;
                goto LABEL_30;
              }
            }
            else
            {
              LastError = GetLastError();
            }
            v6 = v30;
          }
          v29 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            LastError = -2147467259;
          }
LABEL_31:
          *((_DWORD *)this + 9) = LastError;
          if ( LastError < 0 )
            goto LABEL_22;
          v25 = (unsigned int)v14;
          v27 = (unsigned int)v14;
          v20 = SplRegQueryValue(a2, L"DriverDate", &v25, 0, &v27, v12);
          if ( !v20 )
          {
            if ( (v25 != 1 || v27 <= 2) && (v25 != 7 || v27 <= 4) )
              goto LABEL_37;
            v14 = (unsigned __int8 *)DllAllocSplMem(v27);
            if ( v14 )
            {
              v20 = SplRegQueryValue(a2, L"DriverDate", &v25, v14, &v27, v12);
              if ( !v20 )
              {
LABEL_37:
                v20 = 0;
                goto LABEL_38;
              }
            }
            else
            {
              v20 = GetLastError();
            }
          }
          v29 = v20;
          if ( v20 )
          {
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
          }
          else
          {
            v20 = -2147467259;
          }
LABEL_38:
          *((_DWORD *)this + 9) = v20;
          if ( v20 >= 0 )
          {
            v26 = (unsigned int)v15;
            v28[0] = (unsigned int)v15;
            v18 = SplRegQueryValue(a2, L"DriverVersion", &v26, 0, v28, v12);
            if ( !v18 )
            {
              if ( (v26 != 1 || v28[0] <= 2) && (v26 != 7 || v28[0] <= 4) )
                goto LABEL_20;
              v15 = (unsigned __int8 *)DllAllocSplMem(v28[0]);
              if ( v15 )
              {
                v18 = SplRegQueryValue(a2, L"DriverVersion", &v26, v15, v28, v12);
                if ( !v18 )
                {
LABEL_20:
                  v18 = 0;
LABEL_21:
                  *((_DWORD *)this + 9) = v18;
                  if ( v18 >= 0 )
                  {
                    if ( (unsigned int)ConvertDriverDateToFILETIME(v14, (char *)this + 64, &v29) )
                    {
                      v21 = 0;
                    }
                    else
                    {
                      v21 = v29;
                      if ( v29 )
                      {
                        if ( v29 > 0 )
                          v21 = (unsigned __int16)v29 | 0x80070000;
                      }
                      else
                      {
                        v21 = -2147467259;
                      }
                    }
                    *((_DWORD *)this + 9) = v21;
                    if ( v21 >= 0 )
                    {
                      if ( (unsigned int)ConvertDriverVersionToDWORDLONG(v15, (char *)this + 72, &v29) )
                      {
                        v22 = 0;
                      }
                      else
                      {
                        v22 = v29;
                        if ( v29 )
                        {
                          if ( v29 > 0 )
                            v22 = (unsigned __int16)v29 | 0x80070000;
                        }
                        else
                        {
                          v22 = -2147467259;
                        }
                      }
                      *((_DWORD *)this + 9) = v22;
                      if ( v22 >= 0 )
                      {
                        v23 = IIDFromString(v6, (LPIID)((char *)this + 40));
                        *((_DWORD *)this + 9) = v23;
                        if ( v23 >= 0 )
                          *((_DWORD *)this + 9) = NCoreLibrary::TString::Update(
                                                    (NPackageInstallLocalspl::TLinkedCoreDriver *)((char *)this + 56),
                                                    v13);
                      }
                    }
                  }
                  goto LABEL_22;
                }
              }
              else
              {
                v18 = GetLastError();
              }
            }
            v29 = v18;
            if ( v18 )
            {
              if ( v18 > 0 )
                v18 = (unsigned __int16)v18 | 0x80070000;
            }
            else
            {
              v18 = -2147467259;
            }
            goto LABEL_21;
          }
LABEL_22:
          if ( v13 )
            DllFreeSplMem(v13);
          if ( v14 )
            DllFreeSplMem(v14);
          if ( v15 )
            DllFreeSplMem(v15);
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800168b4  mov     [rsp-38h+arg_8], rbx
0x1800168b9  mov     [rsp-38h+arg_10], r8
0x1800168be  push    rbp
0x1800168bf  push    rsi
0x1800168c0  push    rdi
0x1800168c1  push    r12
0x1800168c3  push    r13
0x1800168c5  push    r14
0x1800168c7  push    r15
0x1800168c9  mov     rbp, rsp
0x1800168cc  sub     rsp, 50h
0x1800168d0  mov     dword ptr [rcx+8], 6B6E6C74h
0x1800168d7  lea     rax, ??_7TLinkedCoreDriver@NPackageInstallLocalspl@@6B@; const NPackageInstallLocalspl::TLinkedCoreDriver::`vftable'
0x1800168de  mov     [rcx], rax
0x1800168e1  mov     rbx, rcx
0x1800168e4  mov     [rcx+10h], rcx
0x1800168e8  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800168ef  mov     [rcx+18h], rcx
0x1800168f3  mov     r13, rdx
0x1800168f6  mov     dword ptr [rcx+20h], 50726F43h
0x1800168fd  xor     edx, edx
0x1800168ff  mov     [rcx+38h], rax
0x180016903  mov     r15, r8
0x180016906  mov     [rcx+50h], rdx
0x18001690a  mov     rax, r9
0x18001690d  neg     rax
0x180016910  mov     [rbp+arg_0], edx
0x180016913  mov     r8d, 80070057h
0x180016919  sbb     ecx, ecx
0x18001691b  not     ecx
0x18001691d  and     ecx, r8d
0x180016920  mov     [rbx+24h], ecx
0x180016923  test    r9, r9
0x180016926  jz      loc_180016ADB
0x18001692c  mov     rcx, rbx; this
0x18001692f  mov     [rbx+50h], r9
0x180016933  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x180016938  mov     [rbx+24h], eax
0x18001693b  test    eax, eax
0x18001693d  js      loc_180016ADB
0x180016943  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180016947  jz      loc_180016C99
0x18001694d  mov     eax, edx
0x18001694f  test    r15, r15
0x180016952  jz      loc_180016C99
0x180016958  mov     [rbx+24h], eax
0x18001695b  test    eax, eax
0x18001695d  js      loc_180016ADB
0x180016963  mov     rax, [r9+0C0h]
0x18001696a  mov     r12, [rax+48h]
0x18001696e  mov     rax, r12
0x180016971  neg     rax
0x180016974  sbb     ecx, ecx
0x180016976  not     ecx
0x180016978  and     ecx, r8d
0x18001697b  mov     [rbx+24h], ecx
0x18001697e  test    r12, r12
0x180016981  jz      loc_180016ADB
0x180016987  mov     rdi, rdx
0x18001698a  mov     [rbp+arg_18], edx
0x18001698d  mov     rsi, rdx
0x180016990  mov     [rbp+var_20], edx
0x180016993  mov     r14, rdx
0x180016996  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x18001699b  lea     rax, [rbp+var_20]
0x18001699f  xor     r9d, r9d; unsigned __int8 *
0x1800169a2  lea     rdx, aInfpath; "InfPath"
0x1800169a9  mov     [rsp+50h+var_30], rax; unsigned int *
0x1800169ae  lea     r8, [rbp+arg_18]; unsigned int *
0x1800169b2  mov     rcx, r13; void *
0x1800169b5  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x1800169ba  test    eax, eax
0x1800169bc  jnz     short loc_180016A16
0x1800169be  cmp     [rbp+arg_18], 1
0x1800169c2  mov     ecx, [rbp+var_20]
0x1800169c5  jnz     loc_180016AF6
0x1800169cb  cmp     ecx, 2
0x1800169ce  jbe     loc_180016AF6
0x1800169d4  call    cs:__imp_DllAllocSplMem
0x1800169da  mov     r15, rax
0x1800169dd  test    rax, rax
0x1800169e0  jz      loc_180016CA1
0x1800169e6  lea     rax, [rbp+var_20]
0x1800169ea  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x1800169ef  mov     r9, r15; unsigned __int8 *
0x1800169f2  mov     [rsp+50h+var_30], rax; unsigned int *
0x1800169f7  lea     r8, [rbp+arg_18]; unsigned int *
0x1800169fb  mov     rcx, r13; void *
0x1800169fe  lea     rdx, aInfpath; "InfPath"
0x180016a05  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180016a0a  test    eax, eax
0x180016a0c  jz      loc_180016B99
0x180016a12  mov     r15, [rbp+arg_10]
0x180016a16  mov     [rbp+arg_0], eax
0x180016a19  test    eax, eax
0x180016a1b  jnz     loc_180016C4E
0x180016a21  mov     eax, 80004005h
0x180016a26  jmp     loc_180016B02
0x180016a2b  lea     rax, [rbp+var_10]
0x180016a2f  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x180016a34  xor     r9d, r9d; unsigned __int8 *
0x180016a37  mov     [rsp+50h+var_30], rax; unsigned int *
0x180016a3c  lea     r8, [rbp+var_18]; unsigned int *
0x180016a40  mov     [rbp+var_18], r14d
0x180016a44  lea     rdx, aDriverversion_0; "DriverVersion"
0x180016a4b  mov     [rbp+var_10], r14d
0x180016a4f  mov     rcx, r13; void *
0x180016a52  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180016a57  test    eax, eax
0x180016a59  jnz     loc_180016CC9
0x180016a5f  cmp     [rbp+var_18], 1
0x180016a63  mov     ecx, [rbp+var_10]
0x180016a66  jnz     loc_180016BC8
0x180016a6c  cmp     ecx, 2
0x180016a6f  jbe     loc_180016BC8
0x180016a75  call    cs:__imp_DllAllocSplMem
0x180016a7b  mov     r14, rax
0x180016a7e  test    rax, rax
0x180016a81  jz      loc_180016CC3
0x180016a87  lea     rax, [rbp+var_10]
0x180016a8b  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x180016a90  mov     r9, r14; unsigned __int8 *
0x180016a93  mov     [rsp+50h+var_30], rax; unsigned int *
0x180016a98  lea     r8, [rbp+var_18]; unsigned int *
0x180016a9c  mov     rcx, r13; void *
0x180016a9f  lea     rdx, aDriverversion_0; "DriverVersion"
0x180016aa6  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180016aab  test    eax, eax
0x180016aad  jnz     loc_180016CC9
0x180016ab3  xor     eax, eax
0x180016ab5  mov     [rbx+24h], eax
0x180016ab8  test    eax, eax
0x180016aba  jns     loc_180016CDA
0x180016ac0  test    rdi, rdi
0x180016ac3  jnz     loc_180016D17
0x180016ac9  test    rsi, rsi
0x180016acc  jnz     loc_180016D25
0x180016ad2  test    r14, r14
0x180016ad5  jnz     loc_180016D33
0x180016adb  mov     rax, rbx
0x180016ade  mov     rbx, [rsp+50h+arg_8]
0x180016ae6  add     rsp, 50h
0x180016aea  pop     r15
0x180016aec  pop     r14
0x180016aee  pop     r13
0x180016af0  pop     r12
0x180016af2  pop     rdi
0x180016af3  pop     rsi
0x180016af4  pop     rbp
0x180016af5  retn
0x180016af6  cmp     [rbp+arg_18], 7
0x180016afa  jz      loc_180016BAD
0x180016b00  xor     eax, eax
0x180016b02  mov     [rbx+24h], eax
0x180016b05  test    eax, eax
0x180016b07  js      short loc_180016AC0
0x180016b09  lea     rax, [rbp+var_14]
0x180016b0d  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x180016b12  xor     r9d, r9d; unsigned __int8 *
0x180016b15  mov     [rsp+50h+var_30], rax; unsigned int *
0x180016b1a  lea     r8, [rbp+var_1C]; unsigned int *
0x180016b1e  mov     [rbp+var_1C], esi
0x180016b21  lea     rdx, aDriverdate; "DriverDate"
0x180016b28  mov     [rbp+var_14], esi
0x180016b2b  mov     rcx, r13; void *
0x180016b2e  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180016b33  test    eax, eax
0x180016b35  jnz     loc_180016CB2
0x180016b3b  cmp     [rbp+var_1C], 1
0x180016b3f  mov     ecx, [rbp+var_14]
0x180016b42  jnz     short loc_180016BBB
0x180016b44  cmp     ecx, 2
0x180016b47  jbe     short loc_180016BBB
0x180016b49  call    cs:__imp_DllAllocSplMem
0x180016b4f  mov     rsi, rax
0x180016b52  test    rax, rax
0x180016b55  jz      loc_180016CAC
0x180016b5b  lea     rax, [rbp+var_14]
0x180016b5f  mov     [rsp+50h+var_28], r12; struct _INISPOOLER *
0x180016b64  mov     r9, rsi; unsigned __int8 *
0x180016b67  mov     [rsp+50h+var_30], rax; unsigned int *
0x180016b6c  lea     r8, [rbp+var_1C]; unsigned int *
0x180016b70  mov     rcx, r13; void *
0x180016b73  lea     rdx, aDriverdate; "DriverDate"
0x180016b7a  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180016b7f  test    eax, eax
0x180016b81  jnz     loc_180016CB2
0x180016b87  xor     eax, eax
0x180016b89  mov     [rbx+24h], eax
0x180016b8c  test    eax, eax
0x180016b8e  js      loc_180016AC0
0x180016b94  jmp     loc_180016A2B
0x180016b99  test    [rbp+var_20], 0FFFFFFFEh
0x180016ba0  cmova   rdi, r15
0x180016ba4  mov     r15, [rbp+arg_10]
0x180016ba8  jmp     loc_180016B00
0x180016bad  cmp     ecx, 4
0x180016bb0  ja      loc_1800169D4
0x180016bb6  jmp     loc_180016B00
0x180016bbb  cmp     [rbp+var_1C], 7
0x180016bbf  jnz     short loc_180016B87
0x180016bc1  cmp     ecx, 4
0x180016bc4  ja      short loc_180016B49
0x180016bc6  jmp     short loc_180016B87
0x180016bc8  cmp     [rbp+var_18], 7
0x180016bcc  jnz     loc_180016AB3
0x180016bd2  cmp     ecx, 4
0x180016bd5  ja      loc_180016A75
0x180016bdb  jmp     loc_180016AB3
0x180016be0  movzx   eax, ax
0x180016be3  or      eax, 80070000h
0x180016be8  mov     [rbx+24h], eax
0x180016beb  test    eax, eax
0x180016bed  js      loc_180016AC0
0x180016bf3  lea     rdx, [rbx+48h]
0x180016bf7  mov     rcx, r14
0x180016bfa  lea     r8, [rbp+arg_0]
0x180016bfe  call    ConvertDriverVersionToDWORDLONG
0x180016c03  test    eax, eax
0x180016c05  jz      loc_180016D06
0x180016c0b  xor     eax, eax
0x180016c0d  jmp     short loc_180016C17
0x180016c0f  movzx   eax, ax
0x180016c12  or      eax, 80070000h
0x180016c17  mov     [rbx+24h], eax
0x180016c1a  test    eax, eax
0x180016c1c  js      loc_180016AC0
0x180016c22  lea     rdx, [rbx+28h]; lpiid
0x180016c26  mov     rcx, r15; lpsz
0x180016c29  call    cs:__imp_IIDFromString
0x180016c2f  mov     [rbx+24h], eax
0x180016c32  test    eax, eax
0x180016c34  js      loc_180016AC0
0x180016c3a  mov     rdx, rdi; unsigned __int16 *
0x180016c3d  lea     rcx, [rbx+38h]; this
0x180016c41  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180016c46  mov     [rbx+24h], eax
0x180016c49  jmp     loc_180016AC0
0x180016c4e  jle     loc_180016B02
0x180016c54  movzx   eax, ax
0x180016c57  or      eax, 80070000h
0x180016c5c  jmp     loc_180016B02
0x180016c61  jle     loc_180016B89
0x180016c67  movzx   eax, ax
0x180016c6a  or      eax, 80070000h
0x180016c6f  jmp     loc_180016B89
0x180016c74  jle     loc_180016AB5
0x180016c7a  movzx   eax, ax
0x180016c7d  or      eax, 80070000h
0x180016c82  jmp     loc_180016AB5
0x180016c87  jle     loc_180016BE8
0x180016c8d  jmp     loc_180016BE0
0x180016c92  jle     short loc_180016C17
0x180016c94  jmp     loc_180016C0F
0x180016c99  mov     eax, r8d
0x180016c9c  jmp     loc_180016958
0x180016ca1  call    cs:__imp_GetLastError
0x180016ca7  jmp     loc_180016A12
0x180016cac  call    cs:__imp_GetLastError
0x180016cb2  mov     [rbp+arg_0], eax
0x180016cb5  test    eax, eax
0x180016cb7  jnz     short loc_180016C61
0x180016cb9  mov     eax, 80004005h
0x180016cbe  jmp     loc_180016B89
0x180016cc3  call    cs:__imp_GetLastError
0x180016cc9  mov     [rbp+arg_0], eax
0x180016ccc  test    eax, eax
0x180016cce  jnz     short loc_180016C74
0x180016cd0  mov     eax, 80004005h
0x180016cd5  jmp     loc_180016AB5
0x180016cda  lea     rdx, [rbx+40h]
0x180016cde  mov     rcx, rsi
0x180016ce1  lea     r8, [rbp+arg_0]
0x180016ce5  call    ConvertDriverDateToFILETIME
0x180016cea  test    eax, eax
0x180016cec  jz      short loc_180016CF5
0x180016cee  xor     eax, eax
0x180016cf0  jmp     loc_180016BE8
0x180016cf5  mov     eax, [rbp+arg_0]
0x180016cf8  test    eax, eax
0x180016cfa  jnz     short loc_180016C87
0x180016cfc  mov     eax, 80004005h
0x180016d01  jmp     loc_180016BE8
0x180016d06  mov     eax, [rbp+arg_0]
0x180016d09  test    eax, eax
0x180016d0b  jnz     short loc_180016C92
0x180016d0d  mov     eax, 80004005h
0x180016d12  jmp     loc_180016C17
0x180016d17  mov     rcx, rdi
0x180016d1a  call    cs:__imp_DllFreeSplMem
0x180016d20  jmp     loc_180016AC9
0x180016d25  mov     rcx, rsi
0x180016d28  call    cs:__imp_DllFreeSplMem
0x180016d2e  jmp     loc_180016AD2
0x180016d33  mov     rcx, r14
0x180016d36  call    cs:__imp_DllFreeSplMem
0x180016d3c  jmp     loc_180016ADB
```
