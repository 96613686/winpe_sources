# GetWidthHeightFourCCFromMT(IMFMediaType *,uint *,uint *,ulong *)

- ea: `0x1800041dc`
- end: `0x180004403`
- name: `?GetWidthHeightFourCCFromMT@@YAJPEAUIMFMediaType@@PEAI1PEAK@Z`
- size: `551`
- prototype: `__int64 __fastcall(struct IMFMediaType *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180002540`
- `0x180002810`

## callees

- `0x180001580`
- `0x180001ec8`
- `0x180002200`
- `0x1800041dc`
- `0x180006950`
- `0x1800082ec`
- `0x180008358`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004323`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004323`

## pseudocode

```c
__int64 __fastcall GetWidthHeightFourCCFromMT(
        struct IMFMediaType *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  struct CallStackContext *v17; // rax
  int v18; // ecx
  int v19; // ecx
  _BYTE v21[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF
  __int128 v23; // [rsp+40h] [rbp-48h] BYREF

  v23 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v21, "GetWidthHeightFourCCFromMT", 731);
  v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))a1->lpVtbl->GetGUID)(
         a1,
         &MF_MT_SUBTYPE,
         &v23);
  if ( v8 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v22 = 0;
    v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64 *))lpVtbl->GetUINT64)(
           a1,
           &MF_MT_FRAME_SIZE,
           &v22);
    if ( v8 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( !v15 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v16 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "GetWidthHeightFourCCFromMT", 732, v8);
      }
      if ( g_wppLevels )
      {
        v11 = 55;
        goto LABEL_22;
      }
    }
    else
    {
      v13 = v22;
      *a2 = HIDWORD(v22);
      v14 = v23;
      *a3 = v13;
      *a4 = v14;
    }
  }
  else
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v9;
      if ( !v9 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v10 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v10 + 499) != v8 )
        CallStackContext::TraceFailure(v10, "GetWidthHeightFourCCFromMT", 731, v8);
    }
    if ( g_wppLevels )
    {
      v11 = 54;
LABEL_22:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids, 0, v8);
    }
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v17 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
    v18 = *((_DWORD *)v17 + 497);
    if ( v18 )
    {
      v19 = v18 - 1;
      *((_DWORD *)v17 + 497) = v19;
      if ( !v19 )
        CallStackContext::ClearState(v17);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800041dc  push    rbx
0x1800041de  push    rsi
0x1800041df  push    rdi
0x1800041e0  push    r14
0x1800041e2  push    r15
0x1800041e4  sub     rsp, 60h
0x1800041e8  mov     rax, cs:__security_cookie
0x1800041ef  xor     rax, rsp
0x1800041f2  mov     [rsp+88h+var_38], rax
0x1800041f7  mov     r14, r8
0x1800041fa  mov     rsi, rdx
0x1800041fd  mov     rdi, rcx
0x180004200  lea     rdx, aGetwidthheight; "GetWidthHeightFourCCFromMT"
0x180004207  xorps   xmm0, xmm0
0x18000420a  lea     rcx, [rsp+88h+var_58]; this
0x18000420f  mov     r8d, 2DBh; int
0x180004215  mov     r15, r9
0x180004218  movups  [rsp+88h+var_48], xmm0
0x18000421d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180004222  mov     rax, [rdi]
0x180004225  lea     r8, [rsp+88h+var_48]
0x18000422a  lea     rdx, MF_MT_SUBTYPE
0x180004231  mov     rcx, rdi
0x180004234  mov     rax, [rax+50h]
0x180004238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000423d  mov     ebx, eax
0x18000423f  test    eax, eax
0x180004241  jns     loc_1800042D2
0x180004247  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18000424f  jnz     short loc_180004289
0x180004251  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180004257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000425e  mov     rcx, rax
0x180004261  test    rax, rax
0x180004264  jz      short loc_18000427B
0x180004266  mov     rax, [rax]
0x180004269  mov     edx, 7F0h
0x18000426e  mov     rax, [rax+8]
0x180004272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004277  test    eax, eax
0x180004279  jnz     short loc_180004289
0x18000427b  lea     rax, off_180022080
0x180004282  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004289  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180004290  cmp     byte ptr [rcx+8], 0
0x180004294  jz      short loc_1800042BB
0x180004296  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000429b  cmp     [rax+7CCh], ebx
0x1800042a1  jz      short loc_1800042BB
0x1800042a3  mov     r9d, ebx; int
0x1800042a6  lea     rdx, aGetwidthheight; "GetWidthHeightFourCCFromMT"
0x1800042ad  mov     r8d, 2DBh; int
0x1800042b3  mov     rcx, rax; this
0x1800042b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800042bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800042c2  jb      loc_1800043B9
0x1800042c8  mov     edx, 36h ; '6'
0x1800042cd  jmp     loc_18000439B
0x1800042d2  mov     rax, [rdi]
0x1800042d5  lea     r8, [rsp+88h+var_50]
0x1800042da  lea     rdx, MF_MT_FRAME_SIZE
0x1800042e1  mov     [rsp+88h+var_50], 0
0x1800042ea  mov     rcx, rdi
0x1800042ed  mov     rax, [rax+40h]
0x1800042f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f6  mov     ebx, eax
0x1800042f8  test    eax, eax
0x1800042fa  js      short loc_180004319
0x1800042fc  mov     rcx, [rsp+88h+var_50]
0x180004301  mov     rax, rcx
0x180004304  shr     rax, 20h
0x180004308  mov     [rsi], eax
0x18000430a  mov     eax, dword ptr [rsp+88h+var_48]
0x18000430e  mov     [r14], ecx
0x180004311  mov     [r15], eax
0x180004314  jmp     loc_1800043B9
0x180004319  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180004321  jnz     short loc_18000435B
0x180004323  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180004329  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004330  mov     rcx, rax
0x180004333  test    rax, rax
0x180004336  jz      short loc_18000434D
0x180004338  mov     rax, [rax]
0x18000433b  mov     edx, 7F0h
0x180004340  mov     rax, [rax+8]
0x180004344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004349  test    eax, eax
0x18000434b  jnz     short loc_18000435B
0x18000434d  lea     rax, off_180022080
0x180004354  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000435b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180004362  cmp     byte ptr [rcx+8], 0
0x180004366  jz      short loc_18000438D
0x180004368  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000436d  cmp     [rax+7CCh], ebx
0x180004373  jz      short loc_18000438D
0x180004375  mov     r9d, ebx; int
0x180004378  lea     rdx, aGetwidthheight; "GetWidthHeightFourCCFromMT"
0x18000437f  mov     r8d, 2DCh; int
0x180004385  mov     rcx, rax; this
0x180004388  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000438d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004394  jb      short loc_1800043B9
0x180004396  mov     edx, 37h ; '7'
0x18000439b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043a2  lea     r8, WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids
0x1800043a9  xor     r9d, r9d
0x1800043ac  mov     [rsp+88h+var_68], ebx
0x1800043b0  mov     rcx, [rcx+10h]
0x1800043b4  call    WPP_SF_qd
0x1800043b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800043c0  cmp     byte ptr [rcx+8], 0
0x1800043c4  jz      short loc_1800043E8
0x1800043c6  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800043cb  mov     ecx, [rax+7C4h]
0x1800043d1  test    ecx, ecx
0x1800043d3  jz      short loc_1800043E8
0x1800043d5  sub     ecx, 1
0x1800043d8  mov     [rax+7C4h], ecx
0x1800043de  jnz     short loc_1800043E8
0x1800043e0  mov     rcx, rax; this
0x1800043e3  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x1800043e8  mov     eax, ebx
0x1800043ea  mov     rcx, [rsp+88h+var_38]
0x1800043ef  xor     rcx, rsp; StackCookie
0x1800043f2  call    __security_check_cookie
0x1800043f7  add     rsp, 60h
0x1800043fb  pop     r15
0x1800043fd  pop     r14
0x1800043ff  pop     rdi
0x180004400  pop     rsi
0x180004401  pop     rbx
0x180004402  retn
```
