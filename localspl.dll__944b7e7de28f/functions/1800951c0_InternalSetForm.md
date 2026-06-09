# InternalSetForm

- ea: `0x1800951c0`
- end: `0x180095522`
- name: `InternalSetForm`
- size: `866`
- prototype: `__int64 __fastcall(struct _INISPOOLER *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180094054`
- `0x1800940cc`

## callees

- `0x1800051f0`
- `0x180005d90`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x180009630`
- `0x18000d988`
- `0x18000ec10`
- `0x18000f238`
- `0x18002ca24`
- `0x18003ea2c`
- `0x180046650`
- `0x180094534`
- `0x1800945a4`
- `0x180094738`
- `0x1800951c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095229`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800954a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800954d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095229`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800954a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800954d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009543d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009543d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800952f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800952f5`
- `SPOOLSS!DllFreeSplMem` at `0x180095371`
- `SPOOLSS!DllFreeSplMem` at `0x1800953b7`
- `SPOOLSS!DllFreeSplMem` at `0x180095371`
- `SPOOLSS!DllFreeSplMem` at `0x1800953b7`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800952c2`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800952c2`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180095461`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180095461`

## pseudocode

```c
_BOOL8 __fastcall InternalSetForm(struct _INISPOOLER *a1, __int64 a2, unsigned int a3, int *a4)
{
  __int64 v6; // r12
  int v8; // r14d
  DWORD LastError; // eax
  __int64 IniKey; // rax
  __int64 v11; // rbx
  DWORD v12; // edi
  __int128 v13; // xmm0
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  __int64 v16; // rcx
  const wchar_t *v17; // rdi
  unsigned int v18; // r12d
  const unsigned __int16 *v19; // r13
  struct _LANGPAIRNODE *v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // rcx
  unsigned __int16 v27; // [rsp+50h] [rbp-29h]
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h]
  HANDLE hToken; // [rsp+68h] [rbp-11h]
  unsigned __int8 v31[32]; // [rsp+70h] [rbp-9h] BYREF

  v29 = a2;
  hKey = 0;
  v6 = a2;
  memset(v31, 0, sizeof(v31));
  if ( !a1 )
    return 0;
  v8 = 1;
  if ( a3 - 1 > 1 )
  {
    SetLastError(0x7Cu);
    return 0;
  }
  if ( !(unsigned int)ValidateForm((unsigned __int8 *)a4, 0, a3) )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalSetForm",
      L"Specified form to add is invalid.  Error %d",
      LastError);
    return 0;
  }
  if ( !(unsigned int)ValidateObjectAccess(0, 1, 0, 0, (__int64)a1, 1) )
    return 0;
  EnterSplSem(0);
  InitializeForms(a1);
  IniKey = FindIniKey(*((_QWORD *)a1 + 9), v6, 0);
  v11 = IniKey;
  if ( !IniKey || *(_DWORD *)(IniKey + 60) == 1 || (*(_BYTE *)a4 & 1) != 0 )
  {
    SetLastError(IniKey != 0 ? 87 : 1902);
    LeaveSplSem(v26);
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalSetForm",
      L"Form '%ws' does not exist or is a built-in form.",
      v6);
    return 0;
  }
  hToken = RevertToPrinterSelf();
  if ( hToken )
  {
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)a1 + 20), 0, 0x20006u, &hKey);
    if ( !v12 )
    {
      v13 = *(_OWORD *)(a4 + 6);
      v14 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
      *(_QWORD *)v31 = *((_QWORD *)a4 + 2);
      v15 = *a4;
      *(_OWORD *)&v31[8] = v13;
      *(_DWORD *)&v31[28] = v15;
      *(_DWORD *)&v31[24] = *(_DWORD *)(v11 + 64);
      v12 = SplRegSetValue(hKey, v14, 3u, v31, 0x20u, a1);
      if ( !v12 && a3 == 2 )
      {
        if ( a4[12] == 1 )
        {
          v16 = *(_QWORD *)(v11 + 80);
          v17 = 0;
          v18 = 0;
          v27 = 0;
          v19 = 0;
          if ( v16 )
          {
            DllFreeSplMem(v16);
            *(_QWORD *)(v11 + 80) = 0;
          }
          v20 = *(struct _LANGPAIRNODE **)(v11 + 88);
          if ( v20 )
          {
            FreeLangPair(v20);
            *(_QWORD *)(v11 + 88) = 0;
          }
        }
        else
        {
          v8 = 0;
          if ( a4[12] == 2 )
          {
            v17 = (const wchar_t *)*((_QWORD *)a4 + 7);
            v18 = a4[16];
            v19 = 0;
            v27 = 0;
            if ( v17 )
            {
              v21 = *(_QWORD *)(v11 + 80);
              if ( v21 )
                DllFreeSplMem(v21);
              *(_QWORD *)(v11 + 80) = BuildResourceName(v17, v18);
            }
          }
          else
          {
            v17 = 0;
            if ( a4[12] == 4 )
            {
              v19 = (const unsigned __int16 *)*((_QWORD *)a4 + 9);
              v18 = 0;
              v27 = *((_WORD *)a4 + 40);
              AddLanguagePairNode((struct _LANGPAIRNODE **)(v11 + 88), v19, v27);
            }
            else
            {
              v19 = 0;
              v27 = 0;
              v18 = 0;
            }
          }
        }
        v22 = RegistrySetFormInfo2(
                hKey,
                *((unsigned __int16 **)a4 + 1),
                *((const char **)a4 + 5),
                v17,
                v18,
                v19,
                v27,
                v8,
                a1);
        v6 = v29;
        v12 = v22;
      }
      RegCloseKey(hKey);
      if ( !v12 )
      {
        *(_QWORD *)(v11 + 36) = *((_QWORD *)a4 + 2);
        *(_OWORD *)(v11 + 44) = *(_OWORD *)(a4 + 6);
        *(_DWORD *)(v11 + 60) = *a4;
      }
    }
    ImpersonatePrinterClient(hToken);
  }
  else
  {
    v12 = GetLastError();
  }
  if ( v12 )
  {
    LeaveSplSem(v23);
    SetLastError(v12);
    LocalSpoolerTelemetry::WriteDbgTraceError("InternalSetForm", L"SetForm operation failed for form '%ws'", v6);
  }
  else
  {
    SetPrinterChange(0, 0, 0, 0x20000, (__int64)a1);
    BroadcastChangeForms(a1);
    LeaveSplSem(v24);
  }
  return v12 == 0;
}

