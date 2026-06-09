# NamedPipeAdaptor::WriteMessage(unsigned __int64,void const *)

- ea: `0x14002e160`
- end: `0x14002e28b`
- name: `?WriteMessage@NamedPipeAdaptor@@UEAAJ_KPEBX@Z`
- size: `299`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *this, rsize_t, const void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002d9d`
- `0x140008188`
- `0x14002b864`
- `0x14002dca4`
- `0x14002dd04`
- `0x14002df68`
- `0x14002e160`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14002e1de`
- `msvcrt!memcpy_s` at `0x14002e1de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002e220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002e239`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002e220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002e239`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002e17d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002e17d`

## string_xrefs

- `0x14002e1bd`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002e1f2`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002e260`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::WriteMessage(NamedPipeAdaptor *this, rsize_t a2, const void *a3)
{
  RTL_SRWLOCK *v3; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  void *v9; // rdx
  int v11; // eax
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-48h]
  char *v14; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  if ( *((_DWORD *)this + 36) != 3 )
  {
    v7 = -2147019873;
    v8 = 197;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)v7,
      v13);
LABEL_8:
    ReleaseSRWLockExclusive(v3);
    return v7;
  }
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>((char *)this + 256, a2) )
  {
    v7 = -2147024882;
    v8 = 201;
    goto LABEL_5;
  }
  if ( memcpy_s(*((void *const *)this + 32), *((_QWORD *)this + 33) - *((_QWORD *)this + 32), a3, a2) )
  {
    v7 = -2147418113;
    LODWORD(v14) = *errno_0();
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCB,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)0x8000FFFFLL,
      (int)"memcpy_s failed (%d)",
      v14);
    goto LABEL_8;
  }
  wil::details::SetEvent(*((wil::details **)this + 44), v9);
  ReleaseSRWLockExclusive(v3);
  v11 = NamedPipeAdaptor::WaitForEvent((char *)this - 48, (char *)this + 360, 5000);
  v12 = v11;
  if ( v11 >= 0 )
    return *((unsigned int *)this + 92);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
    (const char *)(unsigned int)v11,
    v13);
  return v12;
}

```

## disassembly

```asm
0x14002e160  push    rbx
0x14002e162  push    rbp
0x14002e163  push    rsi
0x14002e164  push    rdi
0x14002e165  push    r14
0x14002e167  push    r15
0x14002e169  sub     rsp, 38h
0x14002e16d  lea     rdi, [rcx+8]
0x14002e171  mov     rbx, rcx
0x14002e174  mov     rcx, rdi; SRWLock
0x14002e177  mov     r15, r8
0x14002e17a  mov     rbp, rdx
0x14002e17d  call    cs:__imp_AcquireSRWLockExclusive
0x14002e183  cmp     dword ptr [rbx+90h], 3
0x14002e18a  jz      short loc_14002E198
0x14002e18c  mov     ebx, 8007139Fh
0x14002e191  mov     edx, 0C5h
0x14002e196  jmp     short loc_14002E1B8
0x14002e198  lea     r14, [rbx+100h]
0x14002e19f  mov     rdx, rbp
0x14002e1a2  mov     rcx, r14
0x14002e1a5  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x14002e1aa  test    al, al
0x14002e1ac  jnz     short loc_14002E1CE
0x14002e1ae  mov     ebx, 8007000Eh
0x14002e1b3  mov     edx, 0C9h; void *
0x14002e1b8  mov     rcx, [rsp+68h]; this
0x14002e1bd  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002e1c4  mov     r9d, ebx; char *
0x14002e1c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e1cc  jmp     short loc_14002E21D
0x14002e1ce  mov     rdx, [r14+8]
0x14002e1d2  mov     r9, rbp; SourceSize
0x14002e1d5  sub     rdx, [r14]; DestinationSize
0x14002e1d8  mov     r8, r15; Source
0x14002e1db  mov     rcx, [r14]; Destination
0x14002e1de  call    cs:__imp_memcpy_s
0x14002e1e4  test    eax, eax
0x14002e1e6  jz      short loc_14002E22A
0x14002e1e8  call    _errno_0
0x14002e1ed  mov     rcx, [rsp+68h]; this
0x14002e1f2  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002e1f9  mov     ebx, 8000FFFFh
0x14002e1fe  mov     edx, 0CBh; void *
0x14002e203  mov     r9d, ebx; char *
0x14002e206  mov     eax, [rax]
0x14002e208  mov     dword ptr [rsp+68h+var_40], eax; char *
0x14002e20c  lea     rax, aMemcpySFailedD; "memcpy_s failed (%d)"
0x14002e213  mov     qword ptr [rsp+68h+var_48], rax; int
0x14002e218  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14002e21d  mov     rcx, rdi; SRWLock
0x14002e220  call    cs:__imp_ReleaseSRWLockExclusive
0x14002e226  mov     eax, ebx
0x14002e228  jmp     short loc_14002E27E
0x14002e22a  mov     rcx, [rbx+160h]; this
0x14002e231  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002e236  mov     rcx, rdi; SRWLock
0x14002e239  call    cs:__imp_ReleaseSRWLockExclusive
0x14002e23f  lea     rdx, [rbx+168h]
0x14002e246  mov     r8d, 1388h
0x14002e24c  lea     rcx, [rbx-30h]
0x14002e250  call    ?WaitForEvent@NamedPipeAdaptor@@AEAAJAEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@K@Z
0x14002e255  mov     edi, eax
0x14002e257  test    eax, eax
0x14002e259  jns     short loc_14002E278
0x14002e25b  mov     rcx, [rsp+68h]; this
0x14002e260  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002e267  mov     r9d, eax; char *
0x14002e26a  mov     edx, 0D0h; void *
0x14002e26f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e274  mov     eax, edi
0x14002e276  jmp     short loc_14002E27E
0x14002e278  mov     eax, [rbx+170h]
0x14002e27e  add     rsp, 38h
0x14002e282  pop     r15
0x14002e284  pop     r14
0x14002e286  pop     rdi
0x14002e287  pop     rsi
0x14002e288  pop     rbp
0x14002e289  pop     rbx
0x14002e28a  retn
```
