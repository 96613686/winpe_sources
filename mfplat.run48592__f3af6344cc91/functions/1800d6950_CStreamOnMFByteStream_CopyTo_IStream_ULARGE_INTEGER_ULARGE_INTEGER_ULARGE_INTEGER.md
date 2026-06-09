# CStreamOnMFByteStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x1800d6950`
- end: `0x1800d6ed0`
- name: `?CopyTo@CStreamOnMFByteStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `1408`
- prototype: `__int64 __fastcall(CStreamOnMFByteStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011480`
- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800d6950`
- `0x18011fff0`
- `0x180120030`
- `0x180125154`
- `0x18013644c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d69da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d69da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800d6b37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800d6b37`

## string_xrefs

- `0x1800d6983`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6a5e`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6b07`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6bb9`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6d02`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6d91`: `CStreamOnMFByteStream::CopyTo`
- `0x1800d6e43`: `CStreamOnMFByteStream::CopyTo`

## pseudocode

```c
__int64 __fastcall CStreamOnMFByteStream::CopyTo(
        CStreamOnMFByteStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  void *v8; // r13
  CallStackTracing *v9; // rcx
  int v10; // esi
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned int LowPart; // r12d
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  void *v28; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+B0h] [rbp+40h] BYREF
  union _ULARGE_INTEGER *v31; // [rsp+C8h] [rbp+58h]

  v31 = a4;
  v28 = 0;
  v27 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  v8 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "CStreamOnMFByteStream::CopyTo", 555);
  if ( (unsigned __int8)byte_1801FD28C >= 0x10u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 22), 33, &WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids, 0);
  GetSystemTimeAsFileTime((LPFILETIME)this + 8);
  if ( !*((_DWORD *)this + 4) )
  {
    v24 = CallStackTracing::s_wpInstance;
    v10 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v24 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v24->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v24);
      if ( ThreadRelativeContext->m_result != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamOnMFByteStream::CopyTo", 563, -2147418113);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_72;
    v12 = 34;
    goto LABEL_71;
  }
  if ( !a2 )
  {
    v9 = CallStackTracing::s_wpInstance;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v9->m_fEnabled )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( v11->m_result != -2147467261 )
        CallStackContext::TraceFailure(v11, "CStreamOnMFByteStream::CopyTo", 566, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_72;
    v12 = 35;
LABEL_71:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids, this, v10);
LABEL_72:
    v17 = v27;
    goto LABEL_73;
  }
  v10 = CGITPtr::Get((CGITPtr *)this + 4, &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d, &v28);
  if ( v10 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v14->m_result != v10 )
        CallStackContext::TraceFailure(v14, "CStreamOnMFByteStream::CopyTo", 568, v10);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_72;
    v12 = 36;
    goto LABEL_71;
  }
  GetSystemInfo(&SystemInfo);
  v8 = operator new(SystemInfo.dwPageSize);
  if ( !v8 )
  {
    v15 = CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v15);
      if ( v16->m_result != -2147024882 )
        CallStackContext::TraceFailure(v16, "CStreamOnMFByteStream::CopyTo", 573, -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_72;
    v12 = 37;
    goto LABEL_71;
  }
  v17 = v27;
  while ( 1 )
  {
    if ( !a3.QuadPart )
    {
LABEL_41:
      if ( (unsigned __int8)byte_1801FD28C >= 0x10u )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          40,
          &WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids,
          this,
          v17 + a3.QuadPart,
          v17);
      goto LABEL_73;
    }
    LODWORD(v27) = 0;
    LowPart = a3.LowPart;
    if ( SystemInfo.dwPageSize < a3.QuadPart )
      LowPart = SystemInfo.dwPageSize;
    v30 = 0;
    v10 = (*(__int64 (__fastcall **)(void *, void *, _QWORD, unsigned __int64 *))(*(_QWORD *)v28 + 72LL))(
            v28,
            v8,
            LowPart,
            &v27);
    if ( v10 < 0 )
      break;
    v10 = a2->Write(a2, v8, v27, &v30);
    if ( v10 < 0 )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v19->m_fEnabled )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( v20->m_result != v10 )
          CallStackContext::TraceFailure(v20, "CStreamOnMFByteStream::CopyTo", 582, v10);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v21 = 39;
