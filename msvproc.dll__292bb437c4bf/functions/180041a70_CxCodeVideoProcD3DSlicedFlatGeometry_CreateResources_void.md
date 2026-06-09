# CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources(void)

- ea: `0x180041a70`
- end: `0x180041c94`
- name: `?CreateResources@CxCodeVideoProcD3DSlicedFlatGeometry@@UEAAJXZ`
- size: `548`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DSlicedFlatGeometry *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180041a70`
- `0x180068c10`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041bb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041bb6`

## string_xrefs

- `0x180041a7d`: `CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources`
- `0x180041b62`: `CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources`
- `0x180041c0d`: `CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources(CxCodeVideoProcD3DSlicedFlatGeometry *this)
{
  bool v2; // al
  bool v3; // zf
  bool v4; // al
  int Resources; // edi
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v14,
    "CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources",
    281);
  v2 = *((float *)this + 7) == 0.0
    && *((float *)this + 6) == 0.0
    && *((float *)this + 8) == 1.0
    && *((float *)this + 9) == 1.0;
  v3 = *((_DWORD *)this + 4) == 0;
  *((_BYTE *)this + 41) = v2;
  v4 = v3 && !*((_DWORD *)this + 5);
  *((_BYTE *)this + 42) = v4;
  Resources = CxCodeVideoProcD3DFlatGeometry::CreateResources(this);
  if ( Resources >= 0 )
  {
    Resources = (***((__int64 (__fastcall ****)(_QWORD, _QWORD))this + 7))(
                  *((_QWORD *)this + 7),
                  *((unsigned int *)this + 12));
    if ( Resources < 0 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Resources )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources",
            298,
            Resources);
      }
      if ( g_wppLevels )
      {
        v9 = 28;
        goto LABEL_33;
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
      if ( *((_DWORD *)v8 + 499) != Resources )
        CallStackContext::TraceFailure(v8, "CxCodeVideoProcD3DSlicedFlatGeometry::CreateResources", 296, Resources);
    }
    if ( g_wppLevels )
    {
      v9 = 27;
LABEL_33:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids,
        this,
        Resources);
    }
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      29,
      &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids,
      this,
      Resources);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)Resources;
}

```

## disassembly

