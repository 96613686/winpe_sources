# CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants(uint)

- ea: `0x1800529d8`
- end: `0x180052b27`
- name: `?UpdateShaderConstants@CRolling420FrameStitcherMFTDataHandler@@IEAAJI@Z`
- size: `335`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180043a90`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800529d8`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a4f`

## string_xrefs

- `0x1800529ee`: `CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants`
- `0x180052aa6`: `CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants(
        CRolling420FrameStitcherMFTDataHandler *this,
        int a2)
{
  int v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int128 v8; // [rsp+40h] [rbp-18h] BYREF
  char v9; // [rsp+68h] [rbp+10h] BYREF

  *((_DWORD *)this + 37) = a2;
  v8 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v9,
    "CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants",
    540);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, __int128 *))(**((_QWORD **)this + 8) + 112LL))(
         *((_QWORD *)this + 8),
         *((_QWORD *)this + 14),
         0,
         4,
         0,
         &v8);
  if ( v3 >= 0 )
  {
    *(_OWORD *)v8 = *(_OWORD *)((char *)this + 148);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 120LL))(
      *((_QWORD *)this + 8),
      *((_QWORD *)this + 14),
      0);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CRolling420FrameStitcherMFTDataHandler::UpdateShaderConstants",
          540,
          v3);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v3);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800529d8  mov     [rsp+arg_0], rbx
0x1800529dd  push    rdi
0x1800529de  sub     rsp, 50h
0x1800529e2  mov     [rcx+94h], edx
0x1800529e8  mov     rdi, rcx
0x1800529eb  xorps   xmm0, xmm0
0x1800529ee  lea     rdx, aCrolling420fra_0; "CRolling420FrameStitcherMFTDataHandler:"...
0x1800529f5  lea     rcx, [rsp+58h+arg_8]; this
0x1800529fa  mov     r8d, 21Ch; int
0x180052a00  movups  [rsp+58h+var_18], xmm0
0x180052a05  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052a0a  mov     rcx, [rdi+40h]
0x180052a0e  lea     rdx, [rsp+58h+var_18]
0x180052a13  mov     [rsp+58h+var_30], rdx
0x180052a18  mov     r9d, 4
0x180052a1e  mov     rdx, [rdi+70h]
0x180052a22  xor     r8d, r8d
0x180052a25  mov     [rsp+58h+var_38], 0
0x180052a2d  mov     rax, [rcx]
0x180052a30  mov     rax, [rax+70h]
0x180052a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a39  mov     ebx, eax
0x180052a3b  test    eax, eax
0x180052a3d  jns     loc_180052AE9
0x180052a43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a4a  test    rcx, rcx
0x180052a4d  jnz     short loc_180052A90
0x180052a4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052a55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a5c  mov     rcx, rax
0x180052a5f  test    rax, rax
0x180052a62  jz      short loc_180052A82
0x180052a64  mov     rax, [rax]
0x180052a67  mov     edx, 7F0h
0x180052a6c  mov     rax, [rax+8]
0x180052a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a75  test    eax, eax
0x180052a77  jz      short loc_180052A82
0x180052a79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a80  jmp     short loc_180052A90
0x180052a82  lea     rcx, qword_180153440; this
0x180052a89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a90  cmp     byte ptr [rcx+8], 0
0x180052a94  jz      short loc_180052ABB
0x180052a96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052a9b  cmp     [rax+7CCh], ebx
0x180052aa1  jz      short loc_180052ABB
0x180052aa3  mov     r9d, ebx; int
0x180052aa6  lea     rdx, aCrolling420fra_0; "CRolling420FrameStitcherMFTDataHandler:"...
0x180052aad  mov     r8d, 21Ch; int
0x180052ab3  mov     rcx, rax; this
0x180052ab6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052abb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052ac2  jb      short loc_180052B10
0x180052ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180052acb  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x180052ad2  mov     edx, 4Eh ; 'N'
0x180052ad7  mov     [rsp+58h+var_38], ebx
0x180052adb  mov     r9, rdi
0x180052ade  mov     rcx, [rcx+10h]
0x180052ae2  call    WPP_SF_qD
0x180052ae7  jmp     short loc_180052B10
0x180052ae9  mov     rax, qword ptr [rsp+58h+var_18]
0x180052aee  xor     r8d, r8d
0x180052af1  movups  xmm0, xmmword ptr [rdi+94h]
0x180052af8  movdqu  xmmword ptr [rax], xmm0
0x180052afc  mov     rcx, [rdi+40h]
0x180052b00  mov     rdx, [rdi+70h]
0x180052b04  mov     rax, [rcx]
0x180052b07  mov     rax, [rax+78h]
0x180052b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b10  lea     rcx, [rsp+58h+arg_8]; this
0x180052b15  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180052b1a  mov     eax, ebx
0x180052b1c  mov     rbx, [rsp+58h+arg_0]
0x180052b21  add     rsp, 50h
0x180052b25  pop     rdi
0x180052b26  retn
```
