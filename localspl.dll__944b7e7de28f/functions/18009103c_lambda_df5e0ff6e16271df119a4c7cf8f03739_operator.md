# _lambda_df5e0ff6e16271df119a4c7cf8f03739_::operator()

- ea: `0x18009103c`
- end: `0x180091420`
- name: `_lambda_df5e0ff6e16271df119a4c7cf8f03739_::operator()`
- size: `996`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18008ff8c`

## callees

- `0x180005d90`
- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180013b00`
- `0x180031478`
- `0x18003ea2c`
- `0x180045010`
- `0x18009103c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009122f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009125a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009122f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009125a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800913a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800913a9`
- `SPOOLSS!MarshallDownStructure` at `0x180091220`
- `SPOOLSS!MarshallDownStructure` at `0x180091220`
- `SPOOLSS!DllFreeSplMem` at `0x1800913df`
- `SPOOLSS!DllFreeSplMem` at `0x1800913df`
- `SPOOLSS!DllAllocSplMem` at `0x180091117`
- `SPOOLSS!DllAllocSplMem` at `0x1800911bc`
- `SPOOLSS!DllAllocSplMem` at `0x180091117`
- `SPOOLSS!DllAllocSplMem` at `0x1800911bc`
- `SPOOLSS!RevertToPrinterSelf` at `0x180091248`
- `SPOOLSS!RevertToPrinterSelf` at `0x180091248`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800913d3`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800913d3`

## string_xrefs

- `0x1800913f9`: `SplSetPrintProcCacheData::<lambda_df5e0ff6e16271df119a4c7cf8f03739>::operator ()`
- `0x1800913f2`: `Failed to set cache data for datatype '%ws'`

## pseudocode

