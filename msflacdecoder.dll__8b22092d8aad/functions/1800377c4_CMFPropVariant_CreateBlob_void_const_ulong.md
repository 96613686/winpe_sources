# CMFPropVariant::CreateBlob(void const *,ulong)

- ea: `0x1800377c4`
- end: `0x1800378ef`
- name: `?CreateBlob@CMFPropVariant@@QEAAJPEBXK@Z`
- size: `299`
- prototype: `int(CMFPropVariant *__hidden this, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002513c`
- `0x180035148`

## callees

- `0x180016b0c`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x1800377c4`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800377e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800377e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037826`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037826`

## string_xrefs

- `0x1800377f3`: `CMFPropVariant::CreateBlob`
- `0x18003787d`: `CMFPropVariant::CreateBlob`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateBlob(CMFPropVariant *this, const void *a2, unsigned int a3)
{
  size_t v5; // rsi
  __int64 v6; // rdx
  void *v7; // rcx
  __int64 *v8; // rcx
  unsigned int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+60h] [rbp+18h] BYREF

  *(_WORD *)this = 65;
  v5 = a3;
  *((_QWORD *)this + 2) = CoTaskMemAlloc(a3);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CMFPropVariant::CreateBlob", 1805);
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    v9 = 0;
    memcpy_0(v7, a2, v5);
    *((_DWORD *)this + 2) = v5;
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateBlob", 1805, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v9;
}

```

## disassembly

```asm
0x1800377c4  mov     [rsp+arg_0], rbx
0x1800377c9  mov     [rsp+arg_8], rbp
0x1800377ce  push    rsi
0x1800377cf  push    rdi
0x1800377d0  push    r14
0x1800377d2  sub     rsp, 30h
0x1800377d6  mov     rdi, rcx
0x1800377d9  mov     word ptr [rcx], 41h ; 'A'
0x1800377de  mov     ecx, r8d; cb
0x1800377e1  mov     r14, rdx
0x1800377e4  mov     esi, r8d
0x1800377e7  call    cs:__imp_CoTaskMemAlloc
0x1800377ed  mov     r8d, 70Dh; int
0x1800377f3  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x1800377fa  lea     rcx, [rsp+48h+arg_10]; this
0x1800377ff  mov     [rdi+10h], rax
0x180037803  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037808  mov     rcx, [rdi+10h]; void *
0x18003780c  test    rcx, rcx
0x18003780f  jnz     loc_1800378C0
0x180037815  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003781c  mov     ebx, 8007000Eh
0x180037821  test    rcx, rcx
0x180037824  jnz     short loc_180037867
0x180037826  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003782c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037833  mov     rcx, rax
0x180037836  test    rax, rax
0x180037839  jz      short loc_180037859
0x18003783b  mov     rax, [rax]
0x18003783e  mov     edx, 7F0h
0x180037843  mov     rax, [rax+8]
0x180037847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003784c  test    eax, eax
0x18003784e  jz      short loc_180037859
0x180037850  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037857  jmp     short loc_180037867
0x180037859  lea     rcx, qword_18006EB20; this
0x180037860  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037867  cmp     byte ptr [rcx+8], 0
0x18003786b  jz      short loc_180037892
0x18003786d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037872  cmp     [rax+7CCh], ebx
0x180037878  jz      short loc_180037892
0x18003787a  mov     r9d, ebx; int
0x18003787d  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180037884  mov     r8d, 70Dh; int
0x18003788a  mov     rcx, rax; this
0x18003788d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037892  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037897  cmp     al, 1
0x180037899  jb      short loc_1800378D0
0x18003789b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800378a2  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800378a9  mov     edx, 79h ; 'y'
0x1800378ae  mov     [rsp+48h+var_28], ebx
0x1800378b2  mov     r9, rdi
0x1800378b5  mov     rcx, [rcx+10h]
0x1800378b9  call    WPP_SF_qd
0x1800378be  jmp     short loc_1800378D0
0x1800378c0  xor     ebx, ebx
0x1800378c2  mov     r8, rsi; Size
0x1800378c5  mov     rdx, r14; Src
0x1800378c8  call    memcpy_0
0x1800378cd  mov     [rdi+8], esi
0x1800378d0  lea     rcx, [rsp+48h+arg_10]; this
0x1800378d5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800378da  mov     rbp, [rsp+48h+arg_8]
0x1800378df  mov     eax, ebx
0x1800378e1  mov     rbx, [rsp+48h+arg_0]
0x1800378e6  add     rsp, 30h
0x1800378ea  pop     r14
0x1800378ec  pop     rdi
0x1800378ed  pop     rsi
0x1800378ee  retn
```
