# CMFVideoThumbnail::CalcOffsetsForComparison(uint,uint,uint,uint,_MFVideoArea const &)

- ea: `0x180049364`
- end: `0x1800495c8`
- name: `?CalcOffsetsForComparison@CMFVideoThumbnail@@AEAAJIIIIAEBU_MFVideoArea@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, const struct _MFVideoArea *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004cc48`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180049364`
- `0x18004c890`
- `0x180050678`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049506`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049506`

## string_xrefs

- `0x180049383`: `CMFVideoThumbnail::CalcOffsetsForComparison`
- `0x180049561`: `CMFVideoThumbnail::CalcOffsetsForComparison`

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
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  LONG cx; // edi
  LONG cy; // r8d
  int v14; // r11d
  unsigned int v15; // ebx
  unsigned int v16; // edx
  unsigned int i; // r8d
  __int64 v18; // rax
  int v19; // ecx
  int v20; // r14d
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 *v26; // r10
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[8]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v31[16]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CMFVideoThumbnail::CalcOffsetsForComparison",
    603);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v31);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  cx = a6->Area.cx;
  cy = a6->Area.cy;
  if ( cx / 14 && (v14 = cy / 14) != 0 )
  {
    v15 = 0;
    v16 = 8;
    *((_DWORD *)this + 20) = a3 * (a6->OffsetX.value + cx / 4) + a4 * (cy / 4 + a6->OffsetY.value);
    for ( i = 1; i < 8; ++i )
    {
      v18 = i;
      v19 = a3 * (cx / 14) + *((_DWORD *)this + i + 19);
      *((_DWORD *)this + v18 + 20) = v19;
    }
    v20 = v14 * a4;
    do
    {
      v21 = v16;
      v22 = v20 + *((_DWORD *)this + v16 + 12);
      ++v16;
      *((_DWORD *)this + v21 + 20) = v22;
    }
    while ( v16 < 0x40 );
  }
  else
  {
    if ( _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel() )
    {
      WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 17), v23, v25, this, cx, v25);
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    v15 = -1072875854;
    if ( !v26 )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v28, "CMFVideoThumbnail::CalcOffsetsForComparison", 616, -1072875854);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        -1072875854);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return v15;
}

```

## disassembly

