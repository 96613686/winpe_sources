# CSearchHandlerList::RegistryChanged(ulong)

- ea: `0x1800ba2c0`
- end: `0x1800ba43a`
- name: `?RegistryChanged@CSearchHandlerList@@IEAA_NK@Z`
- size: `378`
- prototype: `bool __fastcall(CSearchHandlerList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c9700`

## callees

- `0x18000bf8c`
- `0x180022710`
- `0x180026b58`
- `0x180054e14`
- `0x1800ba2c0`
- `0x1800e2374`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ba39a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ba39a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba351`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba351`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ba2d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ba2d7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800ba3e0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800ba3e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800ba3b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800ba412`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800ba3b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800ba412`

## string_xrefs

- `0x1800ba3a4`: `SearchHandlerList - Registry change detected... waiting 60 seconds to re-inspect.`

## pseudocode

```c
char __fastcall CSearchHandlerList::RegistryChanged(CSearchHandlerList *this, int a2)
{
  int v4; // eax
  HANDLE *v5; // rsi
  HANDLE v6; // rcx
  HANDLE EventW; // rax
  unsigned int Error; // eax
  char v9; // di
  unsigned int v10; // eax
  int v11; // esi
  char v12; // di
  int fAsynchronous; // [rsp+20h] [rbp-38h]
  unsigned int fAsynchronousa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( *((_DWORD *)this + 74) == -1 )
    *((_DWORD *)this + 74) = GetCurrentThreadId();
  if ( !*((_QWORD *)this + 35) )
  {
    v4 = CRegistry::Init(
           (CSearchHandlerList *)((char *)this + 104),
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertyHandlers",
           0x20019u,
           0);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x570,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\handlerlist.cxx",
        (const char *)(unsigned int)v4,
        fAsynchronous);
  }
  v5 = (HANDLE *)((char *)this + 288);
  v6 = (HANDLE)*((_QWORD *)this + 36);
  if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v9 = 0;
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 288,
      EventW);
    v6 = *v5;
    if ( (((unsigned __int64)*v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      Error = ResultFromLastError();
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x578,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\handlerlist.cxx",
        (const char *)Error,
        fAsynchronous);
    }
    v9 = 1;
  }
  if ( WaitForSingleObject(v6, 0) )
  {
    if ( !v9 )
      goto LABEL_16;
  }
  else
  {
    ETWLog::Log(L"SearchHandlerList - Registry change detected... waiting 60 seconds to re-inspect.");
    *((_DWORD *)this + 75) = GetTickCount();
  }
  v10 = RegNotifyChangeKeyValue(*((HKEY *)this + 35), 1, a2 | 5, *v5, 1);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x58B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\handlerlist.cxx",
      (const char *)v10,
      fAsynchronousa);
LABEL_16:
  v11 = *((_DWORD *)this + 75);
  v12 = 0;
  if ( v11 != -1 && GetTickCount() - v11 > 0xEA60 )
  {
    *((_DWORD *)this + 75) = -1;
    return 1;
  }
  return v12;
}

```

## disassembly

