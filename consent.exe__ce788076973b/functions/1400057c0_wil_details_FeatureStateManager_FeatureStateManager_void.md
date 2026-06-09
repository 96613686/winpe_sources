# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400057c0`
- end: `0x140005985`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `453`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14001e8d0`

## callees

- `0x1400057c0`
- `0x1400059fc`
- `0x140005a40`
- `0x14000fd34`
- `0x140017c68`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005904`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005869`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000591c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000593f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000591c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000593f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000592a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000594d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000592a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000594d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058bf`

## string_xrefs

- `0x1400058fd`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  struct _TP_TIMER *v4; // rsi
  void *v5; // rdi
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  void *v7; // rsi
  __int64 v8; // rdi
  void *v9; // rsi
  struct _TP_TIMER *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  void *v12; // rcx
  DWORD LastError; // edi
  DWORD v14; // edi
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v14 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(v14);
  }
  *((_QWORD *)this + 7) = 0;
  v5 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  v6 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v6 )
    wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
  v7 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v7);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = *((_QWORD *)this + 18);
  if ( v8 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v8);
    }
  }
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v10 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v10);
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v11 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
  v12 = (void *)*((_QWORD *)this + 2);
  if ( v12 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v12);
}

```

## disassembly

```asm
0x1400057c0  push    rbx
0x1400057c2  push    rbp
0x1400057c3  push    rsi
0x1400057c4  push    rdi
0x1400057c5  sub     rsp, 28h
0x1400057c9  mov     rbx, rcx
0x1400057cc  mov     byte ptr [rcx], 0
0x1400057cf  mov     rsi, [rcx+30h]
0x1400057d3  test    rsi, rsi
0x1400057d6  jnz     loc_1400058A2
0x1400057dc  xor     ebp, ebp
0x1400057de  mov     [rbx+30h], rbp
0x1400057e2  mov     rsi, [rbx+38h]
0x1400057e6  test    rsi, rsi
0x1400057e9  jnz     loc_1400058BF
0x1400057ef  mov     [rbx+38h], rbp
0x1400057f3  mov     rdi, [rbx+100h]
0x1400057fa  mov     [rbx+100h], rbp
0x140005801  test    rdi, rdi
0x140005804  jnz     loc_14000591C
0x14000580a  mov     rcx, [rbx+0E0h]; this
0x140005811  test    rcx, rcx
0x140005814  jnz     loc_140005935
0x14000581a  mov     rsi, [rbx+0D8h]
0x140005821  mov     [rbx+0D8h], rbp
0x140005828  test    rsi, rsi
0x14000582b  jnz     loc_14000593F
0x140005831  lea     rcx, [rbx+98h]; lpCriticalSection
0x140005838  call    cs:__imp_DeleteCriticalSection
0x14000583e  mov     rdi, [rbx+90h]
0x140005845  test    rdi, rdi
0x140005848  jnz     loc_1400058DC
0x14000584e  mov     rsi, [rbx+88h]
0x140005855  mov     [rbx+88h], rbp
0x14000585c  test    rsi, rsi
0x14000585f  jnz     loc_140005958
0x140005865  lea     rcx, [rbx+48h]; lpCriticalSection
0x140005869  call    cs:__imp_DeleteCriticalSection
0x14000586f  mov     rcx, [rbx+38h]; pti
0x140005873  test    rcx, rcx
0x140005876  jnz     loc_140005971
0x14000587c  mov     rcx, [rbx+30h]; pti
0x140005880  test    rcx, rcx
0x140005883  jnz     loc_14000597B
0x140005889  mov     rcx, [rbx+10h]; lpMem
0x14000588d  test    rcx, rcx
0x140005890  jnz     short loc_14000589B
0x140005892  add     rsp, 28h
0x140005896  pop     rdi
0x140005897  pop     rsi
0x140005898  pop     rbp
0x140005899  pop     rbx
0x14000589a  retn
0x14000589b  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400058a0  jmp     short loc_140005892
0x1400058a2  call    cs:__imp_GetLastError
0x1400058a8  mov     edi, eax
0x1400058aa  mov     rcx, rsi; pti
0x1400058ad  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400058b2  mov     ecx, edi; dwErrCode
0x1400058b4  call    cs:__imp_SetLastError
0x1400058ba  jmp     loc_1400057DC
0x1400058bf  call    cs:__imp_GetLastError
0x1400058c5  mov     edi, eax
0x1400058c7  mov     rcx, rsi; pti
0x1400058ca  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400058cf  mov     ecx, edi; dwErrCode
0x1400058d1  call    cs:__imp_SetLastError
0x1400058d7  jmp     loc_1400057EF
0x1400058dc  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1400058e3  test    rax, rax
0x1400058e6  jz      short loc_1400058F5
0x1400058e8  mov     rcx, rdi
0x1400058eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058f0  jmp     loc_14000584E
0x1400058f5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400058fa  mov     rcx, rax; hModule
0x1400058fd  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x140005904  call    cs:__imp_GetProcAddress
0x14000590a  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140005911  test    rax, rax
0x140005914  jz      loc_14000584E
0x14000591a  jmp     short loc_1400058E8
0x14000591c  call    cs:__imp_GetProcessHeap
0x140005922  mov     rcx, rax; hHeap
0x140005925  mov     r8, rdi; lpMem
0x140005928  xor     edx, edx; dwFlags
0x14000592a  call    cs:__imp_HeapFree
0x140005930  jmp     loc_14000580A
0x140005935  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000593a  jmp     loc_14000581A
0x14000593f  call    cs:__imp_GetProcessHeap
0x140005945  mov     rcx, rax; hHeap
0x140005948  mov     r8, rsi; lpMem
0x14000594b  xor     edx, edx; dwFlags
0x14000594d  call    cs:__imp_HeapFree
0x140005953  jmp     loc_140005831
0x140005958  call    cs:__imp_GetProcessHeap
0x14000595e  mov     rcx, rax; hHeap
0x140005961  mov     r8, rsi; lpMem
0x140005964  xor     edx, edx; dwFlags
0x140005966  call    cs:__imp_HeapFree
0x14000596c  jmp     loc_140005865
0x140005971  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140005976  jmp     loc_14000587C
0x14000597b  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140005980  jmp     loc_140005889
```
