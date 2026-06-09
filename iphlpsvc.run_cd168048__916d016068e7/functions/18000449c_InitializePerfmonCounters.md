# InitializePerfmonCounters

- ea: `0x18000449c`
- end: `0x18000464c`
- name: `InitializePerfmonCounters`
- size: `432`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800041a0`
- `0x1800331b0`
- `0x180041710`
- `0x180043398`

## callees

- `0x18000449c`
- `0x18000d7b0`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800045c3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800045c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004513`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045d9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004596`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004596`

## string_xrefs

- `0x1800044e8`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`
- `0x18000452b`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`
- `0x180004601`: `onecoreuap\net\netio\iphlpsvc\service\perfmoncounter.c`

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
0x18000449c  push    rbx
0x18000449e  push    rbp
0x18000449f  push    rsi
0x1800044a0  push    rdi
0x1800044a1  push    r13
0x1800044a3  push    r14
0x1800044a5  sub     rsp, 0C8h
0x1800044ac  mov     rax, cs:__security_cookie
0x1800044b3  xor     rax, rsp
0x1800044b6  mov     [rsp+0F8h+var_48], rax
0x1800044be  mov     rbp, rdx
0x1800044c1  movsxd  rsi, ecx
0x1800044c4  xor     edx, edx; Val
0x1800044c6  lea     rcx, [rsp+0F8h+Buffer]; void *
0x1800044cb  lea     r8d, [rdx+64h]; Size
0x1800044cf  call    memset_0
0x1800044d4  mov     rdi, cs:g_PerfmonLock
0x1800044db  lea     r13, aInitializeperf; "InitializePerfmonCounters"
0x1800044e2  mov     r14d, 76h ; 'v'
0x1800044e8  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800044ef  mov     dword ptr [rsp+0F8h+var_D0], r14d
0x1800044f4  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x1800044fb  mov     r8, rdi
0x1800044fe  mov     [rsp+0F8h+var_D8], r13
0x180004503  mov     ecx, 800000h
0x180004508  call    EventWrite0
0x18000450d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004510  mov     rcx, rdi; hHandle
0x180004513  call    cs:__imp_WaitForSingleObject
0x18000451a  nop     dword ptr [rax+rax+00h]
0x18000451f  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180004526  mov     r8, rdi
0x180004529  mov     ebx, eax
0x18000452b  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004532  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180004539  mov     [rsp+0F8h+var_C8], ebx
0x18000453d  test    ebx, ebx
0x18000453f  mov     dword ptr [rsp+0F8h+var_D0], r14d
0x180004544  mov     ecx, 800000h
0x180004549  mov     [rsp+0F8h+var_D8], r13
0x18000454e  cmovnz  rdx, rax
0x180004552  call    EventWrite0
0x180004557  test    ebx, ebx
0x180004559  jz      short loc_180004565
0x18000455b  mov     edi, 426h
0x180004560  jmp     loc_180004629
0x180004565  mov     edi, cs:PerfmonCounterInitialization
0x18000456b  test    edi, edi
0x18000456d  jnz     short loc_1800045E7
0x18000456f  mov     rcx, cs:g_ModuleHandle; hInstance
0x180004576  lea     r14, CounterSetInstanceContexts
0x18000457d  mov     rbx, rsi
0x180004580  lea     r9d, [rdi+32h]; cchBufferMax
0x180004584  lea     rsi, [rsi+rsi*2]
0x180004588  mov     edx, 258h; uID
0x18000458d  lea     r8, [rsp+0F8h+Buffer]; lpBuffer
0x180004592  mov     [r14+rsi*8], rbp
0x180004596  call    cs:__imp_LoadStringW
0x18000459d  nop     dword ptr [rax+rax+00h]
0x1800045a2  test    eax, eax
0x1800045a4  jz      short loc_1800045D9
0x1800045a6  mov     rcx, cs:IphlpsvcProvider; ProviderHandle
0x1800045ad  lea     rdx, PerfmonGuids
0x1800045b4  shl     rbx, 4
0x1800045b8  lea     r8, [rsp+0F8h+Buffer]; Name
0x1800045bd  add     rdx, rbx; CounterSetGuid
0x1800045c0  xor     r9d, r9d; Id
0x1800045c3  call    cs:__imp_PerfCreateInstance
0x1800045ca  nop     dword ptr [rax+rax+00h]
0x1800045cf  mov     [r14+rsi*8+8], rax
0x1800045d4  test    rax, rax
0x1800045d7  jnz     short loc_1800045E7
0x1800045d9  call    cs:__imp_GetLastError
0x1800045e0  nop     dword ptr [rax+rax+00h]
0x1800045e5  mov     edi, eax
0x1800045e7  mov     rbx, cs:g_PerfmonLock
0x1800045ee  mov     rcx, rbx; hMutex
0x1800045f1  call    cs:__imp_ReleaseMutex
0x1800045f8  nop     dword ptr [rax+rax+00h]
0x1800045fd  mov     [rsp+0F8h+var_C8], eax
0x180004601  lea     r9, aOnecoreuapNetN_16; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004608  mov     dword ptr [rsp+0F8h+var_D0], 9Ch
0x180004610  mov     r8, rbx
0x180004613  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18000461a  mov     [rsp+0F8h+var_D8], r13
0x18000461f  mov     ecx, 800000h
0x180004624  call    EventWrite0
0x180004629  mov     eax, edi
0x18000462b  mov     rcx, [rsp+0F8h+var_48]
0x180004633  xor     rcx, rsp; StackCookie
0x180004636  call    __security_check_cookie
0x18000463b  add     rsp, 0C8h
0x180004642  pop     r14
0x180004644  pop     r13
0x180004646  pop     rdi
0x180004647  pop     rsi
0x180004648  pop     rbp
0x180004649  pop     rbx
0x18000464a  retn
```
