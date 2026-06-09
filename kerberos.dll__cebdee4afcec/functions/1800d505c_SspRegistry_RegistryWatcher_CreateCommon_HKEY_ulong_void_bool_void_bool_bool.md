# SspRegistry::RegistryWatcher::CreateCommon(HKEY__ *,ulong (*)(void *),bool,void *,bool,bool)

- ea: `0x1800d505c`
- end: `0x1800d5322`
- name: `?CreateCommon@RegistryWatcher@SspRegistry@@CAPEAV12@PEAUHKEY__@@P6AKPEAX@Z_N133@Z`
- size: `710`
- prototype: `struct SspRegistry::RegistryWatcher *__usercall@<rax>(HKEY hSourceHandle@<rcx>, unsigned int (*)(void *)@<rdx>, bool@<r8b>, void *@<r9>, bool, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800802c0`
- `0x1800941c8`
- `0x18009487c`

## callees

- `0x18007408c`
- `0x1800d4f9c`
- `0x1800d505c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d525c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d525c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d509b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d509b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d5222`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d5222`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d52ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d5306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d52ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d5306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d50ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d50ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d50fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d5105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d50fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d5105`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800d512a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800d512a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d5150`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d5150`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800d5205`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800d5205`
- `ntdll!NtClose` at `0x1800d527d`
- `ntdll!NtClose` at `0x1800d52a0`
- `ntdll!NtClose` at `0x1800d52d6`
- `ntdll!NtClose` at `0x1800d52f9`
- `ntdll!NtClose` at `0x1800d527d`
- `ntdll!NtClose` at `0x1800d52a0`
- `ntdll!NtClose` at `0x1800d52d6`
- `ntdll!NtClose` at `0x1800d52f9`
- `USERENV!RegisterGPNotification` at `0x1800d50ec`
- `USERENV!RegisterGPNotification` at `0x1800d50ec`
- `USERENV!UnregisterGPNotification` at `0x1800d5296`
- `USERENV!UnregisterGPNotification` at `0x1800d52ef`
- `USERENV!UnregisterGPNotification` at `0x1800d5296`
- `USERENV!UnregisterGPNotification` at `0x1800d52ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SspRegistry::RegistryWatcher *__fastcall SspRegistry::RegistryWatcher::CreateCommon(
        HKEY hSourceHandle,
        void (__fastcall *a2)(void *),
        unsigned __int8 a3,
        void *a4,
        bool a5,
        bool a6)
{
  int v7; // esi
  HANDLE EventW; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  HANDLE v15; // rax
  HANDLE v16; // rax
  _QWORD *v17; // rax
  HANDLE v18; // rcx
  HANDLE v20; // rcx
  char v21; // [rsp+40h] [rbp-49h] BYREF
  DWORD dwErrCode; // [rsp+44h] [rbp-45h] BYREF
  HANDLE hEvent; // [rsp+48h] [rbp-41h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v25[5]; // [rsp+58h] [rbp-31h] BYREF
  char v26; // [rsp+80h] [rbp-9h]

  v7 = a3;
  TargetHandle = 0;
  v21 = 0;
  dwErrCode = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  hEvent = EventW;
  v25[1] = &TargetHandle;
  v25[2] = &hEvent;
  v25[3] = &v21;
  v25[4] = &dwErrCode;
  v26 = 1;
  if ( !EventW )
    goto LABEL_2;
  if ( a5 )
  {
    if ( RegisterGPNotification(EventW, a6) )
    {
      v21 = 1;
      goto LABEL_8;
    }
LABEL_2:
    dwErrCode = GetLastError();
LABEL_24:
    if ( TargetHandle )
    {
      NtClose(TargetHandle);
      TargetHandle = 0;
    }
    v20 = hEvent;
    if ( hEvent )
    {
      if ( v21 )
      {
        UnregisterGPNotification(hEvent);
        v20 = hEvent;
      }
      NtClose(v20);
      hEvent = 0;
    }
    SetLastError(dwErrCode);
    return 0;
  }
  CurrentProcess = GetCurrentProcess();
  v12 = GetCurrentProcess();
  if ( !DuplicateHandle(v12, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    goto LABEL_2;
  dwErrCode = RegNotifyChangeKeyValue((HKEY)TargetHandle, v7, v7 | 0x10000004, hEvent, 1);
  if ( dwErrCode )
    goto LABEL_24;
LABEL_8:
  a2(a4);
  v13 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  v14 = v13;
  if ( !v13 )
  {
    v25[0] = 0;
    dwErrCode = 8;
    goto LABEL_23;
  }
  *v13 = v13;
  v13[1] = v13;
  *((_BYTE *)v13 + 16) = 0;
  v13[3] = 0;
  *((_BYTE *)v13 + 32) = 0;
  v13[5] = 0;
  v13[6] = 0;
  v13[7] = 0;
  v13[8] = 0;
  v13[9] = 0;
  v25[0] = v13;
  *((_BYTE *)v13 + 16) = a5;
  v13[7] = a2;
  v13[8] = a4;
  v15 = hEvent;
  hEvent = 0;
  v14[5] = v15;
  if ( !a5 )
  {
    v16 = TargetHandle;
    TargetHandle = 0;
    v14[3] = v16;
    *((_BYTE *)v14 + 32) = v7;
  }
  if ( !RegisterWaitForSingleObject(
          (PHANDLE)v14 + 6,
          (HANDLE)v14[5],
          SspRegistry::RegistryWatcher::WaitCallback,
          v14,
          0xFFFFFFFF,
          8u) )
  {
    dwErrCode = 554;
LABEL_23:
    utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(v25);
    goto LABEL_24;
  }
  AcquireSRWLockExclusive(&stru_180146850);
  v17 = Context;
  if ( *((PVOID **)Context + 1) != &Context )
    __fastfail(3u);
  *v14 = Context;
  v14[1] = &Context;
  v17[1] = v14;
  Context = v14;
  ReleaseSRWLockExclusive(&stru_180146850);
  dwErrCode = 0;
  v25[0] = 0;
  utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(v25);
  if ( TargetHandle )
  {
    NtClose(TargetHandle);
    TargetHandle = 0;
  }
  v18 = hEvent;
  if ( hEvent )
  {
    if ( v21 )
    {
      UnregisterGPNotification(hEvent);
      v18 = hEvent;
    }
    NtClose(v18);
    hEvent = 0;
  }
  SetLastError(dwErrCode);
  return (struct SspRegistry::RegistryWatcher *)v14;
}

```

