# DsPrune(ulong *)

- ea: `0x1800a7810`
- end: `0x1800a79e2`
- name: `?DsPrune@@YAKPEAK@Z`
- size: `466`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800227a4`
- `0x18003ea2c`
- `0x1800a5db8`
- `0x1800a7454`
- `0x1800a7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a783f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7957`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a798e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a783f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7957`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a798e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7913`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a791e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a791e`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7848`
- `SPOOLSS!DllFreeSplMem` at `0x1800a79af`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7848`
- `SPOOLSS!DllFreeSplMem` at `0x1800a79af`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a7852`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a7852`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a79b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a79b5`
- `netutils!NetApiBufferFree` at `0x1800a79a6`
- `netutils!NetApiBufferFree` at `0x1800a79a6`
- `logoncli!DsGetDcSiteCoverageW` at `0x1800a7886`
- `logoncli!DsGetDcSiteCoverageW` at `0x1800a7886`

## string_xrefs

- `0x1800a7861`: `Failed to CoInit on DsPrune thread.  Error hr: 0x%x`

## pseudocode

```c
__int64 __fastcall DsPrune(_DWORD *Parameter)
{
  LPCWSTR v1; // rdi
  HRESULT v3; // eax
  unsigned __int16 v4; // bx
  unsigned int SpoolerNumericPolicy; // eax
  unsigned int v9; // eax
  int v10; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v12; // edi
  unsigned int v13; // ebx
  unsigned int v14; // eax
  _DWORD v15[4]; // [rsp+20h] [rbp-10h] BYREF
  ULONG EntryCount; // [rsp+50h] [rbp+20h] BYREF
  LPCWSTR lpszPathName; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR *SiteNames; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  SiteNames = 0;
  lpszPathName = 0;
  EntryCount = 0;
  if ( Parameter )
  {
    Sleep(60000 * *Parameter);
    DllFreeSplMem(Parameter);
  }
  v3 = CoInitializeEx(0, 0);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( !DsGetDcSiteCoverageW(0, &EntryCount, &SiteNames) )
    {
      if ( !GetDomainRoot((unsigned __int16 **)&lpszPathName) )
      {
        while ( 1 )
        {
          v15[0] = GetSpoolerNumericPolicy(L"PruneDownlevel");
          SpoolerNumericPolicy = GetSpoolerNumericPolicy(L"PruningRetries");
          if ( SpoolerNumericPolicy > 0xA )
            SpoolerNumericPolicy = 10;
          v15[1] = SpoolerNumericPolicy;
          v15[2] = GetSpoolerNumericPolicy(L"PruningRetryLog");
          v9 = GetSpoolerNumericPolicy(L"PruningPriority");
          v10 = v9;
          if ( v9 != dwLastPruningPriority )
          {
            dwLastPruningPriority = v9;
            if ( v9 - 3 <= 0xFFFFFFFA )
              v10 = 0;
            CurrentThread = GetCurrentThread();
            SetThreadPriority(CurrentThread, v10);
          }
          DeleteOrphans(SiteNames, EntryCount, lpszPathName, (struct _PRUNINGPOLICIES *)v15);
          v12 = GetSpoolerNumericPolicy(L"PruningInterval");
          v13 = v12;
          while ( v13 > 0x3C )
          {
            Sleep(0x36EE80u);
            v14 = GetSpoolerNumericPolicy(L"PruningInterval");
            if ( v14 != v12 )
            {
              v12 = v14;
              v13 = v14;
            }
            if ( v13 != -1 )
            {
              if ( v13 <= 0x3C )
                break;
              v13 -= 60;
            }
          }
          Sleep(60000 * v13);
        }
      }
      v1 = lpszPathName;
    }
    if ( SiteNames )
      NetApiBufferFree(SiteNames);
    DllFreeSplMem(v1);
    CoUninitialize();
    LocalSpoolerTelemetry::WriteDbgTraceError("DsPrune", L"DsPruning operations failed.");
    return 0;
  }
  else
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "DsPrune",
      L"Failed to CoInit on DsPrune thread.  Error hr: 0x%x",
      (unsigned int)v3);
    return v4;
  }
}

