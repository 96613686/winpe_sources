# NCryptOpenStorageProvider

- ea: `0x1800102c0`
- end: `0x18001067d`
- name: `NCryptOpenStorageProvider`
- size: `957`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE *phProvider, LPCWSTR pszProviderName, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18000fb20`

## callees

- `0x180001008`
- `0x180001044`
- `0x180007ca0`
- `0x180007d50`
- `0x180007df4`
- `0x180009cd0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x18000f098`
- `0x1800102c0`
- `0x180016dbc`
- `0x180018350`
- `0x180018e18`
- `0x18001f15d`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180010576`
- `ntdll!RtlDllShutdownInProgress` at `0x180010576`
- `bcrypt!BCryptResolveProviders` at `0x180010388`
- `bcrypt!BCryptResolveProviders` at `0x180010388`
- `bcrypt!BCryptFreeBuffer` at `0x180010648`
- `bcrypt!BCryptFreeBuffer` at `0x180010648`

## string_xrefs

- `0x1800104bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptOpenStorageProvider(
        NCRYPT_PROV_HANDLE *phProvider,
        LPCWSTR pszProviderName,
        DWORD dwFlags)
{
  NCRYPT_PROV_HANDLE v4; // rbx
  const WCHAR *pszProvider; // rdi
  NTSTATUS Provider; // r14d
  __int64 v8; // r9
  unsigned int v9; // esi
  __int64 v10; // rax
  unsigned int v11; // eax
  size_t v12; // r14
  void *v13; // rax
  PWSTR v14; // rdx
  const size_t *v15; // rsi
  __int64 ProcessName; // rax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp-99h] BYREF
  ULONG pcbBuffer; // [rsp+48h] [rbp-91h] BYREF
  NTSTATUS v24; // [rsp+4Ch] [rbp-8Dh] BYREF
  DWORD v25; // [rsp+50h] [rbp-89h] BYREF
  __int64 v26; // [rsp+58h] [rbp-81h] BYREF
  __int64 v27; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp-69h] BYREF
  __int64 *v29; // [rsp+90h] [rbp-49h]
  __int64 v30; // [rsp+98h] [rbp-41h]
  __int64 *v31; // [rsp+A0h] [rbp-39h]
  __int64 v32; // [rsp+A8h] [rbp-31h]
  NTSTATUS *v33; // [rsp+B0h] [rbp-29h]
  __int64 v34; // [rsp+B8h] [rbp-21h]
  char v35[16]; // [rsp+C0h] [rbp-19h] BYREF
  DWORD *v36; // [rsp+D0h] [rbp-9h]
  __int64 v37; // [rsp+D8h] [rbp-1h]
  char v38[16]; // [rsp+E0h] [rbp+7h] BYREF

  v4 = 0;
  ppBuffer = 0;
  pcbBuffer = 0;
  pszProvider = pszProviderName;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids,
      (_DWORD)phProvider,
      (__int64)pszProviderName,
      dwFlags);
  if ( phProvider )
  {
    *phProvider = 0;
    Provider = BCryptResolveProviders(0, 0x10001u, L"KEY_STORAGE", pszProvider, 1u, 0, &pcbBuffer, &ppBuffer);
    if ( Provider >= 0 )
    {
      if ( pszProvider && *pszProvider || (v9 = 0, (pszProvider = (*ppBuffer->rgpProviders)->pszProvider) != 0) )
      {
        v10 = -1;
        do
          ++v10;
        while ( pszProvider[v10] );
        v9 = 2 * v10 + 2;
      }
      v11 = v9 + 288;
      if ( v9 < 0xFFFFFEE0 )
      {
        v12 = v11;
        v13 = (void *)SafeAllocaAllocateFromHeap(v11);
        v4 = (NCRYPT_PROV_HANDLE)v13;
        if ( v13 )
        {
          memset_0(v13, 0, v12);
          if ( v9 )
          {
            *(_QWORD *)(v4 + 280) = v4 + 288;
            memcpy_0((void *)(v4 + 288), pszProvider, v9);
          }
          else
          {
            *(_QWORD *)(v4 + 280) = 0;
          }
          Provider = LoadProviderEx(*ppBuffer->rgpProviders, v4 + 16, 256, v4 + 8, v4 + 16);
          if ( Provider >= 0 )
          {
            if ( pszProvider )
              v14 = (PWSTR)pszProvider;
            else
              v14 = (*ppBuffer->rgpProviders)->pszProvider;
            Provider = (*(__int64 (__fastcall **)(NCRYPT_PROV_HANDLE, PWSTR, _QWORD))(v4 + 24))(v4 + 272, v14, dwFlags);
            if ( Provider >= 0 )
            {
              *(_DWORD *)v4 = 1145307137;
              Provider = 0;
              *(_DWORD *)(v4 + 4) = 1;
              *phProvider = v4;
              goto LABEL_44;
            }
            v8 = 960;
          }
          else
          {
            v8 = 944;
          }
        }
        else
        {
          Provider = -2146893810;
          v8 = 914;
        }
      }
      else
      {
        Provider = -1073741675;
        v8 = 905;
      }
    }
    else
    {
      v8 = 882;
    }
  }
  else
  {
    Provider = -2146893785;
    v8 = 860;
  }
  DebugTraceError(
    (unsigned int)Provider,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
    v8);
  if ( v4 )
  {
    if ( *(_QWORD *)(v4 + 8) )
    {
      if ( *(_QWORD *)(v4 + 272) )
        (*(void (**)(void))(v4 + 96))();
      UnloadProvider(*(_QWORD *)(v4 + 8));
    }
    v15 = *(const size_t **)(v4 + 280);
    if ( !v15 )
    {
      if ( pszProvider )
        LODWORD(v15) = (_DWORD)pszProvider;
      else
        v15 = &LocaleName;
    }
  }
  else
  {
    v15 = &LocaleName;
    if ( pszProvider )
      LODWORD(v15) = (_DWORD)pszProvider;
  }
  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) != 0 )
  {
    ProcessName = I_GetProcessName();
    McTemplateU0zdz_EventWriteTransfer(v18, v17, (_DWORD)v15, Provider, ProcessName);
  }
  if ( v4 )
    MSCryptFree(v4);
LABEL_44:
  if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline()
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_18002A078 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18002A078, 0x400000000000LL) )
  {
    v26 = 1;
    v29 = &v26;
    v27 = 0x1000000;
    v31 = &v27;
    v30 = 8;
    v33 = &v24;
    v32 = 8;
    v24 = Provider;
    v34 = 4;
    tlgCreate1Sz_wchar_t(v35, pszProvider);
    v25 = dwFlags;
    v36 = &v25;
    v37 = 4;
    tlgCreate1Sz_wchar_t(v38, g_processImageNameNcrypt);
    tlgWriteAgg((unsigned int)v28, (unsigned int)&word_18002456E, v19, v20, (__int64)v28);
  }
  if ( ppBuffer )
    BCryptFreeBuffer(ppBuffer);
  return NormalizeNteStatus((unsigned int)Provider);
}

```

