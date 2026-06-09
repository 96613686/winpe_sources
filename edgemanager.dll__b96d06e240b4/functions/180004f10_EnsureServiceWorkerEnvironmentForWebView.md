# EnsureServiceWorkerEnvironmentForWebView

- ea: `0x180004f10`
- end: `0x1800051af`
- name: `EnsureServiceWorkerEnvironmentForWebView`
- size: `671`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004f10`
- `0x180018b30`
- `0x1800192a8`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `iertutil!__imp_GetValue` at `0x180004f7c`
- `iertutil!__imp_GetValue` at `0x180004f7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004fc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004fc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000507b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000507b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005053`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005115`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005053`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000519a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000519a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fce`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004fa6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004fa6`
- `edgeIso!__imp_?IsoAddCreationDefinition@@YAJPEAU_IsoCreationDefinitionBase@@@Z` at `0x180005174`
- `edgeIso!__imp_?IsoAddCreationDefinition@@YAJPEAU_IsoCreationDefinitionBase@@@Z` at `0x180005174`

## string_xrefs

- `0x180005020`: `onecoreuap\inetcore\edgemanager\webview\serviceworker\serviceworker.cpp`
- `0x18000508b`: `onecoreuap\inetcore\edgemanager\webview\serviceworker\serviceworker.cpp`
- `0x1800050b0`: `onecoreuap\inetcore\edgemanager\webview\serviceworker\serviceworker.cpp`
- `0x1800050dc`: `onecoreuap\inetcore\edgemanager\webview\serviceworker\serviceworker.cpp`
- `0x180005124`: `onecoreuap\inetcore\edgemanager\webview\serviceworker\serviceworker.cpp`
- `0x180004f9a`: `WebRuntimeManager.dll`
- `0x180005074`: `EnsureServiceWorkerManagerComponent`

## pseudocode

```c
__int64 __fastcall EnsureServiceWorkerEnvironmentForWebView(int a1, int a2, __int64 a3)
{
  const char *v6; // r9
  int v7; // ebx
  int Value; // eax
  bool v9; // zf
  HMODULE LibraryW; // rax
  HMODULE v11; // r15
  HMODULE v12; // r14
  DWORD LastError; // ebx
  char v14; // al
  unsigned int v15; // r8d
  const char *v16; // r9
  FARPROC ProcAddress; // rax
  const char *v18; // r9
  int v19; // eax
  const char *v20; // r9
  unsigned int v21; // ebx
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Parameter; // [rsp+78h] [rbp+20h] BYREF
  int v26; // [rsp+7Ch] [rbp+24h]

  EnterCriticalSection(&s_runtimeSetupLock);
  if ( !byte_1800B6C26 )
  {
    if ( (NtCurrentPeb()->BitField & 0x10) == 0 )
      goto LABEL_11;
    v7 = 0;
    Parameter = 0;
    Value = GetValue(
              (__int64 *)SettingStore::IEVALUE_ExperimentalFeatures_DisableServiceWorkers,
              0,
              1,
              &Parameter,
              4,
              0,
              0);
    v9 = Value == 0;
    if ( Value >= 0 )
    {
      LOBYTE(v7) = Parameter != 0;
      v9 = Value == 0;
    }
    if ( !v9 || v7 )
      goto LABEL_11;
    LibraryW = LoadLibraryW(L"WebRuntimeManager.dll");
    v11 = hLibModule;
    v12 = LibraryW;
    if ( hLibModule )
    {
      LastError = GetLastError();
      FreeLibrary(v11);
      SetLastError(LastError);
    }
    hLibModule = v12;
    if ( v12 )
      v14 = 1;
    else
LABEL_11:
      v14 = 0;
    byte_1800B6C25 = v14;
    byte_1800B6C26 = 1;
  }
  if ( !byte_1800B6C25 )
    goto LABEL_36;
  if ( a1 )
  {
    if ( byte_1800B6C23 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\serviceworker\\serviceworker.cpp",
        v6);
    if ( !byte_1800B6C24 )
    {
      Parameter = a1;
      v26 = a2;
      if ( !InitOnceExecuteOnce(&stru_1800B6C28, (PINIT_ONCE_FN)InitializeIsoForOOPWebview, &Parameter, 0) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\serviceworker\\serviceworker.cpp",
          v20);
      byte_1800B6C24 = 1;
    }
  }
  else
  {
    if ( byte_1800B6C24 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\serviceworker\\serviceworker.cpp",
        v6);
    if ( !byte_1800B6C23 )
    {
      if ( !InitOnceExecuteOnce(&InitOnce, lambda_e825ad819ca9b0dbeb085ba99d51d0a8_::_lambda_invoker_cdecl_, 0, 0) )
        wil::details::in1diag3::FailFast_GetLastError(retaddr, (void *)0x87, v15, v16);
      ProcAddress = GetProcAddress(hLibModule, "EnsureServiceWorkerManagerComponent");
      if ( !ProcAddress )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\serviceworker\\serviceworker.cpp",
          v18);
      v19 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
      if ( v19 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\serviceworker\\serviceworker.cpp",
          (const char *)(unsigned int)v19,
          v23);
      byte_1800B6C23 = 1;
    }
  }
  if ( !byte_1800B6C22 && a3 )
  {
    dword_1800B7110 = 4;
    qword_1800B7118 = a3;
    dword_1800B7100 = 137;
    byte_1800B7104 = 1;
    IsoAddCreationDefinition((struct _IsoCreationDefinitionBase *)&dword_1800B7100);
    byte_1800B6C22 = 1;
  }
  if ( byte_1800B6C25 )
    v21 = 0;
  else
