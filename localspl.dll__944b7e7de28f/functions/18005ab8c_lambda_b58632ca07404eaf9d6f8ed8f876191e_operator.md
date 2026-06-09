# _lambda_b58632ca07404eaf9d6f8ed8f876191e_::operator()

- ea: `0x18005ab8c`
- end: `0x18005af9c`
- name: `_lambda_b58632ca07404eaf9d6f8ed8f876191e_::operator()`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ab6c`

## callees

- `0x1800062a4`
- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x18000a8f0`
- `0x18001fcc8`
- `0x180038698`
- `0x18003ea2c`
- `0x1800430b8`
- `0x18005ab8c`
- `0x18005b9a4`
- `0x18005c0b4`
- `0x180073054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005acb2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005acb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005adfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005af0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005adfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005af0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ae58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005af28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ae58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005af28`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18005ae47`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18005ae47`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x18005ae31`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x18005ae31`
- `SPOOLSS!DllFreeSplMem` at `0x18005aef4`
- `SPOOLSS!DllFreeSplMem` at `0x18005aefd`
- `SPOOLSS!DllFreeSplMem` at `0x18005aef4`
- `SPOOLSS!DllFreeSplMem` at `0x18005aefd`

## pseudocode

```c
int __fastcall lambda_b58632ca07404eaf9d6f8ed8f876191e_::operator()(__int64 a1)
{
  __int64 *v1; // rax
  unsigned __int16 *v2; // r12
  struct _PRINTER_INFO_2W *v4; // rbp
  __int64 v5; // rbx
  int ServerSecurityDescriptor; // eax
  int *v7; // rcx
  _DWORD *v8; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rsi
  int v12; // r14d
  struct _devicemodeW *v13; // r15
  int v14; // r13d
  const unsigned __int16 *v15; // r9
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  __int64 v23; // rcx
  int *v24; // r8
  int MasqPrinterInfo; // eax
  __int64 v26; // rcx
  struct _devicemodeW *v27; // rax
  BOOL v28; // eax
  DWORD v29; // ecx
  __int64 v30; // rdx
  struct _devicemodeW *Src; // rcx
  __int64 v32; // rcx
  const char *v33; // r9
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  BOOL v36; // [rsp+A0h] [rbp+8h]
  struct _PRINTER_INFO_2W *v37; // [rsp+A8h] [rbp+10h] BYREF

  v1 = *(__int64 **)a1;
  v2 = 0;
  v37 = 0;
  v4 = 0;
  v5 = *v1;
  EnterSplSem(1);
  if ( (*(_BYTE *)(v5 + 88) & 0x10) != 0 )
  {
    ServerSecurityDescriptor = GetServerSecurityDescriptor(
                                 (struct _SPOOL *)v5,
                                 **(_DWORD **)(a1 + 16),
                                 **(unsigned __int8 ***)(a1 + 24),
                                 **(_DWORD **)(a1 + 32),
                                 **(unsigned int ***)(a1 + 40));
    v7 = *(int **)(a1 + 8);
    *v7 = ServerSecurityDescriptor;
    LeaveSplSem(v7);
    v8 = *(_DWORD **)(a1 + 8);
    if ( !*v8 )
    {
      LODWORD(v8) = GetLastError();
      if ( (_DWORD)v8 != 122 )
      {
        LODWORD(v8) = GetLastError();
        if ( (_DWORD)v8 != 124 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x591,
            (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
            v9);
      }
    }
    return (int)v8;
  }
  v10 = 258;
  v11 = *(_QWORD *)(v5 + 64);
  if ( **(_DWORD **)(a1 + 16) == 3 )
    v10 = 256;
  if ( !(unsigned int)ValidateSpoolHandle(v5, v10) || !v11 )
  {
    SetLastError(6u);
    LeaveSplSem(v32);
    v8 = *(_DWORD **)(a1 + 8);
    *v8 = 0;
    return (int)v8;
  }
  v12 = *(_DWORD *)(v5 + 88) & 0x20;
  v13 = 0;
  v14 = 0;
  v36 = *(_DWORD *)(v5 + 248) >= 0x1F40u;
  if ( (*(_DWORD *)(v11 + 152) & 0x400000) != 0 )
    LOBYTE(v14) = *(_BYTE *)(v5 + 329) == 0;
  if ( v12 && **(_DWORD **)(a1 + 16) == 2 && *(_QWORD *)(v11 + 104) )
  {
    if ( wcsstr(*(const wchar_t **)(v5 + 24), L",DrvConvert") )
      v15 = *(const unsigned __int16 **)(v5 + 24);
    else
      v15 = 0;
    v13 = ConvertDevModeToSpecifiedVersion((struct _INIPRINTER *)v11, *(struct _devicemodeW **)(v11 + 104), 0, v15, 1);
  }
  if ( *(char *)(v5 + 88) < 0 || *(struct _INISPOOLER **)(v5 + 168) != pLocalIniSpooler )
    v2 = *(unsigned __int16 **)(v5 + 32);
  v16 = **(_DWORD **)(a1 + 16);
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
          if ( AreAllAccessesGranted(*(_DWORD *)(v5 + 116), 0x80000u) )
            goto LABEL_30;
          v28 = AreAnyAccessesGranted(*(_DWORD *)(v5 + 116), 0x1020000u);
          goto LABEL_41;
        }
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( (unsigned int)(v22 - 1) >= 2 )
                goto LABEL_30;
            }
          }
        }
      }
    }
  }
  v28 = AccessGranted(1u, 8u, (struct _SPOOL *)v5);
LABEL_41:
  if ( !v28 )
  {
    v29 = 5;
    goto LABEL_43;
  }
LABEL_30:
  if ( !(unsigned int)ShouldGetMasqDataForHandle(v5) || !*(_QWORD *)(v5 + 104) )
  {
LABEL_35:
    v27 = v13;
    if ( !v12 )
      v27 = *(struct _devicemodeW **)(v11 + 104);
    ***(_DWORD ***)(a1 + 40) = GetPrinterSize(
                                 (struct _INIPRINTER *)v11,
                                 **(_DWORD **)(a1 + 16),
                                 0,
                                 v2,
                                 v27,
                                 v4,
                                 v36,
                                 v14);
    if ( GetLastError() == 534 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplGetPrinter::<lambda_b58632ca07404eaf9d6f8ed8f876191e>::operator ()",
        L"Returning from SplGetPrinter(), because of Integer Overflow.");
      **(_DWORD **)(a1 + 8) = 0;
      goto LABEL_51;
    }
    v30 = **(unsigned int **)(a1 + 32);
    if ( ***(_DWORD ***)(a1 + 40) <= (unsigned int)v30 )
    {
      Src = v13;
      if ( !v12 )
        Src = *(struct _devicemodeW **)(v11 + 104);
      if ( CopyIniPrinterToPrinter(
             (struct _INIPRINTER *)v11,
             **(_DWORD **)(a1 + 16),
             **(unsigned __int8 ***)(a1 + 24),
             (unsigned __int8 *)(**(_QWORD **)(a1 + 24) + v30),
             v4,
             v2,
             1,
             *(_DWORD *)(v5 + 116),
             Src,
             v36,
             v14) )
      {
        **(_DWORD **)(a1 + 8) = 1;
      }
      goto LABEL_51;
    }
    v29 = 122;
LABEL_43:
    SetLastError(v29);
    goto LABEL_51;
  }
  LeaveSplSem(v23);
  if ( ((**(_DWORD **)(a1 + 16) - 2) & 0xFFFFFFFB) != 0
    || (MasqPrinterInfo = RetrieveMasqPrinterInfo(v5, (__int64 *)&v37, v24), v4 = v37, MasqPrinterInfo) )
  {
    EnterSplSem(1);
    if ( !(unsigned int)ValidateSpoolHandle(v5, 16) )
    {
LABEL_51:
      LeaveSplSem(v26);
      goto LABEL_52;
    }
    goto LABEL_35;
  }
LABEL_52:
  DllFreeSplMem(v4);
  DllFreeSplMem(v13);
  v8 = *(_DWORD **)(a1 + 8);
  if ( !*v8 )
  {
    LODWORD(v8) = GetLastError();
    if ( (_DWORD)v8 != 6 && (_DWORD)v8 != 122 && (_DWORD)v8 != 124 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplGetPrinter::<lambda_b58632ca07404eaf9d6f8ed8f876191e>::operator ()",
        L"Failed.  Error %d",
        (unsigned int)v8);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x665,
        (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
        v33);
    }
  }
  return (int)v8;
}

```

