# RetrievalPreFetchJobThreadProc(void *)

- ea: `0x18000f950`
- end: `0x18000fb32`
- name: `?RetrievalPreFetchJobThreadProc@@YAKPEAX@Z`
- size: `482`
- prototype: `void __fastcall __noreturn(struct _RTL_CRITICAL_SECTION *Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004530`
- `0x1800068f0`
- `0x1800089a0`
- `0x180008a10`
- `0x18000b720`
- `0x18000b9b0`
- `0x18000baa8`
- `0x18000f924`
- `0x18000f950`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18000fb2b`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18000fb2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000fad2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000fad2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fa35`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fa35`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f9ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f9ad`

## pseudocode

```c
void __fastcall __noreturn RetrievalPreFetchJobThreadProc(struct _RTL_CRITICAL_SECTION *Parameter)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  struct _CUCS_PRE_FETCH_JOB_ENTRY *v4; // rbx
  int v5; // ebp
  int v6; // esi
  HMODULE v7; // rbx
  signed __int32 v8[8]; // [rsp+0h] [rbp-48h] BYREF
  int v9; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  if ( !(unsigned int)RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(Parameter) )
  {
    v4 = (struct _CUCS_PRE_FETCH_JOB_ENTRY *)pRetrievalPreFetchJobHead;
    v5 = 0;
    v6 = 0;
    if ( !pRetrievalPreFetchJobHead )
    {
LABEL_27:
      v7 = *(HMODULE *)&Parameter[1].LockCount;
      *(_QWORD *)&Parameter[1].LockCount = 0;
      HIDWORD(Parameter[1].DebugInfo) = 0;
      RetrievalPreFetchJobThreadProcUnlock((struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)Parameter);
LABEL_23:
      if ( v7 )
        FreeLibraryAndExitThread(v7, 0);
      ExitThread(0);
    }
    while ( 1 )
    {
      RemoveFromLinkList2(v3, v2, v4);
      *((_DWORD *)v4 + 29) = 3;
      RetrievalPreFetchJobThreadProcUnlock((struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)Parameter);
      if ( !v5 )
      {
        if ( CoInitializeEx(0, 0) >= 0 )
        {
          ppv = 0;
          if ( CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkCostManager, &ppv) >= 0 )
          {
            v9 = 0;
            if ( (*(int (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, &v9, 0) >= 0
              && (_WORD)v9
              && (v9 & 1) == 0 )
            {
              v6 = 1;
            }
          }
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          CoUninitialize();
        }
        v5 = 1;
        g_fLastHasNetworkCost = v6;
        _InterlockedOr(v8, 0);
      }
      if ( v6 )
      {
        *((_DWORD *)v4 + 30) = 5035;
      }
      else if ( (unsigned int)IsPreFetchDisabledForAutoUpdateUrl(*((unsigned int *)v4 + 35), *((_QWORD *)v4 + 9)) )
      {
        *((_DWORD *)v4 + 30) = 50;
      }
      else
      {
        ProcessRetrievalPreFetchJob(v4);
      }
      if ( (unsigned int)RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(Parameter) )
        break;
      if ( *((_QWORD *)v4 + 6) )
      {
        *((_DWORD *)v4 + 29) = 4;
        AddToBeRunJobEx(v4, 3, 0);
      }
      else
      {
        RetrievalPreFetchJobThreadProcUnlock((struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)Parameter);
        FreePreFetchJob(v4);
        if ( (unsigned int)RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(Parameter) )
          goto LABEL_22;
      }
      v4 = (struct _CUCS_PRE_FETCH_JOB_ENTRY *)pRetrievalPreFetchJobHead;
      if ( !pRetrievalPreFetchJobHead )
        goto LABEL_27;
    }
    FreePreFetchJob(v4);
  }
LABEL_22:
  v7 = *(HMODULE *)&Parameter[1].LockCount;
  *(_QWORD *)&Parameter[1].LockCount = 0;
  HIDWORD(Parameter[1].DebugInfo) = 0;
  FreeRetrievalPreFetchJobInfo(Parameter);
  goto LABEL_23;
}

```

