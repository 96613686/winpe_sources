# InternalSetDefaultPrinter(ushort const *,ulong,ushort const *,ushort const *,int,ushort const *,ushort * *)

- ea: `0x180012e60`
- end: `0x18001329c`
- name: `?InternalSetDefaultPrinter@@YAHPEBGK00H0PEAPEAG@Z`
- size: `1084`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x180040674`

## callees

- `0x180012e60`
- `0x1800132a4`
- `0x18001366c`
- `0x180013e60`
- `0x180014278`
- `0x18001fb10`
- `0x1800224a4`
- `0x1800243a8`
- `0x1800297bc`
- `0x18002db3c`
- `0x1800c82fc`
- `0x1800c85a4`
- `0x1800c9cac`
- `0x1800c9e04`
- `0x1800c9ed8`
- `0x1800c9f30`
- `0x1800c9fbc`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013123`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013162`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013123`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013275`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013275`
- `SPOOLSS!DllFreeSplMem` at `0x180012fb7`
- `SPOOLSS!DllFreeSplMem` at `0x180013112`
- `SPOOLSS!DllFreeSplMem` at `0x180013250`
- `SPOOLSS!DllFreeSplMem` at `0x180013260`
- `SPOOLSS!DllFreeSplMem` at `0x180012fb7`
- `SPOOLSS!DllFreeSplMem` at `0x180013112`
- `SPOOLSS!DllFreeSplMem` at `0x180013250`
- `SPOOLSS!DllFreeSplMem` at `0x180013260`
- `SPOOLSS!AllocSplStr` at `0x180012f6f`
- `SPOOLSS!AllocSplStr` at `0x180012ffc`
- `SPOOLSS!AllocSplStr` at `0x180012f6f`
- `SPOOLSS!AllocSplStr` at `0x180012ffc`
- `USER32!SendNotifyMessageW` at `0x180013183`
- `USER32!SendNotifyMessageW` at `0x180013183`

## pseudocode

