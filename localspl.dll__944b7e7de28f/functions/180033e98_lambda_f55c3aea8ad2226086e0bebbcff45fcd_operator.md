# _lambda_f55c3aea8ad2226086e0bebbcff45fcd_::operator()

- ea: `0x180033e98`
- end: `0x180034301`
- name: `_lambda_f55c3aea8ad2226086e0bebbcff45fcd_::operator()`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18008ffec`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180013b00`
- `0x1800170a0`
- `0x180031478`
- `0x180033e98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034248`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003404c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003404c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034154`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003403c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003403c`
- `SPOOLSS!MarshallUpStructure` at `0x1800341bf`
- `SPOOLSS!MarshallUpStructure` at `0x18003423a`
- `SPOOLSS!MarshallUpStructure` at `0x1800341bf`
- `SPOOLSS!MarshallUpStructure` at `0x18003423a`
- `SPOOLSS!DllFreeSplMem` at `0x1800342ea`
- `SPOOLSS!DllFreeSplMem` at `0x1800342ea`
- `SPOOLSS!DllAllocSplMem` at `0x1800340bb`
- `SPOOLSS!DllAllocSplMem` at `0x1800340bb`
- `SPOOLSS!RevertToPrinterSelf` at `0x180033f5d`
- `SPOOLSS!RevertToPrinterSelf` at `0x180033f5d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18003417d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18003417d`

## pseudocode

