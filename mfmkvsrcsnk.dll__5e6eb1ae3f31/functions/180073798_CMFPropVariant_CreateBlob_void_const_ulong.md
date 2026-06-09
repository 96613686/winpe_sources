# CMFPropVariant::CreateBlob(void const *,ulong)

- ea: `0x180073798`
- end: `0x1800738c3`
- name: `?CreateBlob@CMFPropVariant@@QEAAJPEBXK@Z`
- size: `299`
- prototype: `int(CMFPropVariant *__hidden this, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071710`

## callees

- `0x1800036c5`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180073798`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800737bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800737bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800737fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800737fa`

## string_xrefs

- `0x1800737c7`: `CMFPropVariant::CreateBlob`
- `0x180073851`: `CMFPropVariant::CreateBlob`

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
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180073798  mov     [rsp+arg_0], rbx
0x18007379d  mov     [rsp+arg_8], rbp
0x1800737a2  push    rsi
0x1800737a3  push    rdi
0x1800737a4  push    r14
0x1800737a6  sub     rsp, 30h
0x1800737aa  mov     rdi, rcx
0x1800737ad  mov     word ptr [rcx], 41h ; 'A'
0x1800737b2  mov     ecx, r8d; cb
0x1800737b5  mov     r14, rdx
0x1800737b8  mov     esi, r8d
0x1800737bb  call    cs:__imp_CoTaskMemAlloc
0x1800737c1  mov     r8d, 70Dh; int
0x1800737c7  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x1800737ce  lea     rcx, [rsp+48h+arg_10]; this
0x1800737d3  mov     [rdi+10h], rax
0x1800737d7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800737dc  mov     rcx, [rdi+10h]; void *
0x1800737e0  test    rcx, rcx
0x1800737e3  jnz     loc_180073894
0x1800737e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800737f0  mov     ebx, 8007000Eh
0x1800737f5  test    rcx, rcx
0x1800737f8  jnz     short loc_18007383B
0x1800737fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073800  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073807  mov     rcx, rax
0x18007380a  test    rax, rax
0x18007380d  jz      short loc_18007382D
0x18007380f  mov     rax, [rax]
0x180073812  mov     edx, 7F0h
0x180073817  mov     rax, [rax+8]
0x18007381b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073820  test    eax, eax
0x180073822  jz      short loc_18007382D
0x180073824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007382b  jmp     short loc_18007383B
0x18007382d  lea     rcx, qword_1800D6F70; this
0x180073834  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007383b  cmp     byte ptr [rcx+8], 0
0x18007383f  jz      short loc_180073866
0x180073841  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073846  cmp     [rax+7CCh], ebx
0x18007384c  jz      short loc_180073866
0x18007384e  mov     r9d, ebx; int
0x180073851  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180073858  mov     r8d, 70Dh; int
0x18007385e  mov     rcx, rax; this
0x180073861  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073866  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007386d  jb      short loc_1800738A4
0x18007386f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073876  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18007387d  mov     edx, 79h ; 'y'
0x180073882  mov     [rsp+48h+var_28], ebx
0x180073886  mov     r9, rdi
0x180073889  mov     rcx, [rcx+10h]
0x18007388d  call    WPP_SF_qD
0x180073892  jmp     short loc_1800738A4
0x180073894  xor     ebx, ebx
0x180073896  mov     r8, rsi; Size
0x180073899  mov     rdx, r14; Src
0x18007389c  call    memcpy_0
0x1800738a1  mov     [rdi+8], esi
0x1800738a4  lea     rcx, [rsp+48h+arg_10]; this
0x1800738a9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800738ae  mov     rbp, [rsp+48h+arg_8]
0x1800738b3  mov     eax, ebx
0x1800738b5  mov     rbx, [rsp+48h+arg_0]
0x1800738ba  add     rsp, 30h
0x1800738be  pop     r14
0x1800738c0  pop     rdi
0x1800738c1  pop     rsi
0x1800738c2  retn
```