```asm
0x180041a70  mov     [rsp+arg_8], rbx
0x180041a75  push    rdi
0x180041a76  sub     rsp, 30h
0x180041a7a  mov     rbx, rcx
0x180041a7d  lea     rdx, aCxcodevideopro_36; "CxCodeVideoProcD3DSlicedFlatGeometry::C"...
0x180041a84  lea     rcx, [rsp+38h+arg_0]; this
0x180041a89  mov     r8d, 119h; int
0x180041a8f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180041a94  movss   xmm0, dword ptr [rbx+1Ch]
0x180041a99  xorps   xmm1, xmm1
0x180041a9c  ucomiss xmm0, xmm1
0x180041a9f  jp      short loc_180041AD3
0x180041aa1  jnz     short loc_180041AD3
0x180041aa3  movss   xmm0, dword ptr [rbx+18h]
0x180041aa8  ucomiss xmm0, xmm1
0x180041aab  jp      short loc_180041AD3
0x180041aad  jnz     short loc_180041AD3
0x180041aaf  movss   xmm0, dword ptr [rbx+20h]
0x180041ab4  movss   xmm1, cs:__real@3f800000
0x180041abc  ucomiss xmm0, xmm1
0x180041abf  jp      short loc_180041AD3
0x180041ac1  jnz     short loc_180041AD3
0x180041ac3  movss   xmm0, dword ptr [rbx+24h]
0x180041ac8  ucomiss xmm0, xmm1
0x180041acb  jp      short loc_180041AD3
0x180041acd  jnz     short loc_180041AD3
0x180041acf  mov     al, 1
0x180041ad1  jmp     short loc_180041AD5
0x180041ad3  xor     al, al
0x180041ad5  cmp     dword ptr [rbx+10h], 0
0x180041ad9  mov     [rbx+29h], al
0x180041adc  jnz     short loc_180041AE8
0x180041ade  cmp     dword ptr [rbx+14h], 0
0x180041ae2  jnz     short loc_180041AE8
0x180041ae4  mov     al, 1
0x180041ae6  jmp     short loc_180041AEA
0x180041ae8  xor     al, al
0x180041aea  mov     rcx, rbx; this
0x180041aed  mov     [rbx+2Ah], al
0x180041af0  call    ?CreateResources@CxCodeVideoProcD3DFlatGeometry@@UEAAJXZ; CxCodeVideoProcD3DFlatGeometry::CreateResources(void)
0x180041af5  mov     edi, eax
0x180041af7  test    eax, eax
0x180041af9  jns     loc_180041B8E
0x180041aff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041b06  test    rcx, rcx
0x180041b09  jnz     short loc_180041B4C
0x180041b0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041b11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041b18  mov     rcx, rax
0x180041b1b  test    rax, rax
0x180041b1e  jz      short loc_180041B3E
0x180041b20  mov     rax, [rax]
0x180041b23  mov     edx, 7F0h
0x180041b28  mov     rax, [rax+8]
0x180041b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b31  test    eax, eax
0x180041b33  jz      short loc_180041B3E
0x180041b35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041b3c  jmp     short loc_180041B4C
0x180041b3e  lea     rcx, qword_180153440; this
0x180041b45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041b4c  cmp     byte ptr [rcx+8], 0
0x180041b50  jz      short loc_180041B77
0x180041b52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041b57  cmp     [rax+7CCh], edi
0x180041b5d  jz      short loc_180041B77
0x180041b5f  mov     r9d, edi; int
0x180041b62  lea     rdx, aCxcodevideopro_36; "CxCodeVideoProcD3DSlicedFlatGeometry::C"...
0x180041b69  mov     r8d, 128h; int
0x180041b6f  mov     rcx, rax; this
0x180041b72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041b77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041b7e  jb      loc_180041C4E
0x180041b84  mov     edx, 1Bh
0x180041b89  jmp     loc_180041C30
0x180041b8e  mov     rcx, [rbx+38h]
0x180041b92  mov     edx, [rbx+30h]
0x180041b95  mov     rax, [rcx]
0x180041b98  mov     rax, [rax]
0x180041b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ba0  mov     edi, eax
0x180041ba2  test    eax, eax
0x180041ba4  jns     loc_180041C4E
0x180041baa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041bb1  test    rcx, rcx
0x180041bb4  jnz     short loc_180041BF7
0x180041bb6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041bbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041bc3  mov     rcx, rax
0x180041bc6  test    rax, rax
0x180041bc9  jz      short loc_180041BE9
0x180041bcb  mov     rax, [rax]
0x180041bce  mov     edx, 7F0h
0x180041bd3  mov     rax, [rax+8]
0x180041bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bdc  test    eax, eax
0x180041bde  jz      short loc_180041BE9
0x180041be0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041be7  jmp     short loc_180041BF7
0x180041be9  lea     rcx, qword_180153440; this
0x180041bf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041bf7  cmp     byte ptr [rcx+8], 0
0x180041bfb  jz      short loc_180041C22
0x180041bfd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041c02  cmp     [rax+7CCh], edi
0x180041c08  jz      short loc_180041C22
0x180041c0a  mov     r9d, edi; int
0x180041c0d  lea     rdx, aCxcodevideopro_36; "CxCodeVideoProcD3DSlicedFlatGeometry::C"...
0x180041c14  mov     r8d, 12Ah; int
0x180041c1a  mov     rcx, rax; this
0x180041c1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041c22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041c29  jb      short loc_180041C4E
0x180041c2b  mov     edx, 1Ch
0x180041c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c37  lea     r8, WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids
0x180041c3e  mov     r9, rbx
0x180041c41  mov     [rsp+38h+var_18], edi
0x180041c45  mov     rcx, [rcx+10h]
0x180041c49  call    WPP_SF_qD
0x180041c4e  cmp     cs:byte_180153DE0, 20h ; ' '
0x180041c55  jb      short loc_180041C7D
0x180041c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c5e  lea     r8, WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids
0x180041c65  mov     edx, 1Dh
0x180041c6a  mov     [rsp+38h+var_18], edi
0x180041c6e  mov     r9, rbx
0x180041c71  mov     rcx, [rcx+150h]
0x180041c78  call    WPP_SF_qD
0x180041c7d  lea     rcx, [rsp+38h+arg_0]; this
0x180041c82  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180041c87  mov     rbx, [rsp+38h+arg_8]
0x180041c8c  mov     eax, edi
0x180041c8e  add     rsp, 30h
0x180041c92  pop     rdi
0x180041c93  retn
```