## disassembly

```asm
0x18000f950  mov     [rsp+arg_10], rbx
0x18000f955  mov     [rsp+arg_18], rbp
0x18000f95a  push    rsi
0x18000f95b  push    rdi
0x18000f95c  push    r15
0x18000f95e  sub     rsp, 30h
0x18000f962  mov     rdi, rcx
0x18000f965  call    ?RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop@@YAHPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000f96a  test    eax, eax
0x18000f96c  jnz     loc_18000FAAD
0x18000f972  mov     rbx, cs:?pRetrievalPreFetchJobHead@@3PEAU_CUCS_PRE_FETCH_JOB_ENTRY@@EA; _CUCS_PRE_FETCH_JOB_ENTRY * pRetrievalPreFetchJobHead
0x18000f979  xor     ebp, ebp
0x18000f97b  xor     esi, esi
0x18000f97d  test    rbx, rbx
0x18000f980  jz      loc_18000FB02
0x18000f986  lea     r15d, [rax+1]
0x18000f98a  mov     r8, rbx
0x18000f98d  call    RemoveFromLinkList2
0x18000f992  mov     rcx, rdi; struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *
0x18000f995  mov     dword ptr [rbx+74h], 3
0x18000f99c  call    ?RetrievalPreFetchJobThreadProcUnlock@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcUnlock(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000f9a1  test    ebp, ebp
0x18000f9a3  jnz     loc_18000FA49
0x18000f9a9  xor     edx, edx; dwCoInit
0x18000f9ab  xor     ecx, ecx; pvReserved
0x18000f9ad  call    cs:__imp_CoInitializeEx
0x18000f9b3  test    eax, eax
0x18000f9b5  js      loc_18000FA3B
0x18000f9bb  lea     rax, [rsp+48h+arg_8]
0x18000f9c0  mov     [rsp+48h+arg_8], 0
0x18000f9c9  lea     r9, IID_INetworkCostManager; riid
0x18000f9d0  mov     [rsp+48h+ppv], rax; ppv
0x18000f9d5  xor     edx, edx; pUnkOuter
0x18000f9d7  lea     r8d, [rbp+17h]; dwClsContext
0x18000f9db  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000f9e2  call    cs:__imp_CoCreateInstance
0x18000f9e8  test    eax, eax
0x18000f9ea  js      short loc_18000FA1F
0x18000f9ec  mov     rcx, [rsp+48h+arg_8]
0x18000f9f1  lea     rdx, [rsp+48h+arg_0]
0x18000f9f6  mov     [rsp+48h+arg_0], ebp
0x18000f9fa  xor     r8d, r8d
0x18000f9fd  mov     rax, [rcx]
0x18000fa00  mov     rax, [rax+18h]
0x18000fa04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa09  test    eax, eax
0x18000fa0b  js      short loc_18000FA1F
0x18000fa0d  movzx   eax, word ptr [rsp+48h+arg_0]
0x18000fa12  test    eax, eax
0x18000fa14  jz      short loc_18000FA1F
0x18000fa16  test    byte ptr [rsp+48h+arg_0], r15b
0x18000fa1b  cmovz   esi, r15d
0x18000fa1f  mov     rcx, [rsp+48h+arg_8]
0x18000fa24  test    rcx, rcx
0x18000fa27  jz      short loc_18000FA35
0x18000fa29  mov     rax, [rcx]
0x18000fa2c  mov     rax, [rax+10h]
0x18000fa30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa35  call    cs:__imp_CoUninitialize
0x18000fa3b  mov     ebp, r15d
0x18000fa3e  mov     cs:?g_fLastHasNetworkCost@@3HA, esi; int g_fLastHasNetworkCost
0x18000fa44  lock or [rsp+48h+var_48], 0
0x18000fa49  test    esi, esi
0x18000fa4b  jz      short loc_18000FA56
0x18000fa4d  mov     dword ptr [rbx+78h], 13ABh
0x18000fa54  jmp     short loc_18000FA7A
0x18000fa56  mov     rdx, [rbx+48h]
0x18000fa5a  mov     ecx, [rbx+8Ch]
0x18000fa60  call    IsPreFetchDisabledForAutoUpdateUrl
0x18000fa65  test    eax, eax
0x18000fa67  jz      short loc_18000FA72
0x18000fa69  mov     dword ptr [rbx+78h], 32h ; '2'
0x18000fa70  jmp     short loc_18000FA7A
0x18000fa72  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x18000fa75  call    ?ProcessRetrievalPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; ProcessRetrievalPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x18000fa7a  mov     rcx, rdi; lpCriticalSection
0x18000fa7d  call    ?RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop@@YAHPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000fa82  test    eax, eax
0x18000fa84  jnz     loc_18000FB1F
0x18000fa8a  cmp     qword ptr [rbx+30h], 0
0x18000fa8f  jnz     short loc_18000FAD9
0x18000fa91  mov     rcx, rdi; struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *
0x18000fa94  call    ?RetrievalPreFetchJobThreadProcUnlock@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcUnlock(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000fa99  mov     rcx, rbx; hMem
0x18000fa9c  call    FreePreFetchJob
0x18000faa1  mov     rcx, rdi; lpCriticalSection
0x18000faa4  call    ?RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop@@YAHPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000faa9  test    eax, eax
0x18000faab  jz      short loc_18000FAF2
0x18000faad  mov     rbx, [rdi+30h]
0x18000fab1  mov     rcx, rdi; hMem
0x18000fab4  mov     qword ptr [rdi+30h], 0
0x18000fabc  mov     dword ptr [rdi+2Ch], 0
0x18000fac3  call    ?FreeRetrievalPreFetchJobInfo@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; FreeRetrievalPreFetchJobInfo(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000fac8  test    rbx, rbx
0x18000facb  jz      short loc_18000FB29
0x18000facd  xor     edx, edx; dwExitCode
0x18000facf  mov     rcx, rbx; hLibModule
0x18000fad2  call    cs:__imp_FreeLibraryAndExitThread
0x18000fad8  int     3; Trap to Debugger
0x18000fad9  xor     r9d, r9d
0x18000fadc  mov     dword ptr [rbx+74h], 4
0x18000fae3  xor     r8d, r8d
0x18000fae6  mov     rcx, rbx
0x18000fae9  lea     edx, [r9+3]
0x18000faed  call    AddToBeRunJobEx
0x18000faf2  mov     rbx, cs:?pRetrievalPreFetchJobHead@@3PEAU_CUCS_PRE_FETCH_JOB_ENTRY@@EA; _CUCS_PRE_FETCH_JOB_ENTRY * pRetrievalPreFetchJobHead
0x18000faf9  test    rbx, rbx
0x18000fafc  jnz     loc_18000F98A
0x18000fb02  mov     rbx, [rdi+30h]
0x18000fb06  mov     rcx, rdi; struct _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *
0x18000fb09  mov     qword ptr [rdi+30h], 0
0x18000fb11  mov     dword ptr [rdi+2Ch], 0
0x18000fb18  call    ?RetrievalPreFetchJobThreadProcUnlock@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; RetrievalPreFetchJobThreadProcUnlock(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000fb1d  jmp     short loc_18000FAC8
0x18000fb1f  mov     rcx, rbx; hMem
0x18000fb22  call    FreePreFetchJob
0x18000fb27  jmp     short loc_18000FAAD
0x18000fb29  xor     ecx, ecx; dwExitCode
0x18000fb2b  call    cs:__imp_ExitThread
```