```asm
0x180049364  push    rbx
0x180049366  push    rbp
0x180049367  push    rsi
0x180049368  push    rdi
0x180049369  push    r14
0x18004936b  push    r15
0x18004936d  sub     rsp, 58h
0x180049371  mov     rax, cs:__security_cookie
0x180049378  xor     rax, rsp
0x18004937b  mov     [rsp+88h+var_40], rax
0x180049380  mov     r15d, r8d
0x180049383  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x18004938a  mov     rsi, rcx
0x18004938d  mov     r8d, 25Bh; int
0x180049393  lea     rcx, [rsp+88h+var_58]; this
0x180049398  mov     r14d, r9d
0x18004939b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800493a0  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800493a7  cmp     byte ptr [r10+8], 0
0x1800493ac  jz      short loc_18004940E
0x1800493ae  cmp     qword ptr [rsi+190h], 0
0x1800493b6  jz      short loc_18004940E
0x1800493b8  mov     rcx, r10; this
0x1800493bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800493c0  mov     rcx, [rsi+190h]
0x1800493c7  mov     rdi, rax
0x1800493ca  mov     rdx, [rcx]
0x1800493cd  mov     rax, [rdx+128h]
0x1800493d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493d9  mov     rcx, [rsi+190h]
0x1800493e0  mov     ebx, eax
0x1800493e2  mov     rdx, [rcx]
0x1800493e5  mov     rax, [rdx+118h]
0x1800493ec  lea     rdx, [rsp+88h+var_50]
0x1800493f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493f6  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800493fd  movups  xmm0, xmmword ptr [rax]
0x180049400  mov     [rdi+7E0h], ebx
0x180049406  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004940e  mov     rbp, [rsp+88h+arg_28]
0x180049416  mov     r11d, 92492493h
0x18004941c  mov     eax, r11d
0x18004941f  mov     edi, [rbp+8]
0x180049422  mov     r8d, [rbp+0Ch]
0x180049426  imul    edi
0x180049428  lea     r9d, [rdi+rdx]
0x18004942c  sar     r9d, 3
0x180049430  mov     ecx, r9d
0x180049433  shr     ecx, 1Fh
0x180049436  add     r9d, ecx
0x180049439  jz      loc_1800494CD
0x18004943f  mov     eax, r11d
0x180049442  imul    r8d
0x180049445  lea     r11d, [r8+rdx]
0x180049449  sar     r11d, 3
0x18004944d  mov     ecx, r11d
0x180049450  shr     ecx, 1Fh
0x180049453  add     r11d, ecx
0x180049456  jz      short loc_1800494CD
0x180049458  movsx   ecx, word ptr [rbp+2]
0x18004945c  mov     eax, r8d
0x18004945f  movsx   r8d, word ptr [rbp+6]
0x180049464  cdq
0x180049465  xor     ebx, ebx
0x180049467  lea     r10d, [rbx+4]
0x18004946b  idiv    r10d
0x18004946e  add     r8d, eax
0x180049471  mov     eax, edi
0x180049473  cdq
0x180049474  imul    r8d, r14d
0x180049478  idiv    r10d
0x18004947b  lea     edx, [rbx+8]
0x18004947e  add     eax, ecx
0x180049480  imul    eax, r15d
0x180049484  add     r8d, eax
0x180049487  mov     [rsi+50h], r8d
0x18004948b  lea     r8d, [rbx+1]
0x18004948f  imul    r9d, r15d
0x180049493  lea     eax, [r8-1]
0x180049497  mov     ecx, [rsi+rax*4+50h]
0x18004949b  mov     eax, r8d
0x18004949e  add     ecx, r9d
0x1800494a1  inc     r8d
0x1800494a4  mov     [rsi+rax*4+50h], ecx
0x1800494a8  cmp     r8d, edx
0x1800494ab  jb      short loc_180049493
0x1800494ad  imul    r14d, r11d
0x1800494b1  lea     eax, [rdx-8]
0x1800494b4  mov     ecx, [rsi+rax*4+50h]
0x1800494b8  mov     eax, edx
0x1800494ba  add     ecx, r14d
0x1800494bd  inc     edx
0x1800494bf  mov     [rsi+rax*4+50h], ecx
0x1800494c3  cmp     edx, 40h ; '@'
0x1800494c6  jb      short loc_1800494B1
0x1800494c8  jmp     loc_1800495A2
0x1800494cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_SOURCES@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel(void)
0x1800494d2  cmp     al, 1
0x1800494d4  jb      short loc_1800494FC
0x1800494d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800494dd  mov     r9, rsi
0x1800494e0  mov     [rsp+88h+var_60], r8d
0x1800494e5  mov     [rsp+88h+var_68], edi
0x1800494e9  mov     rcx, [rcx+88h]
0x1800494f0  call    WPP_SF_qdd
0x1800494f5  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800494fc  mov     ebx, 0C00D36B2h
0x180049501  test    r10, r10
0x180049504  jnz     short loc_180049547
0x180049506  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004950c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049513  mov     rcx, rax
0x180049516  test    rax, rax
0x180049519  jz      short loc_180049539
0x18004951b  mov     rax, [rax]
0x18004951e  mov     edx, 7F0h
0x180049523  mov     rax, [rax+8]
0x180049527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004952c  test    eax, eax
0x18004952e  jz      short loc_180049539
0x180049530  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049537  jmp     short loc_180049547
0x180049539  lea     r10, qword_18006EB20
0x180049540  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r10; CallStackTracing * CallStackTracing::s_wpInstance
0x180049547  cmp     byte ptr [r10+8], 0
0x18004954c  jz      short loc_180049576
0x18004954e  mov     rcx, r10; this
0x180049551  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049556  cmp     [rax+7CCh], ebx
0x18004955c  jz      short loc_180049576
0x18004955e  mov     r9d, ebx; int
0x180049561  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x180049568  mov     r8d, 268h; int
0x18004956e  mov     rcx, rax; this
0x180049571  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049576  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004957b  cmp     al, 1
0x18004957d  jb      short loc_1800495A2
0x18004957f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049586  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004958d  mov     edx, 3Fh ; '?'
0x180049592  mov     [rsp+88h+var_68], ebx
0x180049596  mov     r9, rsi
0x180049599  mov     rcx, [rcx+10h]
0x18004959d  call    WPP_SF_qd
0x1800495a2  lea     rcx, [rsp+88h+var_58]; this
0x1800495a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800495ac  mov     eax, ebx
0x1800495ae  mov     rcx, [rsp+88h+var_40]
0x1800495b3  xor     rcx, rsp; StackCookie
0x1800495b6  call    __security_check_cookie
0x1800495bb  add     rsp, 58h
0x1800495bf  pop     r15
0x1800495c1  pop     r14
0x1800495c3  pop     rdi
0x1800495c4  pop     rsi
0x1800495c5  pop     rbp
0x1800495c6  pop     rbx
0x1800495c7  retn
```
