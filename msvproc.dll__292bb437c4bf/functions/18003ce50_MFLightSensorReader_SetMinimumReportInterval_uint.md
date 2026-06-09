# MFLightSensorReader::SetMinimumReportInterval(uint)

- ea: `0x18003ce50`
- end: `0x18003d0ce`
- name: `?SetMinimumReportInterval@MFLightSensorReader@@QEAAJI@Z`
- size: `638`
- prototype: `__int64 __fastcall(MFLightSensorReader *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800b1790`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18003ce50`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cf22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cff6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cf22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cff6`

## string_xrefs

- `0x18003ce81`: `MFLightSensorReader::SetMinimumReportInterval`
- `0x18003cf86`: `MFLightSensorReader::SetMinimumReportInterval`
- `0x18003d05a`: `MFLightSensorReader::SetMinimumReportInterval`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MFLightSensorReader::SetMinimumReportInterval(MFLightSensorReader *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  unsigned int v11; // ebx
  int v13; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[4]; // [rsp+34h] [rbp-34h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-28h] BYREF

  v13 = 0;
  v15 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v14,
    "MFLightSensorReader::SetMinimumReportInterval",
    57);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 3) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 296LL))(*((_QWORD *)this + 3));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 3) + 280LL))(
                                                            *((_QWORD *)this + 3),
                                                            v16);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  v16[0] = this;
  v16[1] = &v13;
  v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          &v15);
  if ( v13 >= 0 )
  {
    if ( v15 < 0x320 )
      v15 = 800;
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
    if ( v13 >= 0 )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 8u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 25, &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids, this, 800);
    }
    else
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
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( v13 < 0 && *((_DWORD *)v10 + 499) != v13 )
          CallStackContext::TraceFailure(v10, "MFLightSensorReader::SetMinimumReportInterval", 60, v13);
      }
      if ( g_wppLevels )
      {
        v7 = 24;
        goto LABEL_16;
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
      if ( v13 < 0 && *((_DWORD *)v6 + 499) != v13 )
        CallStackContext::TraceFailure(v6, "MFLightSensorReader::SetMinimumReportInterval", 58, v13);
    }
    if ( g_wppLevels )
    {
      v7 = 23;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids, this, v13);
    }
  }
  v11 = v13;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v14);
  return v11;
}

