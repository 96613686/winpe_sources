# CMF2DMediaBuffer::SetBufferReadOnly(int)

- ea: `0x1800649f0`
- end: `0x180064b48`
- name: `?SetBufferReadOnly@CMF2DMediaBuffer@@UEAAJH@Z`
- size: `344`
- prototype: `__int64 __fastcall(CMF2DMediaBuffer *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18002312c`
- `0x180045060`
- `0x180056638`
- `0x1800649f0`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ace`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a95`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180064a85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180064a85`

## string_xrefs

- `0x180064a38`: `CMF2DMediaBuffer::SetBufferReadOnly`
- `0x180064ae5`: `CMF2DMediaBuffer::SetBufferReadOnly`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMF2DMediaBuffer::SetBufferReadOnly(CMF2DMediaBuffer *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v5; // esi
  int v6; // eax
  char *v7; // r14
  CallStackTracing *v8; // rbx
  CallStackContext *v9; // rdi
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  CallStackTracing *v12; // rcx
  __int64 v13; // rax
  char v15; // [rsp+78h] [rbp+10h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 64));
  v5 = 0;
  v6 = a2 != 0;
  v7 = (char *)this - 120;
  if ( v6 != *((_DWORD *)this + 29) )
  {
    if ( *((_DWORD *)this + 6) )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v15, "CMF2DMediaBuffer::SetBufferReadOnly", 791);
      v5 = -2147024179;
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v9 = (CallStackTracing *)((char *)v8 + 208);
        LastError = GetLastError();
        Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v8 + 3));
        if ( Value )
        {
          v9 = Value;
        }
        else if ( !GetLastError() )
        {
          v12 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v12 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v13 = (**(__int64 (__fastcall ***)(CallStackTracing *))v12)(v12);
          if ( v13 )
            v9 = (CallStackContext *)v13;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v9 + 499) != -2147024179 )
          CallStackContext::TraceFailure(v9, "CMF2DMediaBuffer::SetBufferReadOnly", 791, -2147024179);
      }
      if ( g_wppLevels )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_4914b0c617f436cdc4f55e71727dbf4b_Traceguids,
          v7,
          -2147024179);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
    }
    else
    {
      *((_DWORD *)this + 29) = v6;
    }
  }
  LeaveCriticalSection(v4);
  return v5;
}

```

## disassembly

```asm
0x1800649f0  push    rbx
0x1800649f2  push    rbp
0x1800649f3  push    rsi
0x1800649f4  push    rdi
0x1800649f5  push    r14
0x1800649f7  push    r15
0x1800649f9  sub     rsp, 38h
0x1800649fd  mov     ebx, edx
0x1800649ff  mov     rdi, rcx
0x180064a02  lea     rbp, [rcx-40h]
0x180064a06  mov     rcx, rbp; lpCriticalSection
0x180064a09  call    cs:__imp_EnterCriticalSection
0x180064a0f  xor     esi, esi
0x180064a11  xor     eax, eax
0x180064a13  test    ebx, ebx
0x180064a15  setnz   al
0x180064a18  lea     r14, [rdi-78h]
0x180064a1c  cmp     eax, [r14+0ECh]
0x180064a23  jz      loc_180064B2F
0x180064a29  cmp     [rdi+18h], esi
0x180064a2c  jbe     loc_180064B2C
0x180064a32  mov     r8d, 317h; int
0x180064a38  lea     rdx, aCmf2dmediabuff_16; "CMF2DMediaBuffer::SetBufferReadOnly"
0x180064a3f  lea     rcx, [rsp+68h+arg_8]; this
0x180064a44  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180064a49  mov     esi, 800702CDh
0x180064a4e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064a55  test    rbx, rbx
0x180064a58  jnz     short loc_180064A68
0x180064a5a  lea     rbx, qword_18009CF60
0x180064a61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180064a68  cmp     byte ptr [rbx+8], 0
0x180064a6c  jz      loc_180064AF4
0x180064a72  lea     rdi, [rbx+0D0h]
0x180064a79  call    cs:__imp_GetLastError
0x180064a7f  mov     r15d, eax
0x180064a82  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180064a85  call    cs:__imp_TlsGetValue
0x180064a8b  test    rax, rax
0x180064a8e  jz      short loc_180064A95
0x180064a90  mov     rdi, rax
0x180064a93  jmp     short loc_180064ACB
0x180064a95  call    cs:__imp_GetLastError
0x180064a9b  test    eax, eax
0x180064a9d  jnz     short loc_180064ACB
0x180064a9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064aa6  test    rcx, rcx
0x180064aa9  jnz     short loc_180064AB9
0x180064aab  lea     rcx, qword_18009CF60
0x180064ab2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180064ab9  mov     rax, [rcx]
0x180064abc  mov     rax, [rax]
0x180064abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ac4  test    rax, rax
0x180064ac7  cmovnz  rdi, rax
0x180064acb  mov     ecx, r15d; dwErrCode
0x180064ace  call    cs:__imp_SetLastError
0x180064ad4  cmp     [rdi+7CCh], esi
0x180064ada  jz      short loc_180064AF4
0x180064adc  mov     r9d, esi; int
0x180064adf  mov     r8d, 317h; int
0x180064ae5  lea     rdx, aCmf2dmediabuff_16; "CMF2DMediaBuffer::SetBufferReadOnly"
0x180064aec  mov     rcx, rdi; this
0x180064aef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180064af4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064afb  jb      short loc_180064B20
0x180064afd  mov     edx, 3Ch ; '<'
0x180064b02  mov     [rsp+68h+var_48], esi
0x180064b06  mov     r9, r14
0x180064b09  lea     r8, WPP_4914b0c617f436cdc4f55e71727dbf4b_Traceguids
0x180064b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180064b17  mov     rcx, [rcx+10h]
0x180064b1b  call    WPP_SF_qd
0x180064b20  lea     rcx, [rsp+68h+arg_8]; this
0x180064b25  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180064b2a  jmp     short loc_180064B2F
0x180064b2c  mov     [rdi+74h], eax
0x180064b2f  mov     rcx, rbp; lpCriticalSection
0x180064b32  call    cs:__imp_LeaveCriticalSection
0x180064b38  nop
0x180064b39  mov     eax, esi
0x180064b3b  add     rsp, 38h
0x180064b3f  pop     r15
0x180064b41  pop     r14
0x180064b43  pop     rdi
0x180064b44  pop     rsi
0x180064b45  pop     rbp
0x180064b46  pop     rbx
0x180064b47  retn
```