## disassembly

```asm
0x18005ab8c  mov     r11, rsp
0x18005ab8f  mov     [r11+18h], rbx
0x18005ab93  push    rbp
0x18005ab94  push    rsi
0x18005ab95  push    rdi
0x18005ab96  push    r12
0x18005ab98  push    r13
0x18005ab9a  push    r14
0x18005ab9c  push    r15
0x18005ab9e  sub     rsp, 60h
0x18005aba2  mov     rax, [rcx]
0x18005aba5  xor     r12d, r12d
0x18005aba8  mov     rdi, rcx
0x18005abab  mov     [r11+10h], r12
0x18005abaf  mov     ebp, r12d
0x18005abb2  mov     rbx, [rax]
0x18005abb5  lea     ecx, [r12+1]
0x18005abba  call    EnterSplSem
0x18005abbf  test    byte ptr [rbx+58h], 10h
0x18005abc3  jz      short loc_18005AC28
0x18005abc5  mov     rax, [rdi+28h]
0x18005abc9  mov     rcx, rbx; struct _SPOOL *
0x18005abcc  mov     r9, [rdi+20h]
0x18005abd0  mov     r8, [rdi+18h]
0x18005abd4  mov     rdx, [rdi+10h]
0x18005abd8  mov     rax, [rax]
0x18005abdb  mov     r9d, [r9]; unsigned int
0x18005abde  mov     r8, [r8]; unsigned __int8 *
0x18005abe1  mov     edx, [rdx]; unsigned int
0x18005abe3  mov     [rsp+98h+var_78], rax; unsigned int *
0x18005abe8  call    ?GetServerSecurityDescriptor@@YAHPEAU_SPOOL@@KPEAEKPEAK@Z; GetServerSecurityDescriptor(_SPOOL *,ulong,uchar *,ulong,ulong *)
0x18005abed  mov     rcx, [rdi+8]
0x18005abf1  mov     [rcx], eax
0x18005abf3  call    LeaveSplSem
0x18005abf8  mov     rax, [rdi+8]
0x18005abfc  cmp     [rax], r12d
0x18005abff  jnz     loc_18005AF3A
0x18005ac05  call    cs:__imp_GetLastError
0x18005ac0b  cmp     eax, 7Ah ; 'z'
0x18005ac0e  jz      loc_18005AF3A
0x18005ac14  call    cs:__imp_GetLastError
0x18005ac1a  cmp     eax, 7Ch ; '|'
0x18005ac1d  jnz     loc_18005AF52
0x18005ac23  jmp     loc_18005AF3A
0x18005ac28  mov     rax, [rdi+10h]
0x18005ac2c  mov     edx, 102h
0x18005ac31  mov     rsi, [rbx+40h]
0x18005ac35  cmp     dword ptr [rax], 3
0x18005ac38  lea     ecx, [rdx-2]
0x18005ac3b  cmovz   edx, ecx
0x18005ac3e  mov     rcx, rbx
0x18005ac41  call    ValidateSpoolHandle
0x18005ac46  test    eax, eax
0x18005ac48  jz      loc_18005AF23
0x18005ac4e  test    rsi, rsi
0x18005ac51  jz      loc_18005AF23
0x18005ac57  mov     r14d, [rbx+58h]
0x18005ac5b  mov     eax, r12d
0x18005ac5e  and     r14d, 20h
0x18005ac62  mov     r15, r12
0x18005ac65  cmp     dword ptr [rbx+0F8h], 1F40h
0x18005ac6f  mov     r13d, r12d
0x18005ac72  setnb   al
0x18005ac75  test    dword ptr [rsi+98h], 400000h
0x18005ac7f  mov     [rsp+98h+arg_0], eax
0x18005ac86  jz      short loc_18005AC93
0x18005ac88  cmp     [rbx+149h], r12b
0x18005ac8f  setz    r13b
0x18005ac93  test    r14d, r14d
0x18005ac96  jz      short loc_18005ACE0
0x18005ac98  mov     rax, [rdi+10h]
0x18005ac9c  cmp     dword ptr [rax], 2
0x18005ac9f  jnz     short loc_18005ACE0
0x18005aca1  cmp     [rsi+68h], r12
0x18005aca5  jz      short loc_18005ACE0
0x18005aca7  mov     rcx, [rbx+18h]; Str
0x18005acab  lea     rdx, aDrvconvert_0; ",DrvConvert"
0x18005acb2  call    cs:__imp_wcsstr
0x18005acb8  mov     rdx, [rsi+68h]; Src
0x18005acbc  xor     r8d, r8d
0x18005acbf  mov     dword ptr [rsp+98h+var_78], 1; int
0x18005acc7  mov     rcx, rsi; struct _INIPRINTER *
0x18005acca  test    rax, rax
0x18005accd  jz      short loc_18005ACD5
0x18005accf  mov     r9, [rbx+18h]
0x18005acd3  jmp     short loc_18005ACD8
0x18005acd5  xor     r9d, r9d
0x18005acd8  call    ConvertDevModeToSpecifiedVersion
0x18005acdd  mov     r15, rax
0x18005ace0  test    byte ptr [rbx+58h], 80h
0x18005ace4  jnz     short loc_18005ACF6
0x18005ace6  mov     rax, cs:pLocalIniSpooler
0x18005aced  cmp     [rbx+0A8h], rax
0x18005acf4  jz      short loc_18005ACFA
0x18005acf6  mov     r12, [rbx+20h]
0x18005acfa  mov     rcx, [rdi+10h]
0x18005acfe  mov     edx, [rcx]
0x18005ad00  test    edx, edx
0x18005ad02  jz      loc_18005AE63
0x18005ad08  sub     edx, 1
0x18005ad0b  jz      loc_18005AE63
0x18005ad11  sub     edx, 1
0x18005ad14  jz      loc_18005AE63
0x18005ad1a  sub     edx, 1
0x18005ad1d  jz      loc_18005AE29
0x18005ad23  sub     edx, 1
0x18005ad26  jz      loc_18005AE63
0x18005ad2c  sub     edx, 1
0x18005ad2f  jz      loc_18005AE63
0x18005ad35  sub     edx, 1
0x18005ad38  jz      loc_18005AE63
0x18005ad3e  sub     edx, 1
0x18005ad41  jz      loc_18005AE63
0x18005ad47  cmp     edx, 1
0x18005ad4a  jz      loc_18005AE63
0x18005ad50  mov     rcx, rbx
0x18005ad53  call    ShouldGetMasqDataForHandle
0x18005ad58  test    eax, eax
0x18005ad5a  jz      short loc_18005ADB7
0x18005ad5c  cmp     [rbx+68h], rbp
0x18005ad60  jz      short loc_18005ADB7
0x18005ad62  call    LeaveSplSem
0x18005ad67  mov     rax, [rdi+10h]
0x18005ad6b  mov     ecx, [rax]
0x18005ad6d  sub     ecx, 2
0x18005ad70  test    ecx, 0FFFFFFFBh
0x18005ad76  jnz     short loc_18005AD98
0x18005ad78  lea     rdx, [rsp+98h+arg_8]
0x18005ad80  mov     rcx, rbx
0x18005ad83  call    RetrieveMasqPrinterInfo
0x18005ad88  mov     rbp, [rsp+98h+arg_8]
0x18005ad90  test    eax, eax
0x18005ad92  jz      loc_18005AEF1
0x18005ad98  mov     ecx, 1
0x18005ad9d  call    EnterSplSem
0x18005ada2  mov     edx, 10h
0x18005ada7  mov     rcx, rbx
0x18005adaa  call    ValidateSpoolHandle
0x18005adaf  test    eax, eax
0x18005adb1  jz      loc_18005AEEC
0x18005adb7  mov     rax, r15
0x18005adba  test    r14d, r14d
0x18005adbd  jnz     short loc_18005ADC3
0x18005adbf  mov     rax, [rsi+68h]
0x18005adc3  mov     rdx, [rdi+10h]
0x18005adc7  mov     r9, r12; unsigned __int16 *
0x18005adca  mov     ecx, [rsp+98h+arg_0]
0x18005add1  xor     r8d, r8d; unsigned int
0x18005add4  mov     [rsp+98h+var_60], r13d; int
0x18005add9  mov     [rsp+98h+var_68], ecx; int
0x18005addd  mov     rcx, rsi; struct _INIPRINTER *
0x18005ade0  mov     edx, [rdx]; unsigned int
0x18005ade2  mov     [rsp+98h+var_70], rbp; struct _PRINTER_INFO_2W *
0x18005ade7  mov     [rsp+98h+var_78], rax; struct _devicemodeW *
0x18005adec  call    ?GetPrinterSize@@YAKPEAU_INIPRINTER@@KKPEAGPEAU_devicemodeW@@PEAU_PRINTER_INFO_2W@@HH@Z; GetPrinterSize(_INIPRINTER *,ulong,ulong,ushort *,_devicemodeW *,_PRINTER_INFO_2W *,int,int)
0x18005adf1  mov     rcx, [rdi+28h]
0x18005adf5  mov     rdx, [rcx]
0x18005adf8  mov     [rdx], eax
0x18005adfa  call    cs:__imp_GetLastError
0x18005ae00  cmp     eax, 216h
0x18005ae05  jnz     short loc_18005AE75
0x18005ae07  lea     rdx, aReturningFromS; "Returning from SplGetPrinter(), because"...
0x18005ae0e  lea     rcx, aSplgetprinterL; "SplGetPrinter::<lambda_b58632ca07404eaf"...
0x18005ae15  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18005ae1a  mov     rax, [rdi+8]
0x18005ae1e  mov     dword ptr [rax], 0
0x18005ae24  jmp     loc_18005AEEC
0x18005ae29  mov     ecx, [rbx+74h]; GrantedAccess
0x18005ae2c  mov     edx, 80000h; DesiredAccess
0x18005ae31  call    cs:__imp_AreAllAccessesGranted
0x18005ae37  test    eax, eax
0x18005ae39  jnz     loc_18005AD50
0x18005ae3f  mov     ecx, [rbx+74h]; GrantedAccess
0x18005ae42  mov     edx, 1020000h; DesiredAccess
0x18005ae47  call    cs:__imp_AreAnyAccessesGranted
0x18005ae4d  test    eax, eax
0x18005ae4f  jnz     loc_18005AD50
0x18005ae55  lea     ecx, [rax+5]; dwErrCode
0x18005ae58  call    cs:__imp_SetLastError
0x18005ae5e  jmp     loc_18005AEEC
0x18005ae63  mov     edx, 8; unsigned int
0x18005ae68  mov     r8, rbx; struct _SPOOL *
0x18005ae6b  lea     ecx, [rdx-7]; unsigned int
0x18005ae6e  call    ?AccessGranted@@YAHKKPEAU_SPOOL@@@Z; AccessGranted(ulong,ulong,_SPOOL *)
0x18005ae73  jmp     short loc_18005AE4D
0x18005ae75  mov     rax, [rdi+20h]
0x18005ae79  mov     edx, [rax]
0x18005ae7b  mov     rax, [rdi+28h]
0x18005ae7f  mov     rcx, [rax]
0x18005ae82  cmp     [rcx], edx
0x18005ae84  jbe     short loc_18005AE8D
0x18005ae86  mov     ecx, 7Ah ; 'z'
0x18005ae8b  jmp     short loc_18005AE58
0x18005ae8d  mov     rcx, r15
0x18005ae90  test    r14d, r14d
0x18005ae93  jnz     short loc_18005AE99
0x18005ae95  mov     rcx, [rsi+68h]
0x18005ae99  mov     rax, [rdi+18h]
0x18005ae9d  mov     [rsp+98h+var_48], r13d; int
0x18005aea2  mov     r8, [rax]; unsigned __int8 *
0x18005aea5  mov     eax, [rsp+98h+arg_0]
0x18005aeac  mov     [rsp+98h+var_50], eax; int
0x18005aeb0  mov     eax, [rbx+74h]
0x18005aeb3  mov     ebx, 1
0x18005aeb8  mov     [rsp+98h+Src], rcx; Src
0x18005aebd  lea     r9, [r8+rdx]; unsigned __int8 *
0x18005aec1  mov     rdx, [rdi+10h]
0x18005aec5  mov     rcx, rsi; struct _INIPRINTER *
0x18005aec8  mov     [rsp+98h+var_60], eax; unsigned int
0x18005aecc  mov     [rsp+98h+var_68], ebx; int
0x18005aed0  mov     [rsp+98h+var_70], r12; unsigned __int16 *
0x18005aed5  mov     edx, [rdx]; unsigned int
0x18005aed7  mov     [rsp+98h+var_78], rbp; struct _PRINTER_INFO_2W *
0x18005aedc  call    ?CopyIniPrinterToPrinter@@YAPEAEPEAU_INIPRINTER@@KPEAE1PEAU_PRINTER_INFO_2W@@PEAGHKPEAU_devicemodeW@@HH@Z; CopyIniPrinterToPrinter(_INIPRINTER *,ulong,uchar *,uchar *,_PRINTER_INFO_2W *,ushort *,int,ulong,_devicemodeW *,int,int)
0x18005aee1  test    rax, rax
0x18005aee4  jz      short loc_18005AEEC
0x18005aee6  mov     rax, [rdi+8]
0x18005aeea  mov     [rax], ebx
0x18005aeec  call    LeaveSplSem
0x18005aef1  mov     rcx, rbp
0x18005aef4  call    cs:__imp_DllFreeSplMem
0x18005aefa  mov     rcx, r15
0x18005aefd  call    cs:__imp_DllFreeSplMem
0x18005af03  mov     rax, [rdi+8]
0x18005af07  cmp     dword ptr [rax], 0
0x18005af0a  jnz     short loc_18005AF3A
0x18005af0c  call    cs:__imp_GetLastError
0x18005af12  cmp     eax, 6
0x18005af15  jz      short loc_18005AF3A
0x18005af17  cmp     eax, 7Ah ; 'z'
0x18005af1a  jz      short loc_18005AF3A
0x18005af1c  cmp     eax, 7Ch ; '|'
0x18005af1f  jnz     short loc_18005AF6C
0x18005af21  jmp     short loc_18005AF3A
0x18005af23  mov     ecx, 6; dwErrCode
0x18005af28  call    cs:__imp_SetLastError
0x18005af2e  call    LeaveSplSem
0x18005af33  mov     rax, [rdi+8]
0x18005af37  mov     [rax], r12d
0x18005af3a  mov     rbx, [rsp+98h+arg_10]
0x18005af42  add     rsp, 60h
0x18005af46  pop     r15
0x18005af48  pop     r14
0x18005af4a  pop     r13
0x18005af4c  pop     r12
0x18005af4e  pop     rdi
0x18005af4f  pop     rsi
0x18005af50  pop     rbp
0x18005af51  retn
0x18005af52  mov     rcx, [rsp+98h]; this
0x18005af5a  lea     r8, aPrintscanPrint_4; "printscan\\print\\spooler\\localspl\\ge"...
0x18005af61  mov     edx, 591h; void *
0x18005af66  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005af6c  mov     r8d, eax
0x18005af6f  lea     rdx, aFailedErrorD; "Failed.  Error %d"
0x18005af76  lea     rcx, aSplgetprinterL; "SplGetPrinter::<lambda_b58632ca07404eaf"...
0x18005af7d  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18005af82  mov     rcx, [rsp+98h]; this
0x18005af8a  lea     r8, aPrintscanPrint_4; "printscan\\print\\spooler\\localspl\\ge"...
0x18005af91  mov     edx, 665h; void *
0x18005af96  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
