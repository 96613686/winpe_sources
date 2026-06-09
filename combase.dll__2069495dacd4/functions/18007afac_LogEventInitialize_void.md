# LogEventInitialize(void)

- ea: `0x18007afac`
- end: `0x18007b10f`
- name: `?LogEventInitialize@@YAXXZ`
- size: `355`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007aac0`
- `0x180154b60`

## callees

- `0x180040078`
- `0x18007afac`
- `0x1801567c4`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b104`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b063`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007afd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007afd5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18007b006`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18007b006`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x18007b023`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x18007b023`

## string_xrefs

- `0x18007afdb`: `MSFT.VSA.COM.DISABLE.%d`
- `0x18007b0bf`: `COM Runtime %d`

## pseudocode

```c
void LogEventInitialize(void)
{
  __int64 CurrentProcessId; // rdi
  HANDLE v1; // rax
  CDebugEventFire *v2; // rbx
  wchar_t sz[32]; // [rsp+20h] [rbp-A8h] BYREF
  wchar_t szEvent[40]; // [rsp+60h] [rbp-68h] BYREF

  if ( !g_hEventLogger )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( StringCchPrintfW(szEvent, 0x28u, L"MSFT.VSA.COM.DISABLE.%d", CurrentProcessId) >= 0 )
    {
      v1 = OpenEventW(0x100000u, 0, szEvent);
      if ( v1 )
      {
        CloseHandle(v1);
      }
      else
      {
        g_hEventLogger = OpenEventA(0x100002u, 0, "MSFT.VSA.IEC.STATUS.6c736db0");
        if ( g_hEventLogger )
        {
          v2 = (CDebugEventFire *)HeapAlloc(g_hHeap, 0, 0x68u);
          if ( v2 )
          {
            v2->__vftable = (CDebugEventFire_vtbl *)COle32DebugEventFire::`vftable';
            CDebugEventFire::Initialize(v2);
            v2->QueryInterface(v2, &IID_ISystemDebugEventFire, (void **)&g_pEventFire);
            if ( StringCchPrintfW(sz, 0x20u, L"COM Runtime %d", (unsigned int)CurrentProcessId) >= 0 )
              g_pEventFire->BeginSession(g_pEventFire, &GUID_ComEventLogSession, sz);
          }
          else
          {
            CloseHandle(g_hEventLogger);
            g_hEventLogger = 0;
            g_pEventFire = 0;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18007afac  mov     [rsp+arg_0], rbx
0x18007afb1  push    rdi
0x18007afb2  sub     rsp, 0C0h
0x18007afb9  mov     rax, cs:__security_cookie
0x18007afc0  xor     rax, rsp
0x18007afc3  mov     [rsp+0C8h+var_18], rax
0x18007afcb  cmp     cs:g_hEventLogger, 0
0x18007afd3  jnz     short loc_18007B035
0x18007afd5  call    cs:__imp_GetCurrentProcessId
0x18007afdb  lea     r8, aMsftVsaComDisa; "MSFT.VSA.COM.DISABLE.%d"
0x18007afe2  mov     edx, 28h ; '('; cchDest
0x18007afe7  mov     r9d, eax
0x18007afea  lea     rcx, [rsp+0C8h+szEvent]; pszDest
0x18007afef  mov     edi, eax
0x18007aff1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007aff6  test    eax, eax
0x18007aff8  js      short loc_18007B035
0x18007affa  lea     r8, [rsp+0C8h+szEvent]; lpName
0x18007afff  xor     edx, edx; bInheritHandle
0x18007b001  mov     ecx, 100000h; dwDesiredAccess
0x18007b006  call    cs:__imp_OpenEventW
0x18007b00c  test    rax, rax
0x18007b00f  jnz     loc_18007B101
0x18007b015  lea     r8, Name; "MSFT.VSA.IEC.STATUS.6c736db0"
0x18007b01c  xor     edx, edx; bInheritHandle
0x18007b01e  mov     ecx, 100002h; dwDesiredAccess
0x18007b023  call    cs:__imp_OpenEventA
0x18007b029  mov     cs:g_hEventLogger, rax
0x18007b030  test    rax, rax
0x18007b033  jnz     short loc_18007B056
0x18007b035  mov     rcx, [rsp+0C8h+var_18]
0x18007b03d  xor     rcx, rsp; StackCookie
0x18007b040  call    __security_check_cookie
0x18007b045  mov     rbx, [rsp+0C8h+arg_0]
0x18007b04d  add     rsp, 0C0h
0x18007b054  pop     rdi
0x18007b055  retn
0x18007b056  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007b05d  xor     edx, edx; dwFlags
0x18007b05f  lea     r8d, [rdx+68h]; dwBytes
0x18007b063  call    cs:__imp_HeapAlloc
0x18007b069  mov     rbx, rax
0x18007b06c  test    rax, rax
0x18007b06f  jnz     short loc_18007B08E
0x18007b071  mov     rcx, cs:g_hEventLogger; hObject
0x18007b078  call    cs:__imp_CloseHandle
0x18007b07e  mov     cs:g_hEventLogger, rbx
0x18007b085  mov     cs:g_pEventFire, rbx
0x18007b08c  jmp     short loc_18007B035
0x18007b08e  lea     rax, ??_7COle32DebugEventFire@@6B@; const COle32DebugEventFire::`vftable'
0x18007b095  mov     rcx, rbx; this
0x18007b098  mov     [rbx], rax
0x18007b09b  call    ?Initialize@CDebugEventFire@@QEAAJXZ; CDebugEventFire::Initialize(void)
0x18007b0a0  mov     rcx, [rbx]
0x18007b0a3  lea     r8, g_pEventFire
0x18007b0aa  lea     rdx, IID_ISystemDebugEventFire
0x18007b0b1  mov     rax, [rcx]
0x18007b0b4  mov     rcx, rbx
0x18007b0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0bc  mov     r9d, edi
0x18007b0bf  lea     r8, aComRuntimeD; "COM Runtime %d"
0x18007b0c6  mov     edx, 20h ; ' '; cchDest
0x18007b0cb  lea     rcx, [rsp+0C8h+sz]; pszDest
0x18007b0d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b0d5  test    eax, eax
0x18007b0d7  js      loc_18007B035
0x18007b0dd  mov     rcx, cs:g_pEventFire
0x18007b0e4  lea     r8, [rsp+0C8h+sz]
0x18007b0e9  lea     rdx, GUID_ComEventLogSession
0x18007b0f0  mov     rax, [rcx]
0x18007b0f3  mov     rax, [rax+18h]
0x18007b0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0fc  jmp     loc_18007B035
0x18007b101  mov     rcx, rax; hObject
0x18007b104  call    cs:__imp_CloseHandle
0x18007b10a  jmp     loc_18007B035
```
