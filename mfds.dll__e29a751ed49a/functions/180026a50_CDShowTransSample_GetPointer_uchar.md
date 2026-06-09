# CDShowTransSample::GetPointer(uchar * *)

- ea: `0x180026a50`
- end: `0x180026df7`
- name: `?GetPointer@CDShowTransSample@@UEAAJPEAPEAE@Z`
- size: `935`
- prototype: `__int64 __fastcall(CDShowTransSample *__hidden this, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002820`
- `0x1800140b0`
- `0x180026a50`
- `0x180032a50`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026af3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026af3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026bea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026ad8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026b6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026ad8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026b6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026cbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026da8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026cbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026da8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDShowTransSample::GetPointer(CDShowTransSample *this, unsigned __int8 **a2)
{
  int v4; // esi
  unsigned __int8 **v5; // rdi
  CallStackTracing *v7; // rbp
  char *v8; // rsi
  DWORD LastError; // r15d
  char *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  CallStackTracing *v13; // rbp
  GUID *v14; // rbx
  DWORD v15; // r15d
  GUID *v16; // rax
  int v17; // eax
  int v18; // eax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  CallStackTracing *v26; // rax
  CallStackTracing *v27; // rax
  char v28; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 5) )
  {
    v4 = 0;
    v5 = (unsigned __int8 **)((char *)this + 48);
    if ( !*((_QWORD *)this + 6) )
    {
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v7 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v8 = (char *)v7 + 208;
        LastError = GetLastError();
        Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
        if ( Value )
        {
          v8 = Value;
        }
        else if ( !GetLastError() )
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v19 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
          if ( v20 )
            v8 = (char *)v20;
        }
        SetLastError(LastError);
        v11 = *((unsigned int *)v8 + 497);
        if ( (unsigned int)v11 < *((_DWORD *)v8 + 498) )
        {
          v12 = 2 * v11;
          *(_QWORD *)&v8[8 * v12] = "CDShowTransSample::GetPointer";
          *(_DWORD *)&v8[8 * v12 + 8] = 204;
        }
        ++*((_DWORD *)v8 + 497);
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
             *((_QWORD *)this + 5),
             v5,
             0,
             0);
      if ( v4 < 0 )
      {
        v24 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransSample::GetPointer", 204, v4);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v4);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
        return (unsigned int)v4;
      }
      v13 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v14 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
        v15 = GetLastError();
        v16 = (GUID *)TlsGetValue(*((_DWORD *)v13 + 3));
        if ( v16 )
        {
          v14 = v16;
        }
        else if ( !GetLastError() )
        {
          v21 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v21 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
          if ( v22 )
            v14 = (GUID *)v22;
        }
        SetLastError(v15);
        v17 = *(_DWORD *)&v14[124].Data2;
        if ( v17 )
        {
          v18 = v17 - 1;
          *(_DWORD *)&v14[124].Data2 = v18;
          if ( !v18 )
          {
            *(_DWORD *)&v14[124].Data2 = 0;
            v14[125] = GUID_00000000_0000_0000_0000_000000000000;
            *(_QWORD *)&v14[126].Data1 = 0;
            *(_DWORD *)&v14[124].Data4[4] = 0;
            *(_DWORD *)v14[126].Data4 = 0;
            v14[124].Data1 = GetCurrentThreadId();
          }
        }
      }
    }
    *a2 = *v5;
    return (unsigned int)v4;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180026a50  mov     [rsp+arg_8], rbx
