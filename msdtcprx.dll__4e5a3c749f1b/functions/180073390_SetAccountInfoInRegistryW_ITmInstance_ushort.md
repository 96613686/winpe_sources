# SetAccountInfoInRegistryW(ITmInstance *,ushort *)

- ea: `0x180073390`
- end: `0x1800737d2`
- name: `?SetAccountInfoInRegistryW@@YAJPEAUITmInstance@@PEAG@Z`
- size: `1090`
- prototype: `int(struct ITmInstance *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180047cac`
- `0x180050a7c`

## callees

- `0x180006054`
- `0x18000f674`
- `0x180010870`
- `0x180011ac0`
- `0x18001d138`
- `0x18001d178`
- `0x18001d184`
- `0x18002f534`
- `0x180062658`
- `0x1800731a0`
- `0x180073390`
- `0x180079a4c`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734ec`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800734e2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800734e2`
- `msvcrt!wcschr` at `0x18007367a`
- `msvcrt!wcschr` at `0x18007367a`

## string_xrefs

- `0x180073557`: `com\complus\dtc\shared\util\security.cpp`
- `0x1800735d0`: `com\complus\dtc\shared\util\security.cpp`
- `0x180073637`: `com\complus\dtc\shared\util\security.cpp`
- `0x18007372d`: `com\complus\dtc\shared\util\security.cpp`
- `0x180073763`: `com\complus\dtc\shared\util\security.cpp`
- `0x180073453`: `com\complus\dtc\shared\util\scm.cpp`
- `0x1800735ad`: `com\complus\dtc\shared\util\scm.cpp`
- `0x1800735d7`: `msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: CService::Create failed, hr=0x%x\n`
- `0x1800735ff`: `SetAccountInfoInRegistryW: CService::Create failed`
- `0x18007355e`: `msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: CService::GetAccount failed, hr=0x%x\n`
- `0x180073586`: `SetAccountInfoInRegistryW: FAILED - pDTCService->GetAccount(...)`
- `0x18007363e`: `msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: LookupSpecialAccount failed, hr=0x%x\n`
- `0x180073664`: `SetAccountInfoInRegistryW: LookupSpecialAccount failed`
- `0x180073734`: `msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW : SetRegKeyValue32W: failed to set a registry value, hr=0x%x\n`
- `0x18007375a`: `SetAccountInfoInRegistryW : SetRegKeyValue32W: failed to set a registry value.`
- `0x18007345a`: `CService::InternalInit call failed`
- `0x1800735b4`: `QueryServiceConfigW call failed`

## pseudocode