## disassembly

```asm
0x1800102c0  mov     [rsp-8+arg_18], rbx
0x1800102c5  push    rbp
0x1800102c6  push    rsi
0x1800102c7  push    rdi
0x1800102c8  push    r12
0x1800102ca  push    r13
0x1800102cc  push    r14
0x1800102ce  push    r15
0x1800102d0  lea     rbp, [rsp-27h]
0x1800102d5  sub     rsp, 100h
0x1800102dc  mov     rax, cs:__security_cookie
0x1800102e3  xor     rax, rsp
0x1800102e6  mov     [rbp+57h+var_40], rax
0x1800102ea  xor     r13d, r13d
0x1800102ed  mov     r12d, r8d
0x1800102f0  mov     ebx, r13d
0x1800102f3  mov     [rsp+130h+var_F0], r13
0x1800102f8  mov     [rsp+130h+var_E8], r13d
0x1800102fd  mov     rdi, rdx
0x180010300  mov     r15, rcx
0x180010303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001030a  lea     rax, WPP_GLOBAL_Control
0x180010311  cmp     rcx, rax
0x180010314  jz      short loc_18001033D
0x180010316  test    byte ptr [rcx+1Ch], 4
0x18001031a  jz      short loc_18001033D
0x18001031c  mov     rcx, [rcx+10h]
0x180010320  lea     edx, [r13+0Dh]
0x180010324  mov     [rsp+130h+dwFlags], r8d
0x180010329  mov     r9, r15
0x18001032c  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids
0x180010333  mov     qword ptr [rsp+130h+dwMode], rdi
0x180010338  call    WPP_SF_qSD
0x18001033d  test    r15, r15
0x180010340  jnz     short loc_180010353
0x180010342  mov     r14d, 80090027h
0x180010348  mov     r9d, 35Ch
0x18001034e  jmp     loc_1800104BD
0x180010353  lea     rax, [rsp+130h+var_F0]
0x180010358  mov     [r15], r13
0x18001035b  mov     [rsp+130h+ppBuffer], rax; ppBuffer
0x180010360  lea     r8, pszFunction; "KEY_STORAGE"
0x180010367  lea     rax, [rsp+130h+var_E8]
0x18001036c  mov     r9, rdi; pszProvider
0x18001036f  mov     [rsp+130h+pcbBuffer], rax; pcbBuffer
0x180010374  mov     edx, 10001h; dwInterface
0x180010379  mov     [rsp+130h+dwFlags], r13d; dwFlags
0x18001037e  xor     ecx, ecx; pszContext
0x180010380  mov     [rsp+130h+dwMode], 1; dwMode
0x180010388  call    cs:__imp_BCryptResolveProviders
0x18001038e  mov     r14d, eax
0x180010391  test    eax, eax
0x180010393  jns     short loc_1800103A0
0x180010395  mov     r9d, 372h
0x18001039b  jmp     loc_1800104BD
0x1800103a0  test    rdi, rdi
0x1800103a3  jz      short loc_1800103AB
0x1800103a5  cmp     r13w, [rdi]
0x1800103a9  jnz     short loc_1800103C3
0x1800103ab  mov     rax, [rsp+130h+var_F0]
0x1800103b0  mov     esi, r13d
0x1800103b3  mov     rcx, [rax+8]
0x1800103b7  mov     rax, [rcx]
0x1800103ba  mov     rdi, [rax+10h]
0x1800103be  test    rdi, rdi
0x1800103c1  jz      short loc_1800103D8
0x1800103c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800103c7  inc     rax
0x1800103ca  cmp     [rdi+rax*2], r13w
0x1800103cf  jnz     short loc_1800103C7
0x1800103d1  lea     esi, ds:2[rax*2]
0x1800103d8  lea     eax, [rsi+120h]
0x1800103de  cmp     eax, 120h
0x1800103e3  jnb     short loc_1800103F6
0x1800103e5  mov     r14d, 0C0000095h
0x1800103eb  mov     r9d, 389h
0x1800103f1  jmp     loc_1800104BD
0x1800103f6  mov     ecx, eax
0x1800103f8  mov     r14d, eax
0x1800103fb  call    SafeAllocaAllocateFromHeap
0x180010400  mov     rbx, rax
0x180010403  test    rax, rax
0x180010406  jnz     short loc_180010419
0x180010408  mov     r14d, 8009000Eh
0x18001040e  mov     r9d, 392h
0x180010414  jmp     loc_1800104BD
0x180010419  mov     r8, r14; Size
0x18001041c  xor     edx, edx; Val
0x18001041e  mov     rcx, rbx; void *
0x180010421  call    memset_0
0x180010426  test    esi, esi
0x180010428  jz      short loc_180010445
0x18001042a  lea     rcx, [rbx+120h]; void *
0x180010431  mov     r8d, esi; Size
0x180010434  mov     rdx, rdi; Src
0x180010437  mov     [rbx+118h], rcx
0x18001043e  call    memcpy_0
0x180010443  jmp     short loc_18001044C
0x180010445  mov     [rbx+118h], r13
0x18001044c  mov     rax, [rsp+130h+var_F0]
0x180010451  lea     rdx, [rbx+10h]
0x180010455  lea     r9, [rbx+8]
0x180010459  mov     qword ptr [rsp+130h+dwMode], rdx
0x18001045e  mov     r8d, 100h
0x180010464  mov     rcx, [rax+8]
0x180010468  mov     rcx, [rcx]
0x18001046b  call    LoadProviderEx
0x180010470  mov     r14d, eax
0x180010473  test    eax, eax
0x180010475  jns     short loc_18001047F
0x180010477  mov     r9d, 3B0h
0x18001047d  jmp     short loc_1800104BD
0x18001047f  test    rdi, rdi
0x180010482  jz      short loc_180010489
0x180010484  mov     rdx, rdi
0x180010487  jmp     short loc_180010499
0x180010489  mov     rax, [rsp+130h+var_F0]
0x18001048e  mov     rcx, [rax+8]
0x180010492  mov     rax, [rcx]
0x180010495  mov     rdx, [rax+10h]
0x180010499  mov     rax, [rbx+18h]
0x18001049d  lea     rcx, [rbx+110h]
0x1800104a4  mov     r8d, r12d
0x1800104a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ac  mov     r14d, eax
0x1800104af  test    eax, eax
0x1800104b1  jns     loc_180010556
0x1800104b7  mov     r9d, 3C0h
0x1800104bd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800104c4  mov     ecx, r14d
0x1800104c7  lea     rdx, aStatus; "Status"
0x1800104ce  call    DebugTraceError
0x1800104d3  test    rbx, rbx
0x1800104d6  jz      short loc_18001051B
0x1800104d8  cmp     [rbx+8], r13
0x1800104dc  jz      short loc_1800104FC
0x1800104de  mov     rcx, [rbx+110h]
0x1800104e5  test    rcx, rcx
0x1800104e8  jz      short loc_1800104F3
0x1800104ea  mov     rax, [rbx+60h]
0x1800104ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f3  mov     rcx, [rbx+8]
0x1800104f7  call    UnloadProvider
0x1800104fc  mov     rsi, [rbx+118h]
0x180010503  test    rsi, rsi
0x180010506  jnz     short loc_180010529
0x180010508  test    rdi, rdi
0x18001050b  jz      short loc_180010512
0x18001050d  mov     rsi, rdi
0x180010510  jmp     short loc_180010529
0x180010512  lea     rsi, LocaleName
0x180010519  jmp     short loc_180010529
0x18001051b  test    rdi, rdi
0x18001051e  lea     rsi, LocaleName
0x180010525  cmovnz  rsi, rdi
0x180010529  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x180010530  jz      short loc_180010547
0x180010532  call    I_GetProcessName
0x180010537  mov     r9d, r14d
0x18001053a  mov     qword ptr [rsp+130h+dwMode], rax
0x18001053f  mov     r8, rsi
0x180010542  call    McTemplateU0zdz_EventWriteTransfer
0x180010547  test    rbx, rbx
0x18001054a  jz      short loc_180010569
0x18001054c  mov     rcx, rbx
0x18001054f  call    MSCryptFree
0x180010554  jmp     short loc_180010569
0x180010556  mov     dword ptr [rbx], 44440001h
0x18001055c  mov     r14d, r13d
0x18001055f  mov     dword ptr [rbx+4], 1
0x180010566  mov     [r15], rbx
0x180010569  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x18001056e  test    eax, eax
0x180010570  jz      loc_18001063E
0x180010576  call    cs:__imp_RtlDllShutdownInProgress
0x18001057c  test    al, al
0x18001057e  jnz     loc_18001063E
0x180010584  mov     eax, cs:dword_18002A078
0x18001058a  cmp     eax, 5
0x18001058d  jbe     loc_18001063E
0x180010593  mov     rdx, 400000000000h
0x18001059d  lea     rcx, dword_18002A078
0x1800105a4  call    _tlgKeywordOn
0x1800105a9  test    al, al
0x1800105ab  jz      loc_18001063E
0x1800105b1  lea     rax, [rsp+130h+var_D8]
0x1800105b6  mov     [rsp+130h+var_D8], 1
0x1800105bf  mov     [rbp+57h+var_A0], rax
0x1800105c3  lea     rcx, [rbp+57h+var_70]
0x1800105c7  lea     rax, [rbp+57h+var_D0]
0x1800105cb  mov     [rbp+57h+var_D0], 1000000h
0x1800105d3  mov     [rbp+57h+var_90], rax
0x1800105d7  mov     r9d, 8
0x1800105dd  lea     rax, [rsp+130h+var_E4]
0x1800105e2  mov     [rbp+57h+var_98], r9
0x1800105e6  mov     rdx, rdi
0x1800105e9  mov     [rbp+57h+var_80], rax
0x1800105ed  mov     [rbp+57h+var_88], r9
0x1800105f1  mov     [rsp+130h+var_E4], r14d
0x1800105f6  mov     [rbp+57h+var_78], 4
0x1800105fe  call    _tlgCreate1Sz_wchar_t
0x180010603  lea     rax, [rsp+130h+var_E0]
0x180010608  mov     [rsp+130h+var_E0], r12d
0x18001060d  lea     rdx, g_processImageNameNcrypt; "UNKNOWN"
0x180010614  mov     [rbp+57h+var_60], rax
0x180010618  lea     rcx, [rbp+57h+var_50]
0x18001061c  mov     [rbp+57h+var_58], 4
0x180010624  call    _tlgCreate1Sz_wchar_t
0x180010629  lea     rcx, [rbp+57h+var_C0]
0x18001062d  lea     rdx, word_18002456E
0x180010634  mov     qword ptr [rsp+130h+dwMode], rcx
0x180010639  call    _tlgWriteAgg
0x18001063e  mov     rcx, [rsp+130h+var_F0]; pvBuffer
0x180010643  test    rcx, rcx
0x180010646  jz      short loc_18001064E
0x180010648  call    cs:__imp_BCryptFreeBuffer
0x18001064e  mov     ecx, r14d
0x180010651  call    NormalizeNteStatus
0x180010656  mov     rcx, [rbp+57h+var_40]
0x18001065a  xor     rcx, rsp; StackCookie
0x18001065d  call    __security_check_cookie
0x180010662  mov     rbx, [rsp+130h+arg_18]
0x18001066a  add     rsp, 100h
0x180010671  pop     r15
0x180010673  pop     r14
0x180010675  pop     r13
0x180010677  pop     r12
0x180010679  pop     rdi
0x18001067a  pop     rsi
0x18001067b  pop     rbp
0x18001067c  retn
```