```c
__int64 __fastcall InternalSetDefaultPrinter(
        unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7)
{
  unsigned __int16 **v7; // r13
  unsigned __int16 *v10; // rdi
  int v11; // r12d
  int v12; // ebx
  DWORD LastError; // eax
  DWORD MRUEstablished; // ebx
  int v15; // edi
  DWORD v16; // eax
  LPCWSTR v17; // r15
  unsigned int v18; // r12d
  DWORD CurrentNetworkId; // eax
  BOOL v20; // r15d
  unsigned int v21; // r14d
  SplLogType *v22; // rax
  __int64 v23; // r10
  __int64 v24; // r11
  unsigned __int16 *v26; // [rsp+48h] [rbp-91h] BYREF
  LPCWSTR lpValue; // [rsp+50h] [rbp-89h] BYREF
  int v28; // [rsp+58h] [rbp-81h]
  unsigned __int16 *v29; // [rsp+60h] [rbp-79h]
  int v30; // [rsp+68h] [rbp-71h] BYREF
  __int64 v31; // [rsp+70h] [rbp-69h]
  int v32; // [rsp+78h] [rbp-61h]
  BOOL v33; // [rsp+80h] [rbp-59h] BYREF
  __int64 v34; // [rsp+88h] [rbp-51h]
  int v35; // [rsp+90h] [rbp-49h]
  _BYTE v36[24]; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v37[24]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v38[80]; // [rsp+C8h] [rbp-11h] BYREF
  int v39; // [rsp+128h] [rbp+4Fh]

  v7 = a7;
  v29 = 0;
  lpValue = 0;
  v26 = 0;
  v10 = 0;
  v39 = 0;
  v11 = 0;
  v28 = 0;
  if ( a7 )
    *a7 = 0;
  InternalGetDefaultPrinter(0, 0, a3, a4, a6, &v26);
  if ( a1 && *a1 )
  {
    lpValue = 0;
    LODWORD(a7) = 0;
    if ( (unsigned int)IsPrinterValid(a1) )
      goto LABEL_15;
    v12 = (int)a7;
    if ( (_DWORD)a7 )
    {
      v10 = (unsigned __int16 *)AllocSplStr(a1);
      if ( !v10 )
      {
        v29 = L"AllocSplStr failed";
        goto LABEL_15;
      }
    }
    else
    {
      if ( (unsigned int)GetActualPrinterName(a1, (unsigned __int16 **)&lpValue) )
      {
        v10 = (unsigned __int16 *)lpValue;
        v12 = 1;
        LODWORD(a7) = 1;
LABEL_11:
        if ( !a5 )
          goto LABEL_14;
        if ( !(unsigned int)CheckIfPrinterValidUsingAPI(v10) )
        {
          v12 = (int)a7;
LABEL_14:
          if ( !v12 )
            goto LABEL_15;
          goto LABEL_31;
        }
LABEL_15:
        MRUEstablished = 1801;
        goto LABEL_49;
      }
      LastError = GetLastError();
      v29 = L"GetActualPrinterName failed";
      if ( LastError )
        goto LABEL_15;
    }
    if ( !v12 )
      goto LABEL_15;
    goto LABEL_11;
  }
  LODWORD(a7) = 0;
  MRUEstablished = GetMRUEstablished(a3, &a7);
  if ( MRUEstablished )
  {
    v15 = 1;
    MRUEstablished = 0;
  }
  else
  {
    v15 = (int)a7;
  }
  if ( v26 )
  {
    DllFreeSplMem(v26);
    v26 = 0;
  }
  InternalGetDefaultPrinter(0, 1, a3, a4, a6, &v26);
  if ( v26 && (a2 || v15) )
  {
    v10 = (unsigned __int16 *)AllocSplStr(v26);
    goto LABEL_49;
  }
  if ( !(unsigned int)ChooseDefaultPrinter((unsigned __int16 **)&lpValue) )
  {
    MRUEstablished = GetLastError();
    v29 = L"ChooseDefaultPrinter failed";
  }
  v10 = (unsigned __int16 *)lpValue;
  if ( MRUEstablished )
    goto LABEL_49;
  v11 = 1;
  v39 = 1;
LABEL_31:
  if ( (unsigned int)IsRedirectedPrinter(v10) )
  {
    MRUEstablished = SetSessionDefaultPrinter(v10, a3);
    if ( MRUEstablished || !(unsigned int)RunningInContainerOS() )
      goto LABEL_49;
    v16 = SetGlobalDefaultPrinter(v10, a3);
    goto LABEL_39;
  }
  v28 = 1;
  MRUEstablished = SetGlobalDefaultPrinter(v10, a3);
  if ( MRUEstablished || a2 )
    goto LABEL_49;
  if ( v11 )
  {
    v16 = SetMRUEstablished(0, a3);
LABEL_39:
    MRUEstablished = v16;
    goto LABEL_49;
  }
  v17 = 0;
  v18 = 0;
  lpValue = 0;
  LODWORD(a7) = 0;
  MRUEstablished = SetMRUEstablished(1, a3);
  if ( !MRUEstablished )
  {
    CurrentNetworkId = GetCurrentNetworkId((unsigned __int16 **)&lpValue, (enum DefPrnNetworkDescriptor *)&a7);
    v17 = lpValue;
    MRUEstablished = CurrentNetworkId;
    v18 = (unsigned int)a7;
  }
  if ( MRUEstablished == 1168 )
  {
    MRUEstablished = 0;
  }
  else if ( !MRUEstablished )
  {
    if ( !v17 )
      goto LABEL_49;
    MRUEstablished = SetDefaultPrinterForNetwork(v17, v18, v10, a3);
  }
  if ( v17 )
    DllFreeSplMem(v17);
LABEL_49:
  v20 = !(unsigned int)_o__wcsicmp(a6, L"spoolsv.exe") || v39;
  if ( MRUEstablished )
    goto LABEL_60;
  if ( v28 )
    CleanupSessionDefaultPrinterIfAny(a3);
  if ( v26 && !(unsigned int)_o__wcsicmp(v10, v26) )
  {
LABEL_60:
    v21 = a2;
  }
  else
  {
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"windows");
    v21 = a2;
    if ( a2 == 1 )
    {
      SplLogType::SplLogType((SplLogType *)v36, a6);
      v30 = 0;
      v31 = 4;
      v32 = 0;
      SplLogType::SplLogType((SplLogType *)v37, v10);
      v22 = SplLogType::SplLogType((SplLogType *)v38, v26);
      v33 = v20;
      v34 = 4;
      v35 = 0;
      SplLogEvent2(&DEFAULT_PRINTER_CHANGED_EVENT, (struct SplLogType *)&v33, v22, v23, &v30, v24, 0);
    }
  }
  SplLibTelemetry::DefaultPrinterChanged(v26, v10, v20, v21, v29, MRUEstablished);
  if ( v7 )
  {
    *v7 = v10;
    v10 = 0;
  }
  if ( v10 )
    DllFreeSplMem(v10);
  if ( v26 )
  {
    DllFreeSplMem(v26);
    v26 = 0;
  }
  if ( !MRUEstablished )
    return 1;
  SetLastError(MRUEstablished);
  return 0;
}

```

