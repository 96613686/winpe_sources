# CMFVideoThumbnail::CreateInstance(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,CMFVideoThumbnail * *)

- ea: `0x180066fe0`
- end: `0x1800671bf`
- name: `?CreateInstance@CMFVideoThumbnail@@SAJW4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAPEAV1@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800535e0`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180064274`
- `0x180066fe0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067028`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067110`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067028`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067110`

## string_xrefs

- `0x180066ff7`: `CMFVideoThumbnail::CreateInstance`
- `0x18006707f`: `CMFVideoThumbnail::CreateInstance`
- `0x180067167`: `CMFVideoThumbnail::CreateInstance`

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
        v18 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180066fe0  mov     [rsp+arg_0], rbx
0x180066fe5  push    rdi
0x180066fe6  sub     rsp, 30h
0x180066fea  mov     rdi, r8
0x180066fed  mov     [rsp+38h+arg_10], 0
0x180066ff5  mov     ebx, ecx
0x180066ff7  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x180066ffe  mov     r8d, 78h ; 'x'; int
0x180067004  lea     rcx, [rsp+38h+arg_8]; this
0x180067009  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006700e  test    rdi, rdi
0x180067011  jnz     loc_1800670AB
0x180067017  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006701e  mov     ebx, 80004003h
0x180067023  test    rcx, rcx
0x180067026  jnz     short loc_180067069
0x180067028  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006702e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067035  mov     rcx, rax
0x180067038  test    rax, rax
0x18006703b  jz      short loc_18006705B
0x18006703d  mov     rax, [rax]
0x180067040  mov     edx, 7F0h
0x180067045  mov     rax, [rax+8]
0x180067049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006704e  test    eax, eax
0x180067050  jz      short loc_18006705B
0x180067052  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067059  jmp     short loc_180067069
0x18006705b  lea     rcx, qword_1800D6F70; this
0x180067062  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067069  cmp     byte ptr [rcx+8], 0
0x18006706d  jz      short loc_180067094
0x18006706f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067074  cmp     [rax+7CCh], ebx
0x18006707a  jz      short loc_180067094
0x18006707c  mov     r9d, ebx; int
0x18006707f  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x180067086  mov     r8d, 78h ; 'x'; int
0x18006708c  mov     rcx, rax; this
0x18006708f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067094  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006709b  jb      loc_1800671A8
0x1800670a1  mov     edx, 0Ah
0x1800670a6  jmp     loc_18006718A
0x1800670ab  mov     ecx, 198h; Size
0x1800670b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800670b5  test    rax, rax
0x1800670b8  jz      short loc_1800670F8
0x1800670ba  lea     r9, [rsp+38h+arg_10]
0x1800670bf  mov     edx, ebx
0x1800670c1  mov     rcx, rax
0x1800670c4  call    ??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z; CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)
0x1800670c9  mov     [rdi], rax
0x1800670cc  mov     rcx, rax
0x1800670cf  test    rax, rax
0x1800670d2  jz      short loc_1800670FF
0x1800670d4  mov     ebx, [rsp+38h+arg_10]
0x1800670d8  test    ebx, ebx
0x1800670da  jns     loc_1800671A8
0x1800670e0  mov     rax, [rax]
0x1800670e3  mov     rax, [rax+10h]
0x1800670e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670ec  mov     qword ptr [rdi], 0
0x1800670f3  jmp     loc_1800671A8
0x1800670f8  mov     qword ptr [rdi], 0
0x1800670ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067106  mov     ebx, 8007000Eh
0x18006710b  test    rcx, rcx
0x18006710e  jnz     short loc_180067151
0x180067110  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067116  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006711d  mov     rcx, rax
0x180067120  test    rax, rax
0x180067123  jz      short loc_180067143
0x180067125  mov     rax, [rax]
0x180067128  mov     edx, 7F0h
0x18006712d  mov     rax, [rax+8]
0x180067131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067136  test    eax, eax
0x180067138  jz      short loc_180067143
0x18006713a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067141  jmp     short loc_180067151
0x180067143  lea     rcx, qword_1800D6F70; this
0x18006714a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067151  cmp     byte ptr [rcx+8], 0
0x180067155  jz      short loc_18006717C
0x180067157  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006715c  cmp     [rax+7CCh], ebx
0x180067162  jz      short loc_18006717C
0x180067164  mov     r9d, ebx; int
0x180067167  lea     rdx, aCmfvideothumbn_7; "CMFVideoThumbnail::CreateInstance"
0x18006716e  mov     r8d, 7Bh ; '{'; int
0x180067174  mov     rcx, rax; this
0x180067177  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006717c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067183  jb      short loc_1800671A8
0x180067185  mov     edx, 0Bh
0x18006718a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067191  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067198  xor     r9d, r9d
0x18006719b  mov     [rsp+38h+var_18], ebx
0x18006719f  mov     rcx, [rcx+10h]
0x1800671a3  call    WPP_SF_qD
0x1800671a8  lea     rcx, [rsp+38h+arg_8]; this
0x1800671ad  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800671b2  mov     eax, ebx
0x1800671b4  mov     rbx, [rsp+38h+arg_0]
0x1800671b9  add     rsp, 30h
0x1800671bd  pop     rdi
0x1800671be  retn
```
