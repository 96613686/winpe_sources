# SspRegistry::RegistryWatcher::CreateCommon(HKEY__ *,ulong (*)(void *),bool,void *,bool,bool)

- ea: `0x18005a58c`
- end: `0x18005a88f`
- name: `?CreateCommon@RegistryWatcher@SspRegistry@@CAPEAV12@PEAUHKEY__@@P6AKPEAX@Z_N133@Z`
- size: `771`
- prototype: `struct SspRegistry::RegistryWatcher *__fastcall(HKEY, unsigned int (*)(void *), bool, void *, DWORD dwErrCode, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049da8`

## callees

- `0x18002ffec`
- `0x180047f50`
- `0x18005a4cc`
- `0x18005a58c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a824`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a87e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a824`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a653`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a5c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a5c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a79a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a79a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7d4`
- `USERENV!UnregisterGPNotification` at `0x18005a61e`
- `USERENV!UnregisterGPNotification` at `0x18005a67e`
- `USERENV!UnregisterGPNotification` at `0x18005a770`
- `USERENV!UnregisterGPNotification` at `0x18005a80d`
- `USERENV!UnregisterGPNotification` at `0x18005a867`
- `USERENV!UnregisterGPNotification` at `0x18005a61e`
- `USERENV!UnregisterGPNotification` at `0x18005a67e`
- `USERENV!UnregisterGPNotification` at `0x18005a770`
- `USERENV!UnregisterGPNotification` at `0x18005a80d`
- `USERENV!UnregisterGPNotification` at `0x18005a867`
- `USERENV!RegisterGPNotification` at `0x18005a649`
- `USERENV!RegisterGPNotification` at `0x18005a649`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005a733`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005a733`
- `ntdll!NtClose` at `0x18005a605`
- `ntdll!NtClose` at `0x18005a628`
- `ntdll!NtClose` at `0x18005a665`
- `ntdll!NtClose` at `0x18005a688`
- `ntdll!NtClose` at `0x18005a757`
- `ntdll!NtClose` at `0x18005a77a`
- `ntdll!NtClose` at `0x18005a7f4`
- `ntdll!NtClose` at `0x18005a817`
- `ntdll!NtClose` at `0x18005a84e`
- `ntdll!NtClose` at `0x18005a871`
- `ntdll!NtClose` at `0x18005a605`
- `ntdll!NtClose` at `0x18005a628`
- `ntdll!NtClose` at `0x18005a665`
- `ntdll!NtClose` at `0x18005a688`
- `ntdll!NtClose` at `0x18005a757`
- `ntdll!NtClose` at `0x18005a77a`
- `ntdll!NtClose` at `0x18005a7f4`
- `ntdll!NtClose` at `0x18005a817`
- `ntdll!NtClose` at `0x18005a84e`
- `ntdll!NtClose` at `0x18005a871`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct SspRegistry::RegistryWatcher *__fastcall SspRegistry::RegistryWatcher::CreateCommon(
        HKEY a1,
        unsigned int (*a2)(void *),
        __int64 a3,
        void *a4,
        DWORD dwErrCode)
{
  HANDLE EventW; // rax
  HANDLE v6; // rcx
  HANDLE v7; // rcx
  HKEY v8; // rax
  _QWORD *v9; // rbx
  HANDLE v10; // rdx
  HANDLE v11; // rcx
  _QWORD *v12; // rax
  HANDLE v13; // rcx
  HANDLE v15; // rcx
  HKEY v16; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h]
  char v18; // [rsp+90h] [rbp+30h]
  HANDLE hEvent; // [rsp+98h] [rbp+38h]

  hEvent = a4;
  v16 = a1;
  Handle = 0;
  v18 = 0;
  dwErrCode = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  hEvent = EventW;
  if ( !EventW )
  {
    dwErrCode = GetLastError();
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    v6 = hEvent;
    if ( hEvent )
    {
      if ( v18 )
      {
        UnregisterGPNotification(hEvent);
        v6 = hEvent;
      }
      NtClose(v6);
      hEvent = 0;
    }
LABEL_41:
    SetLastError(dwErrCode);
    return 0;
  }
  if ( !RegisterGPNotification(EventW, 1) )
  {
    dwErrCode = GetLastError();
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    v7 = hEvent;
    if ( hEvent )
    {
      if ( v18 )
      {
        UnregisterGPNotification(hEvent);
        v7 = hEvent;
      }
      NtClose(v7);
      hEvent = 0;
    }
    goto LABEL_41;
  }
  v18 = 1;
  NtlmQueryPolicyChangeCallback(0);
  v8 = (HKEY)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v16 = 0;
    dwErrCode = 8;
    utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(&v16);
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    v15 = hEvent;
    if ( hEvent )
    {
      if ( v18 )
      {
        UnregisterGPNotification(hEvent);
        v15 = hEvent;
      }
      NtClose(v15);
      hEvent = 0;
    }
    goto LABEL_41;
  }
  *(_QWORD *)v8 = v8;
  *((_QWORD *)v8 + 1) = v8;
  *((_BYTE *)v8 + 16) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *((_BYTE *)v8 + 32) = 0;
  *((_QWORD *)v8 + 5) = 0;
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_QWORD *)v8 + 8) = 0;
  *((_QWORD *)v8 + 9) = 0;
  v16 = v8;
  *((_BYTE *)v8 + 16) = 1;
  *((_QWORD *)v8 + 7) = NtlmQueryPolicyChangeCallback;
  *((_QWORD *)v8 + 8) = 0;
  v10 = hEvent;
  hEvent = 0;
  *((_QWORD *)v8 + 5) = v10;
  if ( !RegisterWaitForSingleObject(
          (PHANDLE)v8 + 6,
          v10,
          SspRegistry::RegistryWatcher::WaitCallback,
          v8,
          0xFFFFFFFF,
          8u) )
  {
    dwErrCode = 554;
    utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(&v16);
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    v11 = hEvent;
    if ( hEvent )
    {
      if ( v18 )
      {
        UnregisterGPNotification(hEvent);
        v11 = hEvent;
      }
      NtClose(v11);
      hEvent = 0;
    }
    goto LABEL_41;
  }
  AcquireSRWLockExclusive(&stru_18008A5F8);
  v12 = Context;
  if ( *((PVOID **)Context + 1) != &Context )
    __fastfail(3u);
  *v9 = Context;
  v9[1] = &Context;
  v12[1] = v9;
  Context = v9;
  ReleaseSRWLockExclusive(&stru_18008A5F8);
  dwErrCode = 0;
  v16 = 0;
  utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(&v16);
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  v13 = hEvent;
  if ( hEvent )
  {
    if ( v18 )
    {
      UnregisterGPNotification(hEvent);
      v13 = hEvent;
    }
    NtClose(v13);
    hEvent = 0;
  }
  SetLastError(dwErrCode);
  return (struct SspRegistry::RegistryWatcher *)v9;
}

```

