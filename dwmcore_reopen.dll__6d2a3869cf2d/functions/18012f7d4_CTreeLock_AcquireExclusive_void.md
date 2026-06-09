# CTreeLock::AcquireExclusive(void)

- ea: `0x18012f7d4`
- end: `0x18012f885`
- name: `?AcquireExclusive@CTreeLock@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(CTreeLock *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001847c`
- `0x18012fe64`
- `0x18018476c`

## callees

- `0x18004fce4`
- `0x180050270`
- `0x1800516b0`
- `0x18012f7d4`
- `0x180202804`
- `0x180204120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012f7dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012f7dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18012f831`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18012f831`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18012f7f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18012f7f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f7e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f7e3`

## string_xrefs

- `0x18012f864`: `onecoreuap\windows\dwm\dwmcore\common\threadcontext.cpp`

## pseudocode

```c
void __fastcall CTreeLock::AcquireExclusive(RTL_SRWLOCK *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // ecx
  _DWORD *Value; // rbx
  CThreadContext *v5; // rax
  CThreadContext *v6; // rax
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  AcquireSRWLockExclusive(this);
  CurrentThreadId = GetCurrentThreadId();
  v3 = CThreadContext::s_dwTlsIndex;
  LODWORD(this[1].Ptr) = CurrentThreadId;
  Value = TlsGetValue(v3);
  if ( !Value )
  {
    v5 = (CThreadContext *)MIDL_user_allocate(0x1C0u);
    if ( !v5 || (v6 = CThreadContext::CThreadContext(v5), (Value = v6) == 0) )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\common\\threadcontext.cpp",
        (const char *)0x8007000ELL,
        v7);
      ModuleFailFastForHRESULT(-2147024882, retaddr);
    }
    TlsSetValue(CThreadContext::s_dwTlsIndex, v6);
  }
  ++Value[10];
}

```

## disassembly

```asm
0x18012f7d4  push    rbx
0x18012f7d6  sub     rsp, 30h
0x18012f7da  mov     rbx, rcx
0x18012f7dd  call    cs:__imp_AcquireSRWLockExclusive
0x18012f7e3  call    cs:__imp_GetCurrentThreadId
0x18012f7e9  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x18012f7ef  mov     [rbx+8], eax
0x18012f7f2  call    cs:__imp_TlsGetValue
0x18012f7f8  mov     rbx, rax
0x18012f7fb  test    rax, rax
0x18012f7fe  jz      short loc_18012F809
0x18012f800  inc     dword ptr [rbx+28h]
0x18012f803  add     rsp, 30h
0x18012f807  pop     rbx
0x18012f808  retn
0x18012f809  mov     ecx, 1C0h; size
0x18012f80e  call    MIDL_user_allocate
0x18012f813  test    rax, rax
0x18012f816  jz      short loc_18012F839
0x18012f818  mov     rcx, rax; this
0x18012f81b  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x18012f820  mov     rbx, rax
0x18012f823  test    rax, rax
0x18012f826  jz      short loc_18012F839
0x18012f828  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x18012f82e  mov     rdx, rax; lpTlsValue
0x18012f831  call    cs:__imp_TlsSetValue
0x18012f837  jmp     short loc_18012F800
0x18012f839  xor     edx, edx; int *
0x18012f83b  mov     [rsp+38h+var_10], 0; void *
0x18012f844  mov     ebx, 8007000Eh
0x18012f849  mov     [rsp+38h+var_18], 28h ; '('; int
0x18012f851  mov     r9d, ebx; int
0x18012f854  xor     r8d, r8d; unsigned int
0x18012f857  lea     ecx, [rdx+14h]; unsigned int
0x18012f85a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18012f85f  mov     rcx, [rsp+38h]; this
0x18012f864  lea     r8, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\dwmcore\\comm"...
0x18012f86b  mov     r9d, ebx; char *
0x18012f86e  mov     edx, 87h; void *
0x18012f873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f878  mov     rdx, [rsp+38h]; void *
0x18012f87d  mov     ecx, ebx; int
0x18012f87f  call    ModuleFailFastForHRESULT
```
