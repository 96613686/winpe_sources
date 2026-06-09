# CMFVideoThumbnail::CalcOffsetsForComparison(uint,uint,uint,uint,_MFVideoArea const &)

- ea: `0x1800678cc`
- end: `0x180067b37`
- name: `?CalcOffsetsForComparison@CMFVideoThumbnail@@AEAAJIIIIAEBU_MFVideoArea@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, const struct _MFVideoArea *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006b2cc`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800678cc`
- `0x18006ee78`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a6e`

## string_xrefs

- `0x1800678eb`: `CMFVideoThumbnail::CalcOffsetsForComparison`
- `0x180067acf`: `CMFVideoThumbnail::CalcOffsetsForComparison`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CalcOffsetsForComparison(
        CMFVideoThumbnail *this,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        const struct _MFVideoArea *a6)
{
  __int64 v9; // rdx
  __int64 *v10; // r10
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  __int64 v15; // r9
  LONG cx; // edi
  __int64 cy; // r8
  __int64 v18; // rcx
  unsigned int v19; // ebx
  unsigned int v20; // edx
  unsigned int i; // r8d
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r9d
  __int64 v25; // rax
  int v26; // ecx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[8]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v31[16]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CMFVideoThumbnail::CalcOffsetsForComparison",
    603);
  v10 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v13 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                        *((_QWORD *)this + 50),
                        v31);
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = *v13;
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  v15 = 2454267027LL;
  cx = a6->Area.cx;
  cy = (unsigned int)a6->Area.cy;
  LODWORD(v9) = (unsigned __int64)(-1840700269LL * cx) >> 32;
  v18 = (unsigned int)((unsigned __int64)(2454267027LL * cx) >> 32) >> 31;
  if ( cx / 14
    && (LODWORD(v9) = (unsigned __int64)(-1840700269LL * (int)cy) >> 32,
        v18 = (unsigned int)((unsigned __int64)(2454267027LL * (int)cy) >> 32) >> 31,
        v15 = (unsigned int)((int)cy / 14),
        (_DWORD)v15) )
  {
    v19 = 0;
    v20 = 8;
    *((_DWORD *)this + 20) = a3 * (a6->OffsetX.value + cx / 4) + a4 * ((int)cy / 4 + a6->OffsetY.value);
    for ( i = 1; i < 8; ++i )
    {
      v22 = i;
      v23 = a3 * (cx / 14) + *((_DWORD *)this + i + 19);
      *((_DWORD *)this + v22 + 20) = v23;
    }
    v24 = a4 * v15;
    do
    {
      v25 = v20;
      v26 = v24 + *((_DWORD *)this + v20 + 12);
      ++v20;
      *((_DWORD *)this + v25 + 20) = v26;
    }
    while ( v20 < 0x40 );
  }
  else
  {
    if ( byte_1800DC8D3 )
    {
      WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 17), v9, cy, this, cx, a6->Area.cy);
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    v19 = -1072875854;
    if ( !v10 )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v9, cy, v15);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v28 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v28, "CMFVideoThumbnail::CalcOffsetsForComparison", 616, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        -1072875854);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return v19;
}