```asm
0x1800ba2c0  push    rbx
0x1800ba2c2  push    rbp
0x1800ba2c3  push    rsi
0x1800ba2c4  push    rdi
0x1800ba2c5  sub     rsp, 38h
0x1800ba2c9  cmp     dword ptr [rcx+128h], 0FFFFFFFFh
0x1800ba2d0  mov     ebp, edx
0x1800ba2d2  mov     rbx, rcx
0x1800ba2d5  jnz     short loc_1800BA2E3
0x1800ba2d7  call    cs:__imp_GetCurrentThreadId
0x1800ba2dd  mov     [rbx+128h], eax
0x1800ba2e3  lea     rcx, [rbx+68h]; this
0x1800ba2e7  cmp     qword ptr [rcx+0B0h], 0
0x1800ba2ef  jnz     short loc_1800BA331
0x1800ba2f1  mov     r9d, 20019h; unsigned int
0x1800ba2f7  mov     qword ptr [rsp+58h+fAsynchronous], 0; int
0x1800ba300  lea     r8, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800ba307  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800ba30e  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1800ba313  test    eax, eax
0x1800ba315  jns     short loc_1800BA331
0x1800ba317  mov     rcx, [rsp+58h]; this
0x1800ba31c  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800ba323  mov     r9d, eax; char *
0x1800ba326  mov     edx, 570h; void *
0x1800ba32b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba331  lea     rsi, [rbx+120h]
0x1800ba338  mov     rcx, [rsi]; hHandle
0x1800ba33b  lea     rax, [rcx+1]
0x1800ba33f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800ba345  jnz     short loc_1800BA395
0x1800ba347  xor     r9d, r9d; lpName
0x1800ba34a  xor     r8d, r8d; bInitialState
0x1800ba34d  xor     edx, edx; bManualReset
0x1800ba34f  xor     ecx, ecx; lpEventAttributes
0x1800ba351  call    cs:__imp_CreateEventW
0x1800ba357  mov     rdx, rax
0x1800ba35a  mov     rcx, rsi
0x1800ba35d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ba362  mov     rcx, [rsi]
0x1800ba365  lea     rax, [rcx+1]
0x1800ba369  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800ba36f  jnz     short loc_1800BA390
0x1800ba371  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800ba376  mov     rcx, [rsp+58h]; this
0x1800ba37b  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800ba382  mov     r9d, eax; char *
0x1800ba385  mov     edx, 578h; void *
0x1800ba38a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba390  mov     dil, 1
0x1800ba393  jmp     short loc_1800BA398
0x1800ba395  xor     dil, dil
0x1800ba398  xor     edx, edx; dwMilliseconds
0x1800ba39a  call    cs:__imp_WaitForSingleObject
0x1800ba3a0  test    eax, eax
0x1800ba3a2  jnz     short loc_1800BA3BE
0x1800ba3a4  lea     rcx, aSearchhandlerl_1; "SearchHandlerList - Registry change det"...
0x1800ba3ab  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800ba3b0  call    cs:__imp_GetTickCount
0x1800ba3b6  mov     [rbx+12Ch], eax
0x1800ba3bc  jmp     short loc_1800BA3C3
0x1800ba3be  test    dil, dil
0x1800ba3c1  jz      short loc_1800BA404
0x1800ba3c3  mov     r9, [rsi]; hEvent
0x1800ba3c6  or      ebp, 5
0x1800ba3c9  mov     rcx, [rbx+118h]; hKey
0x1800ba3d0  mov     r8d, ebp; dwNotifyFilter
0x1800ba3d3  mov     edx, 1; bWatchSubtree
0x1800ba3d8  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x1800ba3e0  call    cs:__imp_RegNotifyChangeKeyValue
0x1800ba3e6  test    eax, eax
0x1800ba3e8  jz      short loc_1800BA404
0x1800ba3ea  mov     rcx, [rsp+58h]; this
0x1800ba3ef  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800ba3f6  mov     r9d, eax; char *
0x1800ba3f9  mov     edx, 58Bh; void *
0x1800ba3fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ba404  mov     esi, [rbx+12Ch]
0x1800ba40a  xor     dil, dil
0x1800ba40d  cmp     esi, 0FFFFFFFFh
0x1800ba410  jz      short loc_1800BA42E
0x1800ba412  call    cs:__imp_GetTickCount
0x1800ba418  sub     eax, esi
0x1800ba41a  cmp     eax, 0EA60h
0x1800ba41f  jbe     short loc_1800BA42E
0x1800ba421  mov     dword ptr [rbx+12Ch], 0FFFFFFFFh
0x1800ba42b  mov     dil, 1
0x1800ba42e  mov     al, dil
0x1800ba431  add     rsp, 38h
0x1800ba435  pop     rdi
0x1800ba436  pop     rsi
0x1800ba437  pop     rbp
0x1800ba438  pop     rbx
0x1800ba439  retn
```
