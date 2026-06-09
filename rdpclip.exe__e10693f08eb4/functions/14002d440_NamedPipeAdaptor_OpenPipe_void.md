# NamedPipeAdaptor::OpenPipe(void)

- ea: `0x14002d440`
- end: `0x14002d52e`
- name: `?OpenPipe@NamedPipeAdaptor@@UEAAJXZ`
- size: `238`
- prototype: `int(NamedPipeAdaptor *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140008188`
- `0x14002d440`
- `0x14002dd04`
- `0x14002df68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d489`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d4a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d489`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d4a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d459`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d459`

## string_xrefs

- `0x14002d46d`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d4dc`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d503`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::OpenPipe(NamedPipeAdaptor *this)
{
  RTL_SRWLOCK *v1; // rdi
  unsigned int v3; // ebx
  void *v5; // rdx
  int v6; // eax
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  if ( *((_DWORD *)this + 36) != 1 )
  {
    v3 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)0x8007139FLL,
      v8);
    ReleaseSRWLockExclusive(v1);
    return v3;
  }
  *((_DWORD *)this + 36) = 2;
  ReleaseSRWLockExclusive(v1);
  wil::details::SetEvent(*((wil::details **)this + 41), v5);
  if ( !*((_DWORD *)this + 4) )
  {
    v6 = NamedPipeAdaptor::WaitForEvent((char *)this - 48, (char *)this + 336, 30000);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)(unsigned int)v6,
        v8);
      return v7;
    }
    v3 = *((_DWORD *)this + 86);
    if ( (v3 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)v3,
        v8);
      return v3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002d440  mov     [rsp+arg_0], rbx
0x14002d445  mov     [rsp+arg_8], rsi
0x14002d44a  push    rdi; int
0x14002d44b  sub     rsp, 20h
0x14002d44f  lea     rdi, [rcx+8]
0x14002d453  mov     rbx, rcx
0x14002d456  mov     rcx, rdi; SRWLock
0x14002d459  call    cs:__imp_AcquireSRWLockExclusive
0x14002d45f  cmp     dword ptr [rbx+90h], 1
0x14002d466  jz      short loc_14002D496
0x14002d468  mov     rcx, [rsp+28h]; this
0x14002d46d  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d474  mov     ebx, 8007139Fh
0x14002d479  mov     edx, 0ACh; void *
0x14002d47e  mov     r9d, ebx; char *
0x14002d481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d486  mov     rcx, rdi; SRWLock
0x14002d489  call    cs:__imp_ReleaseSRWLockExclusive
0x14002d48f  mov     eax, ebx
0x14002d491  jmp     loc_14002D51E
0x14002d496  mov     rcx, rdi; SRWLock
0x14002d499  mov     dword ptr [rbx+90h], 2
0x14002d4a3  call    cs:__imp_ReleaseSRWLockExclusive
0x14002d4a9  mov     rcx, [rbx+148h]; this
0x14002d4b0  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002d4b5  cmp     dword ptr [rbx+10h], 0
0x14002d4b9  jnz     short loc_14002D51C
0x14002d4bb  lea     rdx, [rbx+150h]
0x14002d4c2  mov     r8d, 7530h
0x14002d4c8  lea     rcx, [rbx-30h]
0x14002d4cc  call    ?WaitForEvent@NamedPipeAdaptor@@AEAAJAEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@K@Z
0x14002d4d1  mov     edi, eax
0x14002d4d3  test    eax, eax
0x14002d4d5  jns     short loc_14002D4F4
0x14002d4d7  mov     rcx, [rsp+28h]; this
0x14002d4dc  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d4e3  mov     r9d, eax; char *
0x14002d4e6  mov     edx, 0B6h; void *
0x14002d4eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d4f0  mov     eax, edi
0x14002d4f2  jmp     short loc_14002D51E
0x14002d4f4  mov     ebx, [rbx+158h]
0x14002d4fa  test    ebx, ebx
0x14002d4fc  jns     short loc_14002D51C
0x14002d4fe  mov     rcx, [rsp+28h]; this
0x14002d503  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d50a  mov     r9d, ebx; char *
0x14002d50d  mov     edx, 0B7h; void *
0x14002d512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d517  jmp     loc_14002D48F
0x14002d51c  xor     eax, eax
0x14002d51e  mov     rbx, [rsp+28h+arg_0]
0x14002d523  mov     rsi, [rsp+28h+arg_8]
0x14002d528  add     rsp, 20h
0x14002d52c  pop     rdi
0x14002d52d  retn
```
