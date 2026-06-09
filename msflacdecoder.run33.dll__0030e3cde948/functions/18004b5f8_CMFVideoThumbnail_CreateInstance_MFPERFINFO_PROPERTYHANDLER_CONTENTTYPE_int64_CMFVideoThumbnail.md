# CMFVideoThumbnail::CreateInstance(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,CMFVideoThumbnail * *)

- ea: `0x18004b5f8`
- end: `0x18004b7d7`
- name: `?CreateInstance@CMFVideoThumbnail@@SAJW4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAPEAV1@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18003bfb0`

## callees

- `0x1800018a4`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048950`
- `0x18004b5f8`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b728`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b728`

## string_xrefs

- `0x18004b60f`: `CMFVideoThumbnail::CreateInstance`
- `0x18004b697`: `CMFVideoThumbnail::CreateInstance`
- `0x18004b77f`: `CMFVideoThumbnail::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateInstance(int a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rdx
  __int64 *v6; // rcx
  unsigned int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v19; // [rsp+48h] [rbp+10h] BYREF
  int v20; // [rsp+50h] [rbp+18h] BYREF

  v20 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v19, "CMFVideoThumbnail::CreateInstance", 120);
  if ( a3 )
  {
    v11 = operator new(0x198u);
    if ( v11 )
    {
      v14 = CMFVideoThumbnail::CMFVideoThumbnail((__int64)v11, a1, v13, (unsigned int *)&v20);
      *a3 = v14;
      if ( v14 )
      {
        v7 = v20;
        if ( v20 < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          *a3 = 0;
        }
        goto LABEL_28;
      }
    }
    else
    {
      *a3 = 0;
    }
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFVideoThumbnail::CreateInstance", 123, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 11;
      goto LABEL_27;
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v9 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v9, "CMFVideoThumbnail::CreateInstance", 120, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 10;
LABEL_27:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, 0, v7);
    }
  }
LABEL_28:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
  return v7;
}

```

## disassembly

```asm
0x18004b5f8  mov     [rsp+arg_0], rbx
0x18004b5fd  push    rdi
0x18004b5fe  sub     rsp, 30h
0x18004b602  mov     rdi, r8
0x18004b605  mov     [rsp+38h+arg_10], 0
0x18004b60d  mov     ebx, ecx
0x18004b60f  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x18004b616  mov     r8d, 78h ; 'x'; int
0x18004b61c  lea     rcx, [rsp+38h+arg_8]; this
0x18004b621  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b626  test    rdi, rdi
0x18004b629  jnz     loc_18004B6C3
0x18004b62f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b636  mov     ebx, 80004003h
0x18004b63b  test    rcx, rcx
0x18004b63e  jnz     short loc_18004B681
0x18004b640  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b646  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b64d  mov     rcx, rax
0x18004b650  test    rax, rax
0x18004b653  jz      short loc_18004B673
0x18004b655  mov     rax, [rax]
0x18004b658  mov     edx, 7F0h
0x18004b65d  mov     rax, [rax+8]
0x18004b661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b666  test    eax, eax
0x18004b668  jz      short loc_18004B673
0x18004b66a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b671  jmp     short loc_18004B681
0x18004b673  lea     rcx, qword_18006EB20; this
0x18004b67a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b681  cmp     byte ptr [rcx+8], 0
0x18004b685  jz      short loc_18004B6AC
0x18004b687  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b68c  cmp     [rax+7CCh], ebx
0x18004b692  jz      short loc_18004B6AC
0x18004b694  mov     r9d, ebx; int
0x18004b697  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x18004b69e  mov     r8d, 78h ; 'x'; int
0x18004b6a4  mov     rcx, rax; this
0x18004b6a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b6ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b6b1  cmp     al, 1
0x18004b6b3  jb      loc_18004B7C0
0x18004b6b9  mov     edx, 0Ah
0x18004b6be  jmp     loc_18004B7A2
0x18004b6c3  mov     ecx, 198h; Size
0x18004b6c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b6cd  test    rax, rax
0x18004b6d0  jz      short loc_18004B710
0x18004b6d2  lea     r9, [rsp+38h+arg_10]
0x18004b6d7  mov     edx, ebx
0x18004b6d9  mov     rcx, rax
0x18004b6dc  call    ??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z; CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)
0x18004b6e1  mov     [rdi], rax
0x18004b6e4  mov     rcx, rax
0x18004b6e7  test    rax, rax
0x18004b6ea  jz      short loc_18004B717
0x18004b6ec  mov     ebx, [rsp+38h+arg_10]
0x18004b6f0  test    ebx, ebx
0x18004b6f2  jns     loc_18004B7C0
0x18004b6f8  mov     rax, [rax]
0x18004b6fb  mov     rax, [rax+10h]
0x18004b6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b704  mov     qword ptr [rdi], 0
0x18004b70b  jmp     loc_18004B7C0
0x18004b710  mov     qword ptr [rdi], 0
0x18004b717  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b71e  mov     ebx, 8007000Eh
0x18004b723  test    rcx, rcx
0x18004b726  jnz     short loc_18004B769
0x18004b728  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b72e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b735  mov     rcx, rax
0x18004b738  test    rax, rax
0x18004b73b  jz      short loc_18004B75B
0x18004b73d  mov     rax, [rax]
0x18004b740  mov     edx, 7F0h
0x18004b745  mov     rax, [rax+8]
0x18004b749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b74e  test    eax, eax
0x18004b750  jz      short loc_18004B75B
0x18004b752  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b759  jmp     short loc_18004B769
0x18004b75b  lea     rcx, qword_18006EB20; this
0x18004b762  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b769  cmp     byte ptr [rcx+8], 0
0x18004b76d  jz      short loc_18004B794
0x18004b76f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b774  cmp     [rax+7CCh], ebx
0x18004b77a  jz      short loc_18004B794
0x18004b77c  mov     r9d, ebx; int
0x18004b77f  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x18004b786  mov     r8d, 7Bh ; '{'; int
0x18004b78c  mov     rcx, rax; this
0x18004b78f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b794  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b799  cmp     al, 1
0x18004b79b  jb      short loc_18004B7C0
0x18004b79d  mov     edx, 0Bh
0x18004b7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7a9  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004b7b0  xor     r9d, r9d
0x18004b7b3  mov     [rsp+38h+var_18], ebx
0x18004b7b7  mov     rcx, [rcx+10h]
0x18004b7bb  call    WPP_SF_qd
0x18004b7c0  lea     rcx, [rsp+38h+arg_8]; this
0x18004b7c5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004b7ca  mov     eax, ebx
0x18004b7cc  mov     rbx, [rsp+38h+arg_0]
0x18004b7d1  add     rsp, 30h
0x18004b7d5  pop     rdi
0x18004b7d6  retn
```