## disassembly

```asm
0x1800d505c  push    rbp
0x1800d505e  push    rbx
0x1800d505f  push    rsi
0x1800d5060  push    rdi
0x1800d5061  push    r12
0x1800d5063  push    r13
0x1800d5065  push    r14
0x1800d5067  push    r15
0x1800d5069  lea     rbp, [rsp-0Fh]
0x1800d506e  sub     rsp, 98h
0x1800d5075  mov     r14, r9
0x1800d5078  movzx   esi, r8b
0x1800d507c  mov     r15, rdx
0x1800d507f  mov     r12, rcx
0x1800d5082  xor     r13d, r13d
0x1800d5085  mov     [rbp+47h+TargetHandle], r13
0x1800d5089  mov     [rbp+47h+var_90], r13b
0x1800d508d  mov     [rbp+47h+dwErrCode], r13d
0x1800d5091  xor     r9d, r9d; lpName
0x1800d5094  xor     r8d, r8d; bInitialState
0x1800d5097  xor     edx, edx; bManualReset
0x1800d5099  xor     ecx, ecx; lpEventAttributes
0x1800d509b  call    cs:__imp_CreateEventW
0x1800d50a1  mov     [rbp+47h+hEvent], rax
0x1800d50a5  lea     rcx, [rbp+47h+TargetHandle]
0x1800d50a9  mov     [rbp+47h+var_70], rcx
0x1800d50ad  lea     rcx, [rbp+47h+hEvent]
0x1800d50b1  mov     [rbp+47h+var_68], rcx
0x1800d50b5  lea     rcx, [rbp+47h+var_90]
0x1800d50b9  mov     [rbp+47h+var_60], rcx
0x1800d50bd  lea     rcx, [rbp+47h+dwErrCode]
0x1800d50c1  mov     [rbp+47h+var_58], rcx
0x1800d50c5  mov     [rbp+47h+var_50], 1
0x1800d50c9  test    rax, rax
0x1800d50cc  jnz     short loc_1800D50DC
0x1800d50ce  call    cs:__imp_GetLastError
0x1800d50d4  mov     [rbp+47h+dwErrCode], eax
0x1800d50d7  jmp     loc_1800D52CD
0x1800d50dc  mov     dil, [rbp+47h+arg_20]
0x1800d50e0  test    dil, dil
0x1800d50e3  jz      short loc_1800D50FC
0x1800d50e5  movzx   edx, [rbp+47h+arg_28]; bMachine
0x1800d50e9  mov     rcx, rax; hEvent
0x1800d50ec  call    cs:__imp_RegisterGPNotification
0x1800d50f2  test    eax, eax
0x1800d50f4  jz      short loc_1800D50CE
0x1800d50f6  mov     [rbp+47h+var_90], 1
0x1800d50fa  jmp     short loc_1800D5161
0x1800d50fc  call    cs:__imp_GetCurrentProcess
0x1800d5102  mov     rbx, rax
0x1800d5105  call    cs:__imp_GetCurrentProcess
0x1800d510b  mov     [rsp+0D0h+dwOptions], 2; dwOptions
0x1800d5113  mov     [rsp+0D0h+bInheritHandle], r13d; bInheritHandle
0x1800d5118  mov     [rsp+0D0h+dwDesiredAccess], r13d; dwDesiredAccess
0x1800d511d  lea     r9, [rbp+47h+TargetHandle]; lpTargetHandle
0x1800d5121  mov     r8, rbx; hTargetProcessHandle
0x1800d5124  mov     rdx, r12; hSourceHandle
0x1800d5127  mov     rcx, rax; hSourceProcessHandle
0x1800d512a  call    cs:__imp_DuplicateHandle
0x1800d5130  test    eax, eax
0x1800d5132  jz      short loc_1800D50CE
0x1800d5134  mov     edx, esi; bWatchSubtree
0x1800d5136  mov     r8d, esi
0x1800d5139  or      r8d, 10000004h; dwNotifyFilter
0x1800d5140  mov     [rsp+0D0h+dwDesiredAccess], 1; fAsynchronous
0x1800d5148  mov     r9, [rbp+47h+hEvent]; hEvent
0x1800d514c  mov     rcx, [rbp+47h+TargetHandle]; hKey
0x1800d5150  call    cs:__imp_RegNotifyChangeKeyValue
0x1800d5156  mov     [rbp+47h+dwErrCode], eax
0x1800d5159  test    eax, eax
0x1800d515b  jnz     loc_1800D52CD
0x1800d5161  mov     rcx, r14
0x1800d5164  mov     rax, r15
0x1800d5167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d516c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d5173  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800d5178  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d517d  mov     rbx, rax
0x1800d5180  test    rax, rax
0x1800d5183  jz      loc_1800D52B8
0x1800d5189  mov     [rax], rax
0x1800d518c  mov     [rax+8], rax
0x1800d5190  mov     [rax+10h], r13b
0x1800d5194  mov     [rax+18h], r13
0x1800d5198  mov     [rax+20h], r13b
0x1800d519c  mov     [rax+28h], r13
0x1800d51a0  mov     [rax+30h], r13
0x1800d51a4  mov     [rax+38h], r13
0x1800d51a8  mov     [rax+40h], r13
0x1800d51ac  xor     eax, eax
0x1800d51ae  mov     [rbx+48h], rax
0x1800d51b2  mov     [rbp+47h+var_78], rbx
0x1800d51b6  mov     [rbx+10h], dil
0x1800d51ba  mov     [rbx+38h], r15
0x1800d51be  mov     [rbx+40h], r14
0x1800d51c2  mov     rax, [rbp+47h+hEvent]
0x1800d51c6  mov     [rbp+47h+hEvent], r13
0x1800d51ca  mov     [rbx+28h], rax
0x1800d51ce  test    dil, dil
0x1800d51d1  jnz     short loc_1800D51E3
0x1800d51d3  mov     rax, [rbp+47h+TargetHandle]
0x1800d51d7  mov     [rbp+47h+TargetHandle], r13
0x1800d51db  mov     [rbx+18h], rax
0x1800d51df  mov     [rbx+20h], sil
0x1800d51e3  lea     rcx, [rbx+30h]; phNewWaitObject
0x1800d51e7  mov     [rsp+0D0h+bInheritHandle], 8; dwFlags
0x1800d51ef  mov     [rsp+0D0h+dwDesiredAccess], 0FFFFFFFFh; dwMilliseconds
0x1800d51f7  mov     r9, rbx; Context
0x1800d51fa  lea     r8, ?WaitCallback@RegistryWatcher@SspRegistry@@CAXPEAXE@Z; Callback
0x1800d5201  mov     rdx, [rbx+28h]; hObject
0x1800d5205  call    cs:__imp_RegisterWaitForSingleObject
0x1800d520b  test    eax, eax
0x1800d520d  jnz     short loc_1800D521B
0x1800d520f  mov     [rbp+47h+dwErrCode], 22Ah
0x1800d5216  jmp     loc_1800D52C3
0x1800d521b  lea     rcx, stru_180146850; SRWLock
0x1800d5222  call    cs:__imp_AcquireSRWLockExclusive
0x1800d5228  mov     rax, cs:Context
0x1800d522f  lea     rcx, Context
0x1800d5236  cmp     [rax+8], rcx
0x1800d523a  jz      short loc_1800D5243
0x1800d523c  mov     ecx, 3
0x1800d5241  int     29h; Win8: RtlFailFast(ecx)
0x1800d5243  mov     [rbx], rax
0x1800d5246  mov     [rbx+8], rcx
0x1800d524a  mov     [rax+8], rbx
0x1800d524e  mov     cs:Context, rbx
0x1800d5255  lea     rcx, stru_180146850; SRWLock
0x1800d525c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d5262  mov     [rbp+47h+dwErrCode], r13d
0x1800d5266  mov     [rbp+47h+var_78], r13
0x1800d526a  lea     rcx, [rbp+47h+var_78]
0x1800d526e  call    ??1?$unique_ptr@VRegistryWatcher@SspRegistry@@U?$default_delete@VRegistryWatcher@SspRegistry@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(void)
0x1800d5273  nop
0x1800d5274  mov     rcx, [rbp+47h+TargetHandle]; Handle
0x1800d5278  test    rcx, rcx
0x1800d527b  jz      short loc_1800D5287
0x1800d527d  call    cs:__imp_NtClose
0x1800d5283  mov     [rbp+47h+TargetHandle], r13
0x1800d5287  mov     rcx, [rbp+47h+hEvent]; hEvent
0x1800d528b  test    rcx, rcx
0x1800d528e  jz      short loc_1800D52AA
0x1800d5290  cmp     [rbp+47h+var_90], r13b
0x1800d5294  jz      short loc_1800D52A0
0x1800d5296  call    cs:__imp_UnregisterGPNotification
0x1800d529c  mov     rcx, [rbp+47h+hEvent]; Handle
0x1800d52a0  call    cs:__imp_NtClose
0x1800d52a6  mov     [rbp+47h+hEvent], r13
0x1800d52aa  mov     ecx, [rbp+47h+dwErrCode]; dwErrCode
0x1800d52ad  call    cs:__imp_SetLastError
0x1800d52b3  mov     rax, rbx
0x1800d52b6  jmp     short loc_1800D530E
0x1800d52b8  mov     [rbp+47h+var_78], r13
0x1800d52bc  mov     [rbp+47h+dwErrCode], 8
0x1800d52c3  lea     rcx, [rbp+47h+var_78]
0x1800d52c7  call    ??1?$unique_ptr@VRegistryWatcher@SspRegistry@@U?$default_delete@VRegistryWatcher@SspRegistry@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(void)
0x1800d52cc  nop
0x1800d52cd  mov     rcx, [rbp+47h+TargetHandle]; Handle
0x1800d52d1  test    rcx, rcx
0x1800d52d4  jz      short loc_1800D52E0
0x1800d52d6  call    cs:__imp_NtClose
0x1800d52dc  mov     [rbp+47h+TargetHandle], r13
0x1800d52e0  mov     rcx, [rbp+47h+hEvent]; hEvent
0x1800d52e4  test    rcx, rcx
0x1800d52e7  jz      short loc_1800D5303
0x1800d52e9  cmp     [rbp+47h+var_90], r13b
0x1800d52ed  jz      short loc_1800D52F9
0x1800d52ef  call    cs:__imp_UnregisterGPNotification
0x1800d52f5  mov     rcx, [rbp+47h+hEvent]; Handle
0x1800d52f9  call    cs:__imp_NtClose
0x1800d52ff  mov     [rbp+47h+hEvent], r13
0x1800d5303  mov     ecx, [rbp+47h+dwErrCode]; dwErrCode
0x1800d5306  call    cs:__imp_SetLastError
0x1800d530c  xor     eax, eax
0x1800d530e  add     rsp, 98h
0x1800d5315  pop     r15
0x1800d5317  pop     r14
0x1800d5319  pop     r13
0x1800d531b  pop     r12
0x1800d531d  pop     rdi
0x1800d531e  pop     rsi
0x1800d531f  pop     rbx
0x1800d5320  pop     rbp
0x1800d5321  retn
```