```c
void __fastcall lambda_df5e0ff6e16271df119a4c7cf8f03739_::operator()(__int64 **a1)
{
  __int64 v2; // rsi
  __int64 v3; // r14
  unsigned int v4; // r15d
  __int64 *v5; // rax
  int v6; // ebx
  const unsigned __int16 *v7; // r13
  int v8; // ecx
  __int64 *v9; // rax
  int v10; // ebx
  const struct _FieldInfo near *const *v11; // rdx
  DWORD v12; // eax
  HANDLE v13; // r12
  DWORD LastError; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 *v18; // rbx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 *v21; // rbx
  __int64 *v22; // rbx
  HKEY v23; // rcx
  __int64 v24; // rax
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY v26; // [rsp+88h] [rbp+48h] BYREF
  HKEY v27; // [rsp+90h] [rbp+50h] BYREF

  v2 = 0;
  v3 = **a1;
  v4 = 36;
  v5 = a1[1];
  v27 = 0;
  hKey = 0;
  v26 = 0;
  if ( *(_DWORD *)v5 < 0x24u )
  {
    if ( *(_DWORD *)v5 < 0x10u )
    {
      v4 = 0;
      v7 = 0;
      v6 = 0;
    }
    else
    {
      v6 = 1;
      v7 = (const unsigned __int16 *)&szPrintProcCacheValue1;
      v4 = 16;
    }
  }
  else
  {
    v6 = 2;
    v7 = szPrintProcCacheValue2;
  }
  if ( !*a1[3]
    || !*a1[4]
    || !v6
    || !(unsigned int)ValidateSpoolHandle(v3, 16)
    || (v8 = 0, (*(_DWORD *)(*(_QWORD *)(v3 + 168) + 168LL) & 0x4000000) == 0) )
  {
    v8 = 87;
  }
  *(_DWORD *)a1[2] = v8;
  v9 = a1[2];
  if ( !*(_DWORD *)v9 )
  {
    v10 = v6 - 1;
    if ( v10 )
    {
      if ( v10 != 1 )
      {
        *(_DWORD *)v9 = 87;
        goto LABEL_24;
      }
      v2 = DllAllocSplMem(v4);
      *(_DWORD *)a1[2] = v2 != 0 ? 0 : 0xE;
      if ( *(_DWORD *)a1[2] )
      {
LABEL_24:
        if ( !*(_DWORD *)a1[2] )
        {
          v13 = RevertToPrinterSelf();
          if ( v13 )
            LastError = 0;
          else
            LastError = GetLastError();
          *(_DWORD *)a1[2] = LastError;
          if ( !*(_DWORD *)a1[2] )
          {
            EnterSplSem(0);
            v15 = *(_QWORD *)(v3 + 64);
            if ( v15 )
            {
              v16 = SafeIncrementReference((unsigned int *)(v15 + 16));
              v17 = *(_QWORD *)(v3 + 64);
              if ( v16 > *(_DWORD *)(v17 + 248) )
                *(_DWORD *)(v17 + 248) = *(_DWORD *)(v17 + 16);
            }
            v18 = a1[2];
            *(_DWORD *)v18 = OpenPrinterKey(*(_QWORD *)(v3 + 64), 0x2001Fu, &v27, 0, 1);
            LeaveSplSem(v19);
            if ( !*(_DWORD *)a1[2] )
            {
              v20 = a1[2];
              *(_DWORD *)v20 = OpenPrintProcCacheKey(
                                 v27,
                                 0x2001Fu,
                                 1,
                                 *(struct _INISPOOLER **)(v3 + 168),
                                 (void **)&hKey);
              if ( !*(_DWORD *)a1[2] )
              {
                v21 = a1[2];
                *(_DWORD *)v21 = SplRegCreateKey(
                                   hKey,
                                   (const unsigned __int16 *)*a1[3],
                                   0,
                                   0x2001Fu,
                                   0,
                                   (void **)&v26,
                                   0);
                RegCloseKey(hKey);
                if ( !*(_DWORD *)a1[2] )
                {
                  v22 = a1[2];
                  *(_DWORD *)v22 = SplRegSetValue(v26, v7, 3u, (BYTE *)v2, v4, *(struct _INISPOOLER **)(v3 + 168));
                  RegCloseKey(v26);
                }
              }
            }
            EnterSplSem(0);
            v23 = v27;
            if ( v27 )
              RegCloseKey(v27);
            v24 = *(_QWORD *)(v3 + 64);
            if ( v24 )
            {
              v23 = (HKEY)(v24 + 16);
              if ( *(_DWORD *)(v24 + 16) )
                SafeDecrementReference((unsigned int *)v23);
            }
            LeaveSplSem(v23);
          }
          if ( v13 )
            ImpersonatePrinterClient(v13);
        }
        goto LABEL_44;
      }
      v11 = &PrintProcessorCaps2Fields;
      *(_DWORD *)v2 = *(_DWORD *)*a1[4];
      *(_DWORD *)(v2 + 4) = *(_DWORD *)(*a1[4] + 4);
      *(_DWORD *)(v2 + 8) = *(_DWORD *)(*a1[4] + 8);
      *(_DWORD *)(v2 + 12) = *(_DWORD *)(*a1[4] + 12);
      *(_DWORD *)(v2 + 16) = *(_DWORD *)(*a1[4] + 16);
      *(_DWORD *)(v2 + 20) = *(_DWORD *)(*a1[4] + 20);
      *(_DWORD *)(v2 + 24) = *(_DWORD *)(*a1[4] + 24);
      *(_DWORD *)(v2 + 28) = *(_DWORD *)(*a1[4] + 28);
      *(_DWORD *)(v2 + 32) = *(_DWORD *)(*a1[4] + 32);
    }
    else
    {
      v2 = DllAllocSplMem(v4);
      *(_DWORD *)a1[2] = v2 != 0 ? 0 : 0xE;
      if ( *(_DWORD *)a1[2] )
        goto LABEL_24;
      v11 = &PrintProcessorCaps1Fields;
      *(_DWORD *)v2 = *(_DWORD *)*a1[4];
      *(_DWORD *)(v2 + 4) = *(_DWORD *)(*a1[4] + 4);
      *(_DWORD *)(v2 + 8) = *(_DWORD *)(*a1[4] + 8);
      *(_DWORD *)(v2 + 12) = *(_DWORD *)(*a1[4] + 12);
    }
    if ( (unsigned int)MarshallDownStructure(v2, v11, v4, 0) )
      v12 = 0;
    else
      v12 = GetLastError();
    *(_DWORD *)a1[2] = v12;
    goto LABEL_24;
  }
LABEL_44:
  DllFreeSplMem(v2);
  if ( *(_DWORD *)a1[2] )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplSetPrintProcCacheData::<lambda_df5e0ff6e16271df119a4c7cf8f03739>::operator ()",
      L"Failed to set cache data for datatype '%ws'",
      *a1[3]);
}

```

