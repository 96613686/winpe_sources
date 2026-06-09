# CMFVideoThumbnail::CalcOffsetsForComparison(uint,uint,uint,uint,_MFVideoArea const &)

- ea: `0x180064d5c`
- end: `0x180064fc0`
- name: `?CalcOffsetsForComparison@CMFVideoThumbnail@@AEAAJIIIIAEBU_MFVideoArea@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, const struct _MFVideoArea *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006860c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180064d5c`
- `0x18006c088`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064efe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064efe`

## string_xrefs

- `0x180064d7b`: `CMFVideoThumbnail::CalcOffsetsForComparison`
- `0x180064f59`: `CMFVideoThumbnail::CalcOffsetsForComparison`

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
    if ( byte_1800D78D3 )
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
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180064d5c  push    rbx
0x180064d5e  push    rbp
0x180064d5f  push    rsi
0x180064d60  push    rdi
0x180064d61  push    r14
0x180064d63  push    r15
0x180064d65  sub     rsp, 58h
0x180064d69  mov     rax, cs:__security_cookie
0x180064d70  xor     rax, rsp
0x180064d73  mov     [rsp+88h+var_40], rax
0x180064d78  mov     r15d, r8d
0x180064d7b  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x180064d82  mov     rsi, rcx
0x180064d85  mov     r8d, 25Bh; int
0x180064d8b  lea     rcx, [rsp+88h+var_58]; this
0x180064d90  mov     r14d, r9d
0x180064d93  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180064d98  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064d9f  cmp     byte ptr [r10+8], 0
0x180064da4  jz      short loc_180064E06
0x180064da6  cmp     qword ptr [rsi+190h], 0
0x180064dae  jz      short loc_180064E06
0x180064db0  mov     rcx, r10; this
0x180064db3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180064db8  mov     rcx, [rsi+190h]
0x180064dbf  mov     rdi, rax
0x180064dc2  mov     rdx, [rcx]
0x180064dc5  mov     rax, [rdx+128h]
0x180064dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064dd1  mov     rcx, [rsi+190h]
0x180064dd8  mov     ebx, eax
0x180064dda  mov     rdx, [rcx]
0x180064ddd  mov     rax, [rdx+118h]
0x180064de4  lea     rdx, [rsp+88h+var_50]
0x180064de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064dee  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064df5  movups  xmm0, xmmword ptr [rax]
0x180064df8  mov     [rdi+7E0h], ebx
0x180064dfe  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180064e06  mov     rbp, [rsp+88h+arg_28]
0x180064e0e  mov     r9d, 92492493h
0x180064e14  mov     eax, r9d
0x180064e17  mov     edi, [rbp+8]
0x180064e1a  mov     r8d, [rbp+0Ch]
0x180064e1e  imul    edi
0x180064e20  lea     r11d, [rdi+rdx]
0x180064e24  sar     r11d, 3
0x180064e28  mov     ecx, r11d
0x180064e2b  shr     ecx, 1Fh
0x180064e2e  add     r11d, ecx
0x180064e31  jz      loc_180064EC5
0x180064e37  mov     eax, r9d
0x180064e3a  imul    r8d
0x180064e3d  lea     r9d, [r8+rdx]
0x180064e41  sar     r9d, 3
0x180064e45  mov     ecx, r9d
0x180064e48  shr     ecx, 1Fh
0x180064e4b  add     r9d, ecx
0x180064e4e  jz      short loc_180064EC5
0x180064e50  movsx   ecx, word ptr [rbp+2]
0x180064e54  mov     eax, r8d
0x180064e57  movsx   r8d, word ptr [rbp+6]
0x180064e5c  cdq
0x180064e5d  xor     ebx, ebx
0x180064e5f  lea     r10d, [rbx+4]
0x180064e63  idiv    r10d
0x180064e66  add     r8d, eax
0x180064e69  mov     eax, edi
0x180064e6b  cdq
0x180064e6c  imul    r8d, r14d
0x180064e70  idiv    r10d
0x180064e73  lea     edx, [rbx+8]
0x180064e76  add     eax, ecx
0x180064e78  imul    eax, r15d
0x180064e7c  add     r8d, eax
0x180064e7f  mov     [rsi+50h], r8d
0x180064e83  lea     r8d, [rbx+1]
0x180064e87  imul    r11d, r15d
0x180064e8b  lea     eax, [r8-1]
0x180064e8f  mov     ecx, [rsi+rax*4+50h]
0x180064e93  mov     eax, r8d
0x180064e96  add     ecx, r11d
0x180064e99  inc     r8d
0x180064e9c  mov     [rsi+rax*4+50h], ecx
0x180064ea0  cmp     r8d, edx
0x180064ea3  jb      short loc_180064E8B
0x180064ea5  imul    r9d, r14d
0x180064ea9  lea     eax, [rdx-8]
0x180064eac  mov     ecx, [rsi+rax*4+50h]
0x180064eb0  mov     eax, edx
0x180064eb2  add     ecx, r9d
0x180064eb5  inc     edx
0x180064eb7  mov     [rsi+rax*4+50h], ecx
0x180064ebb  cmp     edx, 40h ; '@'
0x180064ebe  jb      short loc_180064EA9
0x180064ec0  jmp     loc_180064F9A
0x180064ec5  cmp     cs:byte_1800D78D3, 1
0x180064ecc  jb      short loc_180064EF4
0x180064ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180064ed5  mov     r9, rsi
0x180064ed8  mov     [rsp+88h+var_60], r8d
0x180064edd  mov     [rsp+88h+var_68], edi
0x180064ee1  mov     rcx, [rcx+88h]
0x180064ee8  call    WPP_SF_qdd
0x180064eed  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064ef4  mov     ebx, 0C00D36B2h
0x180064ef9  test    r10, r10
0x180064efc  jnz     short loc_180064F3F
0x180064efe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180064f04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f0b  mov     rcx, rax
0x180064f0e  test    rax, rax
0x180064f11  jz      short loc_180064F31
0x180064f13  mov     rax, [rax]
0x180064f16  mov     edx, 7F0h
0x180064f1b  mov     rax, [rax+8]
0x180064f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f24  test    eax, eax
0x180064f26  jz      short loc_180064F31
0x180064f28  mov     r10, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f2f  jmp     short loc_180064F3F
0x180064f31  lea     r10, qword_1800D6F70
0x180064f38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r10; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f3f  cmp     byte ptr [r10+8], 0
0x180064f44  jz      short loc_180064F6E
0x180064f46  mov     rcx, r10; this
0x180064f49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180064f4e  cmp     [rax+7CCh], ebx
0x180064f54  jz      short loc_180064F6E
0x180064f56  mov     r9d, ebx; int
0x180064f59  lea     rdx, aCmfvideothumbn_0; "CMFVideoThumbnail::CalcOffsetsForCompar"...
0x180064f60  mov     r8d, 268h; int
0x180064f66  mov     rcx, rax; this
0x180064f69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180064f6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064f75  jb      short loc_180064F9A
0x180064f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180064f7e  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180064f85  mov     edx, 3Fh ; '?'
0x180064f8a  mov     [rsp+88h+var_68], ebx
0x180064f8e  mov     r9, rsi
0x180064f91  mov     rcx, [rcx+10h]
0x180064f95  call    WPP_SF_qD
0x180064f9a  lea     rcx, [rsp+88h+var_58]; this
0x180064f9f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180064fa4  mov     eax, ebx
0x180064fa6  mov     rcx, [rsp+88h+var_40]
0x180064fab  xor     rcx, rsp; StackCookie
0x180064fae  call    __security_check_cookie
0x180064fb3  add     rsp, 58h
0x180064fb7  pop     r15
0x180064fb9  pop     r14
0x180064fbb  pop     rdi
0x180064fbc  pop     rsi
0x180064fbd  pop     rbp
0x180064fbe  pop     rbx
0x180064fbf  retn
```