```c
__int64 *__fastcall lambda_f55c3aea8ad2226086e0bebbcff45fcd_::operator()(__int64 **a1)
{
  __int64 v2; // r14
  __int64 *v3; // rax
  int v4; // ecx
  __int64 *result; // rax
  __int64 *v6; // rax
  unsigned __int8 *v7; // rsi
  int v8; // r15d
  const unsigned __int16 *v9; // r12
  HANDLE v10; // r13
  DWORD LastError; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 *v15; // rbx
  __int64 v16; // rcx
  __int64 *v17; // rbx
  __int64 *v18; // rax
  int *v19; // rbx
  int v20; // eax
  unsigned __int8 *v21; // rax
  __int64 *v22; // rax
  HKEY v23; // rcx
  __int64 v24; // rax
  __int64 *v25; // rcx
  DWORD v26; // eax
  DWORD v27; // eax
  HKEY v28; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+60h] BYREF

  v2 = **a1;
  v3 = a1[2];
  v28 = 0;
  hKey = 0;
  phkResult = 0;
  v29 = 0;
  v30 = 0;
  if ( !*v3
    || !*a1[3]
    || !(unsigned int)ValidateSpoolHandle(v2, 16)
    || (v4 = 0, (*(_DWORD *)(*(_QWORD *)(v2 + 168) + 168LL) & 0x4000000) == 0) )
  {
    v4 = 87;
  }
  *(_DWORD *)a1[1] = v4;
  result = a1[1];
  if ( !*(_DWORD *)result )
  {
    v6 = a1[4];
    v7 = 0;
    if ( *(_DWORD *)v6 < 0x24u )
    {
      if ( *(_DWORD *)v6 < 0x10u )
      {
        v9 = 0;
        v29 = 0;
        v8 = 0;
      }
      else
      {
        v29 = 16;
        v8 = 1;
        v9 = (const unsigned __int16 *)&szPrintProcCacheValue1;
      }
    }
    else
    {
      v8 = 2;
      v29 = 36;
      v9 = szPrintProcCacheValue2;
    }
    v10 = RevertToPrinterSelf();
    if ( v10 )
      LastError = 0;
    else
      LastError = GetLastError();
    *(_DWORD *)a1[1] = LastError;
    if ( *(_DWORD *)a1[1] )
    {
LABEL_41:
      if ( v10 )
        ImpersonatePrinterClient(v10);
      v25 = a1[1];
      if ( !*(_DWORD *)v25 )
      {
        if ( *a1[5] && v8 )
        {
          if ( v8 == 1 )
          {
            if ( (unsigned int)MarshallUpStructure(v29, v7, &PrintProcessorCaps1Fields, v29, 0) )
              v26 = 0;
            else
              v26 = GetLastError();
            *(_DWORD *)a1[1] = v26;
            if ( !*(_DWORD *)a1[1] )
            {
              *(_DWORD *)*a1[5] = *(_DWORD *)v7;
              *(_DWORD *)(*a1[5] + 4) = *((_DWORD *)v7 + 1);
              *(_DWORD *)(*a1[5] + 8) = *((_DWORD *)v7 + 2);
              *(_DWORD *)(*a1[5] + 12) = *((_DWORD *)v7 + 3);
            }
          }
          else
          {
            if ( (unsigned int)MarshallUpStructure(v29, v7, &PrintProcessorCaps2Fields, v29, 0) )
              v27 = 0;
            else
              v27 = GetLastError();
            *(_DWORD *)a1[1] = v27;
            if ( !*(_DWORD *)a1[1] )
            {
              *(_DWORD *)*a1[5] = *(_DWORD *)v7;
              *(_DWORD *)(*a1[5] + 4) = *((_DWORD *)v7 + 1);
              *(_DWORD *)(*a1[5] + 8) = *((_DWORD *)v7 + 2);
              *(_DWORD *)(*a1[5] + 12) = *((_DWORD *)v7 + 3);
              *(_DWORD *)(*a1[5] + 16) = *((_DWORD *)v7 + 4);
              *(_DWORD *)(*a1[5] + 20) = *((_DWORD *)v7 + 5);
              *(_DWORD *)(*a1[5] + 24) = *((_DWORD *)v7 + 6);
              *(_DWORD *)(*a1[5] + 28) = *((_DWORD *)v7 + 7);
              *(_DWORD *)(*a1[5] + 32) = *((_DWORD *)v7 + 8);
            }
          }
        }
        else
        {
          *(_DWORD *)v25 = 234;
          *(_DWORD *)*a1[3] = v29;
        }
      }
      return (__int64 *)DllFreeSplMem(v7);
    }
    EnterSplSem(0);
    v12 = *(_QWORD *)(v2 + 64);
    if ( v12 )
    {
      v13 = SafeIncrementReference((unsigned int *)(v12 + 16));
      v14 = *(_QWORD *)(v2 + 64);
      if ( v13 > *(_DWORD *)(v14 + 248) )
        *(_DWORD *)(v14 + 248) = *(_DWORD *)(v14 + 16);
    }
    v15 = a1[1];
    *(_DWORD *)v15 = OpenPrinterKey(*(_QWORD *)(v2 + 64), 0x20019u, &v28, 0, 1);
    LeaveSplSem(v16);
    if ( *(_DWORD *)a1[1]
      || (v17 = a1[1],
          *(_DWORD *)v17 = OpenPrintProcCacheKey(v28, 0x20019u, 0, *(struct _INISPOOLER **)(v2 + 168), (void **)&hKey),
          *(_DWORD *)a1[1])
      || (*(_DWORD *)a1[1] = RegOpenKeyExW(hKey, (LPCWSTR)*a1[2], 0, 0x20019u, &phkResult),
          RegCloseKey(hKey),
          v18 = a1[1],
          *(_DWORD *)v18) )
    {
LABEL_35:
      EnterSplSem(0);
      v23 = v28;
      if ( v28 )
        RegCloseKey(v28);
      v24 = *(_QWORD *)(v2 + 64);
      if ( v24 )
      {
        v23 = (HKEY)(v24 + 16);
        if ( *(_DWORD *)(v24 + 16) )
          SafeDecrementReference((unsigned int *)v23);
      }
      LeaveSplSem(v23);
      goto LABEL_41;
    }
    if ( v29 )
    {
      v21 = (unsigned __int8 *)DllAllocSplMem(v29);
      v7 = v21;
      *(_DWORD *)a1[1] = v21 == 0 ? 0xE : 0;
      if ( !*(_DWORD *)a1[1] )
      {
        v19 = (int *)a1[1];
        v20 = SplRegQueryValue(phkResult, v9, &v30, v21, &v29, *(struct _INISPOOLER **)(v2 + 168));
        goto LABEL_27;
      }
    }
    else
    {
      *(_DWORD *)v18 = SplRegQueryValue(
                         phkResult,
                         szPrintProcCacheValue2,
                         &v30,
                         0,
                         &v29,
                         *(struct _INISPOOLER **)(v2 + 168));
      if ( *(_DWORD *)a1[1] )
      {
        v19 = (int *)a1[1];
        v20 = SplRegQueryValue(
                phkResult,
                (const unsigned __int16 *)&szPrintProcCacheValue1,
                &v30,
                0,
                &v29,
                *(struct _INISPOOLER **)(v2 + 168));
LABEL_27:
        *v19 = v20;
      }
    }
    v22 = a1[1];
    if ( (!*(_DWORD *)v22 || *(_DWORD *)v22 == 234) && (v30 != 3 || v29 != 16 && v29 != 36) )
      *(_DWORD *)v22 = 13;
    RegCloseKey(phkResult);
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x180033e98  push    rbp
0x180033e9a  push    rbx
0x180033e9b  push    rsi
0x180033e9c  push    rdi
0x180033e9d  push    r12
0x180033e9f  push    r13
0x180033ea1  push    r14
0x180033ea3  push    r15
0x180033ea5  mov     rbp, rsp
0x180033ea8  sub     rsp, 48h
0x180033eac  mov     rax, [rcx]
0x180033eaf  xor     ebx, ebx
0x180033eb1  mov     rdi, rcx
0x180033eb4  mov     r14, [rax]
0x180033eb7  lea     r12d, [rbx+10h]
0x180033ebb  mov     rax, [rcx+10h]
0x180033ebf  mov     [rbp+var_18], rbx
0x180033ec3  mov     [rbp+hKey], rbx
0x180033ec7  mov     [rbp+arg_10], rbx
0x180033ecb  mov     [rbp+arg_0], ebx
0x180033ece  mov     [rbp+arg_8], ebx
0x180033ed1  cmp     [rax], rbx
0x180033ed4  jz      short loc_180033F03
0x180033ed6  mov     rax, [rcx+18h]
0x180033eda  cmp     [rax], rbx
0x180033edd  jz      short loc_180033F03
0x180033edf  mov     edx, r12d
0x180033ee2  mov     rcx, r14
0x180033ee5  call    ValidateSpoolHandle
0x180033eea  test    eax, eax
0x180033eec  jz      short loc_180033F03
0x180033eee  mov     rax, [r14+0A8h]
0x180033ef5  mov     ecx, ebx
0x180033ef7  test    dword ptr [rax+0A8h], 4000000h
0x180033f01  jnz     short loc_180033F08
0x180033f03  mov     ecx, 57h ; 'W'
0x180033f08  mov     rax, [rdi+8]
0x180033f0c  mov     [rax], ecx
0x180033f0e  mov     rax, [rdi+8]
0x180033f12  cmp     [rax], ebx
0x180033f14  jnz     loc_1800342F0
0x180033f1a  mov     rax, [rdi+20h]
0x180033f1e  mov     rsi, rbx
0x180033f21  cmp     dword ptr [rax], 24h ; '$'
0x180033f24  jb      short loc_180033F3C
0x180033f26  mov     r15d, 2
0x180033f2c  mov     [rbp+arg_0], 24h ; '$'
0x180033f33  lea     r12, ?szPrintProcCacheValue2@@3PAGA
0x180033f3a  jmp     short loc_180033F5D
0x180033f3c  cmp     [rax], r12d
0x180033f3f  jb      short loc_180033F54
0x180033f41  mov     [rbp+arg_0], r12d
0x180033f45  mov     r15d, 1
0x180033f4b  lea     r12, ?szPrintProcCacheValue1@@3PAGA
0x180033f52  jmp     short loc_180033F5D
0x180033f54  mov     r12, rbx
0x180033f57  mov     [rbp+arg_0], ebx
0x180033f5a  mov     r15d, ebx
0x180033f5d  call    cs:__imp_RevertToPrinterSelf
0x180033f63  mov     r13, rax
0x180033f66  test    rax, rax
0x180033f69  jz      short loc_180033F6F
0x180033f6b  mov     eax, ebx
0x180033f6d  jmp     short loc_180033F75
0x180033f6f  call    cs:__imp_GetLastError
0x180033f75  mov     rcx, [rdi+8]
0x180033f79  mov     [rcx], eax
0x180033f7b  mov     rax, [rdi+8]
0x180033f7f  cmp     [rax], ebx
0x180033f81  jnz     loc_180034175
0x180033f87  xor     ecx, ecx
0x180033f89  call    EnterSplSem
0x180033f8e  mov     rcx, [r14+40h]
0x180033f92  test    rcx, rcx
0x180033f95  jz      short loc_180033FB5
0x180033f97  add     rcx, 10h; unsigned int *
0x180033f9b  call    ?SafeIncrementReference@@YAKPEAK@Z
0x180033fa0  mov     rcx, [r14+40h]
0x180033fa4  cmp     eax, [rcx+0F8h]
0x180033faa  jbe     short loc_180033FB5
0x180033fac  mov     eax, [rcx+10h]
0x180033faf  mov     [rcx+0F8h], eax
0x180033fb5  mov     rcx, [r14+40h]
0x180033fb9  lea     r8, [rbp+var_18]
0x180033fbd  mov     rbx, [rdi+8]
0x180033fc1  xor     r9d, r9d
0x180033fc4  mov     edx, 20019h
0x180033fc9  mov     dword ptr [rsp+48h+phkResult], 1
0x180033fd1  call    OpenPrinterKey
0x180033fd6  mov     [rbx], eax
0x180033fd8  call    LeaveSplSem
0x180033fdd  mov     rax, [rdi+8]
0x180033fe1  xor     ebx, ebx
0x180033fe3  cmp     [rax], ebx
0x180033fe5  jnz     loc_180034144
0x180033feb  mov     r9, [r14+0A8h]; struct _INISPOOLER *
0x180033ff2  mov     rbx, rax
0x180033ff5  mov     rcx, [rbp+var_18]; void *
0x180033ff9  lea     rax, [rbp+hKey]
0x180033ffd  xor     r8d, r8d; int
0x180034000  mov     [rsp+48h+phkResult], rax; void **
0x180034005  mov     edx, 20019h; unsigned int
0x18003400a  call    ?OpenPrintProcCacheKey@@YAKPEAXKHPEAU_INISPOOLER@@PEAPEAX@Z
0x18003400f  mov     [rbx], eax
0x180034011  xor     ebx, ebx
0x180034013  mov     rax, [rdi+8]
0x180034017  cmp     [rax], ebx
0x180034019  jnz     loc_180034144
0x18003401f  mov     rdx, [rdi+10h]
0x180034023  lea     rax, [rbp+arg_10]
0x180034027  mov     rcx, [rbp+hKey]; hKey
0x18003402b  mov     r9d, 20019h; samDesired
0x180034031  xor     r8d, r8d; ulOptions
0x180034034  mov     [rsp+48h+phkResult], rax; phkResult
0x180034039  mov     rdx, [rdx]; lpSubKey
0x18003403c  call    cs:__imp_RegOpenKeyExW
0x180034042  mov     rcx, [rdi+8]
0x180034046  mov     [rcx], eax
0x180034048  mov     rcx, [rbp+hKey]; hKey
0x18003404c  call    cs:__imp_RegCloseKey
0x180034052  mov     rax, [rdi+8]
0x180034056  cmp     [rax], ebx
0x180034058  jnz     loc_180034144
0x18003405e  mov     ecx, [rbp+arg_0]
0x180034061  test    ecx, ecx
0x180034063  jnz     short loc_1800340BB
0x180034065  mov     rcx, [rbp+arg_10]; void *
0x180034069  lea     r8, [rbp+arg_8]; unsigned int *
0x18003406d  mov     rbx, rax
0x180034070  lea     rdx, ?szPrintProcCacheValue2@@3PAGA
0x180034077  mov     rax, [r14+0A8h]
0x18003407e  xor     r9d, r9d; unsigned __int8 *
0x180034081  mov     [rsp+48h+var_20], rax; struct _INISPOOLER *
0x180034086  lea     rax, [rbp+arg_0]
0x18003408a  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18003408f  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z
0x180034094  mov     [rbx], eax
0x180034096  xor     ebx, ebx
0x180034098  mov     rax, [rdi+8]
0x18003409c  cmp     [rax], ebx
0x18003409e  jz      short loc_180034112
0x1800340a0  mov     rbx, rax
0x1800340a3  lea     rdx, ?szPrintProcCacheValue1@@3PAGA
0x1800340aa  mov     rax, [r14+0A8h]
0x1800340b1  xor     r9d, r9d
0x1800340b4  mov     [rsp+48h+var_20], rax
0x1800340b9  jmp     short loc_1800340F8
0x1800340bb  call    cs:__imp_DllAllocSplMem
0x1800340c1  mov     rcx, rax
0x1800340c4  mov     rsi, rax
0x1800340c7  neg     rcx
0x1800340ca  mov     rcx, [rdi+8]
0x1800340ce  sbb     r8d, r8d
0x1800340d1  not     r8d
0x1800340d4  and     r8d, 0Eh
0x1800340d8  mov     [rcx], r8d
0x1800340db  mov     rcx, [rdi+8]
0x1800340df  cmp     [rcx], ebx
0x1800340e1  jnz     short loc_180034112
0x1800340e3  mov     rbx, rcx
0x1800340e6  mov     r9, rax; unsigned __int8 *
0x1800340e9  mov     rcx, [r14+0A8h]
0x1800340f0  mov     rdx, r12; unsigned __int16 *
0x1800340f3  mov     [rsp+48h+var_20], rcx; struct _INISPOOLER *
0x1800340f8  mov     rcx, [rbp+arg_10]; void *
0x1800340fc  lea     rax, [rbp+arg_0]
0x180034100  lea     r8, [rbp+arg_8]; unsigned int *
0x180034104  mov     [rsp+48h+phkResult], rax; unsigned int *
0x180034109  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z
0x18003410e  mov     [rbx], eax
0x180034110  xor     ebx, ebx
0x180034112  mov     rax, [rdi+8]
0x180034116  cmp     [rax], ebx
0x180034118  jz      short loc_180034122
0x18003411a  cmp     dword ptr [rax], 0EAh
0x180034120  jnz     short loc_18003413A
0x180034122  cmp     [rbp+arg_8], 3
0x180034126  jnz     short loc_180034134
0x180034128  cmp     [rbp+arg_0], 10h
0x18003412c  jz      short loc_18003413A
0x18003412e  cmp     [rbp+arg_0], 24h ; '$'
0x180034132  jz      short loc_18003413A
0x180034134  mov     dword ptr [rax], 0Dh
0x18003413a  mov     rcx, [rbp+arg_10]; hKey
0x18003413e  call    cs:__imp_RegCloseKey
0x180034144  xor     ecx, ecx
0x180034146  call    EnterSplSem
0x18003414b  mov     rcx, [rbp+var_18]; hKey
0x18003414f  test    rcx, rcx
0x180034152  jz      short loc_18003415A
0x180034154  call    cs:__imp_RegCloseKey
0x18003415a  mov     rax, [r14+40h]
0x18003415e  test    rax, rax
0x180034161  jz      short loc_180034170
0x180034163  lea     rcx, [rax+10h]; unsigned int *
0x180034167  cmp     [rcx], ebx
0x180034169  jz      short loc_180034170
0x18003416b  call    ?SafeDecrementReference@@YAKPEAK@Z
0x180034170  call    LeaveSplSem
0x180034175  test    r13, r13
0x180034178  jz      short loc_180034183
0x18003417a  mov     rcx, r13; hToken
0x18003417d  call    cs:__imp_ImpersonatePrinterClient
0x180034183  mov     rcx, [rdi+8]
0x180034187  cmp     [rcx], ebx
0x180034189  jnz     loc_1800342E7
0x18003418f  mov     rax, [rdi+28h]
0x180034193  cmp     [rax], rbx
0x180034196  jz      loc_1800342D5
0x18003419c  test    r15d, r15d
0x18003419f  jz      loc_1800342D5
0x1800341a5  cmp     r15d, 1
0x1800341a9  jnz     short loc_18003421C
0x1800341ab  mov     ecx, [rbp+arg_0]
0x1800341ae  lea     r8, ?PrintProcessorCaps1Fields@@3QBU_FieldInfo@@B
0x1800341b5  mov     r9d, ecx
0x1800341b8  mov     dword ptr [rsp+48h+phkResult], ebx
0x1800341bc  mov     rdx, rsi
0x1800341bf  call    cs:__imp_MarshallUpStructure
0x1800341c5  test    eax, eax
0x1800341c7  jz      short loc_1800341CD
0x1800341c9  mov     eax, ebx
0x1800341cb  jmp     short loc_1800341D3
0x1800341cd  call    cs:__imp_GetLastError
0x1800341d3  mov     rcx, [rdi+8]
0x1800341d7  mov     [rcx], eax
0x1800341d9  mov     rax, [rdi+8]
0x1800341dd  cmp     [rax], ebx
0x1800341df  jnz     loc_1800342E7
0x1800341e5  mov     rax, [rdi+28h]
0x1800341e9  mov     rcx, [rax]
0x1800341ec  mov     eax, [rsi]
0x1800341ee  mov     [rcx], eax
0x1800341f0  mov     rax, [rdi+28h]
0x1800341f4  mov     rcx, [rax]
0x1800341f7  mov     eax, [rsi+4]
0x1800341fa  mov     [rcx+4], eax
0x1800341fd  mov     rax, [rdi+28h]
0x180034201  mov     rcx, [rax]
0x180034204  mov     eax, [rsi+8]
0x180034207  mov     [rcx+8], eax
0x18003420a  mov     rax, [rdi+28h]
0x18003420e  mov     rcx, [rax]
0x180034211  mov     eax, [rsi+0Ch]
0x180034214  mov     [rcx+0Ch], eax
0x180034217  jmp     loc_1800342E7
0x18003421c  cmp     r15d, 2
0x180034220  jnz     loc_1800342E7
0x180034226  mov     ecx, [rbp+arg_0]
0x180034229  lea     r8, ?PrintProcessorCaps2Fields@@3QBU_FieldInfo@@B
0x180034230  mov     r9d, ecx
0x180034233  mov     dword ptr [rsp+48h+phkResult], ebx
0x180034237  mov     rdx, rsi
0x18003423a  call    cs:__imp_MarshallUpStructure
0x180034240  test    eax, eax
0x180034242  jz      short loc_180034248
0x180034244  mov     eax, ebx
0x180034246  jmp     short loc_18003424E
0x180034248  call    cs:__imp_GetLastError
0x18003424e  mov     rcx, [rdi+8]
0x180034252  mov     [rcx], eax
0x180034254  mov     rax, [rdi+8]
0x180034258  cmp     [rax], ebx
0x18003425a  jnz     loc_1800342E7
0x180034260  mov     rax, [rdi+28h]
0x180034264  mov     rcx, [rax]
0x180034267  mov     eax, [rsi]
0x180034269  mov     [rcx], eax
0x18003426b  mov     rax, [rdi+28h]
0x18003426f  mov     rcx, [rax]
0x180034272  mov     eax, [rsi+4]
0x180034275  mov     [rcx+4], eax
0x180034278  mov     rax, [rdi+28h]
0x18003427c  mov     rcx, [rax]
0x18003427f  mov     eax, [rsi+8]
0x180034282  mov     [rcx+8], eax
0x180034285  mov     rax, [rdi+28h]
0x180034289  mov     rcx, [rax]
0x18003428c  mov     eax, [rsi+0Ch]
0x18003428f  mov     [rcx+0Ch], eax
0x180034292  mov     rax, [rdi+28h]
0x180034296  mov     rcx, [rax]
0x180034299  mov     eax, [rsi+10h]
0x18003429c  mov     [rcx+10h], eax
0x18003429f  mov     rax, [rdi+28h]
0x1800342a3  mov     rcx, [rax]
0x1800342a6  mov     eax, [rsi+14h]
0x1800342a9  mov     [rcx+14h], eax
0x1800342ac  mov     rax, [rdi+28h]
0x1800342b0  mov     rcx, [rax]
0x1800342b3  mov     eax, [rsi+18h]
0x1800342b6  mov     [rcx+18h], eax
0x1800342b9  mov     rax, [rdi+28h]
0x1800342bd  mov     rcx, [rax]
0x1800342c0  mov     eax, [rsi+1Ch]
0x1800342c3  mov     [rcx+1Ch], eax
0x1800342c6  mov     rax, [rdi+28h]
0x1800342ca  mov     rcx, [rax]
0x1800342cd  mov     eax, [rsi+20h]
0x1800342d0  mov     [rcx+20h], eax
  ... truncated ...
```