LABEL_36:
    v21 = -2147024846;
  LeaveCriticalSection(&s_runtimeSetupLock);
  return v21;
}

```

## disassembly

```asm
0x180004f10  mov     [rsp+arg_10], rbx
0x180004f15  push    rbp
0x180004f16  push    rsi
0x180004f17  push    rdi
0x180004f18  sub     rsp, 40h
0x180004f1c  mov     esi, ecx
0x180004f1e  mov     rdi, r8
0x180004f21  lea     rcx, ?s_runtimeSetupLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180004f28  mov     ebp, edx
0x180004f2a  call    cs:__imp_EnterCriticalSection
0x180004f30  cmp     cs:byte_1800B6C26, 0
0x180004f37  jnz     loc_180004FFD
0x180004f3d  mov     rax, gs:60h
0x180004f46  test    byte ptr [rax+3], 10h
0x180004f4a  jz      loc_180004FEE
0x180004f50  mov     rcx, cs:?IEVALUE_ExperimentalFeatures_DisableServiceWorkers@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ExperimentalFeatures_DisableServiceWorkers
0x180004f57  lea     r9, [rsp+58h+Parameter]
0x180004f5c  xor     ebx, ebx
0x180004f5e  xor     edx, edx
0x180004f60  mov     [rsp+58h+var_28], rbx
0x180004f65  mov     r8d, 1
0x180004f6b  mov     [rsp+58h+var_30], rbx
0x180004f70  mov     [rsp+58h+var_38], 4
0x180004f78  mov     [rsp+58h+Parameter], ebx
0x180004f7c  call    cs:__imp_GetValue
0x180004f82  test    eax, eax
0x180004f84  js      short loc_180004F8F
0x180004f86  cmp     [rsp+58h+Parameter], ebx
0x180004f8a  setnz   bl
0x180004f8d  test    eax, eax
0x180004f8f  jnz     short loc_180004FEE
0x180004f91  test    ebx, ebx
0x180004f93  jnz     short loc_180004FEE
0x180004f95  mov     [rsp+58h+arg_0], r14
0x180004f9a  lea     rcx, aWebruntimemana; "WebRuntimeManager.dll"
0x180004fa1  mov     [rsp+58h+arg_8], r15
0x180004fa6  call    cs:__imp_LoadLibraryW
0x180004fac  mov     r15, cs:hLibModule
0x180004fb3  mov     r14, rax
0x180004fb6  test    r15, r15
0x180004fb9  jz      short loc_180004FD4
0x180004fbb  call    cs:__imp_GetLastError
0x180004fc1  mov     rcx, r15; hLibModule
0x180004fc4  mov     ebx, eax
0x180004fc6  call    cs:__imp_FreeLibrary
0x180004fcc  mov     ecx, ebx; dwErrCode
0x180004fce  call    cs:__imp_SetLastError
0x180004fd4  mov     r15, [rsp+58h+arg_8]
0x180004fd9  test    r14, r14
0x180004fdc  mov     cs:hLibModule, r14
0x180004fe3  mov     r14, [rsp+58h+arg_0]
0x180004fe8  jz      short loc_180004FEE
0x180004fea  mov     al, 1
0x180004fec  jmp     short loc_180004FF0
0x180004fee  xor     al, al
0x180004ff0  mov     cs:byte_1800B6C25, al
0x180004ff6  mov     cs:byte_1800B6C26, 1
0x180004ffd  cmp     cs:byte_1800B6C25, 0
0x180005004  jz      loc_18000518E
0x18000500a  test    esi, esi
0x18000500c  jnz     loc_1800050CE
0x180005012  cmp     cs:byte_1800B6C24, sil
0x180005019  jz      short loc_180005032
0x18000501b  mov     rcx, [rsp+58h]; this
0x180005020  lea     r8, aOnecoreuapInet_47; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180005027  mov     edx, 12Eh; void *
0x18000502c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005032  cmp     cs:byte_1800B6C23, 0
0x180005039  jnz     loc_18000513D
0x18000503f  xor     r9d, r9d; Context
0x180005042  lea     rdx, _lambda_e825ad819ca9b0dbeb085ba99d51d0a8____lambda_invoker_cdecl_; InitFn
0x180005049  xor     r8d, r8d; Parameter
0x18000504c  lea     rcx, InitOnce; InitOnce
0x180005053  call    cs:__imp_InitOnceExecuteOnce
0x180005059  test    eax, eax
0x18000505b  jnz     short loc_18000506D
0x18000505d  mov     rcx, [rsp+58h]; this
0x180005062  mov     edx, 87h; void *
0x180005067  call    ?FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_GetLastError(void *,uint,char const *)
0x18000506d  mov     rcx, cs:hLibModule; hModule
0x180005074  lea     rdx, aEnsureservicew_0; "EnsureServiceWorkerManagerComponent"
0x18000507b  call    cs:__imp_GetProcAddress
0x180005081  test    rax, rax
0x180005084  jnz     short loc_18000509D
0x180005086  mov     rcx, [rsp+58h]; this
0x18000508b  lea     r8, aOnecoreuapInet_47; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180005092  mov     edx, 0F1h; void *
0x180005097  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000509d  mov     ecx, 2
0x1800050a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a7  test    eax, eax
0x1800050a9  jns     short loc_1800050C5
0x1800050ab  mov     rcx, [rsp+58h]; this
0x1800050b0  lea     r8, aOnecoreuapInet_47; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800050b7  mov     r9d, eax; char *
0x1800050ba  mov     edx, 0F2h; void *
0x1800050bf  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800050c5  mov     cs:byte_1800B6C23, 1
0x1800050cc  jmp     short loc_18000513D
0x1800050ce  cmp     cs:byte_1800B6C23, 0
0x1800050d5  jz      short loc_1800050EE
0x1800050d7  mov     rcx, [rsp+58h]; this
0x1800050dc  lea     r8, aOnecoreuapInet_47; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800050e3  mov     edx, 13Ah; void *
0x1800050e8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800050ee  cmp     cs:byte_1800B6C24, 0
0x1800050f5  jnz     short loc_18000513D
0x1800050f7  xor     r9d, r9d; Context
0x1800050fa  mov     [rsp+58h+Parameter], esi
0x1800050fe  lea     r8, [rsp+58h+Parameter]; Parameter
0x180005103  mov     [rsp+58h+arg_1C], ebp
0x180005107  lea     rdx, ?InitializeIsoForOOPWebview@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000510e  lea     rcx, stru_1800B6C28; InitOnce
0x180005115  call    cs:__imp_InitOnceExecuteOnce
0x18000511b  test    eax, eax
0x18000511d  jnz     short loc_180005136
0x18000511f  mov     rcx, [rsp+58h]; this
0x180005124  lea     r8, aOnecoreuapInet_47; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000512b  mov     edx, 0E5h; void *
0x180005130  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005136  mov     cs:byte_1800B6C24, 1
0x18000513d  cmp     cs:byte_1800B6C22, 0
0x180005144  jnz     short loc_180005181
0x180005146  test    rdi, rdi
0x180005149  jz      short loc_180005181
0x18000514b  lea     rcx, dword_1800B7100
0x180005152  mov     cs:dword_1800B7110, 4
0x18000515c  mov     cs:qword_1800B7118, rdi
0x180005163  mov     cs:dword_1800B7100, 89h
0x18000516d  mov     cs:byte_1800B7104, 1
0x180005174  call    cs:__imp_?IsoAddCreationDefinition@@YAJPEAU_IsoCreationDefinitionBase@@@Z; IsoAddCreationDefinition(_IsoCreationDefinitionBase *)
0x18000517a  mov     cs:byte_1800B6C22, 1
0x180005181  cmp     cs:byte_1800B6C25, 0
0x180005188  jz      short loc_18000518E
0x18000518a  xor     ebx, ebx
0x18000518c  jmp     short loc_180005193
0x18000518e  mov     ebx, 80070032h
0x180005193  lea     rcx, ?s_runtimeSetupLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x18000519a  call    cs:__imp_LeaveCriticalSection
0x1800051a0  mov     eax, ebx
0x1800051a2  mov     rbx, [rsp+58h+arg_10]
0x1800051a7  add     rsp, 40h
0x1800051ab  pop     rdi
0x1800051ac  pop     rsi
0x1800051ad  pop     rbp
0x1800051ae  retn
```
