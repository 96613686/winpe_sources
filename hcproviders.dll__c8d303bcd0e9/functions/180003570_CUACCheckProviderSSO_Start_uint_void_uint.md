# CUACCheckProviderSSO::Start(uint,void * *,uint *)

- ea: `0x180003570`
- end: `0x1800036c0`
- name: `?Start@CUACCheckProviderSSO@@UEAAJIPEAPEAXPEAI@Z`
- size: `336`
- prototype: `__int64 __fastcall(CUACCheckProviderSSO *__hidden this, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003570`
- `0x180004380`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003613`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800035fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800035fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003658`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003658`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800035a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800035a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003684`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003684`

## pseudocode

```c
HRESULT __fastcall CUACCheckProviderSSO::Start(CUACCheckProviderSSO *this, __int64 a2, void **a3, unsigned int *a4)
{
  HRESULT result; // eax
  signed int started; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  LSTATUS v9; // eax
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  *a4 = 0;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( result >= 0 )
  {
    started = (*(__int64 (__fastcall **)(LPVOID, char *, GUID *, unsigned int *))(*(_QWORD *)ppv + 24LL))(
                ppv,
                (char *)this - 8,
                &IID_IOleCommandTarget,
                &CUACCheckProviderSSO::s_dwCookie);
    if ( started >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, L"{43a2b8d7-6fed-4c18-bd36-b4630d61afb5}");
      *((_QWORD *)this + 2) = EventW;
      if ( EventW )
      {
        SetEvent(EventW);
        v9 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
               0,
               0x10u,
               (PHKEY)this + 3);
        started = v9;
        if ( v9 > 0 )
          started = (unsigned __int16)v9 | 0x80070000;
        if ( started >= 0 )
          started = CUACCheckProviderSSO::_StartWatching((CUACCheckProviderSSO *)((char *)this - 8));
      }
      else
      {
        LastError = GetLastError();
        started = LastError;
        if ( LastError > 0 )
          started = (unsigned __int16)LastError | 0x80070000;
        if ( started >= 0 )
          started = -2147467259;
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return started;
  }
  return result;
}

```

## disassembly

```asm
0x180003570  push    rdi
0x180003572  sub     rsp, 30h
0x180003576  xor     eax, eax
0x180003578  mov     rdi, rcx
0x18000357b  mov     [r9], eax
0x18000357e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003585  mov     [rsp+38h+arg_18], rax
0x18000358a  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003591  lea     rax, [rsp+38h+arg_18]
0x180003596  xor     edx, edx; pUnkOuter
0x180003598  mov     r8d, 1; dwClsContext
0x18000359e  mov     [rsp+38h+ppv], rax; ppv
0x1800035a3  call    cs:__imp_CoCreateInstance
0x1800035aa  nop     dword ptr [rax+rax+00h]
0x1800035af  test    eax, eax
0x1800035b1  jns     short loc_1800035BA
0x1800035b3  add     rsp, 30h
0x1800035b7  pop     rdi
0x1800035b8  retn
0x1800035ba  mov     rcx, [rsp+38h+arg_18]
0x1800035bf  lea     r9, ?s_dwCookie@CUACCheckProviderSSO@@0KA; ulong CUACCheckProviderSSO::s_dwCookie
0x1800035c6  mov     [rsp+38h+arg_0], rbx
0x1800035cb  lea     r8, IID_IOleCommandTarget
0x1800035d2  lea     rdx, [rdi-8]
0x1800035d6  mov     [rsp+38h+arg_8], rsi
0x1800035db  mov     rax, [rcx]
0x1800035de  mov     rax, [rax+18h]
0x1800035e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e7  mov     ebx, eax
0x1800035e9  test    eax, eax
0x1800035eb  js      short loc_180003633
0x1800035ed  lea     r9, Name; "{43a2b8d7-6fed-4c18-bd36-b4630d61afb5}"
0x1800035f4  xor     r8d, r8d; bInitialState
0x1800035f7  mov     edx, 1; bManualReset
0x1800035fc  xor     ecx, ecx; lpEventAttributes
0x1800035fe  call    cs:__imp_CreateEventW
0x180003605  nop     dword ptr [rax+rax+00h]
0x18000360a  mov     [rdi+10h], rax
0x18000360e  test    rax, rax
0x180003611  jnz     short loc_180003655
0x180003613  call    cs:__imp_GetLastError
0x18000361a  nop     dword ptr [rax+rax+00h]
0x18000361f  mov     ebx, eax
0x180003621  test    eax, eax
0x180003623  jg      loc_1800036B2
0x180003629  test    ebx, ebx
0x18000362b  mov     eax, 80004005h
0x180003630  cmovns  ebx, eax
0x180003633  mov     rcx, [rsp+38h+arg_18]
0x180003638  mov     rax, [rcx]
0x18000363b  mov     rax, [rax+10h]
0x18000363f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003644  mov     rsi, [rsp+38h+arg_8]
0x180003649  mov     eax, ebx
0x18000364b  mov     rbx, [rsp+38h+arg_0]
0x180003650  jmp     loc_1800035B3
0x180003655  mov     rcx, rax; hEvent
0x180003658  call    cs:__imp_SetEvent
0x18000365f  nop     dword ptr [rax+rax+00h]
0x180003664  lea     rax, [rdi+18h]
0x180003668  mov     r9d, 10h; samDesired
0x18000366e  xor     r8d, r8d; ulOptions
0x180003671  mov     [rsp+38h+ppv], rax; phkResult
0x180003676  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000367d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003684  call    cs:__imp_RegOpenKeyExW
0x18000368b  nop     dword ptr [rax+rax+00h]
0x180003690  mov     ebx, eax
0x180003692  test    eax, eax
0x180003694  jg      short loc_1800036A7
0x180003696  test    ebx, ebx
0x180003698  js      short loc_180003633
0x18000369a  lea     rcx, [rdi-8]; this
0x18000369e  call    ?_StartWatching@CUACCheckProviderSSO@@AEAAJXZ; CUACCheckProviderSSO::_StartWatching(void)
0x1800036a3  mov     ebx, eax
0x1800036a5  jmp     short loc_180003633
0x1800036a7  movzx   ebx, ax
0x1800036aa  or      ebx, 80070000h
0x1800036b0  jmp     short loc_180003696
0x1800036b2  movzx   ebx, ax
0x1800036b5  or      ebx, 80070000h
0x1800036bb  jmp     loc_180003629
```
