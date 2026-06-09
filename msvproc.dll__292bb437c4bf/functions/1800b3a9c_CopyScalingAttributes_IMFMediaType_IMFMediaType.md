# CopyScalingAttributes(IMFMediaType *,IMFMediaType *)

- ea: `0x1800b3a9c`
- end: `0x1800b3edb`
- name: `?CopyScalingAttributes@@YAJPEAUIMFMediaType@@0@Z`
- size: `1087`
- prototype: `__int64 __fastcall(struct IMFMediaType *, struct IMFMediaType *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18005d29c`
- `0x1800b3710`
- `0x1800b5fc0`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800b3a9c`
- `0x1800b3ee4`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3aee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3b95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3c3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3d8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3e31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3aee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3b95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3c3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3d8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3e31`

## string_xrefs

- `0x1800b3aa9`: `CopyScalingAttributes`

## pseudocode

```c
__int64 __fastcall CopyScalingAttributes(struct IMFMediaType *a1, struct IMFMediaType *a2)
{
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v25; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v25, "CopyScalingAttributes", 253);
  v4 = CopySingleAttribute(&MF_MT_FRAME_SIZE, a1, a2);
  if ( v4 >= 0 )
  {
    v4 = CopySingleAttribute(&MF_MT_PAN_SCAN_APERTURE, a1, a2);
    if ( v4 >= 0 )
    {
      v4 = CopySingleAttribute(&MF_MT_GEOMETRIC_APERTURE, a1, a2);
      if ( v4 >= 0 )
      {
        v4 = CopySingleAttribute(&MF_MT_MINIMUM_DISPLAY_APERTURE, a1, a2);
        if ( v4 >= 0 )
        {
          v4 = CopySingleAttribute(&MF_MT_PIXEL_ASPECT_RATIO, a1, a2);
          if ( v4 >= 0 )
          {
            v4 = CopySingleAttribute(&MF_MT_VIDEO_ROTATION, a1, a2);
            if ( v4 < 0 )
            {
              v21 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v22;
                if ( v22
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
                {
                  v21 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v21 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v21 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CopyScalingAttributes", 258, v4);
              }
              if ( g_wppLevels )
              {
                v8 = 30;
                goto LABEL_67;
              }
            }
          }
          else
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v19;
              if ( v19
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
              {
                v18 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v18 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v18 + 8) )
            {
              v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
              if ( *((_DWORD *)v20 + 499) != v4 )
                CallStackContext::TraceFailure(v20, "CopyScalingAttributes", 257, v4);
            }
            if ( g_wppLevels )
            {
              v8 = 29;
              goto LABEL_67;
            }
          }
        }
        else
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v16;
            if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
            {
              v15 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v15 + 8) )
          {
            v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
            if ( *((_DWORD *)v17 + 499) != v4 )
              CallStackContext::TraceFailure(v17, "CopyScalingAttributes", 256, v4);
          }
          if ( g_wppLevels )
          {
            v8 = 28;
            goto LABEL_67;
          }
        }
      }
      else
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v14 + 499) != v4 )
            CallStackContext::TraceFailure(v14, "CopyScalingAttributes", 255, v4);
        }
        if ( g_wppLevels )
        {
          v8 = 27;
          goto LABEL_67;
        }
      }
    }
    else
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v4 )
          CallStackContext::TraceFailure(v11, "CopyScalingAttributes", 254, v4);
      }
      if ( g_wppLevels )
      {
        v8 = 26;
        goto LABEL_67;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CopyScalingAttributes", 253, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 25;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids, 0, v4);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b3a9c  push    rbx
0x1800b3a9e  push    rsi
0x1800b3a9f  push    rdi
0x1800b3aa0  push    r14
0x1800b3aa2  sub     rsp, 38h
0x1800b3aa6  mov     rdi, rdx
0x1800b3aa9  lea     r14, aCopyscalingatt; "CopyScalingAttributes"
0x1800b3ab0  mov     rsi, rcx
0x1800b3ab3  mov     rdx, r14; char *
0x1800b3ab6  mov     r8d, 0FDh; int
0x1800b3abc  lea     rcx, [rsp+58h+arg_10]; this
0x1800b3ac1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b3ac6  mov     r8, rdi; struct IMFMediaType *
0x1800b3ac9  lea     rcx, MF_MT_FRAME_SIZE; struct _GUID *
0x1800b3ad0  mov     rdx, rsi; struct IMFMediaType *
0x1800b3ad3  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3ad8  mov     ebx, eax
0x1800b3ada  test    eax, eax
0x1800b3adc  jns     loc_1800B3B6D
0x1800b3ae2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3ae9  test    rcx, rcx
0x1800b3aec  jnz     short loc_1800B3B2F
0x1800b3aee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3af4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3afb  mov     rcx, rax
0x1800b3afe  test    rax, rax
0x1800b3b01  jz      short loc_1800B3B21
0x1800b3b03  mov     rax, [rax]
0x1800b3b06  mov     edx, 7F0h
0x1800b3b0b  mov     rax, [rax+8]
0x1800b3b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b14  test    eax, eax
0x1800b3b16  jz      short loc_1800B3B21
0x1800b3b18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3b1f  jmp     short loc_1800B3B2F
0x1800b3b21  lea     rcx, qword_180153440; this
0x1800b3b28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3b2f  cmp     byte ptr [rcx+8], 0
0x1800b3b33  jz      short loc_1800B3B56
0x1800b3b35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3b3a  cmp     [rax+7CCh], ebx
0x1800b3b40  jz      short loc_1800B3B56
0x1800b3b42  mov     r9d, ebx; int
0x1800b3b45  mov     r8d, 0FDh; int
0x1800b3b4b  mov     rdx, r14; char *
0x1800b3b4e  mov     rcx, rax; this
0x1800b3b51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3b56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3b5d  jb      loc_1800B3EC5
0x1800b3b63  mov     edx, 19h
0x1800b3b68  jmp     loc_1800B3EA7
0x1800b3b6d  mov     r8, rdi; struct IMFMediaType *
0x1800b3b70  lea     rcx, MF_MT_PAN_SCAN_APERTURE; struct _GUID *
0x1800b3b77  mov     rdx, rsi; struct IMFMediaType *
0x1800b3b7a  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3b7f  mov     ebx, eax
0x1800b3b81  test    eax, eax
0x1800b3b83  jns     loc_1800B3C14
0x1800b3b89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3b90  test    rcx, rcx
0x1800b3b93  jnz     short loc_1800B3BD6
0x1800b3b95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3b9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3ba2  mov     rcx, rax
0x1800b3ba5  test    rax, rax
0x1800b3ba8  jz      short loc_1800B3BC8
0x1800b3baa  mov     rax, [rax]
0x1800b3bad  mov     edx, 7F0h
0x1800b3bb2  mov     rax, [rax+8]
0x1800b3bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bbb  test    eax, eax
0x1800b3bbd  jz      short loc_1800B3BC8
0x1800b3bbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3bc6  jmp     short loc_1800B3BD6
0x1800b3bc8  lea     rcx, qword_180153440; this
0x1800b3bcf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3bd6  cmp     byte ptr [rcx+8], 0
0x1800b3bda  jz      short loc_1800B3BFD
0x1800b3bdc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3be1  cmp     [rax+7CCh], ebx
0x1800b3be7  jz      short loc_1800B3BFD
0x1800b3be9  mov     r9d, ebx; int
0x1800b3bec  mov     r8d, 0FEh; int
0x1800b3bf2  mov     rdx, r14; char *
0x1800b3bf5  mov     rcx, rax; this
0x1800b3bf8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3bfd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3c04  jb      loc_1800B3EC5
0x1800b3c0a  mov     edx, 1Ah
0x1800b3c0f  jmp     loc_1800B3EA7
0x1800b3c14  mov     r8, rdi; struct IMFMediaType *
0x1800b3c17  lea     rcx, MF_MT_GEOMETRIC_APERTURE; struct _GUID *
0x1800b3c1e  mov     rdx, rsi; struct IMFMediaType *
0x1800b3c21  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3c26  mov     ebx, eax
0x1800b3c28  test    eax, eax
0x1800b3c2a  jns     loc_1800B3CBB
0x1800b3c30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3c37  test    rcx, rcx
0x1800b3c3a  jnz     short loc_1800B3C7D
0x1800b3c3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3c42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3c49  mov     rcx, rax
0x1800b3c4c  test    rax, rax
0x1800b3c4f  jz      short loc_1800B3C6F
0x1800b3c51  mov     rax, [rax]
0x1800b3c54  mov     edx, 7F0h
0x1800b3c59  mov     rax, [rax+8]
0x1800b3c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c62  test    eax, eax
0x1800b3c64  jz      short loc_1800B3C6F
0x1800b3c66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3c6d  jmp     short loc_1800B3C7D
0x1800b3c6f  lea     rcx, qword_180153440; this
0x1800b3c76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3c7d  cmp     byte ptr [rcx+8], 0
0x1800b3c81  jz      short loc_1800B3CA4
0x1800b3c83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3c88  cmp     [rax+7CCh], ebx
0x1800b3c8e  jz      short loc_1800B3CA4
0x1800b3c90  mov     r9d, ebx; int
0x1800b3c93  mov     r8d, 0FFh; int
0x1800b3c99  mov     rdx, r14; char *
0x1800b3c9c  mov     rcx, rax; this
0x1800b3c9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3ca4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3cab  jb      loc_1800B3EC5
0x1800b3cb1  mov     edx, 1Bh
0x1800b3cb6  jmp     loc_1800B3EA7
0x1800b3cbb  mov     r8, rdi; struct IMFMediaType *
0x1800b3cbe  lea     rcx, MF_MT_MINIMUM_DISPLAY_APERTURE; struct _GUID *
0x1800b3cc5  mov     rdx, rsi; struct IMFMediaType *
0x1800b3cc8  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3ccd  mov     ebx, eax
0x1800b3ccf  test    eax, eax
0x1800b3cd1  jns     loc_1800B3D62
0x1800b3cd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3cde  test    rcx, rcx
0x1800b3ce1  jnz     short loc_1800B3D24
0x1800b3ce3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3ce9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3cf0  mov     rcx, rax
0x1800b3cf3  test    rax, rax
0x1800b3cf6  jz      short loc_1800B3D16
0x1800b3cf8  mov     rax, [rax]
0x1800b3cfb  mov     edx, 7F0h
0x1800b3d00  mov     rax, [rax+8]
0x1800b3d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d09  test    eax, eax
0x1800b3d0b  jz      short loc_1800B3D16
0x1800b3d0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3d14  jmp     short loc_1800B3D24
0x1800b3d16  lea     rcx, qword_180153440; this
0x1800b3d1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3d24  cmp     byte ptr [rcx+8], 0
0x1800b3d28  jz      short loc_1800B3D4B
0x1800b3d2a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3d2f  cmp     [rax+7CCh], ebx
0x1800b3d35  jz      short loc_1800B3D4B
0x1800b3d37  mov     r9d, ebx; int
0x1800b3d3a  mov     r8d, 100h; int
0x1800b3d40  mov     rdx, r14; char *
0x1800b3d43  mov     rcx, rax; this
0x1800b3d46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3d4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3d52  jb      loc_1800B3EC5
0x1800b3d58  mov     edx, 1Ch
0x1800b3d5d  jmp     loc_1800B3EA7
0x1800b3d62  mov     r8, rdi; struct IMFMediaType *
0x1800b3d65  lea     rcx, MF_MT_PIXEL_ASPECT_RATIO; struct _GUID *
0x1800b3d6c  mov     rdx, rsi; struct IMFMediaType *
0x1800b3d6f  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3d74  mov     ebx, eax
0x1800b3d76  test    eax, eax
0x1800b3d78  jns     loc_1800B3E09
0x1800b3d7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3d85  test    rcx, rcx
0x1800b3d88  jnz     short loc_1800B3DCB
0x1800b3d8a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3d90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3d97  mov     rcx, rax
0x1800b3d9a  test    rax, rax
0x1800b3d9d  jz      short loc_1800B3DBD
0x1800b3d9f  mov     rax, [rax]
0x1800b3da2  mov     edx, 7F0h
0x1800b3da7  mov     rax, [rax+8]
0x1800b3dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3db0  test    eax, eax
0x1800b3db2  jz      short loc_1800B3DBD
0x1800b3db4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3dbb  jmp     short loc_1800B3DCB
0x1800b3dbd  lea     rcx, qword_180153440; this
0x1800b3dc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3dcb  cmp     byte ptr [rcx+8], 0
0x1800b3dcf  jz      short loc_1800B3DF2
0x1800b3dd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3dd6  cmp     [rax+7CCh], ebx
0x1800b3ddc  jz      short loc_1800B3DF2
0x1800b3dde  mov     r9d, ebx; int
0x1800b3de1  mov     r8d, 101h; int
0x1800b3de7  mov     rdx, r14; char *
0x1800b3dea  mov     rcx, rax; this
0x1800b3ded  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3df2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3df9  jb      loc_1800B3EC5
0x1800b3dff  mov     edx, 1Dh
0x1800b3e04  jmp     loc_1800B3EA7
0x1800b3e09  mov     r8, rdi; struct IMFMediaType *
0x1800b3e0c  lea     rcx, MF_MT_VIDEO_ROTATION; struct _GUID *
0x1800b3e13  mov     rdx, rsi; struct IMFMediaType *
0x1800b3e16  call    ?CopySingleAttribute@@YAJAEBU_GUID@@PEAUIMFMediaType@@1@Z; CopySingleAttribute(_GUID const &,IMFMediaType *,IMFMediaType *)
0x1800b3e1b  mov     ebx, eax
0x1800b3e1d  test    eax, eax
0x1800b3e1f  jns     loc_1800B3EC5
0x1800b3e25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3e2c  test    rcx, rcx
0x1800b3e2f  jnz     short loc_1800B3E72
0x1800b3e31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3e37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3e3e  mov     rcx, rax
0x1800b3e41  test    rax, rax
0x1800b3e44  jz      short loc_1800B3E64
0x1800b3e46  mov     rax, [rax]
0x1800b3e49  mov     edx, 7F0h
0x1800b3e4e  mov     rax, [rax+8]
0x1800b3e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e57  test    eax, eax
0x1800b3e59  jz      short loc_1800B3E64
0x1800b3e5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3e62  jmp     short loc_1800B3E72
0x1800b3e64  lea     rcx, qword_180153440; this
0x1800b3e6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3e72  cmp     byte ptr [rcx+8], 0
0x1800b3e76  jz      short loc_1800B3E99
0x1800b3e78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3e7d  cmp     [rax+7CCh], ebx
0x1800b3e83  jz      short loc_1800B3E99
0x1800b3e85  mov     r9d, ebx; int
0x1800b3e88  mov     r8d, 102h; int
0x1800b3e8e  mov     rdx, r14; char *
0x1800b3e91  mov     rcx, rax; this
0x1800b3e94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3e99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3ea0  jb      short loc_1800B3EC5
0x1800b3ea2  mov     edx, 1Eh
0x1800b3ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3eae  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800b3eb5  xor     r9d, r9d
0x1800b3eb8  mov     [rsp+58h+var_38], ebx
0x1800b3ebc  mov     rcx, [rcx+10h]
0x1800b3ec0  call    WPP_SF_qD
0x1800b3ec5  lea     rcx, [rsp+58h+arg_10]; this
0x1800b3eca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b3ecf  mov     eax, ebx
0x1800b3ed1  add     rsp, 38h
0x1800b3ed5  pop     r14
0x1800b3ed7  pop     rdi
0x1800b3ed8  pop     rsi
0x1800b3ed9  pop     rbx
0x1800b3eda  retn
```