```

## disassembly

```asm
0x1800951c0  mov     [rsp-8+arg_10], rbx
0x1800951c5  push    rbp
0x1800951c6  push    rsi
0x1800951c7  push    rdi
0x1800951c8  push    r12
0x1800951ca  push    r13
0x1800951cc  push    r14
0x1800951ce  push    r15
0x1800951d0  lea     rbp, [rsp-27h]
0x1800951d5  sub     rsp, 0A0h
0x1800951dc  mov     rax, cs:__security_cookie
0x1800951e3  xor     rax, rsp
0x1800951e6  mov     [rbp+57h+var_40], rax
0x1800951ea  mov     [rbp+57h+var_70], rdx
0x1800951ee  xorps   xmm0, xmm0
0x1800951f1  mov     [rbp+57h+hKey], 0
0x1800951f9  mov     rsi, r9
0x1800951fc  mov     r13d, r8d
0x1800951ff  mov     r12, rdx
0x180095202  mov     r15, rcx
0x180095205  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180095209  movups  [rbp+57h+var_50], xmm0
0x18009520d  test    rcx, rcx
0x180095210  jz      loc_1800954F9
0x180095216  lea     eax, [r8-1]
0x18009521a  mov     r14d, 1
0x180095220  cmp     eax, r14d
0x180095223  jbe     short loc_180095234
0x180095225  lea     ecx, [r14+7Bh]; dwErrCode
0x180095229  call    cs:__imp_SetLastError
0x18009522f  jmp     loc_1800954F9
0x180095234  xor     edx, edx; int
0x180095236  mov     rcx, rsi; unsigned __int8 *
0x180095239  call    ?ValidateForm@@YAHPEAEHK@Z; ValidateForm(uchar *,int,ulong)
0x18009523e  test    eax, eax
0x180095240  jnz     short loc_180095263
0x180095242  call    cs:__imp_GetLastError
0x180095248  mov     r8d, eax
0x18009524b  lea     rdx, aSpecifiedFormT; "Specified form to add is invalid.  Erro"...
0x180095252  lea     rcx, aInternalsetfor; "InternalSetForm"
0x180095259  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009525e  jmp     loc_1800954F9
0x180095263  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x180095268  xor     r9d, r9d
0x18009526b  xor     r8d, r8d
0x18009526e  mov     [rsp+0D0h+phkResult], r15
0x180095273  mov     edx, r14d
0x180095276  xor     ecx, ecx
0x180095278  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x18009527d  test    eax, eax
0x18009527f  jz      loc_1800954F9
0x180095285  xor     ecx, ecx
0x180095287  call    EnterSplSem
0x18009528c  mov     rcx, r15; struct _INISPOOLER *
0x18009528f  call    InitializeForms
0x180095294  mov     rcx, [r15+48h]
0x180095298  xor     r8d, r8d
0x18009529b  mov     rdx, r12
0x18009529e  call    FindIniKey
0x1800952a3  mov     rbx, rax
0x1800952a6  test    rax, rax
0x1800952a9  jz      loc_1800954C7
0x1800952af  cmp     [rax+3Ch], r14d
0x1800952b3  jz      loc_1800954C7
0x1800952b9  test    [rsi], r14b
0x1800952bc  jnz     loc_1800954C7
0x1800952c2  call    cs:__imp_RevertToPrinterSelf
0x1800952c8  mov     [rbp+57h+hToken], rax
0x1800952cc  test    rax, rax
0x1800952cf  jz      loc_180095469
0x1800952d5  mov     rdx, [r15+0A0h]; lpSubKey
0x1800952dc  lea     rax, [rbp+57h+hKey]
0x1800952e0  mov     r9d, 20006h; samDesired
0x1800952e6  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800952eb  xor     r8d, r8d; ulOptions
0x1800952ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800952f5  call    cs:__imp_RegOpenKeyExW
0x1800952fb  mov     edi, eax
0x1800952fd  test    eax, eax
0x1800952ff  jnz     loc_18009545D
0x180095305  mov     rax, [rsi+10h]
0x180095309  lea     r9, [rbp+57h+var_60]; unsigned __int8 *
0x18009530d  movups  xmm0, xmmword ptr [rsi+18h]
0x180095311  mov     rdx, [rsi+8]; unsigned __int16 *
0x180095315  lea     r8d, [rdi+3]; unsigned int
0x180095319  mov     rcx, [rbp+57h+hKey]; void *
0x18009531d  mov     qword ptr [rbp+57h+var_60], rax
0x180095321  mov     eax, [rsi]
0x180095323  movdqu  xmmword ptr [rbp+57h+var_60+8], xmm0
0x180095328  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x18009532b  mov     eax, [rbx+40h]
0x18009532e  mov     [rsp+0D0h+var_A8], r15; struct _INISPOOLER *
0x180095333  mov     dword ptr [rbp+57h+var_50+8], eax
0x180095336  mov     dword ptr [rsp+0D0h+phkResult], 20h ; ' '; unsigned int
0x18009533e  call    ?SplRegSetValue@@YAJPEAXPEBGKPEBEKPEAU_INISPOOLER@@@Z; SplRegSetValue(void *,ushort const *,ulong,uchar const *,ulong,_INISPOOLER *)
0x180095343  mov     edi, eax
0x180095345  test    eax, eax
0x180095347  jnz     loc_180095439
0x18009534d  cmp     r13d, 2
0x180095351  jnz     loc_180095439
0x180095357  cmp     [rsi+30h], r14d
0x18009535b  jnz     short loc_18009538F
0x18009535d  mov     rcx, [rbx+50h]
0x180095361  xor     edi, edi
0x180095363  xor     r12d, r12d
0x180095366  mov     dword ptr [rbp+57h+var_80], edi
0x180095369  xor     r13d, r13d
0x18009536c  test    rcx, rcx
0x18009536f  jz      short loc_18009537B
0x180095371  call    cs:__imp_DllFreeSplMem
0x180095377  mov     [rbx+50h], rdi
0x18009537b  mov     rcx, [rbx+58h]; struct _LANGPAIRNODE *
0x18009537f  test    rcx, rcx
0x180095382  jz      short loc_180095401
0x180095384  call    ?FreeLangPair@@YAXPEAU_LANGPAIRNODE@@@Z; FreeLangPair(_LANGPAIRNODE *)
0x180095389  mov     [rbx+58h], rdi
0x18009538d  jmp     short loc_180095401
0x18009538f  xor     r14d, r14d
0x180095392  cmp     dword ptr [rsi+30h], 2
0x180095396  jnz     short loc_1800953CE
0x180095398  mov     rdi, [rsi+38h]
0x18009539c  xor     eax, eax
0x18009539e  mov     r12d, [rsi+40h]
0x1800953a2  xor     r13d, r13d
0x1800953a5  mov     [rbp+57h+var_80], ax
0x1800953a9  test    rdi, rdi
0x1800953ac  jz      short loc_180095401
0x1800953ae  mov     rcx, [rbx+50h]
0x1800953b2  test    rcx, rcx
0x1800953b5  jz      short loc_1800953BD
0x1800953b7  call    cs:__imp_DllFreeSplMem
0x1800953bd  mov     edx, r12d; unsigned int
0x1800953c0  mov     rcx, rdi; pszSrc
0x1800953c3  call    ?BuildResourceName@@YAPEAGPEBGK@Z; BuildResourceName(ushort const *,ulong)
0x1800953c8  mov     [rbx+50h], rax
0x1800953cc  jmp     short loc_180095401
0x1800953ce  xor     edi, edi
0x1800953d0  cmp     dword ptr [rsi+30h], 4
0x1800953d4  jnz     short loc_1800953F5
0x1800953d6  mov     r13, [rsi+48h]
0x1800953da  lea     rcx, [rbx+58h]; struct _LANGPAIRNODE **
0x1800953de  movzx   r8d, word ptr [rsi+50h]; unsigned __int16
0x1800953e3  mov     rdx, r13; unsigned __int16 *
0x1800953e6  xor     r12d, r12d
0x1800953e9  mov     [rbp+57h+var_80], r8w
0x1800953ee  call    ?AddLanguagePairNode@@YAXPEAPEAU_LANGPAIRNODE@@PEBGG@Z; AddLanguagePairNode(_LANGPAIRNODE * *,ushort const *,ushort)
0x1800953f3  jmp     short loc_180095401
0x1800953f5  xor     eax, eax
0x1800953f7  xor     r13d, r13d
0x1800953fa  mov     [rbp+57h+var_80], ax
0x1800953fe  xor     r12d, r12d
0x180095401  mov     r8, [rsi+28h]; char *
0x180095405  mov     r9, rdi; unsigned __int16 *
0x180095408  mov     rdx, [rsi+8]; unsigned __int16 *
0x18009540c  mov     rcx, [rbp+57h+hKey]; void *
0x180095410  mov     [rsp+0D0h+var_90], r15; struct _INISPOOLER *
0x180095415  mov     [rsp+0D0h+var_98], r14d; int
0x18009541a  mov     r14d, dword ptr [rbp+57h+var_80]
0x18009541e  mov     [rsp+0D0h+var_A0], r14w; unsigned __int16
0x180095424  mov     [rsp+0D0h+var_A8], r13; unsigned __int16 *
0x180095429  mov     dword ptr [rsp+0D0h+phkResult], r12d; unsigned int
0x18009542e  call    ?RegistrySetFormInfo2@@YAKPEAXPEAGPEBDPEBGK3GHPEAU_INISPOOLER@@@Z; RegistrySetFormInfo2(void *,ushort *,char const *,ushort const *,ulong,ushort const *,ushort,int,_INISPOOLER *)
0x180095433  mov     r12, [rbp+57h+var_70]
0x180095437  mov     edi, eax
0x180095439  mov     rcx, [rbp+57h+hKey]; hKey
0x18009543d  call    cs:__imp_RegCloseKey
0x180095443  test    edi, edi
0x180095445  jnz     short loc_18009545D
0x180095447  mov     rax, [rsi+10h]
0x18009544b  mov     [rbx+24h], rax
0x18009544f  movups  xmm0, xmmword ptr [rsi+18h]
0x180095453  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x180095458  mov     eax, [rsi]
0x18009545a  mov     [rbx+3Ch], eax
0x18009545d  mov     rcx, [rbp+57h+hToken]; hToken
0x180095461  call    cs:__imp_ImpersonatePrinterClient
0x180095467  jmp     short loc_180095471
0x180095469  call    cs:__imp_GetLastError
0x18009546f  mov     edi, eax
0x180095471  test    edi, edi
0x180095473  jnz     short loc_18009549B
0x180095475  mov     r9d, 20000h
0x18009547b  mov     [rsp+0D0h+phkResult], r15
0x180095480  xor     r8d, r8d
0x180095483  xor     edx, edx
0x180095485  xor     ecx, ecx
0x180095487  call    SetPrinterChange
0x18009548c  mov     rcx, r15; struct _INISPOOLER *
0x18009548f  call    ?BroadcastChangeForms@@YAXPEAU_INISPOOLER@@@Z; BroadcastChangeForms(_INISPOOLER *)
0x180095494  call    LeaveSplSem
0x180095499  jmp     short loc_1800954BE
0x18009549b  call    LeaveSplSem
0x1800954a0  mov     ecx, edi; dwErrCode
0x1800954a2  call    cs:__imp_SetLastError
0x1800954a8  mov     r8, r12
0x1800954ab  lea     rdx, aSetformOperati; "SetForm operation failed for form '%ws'"
0x1800954b2  lea     rcx, aInternalsetfor; "InternalSetForm"
0x1800954b9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800954be  xor     eax, eax
0x1800954c0  test    edi, edi
0x1800954c2  setz    al
0x1800954c5  jmp     short loc_1800954FB
0x1800954c7  neg     rbx
0x1800954ca  sbb     ecx, ecx
0x1800954cc  and     ecx, 0FFFFF8E9h
0x1800954d2  add     ecx, 76Eh; dwErrCode
0x1800954d8  call    cs:__imp_SetLastError
0x1800954de  call    LeaveSplSem
0x1800954e3  mov     r8, r12
0x1800954e6  lea     rdx, aFormWsDoesNotE; "Form '%ws' does not exist or is a built"...
0x1800954ed  lea     rcx, aInternalsetfor; "InternalSetForm"
0x1800954f4  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800954f9  xor     eax, eax
0x1800954fb  mov     rcx, [rbp+57h+var_40]
0x1800954ff  xor     rcx, rsp; StackCookie
0x180095502  call    __security_check_cookie
0x180095507  mov     rbx, [rsp+0D0h+arg_10]
0x18009550f  add     rsp, 0A0h
0x180095516  pop     r15
0x180095518  pop     r14
0x18009551a  pop     r13
0x18009551c  pop     r12
0x18009551e  pop     rdi
0x18009551f  pop     rsi
0x180095520  pop     rbp
0x180095521  retn
```