## disassembly

```asm
0x18009103c  mov     [rsp-38h+arg_18], rbx
0x180091041  push    rbp
0x180091042  push    rsi
0x180091043  push    rdi
0x180091044  push    r12
0x180091046  push    r13
0x180091048  push    r14
0x18009104a  push    r15
0x18009104c  mov     rbp, rsp
0x18009104f  sub     rsp, 40h
0x180091053  mov     rax, [rcx]
0x180091056  xor     r12d, r12d
0x180091059  mov     rdi, rcx
0x18009105c  mov     esi, r12d
0x18009105f  mov     r14, [rax]
0x180091062  lea     r15d, [r12+24h]
0x180091067  mov     rax, [rcx+8]
0x18009106b  lea     edx, [r12+10h]
0x180091070  mov     [rbp+arg_10], r12
0x180091074  mov     [rbp+hKey], r12
0x180091078  mov     [rbp+arg_8], r12
0x18009107c  cmp     [rax], r15d
0x18009107f  jb      short loc_18009108D
0x180091081  lea     ebx, [rdx-0Eh]
0x180091084  lea     r13, ?szPrintProcCacheValue2@@3PAGA; "PrintProcCaps2"
0x18009108b  jmp     short loc_1800910AB
0x18009108d  cmp     [rax], edx
0x18009108f  jb      short loc_1800910A2
0x180091091  mov     ebx, 1
0x180091096  lea     r13, ?szPrintProcCacheValue1@@3PAGA; "PrintProcCaps1"
0x18009109d  mov     r15d, edx
0x1800910a0  jmp     short loc_1800910AB
0x1800910a2  mov     r15d, r12d
0x1800910a5  mov     r13, r12
0x1800910a8  mov     ebx, r12d
0x1800910ab  mov     rax, [rcx+18h]
0x1800910af  cmp     [rax], r12
0x1800910b2  jz      short loc_1800910E3
0x1800910b4  mov     rax, [rcx+20h]
0x1800910b8  cmp     [rax], r12
0x1800910bb  jz      short loc_1800910E3
0x1800910bd  test    ebx, ebx
0x1800910bf  jz      short loc_1800910E3
0x1800910c1  mov     rcx, r14
0x1800910c4  call    ValidateSpoolHandle
0x1800910c9  test    eax, eax
0x1800910cb  jz      short loc_1800910E3
0x1800910cd  mov     rax, [r14+0A8h]
0x1800910d4  mov     ecx, r12d
0x1800910d7  test    dword ptr [rax+0A8h], 4000000h
0x1800910e1  jnz     short loc_1800910E8
0x1800910e3  mov     ecx, 57h ; 'W'
0x1800910e8  mov     rax, [rdi+10h]
0x1800910ec  mov     [rax], ecx
0x1800910ee  mov     rax, [rdi+10h]
0x1800910f2  cmp     [rax], r12d
0x1800910f5  jnz     loc_1800913DC
0x1800910fb  sub     ebx, 1
0x1800910fe  jz      loc_1800911B9
0x180091104  cmp     ebx, 1
0x180091107  jz      short loc_180091114
0x180091109  mov     dword ptr [rax], 57h ; 'W'
0x18009110f  jmp     loc_18009123B
0x180091114  mov     ecx, r15d
0x180091117  call    cs:__imp_DllAllocSplMem
0x18009111d  mov     rsi, rax
0x180091120  neg     rax
0x180091123  mov     rax, [rdi+10h]
0x180091127  sbb     ecx, ecx
0x180091129  not     ecx
0x18009112b  and     ecx, 0Eh
0x18009112e  mov     [rax], ecx
0x180091130  mov     rax, [rdi+10h]
0x180091134  cmp     [rax], r12d
0x180091137  jnz     loc_18009123B
0x18009113d  mov     rax, [rdi+20h]
0x180091141  lea     rdx, ?PrintProcessorCaps2Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const PrintProcessorCaps2Fields
0x180091148  mov     rcx, [rax]
0x18009114b  mov     eax, [rcx]
0x18009114d  mov     [rsi], eax
0x18009114f  mov     rax, [rdi+20h]
0x180091153  mov     rcx, [rax]
0x180091156  mov     eax, [rcx+4]
0x180091159  mov     [rsi+4], eax
0x18009115c  mov     rax, [rdi+20h]
0x180091160  mov     rcx, [rax]
0x180091163  mov     eax, [rcx+8]
0x180091166  mov     [rsi+8], eax
0x180091169  mov     rax, [rdi+20h]
0x18009116d  mov     rcx, [rax]
0x180091170  mov     eax, [rcx+0Ch]
0x180091173  mov     [rsi+0Ch], eax
0x180091176  mov     rax, [rdi+20h]
0x18009117a  mov     rcx, [rax]
0x18009117d  mov     eax, [rcx+10h]
0x180091180  mov     [rsi+10h], eax
0x180091183  mov     rax, [rdi+20h]
0x180091187  mov     rcx, [rax]
0x18009118a  mov     eax, [rcx+14h]
0x18009118d  mov     [rsi+14h], eax
0x180091190  mov     rax, [rdi+20h]
0x180091194  mov     rcx, [rax]
0x180091197  mov     eax, [rcx+18h]
0x18009119a  mov     [rsi+18h], eax
0x18009119d  mov     rax, [rdi+20h]
0x1800911a1  mov     rcx, [rax]
0x1800911a4  mov     eax, [rcx+1Ch]
0x1800911a7  mov     [rsi+1Ch], eax
0x1800911aa  mov     rax, [rdi+20h]
0x1800911ae  mov     rcx, [rax]
0x1800911b1  mov     eax, [rcx+20h]
0x1800911b4  mov     [rsi+20h], eax
0x1800911b7  jmp     short loc_180091217
0x1800911b9  mov     ecx, r15d
0x1800911bc  call    cs:__imp_DllAllocSplMem
0x1800911c2  mov     rsi, rax
0x1800911c5  neg     rax
0x1800911c8  mov     rax, [rdi+10h]
0x1800911cc  sbb     ecx, ecx
0x1800911ce  not     ecx
0x1800911d0  and     ecx, 0Eh
0x1800911d3  mov     [rax], ecx
0x1800911d5  mov     rax, [rdi+10h]
0x1800911d9  cmp     [rax], r12d
0x1800911dc  jnz     short loc_18009123B
0x1800911de  mov     rax, [rdi+20h]
0x1800911e2  lea     rdx, ?PrintProcessorCaps1Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const PrintProcessorCaps1Fields
0x1800911e9  mov     rcx, [rax]
0x1800911ec  mov     eax, [rcx]
0x1800911ee  mov     [rsi], eax
0x1800911f0  mov     rax, [rdi+20h]
0x1800911f4  mov     rcx, [rax]
0x1800911f7  mov     eax, [rcx+4]
0x1800911fa  mov     [rsi+4], eax
0x1800911fd  mov     rax, [rdi+20h]
0x180091201  mov     rcx, [rax]
0x180091204  mov     eax, [rcx+8]
0x180091207  mov     [rsi+8], eax
0x18009120a  mov     rax, [rdi+20h]
0x18009120e  mov     rcx, [rax]
0x180091211  mov     eax, [rcx+0Ch]
0x180091214  mov     [rsi+0Ch], eax
0x180091217  xor     r9d, r9d
0x18009121a  mov     r8d, r15d
0x18009121d  mov     rcx, rsi
0x180091220  call    cs:__imp_MarshallDownStructure
0x180091226  test    eax, eax
0x180091228  jz      short loc_18009122F
0x18009122a  mov     eax, r12d
0x18009122d  jmp     short loc_180091235
0x18009122f  call    cs:__imp_GetLastError
0x180091235  mov     rcx, [rdi+10h]
0x180091239  mov     [rcx], eax
0x18009123b  mov     rax, [rdi+10h]
0x18009123f  cmp     [rax], r12d
0x180091242  jnz     loc_1800913DC
0x180091248  call    cs:__imp_RevertToPrinterSelf
0x18009124e  mov     r12, rax
0x180091251  test    rax, rax
0x180091254  jz      short loc_18009125A
0x180091256  xor     eax, eax
0x180091258  jmp     short loc_180091260
0x18009125a  call    cs:__imp_GetLastError
0x180091260  mov     rcx, [rdi+10h]
0x180091264  mov     [rcx], eax
0x180091266  mov     rax, [rdi+10h]
0x18009126a  cmp     dword ptr [rax], 0
0x18009126d  jnz     loc_1800913CB
0x180091273  xor     ecx, ecx
0x180091275  call    EnterSplSem
0x18009127a  mov     rcx, [r14+40h]
0x18009127e  test    rcx, rcx
0x180091281  jz      short loc_1800912A1
0x180091283  add     rcx, 10h; unsigned int *
0x180091287  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18009128c  mov     rcx, [r14+40h]
0x180091290  cmp     eax, [rcx+0F8h]
0x180091296  jbe     short loc_1800912A1
0x180091298  mov     eax, [rcx+10h]
0x18009129b  mov     [rcx+0F8h], eax
0x1800912a1  mov     rcx, [r14+40h]
0x1800912a5  lea     r8, [rbp+arg_10]
0x1800912a9  mov     rbx, [rdi+10h]
0x1800912ad  xor     r9d, r9d
0x1800912b0  mov     edx, 2001Fh
0x1800912b5  mov     dword ptr [rsp+40h+var_20], 1
0x1800912bd  call    OpenPrinterKey
0x1800912c2  mov     [rbx], eax
0x1800912c4  call    LeaveSplSem
0x1800912c9  mov     rax, [rdi+10h]
0x1800912cd  cmp     dword ptr [rax], 0
0x1800912d0  jnz     loc_180091399
0x1800912d6  mov     r9, [r14+0A8h]; struct _INISPOOLER *
0x1800912dd  mov     rbx, rax
0x1800912e0  mov     rcx, [rbp+arg_10]; void *
0x1800912e4  lea     rax, [rbp+hKey]
0x1800912e8  mov     edx, 2001Fh; unsigned int
0x1800912ed  mov     [rsp+40h+var_20], rax; void **
0x1800912f2  mov     r8d, 1; int
0x1800912f8  call    ?OpenPrintProcCacheKey@@YAKPEAXKHPEAU_INISPOOLER@@PEAPEAX@Z; OpenPrintProcCacheKey(void *,ulong,int,_INISPOOLER *,void * *)
0x1800912fd  mov     [rbx], eax
0x1800912ff  mov     rax, [rdi+10h]
0x180091303  cmp     dword ptr [rax], 0
0x180091306  jnz     loc_180091399
0x18009130c  mov     rdx, [rdi+18h]
0x180091310  mov     rbx, rax
0x180091313  mov     rax, [r14+0A8h]
0x18009131a  mov     r9d, 2001Fh; unsigned int
0x180091320  mov     rcx, [rbp+hKey]; void *
0x180091324  xor     r8d, r8d; unsigned int
0x180091327  mov     [rsp+40h+var_8], rax; struct _INISPOOLER *
0x18009132c  lea     rax, [rbp+arg_8]
0x180091330  mov     rdx, [rdx]; unsigned __int16 *
0x180091333  mov     [rsp+40h+var_10], 0; unsigned int *
0x18009133c  mov     [rsp+40h+var_18], rax; void **
0x180091341  mov     [rsp+40h+var_20], 0; struct _SECURITY_ATTRIBUTES *
0x18009134a  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18009134f  mov     [rbx], eax
0x180091351  mov     rcx, [rbp+hKey]; hKey
0x180091355  call    cs:__imp_RegCloseKey
0x18009135b  mov     rax, [rdi+10h]
0x18009135f  cmp     dword ptr [rax], 0
0x180091362  jnz     short loc_180091399
0x180091364  mov     rcx, [rbp+arg_8]; void *
0x180091368  mov     rbx, rax
0x18009136b  mov     rax, [r14+0A8h]
0x180091372  mov     r9, rsi; unsigned __int8 *
0x180091375  mov     [rsp+40h+var_18], rax; struct _INISPOOLER *
0x18009137a  mov     r8d, 3; unsigned int
0x180091380  mov     rdx, r13; unsigned __int16 *
0x180091383  mov     dword ptr [rsp+40h+var_20], r15d; unsigned int
0x180091388  call    ?SplRegSetValue@@YAJPEAXPEBGKPEBEKPEAU_INISPOOLER@@@Z; SplRegSetValue(void *,ushort const *,ulong,uchar const *,ulong,_INISPOOLER *)
0x18009138d  mov     [rbx], eax
0x18009138f  mov     rcx, [rbp+arg_8]; hKey
0x180091393  call    cs:__imp_RegCloseKey
0x180091399  xor     ecx, ecx
0x18009139b  call    EnterSplSem
0x1800913a0  mov     rcx, [rbp+arg_10]; hKey
0x1800913a4  test    rcx, rcx
0x1800913a7  jz      short loc_1800913AF
0x1800913a9  call    cs:__imp_RegCloseKey
0x1800913af  mov     rax, [r14+40h]
0x1800913b3  test    rax, rax
0x1800913b6  jz      short loc_1800913C6
0x1800913b8  lea     rcx, [rax+10h]; unsigned int *
0x1800913bc  cmp     dword ptr [rcx], 0
0x1800913bf  jz      short loc_1800913C6
0x1800913c1  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800913c6  call    LeaveSplSem
0x1800913cb  test    r12, r12
0x1800913ce  jz      short loc_1800913D9
0x1800913d0  mov     rcx, r12; hToken
0x1800913d3  call    cs:__imp_ImpersonatePrinterClient
0x1800913d9  xor     r12d, r12d
0x1800913dc  mov     rcx, rsi
0x1800913df  call    cs:__imp_DllFreeSplMem
0x1800913e5  mov     rax, [rdi+10h]
0x1800913e9  cmp     [rax], r12d
0x1800913ec  jz      short loc_180091408
0x1800913ee  mov     r8, [rdi+18h]
0x1800913f2  lea     rdx, aFailedToSetCac; "Failed to set cache data for datatype '"...
0x1800913f9  lea     rcx, aSplsetprintpro_0; "SplSetPrintProcCacheData::<lambda_df5e0"...
0x180091400  mov     r8, [r8]
0x180091403  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180091408  mov     rbx, [rsp+40h+arg_18]
0x180091410  add     rsp, 40h
0x180091414  pop     r15
0x180091416  pop     r14
0x180091418  pop     r13
0x18009141a  pop     r12
0x18009141c  pop     rdi
0x18009141d  pop     rsi
0x18009141e  pop     rbp
0x18009141f  retn
```