0x180026a55  mov     [rsp+arg_10], rbp
0x180026a5a  push    rsi
0x180026a5b  push    rdi
0x180026a5c  push    r12
0x180026a5e  push    r14
0x180026a60  push    r15
0x180026a62  sub     rsp, 30h
0x180026a66  mov     r14, rdx
0x180026a69  mov     rbx, rcx
0x180026a6c  cmp     qword ptr [rcx+28h], 0
0x180026a71  jz      loc_180026C01
0x180026a77  xor     esi, esi
0x180026a79  lea     rdi, [rcx+30h]
0x180026a7d  cmp     [rdi], rsi
0x180026a80  jz      short loc_180026AA2
0x180026a82  mov     rax, [rdi]
0x180026a85  mov     [r14], rax
0x180026a88  mov     eax, esi
0x180026a8a  mov     rbx, [rsp+58h+arg_8]
0x180026a8f  mov     rbp, [rsp+58h+arg_10]
0x180026a94  add     rsp, 30h
0x180026a98  pop     r15
0x180026a9a  pop     r14
0x180026a9c  pop     r12
0x180026a9e  pop     rdi
0x180026a9f  pop     rsi
0x180026aa0  retn
0x180026aa2  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026aa9  test    rbp, rbp
0x180026aac  jz      loc_180026CF4
0x180026ab2  lea     r12, aCdshowtranssam; "CDShowTransSample::GetPointer"
0x180026ab9  cmp     [rbp+8], sil
0x180026abd  jz      short loc_180026B22
0x180026abf  lea     rsi, [rbp+0D0h]
0x180026ac6  call    cs:__imp_GetLastError
0x180026acd  nop     dword ptr [rax+rax+00h]
0x180026ad2  mov     r15d, eax
0x180026ad5  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x180026ad8  call    cs:__imp_TlsGetValue
0x180026adf  nop     dword ptr [rax+rax+00h]
0x180026ae4  test    rax, rax
0x180026ae7  jz      loc_180026C0B
0x180026aed  mov     rsi, rax
0x180026af0  mov     ecx, r15d; dwErrCode
0x180026af3  call    cs:__imp_SetLastError
0x180026afa  nop     dword ptr [rax+rax+00h]
0x180026aff  mov     eax, [rsi+7C4h]
0x180026b05  cmp     eax, [rsi+7C8h]
0x180026b0b  jnb     short loc_180026B1C
0x180026b0d  add     rax, rax
0x180026b10  mov     [rsi+rax*8], r12
0x180026b14  mov     dword ptr [rsi+rax*8+8], 0CCh
0x180026b1c  inc     dword ptr [rsi+7C4h]
0x180026b22  mov     rcx, [rbx+28h]
0x180026b26  mov     rax, [rcx]
0x180026b29  xor     r9d, r9d
0x180026b2c  xor     r8d, r8d
0x180026b2f  mov     rdx, rdi
0x180026b32  mov     rax, [rax+18h]
0x180026b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b3b  mov     esi, eax
0x180026b3d  test    eax, eax
0x180026b3f  js      loc_180026CAB
0x180026b45  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b4c  cmp     byte ptr [rbp+8], 0
0x180026b50  jz      loc_180026A82
0x180026b56  lea     rbx, [rbp+0D0h]
0x180026b5d  call    cs:__imp_GetLastError
0x180026b64  nop     dword ptr [rax+rax+00h]
0x180026b69  mov     r15d, eax
0x180026b6c  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x180026b6f  call    cs:__imp_TlsGetValue
0x180026b76  nop     dword ptr [rax+rax+00h]
0x180026b7b  test    rax, rax
0x180026b7e  jz      loc_180026C46
0x180026b84  mov     rbx, rax
0x180026b87  mov     ecx, r15d; dwErrCode
0x180026b8a  call    cs:__imp_SetLastError
0x180026b91  nop     dword ptr [rax+rax+00h]
0x180026b96  mov     eax, [rbx+7C4h]
0x180026b9c  test    eax, eax
0x180026b9e  jz      loc_180026A82
0x180026ba4  sub     eax, 1
0x180026ba7  mov     [rbx+7C4h], eax
0x180026bad  jnz     loc_180026A82
0x180026bb3  mov     dword ptr [rbx+7C4h], 0
0x180026bbd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180026bc4  movups  xmmword ptr [rbx+7D0h], xmm0
0x180026bcb  mov     qword ptr [rbx+7E0h], 0
0x180026bd6  mov     dword ptr [rbx+7CCh], 0
0x180026be0  mov     dword ptr [rbx+7E8h], 0
0x180026bea  call    cs:__imp_GetCurrentThreadId
0x180026bf1  nop     dword ptr [rax+rax+00h]
0x180026bf6  mov     [rbx+7C0h], eax
0x180026bfc  jmp     loc_180026A82
0x180026c01  mov     eax, 8007000Eh
0x180026c06  jmp     loc_180026A8A
0x180026c0b  call    cs:__imp_GetLastError
0x180026c12  nop     dword ptr [rax+rax+00h]
0x180026c17  test    eax, eax
0x180026c19  jnz     loc_180026AF0
0x180026c1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026c26  test    rcx, rcx
0x180026c29  jz      loc_180026D05
0x180026c2f  mov     rax, [rcx]
0x180026c32  mov     rax, [rax]
0x180026c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c3a  test    rax, rax
0x180026c3d  cmovnz  rsi, rax
0x180026c41  jmp     loc_180026AF0
0x180026c46  call    cs:__imp_GetLastError
0x180026c4d  nop     dword ptr [rax+rax+00h]
0x180026c52  test    eax, eax
0x180026c54  jnz     loc_180026B87
0x180026c5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026c61  test    rcx, rcx
0x180026c64  jz      loc_180026DA8
0x180026c6a  mov     rax, [rcx]
0x180026c6d  mov     rax, [rax]
0x180026c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c75  test    rax, rax
0x180026c78  cmovnz  rbx, rax
0x180026c7c  jmp     loc_180026B87
0x180026c81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026c86  cmp     [rax+7CCh], esi
0x180026c8c  jz      loc_180026D6C
0x180026c92  mov     r9d, esi; int
0x180026c95  mov     r8d, 0CCh; int
0x180026c9b  mov     rdx, r12; char *
0x180026c9e  mov     rcx, rax; this
0x180026ca1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026ca6  jmp     loc_180026D6C
0x180026cab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026cb2  test    rcx, rcx
0x180026cb5  jnz     loc_180026D62
0x180026cbb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026cc2  nop     dword ptr [rax+rax+00h]
0x180026cc7  mov     rcx, rax
0x180026cca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026cd1  test    rax, rax
0x180026cd4  jz      short loc_180026D54
0x180026cd6  mov     rax, [rax]
0x180026cd9  mov     edx, 7F0h
0x180026cde  mov     rax, [rax+8]
0x180026ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce7  test    eax, eax
0x180026ce9  jz      short loc_180026D54
0x180026ceb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026cf2  jmp     short loc_180026D62
0x180026cf4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026cf9  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d00  jmp     loc_180026AB2
0x180026d05  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026d0c  nop     dword ptr [rax+rax+00h]
0x180026d11  mov     rcx, rax
0x180026d14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d1b  test    rax, rax
0x180026d1e  jz      short loc_180026D41
0x180026d20  mov     rax, [rax]
0x180026d23  mov     edx, 7F0h
0x180026d28  mov     rax, [rax+8]
0x180026d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d31  test    eax, eax
0x180026d33  jz      short loc_180026D41
0x180026d35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d3c  jmp     loc_180026C2F
0x180026d41  lea     rcx, qword_1800EB130
0x180026d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d4f  jmp     loc_180026C2F
0x180026d54  lea     rcx, qword_1800EB130; this
0x180026d5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d62  cmp     byte ptr [rcx+8], 0
0x180026d66  jnz     loc_180026C81
0x180026d6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026d73  jb      short loc_180026D99
0x180026d75  mov     edx, 0Ah
0x180026d7a  mov     [rsp+58h+var_38], esi
0x180026d7e  mov     r9, rbx
0x180026d81  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x180026d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d8f  mov     rcx, [rcx+10h]
0x180026d93  call    WPP_SF_qD
0x180026d98  nop
0x180026d99  lea     rcx, [rsp+58h+arg_0]; this
0x180026d9e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026da3  jmp     loc_180026A88
0x180026da8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026daf  nop     dword ptr [rax+rax+00h]
0x180026db4  mov     rcx, rax
0x180026db7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026dbe  test    rax, rax
0x180026dc1  jz      short loc_180026DE4
0x180026dc3  mov     rax, [rax]
0x180026dc6  mov     edx, 7F0h
0x180026dcb  mov     rax, [rax+8]
0x180026dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dd4  test    eax, eax
0x180026dd6  jz      short loc_180026DE4
0x180026dd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ddf  jmp     loc_180026C6A
0x180026de4  lea     rcx, qword_1800EB130
0x180026deb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026df2  jmp     loc_180026C6A
```
