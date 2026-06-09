# CGhostThread::WorkerThreadProc(void)

- ea: `0x180008c10`
- end: `0x180008ca0`
- name: `?WorkerThreadProc@CGhostThread@@AEAAKXZ`
- size: `144`
- prototype: `unsigned int __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008cb0`

## callees

- `0x1800084c8`
- `0x1800087f0`
- `0x180008970`
- `0x180008b00`
- `0x180008c10`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008c2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c8d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetThreadDesktop` at `0x180008c20`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetThreadDesktop` at `0x180008c20`

## pseudocode

```c
__int64 __fastcall CGhostThread::WorkerThreadProc(CGhostThread *this)
{
  unsigned int v2; // esi
  unsigned int v3; // edi

  if ( SetThreadDesktop(*((HDESK *)this + 10)) && SetEvent(*((HANDLE *)this + 11)) )
  {
    v2 = CGhostThread::PumpGhostWindowMsgs(this);
    CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
    v3 = 4;
    if ( (unsigned int)CGhostThread::GetState(this) == 2 )
      v3 = 1;
    CGhostThread::CleanupAllGhosts(this, v3 == 4);
    *((_DWORD *)this + 26) = 0;
    CGhostThread::SetState(this, v3);
    CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  }
  else
  {
    return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x180008c10  push    rbx
0x180008c12  push    rbp
0x180008c13  push    rsi
0x180008c14  push    rdi
0x180008c15  sub     rsp, 28h
0x180008c19  mov     rbx, rcx
0x180008c1c  mov     rcx, [rcx+50h]; hDesktop
0x180008c20  call    cs:__imp_SetThreadDesktop
0x180008c26  test    eax, eax
0x180008c28  jz      short loc_180008C8D
0x180008c2a  mov     rcx, [rbx+58h]; hEvent
0x180008c2e  call    cs:__imp_SetEvent
0x180008c34  test    eax, eax
0x180008c36  jz      short loc_180008C8D
0x180008c38  mov     rcx, rbx; this
0x180008c3b  call    ?PumpGhostWindowMsgs@CGhostThread@@AEAAKXZ; CGhostThread::PumpGhostWindowMsgs(void)
0x180008c40  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008c44  mov     esi, eax
0x180008c46  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008c4b  mov     rcx, rbx
0x180008c4e  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008c53  mov     ecx, 4
0x180008c58  mov     edi, ecx
0x180008c5a  sub     eax, 2
0x180008c5d  jnz     short loc_180008C62
0x180008c5f  lea     edi, [rcx-3]
0x180008c62  xor     edx, edx
0x180008c64  cmp     edi, ecx
0x180008c66  mov     rcx, rbx; this
0x180008c69  setz    dl; int
0x180008c6c  call    ?CleanupAllGhosts@CGhostThread@@AEAAHH@Z; CGhostThread::CleanupAllGhosts(int)
0x180008c71  mov     edx, edi
0x180008c73  mov     dword ptr [rbx+68h], 0
0x180008c7a  mov     rcx, rbx
0x180008c7d  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x180008c82  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008c86  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008c8b  jmp     short loc_180008C95
0x180008c8d  call    cs:__imp_GetLastError
0x180008c93  mov     esi, eax
0x180008c95  mov     eax, esi
0x180008c97  add     rsp, 28h
0x180008c9b  pop     rdi
0x180008c9c  pop     rsi
0x180008c9d  pop     rbp
0x180008c9e  pop     rbx
0x180008c9f  retn
```
