# InitializePerfmonCounters

- ea: `0x1800044ac`
- end: `0x18000465c`
- name: `InitializePerfmonCounters`
- size: `432`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800041b0`
- `0x1800331c0`
- `0x1800416d0`
- `0x180043358`

## callees

- `0x1800044ac`
- `0x18000d7c0`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800045d3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800045d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004601`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004601`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004523`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800045a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800045a6`

## string_xrefs

- `0x1800044f8`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`
- `0x18000453b`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`
- `0x180004611`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`

## pseudocode

```c
__int64 __fastcall InitializePerfmonCounters(int a1, __int64 a2)
{
  __int64 v3; // rsi
  HANDLE v4; // rdi
  DWORD v5; // eax
  const wchar_t *v6; // rdx
  DWORD v7; // ebx
  DWORD LastError; // edi
  HINSTANCE v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rsi
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  HANDLE v13; // rbx
  __int64 v15; // [rsp+28h] [rbp-D0h]
  __int64 v16; // [rsp+28h] [rbp-D0h]
  __int64 v17; // [rsp+30h] [rbp-C8h]
  WCHAR Buffer[56]; // [rsp+40h] [rbp-B8h] BYREF

  v3 = a1;
  memset_0(Buffer, 0, 0x64u);
  v4 = g_PerfmonLock;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_PerfmonLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\perfmoncounter.c",
    "InitializePerfmonCounters",
    118);
  v5 = WaitForSingleObject(v4, 0xFFFFFFFF);
  v6 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v7 = v5;
  LODWORD(v15) = 118;
  if ( v5 )
    v6 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  EventWrite0(
    0x800000,
    v6,
    v4,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\perfmoncounter.c",
    "InitializePerfmonCounters",
    v15,
    v5);
  if ( v7 )
  {
    return 1062;
  }
  else
  {
    LastError = PerfmonCounterInitialization;
    if ( !PerfmonCounterInitialization )
    {
      v9 = g_ModuleHandle;
      v10 = v3;
      v11 = 3 * v3;
      CounterSetInstanceContexts[v11] = a2;
      if ( !LoadStringW(v9, 0x258u, Buffer, 50)
        || (Instance = PerfCreateInstance(IphlpsvcProvider, (LPCGUID)&PerfmonGuids[v10], Buffer, 0),
            (CounterSetInstanceContexts[v11 + 1] = (__int64)Instance) == 0) )
      {
        LastError = GetLastError();
      }
    }
    v13 = g_PerfmonLock;
    LODWORD(v17) = ReleaseMutex(g_PerfmonLock);
    LODWORD(v16) = 156;
    EventWrite0(
      0x800000,
      L"Lock (%p) released at %S : %S : %u. Return %d",
      v13,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\perfmoncounter.c",
      "InitializePerfmonCounters",
      v16,
      v17);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800044ac  push    rbx
0x1800044ae  push    rbp
0x1800044af  push    rsi
0x1800044b0  push    rdi
0x1800044b1  push    r13
0x1800044b3  push    r14
0x1800044b5  sub     rsp, 0C8h
0x1800044bc  mov     rax, cs:__security_cookie
0x1800044c3  xor     rax, rsp
0x1800044c6  mov     [rsp+0F8h+var_48], rax
0x1800044ce  mov     rbp, rdx
0x1800044d1  movsxd  rsi, ecx
0x1800044d4  xor     edx, edx; Val
0x1800044d6  lea     rcx, [rsp+0F8h+Buffer]; void *
0x1800044db  lea     r8d, [rdx+64h]; Size
0x1800044df  call    memset_0
0x1800044e4  mov     rdi, cs:g_PerfmonLock
0x1800044eb  lea     r13, aInitializeperf; "InitializePerfmonCounters"
0x1800044f2  mov     r14d, 76h ; 'v'
0x1800044f8  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800044ff  mov     dword ptr [rsp+0F8h+var_D0], r14d
0x180004504  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18000450b  mov     r8, rdi
0x18000450e  mov     [rsp+0F8h+var_D8], r13
0x180004513  mov     ecx, 800000h
0x180004518  call    EventWrite0
0x18000451d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004520  mov     rcx, rdi; hHandle
0x180004523  call    cs:__imp_WaitForSingleObject
0x18000452a  nop     dword ptr [rax+rax+00h]
0x18000452f  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180004536  mov     r8, rdi
0x180004539  mov     ebx, eax
0x18000453b  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004542  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180004549  mov     [rsp+0F8h+var_C8], ebx
0x18000454d  test    ebx, ebx
0x18000454f  mov     dword ptr [rsp+0F8h+var_D0], r14d
0x180004554  mov     ecx, 800000h
0x180004559  mov     [rsp+0F8h+var_D8], r13
0x18000455e  cmovnz  rdx, rax
0x180004562  call    EventWrite0
0x180004567  test    ebx, ebx
0x180004569  jz      short loc_180004575
0x18000456b  mov     edi, 426h
0x180004570  jmp     loc_180004639
0x180004575  mov     edi, cs:PerfmonCounterInitialization
0x18000457b  test    edi, edi
0x18000457d  jnz     short loc_1800045F7
0x18000457f  mov     rcx, cs:g_ModuleHandle; hInstance
0x180004586  lea     r14, CounterSetInstanceContexts
0x18000458d  mov     rbx, rsi
0x180004590  lea     r9d, [rdi+32h]; cchBufferMax
0x180004594  lea     rsi, [rsi+rsi*2]
0x180004598  mov     edx, 258h; uID
0x18000459d  lea     r8, [rsp+0F8h+Buffer]; lpBuffer
0x1800045a2  mov     [r14+rsi*8], rbp
0x1800045a6  call    cs:__imp_LoadStringW
0x1800045ad  nop     dword ptr [rax+rax+00h]
0x1800045b2  test    eax, eax
0x1800045b4  jz      short loc_1800045E9
0x1800045b6  mov     rcx, cs:IphlpsvcProvider; ProviderHandle
0x1800045bd  lea     rdx, PerfmonGuids
0x1800045c4  shl     rbx, 4
0x1800045c8  lea     r8, [rsp+0F8h+Buffer]; Name
0x1800045cd  add     rdx, rbx; CounterSetGuid
0x1800045d0  xor     r9d, r9d; Id
0x1800045d3  call    cs:__imp_PerfCreateInstance
0x1800045da  nop     dword ptr [rax+rax+00h]
0x1800045df  mov     [r14+rsi*8+8], rax
0x1800045e4  test    rax, rax
0x1800045e7  jnz     short loc_1800045F7
0x1800045e9  call    cs:__imp_GetLastError
0x1800045f0  nop     dword ptr [rax+rax+00h]
0x1800045f5  mov     edi, eax
0x1800045f7  mov     rbx, cs:g_PerfmonLock
0x1800045fe  mov     rcx, rbx; hMutex
0x180004601  call    cs:__imp_ReleaseMutex
0x180004608  nop     dword ptr [rax+rax+00h]
0x18000460d  mov     [rsp+0F8h+var_C8], eax
0x180004611  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004618  mov     dword ptr [rsp+0F8h+var_D0], 9Ch
0x180004620  mov     r8, rbx
0x180004623  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18000462a  mov     [rsp+0F8h+var_D8], r13
0x18000462f  mov     ecx, 800000h
0x180004634  call    EventWrite0
0x180004639  mov     eax, edi
0x18000463b  mov     rcx, [rsp+0F8h+var_48]
0x180004643  xor     rcx, rsp; StackCookie
0x180004646  call    __security_check_cookie
0x18000464b  add     rsp, 0C8h
0x180004652  pop     r14
0x180004654  pop     r13
0x180004656  pop     rdi
0x180004657  pop     rsi
0x180004658  pop     rbp
0x180004659  pop     rbx
0x18000465a  retn
```
