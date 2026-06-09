# _lambda_8cac10d3f4426eeedcc8a30f5a16a68b_::operator()

- ea: `0x180090b04`
- end: `0x180090e1d`
- name: `_lambda_8cac10d3f4426eeedcc8a30f5a16a68b_::operator()`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18008fee0`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180013b00`
- `0x180031478`
- `0x18003ea2c`
- `0x180090b04`
- `0x18009ef60`
- `0x18009f050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090dac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090dac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090dc2`
- `SPOOLSS!DllFreeSplMem` at `0x180090d64`
- `SPOOLSS!DllFreeSplMem` at `0x180090d76`
- `SPOOLSS!DllFreeSplMem` at `0x180090d64`
- `SPOOLSS!DllFreeSplMem` at `0x180090d76`
- `SPOOLSS!DllAllocSplMem` at `0x180090ca5`
- `SPOOLSS!DllAllocSplMem` at `0x180090ce1`
- `SPOOLSS!DllAllocSplMem` at `0x180090ca5`
- `SPOOLSS!DllAllocSplMem` at `0x180090ce1`
- `SPOOLSS!RevertToPrinterSelf` at `0x180090b85`
- `SPOOLSS!RevertToPrinterSelf` at `0x180090b85`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180090dec`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180090dec`

## string_xrefs

- `0x180090e02`: `SplEnumPrintProcCacheData::<lambda_8cac10d3f4426eeedcc8a30f5a16a68b>::operator ()`
- `0x180090dfb`: `Failed to enumerate cache data.`

## pseudocode

```c
void __fastcall lambda_8cac10d3f4426eeedcc8a30f5a16a68b_::operator()(__int64 **a1)
{
  __int64 v2; // rsi
  __int64 *v3; // rax
  int v4; // ecx
  HANDLE v5; // r15
  DWORD LastError; // eax
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rbx
  __int64 *v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 *v16; // rcx
  unsigned int v17; // r14d
  __int64 v18; // rax
  unsigned int i; // r14d
  HKEY v20; // rcx
  __int64 v21; // rax
  HKEY v22; // [rsp+50h] [rbp-10h] BYREF
  struct _FILETIME v23; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v26; // [rsp+B0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+58h] BYREF

  v2 = **a1;
  v3 = a1[2];
  v22 = 0;
  hKey = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  if ( !*v3
    || !(unsigned int)ValidateSpoolHandle(v2, 16)
    || (v4 = 0, (*(_DWORD *)(*(_QWORD *)(v2 + 168) + 168LL) & 0x4000000) == 0) )
  {
    v4 = 87;
  }
  *(_DWORD *)a1[1] = v4;
  if ( !*(_DWORD *)a1[1] )
  {
    v5 = RevertToPrinterSelf();
    if ( v5 )
      LastError = 0;
    else
      LastError = GetLastError();
    *(_DWORD *)a1[1] = LastError;
    if ( !*(_DWORD *)a1[1] )
    {
      EnterSplSem(0);
      v7 = *(_QWORD *)(v2 + 64);
      if ( v7 )
      {
        v8 = SafeIncrementReference((unsigned int *)(v7 + 16));
        v9 = *(_QWORD *)(v2 + 64);
        if ( v8 > *(_DWORD *)(v9 + 248) )
          *(_DWORD *)(v9 + 248) = *(_DWORD *)(v9 + 16);
      }
      v10 = a1[1];
      *(_DWORD *)v10 = OpenPrinterKey(*(_QWORD *)(v2 + 64), 0x2001Fu, &v22, 0, 1);
      LeaveSplSem(v11);
      if ( !*(_DWORD *)a1[1] )
      {
        v12 = a1[1];
        *(_DWORD *)v12 = OpenPrintProcCacheKey(v22, 0x2001Fu, 0, *(struct _INISPOOLER **)(v2 + 168), (void **)&hKey);
        if ( !*(_DWORD *)a1[1] )
        {
          v13 = a1[1];
          *(_DWORD *)v13 = SplRegQueryInfoKey(hKey, &v24, &v25, 0, 0, 0, 0, 0, *(struct _INISPOOLER **)(v2 + 168));
          v14 = 8LL * v24;
          if ( v14 > 0xFFFFFFFF )
            *(_DWORD *)a1[1] = 87;
          if ( !*(_DWORD *)a1[1] )
          {
            v15 = DllAllocSplMem(v14);
            *(_DWORD *)a1[1] = v15 == 0 ? 0xE : 0;
            v16 = a1[1];
            if ( !*(_DWORD *)v16 )
            {
              v17 = 0;
              do
              {
                if ( v17 >= v24 )
                  break;
                v18 = DllAllocSplMem(2 * v25 + 2);
                *(_QWORD *)(v15 + 8LL * v17) = v18;
                *(_DWORD *)a1[1] = v18 != 0 ? 0 : 0xE;
                if ( !*(_DWORD *)a1[1] )
                {
                  v26 = v25 + 1;
                  *(_DWORD *)a1[1] = SplRegEnumKey(
                                       hKey,
                                       v17,
                                       *(unsigned __int16 **)(v15 + 8LL * v17),
                                       &v26,
                                       &v23,
                                       *(struct _INISPOOLER **)(v2 + 168));
                }
                v16 = a1[1];
                ++v17;
              }
              while ( !*(_DWORD *)v16 );
              if ( !*(_DWORD *)v16 )
                goto LABEL_29;
            }
            if ( v15 )
            {
              for ( i = 0; i < v24; ++i )
                DllFreeSplMem(*(_QWORD *)(v15 + 8LL * i));
              DllFreeSplMem(v15);
              *(_QWORD *)*a1[2] = 0;
              *(_DWORD *)*a1[3] = 0;
            }
            else
            {
LABEL_29:
              *(_QWORD *)*a1[2] = v15;
              *(_DWORD *)*a1[3] = v24;
            }
          }
          RegCloseKey(hKey);
        }
      }
      EnterSplSem(0);
      v20 = v22;
      if ( v22 )
        RegCloseKey(v22);
      v21 = *(_QWORD *)(v2 + 64);
      if ( v21 )
      {
        v20 = (HKEY)(v21 + 16);
        if ( *(_DWORD *)(v21 + 16) )
          SafeDecrementReference((unsigned int *)v20);
      }
      LeaveSplSem(v20);
    }
    if ( v5 )
      ImpersonatePrinterClient(v5);
  }
  if ( *(_DWORD *)a1[1] )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplEnumPrintProcCacheData::<lambda_8cac10d3f4426eeedcc8a30f5a16a68b>::operator ()",
      L"Failed to enumerate cache data.");
}

```