## disassembly

```asm
0x180012e60  mov     rax, rsp
0x180012e63  mov     [rax+18h], rbx
0x180012e67  mov     [rax+20h], r9
0x180012e6b  mov     [rax+10h], edx
0x180012e6e  push    rbp
0x180012e6f  push    rsi
0x180012e70  push    rdi
0x180012e71  push    r12
0x180012e73  push    r13
0x180012e75  push    r14
0x180012e77  push    r15
0x180012e79  lea     rbp, [rax-47h]
0x180012e7d  sub     rsp, 0E0h
0x180012e84  mov     r13, [rbp+3Fh+arg_30]
0x180012e88  xor     ebx, ebx
0x180012e8a  mov     [rbp+3Fh+var_B8], rbx
0x180012e8e  mov     r14, r8
0x180012e91  mov     [rsp+110h+lpValue], rbx
0x180012e96  mov     r15, rcx
0x180012e99  mov     [rsp+110h+var_D0], rbx
0x180012e9e  mov     edi, ebx
0x180012ea0  mov     [rbp+3Fh+arg_0], ebx
0x180012ea3  mov     r12d, ebx
0x180012ea6  mov     [rsp+110h+var_C0], ebx
0x180012eaa  test    r13, r13
0x180012ead  jz      short loc_180012EB3
0x180012eaf  mov     [r13+0], rbx
0x180012eb3  lea     rcx, [rsp+110h+var_D0]
0x180012eb8  xor     edx, edx; int
0x180012eba  mov     [rsp+110h+var_E8], rcx; unsigned __int16 **
0x180012ebf  mov     rcx, [rbp+3Fh+arg_28]
0x180012ec3  mov     [rsp+110h+var_F0], rcx; unsigned __int16 *
0x180012ec8  xor     ecx, ecx; int
0x180012eca  call    ?InternalGetDefaultPrinter@@YAHHHPEBG00PEAPEAG@Z; InternalGetDefaultPrinter(int,int,ushort const *,ushort const *,ushort const *,ushort * *)
0x180012ecf  test    r15, r15
0x180012ed2  jz      loc_180012F8A
0x180012ed8  cmp     bx, [r15]
0x180012edc  jz      loc_180012F8A
0x180012ee2  mov     esi, 1
0x180012ee7  mov     [rsp+110h+lpValue], rbx
0x180012eec  mov     r8d, esi
0x180012eef  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x180012ef2  lea     r9, [rbp+3Fh+arg_30]
0x180012ef6  mov     rdx, r14
0x180012ef9  mov     rcx, r15; unsigned __int16 *
0x180012efc  call    IsPrinterValid
0x180012f01  test    eax, eax
0x180012f03  jnz     short loc_180012F65
0x180012f05  mov     ebx, dword ptr [rbp+3Fh+arg_30]
0x180012f08  mov     rcx, r15; unsigned __int16 *
0x180012f0b  test    ebx, ebx
0x180012f0d  jnz     short loc_180012F6F
0x180012f0f  lea     rdx, [rsp+110h+lpValue]; unsigned __int16 **
0x180012f14  call    ?GetActualPrinterName@@YAHPEBGPEAPEAG@Z; GetActualPrinterName(ushort const *,ushort * *)
0x180012f19  test    eax, eax
0x180012f1b  jz      short loc_180012F29
0x180012f1d  mov     rdi, [rsp+110h+lpValue]
0x180012f22  mov     ebx, esi
0x180012f24  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x180012f27  jmp     short loc_180012F42
0x180012f29  call    cs:__imp_GetLastError
0x180012f2f  lea     rcx, aGetactualprint; "GetActualPrinterName failed"
0x180012f36  mov     [rbp+3Fh+var_B8], rcx
0x180012f3a  test    eax, eax
0x180012f3c  jnz     short loc_180012F65
0x180012f3e  test    ebx, ebx
0x180012f40  jz      short loc_180012F65
0x180012f42  cmp     [rbp+3Fh+arg_20], r12d
0x180012f46  jz      short loc_180012F5D
0x180012f48  lea     r8, [rbp+3Fh+arg_30]
0x180012f4c  mov     edx, esi
0x180012f4e  mov     rcx, rdi; unsigned __int16 *
0x180012f51  call    CheckIfPrinterValidUsingAPI
0x180012f56  test    eax, eax
0x180012f58  jnz     short loc_180012F65
0x180012f5a  mov     ebx, dword ptr [rbp+3Fh+arg_30]
0x180012f5d  test    ebx, ebx
0x180012f5f  jnz     loc_180013040
0x180012f65  mov     ebx, 709h
0x180012f6a  jmp     loc_180013118
0x180012f6f  call    cs:__imp_AllocSplStr
0x180012f75  mov     rdi, rax
0x180012f78  test    rax, rax
0x180012f7b  jnz     short loc_180012F3E
0x180012f7d  lea     rax, aAllocsplstrFai; "AllocSplStr failed"
0x180012f84  mov     [rbp+3Fh+var_B8], rax
0x180012f88  jmp     short loc_180012F65
0x180012f8a  lea     rdx, [rbp+3Fh+arg_30]
0x180012f8e  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x180012f91  mov     rcx, r14
0x180012f94  call    GetMRUEstablished
0x180012f99  mov     ebx, eax
0x180012f9b  mov     esi, 1
0x180012fa0  test    eax, eax
0x180012fa2  jz      short loc_180012FAA
0x180012fa4  mov     edi, esi
0x180012fa6  xor     ebx, ebx
0x180012fa8  jmp     short loc_180012FAD
0x180012faa  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x180012fad  mov     rcx, [rsp+110h+var_D0]
0x180012fb2  test    rcx, rcx
0x180012fb5  jz      short loc_180012FC2
0x180012fb7  call    cs:__imp_DllFreeSplMem
0x180012fbd  mov     [rsp+110h+var_D0], r12
0x180012fc2  mov     r15, [rbp+3Fh+arg_18]
0x180012fc6  lea     rax, [rsp+110h+var_D0]
0x180012fcb  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x180012fd0  mov     r9, r15; unsigned __int16 *
0x180012fd3  mov     rax, [rbp+3Fh+arg_28]
0x180012fd7  mov     r8, r14; unsigned __int16 *
0x180012fda  mov     edx, esi; int
0x180012fdc  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180012fe1  xor     ecx, ecx; int
0x180012fe3  call    ?InternalGetDefaultPrinter@@YAHHHPEBG00PEAPEAG@Z; InternalGetDefaultPrinter(int,int,ushort const *,ushort const *,ushort const *,ushort * *)
0x180012fe8  mov     rcx, [rsp+110h+var_D0]
0x180012fed  test    rcx, rcx
0x180012ff0  jz      short loc_18001300A
0x180012ff2  cmp     [rbp+3Fh+arg_8], r12d
0x180012ff6  jnz     short loc_180012FFC
0x180012ff8  test    edi, edi
0x180012ffa  jz      short loc_18001300A
0x180012ffc  call    cs:__imp_AllocSplStr
0x180013002  mov     rdi, rax
0x180013005  jmp     loc_180013118
0x18001300a  lea     rcx, [rsp+110h+lpValue]; unsigned __int16 **
0x18001300f  call    ?ChooseDefaultPrinter@@YAHPEAPEAG@Z; ChooseDefaultPrinter(ushort * *)
0x180013014  test    eax, eax
0x180013016  jnz     short loc_18001302B
0x180013018  call    cs:__imp_GetLastError
0x18001301e  mov     ebx, eax
0x180013020  lea     rax, aChoosedefaultp; "ChooseDefaultPrinter failed"
0x180013027  mov     [rbp+3Fh+var_B8], rax
0x18001302b  mov     rdi, [rsp+110h+lpValue]
0x180013030  test    ebx, ebx
0x180013032  jnz     loc_180013118
0x180013038  mov     r12d, esi
0x18001303b  mov     [rbp+3Fh+arg_0], esi
0x18001303e  jmp     short loc_180013044
0x180013040  mov     r15, [rbp+3Fh+arg_18]
0x180013044  mov     rcx, rdi
0x180013047  call    IsRedirectedPrinter
0x18001304c  mov     rdx, r14; LPCWSTR
0x18001304f  mov     rcx, rdi; lpValue
0x180013052  test    eax, eax
0x180013054  jz      short loc_180013082
0x180013056  mov     r8, r15
0x180013059  call    SetSessionDefaultPrinter
0x18001305e  mov     ebx, eax
0x180013060  test    eax, eax
0x180013062  jnz     loc_180013118
0x180013068  call    ?RunningInContainerOS@@YAHXZ; RunningInContainerOS(void)
0x18001306d  test    eax, eax
0x18001306f  jz      loc_180013118
0x180013075  mov     rdx, r14
0x180013078  mov     rcx, rdi
0x18001307b  call    SetGlobalDefaultPrinter
0x180013080  jmp     short loc_1800130A9
0x180013082  mov     [rsp+110h+var_C0], esi
0x180013086  call    SetGlobalDefaultPrinter
0x18001308b  mov     ebx, eax
0x18001308d  test    eax, eax
0x18001308f  jnz     loc_180013118
0x180013095  cmp     [rbp+3Fh+arg_8], eax
0x180013098  jnz     short loc_180013118
0x18001309a  mov     rdx, r14
0x18001309d  test    r12d, r12d
0x1800130a0  jz      short loc_1800130AD
0x1800130a2  xor     ecx, ecx
0x1800130a4  call    SetMRUEstablished
0x1800130a9  mov     ebx, eax
0x1800130ab  jmp     short loc_180013118
0x1800130ad  xor     r15d, r15d
0x1800130b0  xor     r12d, r12d
0x1800130b3  mov     ecx, esi
0x1800130b5  mov     [rsp+110h+lpValue], r15
0x1800130ba  mov     dword ptr [rbp+3Fh+arg_30], r12d
0x1800130be  call    SetMRUEstablished
0x1800130c3  mov     ebx, eax
0x1800130c5  test    eax, eax
0x1800130c7  jnz     short loc_1800130E2
0x1800130c9  lea     rdx, [rbp+3Fh+arg_30]; enum DefPrnNetworkDescriptor *
0x1800130cd  lea     rcx, [rsp+110h+lpValue]; unsigned __int16 **
0x1800130d2  call    GetCurrentNetworkId
0x1800130d7  mov     r15, [rsp+110h+lpValue]
0x1800130dc  mov     ebx, eax
0x1800130de  mov     r12d, dword ptr [rbp+3Fh+arg_30]
0x1800130e2  cmp     ebx, 490h
0x1800130e8  jnz     short loc_1800130EE
0x1800130ea  xor     ebx, ebx
0x1800130ec  jmp     short loc_18001310A
0x1800130ee  test    ebx, ebx
0x1800130f0  jnz     short loc_18001310A
0x1800130f2  test    r15, r15
0x1800130f5  jz      short loc_180013118
0x1800130f7  mov     r9, r14
0x1800130fa  mov     r8, rdi
0x1800130fd  mov     edx, r12d
0x180013100  mov     rcx, r15
0x180013103  call    SetDefaultPrinterForNetwork
0x180013108  mov     ebx, eax
0x18001310a  test    r15, r15
0x18001310d  jz      short loc_180013118
0x18001310f  mov     rcx, r15
0x180013112  call    cs:__imp_DllFreeSplMem
0x180013118  mov     rcx, [rbp+3Fh+arg_28]
0x18001311c  lea     rdx, aSpoolsvExe; "spoolsv.exe"
0x180013123  call    cs:__imp__o__wcsicmp
0x180013129  test    eax, eax
0x18001312b  jz      short loc_180013138
0x18001312d  cmp     [rbp+3Fh+arg_0], 0
0x180013131  jnz     short loc_180013138
0x180013133  xor     r15d, r15d
0x180013136  jmp     short loc_18001313B
0x180013138  mov     r15d, esi
0x18001313b  test    ebx, ebx
0x18001313d  jnz     loc_180013219
0x180013143  cmp     [rsp+110h+var_C0], ebx
0x180013147  jz      short loc_180013155
0x180013149  mov     rdx, [rbp+3Fh+arg_18]
0x18001314d  mov     rcx, r14; lpSubKey
0x180013150  call    CleanupSessionDefaultPrinterIfAny
0x180013155  mov     rdx, [rsp+110h+var_D0]
0x18001315a  test    rdx, rdx
0x18001315d  jz      short loc_180013170
0x18001315f  mov     rcx, rdi
0x180013162  call    cs:__imp__o__wcsicmp
0x180013168  test    eax, eax
0x18001316a  jz      loc_180013219
0x180013170  xor     r8d, r8d; wParam
0x180013173  lea     r9, lParam; "windows"
0x18001317a  mov     ecx, 0FFFFh; hWnd
0x18001317f  lea     edx, [r8+1Ah]; Msg
0x180013183  call    cs:__imp_SendNotifyMessageW
0x180013189  mov     r14d, [rbp+3Fh+arg_8]
0x18001318d  cmp     r14d, esi
0x180013190  jnz     loc_18001321D
0x180013196  mov     rdx, [rbp+3Fh+arg_28]; unsigned __int16 *
0x18001319a  lea     rcx, [rbp+3Fh+var_80]; this
0x18001319e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800131a3  mov     r12d, 4
0x1800131a9  mov     [rbp+3Fh+var_B0], 0
0x1800131b0  mov     rdx, rdi; unsigned __int16 *
0x1800131b3  mov     [rbp+3Fh+var_A8], r12
0x1800131b7  lea     rcx, [rbp+3Fh+var_68]; this
0x1800131bb  mov     [rbp+3Fh+var_A0], 0
0x1800131c2  mov     r11, rax
0x1800131c5  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800131ca  mov     rdx, [rsp+110h+var_D0]; unsigned __int16 *
0x1800131cf  lea     rcx, [rbp+3Fh+var_50]; this
0x1800131d3  mov     r10, rax
0x1800131d6  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800131db  mov     qword ptr [rsp+30h], 0
0x1800131e4  lea     rcx, [rbp+3Fh+var_B0]
0x1800131e8  mov     [rsp+110h+var_E8], r11
0x1800131ed  lea     rdx, [rbp+3Fh+var_98]; struct SplLogType *
0x1800131f1  mov     [rsp+110h+var_F0], rcx
0x1800131f6  mov     r9, r10
0x1800131f9  lea     rcx, DEFAULT_PRINTER_CHANGED_EVENT; struct _EVENT_DESCRIPTOR *
0x180013200  mov     [rbp+3Fh+var_98], r15d
0x180013204  mov     r8, rax
0x180013207  mov     [rbp+3Fh+var_90], r12
0x18001320b  mov     [rbp+3Fh+var_88], 0
0x180013212  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180013217  jmp     short loc_18001321D
0x180013219  mov     r14d, [rbp+3Fh+arg_8]
0x18001321d  mov     rax, [rbp+3Fh+var_B8]
0x180013221  mov     r9d, r14d; unsigned int
0x180013224  mov     rcx, [rsp+110h+var_D0]; unsigned __int16 *
0x180013229  mov     r8d, r15d; int
0x18001322c  mov     dword ptr [rsp+110h+var_E8], ebx; unsigned int
0x180013230  mov     rdx, rdi; unsigned __int16 *
0x180013233  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180013238  call    ?DefaultPrinterChanged@SplLibTelemetry@@SAXPEBG0HK0K@Z; SplLibTelemetry::DefaultPrinterChanged(ushort const *,ushort const *,int,ulong,ushort const *,ulong)
0x18001323d  test    r13, r13
0x180013240  jz      short loc_180013248
0x180013242  mov     [r13+0], rdi
0x180013246  xor     edi, edi
0x180013248  test    rdi, rdi
0x18001324b  jz      short loc_180013256
0x18001324d  mov     rcx, rdi
0x180013250  call    cs:__imp_DllFreeSplMem
0x180013256  mov     rcx, [rsp+110h+var_D0]
0x18001325b  test    rcx, rcx
0x18001325e  jz      short loc_18001326F
0x180013260  call    cs:__imp_DllFreeSplMem
0x180013266  mov     [rsp+110h+var_D0], 0
0x18001326f  test    ebx, ebx
0x180013271  jz      short loc_18001327F
0x180013273  mov     ecx, ebx; dwErrCode
0x180013275  call    cs:__imp_SetLastError
0x18001327b  xor     eax, eax
0x18001327d  jmp     short loc_180013281
0x18001327f  mov     eax, esi
0x180013281  mov     rbx, [rsp+110h+arg_10]
0x180013289  add     rsp, 0E0h
0x180013290  pop     r15
0x180013292  pop     r14
0x180013294  pop     r13
0x180013296  pop     r12
0x180013298  pop     rdi
  ... truncated ...
```
