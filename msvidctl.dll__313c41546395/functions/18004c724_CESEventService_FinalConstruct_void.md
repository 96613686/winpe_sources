# CESEventService::FinalConstruct(void)

- ea: `0x18004c724`
- end: `0x18004c84a`
- name: `?FinalConstruct@CESEventService@@QEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(CESEventService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004c3c8`

## callees

- `0x18004c724`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18004c751`
- `ole32!CoCreateInstance` at `0x18004c751`
- `KERNEL32!CreateThread` at `0x18004c7f6`
- `KERNEL32!CreateThread` at `0x18004c7f6`
- `KERNEL32!CreateEventW` at `0x18004c784`
- `KERNEL32!CreateEventW` at `0x18004c784`
- `KERNEL32!GetLastError` at `0x18004c7a4`
- `KERNEL32!GetLastError` at `0x18004c801`
- `KERNEL32!GetLastError` at `0x18004c7a4`
- `KERNEL32!GetLastError` at `0x18004c801`
- `KERNEL32!LeaveCriticalSection` at `0x18004c837`
- `KERNEL32!LeaveCriticalSection` at `0x18004c837`
- `KERNEL32!EnterCriticalSection` at `0x18004c75d`
- `KERNEL32!EnterCriticalSection` at `0x18004c75d`

## pseudocode

```c
__int64 __fastcall CESEventService::FinalConstruct(CESEventService *this)
{
  int Instance; // edi
  HANDLE v3; // r9
  signed int LastError; // eax
  unsigned int v5; // eax
  HANDLE Thread; // rax
  signed int v7; // eax

  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)this + 21);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( Instance < 0 )
    goto LABEL_17;
  v3 = CESEventService::m_hEventQuit;
  if ( CESEventService::m_hEventQuit == (HANDLE)-1LL )
  {
    CESEventService::m_hEventQuit = CreateEventW(0, 1, 0, 0);
    v3 = CESEventService::m_hEventQuit;
    if ( !CESEventService::m_hEventQuit )
    {
      CESEventService::m_hEventQuit = (HANDLE)-1LL;
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      if ( Instance < 0 )
        goto LABEL_17;
      v3 = CESEventService::m_hEventQuit;
    }
  }
  if ( CESEventService::m_dwEventThreadId )
  {
    v5 = CESEventService::m_dwThreadRefCount;
    if ( CESEventService::m_dwThreadRefCount )
      goto LABEL_16;
  }
  Thread = CreateThread(0, 0, CESEventService::EventingThreadProc, v3, 0, &CESEventService::m_dwEventThreadId);
  if ( Thread )
  {
    CESEventService::m_hEventThread = Thread;
    v5 = 0;
    goto LABEL_16;
  }
  v7 = GetLastError();
  Instance = v7;
  if ( v7 > 0 )
    Instance = (unsigned __int16)v7 | 0x80070000;
  if ( Instance >= 0 )
  {
    v5 = CESEventService::m_dwThreadRefCount;
LABEL_16:
    CESEventService::m_dwThreadRefCount = v5 + 1;
  }
