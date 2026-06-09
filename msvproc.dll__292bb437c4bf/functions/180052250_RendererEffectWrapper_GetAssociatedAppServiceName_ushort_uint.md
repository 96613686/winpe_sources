# RendererEffectWrapper::GetAssociatedAppServiceName(ushort * *,uint *)

- ea: `0x180052250`
- end: `0x180052426`
- name: `?GetAssociatedAppServiceName@RendererEffectWrapper@@QEAAJPEAPEAGPEAI@Z`
- size: `470`
- prototype: `__int64 __fastcall(RendererEffectWrapper *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b4210`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180052250`
- `0x1800b40a4`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800522b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052368`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800522b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052368`

## string_xrefs

- `0x18005226e`: `RendererEffectWrapper::GetAssociatedAppServiceName`
- `0x180052308`: `RendererEffectWrapper::GetAssociatedAppServiceName`
- `0x1800523bf`: `RendererEffectWrapper::GetAssociatedAppServiceName`

## pseudocode

```c
__int64 __fastcall RendererEffectWrapper::GetAssociatedAppServiceName(
        RendererEffectWrapper *this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  int Attributes; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+50h] [rbp+18h] BYREF
  struct IMFAttributes *v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v14,
    "RendererEffectWrapper::GetAssociatedAppServiceName",
    794);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  Attributes = RendererEffectWrapper::GetAttributes(this, &v15);
  if ( Attributes >= 0 )
  {
    Attributes = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, unsigned __int16 **, _QWORD))v15->lpVtbl->GetAllocatedString)(
                   v15,
                   MF_VIDEO_RENDERER_EFFECT_APP_SERVICE_NAME,
                   a2,
                   0);
    if ( Attributes < 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Attributes )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "RendererEffectWrapper::GetAssociatedAppServiceName",
            795,
            Attributes);
      }
      if ( g_wppLevels )
      {
        v9 = 92;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != Attributes )
        CallStackContext::TraceFailure(v8, "RendererEffectWrapper::GetAssociatedAppServiceName", 794, Attributes);
    }
    if ( g_wppLevels )
    {
      v9 = 91;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
        this,
        Attributes);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x180052250  mov     rax, rsp
0x180052253  mov     [rax+8], rbx
0x180052257  mov     [rax+10h], rsi
0x18005225b  push    rdi
0x18005225c  sub     rsp, 30h
0x180052260  mov     rsi, rdx
0x180052263  mov     qword ptr [rax+20h], 0
0x18005226b  mov     rdi, rcx
0x18005226e  lea     rdx, aRenderereffect_4; "RendererEffectWrapper::GetAssociatedApp"...
0x180052275  lea     rcx, [rax+18h]; this
0x180052279  mov     r8d, 31Ah; int
0x18005227f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052284  lea     rcx, [rsp+38h+arg_18]
0x180052289  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005228e  lea     rdx, [rsp+38h+arg_18]; struct IMFAttributes **
0x180052293  mov     rcx, rdi; this
0x180052296  call    ?GetAttributes@RendererEffectWrapper@@QEAAJPEAPEAUIMFAttributes@@@Z; RendererEffectWrapper::GetAttributes(IMFAttributes * *)
0x18005229b  mov     ebx, eax
0x18005229d  test    eax, eax
0x18005229f  jns     loc_180052334
0x1800522a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800522ac  test    rcx, rcx
0x1800522af  jnz     short loc_1800522F2
0x1800522b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800522b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800522be  mov     rcx, rax
0x1800522c1  test    rax, rax
0x1800522c4  jz      short loc_1800522E4
0x1800522c6  mov     rax, [rax]
0x1800522c9  mov     edx, 7F0h
0x1800522ce  mov     rax, [rax+8]
0x1800522d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522d7  test    eax, eax
0x1800522d9  jz      short loc_1800522E4
0x1800522db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800522e2  jmp     short loc_1800522F2
0x1800522e4  lea     rcx, qword_180153440; this
0x1800522eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800522f2  cmp     byte ptr [rcx+8], 0
0x1800522f6  jz      short loc_18005231D
0x1800522f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800522fd  cmp     [rax+7CCh], ebx
0x180052303  jz      short loc_18005231D
0x180052305  mov     r9d, ebx; int
0x180052308  lea     rdx, aRenderereffect_4; "RendererEffectWrapper::GetAssociatedApp"...
0x18005230f  mov     r8d, 31Ah; int
0x180052315  mov     rcx, rax; this
0x180052318  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005231d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052324  jb      loc_180052400
0x18005232a  mov     edx, 5Bh ; '['
0x18005232f  jmp     loc_1800523E2
0x180052334  mov     rcx, [rsp+38h+arg_18]
0x180052339  lea     rdx, MF_VIDEO_RENDERER_EFFECT_APP_SERVICE_NAME
0x180052340  xor     r9d, r9d
0x180052343  mov     r8, rsi
0x180052346  mov     rax, [rcx]
0x180052349  mov     rax, [rax+68h]
0x18005234d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052352  mov     ebx, eax
0x180052354  test    eax, eax
0x180052356  jns     loc_180052400
0x18005235c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052363  test    rcx, rcx
0x180052366  jnz     short loc_1800523A9
0x180052368  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005236e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052375  mov     rcx, rax
0x180052378  test    rax, rax
0x18005237b  jz      short loc_18005239B
0x18005237d  mov     rax, [rax]
0x180052380  mov     edx, 7F0h
0x180052385  mov     rax, [rax+8]
0x180052389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005238e  test    eax, eax
0x180052390  jz      short loc_18005239B
0x180052392  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052399  jmp     short loc_1800523A9
0x18005239b  lea     rcx, qword_180153440; this
0x1800523a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800523a9  cmp     byte ptr [rcx+8], 0
0x1800523ad  jz      short loc_1800523D4
0x1800523af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800523b4  cmp     [rax+7CCh], ebx
0x1800523ba  jz      short loc_1800523D4
0x1800523bc  mov     r9d, ebx; int
0x1800523bf  lea     rdx, aRenderereffect_4; "RendererEffectWrapper::GetAssociatedApp"...
0x1800523c6  mov     r8d, 31Bh; int
0x1800523cc  mov     rcx, rax; this
0x1800523cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800523d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800523db  jb      short loc_180052400
0x1800523dd  mov     edx, 5Ch ; '\'
0x1800523e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523e9  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800523f0  mov     r9, rdi
0x1800523f3  mov     [rsp+38h+var_18], ebx
0x1800523f7  mov     rcx, [rcx+10h]
0x1800523fb  call    WPP_SF_qD
0x180052400  lea     rcx, [rsp+38h+arg_10]; this
0x180052405  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005240a  lea     rcx, [rsp+38h+arg_18]
0x18005240f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052414  mov     rsi, [rsp+38h+arg_8]
0x180052419  mov     eax, ebx
0x18005241b  mov     rbx, [rsp+38h+arg_0]
0x180052420  add     rsp, 30h
0x180052424  pop     rdi
0x180052425  retn
```
