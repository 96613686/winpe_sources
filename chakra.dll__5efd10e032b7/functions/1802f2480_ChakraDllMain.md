# ChakraDllMain

- ea: `0x1802f2480`
- end: `0x1802f2574`
- name: `ChakraDllMain`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1802f245c`

## callees

- `0x1802f2480`
- `0x1802f257c`
- `0x1802f2738`
- `0x1803d4be8`
- `0x180423e9c`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1802f2517`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1802f2517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802f24fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802f24fe`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1802f24e2`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1802f24e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1802f24af`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1802f24af`

## pseudocode

```c
__int64 __fastcall ChakraDllMain(HMODULE a1, int a2, __int64 a3)
{
  switch ( a2 )
  {
    case 1:
      hProxyDll = a1;
      return AttachProcess();
    case 0:
      word_180740AE4 = DeleteAtom(word_180740AE4);
      if ( EtwTraceCore::s_registered )
      {
        EtwTraceCore::s_registered = 0;
        McGenEventUnregister_EventUnregister(&BERP_IE_Context);
        McGenEventUnregister_EventUnregister(&PROVIDER_JSCRIPT9_Context);
        McGenEventUnregister_EventUnregister(&PROVIDER_JSCRIPT9_INTERNAL_Context);
      }
      if ( !a3 )
        DetachProcess();
      return 1;
    case 2:
      TlsSetValue(ThreadContextTLSEntry::s_tlsSlot, 0);
      return 1;
    case 3:
      if ( TryEnterCriticalSection(&stru_18073EC08) )
      {
        ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread();
        LeaveCriticalSection(&stru_18073EC08);
      }
      return 1;
    default:
      return 0;
  }
}

```

## disassembly

```asm
0x1802f2480  mov     rax, rsp
0x1802f2483  mov     [rax+18h], r8
0x1802f2487  mov     [rax+10h], edx
0x1802f248a  mov     [rax+8], rcx
0x1802f248e  sub     rsp, 28h
0x1802f2492  mov     eax, edx
0x1802f2494  cmp     eax, 1
0x1802f2497  jz      short loc_1802F24C6
0x1802f2499  test    eax, eax
0x1802f249b  jz      short loc_1802F2510
0x1802f249d  sub     eax, 1
0x1802f24a0  jz      short loc_1802F24CD
0x1802f24a2  sub     eax, 1
0x1802f24a5  jnz     short loc_1802F24D6
0x1802f24a7  mov     ecx, cs:?s_tlsSlot@ThreadContextTLSEntry@@2IA; dwTlsIndex
0x1802f24ad  xor     edx, edx; lpTlsValue
0x1802f24af  call    cs:__imp_TlsSetValue
0x1802f24b6  nop     dword ptr [rax+rax+00h]
0x1802f24bb  mov     eax, 1
0x1802f24c0  add     rsp, 28h
0x1802f24c4  retn
0x1802f24c6  mov     cs:hProxyDll, rcx
0x1802f24cd  add     rsp, 28h
0x1802f24d1  jmp     AttachProcess
0x1802f24d6  cmp     eax, 1
0x1802f24d9  jnz     short loc_1802F250C
0x1802f24db  lea     rcx, stru_18073EC08; lpCriticalSection
0x1802f24e2  call    cs:__imp_TryEnterCriticalSection
0x1802f24e9  nop     dword ptr [rax+rax+00h]
0x1802f24ee  test    eax, eax
0x1802f24f0  jz      short loc_1802F24BB
0x1802f24f2  call    ?DestroyContextAndEntryForCurrentThread@ThreadBoundThreadContextManager@@SAXXZ; ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread(void)
0x1802f24f7  lea     rcx, stru_18073EC08; lpCriticalSection
0x1802f24fe  call    cs:__imp_LeaveCriticalSection
0x1802f2505  nop     dword ptr [rax+rax+00h]
0x1802f250a  jmp     short loc_1802F24BB
0x1802f250c  xor     eax, eax
0x1802f250e  jmp     short loc_1802F24C0
0x1802f2510  movzx   ecx, cs:word_180740AE4; nAtom
0x1802f2517  call    cs:__imp_DeleteAtom
0x1802f251e  nop     dword ptr [rax+rax+00h]
0x1802f2523  cmp     cs:?s_registered@EtwTraceCore@@2_NA, 0; bool EtwTraceCore::s_registered
0x1802f252a  mov     cs:word_180740AE4, ax
0x1802f2531  jz      short loc_1802F255E
0x1802f2533  lea     rcx, BERP_IE_Context
0x1802f253a  mov     cs:?s_registered@EtwTraceCore@@2_NA, 0; bool EtwTraceCore::s_registered
0x1802f2541  call    McGenEventUnregister_EventUnregister
0x1802f2546  lea     rcx, PROVIDER_JSCRIPT9_Context
0x1802f254d  call    McGenEventUnregister_EventUnregister
0x1802f2552  lea     rcx, PROVIDER_JSCRIPT9_INTERNAL_Context
0x1802f2559  call    McGenEventUnregister_EventUnregister
0x1802f255e  cmp     [rsp+28h+arg_10], 0
0x1802f2564  jnz     loc_1802F24BB
0x1802f256a  call    ?DetachProcess@@YAXXZ; DetachProcess(void)
0x1802f256f  jmp     loc_1802F24BB
```