LABEL_17:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004c724  mov     [rsp+arg_0], rbx
0x18004c729  push    rdi
0x18004c72a  sub     rsp, 30h
0x18004c72e  lea     rax, [rcx+0A8h]
0x18004c735  xor     edx, edx; pUnkOuter
0x18004c737  mov     rbx, rcx
0x18004c73a  mov     [rsp+38h+ppv], rax; ppv
0x18004c73f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18004c746  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18004c74d  lea     r8d, [rdx+1]; dwClsContext
0x18004c751  call    cs:__imp_CoCreateInstance
0x18004c757  lea     rcx, [rbx+70h]; lpCriticalSection
0x18004c75b  mov     edi, eax
0x18004c75d  call    cs:__imp_EnterCriticalSection
0x18004c763  test    edi, edi
0x18004c765  js      loc_18004C833
0x18004c76b  mov     r9, cs:?m_hEventQuit@CESEventService@@0PEAXEA; void * CESEventService::m_hEventQuit
0x18004c772  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18004c776  jnz     short loc_18004C7C4
0x18004c778  xor     r9d, r9d; lpName
0x18004c77b  xor     r8d, r8d; bInitialState
0x18004c77e  xor     ecx, ecx; lpEventAttributes
0x18004c780  lea     edx, [r9+1]; bManualReset
0x18004c784  call    cs:__imp_CreateEventW
0x18004c78a  mov     cs:?m_hEventQuit@CESEventService@@0PEAXEA, rax; void * CESEventService::m_hEventQuit
0x18004c791  mov     r9, rax
0x18004c794  test    rax, rax
0x18004c797  jnz     short loc_18004C7C4
0x18004c799  mov     cs:?m_hEventQuit@CESEventService@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * CESEventService::m_hEventQuit
0x18004c7a4  call    cs:__imp_GetLastError
0x18004c7aa  mov     edi, eax
0x18004c7ac  test    eax, eax
0x18004c7ae  jle     short loc_18004C7B9
0x18004c7b0  movzx   edi, ax
0x18004c7b3  or      edi, 80070000h
0x18004c7b9  test    edi, edi
0x18004c7bb  js      short loc_18004C833
0x18004c7bd  mov     r9, cs:?m_hEventQuit@CESEventService@@0PEAXEA; lpParameter
0x18004c7c4  cmp     cs:?m_dwEventThreadId@CESEventService@@0KA, 0; ulong CESEventService::m_dwEventThreadId
0x18004c7cb  jz      short loc_18004C7D7
0x18004c7cd  mov     eax, cs:?m_dwThreadRefCount@CESEventService@@0KA; ulong CESEventService::m_dwThreadRefCount
0x18004c7d3  test    eax, eax
0x18004c7d5  jnz     short loc_18004C82B
0x18004c7d7  lea     rax, ?m_dwEventThreadId@CESEventService@@0KA; ulong CESEventService::m_dwEventThreadId
0x18004c7de  xor     edx, edx; dwStackSize
0x18004c7e0  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18004c7e5  lea     r8, ?EventingThreadProc@CESEventService@@CAKPEAX@Z; lpStartAddress
0x18004c7ec  xor     ecx, ecx; lpThreadAttributes
0x18004c7ee  mov     dword ptr [rsp+38h+ppv], 0; dwCreationFlags
0x18004c7f6  call    cs:__imp_CreateThread
0x18004c7fc  test    rax, rax
0x18004c7ff  jnz     short loc_18004C822
0x18004c801  call    cs:__imp_GetLastError
0x18004c807  mov     edi, eax
0x18004c809  test    eax, eax
0x18004c80b  jle     short loc_18004C816
0x18004c80d  movzx   edi, ax
0x18004c810  or      edi, 80070000h
0x18004c816  test    edi, edi
0x18004c818  js      short loc_18004C833
0x18004c81a  mov     eax, cs:?m_dwThreadRefCount@CESEventService@@0KA; ulong CESEventService::m_dwThreadRefCount
0x18004c820  jmp     short loc_18004C82B
0x18004c822  mov     cs:?m_hEventThread@CESEventService@@0PEAXEA, rax; void * CESEventService::m_hEventThread
0x18004c829  xor     eax, eax
0x18004c82b  inc     eax
0x18004c82d  mov     cs:?m_dwThreadRefCount@CESEventService@@0KA, eax; ulong CESEventService::m_dwThreadRefCount
0x18004c833  lea     rcx, [rbx+70h]; lpCriticalSection
0x18004c837  call    cs:__imp_LeaveCriticalSection
0x18004c83d  mov     rbx, [rsp+38h+arg_0]
0x18004c842  mov     eax, edi
0x18004c844  add     rsp, 30h
0x18004c848  pop     rdi
0x18004c849  retn
```
