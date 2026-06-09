# CHTTPMailTransport::CHTTPMailTransport(void)

- ea: `0x18009d5bc`
- end: `0x18009d6e3`
- name: `??0CHTTPMailTransport@@QEAA@XZ`
- size: `295`
- prototype: `CHTTPMailTransport *__fastcall(CHTTPMailTransport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002b870`

## callees

- `0x18009d5bc`
- `0x1800cc9ba`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009d6cf`
- `KERNEL32!CloseHandle` at `0x18009d6cf`
- `KERNEL32!InitializeCriticalSection` at `0x18009d64a`
- `KERNEL32!InitializeCriticalSection` at `0x18009d64a`
- `KERNEL32!CreateThread` at `0x18009d6c1`
- `KERNEL32!CreateThread` at `0x18009d6c1`
- `KERNEL32!CreateEventA` at `0x18009d69b`
- `KERNEL32!CreateEventA` at `0x18009d69b`

## pseudocode

```c
CHTTPMailTransport *__fastcall CHTTPMailTransport::CHTTPMailTransport(CHTTPMailTransport *this)
{
  HANDLE v2; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  *((_QWORD *)this + 3) = 1;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &CHTTPMailTransport::`vftable'{for `IHTTPMailTransportW'};
  *((_DWORD *)this + 10) = 8;
  *((_QWORD *)this + 1) = &CHTTPMailTransport::`vftable'{for `IXMLNodeFactory'};
  *((_QWORD *)this + 2) = &CHTTPMailTransport::`vftable'{for `IHTTPMailTransport2'};
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 250) = 0;
  *((_WORD *)this + 1004) = 0;
  *((_QWORD *)this + 263) = 0;
  _InterlockedIncrement(&g_cRef);
  ThreadId = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  memset_0((char *)this + 696, 0, 0x518u);
  memset_0((char *)this + 168, 0, 0x210u);
  memset_0((char *)this + 2016, 0, 0x58u);
  *((_DWORD *)this + 146) = 0;
  *((_QWORD *)this + 13) = CreateEventA(0, 1, 0, 0);
  v2 = CreateThread(0, 0, CHTTPMailTransport::IOThreadFuncProxy, this, 0, &ThreadId);
  if ( v2 )
    CloseHandle(v2);
  return this;
}

```

## disassembly

```asm
0x18009d5bc  mov     [rsp+arg_8], rbx
0x18009d5c1  push    rsi
0x18009d5c2  sub     rsp, 30h
0x18009d5c6  xor     esi, esi
0x18009d5c8  mov     qword ptr [rcx+18h], 1
0x18009d5d0  lea     rax, ??_7CHTTPMailTransport@@6BIHTTPMailTransportW@@@; const CHTTPMailTransport::`vftable'{for `IHTTPMailTransportW'}
0x18009d5d7  mov     [rcx+20h], rsi
0x18009d5db  mov     [rcx], rax
0x18009d5de  mov     rbx, rcx
0x18009d5e1  lea     rax, ??_7CHTTPMailTransport@@6BIXMLNodeFactory@@@; const CHTTPMailTransport::`vftable'{for `IXMLNodeFactory'}
0x18009d5e8  mov     dword ptr [rcx+28h], 8
0x18009d5ef  mov     [rcx+8], rax
0x18009d5f3  lea     rax, ??_7CHTTPMailTransport@@6BIHTTPMailTransport2@@@; const CHTTPMailTransport::`vftable'{for `IHTTPMailTransport2'}
0x18009d5fa  mov     [rcx+10h], rax
0x18009d5fe  mov     [rcx+30h], rsi
0x18009d602  mov     [rcx+38h], rsi
0x18009d606  mov     [rcx+40h], rsi
0x18009d60a  mov     [rcx+48h], rsi
0x18009d60e  mov     [rcx+50h], rsi
0x18009d612  mov     [rcx+58h], rsi
0x18009d616  mov     [rcx+60h], rsi
0x18009d61a  mov     [rcx+68h], rsi
0x18009d61e  mov     [rcx+70h], rsi
0x18009d622  mov     [rcx+78h], rsi
0x18009d626  mov     [rcx+7D0h], rsi
0x18009d62d  mov     [rcx+7D8h], si
0x18009d634  mov     [rcx+838h], rsi
0x18009d63b  lock inc cs:?g_cRef@@3JA; long g_cRef
0x18009d642  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18009d646  mov     [rsp+38h+ThreadId], esi
0x18009d64a  call    cs:__imp_InitializeCriticalSection
0x18009d650  lea     rcx, [rbx+2B8h]; void *
0x18009d657  xor     edx, edx; Val
0x18009d659  mov     r8d, 518h; Size
0x18009d65f  call    memset_0
0x18009d664  lea     rcx, [rbx+0A8h]; void *
0x18009d66b  xor     edx, edx; Val
0x18009d66d  mov     r8d, 210h; Size
0x18009d673  call    memset_0
0x18009d678  lea     rcx, [rbx+7E0h]; void *
0x18009d67f  xor     edx, edx; Val
0x18009d681  lea     r8d, [rsi+58h]; Size
0x18009d685  call    memset_0
0x18009d68a  xor     r9d, r9d; lpName
0x18009d68d  mov     [rbx+248h], esi
0x18009d693  xor     r8d, r8d; bInitialState
0x18009d696  lea     edx, [rsi+1]; bManualReset
0x18009d699  xor     ecx, ecx; lpEventAttributes
0x18009d69b  call    cs:__imp_CreateEventA
0x18009d6a1  mov     [rbx+68h], rax
0x18009d6a5  mov     r9, rbx; lpParameter
0x18009d6a8  lea     r8, ?IOThreadFuncProxy@CHTTPMailTransport@@CAKPEAX@Z; lpStartAddress
0x18009d6af  xor     edx, edx; dwStackSize
0x18009d6b1  lea     rax, [rsp+38h+ThreadId]
0x18009d6b6  xor     ecx, ecx; lpThreadAttributes
0x18009d6b8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18009d6bd  mov     [rsp+38h+dwCreationFlags], esi; dwCreationFlags
0x18009d6c1  call    cs:__imp_CreateThread
0x18009d6c7  test    rax, rax
0x18009d6ca  jz      short loc_18009D6D5
0x18009d6cc  mov     rcx, rax; hObject
0x18009d6cf  call    cs:__imp_CloseHandle
0x18009d6d5  mov     rax, rbx
0x18009d6d8  mov     rbx, [rsp+38h+arg_8]
0x18009d6dd  add     rsp, 30h
0x18009d6e1  pop     rsi
0x18009d6e2  retn
```
