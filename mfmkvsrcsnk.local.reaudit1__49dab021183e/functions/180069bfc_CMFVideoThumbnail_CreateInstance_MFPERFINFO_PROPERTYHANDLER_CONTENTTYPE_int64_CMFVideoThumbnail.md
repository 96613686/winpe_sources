# CMFVideoThumbnail::CreateInstance(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,CMFVideoThumbnail * *)

- ea: `0x180069bfc`
- end: `0x180069de8`
- name: `?CreateInstance@CMFVideoThumbnail@@SAJW4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAPEAV1@@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180055990`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180066d90`
- `0x180069bfc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069c44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069c44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d32`

## string_xrefs

- `0x180069c13`: `CMFVideoThumbnail::CreateInstance`
- `0x180069ca1`: `CMFVideoThumbnail::CreateInstance`
- `0x180069d8f`: `CMFVideoThumbnail::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateInstance(int a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  unsigned int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  void *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+48h] [rbp+10h] BYREF
  int v23; // [rsp+50h] [rbp+18h] BYREF

  v23 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CMFVideoThumbnail::CreateInstance", 120);
  if ( a3 )
  {
    v13 = operator new(0x198u);
    if ( v13 )
    {
      v17 = CMFVideoThumbnail::CMFVideoThumbnail((__int64)v13, a1, v15, (unsigned int *)&v23);
      *a3 = v17;
      if ( v17 )
      {
        v9 = v23;
        if ( v23 < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          *a3 = 0;
        }
        goto LABEL_28;
      }
    }
    else
    {
      *a3 = 0;
    }
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFVideoThumbnail::CreateInstance", 123, -2147024882);
    }
    if ( g_wppLevels )
    {
      v12 = 11;
      goto LABEL_27;
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v11, "CMFVideoThumbnail::CreateInstance", 120, -2147467261);
    }
    if ( g_wppLevels )
    {
      v12 = 10;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, 0, v9);
    }
  }
LABEL_28:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return v9;
}

```

## disassembly

```asm
0x180069bfc  mov     [rsp+arg_0], rbx
0x180069c01  push    rdi
0x180069c02  sub     rsp, 30h
0x180069c06  mov     rdi, r8
0x180069c09  mov     [rsp+38h+arg_10], 0
0x180069c11  mov     ebx, ecx
0x180069c13  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x180069c1a  mov     r8d, 78h ; 'x'; int
0x180069c20  lea     rcx, [rsp+38h+arg_8]; this
0x180069c25  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180069c2a  test    rdi, rdi
0x180069c2d  jnz     loc_180069CCD
0x180069c33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c3a  mov     ebx, 80004003h
0x180069c3f  test    rcx, rcx
0x180069c42  jnz     short loc_180069C8B
0x180069c44  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069c4b  nop     dword ptr [rax+rax+00h]
0x180069c50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c57  mov     rcx, rax
0x180069c5a  test    rax, rax
0x180069c5d  jz      short loc_180069C7D
0x180069c5f  mov     rax, [rax]
0x180069c62  mov     edx, 7F0h
0x180069c67  mov     rax, [rax+8]
0x180069c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c70  test    eax, eax
0x180069c72  jz      short loc_180069C7D
0x180069c74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c7b  jmp     short loc_180069C8B
0x180069c7d  lea     rcx, qword_1800DBF70; this
0x180069c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c8b  cmp     byte ptr [rcx+8], 0
0x180069c8f  jz      short loc_180069CB6
0x180069c91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069c96  cmp     [rax+7CCh], ebx
0x180069c9c  jz      short loc_180069CB6
0x180069c9e  mov     r9d, ebx; int
0x180069ca1  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x180069ca8  mov     r8d, 78h ; 'x'; int
0x180069cae  mov     rcx, rax; this
0x180069cb1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069cb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069cbd  jb      loc_180069DD0
0x180069cc3  mov     edx, 0Ah
0x180069cc8  jmp     loc_180069DB2
0x180069ccd  mov     ecx, 198h; Size
0x180069cd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069cd7  test    rax, rax
0x180069cda  jz      short loc_180069D1A
0x180069cdc  lea     r9, [rsp+38h+arg_10]
0x180069ce1  mov     edx, ebx
0x180069ce3  mov     rcx, rax
0x180069ce6  call    ??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z; CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)
0x180069ceb  mov     [rdi], rax
0x180069cee  mov     rcx, rax
0x180069cf1  test    rax, rax
0x180069cf4  jz      short loc_180069D21
0x180069cf6  mov     ebx, [rsp+38h+arg_10]
0x180069cfa  test    ebx, ebx
0x180069cfc  jns     loc_180069DD0
0x180069d02  mov     rax, [rax]
0x180069d05  mov     rax, [rax+10h]
0x180069d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d0e  mov     qword ptr [rdi], 0
0x180069d15  jmp     loc_180069DD0
0x180069d1a  mov     qword ptr [rdi], 0
0x180069d21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d28  mov     ebx, 8007000Eh
0x180069d2d  test    rcx, rcx
0x180069d30  jnz     short loc_180069D79
0x180069d32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069d39  nop     dword ptr [rax+rax+00h]
0x180069d3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d45  mov     rcx, rax
0x180069d48  test    rax, rax
0x180069d4b  jz      short loc_180069D6B
0x180069d4d  mov     rax, [rax]
0x180069d50  mov     edx, 7F0h
0x180069d55  mov     rax, [rax+8]
0x180069d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d5e  test    eax, eax
0x180069d60  jz      short loc_180069D6B
0x180069d62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d69  jmp     short loc_180069D79
0x180069d6b  lea     rcx, qword_1800DBF70; this
0x180069d72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d79  cmp     byte ptr [rcx+8], 0
0x180069d7d  jz      short loc_180069DA4
0x180069d7f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069d84  cmp     [rax+7CCh], ebx
0x180069d8a  jz      short loc_180069DA4
0x180069d8c  mov     r9d, ebx; int
0x180069d8f  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x180069d96  mov     r8d, 7Bh ; '{'; int
0x180069d9c  mov     rcx, rax; this
0x180069d9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069da4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069dab  jb      short loc_180069DD0
0x180069dad  mov     edx, 0Bh
0x180069db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180069db9  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180069dc0  xor     r9d, r9d
0x180069dc3  mov     [rsp+38h+var_18], ebx
0x180069dc7  mov     rcx, [rcx+10h]
0x180069dcb  call    WPP_SF_qD
0x180069dd0  lea     rcx, [rsp+38h+arg_8]; this
0x180069dd5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180069dda  mov     eax, ebx
0x180069ddc  mov     rbx, [rsp+38h+arg_0]
0x180069de1  add     rsp, 30h
0x180069de5  pop     rdi
0x180069de6  retn
```
