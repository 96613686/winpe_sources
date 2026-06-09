# SNISecInitPackageEx

- ea: `0x1004394a8`
- end: `0x1004398e4`
- name: `SNISecInitPackageEx`
- size: `1084`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100439444`

## callees

- `0x100417768`
- `0x1004394a8`
- `0x100439fac`
- `0x10043a2d4`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100439608`
- `KERNEL32!GetLastError` at `0x10043965c`
- `KERNEL32!GetLastError` at `0x100439608`
- `KERNEL32!GetLastError` at `0x10043965c`
- `KERNEL32!GetProcAddress` at `0x1004395fd`
- `KERNEL32!GetProcAddress` at `0x1004395fd`
- `KERNEL32!FreeLibrary` at `0x1004397f2`
- `KERNEL32!FreeLibrary` at `0x1004397f2`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004396f1`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004396f1`

## string_xrefs

- `0x10043959e`: `secur32.dll`
- `0x1004395f3`: `InitSecurityInterfaceW`

## pseudocode

```c
__int64 __fastcall SNISecInitPackageEx(_DWORD *a1)
{
  struct CCriticalSectionNT_SNI *v2; // r14
  HMODULE v3; // rax
  DWORD LastError; // edi
  unsigned int v5; // ebx
  wchar_t *v6; // r8
  __int64 v7; // rdx
  __int64 (*ProcAddress)(void); // rax
  struct _SECURITY_FUNCTION_TABLE_W *v9; // rax
  char v10; // bp
  __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned int v13; // eax
  int v14; // eax
  int v15; // ecx
  __int64 v17; // [rsp+78h] [rbp+10h] BYREF
  __int64 v18; // [rsp+80h] [rbp+18h] BYREF

  v18 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7DE0[0] )
    bidScopeEnterW(&v18, off_1005E7DE0[0], a1);
  v2 = g_csSecPackageInitialize;
  qword_1005D8458 = -1;
  ghSspiCred.dwLower = -1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL);
  if ( _InterlockedIncrement(&g_cSNISecPackageInitialized) != 1 )
  {
    *a1 = g_cbSspiMaxToken;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5BA8[0] )
      bidTraceW(0, 260096, off_1005E5BA8[0], 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v2 + 2) + 32LL) + 24LL))(*((_QWORD *)v2 + 2) + 32LL);
LABEL_51:
    LastError = 0;
    goto LABEL_52;
  }
  *a1 = 0;
  v3 = SNILoadSystemLibA("secur32.dll");
  g_hSspiLib = v3;
  if ( !v3 )
  {
    LastError = -1;
    v5 = 50122;
    if ( (bidGblFlags & 2) == 0 || !off_1005E5BB0[0] )
      goto LABEL_38;
    SniErrorIdFromStringId(0xC3CAu);
    v6 = off_1005E5BB0[0];
    v7 = 281600;
    goto LABEL_37;
  }
  ProcAddress = GetProcAddress(v3, "InitSecurityInterfaceW");
  if ( !ProcAddress )
  {
    v5 = 50100;
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_1005E5BB8[0] )
      goto LABEL_38;
    SniErrorIdFromStringId(0xC3B4u);
    v6 = off_1005E5BB8[0];
    v7 = 295936;
    goto LABEL_37;
  }
  v9 = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
  g_pFuncs = v9;
  if ( !v9 )
  {
    v5 = 50100;
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_1005E5BC0[0] )
      goto LABEL_38;
    SniErrorIdFromStringId(0xC3B4u);
    v6 = off_1005E5BC0[0];
    v7 = 308224;
    goto LABEL_37;
  }
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    LastError = ((__int64 (__fastcall *)(unsigned __int16 * near *, __int64 *))v9->QuerySecurityPackageInfoW)(
                  (&g_rgszSSP)[v11],
                  &v17);
    if ( !LastError )
    {
      *((_DWORD *)&g_rgfSSPIPackageAvailable + v11) = 1;
      if ( v10 )
      {
        v12 = v17;
        v13 = g_cbSspiMaxToken;
      }
      else
      {
        memcpy_s(&g_szSSP, 0x28u, (&g_rgszSSP)[v11], *((int *)&g_rgcchSSP + v11));
        v12 = v17;
        v10 = 1;
        v13 = *(_DWORD *)(v17 + 8);
        g_cbSspiMaxToken = v13;
      }
      if ( (v11 & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
      {
        if ( *(_DWORD *)(v12 + 8) > v13 )
          v13 = *(_DWORD *)(v12 + 8);
        g_cbSspiMaxToken = v13;
      }
      ((void (*)(void))g_pFuncs->FreeContextBuffer)();
    }
    if ( ++v11 >= 3 )
      break;
    v9 = g_pFuncs;
  }
  if ( v10 )
  {
    v14 = SNI_Spn::SpnInit();
    v15 = g_fSPNInitialized;
    if ( !v14 )
      v15 = 1;
    g_fSPNInitialized = v15;
    *a1 = g_cbSspiMaxToken;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v2 + 2) + 32LL) + 24LL))(*((_QWORD *)v2 + 2) + 32LL);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5BD0[0] )
      bidTraceW(0, 377856, off_1005E5BD0[0], 0);
    goto LABEL_51;
  }
  v5 = 50100;
  if ( (bidGblFlags & 2) != 0 && off_1005E5BC8[0] )
  {
    SniErrorIdFromStringId(0xC3B4u);
    v6 = off_1005E5BC8[0];
    v7 = 354304;
LABEL_37:
    bidTraceW(0, v7, v6, 9);
  }
LABEL_38:
  SNISetLastError(9, LastError, v5);
  if ( ghSspiCred.dwLower != -1 && qword_1005D8458 != -1 )
  {
    ((void (__fastcall *)(struct _SecHandle *))g_pFuncs->FreeCredentialsHandle)(&ghSspiCred);
    qword_1005D8458 = -1;
    ghSspiCred.dwLower = -1;
  }
  if ( g_hSspiLib )
    FreeLibrary(g_hSspiLib);
  SNI_Spn::SpnTerminate();
  _InterlockedAdd(&g_cSNISecPackageInitialized, 0xFFFFFFFF);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v2 + 2) + 32LL) + 24LL))(*((_QWORD *)v2 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5BD8[0] )
    bidTraceW(0, 403456, off_1005E5BD8[0], LastError);
LABEL_52:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v18);
  return LastError;
}

```