## disassembly

```asm
0x180090b04  push    rbp
0x180090b06  push    rbx
0x180090b07  push    rsi
0x180090b08  push    rdi
0x180090b09  push    r12
0x180090b0b  push    r14
0x180090b0d  push    r15
0x180090b0f  mov     rbp, rsp
0x180090b12  sub     rsp, 60h
0x180090b16  mov     rax, [rcx]
0x180090b19  xor     r12d, r12d
0x180090b1c  mov     rdi, rcx
0x180090b1f  mov     rsi, [rax]
0x180090b22  lea     r14d, [r12+57h]
0x180090b27  mov     rax, [rcx+10h]
0x180090b2b  mov     [rbp+var_10], r12
0x180090b2f  mov     [rbp+hKey], r12
0x180090b33  mov     [rbp+arg_0], r12d
0x180090b37  mov     [rbp+arg_8], r12d
0x180090b3b  mov     [rbp+arg_10], r12d
0x180090b3f  mov     qword ptr [rbp+var_8.dwLowDateTime], r12
0x180090b43  cmp     [rax], r12
0x180090b46  jz      short loc_180090B6F
0x180090b48  lea     edx, [r12+10h]
0x180090b4d  mov     rcx, rsi
0x180090b50  call    ValidateSpoolHandle
0x180090b55  test    eax, eax
0x180090b57  jz      short loc_180090B6F
0x180090b59  mov     rax, [rsi+0A8h]
0x180090b60  mov     ecx, r12d
0x180090b63  test    dword ptr [rax+0A8h], 4000000h
0x180090b6d  jnz     short loc_180090B72
0x180090b6f  mov     ecx, r14d
0x180090b72  mov     rax, [rdi+8]
0x180090b76  mov     [rax], ecx
0x180090b78  mov     rax, [rdi+8]
0x180090b7c  cmp     [rax], r12d
0x180090b7f  jnz     loc_180090DF2
0x180090b85  call    cs:__imp_RevertToPrinterSelf
0x180090b8b  mov     r15, rax
0x180090b8e  test    rax, rax
0x180090b91  jz      short loc_180090B98
0x180090b93  mov     eax, r12d
0x180090b96  jmp     short loc_180090B9E
0x180090b98  call    cs:__imp_GetLastError
0x180090b9e  mov     rcx, [rdi+8]
0x180090ba2  mov     [rcx], eax
0x180090ba4  mov     rax, [rdi+8]
0x180090ba8  cmp     [rax], r12d
0x180090bab  jnz     loc_180090DE4
0x180090bb1  xor     ecx, ecx
0x180090bb3  call    EnterSplSem
0x180090bb8  mov     rcx, [rsi+40h]
0x180090bbc  test    rcx, rcx
0x180090bbf  jz      short loc_180090BDF
0x180090bc1  add     rcx, 10h; unsigned int *
0x180090bc5  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180090bca  mov     rcx, [rsi+40h]
0x180090bce  cmp     eax, [rcx+0F8h]
0x180090bd4  jbe     short loc_180090BDF
0x180090bd6  mov     eax, [rcx+10h]
0x180090bd9  mov     [rcx+0F8h], eax
0x180090bdf  mov     rcx, [rsi+40h]
0x180090be3  lea     r8, [rbp+var_10]
0x180090be7  mov     rbx, [rdi+8]
0x180090beb  xor     r9d, r9d
0x180090bee  mov     edx, 2001Fh
0x180090bf3  mov     dword ptr [rsp+60h+var_40], 1
0x180090bfb  call    OpenPrinterKey
0x180090c00  mov     [rbx], eax
0x180090c02  call    LeaveSplSem
0x180090c07  mov     rax, [rdi+8]
0x180090c0b  cmp     [rax], r12d
0x180090c0e  jnz     loc_180090DB2
0x180090c14  mov     r9, [rsi+0A8h]; struct _INISPOOLER *
0x180090c1b  mov     rbx, rax
0x180090c1e  mov     rcx, [rbp+var_10]; void *
0x180090c22  lea     rax, [rbp+hKey]
0x180090c26  xor     r8d, r8d; int
0x180090c29  mov     [rsp+60h+var_40], rax; void **
0x180090c2e  mov     edx, 2001Fh; unsigned int
0x180090c33  call    ?OpenPrintProcCacheKey@@YAKPEAXKHPEAU_INISPOOLER@@PEAPEAX@Z; OpenPrintProcCacheKey(void *,ulong,int,_INISPOOLER *,void * *)
0x180090c38  mov     [rbx], eax
0x180090c3a  mov     rax, [rdi+8]
0x180090c3e  cmp     [rax], r12d
0x180090c41  jnz     loc_180090DB2
0x180090c47  mov     rcx, [rbp+hKey]; void *
0x180090c4b  lea     r8, [rbp+arg_8]; unsigned int *
0x180090c4f  mov     rbx, rax
0x180090c52  lea     rdx, [rbp+arg_0]; unsigned int *
0x180090c56  mov     rax, [rsi+0A8h]
0x180090c5d  xor     r9d, r9d; unsigned int *
0x180090c60  mov     [rsp+60h+var_20], rax; struct _INISPOOLER *
0x180090c65  mov     [rsp+60h+var_28], r12; struct _FILETIME *
0x180090c6a  mov     [rsp+60h+var_30], r12; unsigned int *
0x180090c6f  mov     [rsp+60h+var_38], r12; unsigned int *
0x180090c74  mov     [rsp+60h+var_40], r12; unsigned int *
0x180090c79  call    ?SplRegQueryInfoKey@@YAJPEAXPEAK11111PEAU_FILETIME@@PEAU_INISPOOLER@@@Z; SplRegQueryInfoKey(void *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *,_INISPOOLER *)
0x180090c7e  mov     [rbx], eax
0x180090c80  mov     eax, 0FFFFFFFFh
0x180090c85  mov     ecx, [rbp+arg_0]
0x180090c88  shl     rcx, 3
0x180090c8c  cmp     rcx, rax
0x180090c8f  jbe     short loc_180090C98
0x180090c91  mov     rax, [rdi+8]
0x180090c95  mov     [rax], r14d
0x180090c98  mov     rax, [rdi+8]
0x180090c9c  cmp     [rax], r12d
0x180090c9f  jnz     loc_180090DA8
0x180090ca5  call    cs:__imp_DllAllocSplMem
0x180090cab  mov     rcx, rax
0x180090cae  mov     rbx, rax
0x180090cb1  neg     rcx
0x180090cb4  mov     rcx, [rdi+8]
0x180090cb8  sbb     edx, edx
0x180090cba  not     edx
0x180090cbc  and     edx, 0Eh
0x180090cbf  mov     [rcx], edx
0x180090cc1  mov     rcx, [rdi+8]
0x180090cc5  cmp     [rcx], r12d
0x180090cc8  jnz     loc_180090D4F
0x180090cce  mov     r14d, r12d
0x180090cd1  cmp     r14d, [rbp+arg_0]
0x180090cd5  jnb     short loc_180090D4A
0x180090cd7  mov     ecx, [rbp+arg_8]
0x180090cda  lea     ecx, ds:2[rcx*2]
0x180090ce1  call    cs:__imp_DllAllocSplMem
0x180090ce7  mov     r8d, r14d
0x180090cea  mov     [rbx+r8*8], rax
0x180090cee  neg     rax
0x180090cf1  mov     rax, [rdi+8]
0x180090cf5  sbb     ecx, ecx
0x180090cf7  not     ecx
0x180090cf9  and     ecx, 0Eh
0x180090cfc  mov     [rax], ecx
0x180090cfe  mov     rax, [rdi+8]
0x180090d02  cmp     [rax], r12d
0x180090d05  jnz     short loc_180090D3E
0x180090d07  mov     eax, [rbp+arg_8]
0x180090d0a  lea     r9, [rbp+arg_10]; unsigned int *
0x180090d0e  mov     rcx, [rbp+hKey]; void *
0x180090d12  inc     eax
0x180090d14  mov     [rbp+arg_10], eax
0x180090d17  mov     edx, r14d; unsigned int
0x180090d1a  mov     rax, [rsi+0A8h]
0x180090d21  mov     r8, [rbx+r8*8]; unsigned __int16 *
0x180090d25  mov     [rsp+60h+var_38], rax; struct _INISPOOLER *
0x180090d2a  lea     rax, [rbp+var_8]
0x180090d2e  mov     [rsp+60h+var_40], rax; struct _FILETIME *
0x180090d33  call    ?SplRegEnumKey@@YAJPEAXKPEAGPEAKPEAU_FILETIME@@PEAU_INISPOOLER@@@Z; SplRegEnumKey(void *,ulong,ushort *,ulong *,_FILETIME *,_INISPOOLER *)
0x180090d38  mov     rcx, [rdi+8]
0x180090d3c  mov     [rcx], eax
0x180090d3e  mov     rcx, [rdi+8]
0x180090d42  inc     r14d
0x180090d45  cmp     [rcx], r12d
0x180090d48  jz      short loc_180090CD1
0x180090d4a  cmp     [rcx], r12d
0x180090d4d  jz      short loc_180090D92
0x180090d4f  test    rbx, rbx
0x180090d52  jz      short loc_180090D92
0x180090d54  mov     r14d, r12d
0x180090d57  cmp     [rbp+arg_0], r12d
0x180090d5b  jbe     short loc_180090D73
0x180090d5d  mov     ecx, r14d
0x180090d60  mov     rcx, [rbx+rcx*8]
0x180090d64  call    cs:__imp_DllFreeSplMem
0x180090d6a  inc     r14d
0x180090d6d  cmp     r14d, [rbp+arg_0]
0x180090d71  jb      short loc_180090D5D
0x180090d73  mov     rcx, rbx
0x180090d76  call    cs:__imp_DllFreeSplMem
0x180090d7c  mov     rax, [rdi+10h]
0x180090d80  mov     rcx, [rax]
0x180090d83  mov     [rcx], r12
0x180090d86  mov     rax, [rdi+18h]
0x180090d8a  mov     rcx, [rax]
0x180090d8d  mov     [rcx], r12d
0x180090d90  jmp     short loc_180090DA8
0x180090d92  mov     rax, [rdi+10h]
0x180090d96  mov     rcx, [rax]
0x180090d99  mov     [rcx], rbx
0x180090d9c  mov     rax, [rdi+18h]
0x180090da0  mov     rcx, [rax]
0x180090da3  mov     eax, [rbp+arg_0]
0x180090da6  mov     [rcx], eax
0x180090da8  mov     rcx, [rbp+hKey]; hKey
0x180090dac  call    cs:__imp_RegCloseKey
0x180090db2  xor     ecx, ecx
0x180090db4  call    EnterSplSem
0x180090db9  mov     rcx, [rbp+var_10]; hKey
0x180090dbd  test    rcx, rcx
0x180090dc0  jz      short loc_180090DC8
0x180090dc2  call    cs:__imp_RegCloseKey
0x180090dc8  mov     rax, [rsi+40h]
0x180090dcc  test    rax, rax
0x180090dcf  jz      short loc_180090DDF
0x180090dd1  lea     rcx, [rax+10h]; unsigned int *
0x180090dd5  cmp     [rcx], r12d
0x180090dd8  jz      short loc_180090DDF
0x180090dda  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180090ddf  call    LeaveSplSem
0x180090de4  test    r15, r15
0x180090de7  jz      short loc_180090DF2
0x180090de9  mov     rcx, r15; hToken
0x180090dec  call    cs:__imp_ImpersonatePrinterClient
0x180090df2  mov     rax, [rdi+8]
0x180090df6  cmp     [rax], r12d
0x180090df9  jz      short loc_180090E0E
0x180090dfb  lea     rdx, aFailedToEnumer_3; "Failed to enumerate cache data."
0x180090e02  lea     rcx, aSplenumprintpr_6; "SplEnumPrintProcCacheData::<lambda_8cac"...
0x180090e09  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180090e0e  add     rsp, 60h
0x180090e12  pop     r15
0x180090e14  pop     r14
0x180090e16  pop     r12
0x180090e18  pop     rdi
0x180090e19  pop     rsi
0x180090e1a  pop     rbx
0x180090e1b  pop     rbp
0x180090e1c  retn
```
