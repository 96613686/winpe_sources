# CMFPropVariant::CreateBlob(void const *,ulong)

- ea: `0x180076a94`
- end: `0x180076bcc`
- name: `?CreateBlob@CMFPropVariant@@QEAAJPEBXK@Z`
- size: `312`
- prototype: `int(CMFPropVariant *__hidden this, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800748fc`

## callees

- `0x180003705`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180076a94`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076ab7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076afc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076afc`

## string_xrefs

- `0x180076ac9`: `CMFPropVariant::CreateBlob`
- `0x180076b59`: `CMFPropVariant::CreateBlob`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateBlob(CMFPropVariant *this, const void *a2, unsigned int a3)
{
  size_t v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  void *v9; // rcx
  __int64 *v10; // rcx
  unsigned int v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v15; // [rsp+60h] [rbp+18h] BYREF

  *(_WORD *)this = 65;
  v5 = a3;
  *((_QWORD *)this + 2) = CoTaskMemAlloc(a3);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v15, "CMFPropVariant::CreateBlob", 1805);
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    v11 = 0;
    memcpy_0(v9, a2, v5);
    *((_DWORD *)this + 2) = v5;
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateBlob", 1805, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  return v11;
}

```

## disassembly

```asm
0x180076a94  mov     [rsp+arg_0], rbx
0x180076a99  mov     [rsp+arg_8], rbp
0x180076a9e  push    rsi
0x180076a9f  push    rdi
0x180076aa0  push    r14
0x180076aa2  sub     rsp, 30h
0x180076aa6  mov     rdi, rcx
0x180076aa9  mov     word ptr [rcx], 41h ; 'A'
0x180076aae  mov     ecx, r8d; cb
0x180076ab1  mov     r14, rdx
0x180076ab4  mov     esi, r8d
0x180076ab7  call    cs:__imp_CoTaskMemAlloc
0x180076abe  nop     dword ptr [rax+rax+00h]
0x180076ac3  mov     r8d, 70Dh; int
0x180076ac9  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180076ad0  lea     rcx, [rsp+48h+arg_10]; this
0x180076ad5  mov     [rdi+10h], rax
0x180076ad9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076ade  mov     rcx, [rdi+10h]; void *
0x180076ae2  test    rcx, rcx
0x180076ae5  jnz     loc_180076B9C
0x180076aeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076af2  mov     ebx, 8007000Eh
0x180076af7  test    rcx, rcx
0x180076afa  jnz     short loc_180076B43
0x180076afc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076b03  nop     dword ptr [rax+rax+00h]
0x180076b08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076b0f  mov     rcx, rax
0x180076b12  test    rax, rax
0x180076b15  jz      short loc_180076B35
0x180076b17  mov     rax, [rax]
0x180076b1a  mov     edx, 7F0h
0x180076b1f  mov     rax, [rax+8]
0x180076b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b28  test    eax, eax
0x180076b2a  jz      short loc_180076B35
0x180076b2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076b33  jmp     short loc_180076B43
0x180076b35  lea     rcx, qword_1800DBF70; this
0x180076b3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076b43  cmp     byte ptr [rcx+8], 0
0x180076b47  jz      short loc_180076B6E
0x180076b49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076b4e  cmp     [rax+7CCh], ebx
0x180076b54  jz      short loc_180076B6E
0x180076b56  mov     r9d, ebx; int
0x180076b59  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180076b60  mov     r8d, 70Dh; int
0x180076b66  mov     rcx, rax; this
0x180076b69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076b6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076b75  jb      short loc_180076BAC
0x180076b77  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b7e  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180076b85  mov     edx, 79h ; 'y'
0x180076b8a  mov     [rsp+48h+var_28], ebx
0x180076b8e  mov     r9, rdi
0x180076b91  mov     rcx, [rcx+10h]
0x180076b95  call    WPP_SF_qD
0x180076b9a  jmp     short loc_180076BAC
0x180076b9c  xor     ebx, ebx
0x180076b9e  mov     r8, rsi; Size
0x180076ba1  mov     rdx, r14; Src
0x180076ba4  call    memcpy_0
0x180076ba9  mov     [rdi+8], esi
0x180076bac  lea     rcx, [rsp+48h+arg_10]; this
0x180076bb1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180076bb6  mov     rbp, [rsp+48h+arg_8]
0x180076bbb  mov     eax, ebx
0x180076bbd  mov     rbx, [rsp+48h+arg_0]
0x180076bc2  add     rsp, 30h
0x180076bc6  pop     r14
0x180076bc8  pop     rdi
0x180076bc9  pop     rsi
0x180076bca  retn
```