## disassembly

```asm
0x1004394a8  mov     r11, rsp
0x1004394ab  mov     [r11+8], rbx
0x1004394af  push    rbp
0x1004394b0  push    rsi
0x1004394b1  push    rdi
0x1004394b2  push    r12
0x1004394b4  push    r13
0x1004394b6  push    r14
0x1004394b8  push    r15
0x1004394ba  sub     rsp, 30h
0x1004394be  mov     eax, cs:_bidGblFlags
0x1004394c4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1004394c8  mov     rsi, rcx
0x1004394cb  mov     [r11+18h], r15
0x1004394cf  mov     ecx, 20004h
0x1004394d4  and     eax, ecx
0x1004394d6  cmp     eax, ecx
0x1004394d8  jnz     short loc_1004394F9
0x1004394da  mov     rax, cs:off_1005E7DE0; "<SNISecInitPackageEx|API|SNI> pcbMaxTok"...
0x1004394e1  test    rax, rax
0x1004394e4  jz      short loc_1004394F9
0x1004394e6  mov     rdx, cs:off_1005E7DE0; "<SNISecInitPackageEx|API|SNI> pcbMaxTok"...
0x1004394ed  lea     rcx, [r11+18h]
0x1004394f1  mov     r8, rsi
0x1004394f4  call    _bidScopeEnterW
0x1004394f9  mov     r14, cs:?g_csSecPackageInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csSecPackageInitialize
0x100439500  mov     cs:qword_1005D8458, r15
0x100439507  mov     cs:?ghSspiCred@@3U_SecHandle@@A, r15; _SecHandle ghSspiCred
0x10043950e  mov     rcx, [r14+10h]
0x100439512  add     rcx, 20h ; ' '
0x100439516  mov     rax, [rcx]
0x100439519  mov     rax, [rax+8]
0x10043951d  call    cs:__guard_dispatch_icall_fptr
0x100439523  mov     r12d, 1
0x100439529  mov     eax, r12d
0x10043952c  lock xadd cs:?g_cSNISecPackageInitialized@@3JA, eax; long g_cSNISecPackageInitialized
0x100439534  add     eax, r12d
0x100439537  cmp     eax, r12d
0x10043953a  jz      short loc_10043959B
0x10043953c  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x100439542  mov     ecx, 20002h
0x100439547  mov     [rsi], eax
0x100439549  mov     eax, cs:_bidGblFlags
0x10043954f  and     eax, ecx
0x100439551  cmp     eax, ecx
0x100439553  jnz     short loc_100439581
0x100439555  mov     rax, cs:off_1005E5BA8; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x10043955c  test    rax, rax
0x10043955f  jz      short loc_100439581
0x100439561  mov     eax, cs:?g_cSNISecPackageInitialized@@3JA; long g_cSNISecPackageInitialized
0x100439567  xor     r9d, r9d
0x10043956a  mov     r8, cs:off_1005E5BA8; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x100439571  mov     edx, 3F800h
0x100439576  xor     ecx, ecx
0x100439578  mov     [rsp+68h+var_48], eax
0x10043957c  call    _bidTraceW
0x100439581  mov     rcx, [r14+10h]
0x100439585  add     rcx, 20h ; ' '
0x100439589  mov     rax, [rcx]
0x10043958c  mov     rax, [rax+18h]
0x100439590  call    cs:__guard_dispatch_icall_fptr
0x100439596  jmp     loc_1004398BE
0x10043959b  and     dword ptr [rsi], 0
0x10043959e  lea     rcx, aSecur32Dll_0; "secur32.dll"
0x1004395a5  call    SNILoadSystemLibA
0x1004395aa  mov     cs:?g_hSspiLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hSspiLib
0x1004395b1  test    rax, rax
0x1004395b4  jnz     short loc_1004395F3
0x1004395b6  or      edi, 0FFFFFFFFh
0x1004395b9  mov     ebx, 0C3CAh
0x1004395be  test    byte ptr cs:_bidGblFlags, 2
0x1004395c5  jz      loc_10043979F
0x1004395cb  mov     rax, cs:off_1005E5BB0; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x1004395d2  test    rax, rax
0x1004395d5  jz      loc_10043979F
0x1004395db  mov     ecx, ebx; unsigned int
0x1004395dd  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004395e2  mov     r8, cs:off_1005E5BB0; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x1004395e9  mov     edx, 44C00h
0x1004395ee  jmp     loc_10043978A
0x1004395f3  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x1004395fa  mov     rcx, rax; hModule
0x1004395fd  call    cs:__imp_GetProcAddress
0x100439603  test    rax, rax
0x100439606  jnz     short loc_10043964A
0x100439608  call    cs:__imp_GetLastError
0x10043960e  test    byte ptr cs:_bidGblFlags, 2
0x100439615  mov     ebx, 0C3B4h
0x10043961a  mov     edi, eax
0x10043961c  jz      loc_10043979F
0x100439622  mov     rax, cs:off_1005E5BB8; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x100439629  test    rax, rax
0x10043962c  jz      loc_10043979F
0x100439632  mov     ecx, ebx; unsigned int
0x100439634  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100439639  mov     r8, cs:off_1005E5BB8; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x100439640  mov     edx, 48400h
0x100439645  jmp     loc_10043978A
0x10043964a  call    cs:__guard_dispatch_icall_fptr
0x100439650  mov     cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100439657  test    rax, rax
0x10043965a  jnz     short loc_10043969E
0x10043965c  call    cs:__imp_GetLastError
0x100439662  test    byte ptr cs:_bidGblFlags, 2
0x100439669  mov     ebx, 0C3B4h
0x10043966e  mov     edi, eax
0x100439670  jz      loc_10043979F
0x100439676  mov     rax, cs:off_1005E5BC0; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x10043967d  test    rax, rax
0x100439680  jz      loc_10043979F
0x100439686  mov     ecx, ebx; unsigned int
0x100439688  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10043968d  mov     r8, cs:off_1005E5BC0; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x100439694  mov     edx, 4B400h
0x100439699  jmp     loc_10043978A
0x10043969e  xor     bpl, bpl
0x1004396a1  lea     r13, __ImageBase
0x1004396a8  xor     ebx, ebx
0x1004396aa  mov     rcx, rva ?g_rgszSSP@@3PAPEAGA[r13+rbx*8]; ushort * near * g_rgszSSP ...
0x1004396b2  lea     rdx, [rsp+68h+arg_8]
0x1004396b7  mov     rax, [rax+88h]
0x1004396be  call    cs:__guard_dispatch_icall_fptr
0x1004396c4  mov     edi, eax
0x1004396c6  test    eax, eax
0x1004396c8  jnz     short loc_10043973F
0x1004396ca  mov     rva ?g_rgfSSPIPackageAvailable@@3PAHA[r13+rbx*4], r12d; int near * g_rgfSSPIPackageAvailable ...
0x1004396d2  test    bpl, bpl
0x1004396d5  jnz     short loc_10043970A
0x1004396d7  movsxd  r9, rva ?g_rgcchSSP@@3PAHA[r13+rbx*4]; SourceSize
0x1004396df  lea     edx, [rax+28h]; DestinationSize
0x1004396e2  mov     r8, rva ?g_rgszSSP@@3PAPEAGA[r13+rbx*8]; Source
0x1004396ea  lea     rcx, ?g_szSSP@@3PAGA; Destination
0x1004396f1  call    cs:__imp_memcpy_s
0x1004396f7  mov     rcx, [rsp+68h+arg_8]
0x1004396fc  mov     bpl, r12b
0x1004396ff  mov     eax, [rcx+8]
0x100439702  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x100439708  jmp     short loc_100439715
0x10043970a  mov     rcx, [rsp+68h+arg_8]
0x10043970f  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x100439715  test    rbx, 0FFFFFFFFFFFFFFFDh
0x10043971c  jnz     short loc_10043972B
0x10043971e  cmp     [rcx+8], eax
0x100439721  cmova   eax, [rcx+8]
0x100439725  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x10043972b  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100439732  mov     rax, [rax+80h]
0x100439739  call    cs:__guard_dispatch_icall_fptr
0x10043973f  add     rbx, r12
0x100439742  cmp     rbx, 3
0x100439746  jge     short loc_100439754
0x100439748  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10043974f  jmp     loc_1004396AA
0x100439754  test    bpl, bpl
0x100439757  jnz     loc_100439857
0x10043975d  test    byte ptr cs:_bidGblFlags, 2
0x100439764  mov     ebx, 0C3B4h
0x100439769  jz      short loc_10043979F
0x10043976b  mov     rax, cs:off_1005E5BC8; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x100439772  test    rax, rax
0x100439775  jz      short loc_10043979F
0x100439777  mov     ecx, ebx; unsigned int
0x100439779  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10043977e  mov     r8, cs:off_1005E5BC8; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x100439785  mov     edx, 56800h
0x10043978a  mov     [rsp+68h+var_40], edi
0x10043978e  mov     r9d, 9
0x100439794  xor     ecx, ecx
0x100439796  mov     [rsp+68h+var_48], eax
0x10043979a  call    _bidTraceW
0x10043979f  mov     r8d, ebx
0x1004397a2  mov     edx, edi
0x1004397a4  mov     ecx, 9
0x1004397a9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004397ae  cmp     cs:?ghSspiCred@@3U_SecHandle@@A, r15; _SecHandle ghSspiCred
0x1004397b5  jz      short loc_1004397E6
0x1004397b7  cmp     cs:qword_1005D8458, r15
0x1004397be  jz      short loc_1004397E6
0x1004397c0  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x1004397c7  lea     rcx, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x1004397ce  mov     rax, [rax+20h]
0x1004397d2  call    cs:__guard_dispatch_icall_fptr
0x1004397d8  mov     cs:qword_1005D8458, r15
0x1004397df  mov     cs:?ghSspiCred@@3U_SecHandle@@A, r15; _SecHandle ghSspiCred
0x1004397e6  mov     rcx, cs:?g_hSspiLib@@3PEAUHINSTANCE__@@EA; hLibModule
0x1004397ed  test    rcx, rcx
0x1004397f0  jz      short loc_1004397F8
0x1004397f2  call    cs:__imp_FreeLibrary
0x1004397f8  call    ?SpnTerminate@SNI_Spn@@SAXXZ; SNI_Spn::SpnTerminate(void)
0x1004397fd  lock add cs:?g_cSNISecPackageInitialized@@3JA, r15d; long g_cSNISecPackageInitialized
0x100439805  mov     rcx, [r14+10h]
0x100439809  add     rcx, 20h ; ' '
0x10043980d  mov     rax, [rcx]
0x100439810  mov     rax, [rax+18h]
0x100439814  call    cs:__guard_dispatch_icall_fptr
0x10043981a  mov     eax, cs:_bidGblFlags
0x100439820  mov     ecx, 20002h
0x100439825  and     eax, ecx
0x100439827  cmp     eax, ecx
0x100439829  jnz     loc_1004398C0
0x10043982f  mov     rax, cs:off_1005E5BD8; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x100439836  test    rax, rax
0x100439839  jz      loc_1004398C0
0x10043983f  mov     r8, cs:off_1005E5BD8; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x100439846  mov     r9d, edi
0x100439849  mov     edx, 62800h
0x10043984e  xor     ecx, ecx
0x100439850  call    _bidTraceW
0x100439855  jmp     short loc_1004398C0
0x100439857  call    ?SpnInit@SNI_Spn@@SAKXZ; SNI_Spn::SpnInit(void)
0x10043985c  mov     ecx, cs:?g_fSPNInitialized@@3HA; int g_fSPNInitialized
0x100439862  test    eax, eax
0x100439864  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x10043986a  cmovz   ecx, r12d
0x10043986e  mov     cs:?g_fSPNInitialized@@3HA, ecx; int g_fSPNInitialized
0x100439874  mov     [rsi], eax
0x100439876  mov     rcx, [r14+10h]
0x10043987a  add     rcx, 20h ; ' '
0x10043987e  mov     rax, [rcx]
0x100439881  mov     rax, [rax+18h]
0x100439885  call    cs:__guard_dispatch_icall_fptr
0x10043988b  mov     eax, cs:_bidGblFlags
0x100439891  mov     ecx, 20002h
0x100439896  and     eax, ecx
0x100439898  cmp     eax, ecx
0x10043989a  jnz     short loc_1004398BE
0x10043989c  mov     rax, cs:off_1005E5BD0; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x1004398a3  test    rax, rax
0x1004398a6  jz      short loc_1004398BE
0x1004398a8  mov     r8, cs:off_1005E5BD0; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x1004398af  xor     r9d, r9d
0x1004398b2  mov     edx, 5C400h
0x1004398b7  xor     ecx, ecx
0x1004398b9  call    _bidTraceW
0x1004398be  xor     edi, edi
0x1004398c0  lea     rcx, [rsp+68h+arg_10]; this
0x1004398c8  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004398cd  mov     rbx, [rsp+68h+arg_0]
0x1004398d2  mov     eax, edi
0x1004398d4  add     rsp, 30h
0x1004398d8  pop     r15
0x1004398da  pop     r14
0x1004398dc  pop     r13
0x1004398de  pop     r12
0x1004398e0  pop     rdi
0x1004398e1  pop     rsi
0x1004398e2  pop     rbp
0x1004398e3  retn
```