```

## disassembly

```asm
0x1800a7810  mov     [rsp-18h+arg_18], rbx
0x1800a7815  push    rbp
0x1800a7816  push    rdi
0x1800a7817  push    r14
0x1800a7819  mov     rbp, rsp
0x1800a781c  sub     rsp, 30h
0x1800a7820  xor     edi, edi
0x1800a7822  mov     [rbp+SiteNames], 0
0x1800a782a  mov     [rbp+lpszPathName], rdi
0x1800a782e  mov     rbx, rcx
0x1800a7831  mov     [rbp+EntryCount], edi
0x1800a7834  test    rcx, rcx
0x1800a7837  jz      short loc_1800A784E
0x1800a7839  imul    ecx, [rcx], 0EA60h; dwMilliseconds
0x1800a783f  call    cs:__imp_Sleep
0x1800a7845  mov     rcx, rbx
0x1800a7848  call    cs:__imp_DllFreeSplMem
0x1800a784e  xor     edx, edx; dwCoInit
0x1800a7850  xor     ecx, ecx; pvReserved
0x1800a7852  call    cs:__imp_CoInitializeEx
0x1800a7858  mov     ebx, eax
0x1800a785a  test    eax, eax
0x1800a785c  jns     short loc_1800A787C
0x1800a785e  mov     r8d, eax
0x1800a7861  lea     rdx, aFailedToCoinit; "Failed to CoInit on DsPrune thread.  Er"...
0x1800a7868  lea     rcx, aDsprune; "DsPrune"
0x1800a786f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a7874  movzx   eax, bx
0x1800a7877  jmp     loc_1800A79D4
0x1800a787c  lea     r8, [rbp+SiteNames]; SiteNames
0x1800a7880  xor     ecx, ecx; ServerName
0x1800a7882  lea     rdx, [rbp+EntryCount]; EntryCount
0x1800a7886  call    cs:__imp_DsGetDcSiteCoverageW
0x1800a788c  mov     ebx, eax
0x1800a788e  test    eax, eax
0x1800a7890  jnz     loc_1800A799D
0x1800a7896  lea     rcx, [rbp+lpszPathName]; unsigned __int16 **
0x1800a789a  call    ?GetDomainRoot@@YAKPEAPEAG@Z; GetDomainRoot(ushort * *)
0x1800a789f  mov     ebx, eax
0x1800a78a1  test    eax, eax
0x1800a78a3  jnz     loc_1800A7999
0x1800a78a9  lea     r14d, [rax+0Ah]
0x1800a78ad  xor     edx, edx
0x1800a78af  lea     rcx, aPrunedownlevel; "PruneDownlevel"
0x1800a78b6  call    GetSpoolerNumericPolicy
0x1800a78bb  mov     edx, 2
0x1800a78c0  mov     [rbp+var_10], eax
0x1800a78c3  lea     rcx, aPruningretries; "PruningRetries"
0x1800a78ca  call    GetSpoolerNumericPolicy
0x1800a78cf  cmp     eax, r14d
0x1800a78d2  lea     rcx, aPruningretrylo; "PruningRetryLog"
0x1800a78d9  cmova   eax, r14d
0x1800a78dd  xor     edx, edx
0x1800a78df  mov     [rbp+var_C], eax
0x1800a78e2  call    GetSpoolerNumericPolicy
0x1800a78e7  xor     edx, edx
0x1800a78e9  mov     [rbp+var_8], eax
0x1800a78ec  lea     rcx, aPruningpriorit; "PruningPriority"
0x1800a78f3  call    GetSpoolerNumericPolicy
0x1800a78f8  cmp     eax, cs:?dwLastPruningPriority@@3KA; ulong dwLastPruningPriority
0x1800a78fe  mov     ebx, eax
0x1800a7900  jz      short loc_1800A7924
0x1800a7902  lea     ecx, [rax-3]
0x1800a7905  mov     cs:?dwLastPruningPriority@@3KA, eax; ulong dwLastPruningPriority
0x1800a790b  xor     eax, eax
0x1800a790d  cmp     ecx, 0FFFFFFFAh
0x1800a7910  cmovbe  ebx, eax
0x1800a7913  call    cs:__imp_GetCurrentThread
0x1800a7919  mov     rcx, rax; hThread
0x1800a791c  mov     edx, ebx; nPriority
0x1800a791e  call    cs:__imp_SetThreadPriority
0x1800a7924  mov     r8, [rbp+lpszPathName]; lpszPathName
0x1800a7928  lea     r9, [rbp+var_10]; struct _PRUNINGPOLICIES *
0x1800a792c  mov     edx, [rbp+EntryCount]; unsigned int
0x1800a792f  mov     rcx, [rbp+SiteNames]; unsigned __int16 **
0x1800a7933  call    ?DeleteOrphans@@YAJPEAPEAGKPEAGPEAU_PRUNINGPOLICIES@@@Z; DeleteOrphans(ushort * *,ulong,ushort *,_PRUNINGPOLICIES *)
0x1800a7938  mov     edx, 1E0h
0x1800a793d  lea     rcx, aPruninginterva; "PruningInterval"
0x1800a7944  call    GetSpoolerNumericPolicy
0x1800a7949  mov     edi, eax
0x1800a794b  mov     ebx, eax
0x1800a794d  cmp     eax, 3Ch ; '<'
0x1800a7950  jbe     short loc_1800A7988
0x1800a7952  mov     ecx, 36EE80h; dwMilliseconds
0x1800a7957  call    cs:__imp_Sleep
0x1800a795d  mov     edx, 1E0h
0x1800a7962  lea     rcx, aPruninginterva; "PruningInterval"
0x1800a7969  call    GetSpoolerNumericPolicy
0x1800a796e  cmp     eax, edi
0x1800a7970  jz      short loc_1800A7976
0x1800a7972  mov     edi, eax
0x1800a7974  mov     ebx, eax
0x1800a7976  cmp     ebx, 0FFFFFFFFh
0x1800a7979  jz      short loc_1800A7983
0x1800a797b  cmp     ebx, 3Ch ; '<'
0x1800a797e  jbe     short loc_1800A7988
0x1800a7980  add     ebx, 0FFFFFFC4h
0x1800a7983  cmp     ebx, 3Ch ; '<'
0x1800a7986  ja      short loc_1800A7952
0x1800a7988  imul    ecx, ebx, 0EA60h; dwMilliseconds
0x1800a798e  call    cs:__imp_Sleep
0x1800a7994  jmp     loc_1800A78AD
0x1800a7999  mov     rdi, [rbp+lpszPathName]
0x1800a799d  mov     rcx, [rbp+SiteNames]; Buffer
0x1800a79a1  test    rcx, rcx
0x1800a79a4  jz      short loc_1800A79AC
0x1800a79a6  call    cs:__imp_NetApiBufferFree
0x1800a79ac  mov     rcx, rdi
0x1800a79af  call    cs:__imp_DllFreeSplMem
0x1800a79b5  call    cs:__imp_CoUninitialize
0x1800a79bb  test    ebx, ebx
0x1800a79bd  jz      short loc_1800A79D2
0x1800a79bf  lea     rdx, aDspruningOpera; "DsPruning operations failed."
0x1800a79c6  lea     rcx, aDsprune; "DsPrune"
0x1800a79cd  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a79d2  xor     eax, eax
0x1800a79d4  mov     rbx, [rsp+30h+arg_18]
0x1800a79d9  add     rsp, 30h
0x1800a79dd  pop     r14
0x1800a79df  pop     rdi
0x1800a79e0  pop     rbp
0x1800a79e1  retn
```
