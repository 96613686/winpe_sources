# CRolling420FrameStitcherMFTDataHandler::Init(CRolling420FrameStitcherMFTTypeHandler *)

- ea: `0x18004bc00`
- end: `0x18004bdc9`
- name: `?Init@CRolling420FrameStitcherMFTDataHandler@@QEAAJPEAVCRolling420FrameStitcherMFTTypeHandler@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this, struct CRolling420FrameStitcherMFTTypeHandler *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8518`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18004bc00`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18004bc41`
- `MFPlat!MFCreateAttributes` at `0x18004bc41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd15`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::Init(
        CRolling420FrameStitcherMFTDataHandler *this,
        struct CRolling420FrameStitcherMFTTypeHandler *a2)
{
  HRESULT v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v12; // [rsp+40h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v12,
    "CRolling420FrameStitcherMFTDataHandler::Init",
    161);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  v3 = MFCreateAttributes((IMFAttributes **)this + 4, 1u);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)this + 4) + 168LL))(
           *((_QWORD *)this + 4),
           MF_SA_D3D11_AWARE,
           1);
    if ( v3 < 0 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CRolling420FrameStitcherMFTDataHandler::Init", 162, v3);
      }
      if ( g_wppLevels )
      {
        v7 = 30;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v6 + 499) != v3 )
        CallStackContext::TraceFailure(v6, "CRolling420FrameStitcherMFTDataHandler::Init", 161, v3);
    }
    if ( g_wppLevels )
    {
      v7 = 29;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v3);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004bc00  mov     [rsp+arg_8], rbx
0x18004bc05  mov     [rsp+arg_10], rsi
0x18004bc0a  push    rdi
0x18004bc0b  sub     rsp, 30h
0x18004bc0f  mov     [rcx+8], rdx
0x18004bc13  mov     rdi, rcx
0x18004bc16  lea     rdx, aCrolling420fra_14; "CRolling420FrameStitcherMFTDataHandler:"...
0x18004bc1d  mov     r8d, 0A1h; int
0x18004bc23  lea     rcx, [rsp+38h+arg_0]; this
0x18004bc28  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004bc2d  lea     rsi, [rdi+20h]
0x18004bc31  mov     rcx, rsi
0x18004bc34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004bc39  mov     edx, 1; cInitialSize
0x18004bc3e  mov     rcx, rsi; ppMFAttributes
0x18004bc41  call    cs:__imp_MFCreateAttributes
0x18004bc47  mov     ebx, eax
0x18004bc49  test    eax, eax
0x18004bc4b  jns     loc_18004BCE0
0x18004bc51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc58  test    rcx, rcx
0x18004bc5b  jnz     short loc_18004BC9E
0x18004bc5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bc63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc6a  mov     rcx, rax
0x18004bc6d  test    rax, rax
0x18004bc70  jz      short loc_18004BC90
0x18004bc72  mov     rax, [rax]
0x18004bc75  mov     edx, 7F0h
0x18004bc7a  mov     rax, [rax+8]
0x18004bc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc83  test    eax, eax
0x18004bc85  jz      short loc_18004BC90
0x18004bc87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc8e  jmp     short loc_18004BC9E
0x18004bc90  lea     rcx, qword_180153440; this
0x18004bc97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc9e  cmp     byte ptr [rcx+8], 0
0x18004bca2  jz      short loc_18004BCC9
0x18004bca4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bca9  cmp     [rax+7CCh], ebx
0x18004bcaf  jz      short loc_18004BCC9
0x18004bcb1  mov     r9d, ebx; int
0x18004bcb4  lea     rdx, aCrolling420fra_14; "CRolling420FrameStitcherMFTDataHandler:"...
0x18004bcbb  mov     r8d, 0A1h; int
0x18004bcc1  mov     rcx, rax; this
0x18004bcc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bcc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bcd0  jb      loc_18004BDAD
0x18004bcd6  mov     edx, 1Dh
0x18004bcdb  jmp     loc_18004BD8F
0x18004bce0  mov     rcx, [rsi]
0x18004bce3  lea     rdx, MF_SA_D3D11_AWARE
0x18004bcea  mov     r8d, 1
0x18004bcf0  mov     rax, [rcx]
0x18004bcf3  mov     rax, [rax+0A8h]
0x18004bcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcff  mov     ebx, eax
0x18004bd01  test    eax, eax
0x18004bd03  jns     loc_18004BDAD
0x18004bd09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd10  test    rcx, rcx
0x18004bd13  jnz     short loc_18004BD56
0x18004bd15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bd1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd22  mov     rcx, rax
0x18004bd25  test    rax, rax
0x18004bd28  jz      short loc_18004BD48
0x18004bd2a  mov     rax, [rax]
0x18004bd2d  mov     edx, 7F0h
0x18004bd32  mov     rax, [rax+8]
0x18004bd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd3b  test    eax, eax
0x18004bd3d  jz      short loc_18004BD48
0x18004bd3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd46  jmp     short loc_18004BD56
0x18004bd48  lea     rcx, qword_180153440; this
0x18004bd4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd56  cmp     byte ptr [rcx+8], 0
0x18004bd5a  jz      short loc_18004BD81
0x18004bd5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bd61  cmp     [rax+7CCh], ebx
0x18004bd67  jz      short loc_18004BD81
0x18004bd69  mov     r9d, ebx; int
0x18004bd6c  lea     rdx, aCrolling420fra_14; "CRolling420FrameStitcherMFTDataHandler:"...
0x18004bd73  mov     r8d, 0A2h; int
0x18004bd79  mov     rcx, rax; this
0x18004bd7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bd81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bd88  jb      short loc_18004BDAD
0x18004bd8a  mov     edx, 1Eh
0x18004bd8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd96  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x18004bd9d  mov     r9, rdi
0x18004bda0  mov     [rsp+38h+var_18], ebx
0x18004bda4  mov     rcx, [rcx+10h]
0x18004bda8  call    WPP_SF_qD
0x18004bdad  lea     rcx, [rsp+38h+arg_0]; this
0x18004bdb2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004bdb7  mov     rsi, [rsp+38h+arg_10]
0x18004bdbc  mov     eax, ebx
0x18004bdbe  mov     rbx, [rsp+38h+arg_8]
0x18004bdc3  add     rsp, 30h
0x18004bdc7  pop     rdi
0x18004bdc8  retn
```
