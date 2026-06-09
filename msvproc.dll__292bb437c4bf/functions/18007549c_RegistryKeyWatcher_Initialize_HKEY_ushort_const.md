# RegistryKeyWatcher::Initialize(HKEY__ *,ushort const *)

- ea: `0x18007549c`
- end: `0x1800755b6`
- name: `?Initialize@RegistryKeyWatcher@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `282`
- prototype: `__int64 __fastcall(RegistryKeyWatcher *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041984`

## callees

- `0x18001f56c`
- `0x180037b64`
- `0x18007549c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800754be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800754be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800754e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800754e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075532`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075532`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075524`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075517`

## pseudocode

```c
__int64 __fastcall RegistryKeyWatcher::Initialize(RegistryKeyWatcher *this, HKEY a2, const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  HKEY v5; // rcx
  char *EventW; // rbx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  void **v9; // [rsp+38h] [rbp-20h] BYREF
  char *v10; // [rsp+40h] [rbp-18h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  hKey = HKEY_CURRENT_USER;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = (HKEY)*((_QWORD *)this + 8);
  if ( v5 )
  {
    RegCloseKey(v5);
    *((_QWORD *)this + 8) = 0;
  }
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_6;
  if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows\\CurrentVersion\\VideoSettings", 0, 0x11u, &hKey) )
  {
    CloseHandle(EventW);
LABEL_6:
    if ( v3 )
      LeaveCriticalSection(v3);
    return 2147500037LL;
  }
  *((_QWORD *)this + 8) = hKey;
  v9 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v10 = EventW;
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close((char *)this + 72);
  *((_QWORD *)this + 10) = v10;
  v9 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v10 = 0;
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v9);
  if ( (int)RegistryKeyWatcher::ResetNotify(this) < 0 )
    goto LABEL_6;
  if ( v3 )
    LeaveCriticalSection(v3);
  return 0;
}

```

## disassembly

```asm
0x18007549c  mov     [rsp+arg_0], rbx
0x1800754a1  mov     [rsp+arg_8], rsi
0x1800754a6  push    rdi
0x1800754a7  sub     rsp, 50h
0x1800754ab  lea     rdi, [rcx+58h]
0x1800754af  mov     [rsp+58h+hKey], 0FFFFFFFF80000001h
0x1800754b8  mov     rsi, rcx
0x1800754bb  mov     rcx, rdi; lpCriticalSection
0x1800754be  call    cs:__imp_EnterCriticalSection
0x1800754c4  mov     rcx, [rsi+40h]; hKey
0x1800754c8  test    rcx, rcx
0x1800754cb  jz      short loc_1800754DB
0x1800754cd  call    cs:__imp_RegCloseKey
0x1800754d3  mov     qword ptr [rsi+40h], 0
0x1800754db  xor     r9d, r9d; lpName
0x1800754de  xor     r8d, r8d; bInitialState
0x1800754e1  xor     edx, edx; bManualReset
0x1800754e3  xor     ecx, ecx; lpEventAttributes
0x1800754e5  call    cs:__imp_CreateEventW
0x1800754eb  mov     rbx, rax
0x1800754ee  lea     rcx, [rax-1]
0x1800754f2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800754f6  ja      short loc_18007552A
0x1800754f8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800754fd  lea     rax, [rsp+58h+hKey]
0x180075502  mov     r9d, 11h; samDesired
0x180075508  mov     [rsp+58h+phkResult], rax; phkResult
0x18007550d  xor     r8d, r8d; ulOptions
0x180075510  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180075517  call    cs:__imp_RegOpenKeyExW
0x18007551d  test    eax, eax
0x18007551f  jz      short loc_18007554D
0x180075521  mov     rcx, rbx; hObject
0x180075524  call    cs:__imp_CloseHandle
0x18007552a  test    rdi, rdi
0x18007552d  jz      short loc_180075538
0x18007552f  mov     rcx, rdi; lpCriticalSection
0x180075532  call    cs:__imp_LeaveCriticalSection
0x180075538  mov     eax, 80004005h
0x18007553d  mov     rbx, [rsp+58h+arg_0]
0x180075542  mov     rsi, [rsp+58h+arg_8]
0x180075547  add     rsp, 50h
0x18007554b  pop     rdi
0x18007554c  retn
0x18007554d  mov     rax, [rsp+58h+hKey]
0x180075552  lea     rcx, [rsi+48h]
0x180075556  mov     [rsi+40h], rax
0x18007555a  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180075561  mov     [rsp+58h+var_20], rax
0x180075566  mov     [rsp+58h+var_18], rbx
0x18007556b  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180075570  mov     rax, [rsp+58h+var_18]
0x180075575  lea     rcx, [rsp+58h+var_20]
0x18007557a  mov     [rsi+50h], rax
0x18007557e  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180075585  mov     [rsp+58h+var_20], rax
0x18007558a  mov     [rsp+58h+var_18], 0
0x180075593  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180075598  mov     rcx, rsi; this
0x18007559b  call    ?ResetNotify@RegistryKeyWatcher@@AEAAJXZ; RegistryKeyWatcher::ResetNotify(void)
0x1800755a0  test    eax, eax
0x1800755a2  js      short loc_18007552A
0x1800755a4  test    rdi, rdi
0x1800755a7  jz      short loc_1800755B2
0x1800755a9  mov     rcx, rdi; lpCriticalSection
0x1800755ac  call    cs:__imp_LeaveCriticalSection
0x1800755b2  xor     eax, eax
0x1800755b4  jmp     short loc_18007553D
```