LABEL_61:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids, this, v10);
        goto LABEL_73;
      }
      goto LABEL_73;
    }
    a3.QuadPart -= v30;
    v17 += v30;
    if ( v30 < LowPart )
      goto LABEL_41;
  }
  v22 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v22 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v22->m_fEnabled )
  {
    v23 = CallStackTracing::GetThreadRelativeContext(v22);
    if ( v23->m_result != v10 )
      CallStackContext::TraceFailure(v23, "CStreamOnMFByteStream::CopyTo", 581, v10);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v21 = 38;
    goto LABEL_61;
  }
LABEL_73:
  operator delete(v8);
  if ( v31 )
    v31->QuadPart = v17;
  if ( a5 )
    a5->QuadPart = v17;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v28);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800d6950  mov     [rsp-38h+arg_8], rbx
0x1800d6955  mov     [rsp-38h+arg_18], r9
0x1800d695a  push    rbp
0x1800d695b  push    rsi
0x1800d695c  push    rdi
0x1800d695d  push    r12
0x1800d695f  push    r13
0x1800d6961  push    r14
0x1800d6963  push    r15
0x1800d6965  mov     rbp, rsp
0x1800d6968  sub     rsp, 70h
0x1800d696c  xor     r12d, r12d
0x1800d696f  xorps   xmm0, xmm0
0x1800d6972  mov     rdi, r8
0x1800d6975  mov     [rbp+var_38], r12
0x1800d6979  mov     r15, rdx
0x1800d697c  mov     [rbp+var_40], r12
0x1800d6980  mov     r14, rcx
0x1800d6983  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d698a  mov     r8d, 22Bh; int
0x1800d6990  lea     rcx, [rbp+arg_0]; this
0x1800d6994  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1800d6998  mov     r13d, r12d
0x1800d699b  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800d699f  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1800d69a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d69a8  cmp     cs:byte_1801FD28C, 10h
0x1800d69af  lea     rbx, WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids
0x1800d69b6  jb      short loc_1800D69D6
0x1800d69b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d69bf  lea     edx, [r12+21h]
0x1800d69c4  xor     r9d, r9d
0x1800d69c7  mov     r8, rbx
0x1800d69ca  mov     rcx, [rcx+0B0h]
0x1800d69d1  call    WPP_SF_s
0x1800d69d6  lea     rcx, [r14+40h]; lpSystemTimeAsFileTime
0x1800d69da  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d69e0  lea     rcx, [r14+10h]; this
0x1800d69e4  cmp     [rcx], r12d
0x1800d69e7  jz      loc_1800D6DDB
0x1800d69ed  test    r15, r15
0x1800d69f0  jnz     loc_1800D6A8A
0x1800d69f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d69fd  mov     esi, 80004003h
0x1800d6a02  test    rcx, rcx
0x1800d6a05  jnz     short loc_1800D6A48
0x1800d6a07  mov     rax, cs:stru_1801FC290.__vftable
0x1800d6a0e  lea     r8, stru_1801FC290
0x1800d6a15  mov     edx, 7F0h
0x1800d6a1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6a21  mov     rcx, r8
0x1800d6a24  mov     rax, [rax+8]
0x1800d6a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6a2d  test    eax, eax
0x1800d6a2f  jnz     short loc_1800D6A41
0x1800d6a31  lea     rcx, stru_1801F8A30
0x1800d6a38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6a3f  jmp     short loc_1800D6A48
0x1800d6a41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6a48  cmp     [rcx+8], r12b
0x1800d6a4c  jz      short loc_1800D6A73
0x1800d6a4e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6a53  cmp     [rax+7CCh], esi
0x1800d6a59  jz      short loc_1800D6A73
0x1800d6a5b  mov     r9d, esi; int
0x1800d6a5e  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6a65  mov     r8d, 236h; int
0x1800d6a6b  mov     rcx, rax; this
0x1800d6a6e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6a73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6a7a  jb      loc_1800D6E80
0x1800d6a80  mov     edx, 23h ; '#'
0x1800d6a85  jmp     loc_1800D6E66
0x1800d6a8a  lea     r8, [rbp+var_38]; void **
0x1800d6a8e  lea     rdx, _GUID_ad4c1b00_4bf7_422f_9175_756693d9130d; struct _GUID *
0x1800d6a95  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x1800d6a9a  mov     esi, eax
0x1800d6a9c  test    eax, eax
0x1800d6a9e  jns     loc_1800D6B33
0x1800d6aa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6aab  test    rcx, rcx
0x1800d6aae  jnz     short loc_1800D6AF1
0x1800d6ab0  mov     rax, cs:stru_1801FC290.__vftable
0x1800d6ab7  lea     r8, stru_1801FC290
0x1800d6abe  mov     edx, 7F0h
0x1800d6ac3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6aca  mov     rcx, r8
0x1800d6acd  mov     rax, [rax+8]
0x1800d6ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ad6  test    eax, eax
0x1800d6ad8  jnz     short loc_1800D6AEA
0x1800d6ada  lea     rcx, stru_1801F8A30
0x1800d6ae1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6ae8  jmp     short loc_1800D6AF1
0x1800d6aea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6af1  cmp     [rcx+8], r12b
0x1800d6af5  jz      short loc_1800D6B1C
0x1800d6af7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6afc  cmp     [rax+7CCh], esi
0x1800d6b02  jz      short loc_1800D6B1C
0x1800d6b04  mov     r9d, esi; int
0x1800d6b07  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6b0e  mov     r8d, 238h; int
0x1800d6b14  mov     rcx, rax; this
0x1800d6b17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6b1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6b23  jb      loc_1800D6E80
0x1800d6b29  mov     edx, 24h ; '$'
0x1800d6b2e  jmp     loc_1800D6E66
0x1800d6b33  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800d6b37  call    cs:__imp_GetSystemInfo
0x1800d6b3d  mov     ecx, [rbp+SystemInfo.dwPageSize]; Size
0x1800d6b40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6b45  mov     r13, rax
0x1800d6b48  test    rax, rax
0x1800d6b4b  jnz     loc_1800D6BE5
0x1800d6b51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b58  mov     esi, 8007000Eh
0x1800d6b5d  test    rcx, rcx
0x1800d6b60  jnz     short loc_1800D6BA3
0x1800d6b62  mov     rcx, cs:stru_1801FC290.__vftable
0x1800d6b69  lea     r8, stru_1801FC290
0x1800d6b70  mov     edx, 7F0h
0x1800d6b75  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b7c  mov     rax, [rcx+8]
0x1800d6b80  mov     rcx, r8
0x1800d6b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b88  test    eax, eax
0x1800d6b8a  jnz     short loc_1800D6B9C
0x1800d6b8c  lea     rcx, stru_1801F8A30
0x1800d6b93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b9a  jmp     short loc_1800D6BA3
0x1800d6b9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6ba3  cmp     [rcx+8], r12b
0x1800d6ba7  jz      short loc_1800D6BCE
0x1800d6ba9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6bae  cmp     [rax+7CCh], esi
0x1800d6bb4  jz      short loc_1800D6BCE
0x1800d6bb6  mov     r9d, esi; int
0x1800d6bb9  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6bc0  mov     r8d, 23Dh; int
0x1800d6bc6  mov     rcx, rax; this
0x1800d6bc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6bce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6bd5  jb      loc_1800D6E80
0x1800d6bdb  mov     edx, 25h ; '%'
0x1800d6be0  jmp     loc_1800D6E66
0x1800d6be5  mov     rbx, [rbp+var_40]
0x1800d6be9  test    rdi, rdi
0x1800d6bec  jz      short loc_1800D6C5D
0x1800d6bee  mov     eax, [rbp+SystemInfo.dwPageSize]
0x1800d6bf1  lea     r9, [rbp+var_40]
0x1800d6bf5  mov     rcx, [rbp+var_38]
0x1800d6bf9  cmp     rax, rdi
0x1800d6bfc  mov     dword ptr [rbp+var_40], 0
0x1800d6c03  mov     r12d, edi
0x1800d6c06  cmovb   r12d, [rbp+SystemInfo.dwPageSize]
0x1800d6c0b  mov     rdx, r13
0x1800d6c0e  mov     [rbp+arg_0], 0
0x1800d6c15  mov     r8d, r12d
0x1800d6c18  mov     rax, [rcx]
0x1800d6c1b  mov     rax, [rax+48h]
0x1800d6c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c24  mov     esi, eax
0x1800d6c26  test    eax, eax
0x1800d6c28  js      loc_1800D6D2E
0x1800d6c2e  mov     rax, [r15]
0x1800d6c31  lea     r9, [rbp+arg_0]
0x1800d6c35  mov     r8d, dword ptr [rbp+var_40]
0x1800d6c39  mov     rdx, r13
0x1800d6c3c  mov     rcx, r15
0x1800d6c3f  mov     rax, [rax+20h]
0x1800d6c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c48  mov     esi, eax
0x1800d6c4a  test    eax, eax
0x1800d6c4c  js      short loc_1800D6C9F
0x1800d6c4e  mov     eax, [rbp+arg_0]
0x1800d6c51  sub     rdi, rax
0x1800d6c54  add     rbx, rax
0x1800d6c57  cmp     [rbp+arg_0], r12d
0x1800d6c5b  jnb     short loc_1800D6BE9
0x1800d6c5d  cmp     cs:byte_1801FD28C, 10h
0x1800d6c64  jb      loc_1800D6E84
0x1800d6c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6c71  lea     rax, [rbx+rdi]
0x1800d6c75  mov     edx, 28h ; '('
0x1800d6c7a  mov     [rsp+70h+var_48], rbx
0x1800d6c7f  mov     r9, r14
0x1800d6c82  mov     [rsp+70h+var_50], rax
0x1800d6c87  lea     r8, WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids
0x1800d6c8e  mov     rcx, [rcx+0B0h]
0x1800d6c95  call    WPP_SF_qqq
0x1800d6c9a  jmp     loc_1800D6E84
0x1800d6c9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6ca6  test    rcx, rcx
0x1800d6ca9  jnz     short loc_1800D6CEC
0x1800d6cab  mov     rax, cs:stru_1801FC290.__vftable
0x1800d6cb2  lea     r8, stru_1801FC290
0x1800d6cb9  mov     edx, 7F0h
0x1800d6cbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6cc5  mov     rcx, r8
0x1800d6cc8  mov     rax, [rax+8]
0x1800d6ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6cd1  test    eax, eax
0x1800d6cd3  jnz     short loc_1800D6CE5
0x1800d6cd5  lea     rcx, stru_1801F8A30
0x1800d6cdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6ce3  jmp     short loc_1800D6CEC
0x1800d6ce5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6cec  cmp     byte ptr [rcx+8], 0
0x1800d6cf0  jz      short loc_1800D6D17
0x1800d6cf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6cf7  cmp     [rax+7CCh], esi
0x1800d6cfd  jz      short loc_1800D6D17
0x1800d6cff  mov     r9d, esi; int
0x1800d6d02  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6d09  mov     r8d, 246h; int
0x1800d6d0f  mov     rcx, rax; this
0x1800d6d12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6d17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6d1e  jb      loc_1800D6E84
0x1800d6d24  mov     edx, 27h ; '''
0x1800d6d29  jmp     loc_1800D6DB8
0x1800d6d2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6d35  test    rcx, rcx
0x1800d6d38  jnz     short loc_1800D6D7B
0x1800d6d3a  mov     rax, cs:stru_1801FC290.__vftable
0x1800d6d41  lea     r8, stru_1801FC290
0x1800d6d48  mov     edx, 7F0h
0x1800d6d4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6d54  mov     rcx, r8
0x1800d6d57  mov     rax, [rax+8]
0x1800d6d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d60  test    eax, eax
0x1800d6d62  jnz     short loc_1800D6D74
0x1800d6d64  lea     rcx, stru_1801F8A30
0x1800d6d6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6d72  jmp     short loc_1800D6D7B
0x1800d6d74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6d7b  cmp     byte ptr [rcx+8], 0
0x1800d6d7f  jz      short loc_1800D6DA6
0x1800d6d81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6d86  cmp     [rax+7CCh], esi
0x1800d6d8c  jz      short loc_1800D6DA6
0x1800d6d8e  mov     r9d, esi; int
0x1800d6d91  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6d98  mov     r8d, 245h; int
0x1800d6d9e  mov     rcx, rax; this
0x1800d6da1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6da6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6dad  jb      loc_1800D6E84
0x1800d6db3  mov     edx, 26h ; '&'
0x1800d6db8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6dbf  lea     r8, WPP_a4c330ec2e2e33e742924c72a0acd14c_Traceguids
0x1800d6dc6  mov     r9, r14
0x1800d6dc9  mov     dword ptr [rsp+70h+var_50], esi
0x1800d6dcd  mov     rcx, [rcx+10h]
0x1800d6dd1  call    WPP_SF_qD
0x1800d6dd6  jmp     loc_1800D6E84
0x1800d6ddb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6de2  mov     esi, 8000FFFFh
0x1800d6de7  test    rcx, rcx
0x1800d6dea  jnz     short loc_1800D6E2D
0x1800d6dec  mov     rax, cs:stru_1801FC290.__vftable
0x1800d6df3  lea     r8, stru_1801FC290
0x1800d6dfa  mov     edx, 7F0h
0x1800d6dff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6e06  mov     rcx, r8
0x1800d6e09  mov     rax, [rax+8]
0x1800d6e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e12  test    eax, eax
0x1800d6e14  jnz     short loc_1800D6E26
0x1800d6e16  lea     rcx, stru_1801F8A30
0x1800d6e1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6e24  jmp     short loc_1800D6E2D
0x1800d6e26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6e2d  cmp     [rcx+8], r12b
0x1800d6e31  jz      short loc_1800D6E58
0x1800d6e33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6e38  cmp     [rax+7CCh], esi
0x1800d6e3e  jz      short loc_1800D6E58
0x1800d6e40  mov     r9d, esi; int
0x1800d6e43  lea     rdx, aCstreamonmfbyt_3; "CStreamOnMFByteStream::CopyTo"
0x1800d6e4a  mov     r8d, 233h; int
0x1800d6e50  mov     rcx, rax; this
0x1800d6e53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6e58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6e5f  jb      short loc_1800D6E80
0x1800d6e61  mov     edx, 22h ; '"'
0x1800d6e66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6e6d  mov     r9, r14
0x1800d6e70  mov     r8, rbx
0x1800d6e73  mov     dword ptr [rsp+70h+var_50], esi
0x1800d6e77  mov     rcx, [rcx+10h]
0x1800d6e7b  call    WPP_SF_qD
0x1800d6e80  mov     rbx, [rbp+var_40]
0x1800d6e84  mov     rcx, r13; void *
0x1800d6e87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d6e8c  mov     rax, [rbp+arg_18]
0x1800d6e90  test    rax, rax
  ... truncated ...
```
