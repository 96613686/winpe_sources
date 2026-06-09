# CFLACMetadataWriter::GetMFMetadata(IMFPresentationDescriptor *,ulong,ulong,IMFMetadata * *)

- ea: `0x180031440`
- end: `0x180031687`
- name: `?GetMFMetadata@CFLACMetadataWriter@@UEAAJPEAUIMFPresentationDescriptor@@KKPEAPEAUIMFMetadata@@@Z`
- size: `583`
- prototype: `__int64 __usercall@<rax>(CFLACMetadataWriter *__hidden this@<rcx>, struct IMFPresentationDescriptor *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct IMFMetadata **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031440`
- `0x180031bdc`
- `0x180032770`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800315d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800315d2`

## string_xrefs

- `0x18003145e`: `CFLACMetadataWriter::GetMFMetadata`
- `0x1800314e6`: `CFLACMetadataWriter::GetMFMetadata`
- `0x180031582`: `CFLACMetadataWriter::GetMFMetadata`
- `0x18003162f`: `CFLACMetadataWriter::GetMFMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACMetadataWriter::GetMFMetadata(
        CFLACMetadataWriter *this,
        struct IMFPresentationDescriptor *a2,
        int a3,
        int a4,
        struct IMFMetadata **a5)
{
  __int64 v8; // rdx
  int Interface; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  char v22; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CFLACMetadataWriter::GetMFMetadata", 101);
  if ( a3 )
  {
    Interface = -1072873843;
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873843 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CFLACMetadataWriter::GetMFMetadata", 107, -1072873843);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 10;
LABEL_34:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        this,
        Interface);
    }
  }
  else if ( a4 )
  {
    Interface = -2147024809;
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v16, "CFLACMetadataWriter::GetMFMetadata", 112, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 11;
      goto LABEL_34;
    }
  }
  else
  {
    Interface = CFLACMetadataWriter::QueryInterface(this, &IID_IMFMetadata, (void **)a5);
    if ( Interface < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != Interface )
          CallStackContext::TraceFailure(v20, "CFLACMetadataWriter::GetMFMetadata", 115, Interface);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 12;
        goto LABEL_34;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180031440  mov     [rsp+arg_0], rbx
0x180031445  mov     [rsp+arg_8], rsi
0x18003144a  push    rdi
0x18003144b  sub     rsp, 30h
0x18003144f  mov     esi, r9d
0x180031452  mov     ebx, r8d
0x180031455  mov     rdi, rcx
0x180031458  mov     r8d, 65h ; 'e'; int
0x18003145e  lea     rdx, aCflacmetadataw_0; "CFLACMetadataWriter::GetMFMetadata"
0x180031465  lea     rcx, [rsp+38h+arg_10]; this
0x18003146a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003146f  nop
0x180031470  test    ebx, ebx
0x180031472  jz      loc_18003150C
0x180031478  mov     ebx, 0C00D3E8Dh
0x18003147d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031484  test    rcx, rcx
0x180031487  jnz     short loc_1800314CA
0x180031489  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003148f  mov     rcx, rax
0x180031492  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031499  test    rax, rax
0x18003149c  jz      short loc_1800314BC
0x18003149e  mov     rax, [rax]
0x1800314a1  mov     edx, 7F0h
0x1800314a6  mov     rax, [rax+8]
0x1800314aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314af  test    eax, eax
0x1800314b1  jz      short loc_1800314BC
0x1800314b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800314ba  jmp     short loc_1800314CA
0x1800314bc  lea     rcx, qword_18006EB20; this
0x1800314c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800314ca  cmp     byte ptr [rcx+8], 0
0x1800314ce  jz      short loc_1800314F5
0x1800314d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800314d5  cmp     [rax+7CCh], ebx
0x1800314db  jz      short loc_1800314F5
0x1800314dd  mov     r9d, ebx; int
0x1800314e0  mov     r8d, 6Bh ; 'k'; int
0x1800314e6  lea     rdx, aCflacmetadataw_0; "CFLACMetadataWriter::GetMFMetadata"
0x1800314ed  mov     rcx, rax; this
0x1800314f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800314f5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800314fa  cmp     al, 1
0x1800314fc  jb      loc_18003166B
0x180031502  mov     edx, 0Ah
0x180031507  jmp     loc_18003164C
0x18003150c  test    esi, esi
0x18003150e  jz      loc_1800315A8
0x180031514  mov     ebx, 80070057h
0x180031519  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031520  test    rcx, rcx
0x180031523  jnz     short loc_180031566
0x180031525  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003152b  mov     rcx, rax
0x18003152e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031535  test    rax, rax
0x180031538  jz      short loc_180031558
0x18003153a  mov     rax, [rax]
0x18003153d  mov     edx, 7F0h
0x180031542  mov     rax, [rax+8]
0x180031546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003154b  test    eax, eax
0x18003154d  jz      short loc_180031558
0x18003154f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031556  jmp     short loc_180031566
0x180031558  lea     rcx, qword_18006EB20; this
0x18003155f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031566  cmp     byte ptr [rcx+8], 0
0x18003156a  jz      short loc_180031591
0x18003156c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031571  cmp     [rax+7CCh], ebx
0x180031577  jz      short loc_180031591
0x180031579  mov     r9d, ebx; int
0x18003157c  mov     r8d, 70h ; 'p'; int
0x180031582  lea     rdx, aCflacmetadataw_0; "CFLACMetadataWriter::GetMFMetadata"
0x180031589  mov     rcx, rax; this
0x18003158c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031591  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031596  cmp     al, 1
0x180031598  jb      loc_18003166B
0x18003159e  mov     edx, 0Bh
0x1800315a3  jmp     loc_18003164C
0x1800315a8  mov     r8, [rsp+38h+arg_20]; void **
0x1800315ad  lea     rdx, IID_IMFMetadata; struct _GUID *
0x1800315b4  mov     rcx, rdi; this
0x1800315b7  call    ?QueryInterface@CFLACMetadataWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z; CFLACMetadataWriter::QueryInterface(_GUID const &,void * *)
0x1800315bc  mov     ebx, eax
0x1800315be  test    eax, eax
0x1800315c0  jns     loc_18003166B
0x1800315c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800315cd  test    rcx, rcx
0x1800315d0  jnz     short loc_180031613
0x1800315d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800315d8  mov     rcx, rax
0x1800315db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800315e2  test    rax, rax
0x1800315e5  jz      short loc_180031605
0x1800315e7  mov     rax, [rax]
0x1800315ea  mov     edx, 7F0h
0x1800315ef  mov     rax, [rax+8]
0x1800315f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315f8  test    eax, eax
0x1800315fa  jz      short loc_180031605
0x1800315fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031603  jmp     short loc_180031613
0x180031605  lea     rcx, qword_18006EB20; this
0x18003160c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031613  cmp     byte ptr [rcx+8], 0
0x180031617  jz      short loc_18003163E
0x180031619  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003161e  cmp     [rax+7CCh], ebx
0x180031624  jz      short loc_18003163E
0x180031626  mov     r9d, ebx; int
0x180031629  mov     r8d, 73h ; 's'; int
0x18003162f  lea     rdx, aCflacmetadataw_0; "CFLACMetadataWriter::GetMFMetadata"
0x180031636  mov     rcx, rax; this
0x180031639  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003163e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031643  cmp     al, 1
0x180031645  jb      short loc_18003166B
0x180031647  mov     edx, 0Ch
0x18003164c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031653  mov     [rsp+38h+var_18], ebx
0x180031657  mov     r9, rdi
0x18003165a  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180031661  mov     rcx, [rcx+10h]
0x180031665  call    WPP_SF_qd
0x18003166a  nop
0x18003166b  lea     rcx, [rsp+38h+arg_10]; this
0x180031670  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180031675  mov     eax, ebx
0x180031677  mov     rbx, [rsp+38h+arg_0]
0x18003167c  mov     rsi, [rsp+38h+arg_8]
0x180031681  add     rsp, 30h
0x180031685  pop     rdi
0x180031686  retn
```