```

## disassembly

```asm
0x18003ce50  push    rbp
0x18003ce52  push    rbx
0x18003ce53  push    rsi
0x18003ce54  push    rdi
0x18003ce55  mov     rbp, rsp
0x18003ce58  sub     rsp, 68h
0x18003ce5c  mov     rax, cs:__security_cookie
0x18003ce63  xor     rax, rsp
0x18003ce66  mov     [rbp+var_18], rax
0x18003ce6a  mov     rsi, rcx
0x18003ce6d  mov     [rbp+var_38], 0
0x18003ce74  mov     [rbp+var_30], 0
0x18003ce7b  mov     r8d, 39h ; '9'; int
0x18003ce81  lea     rdx, aMflightsensorr; "MFLightSensorReader::SetMinimumReportIn"...
0x18003ce88  lea     rcx, [rbp+var_34]; this
0x18003ce8c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ce91  nop
0x18003ce92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003ce99  cmp     byte ptr [rcx+8], 0
0x18003ce9d  jz      short loc_18003CEEB
0x18003ce9f  cmp     qword ptr [rsi+18h], 0
0x18003cea4  jz      short loc_18003CEEB
0x18003cea6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ceab  mov     rdi, rax
0x18003ceae  mov     rcx, [rsi+18h]
0x18003ceb2  mov     rdx, [rcx]
0x18003ceb5  mov     rax, [rdx+128h]
0x18003cebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cec1  mov     ebx, eax
0x18003cec3  mov     rcx, [rsi+18h]
0x18003cec7  mov     rdx, [rcx]
0x18003ceca  mov     rax, [rdx+118h]
0x18003ced1  lea     rdx, [rbp+var_28]
0x18003ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ceda  movups  xmm0, xmmword ptr [rax]
0x18003cedd  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18003cee5  mov     [rdi+7E0h], ebx
0x18003ceeb  mov     [rbp+var_28], rsi
0x18003ceef  lea     rax, [rbp+var_38]
0x18003cef3  mov     [rbp+var_20], rax
0x18003cef7  mov     rcx, [rsi+10h]
0x18003cefb  mov     rax, [rcx]
0x18003cefe  lea     rdx, [rbp+var_30]
0x18003cf02  mov     rax, [rax+38h]
0x18003cf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf0b  mov     [rbp+var_38], eax
0x18003cf0e  test    eax, eax
0x18003cf10  jns     loc_18003CFBE
0x18003cf16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf1d  test    rcx, rcx
0x18003cf20  jnz     short loc_18003CF63
0x18003cf22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003cf28  mov     rcx, rax
0x18003cf2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf32  test    rax, rax
0x18003cf35  jz      short loc_18003CF55
0x18003cf37  mov     rax, [rax]
0x18003cf3a  mov     edx, 7F0h
0x18003cf3f  mov     rax, [rax+8]
0x18003cf43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf48  test    eax, eax
0x18003cf4a  jz      short loc_18003CF55
0x18003cf4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf53  jmp     short loc_18003CF63
0x18003cf55  lea     rcx, qword_180153440; this
0x18003cf5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf63  cmp     byte ptr [rcx+8], 0
0x18003cf67  jz      short loc_18003CF95
0x18003cf69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003cf6e  mov     r9d, [rbp+var_38]; int
0x18003cf72  test    r9d, r9d
0x18003cf75  jns     short loc_18003CF95
0x18003cf77  cmp     [rax+7CCh], r9d
0x18003cf7e  jz      short loc_18003CF95
0x18003cf80  mov     r8d, 3Ah ; ':'; int
0x18003cf86  lea     rdx, aMflightsensorr; "MFLightSensorReader::SetMinimumReportIn"...
0x18003cf8d  mov     rcx, rax; this
0x18003cf90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003cf95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cf9c  jb      loc_18003D0AB
0x18003cfa2  mov     edx, 17h
0x18003cfa7  mov     eax, [rbp+var_38]
0x18003cfaa  mov     [rsp+68h+var_48], eax
0x18003cfae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfb5  mov     rcx, [rcx+10h]
0x18003cfb9  jmp     loc_18003D09C
0x18003cfbe  mov     edx, [rbp+var_30]
0x18003cfc1  mov     ebx, 320h
0x18003cfc6  cmp     edx, ebx
0x18003cfc8  jnb     short loc_18003CFCF
0x18003cfca  mov     edx, ebx
0x18003cfcc  mov     [rbp+var_30], ebx
0x18003cfcf  mov     rcx, [rsi+10h]
0x18003cfd3  mov     rax, [rcx]
0x18003cfd6  mov     rax, [rax+40h]
0x18003cfda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfdf  mov     [rbp+var_38], eax
0x18003cfe2  test    eax, eax
0x18003cfe4  jns     loc_18003D07C
0x18003cfea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cff1  test    rcx, rcx
0x18003cff4  jnz     short loc_18003D037
0x18003cff6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003cffc  mov     rcx, rax
0x18003cfff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d006  test    rax, rax
0x18003d009  jz      short loc_18003D029
0x18003d00b  mov     rax, [rax]
0x18003d00e  mov     edx, 7F0h
0x18003d013  mov     rax, [rax+8]
0x18003d017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d01c  test    eax, eax
0x18003d01e  jz      short loc_18003D029
0x18003d020  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d027  jmp     short loc_18003D037
0x18003d029  lea     rcx, qword_180153440; this
0x18003d030  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d037  cmp     byte ptr [rcx+8], 0
0x18003d03b  jz      short loc_18003D069
0x18003d03d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d042  mov     r9d, [rbp+var_38]; int
0x18003d046  test    r9d, r9d
0x18003d049  jns     short loc_18003D069
0x18003d04b  cmp     [rax+7CCh], r9d
0x18003d052  jz      short loc_18003D069
0x18003d054  mov     r8d, 3Ch ; '<'; int
0x18003d05a  lea     rdx, aMflightsensorr; "MFLightSensorReader::SetMinimumReportIn"...
0x18003d061  mov     rcx, rax; this
0x18003d064  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d069  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d070  jb      short loc_18003D0AB
0x18003d072  mov     edx, 18h
0x18003d077  jmp     loc_18003CFA7
0x18003d07c  cmp     cs:byte_180153DE0, 8
0x18003d083  jb      short loc_18003D0AB
0x18003d085  mov     edx, 19h
0x18003d08a  mov     [rsp+68h+var_48], ebx
0x18003d08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d095  mov     rcx, [rcx+150h]
0x18003d09c  mov     r9, rsi
0x18003d09f  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x18003d0a6  call    WPP_SF_qD
0x18003d0ab  mov     ebx, [rbp+var_38]
0x18003d0ae  lea     rcx, [rbp+var_34]; this
0x18003d0b2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d0b7  mov     eax, ebx
0x18003d0b9  mov     rcx, [rbp+var_18]
0x18003d0bd  xor     rcx, rsp; StackCookie
0x18003d0c0  call    __security_check_cookie
0x18003d0c5  add     rsp, 68h
0x18003d0c9  pop     rdi
0x18003d0ca  pop     rsi
0x18003d0cb  pop     rbx
0x18003d0cc  pop     rbp
0x18003d0cd  retn
```