```c
__int64 __fastcall SetAccountInfoInRegistryW(struct ITmInstance *a1, unsigned __int16 *a2)
{
  __int64 v4; // r15
  SC_HANDLE *v5; // r13
  volatile signed __int32 *v6; // rax
  unsigned __int16 *v7; // rdx
  struct CServiceControlManager *v8; // r8
  unsigned int v9; // r9d
  volatile signed __int32 *v10; // rdi
  int v11; // eax
  signed int v12; // ebx
  struct _QUERY_SERVICE_CONFIGW *v13; // rdi
  int i; // esi
  struct _QUERY_SERVICE_CONFIGW *v15; // rax
  signed int LastError; // eax
  const unsigned __int16 *lpServiceStartName; // r8
  __int64 v18; // rax
  int v19; // edi
  unsigned int v20; // r9d
  char *v21; // rdx
  int v22; // ecx
  int v23; // eax
  int v24; // eax
  unsigned __int16 *v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  struct _SPECIAL_ACCOUNT_ *v29; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Str; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[510]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v32; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v33[510]; // [rsp+252h] [rbp+152h] BYREF
  char v34; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v35[783]; // [rsp+451h] [rbp+351h] BYREF

  Str = 0;
  memset_0(v31, 0, sizeof(v31));
  v34 = 0;
  memset_0(v35, 0, 0x303u);
  v4 = -1;
  v29 = 0;
  v5 = 0;
  if ( a2 )
  {
    StringCchCopyW(&Str, 0x100u, a2);
    goto LABEL_35;
  }
  v6 = (volatile signed __int32 *)operator new(0x18u);
  Size = (size_t)v6;
  v10 = v6;
  if ( !v6 )
  {
    v12 = -2147024882;
LABEL_33:
    v19 = v12;
    StringCchPrintfA(
      &v34,
      0x304u,
      "msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: CService::Create failed, hr=0x%x\n",
      "com\\complus\\dtc\\shared\\util\\security.cpp",
      3054,
      v12);
    v20 = 3056;
    v21 = "SetAccountInfoInRegistryW: CService::Create failed";
    goto LABEL_28;
  }
  *v6 = 1;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  v11 = CService::InternalInit((CService *)v6, v7, v8, v9, v26);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v5 = (SC_HANDLE *)v10;
    _InterlockedIncrement(v10);
  }
  else
  {
    TraceFile(v11, "CService::InternalInit call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x13Cu);
  }
  CService::Release((CService *)v10);
  if ( v12 < 0 )
    goto LABEL_33;
  v12 = 0;
  LODWORD(Size) = 64;
  v13 = 0;
  for ( i = 2; i; --i )
  {
    if ( v13 )
      operator delete(v13);
    v15 = (struct _QUERY_SERVICE_CONFIGW *)operator new[]((unsigned int)Size);
    v13 = v15;
    if ( !v15 )
    {
      v12 = -2147024882;
LABEL_31:
      TraceFile(v12, "QueryServiceConfigW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x1E8u);
      goto LABEL_24;
    }
    memset_0(v15, 0, (unsigned int)Size);
    if ( QueryServiceConfigW(v5[2], v13, Size, (LPDWORD)&Size) )
    {
      v12 = 0;
      goto LABEL_19;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
    if ( LastError != 122 )
      break;
  }
  if ( v12 < 0 )
    goto LABEL_31;
LABEL_19:
  lpServiceStartName = v13->lpServiceStartName;
  if ( lpServiceStartName )
  {
    v18 = -1;
    do
      ++v18;
    while ( lpServiceStartName[v18] );
    if ( (unsigned int)(v18 + 1) <= 0x100 )
      StringCchCopyW(&Str, 0x100u, lpServiceStartName);
  }
LABEL_24:
  if ( v13 )
    operator delete(v13);
  if ( v12 < 0 )
  {
    v19 = v12;
    StringCchPrintfA(
      &v34,
      0x304u,
      "msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: CService::GetAccount failed, hr=0x%x\n",
      "com\\complus\\dtc\\shared\\util\\security.cpp",
      3064,
      v12);
    v20 = 3066;
    v21 = "SetAccountInfoInRegistryW: FAILED - pDTCService->GetAccount(...)";
LABEL_28:
    v22 = v12;
LABEL_44:
    TraceFile(v22, v21, "com\\complus\\dtc\\shared\\util\\security.cpp", v20);
    goto LABEL_45;
  }
LABEL_35:
  v23 = LookupSpecialAccount(&Str, &v29);
  v19 = v23;
  if ( v23 < 0 )
  {
    StringCchPrintfA(
      &v34,
      0x304u,
      "msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW: LookupSpecialAccount failed, hr=0x%x\n",
      "com\\complus\\dtc\\shared\\util\\security.cpp",
      3079,
      v23);
    v20 = 3081;
    v21 = "SetAccountInfoInRegistryW: LookupSpecialAccount failed";
LABEL_43:
    v22 = v19;
    goto LABEL_44;
  }
  if ( !wcschr(&Str, 0x5Cu) && v19 == 1 )
  {
    v32 = 0;
    memset_0(v33, 0, sizeof(v33));
    StringCchCopyW(&v32, 0x100u, L".\\");
    StringCchCatW(&v32, 0x100u, &Str);
    StringCchCopyW(&Str, 0x100u, &v32);
  }
  do
    ++v4;
  while ( *(_WORD *)&v31[2 * v4 - 2] );
  v24 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64, wchar_t *, int))(*(_QWORD *)a1 + 248LL))(
          a1,
          L"AccountName",
          1,
          &Str,
          2 * (int)v4 + 2);
  v19 = v24;
  if ( v24 < 0 )
  {
    StringCchPrintfA(
      &v34,
      0x304u,
      "msdtc_trace : File: %s, Line: %d, SetAccountInfoInRegistryW : SetRegKeyValue32W: failed to set a registry value, hr=0x%x\n",
      "com\\complus\\dtc\\shared\\util\\security.cpp",
      3101,
      v24);
    v20 = 3103;
    v21 = "SetAccountInfoInRegistryW : SetRegKeyValue32W: failed to set a registry value.";
    goto LABEL_43;
  }
LABEL_45:
  if ( v5 )
    CService::Release((CService *)v5);
  if ( v19 < 0 )
    DtcWriteToEventLoggerA(1u, 8u, 0xC0001156, 0, 0, &v34, v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180073390  mov     [rsp-8+arg_10], rbx
0x180073395  push    rbp
0x180073396  push    rsi
0x180073397  push    rdi
0x180073398  push    r12
0x18007339a  push    r13
0x18007339c  push    r14
0x18007339e  push    r15
0x1800733a0  lea     rbp, [rsp-670h]
0x1800733a8  sub     rsp, 770h
0x1800733af  mov     rax, cs:__security_cookie
0x1800733b6  xor     rax, rsp
0x1800733b9  mov     [rbp+6A0h+var_40], rax
0x1800733c0  mov     rbx, rdx
0x1800733c3  mov     r12, rcx
0x1800733c6  xor     esi, esi
0x1800733c8  lea     rcx, [rsp+7A0h+var_74E]; void *
0x1800733cd  xor     edx, edx; Val
0x1800733cf  mov     [rsp+7A0h+Str], si
0x1800733d4  mov     r8d, 1FEh; Size
0x1800733da  call    memset_0
0x1800733df  xor     edx, edx; Val
0x1800733e1  mov     [rbp+6A0h+var_350], sil
0x1800733e8  mov     r8d, 303h; Size
0x1800733ee  lea     rcx, [rbp+6A0h+var_34F]; void *
0x1800733f5  call    memset_0
0x1800733fa  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800733fe  mov     [rsp+7A0h+var_758], rsi
0x180073403  mov     r13d, esi
0x180073406  test    rbx, rbx
0x180073409  jnz     loc_180073608
0x18007340f  lea     ecx, [rsi+18h]; Size
0x180073412  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073417  mov     [rsp+7A0h+Size], rax
0x18007341c  mov     rdi, rax
0x18007341f  test    rax, rax
0x180073422  jz      loc_1800735C7
0x180073428  mov     dword ptr [rax], 1
0x18007342e  mov     [rax+8], rsi
0x180073432  mov     [rax+10h], rsi
0x180073436  test    rax, rax
0x180073439  jz      loc_1800735C7
0x18007343f  mov     rcx, rax; this
0x180073442  call    ?InternalInit@CService@@IEAAJPEAGPEAVCServiceControlManager@@K0@Z; CService::InternalInit(ushort *,CServiceControlManager *,ulong,ushort *)
0x180073447  mov     ebx, eax
0x180073449  test    eax, eax
0x18007344b  jns     short loc_18007346A
0x18007344d  mov     r9d, 13Ch; unsigned int
0x180073453  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x18007345a  lea     rdx, aCserviceIntern; "CService::InternalInit call failed"
0x180073461  mov     ecx, eax; int
0x180073463  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180073468  jmp     short loc_180073470
0x18007346a  mov     r13, rdi
0x18007346d  lock inc dword ptr [rdi]
0x180073470  mov     rcx, rdi; this
0x180073473  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x180073478  test    ebx, ebx
0x18007347a  js      loc_1800735CC
0x180073480  mov     ebx, esi
0x180073482  mov     dword ptr [rsp+7A0h+Size], 40h ; '@'
0x18007348a  mov     rdi, rsi
0x18007348d  mov     esi, 2
0x180073492  mov     r14d, 100h
0x180073498  test    esi, esi
0x18007349a  jz      loc_18007359D
0x1800734a0  test    rdi, rdi
0x1800734a3  jz      short loc_1800734AD
0x1800734a5  mov     rcx, rdi; Block
0x1800734a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800734ad  mov     ecx, dword ptr [rsp+7A0h+Size]; unsigned __int64
0x1800734b1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800734b6  mov     rdi, rax
0x1800734b9  test    rax, rax
0x1800734bc  jz      loc_180073594
0x1800734c2  mov     r8d, dword ptr [rsp+7A0h+Size]; Size
0x1800734c7  xor     edx, edx; Val
0x1800734c9  mov     rcx, rax; void *
0x1800734cc  call    memset_0
0x1800734d1  mov     r8d, dword ptr [rsp+7A0h+Size]; cbBufSize
0x1800734d6  lea     r9, [rsp+7A0h+Size]; pcbBytesNeeded
0x1800734db  mov     rcx, [r13+10h]; hService
0x1800734df  mov     rdx, rdi; lpServiceConfig
0x1800734e2  call    cs:__imp_QueryServiceConfigW
0x1800734e8  test    eax, eax
0x1800734ea  jnz     short loc_180073510
0x1800734ec  call    cs:__imp_GetLastError
0x1800734f2  test    eax, eax
0x1800734f4  jg      short loc_1800734FA
0x1800734f6  mov     ebx, eax
0x1800734f8  jmp     short loc_180073503
0x1800734fa  movzx   ebx, ax
0x1800734fd  or      ebx, 80070000h
0x180073503  cmp     eax, 7Ah ; 'z'
0x180073506  jnz     loc_18007359D
0x18007350c  dec     esi
0x18007350e  jmp     short loc_180073492
0x180073510  xor     esi, esi
0x180073512  mov     ebx, esi
0x180073514  mov     r8, [rdi+30h]; unsigned __int16 *
0x180073518  test    r8, r8
0x18007351b  jz      short loc_18007353E
0x18007351d  mov     rax, r15
0x180073520  inc     rax
0x180073523  cmp     [r8+rax*2], si
0x180073528  jnz     short loc_180073520
0x18007352a  inc     eax
0x18007352c  cmp     eax, r14d
0x18007352f  ja      short loc_18007353E
0x180073531  mov     rdx, r14; unsigned __int64
0x180073534  lea     rcx, [rsp+7A0h+Str]; unsigned __int16 *
0x180073539  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007353e  test    rdi, rdi
0x180073541  jz      short loc_18007354B
0x180073543  mov     rcx, rdi; Block
0x180073546  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007354b  test    ebx, ebx
0x18007354d  jns     loc_18007361E
0x180073553  mov     dword ptr [rsp+7A0h+var_778], ebx
0x180073557  lea     r9, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x18007355e  lea     r8, aMsdtcTraceFile_0; "msdtc_trace : File: %s, Line: %d, SetAc"...
0x180073565  mov     dword ptr [rsp+7A0h+var_780], 0BF8h
0x18007356d  mov     edx, 304h; unsigned __int64
0x180073572  lea     rcx, [rbp+6A0h+var_350]; char *
0x180073579  mov     edi, ebx
0x18007357b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180073580  mov     r9d, 0BFAh
0x180073586  lea     rdx, aSetaccountinfo_2; "SetAccountInfoInRegistryW: FAILED - pDT"...
0x18007358d  mov     ecx, ebx
0x18007358f  jmp     loc_180073763
0x180073594  mov     ebx, 8007000Eh
0x180073599  xor     esi, esi
0x18007359b  jmp     short loc_1800735A7
0x18007359d  xor     esi, esi
0x18007359f  test    ebx, ebx
0x1800735a1  jns     loc_180073514
0x1800735a7  mov     r9d, 1E8h; unsigned int
0x1800735ad  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x1800735b4  lea     rdx, aQueryserviceco_1; "QueryServiceConfigW call failed"
0x1800735bb  mov     ecx, ebx; int
0x1800735bd  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800735c2  jmp     loc_18007353E
0x1800735c7  mov     ebx, 8007000Eh
0x1800735cc  mov     dword ptr [rsp+7A0h+var_778], ebx
0x1800735d0  lea     r9, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x1800735d7  lea     r8, aMsdtcTraceFile_1; "msdtc_trace : File: %s, Line: %d, SetAc"...
0x1800735de  mov     dword ptr [rsp+7A0h+var_780], 0BEEh
0x1800735e6  mov     edx, 304h; unsigned __int64
0x1800735eb  lea     rcx, [rbp+6A0h+var_350]; char *
0x1800735f2  mov     edi, ebx
0x1800735f4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800735f9  mov     r9d, 0BF0h
0x1800735ff  lea     rdx, aSetaccountinfo_1; "SetAccountInfoInRegistryW: CService::Cr"...
0x180073606  jmp     short loc_18007358D
0x180073608  mov     r14d, 100h
0x18007360e  lea     rcx, [rsp+7A0h+Str]; unsigned __int16 *
0x180073613  mov     edx, r14d; unsigned __int64
0x180073616  mov     r8, rbx; unsigned __int16 *
0x180073619  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007361e  lea     rdx, [rsp+7A0h+var_758]; struct _SPECIAL_ACCOUNT_ **
0x180073623  lea     rcx, [rsp+7A0h+Str]; unsigned __int16 *
0x180073628  call    ?LookupSpecialAccount@@YAJPEBGPEAPEAU_SPECIAL_ACCOUNT_@@@Z; LookupSpecialAccount(ushort const *,_SPECIAL_ACCOUNT_ * *)
0x18007362d  mov     edi, eax
0x18007362f  test    eax, eax
0x180073631  jns     short loc_180073670
0x180073633  mov     dword ptr [rsp+7A0h+var_778], eax
0x180073637  lea     r9, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x18007363e  lea     r8, aMsdtcTraceFile_2; "msdtc_trace : File: %s, Line: %d, SetAc"...
0x180073645  mov     dword ptr [rsp+7A0h+var_780], 0C07h
0x18007364d  mov     edx, 304h; unsigned __int64
0x180073652  lea     rcx, [rbp+6A0h+var_350]; char *
0x180073659  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18007365e  mov     r9d, 0C09h
0x180073664  lea     rdx, aSetaccountinfo_0; "SetAccountInfoInRegistryW: LookupSpecia"...
0x18007366b  jmp     loc_180073761
0x180073670  mov     edx, 5Ch ; '\'; Ch
0x180073675  lea     rcx, [rsp+7A0h+Str]; Str
0x18007367a  call    cs:__imp_wcschr
0x180073680  test    rax, rax
0x180073683  jnz     short loc_1800736E3
0x180073685  cmp     edi, 1
0x180073688  jnz     short loc_1800736E3
0x18007368a  xor     edx, edx; Val
0x18007368c  mov     [rbp+6A0h+var_550], si
0x180073693  mov     r8d, 1FEh; Size
0x180073699  lea     rcx, [rbp+6A0h+var_54E]; void *
0x1800736a0  call    memset_0
0x1800736a5  lea     r8, asc_1800BC720; ".\\"
0x1800736ac  mov     rdx, r14; unsigned __int64
0x1800736af  lea     rcx, [rbp+6A0h+var_550]; unsigned __int16 *
0x1800736b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800736bb  lea     r8, [rsp+7A0h+Str]; unsigned __int16 *
0x1800736c0  mov     rdx, r14; unsigned __int64
0x1800736c3  lea     rcx, [rbp+6A0h+var_550]; unsigned __int16 *
0x1800736ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800736cf  lea     r8, [rbp+6A0h+var_550]; unsigned __int16 *
0x1800736d6  mov     rdx, r14; unsigned __int64
0x1800736d9  lea     rcx, [rsp+7A0h+Str]; unsigned __int16 *
0x1800736de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800736e3  lea     rax, [rsp+7A0h+Str]
0x1800736e8  inc     r15
0x1800736eb  cmp     [rax+r15*2], si
0x1800736f0  jnz     short loc_1800736E8
0x1800736f2  mov     rax, [r12]
0x1800736f6  lea     edx, ds:2[r15*2]
0x1800736fe  mov     dword ptr [rsp+7A0h+var_780], edx
0x180073702  lea     r9, [rsp+7A0h+Str]
0x180073707  mov     r8d, 1
0x18007370d  lea     rdx, aAccountname; "AccountName"
0x180073714  mov     rcx, r12
0x180073717  mov     rax, [rax+0F8h]
0x18007371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073723  mov     edi, eax
0x180073725  test    eax, eax
0x180073727  jns     short loc_18007376F
0x180073729  mov     dword ptr [rsp+7A0h+var_778], eax
0x18007372d  lea     r9, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x180073734  lea     r8, aMsdtcTraceFile; "msdtc_trace : File: %s, Line: %d, SetAc"...
0x18007373b  mov     dword ptr [rsp+7A0h+var_780], 0C1Dh
0x180073743  mov     edx, 304h; unsigned __int64
0x180073748  lea     rcx, [rbp+6A0h+var_350]; char *
0x18007374f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180073754  mov     r9d, 0C1Fh; unsigned int
0x18007375a  lea     rdx, aSetaccountinfo; "SetAccountInfoInRegistryW : SetRegKeyVa"...
0x180073761  mov     ecx, edi; int
0x180073763  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x18007376a  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18007376f  test    r13, r13
0x180073772  jz      short loc_18007377C
0x180073774  mov     rcx, r13; this
0x180073777  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x18007377c  test    edi, edi
0x18007377e  jns     short loc_1800737A6
0x180073780  xor     r9d, r9d; unsigned int
0x180073783  lea     rax, [rbp+6A0h+var_350]
0x18007378a  mov     [rsp+7A0h+var_778], rax; char *
0x18007378f  mov     r8d, 0C0001156h; unsigned int
0x180073795  mov     [rsp+7A0h+var_780], rsi; void *
0x18007379a  lea     edx, [r9+8]; unsigned int
0x18007379e  lea     ecx, [rdx-7]; unsigned int
0x1800737a1  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x1800737a6  mov     eax, edi
0x1800737a8  mov     rcx, [rbp+6A0h+var_40]
0x1800737af  xor     rcx, rsp; StackCookie
0x1800737b2  call    __security_check_cookie
0x1800737b7  mov     rbx, [rsp+7A0h+arg_10]
0x1800737bf  add     rsp, 770h
0x1800737c6  pop     r15
0x1800737c8  pop     r14
0x1800737ca  pop     r13
0x1800737cc  pop     r12
0x1800737ce  pop     rdi
0x1800737cf  pop     rsi
0x1800737d0  pop     rbp
0x1800737d1  retn
```