## disassembly

```asm
0x18005a58c  mov     rax, rsp
0x18005a58f  mov     [rax+20h], r9
0x18005a593  mov     [rax+18h], r8b
0x18005a597  mov     [rax+10h], rdx
0x18005a59b  mov     [rax+8], rcx
0x18005a59f  push    rbp
0x18005a5a0  push    rbx
0x18005a5a1  push    rdi
0x18005a5a2  mov     rbp, rsp
0x18005a5a5  sub     rsp, 60h
0x18005a5a9  xor     edi, edi
0x18005a5ab  mov     [rbp+Handle], rdi
0x18005a5af  mov     [rbp+arg_10], dil
0x18005a5b3  mov     [rbp+dwErrCode], edi
0x18005a5b6  xor     r9d, r9d; lpName
0x18005a5b9  xor     r8d, r8d; bInitialState
0x18005a5bc  xor     edx, edx; bManualReset
0x18005a5be  xor     ecx, ecx; lpEventAttributes
0x18005a5c0  call    cs:__imp_CreateEventW
0x18005a5c6  mov     [rbp+hEvent], rax
0x18005a5ca  lea     rcx, [rbp+Handle]
0x18005a5ce  mov     [rbp+var_30], rcx
0x18005a5d2  lea     rcx, [rbp+hEvent]
0x18005a5d6  mov     [rbp+var_28], rcx
0x18005a5da  lea     rcx, [rbp+arg_10]
0x18005a5de  mov     [rbp+var_20], rcx
0x18005a5e2  lea     rcx, [rbp+dwErrCode]
0x18005a5e6  mov     [rbp+var_18], rcx
0x18005a5ea  mov     [rbp+var_10], 1
0x18005a5ee  test    rax, rax
0x18005a5f1  jnz     short loc_18005A641
0x18005a5f3  call    cs:__imp_GetLastError
0x18005a5f9  mov     [rbp+dwErrCode], eax
0x18005a5fc  mov     rcx, [rbp+Handle]; Handle
0x18005a600  test    rcx, rcx
0x18005a603  jz      short loc_18005A60F
0x18005a605  call    cs:__imp_NtClose
0x18005a60b  mov     [rbp+Handle], rdi
0x18005a60f  mov     rcx, [rbp+hEvent]; hEvent
0x18005a613  test    rcx, rcx
0x18005a616  jz      short loc_18005A632
0x18005a618  cmp     [rbp+arg_10], dil
0x18005a61c  jz      short loc_18005A628
0x18005a61e  call    cs:__imp_UnregisterGPNotification
0x18005a624  mov     rcx, [rbp+hEvent]; Handle
0x18005a628  call    cs:__imp_NtClose
0x18005a62e  mov     [rbp+hEvent], rdi
0x18005a632  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005a635  call    cs:__imp_SetLastError
0x18005a63b  nop
0x18005a63c  jmp     loc_18005A885
0x18005a641  mov     edx, 1; bMachine
0x18005a646  mov     rcx, rax; hEvent
0x18005a649  call    cs:__imp_RegisterGPNotification
0x18005a64f  test    eax, eax
0x18005a651  jnz     short loc_18005A6A1
0x18005a653  call    cs:__imp_GetLastError
0x18005a659  mov     [rbp+dwErrCode], eax
0x18005a65c  mov     rcx, [rbp+Handle]; Handle
0x18005a660  test    rcx, rcx
0x18005a663  jz      short loc_18005A66F
0x18005a665  call    cs:__imp_NtClose
0x18005a66b  mov     [rbp+Handle], rdi
0x18005a66f  mov     rcx, [rbp+hEvent]; hEvent
0x18005a673  test    rcx, rcx
0x18005a676  jz      short loc_18005A692
0x18005a678  cmp     [rbp+arg_10], dil
0x18005a67c  jz      short loc_18005A688
0x18005a67e  call    cs:__imp_UnregisterGPNotification
0x18005a684  mov     rcx, [rbp+hEvent]; Handle
0x18005a688  call    cs:__imp_NtClose
0x18005a68e  mov     [rbp+hEvent], rdi
0x18005a692  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005a695  call    cs:__imp_SetLastError
0x18005a69b  nop
0x18005a69c  jmp     loc_18005A885
0x18005a6a1  mov     [rbp+arg_10], 1
0x18005a6a5  xor     ecx, ecx; void *
0x18005a6a7  call    ?NtlmQueryPolicyChangeCallback@@YAKPEAX@Z; NtlmQueryPolicyChangeCallback(void *)
0x18005a6ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005a6b3  mov     ecx, 50h ; 'P'; unsigned __int64
0x18005a6b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005a6bd  mov     rbx, rax
0x18005a6c0  test    rax, rax
0x18005a6c3  jz      loc_18005A830
0x18005a6c9  mov     [rax], rax
0x18005a6cc  mov     [rax+8], rax
0x18005a6d0  mov     [rax+10h], dil
0x18005a6d4  mov     [rax+18h], rdi
0x18005a6d8  mov     [rax+20h], dil
0x18005a6dc  mov     [rax+28h], rdi
0x18005a6e0  mov     [rax+30h], rdi
0x18005a6e4  mov     [rax+38h], rdi
0x18005a6e8  mov     [rax+40h], rdi
0x18005a6ec  xor     eax, eax
0x18005a6ee  mov     [rbx+48h], rax
0x18005a6f2  mov     [rbp+arg_0], rbx
0x18005a6f6  mov     byte ptr [rbx+10h], 1
0x18005a6fa  lea     rax, ?NtlmQueryPolicyChangeCallback@@YAKPEAX@Z; NtlmQueryPolicyChangeCallback(void *)
0x18005a701  mov     [rbx+38h], rax
0x18005a705  mov     [rbx+40h], rdi
0x18005a709  mov     rdx, [rbp+hEvent]; hObject
0x18005a70d  mov     [rbp+hEvent], rdi
0x18005a711  mov     [rbx+28h], rdx
0x18005a715  lea     rcx, [rbx+30h]; phNewWaitObject
0x18005a719  mov     [rsp+60h+dwFlags], 8; dwFlags
0x18005a721  mov     [rsp+60h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18005a729  mov     r9, rbx; Context
0x18005a72c  lea     r8, ?WaitCallback@RegistryWatcher@SspRegistry@@CAXPEAXE@Z; Callback
0x18005a733  call    cs:__imp_RegisterWaitForSingleObject
0x18005a739  test    eax, eax
0x18005a73b  jnz     short loc_18005A793
0x18005a73d  mov     [rbp+dwErrCode], 22Ah
0x18005a744  lea     rcx, [rbp+arg_0]
0x18005a748  call    ??1?$unique_ptr@VRegistryWatcher@SspRegistry@@U?$default_delete@VRegistryWatcher@SspRegistry@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(void)
0x18005a74d  nop
0x18005a74e  mov     rcx, [rbp+Handle]; Handle
0x18005a752  test    rcx, rcx
0x18005a755  jz      short loc_18005A761
0x18005a757  call    cs:__imp_NtClose
0x18005a75d  mov     [rbp+Handle], rdi
0x18005a761  mov     rcx, [rbp+hEvent]; hEvent
0x18005a765  test    rcx, rcx
0x18005a768  jz      short loc_18005A784
0x18005a76a  cmp     [rbp+arg_10], dil
0x18005a76e  jz      short loc_18005A77A
0x18005a770  call    cs:__imp_UnregisterGPNotification
0x18005a776  mov     rcx, [rbp+hEvent]; Handle
0x18005a77a  call    cs:__imp_NtClose
0x18005a780  mov     [rbp+hEvent], rdi
0x18005a784  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005a787  call    cs:__imp_SetLastError
0x18005a78d  nop
0x18005a78e  jmp     loc_18005A885
0x18005a793  lea     rcx, stru_18008A5F8; SRWLock
0x18005a79a  call    cs:__imp_AcquireSRWLockExclusive
0x18005a7a0  mov     rax, cs:Context
0x18005a7a7  lea     rcx, Context
0x18005a7ae  cmp     [rax+8], rcx
0x18005a7b2  jz      short loc_18005A7BB
0x18005a7b4  mov     ecx, 3
0x18005a7b9  int     29h; Win8: RtlFailFast(ecx)
0x18005a7bb  mov     [rbx], rax
0x18005a7be  mov     [rbx+8], rcx
0x18005a7c2  mov     [rax+8], rbx
0x18005a7c6  mov     cs:Context, rbx
0x18005a7cd  lea     rcx, stru_18008A5F8; SRWLock
0x18005a7d4  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a7da  mov     [rbp+dwErrCode], edi
0x18005a7dd  mov     [rbp+arg_0], rdi
0x18005a7e1  lea     rcx, [rbp+arg_0]
0x18005a7e5  call    ??1?$unique_ptr@VRegistryWatcher@SspRegistry@@U?$default_delete@VRegistryWatcher@SspRegistry@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(void)
0x18005a7ea  nop
0x18005a7eb  mov     rcx, [rbp+Handle]; Handle
0x18005a7ef  test    rcx, rcx
0x18005a7f2  jz      short loc_18005A7FE
0x18005a7f4  call    cs:__imp_NtClose
0x18005a7fa  mov     [rbp+Handle], rdi
0x18005a7fe  mov     rcx, [rbp+hEvent]; hEvent
0x18005a802  test    rcx, rcx
0x18005a805  jz      short loc_18005A821
0x18005a807  cmp     [rbp+arg_10], dil
0x18005a80b  jz      short loc_18005A817
0x18005a80d  call    cs:__imp_UnregisterGPNotification
0x18005a813  mov     rcx, [rbp+hEvent]; Handle
0x18005a817  call    cs:__imp_NtClose
0x18005a81d  mov     [rbp+hEvent], rdi
0x18005a821  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005a824  call    cs:__imp_SetLastError
0x18005a82a  nop
0x18005a82b  mov     rax, rbx
0x18005a82e  jmp     short loc_18005A887
0x18005a830  mov     [rbp+arg_0], rdi
0x18005a834  mov     [rbp+dwErrCode], 8
0x18005a83b  lea     rcx, [rbp+arg_0]
0x18005a83f  call    ??1?$unique_ptr@VRegistryWatcher@SspRegistry@@U?$default_delete@VRegistryWatcher@SspRegistry@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>::~unique_ptr<SspRegistry::RegistryWatcher,utl::default_delete<SspRegistry::RegistryWatcher>>(void)
0x18005a844  nop
0x18005a845  mov     rcx, [rbp+Handle]; Handle
0x18005a849  test    rcx, rcx
0x18005a84c  jz      short loc_18005A858
0x18005a84e  call    cs:__imp_NtClose
0x18005a854  mov     [rbp+Handle], rdi
0x18005a858  mov     rcx, [rbp+hEvent]; hEvent
0x18005a85c  test    rcx, rcx
0x18005a85f  jz      short loc_18005A87B
0x18005a861  cmp     [rbp+arg_10], dil
0x18005a865  jz      short loc_18005A871
0x18005a867  call    cs:__imp_UnregisterGPNotification
0x18005a86d  mov     rcx, [rbp+hEvent]; Handle
0x18005a871  call    cs:__imp_NtClose
0x18005a877  mov     [rbp+hEvent], rdi
0x18005a87b  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005a87e  call    cs:__imp_SetLastError
0x18005a884  nop
0x18005a885  xor     eax, eax
0x18005a887  add     rsp, 60h
0x18005a88b  pop     rdi
0x18005a88c  pop     rbx
0x18005a88d  pop     rbp
0x18005a88e  retn
```