```

## disassembly

```asm
0x1800678cc  push    rbx
0x1800678ce  push    rbp
0x1800678cf  push    rsi
0x1800678d0  push    rdi
0x1800678d1  push    r14
0x1800678d3  push    r15
0x1800678d5  sub     rsp, 58h
0x1800678d9  mov     rax, cs:__security_cookie
0x1800678e0  xor     rax, rsp
0x1800678e3  mov     [rsp+88h+var_40], rax
0x1800678e8  mov     r15d, r8d
0x1800678eb  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x1800678f2  mov     rsi, rcx
0x1800678f5  mov     r8d, 25Bh; int
0x1800678fb  lea     rcx, [rsp+88h+var_58]; this
0x180067900  mov     r14d, r9d
0x180067903  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067908  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006790f  cmp     byte ptr [r10+8], 0
0x180067914  jz      short loc_180067976
0x180067916  cmp     qword ptr [rsi+190h], 0
0x18006791e  jz      short loc_180067976
0x180067920  mov     rcx, r10; this
0x180067923  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067928  mov     rcx, [rsi+190h]
0x18006792f  mov     rdi, rax
0x180067932  mov     rdx, [rcx]
0x180067935  mov     rax, [rdx+128h]
0x18006793c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067941  mov     rcx, [rsi+190h]
0x180067948  mov     ebx, eax
0x18006794a  mov     rdx, [rcx]
0x18006794d  mov     rax, [rdx+118h]
0x180067954  lea     rdx, [rsp+88h+var_50]
0x180067959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006795e  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067965  movups  xmm0, xmmword ptr [rax]
0x180067968  mov     [rdi+7E0h], ebx
0x18006796e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180067976  mov     rbp, [rsp+88h+arg_28]
0x18006797e  mov     r9d, 92492493h
0x180067984  mov     eax, r9d
0x180067987  mov     edi, [rbp+8]
0x18006798a  mov     r8d, [rbp+0Ch]
0x18006798e  imul    edi
0x180067990  lea     r11d, [rdi+rdx]
0x180067994  sar     r11d, 3
0x180067998  mov     ecx, r11d
0x18006799b  shr     ecx, 1Fh
0x18006799e  add     r11d, ecx
0x1800679a1  jz      loc_180067A35
0x1800679a7  mov     eax, r9d
0x1800679aa  imul    r8d
0x1800679ad  lea     r9d, [r8+rdx]
0x1800679b1  sar     r9d, 3
0x1800679b5  mov     ecx, r9d
0x1800679b8  shr     ecx, 1Fh
0x1800679bb  add     r9d, ecx
0x1800679be  jz      short loc_180067A35
0x1800679c0  movsx   ecx, word ptr [rbp+2]
0x1800679c4  mov     eax, r8d
0x1800679c7  movsx   r8d, word ptr [rbp+6]
0x1800679cc  cdq
0x1800679cd  xor     ebx, ebx
0x1800679cf  lea     r10d, [rbx+4]
0x1800679d3  idiv    r10d
0x1800679d6  add     r8d, eax
0x1800679d9  mov     eax, edi
0x1800679db  cdq
0x1800679dc  imul    r8d, r14d
0x1800679e0  idiv    r10d
0x1800679e3  lea     edx, [rbx+8]
0x1800679e6  add     eax, ecx
0x1800679e8  imul    eax, r15d
0x1800679ec  add     r8d, eax
0x1800679ef  mov     [rsi+50h], r8d
0x1800679f3  lea     r8d, [rbx+1]
0x1800679f7  imul    r11d, r15d
0x1800679fb  lea     eax, [r8-1]
0x1800679ff  mov     ecx, [rsi+rax*4+50h]
0x180067a03  mov     eax, r8d
0x180067a06  add     ecx, r11d
0x180067a09  inc     r8d
0x180067a0c  mov     [rsi+rax*4+50h], ecx
0x180067a10  cmp     r8d, edx
0x180067a13  jb      short loc_1800679FB
0x180067a15  imul    r9d, r14d
0x180067a19  lea     eax, [rdx-8]
0x180067a1c  mov     ecx, [rsi+rax*4+50h]
0x180067a20  mov     eax, edx
0x180067a22  add     ecx, r9d
0x180067a25  inc     edx
0x180067a27  mov     [rsi+rax*4+50h], ecx
0x180067a2b  cmp     edx, 40h ; '@'
0x180067a2e  jb      short loc_180067A19
0x180067a30  jmp     loc_180067B10
0x180067a35  cmp     cs:byte_1800DC8D3, 1
0x180067a3c  jb      short loc_180067A64
0x180067a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a45  mov     r9, rsi
0x180067a48  mov     [rsp+88h+var_60], r8d
0x180067a4d  mov     [rsp+88h+var_68], edi
0x180067a51  mov     rcx, [rcx+88h]
0x180067a58  call    WPP_SF_qdd
0x180067a5d  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a64  mov     ebx, 0C00D36B2h
0x180067a69  test    r10, r10
0x180067a6c  jnz     short loc_180067AB5
0x180067a6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067a75  nop     dword ptr [rax+rax+00h]
0x180067a7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a81  mov     rcx, rax
0x180067a84  test    rax, rax
0x180067a87  jz      short loc_180067AA7
0x180067a89  mov     rax, [rax]
0x180067a8c  mov     edx, 7F0h
0x180067a91  mov     rax, [rax+8]
0x180067a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a9a  test    eax, eax
0x180067a9c  jz      short loc_180067AA7
0x180067a9e  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067aa5  jmp     short loc_180067AB5
0x180067aa7  lea     r10, qword_1800DBF70
0x180067aae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r10; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ab5  cmp     byte ptr [r10+8], 0
0x180067aba  jz      short loc_180067AE4
0x180067abc  mov     rcx, r10; this
0x180067abf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067ac4  cmp     [rax+7CCh], ebx
0x180067aca  jz      short loc_180067AE4
0x180067acc  mov     r9d, ebx; int
0x180067acf  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x180067ad6  mov     r8d, 268h; int
0x180067adc  mov     rcx, rax; this
0x180067adf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067ae4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067aeb  jb      short loc_180067B10
0x180067aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180067af4  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067afb  mov     edx, 3Fh ; '?'
0x180067b00  mov     [rsp+88h+var_68], ebx
0x180067b04  mov     r9, rsi
0x180067b07  mov     rcx, [rcx+10h]
0x180067b0b  call    WPP_SF_qD
0x180067b10  lea     rcx, [rsp+88h+var_58]; this
0x180067b15  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067b1a  mov     eax, ebx
0x180067b1c  mov     rcx, [rsp+88h+var_40]
0x180067b21  xor     rcx, rsp; StackCookie
0x180067b24  call    __security_check_cookie
0x180067b29  add     rsp, 58h
0x180067b2d  pop     r15
0x180067b2f  pop     r14
0x180067b31  pop     rdi
0x180067b32  pop     rsi
0x180067b33  pop     rbp
0x180067b34  pop     rbx
0x180067b35  retn
```
