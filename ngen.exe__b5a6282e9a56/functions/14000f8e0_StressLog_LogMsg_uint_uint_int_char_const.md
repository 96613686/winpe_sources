# StressLog::LogMsg(uint,uint,int,char const *,...)

- ea: `0x14000f8e0`
- end: `0x14000faa1`
- name: `?LogMsg@StressLog@@SAXIIHPEBDZZ`
- size: `449`
- prototype: `void(unsigned int, unsigned int, int, const char *, ...)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140001614`
- `0x14000e4f4`
- `0x14000e5e4`
- `0x14000ee4c`

## callees

- `0x1400010c0`
- `0x14000a148`
- `0x14000f1b8`
- `0x14000f2a4`
- `0x14000f7a8`
- `0x14000f8e0`
- `0x140013200`
- `0x140013334`
- `0x140013f30`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000fa26`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000fa26`

## pseudocode

```c
void StressLog::LogMsg(unsigned int a1, unsigned int a2, int a3, const char *a4, ...)
{
  const char *Format; // r14
  unsigned __int64 v6; // rdi
  unsigned __int8 v7; // si
  __int64 v8; // rbx
  _QWORD *Block; // rax
  ThreadStressLog *ThreadStressLog; // rax
  struct IExecutionEngine *ExecutionEngine; // rax
  unsigned __int64 v12; // rbx
  unsigned __int64 *v13; // rax
  int v14; // eax
  int v15; // edx
  int v16; // r9d
  char Buffer[256]; // [rsp+50h] [rbp-148h] BYREF
  va_list va; // [rsp+1C0h] [rbp+28h] BYREF

  va_start(va, a4);
  Format = a4;
  v6 = a2;
  v7 = a1;
  if ( (a2 & StressLog::theLog) != 0 && a1 <= dword_140027114 )
  {
    v8 = dword_140027130;
    Block = (_QWORD *)__ClrFlsGetBlock();
    if ( Block )
    {
      ThreadStressLog = (ThreadStressLog *)Block[v8];
    }
    else
    {
      ExecutionEngine = GetExecutionEngine();
      ThreadStressLog = (ThreadStressLog *)(*(__int64 (__fastcall **)(struct IExecutionEngine *, _QWORD))(*(_QWORD *)ExecutionEngine + 40LL))(
                                             ExecutionEngine,
                                             (unsigned int)v8);
    }
    if ( !ThreadStressLog )
    {
      ThreadStressLog = StressLog::CreateThreadStressLog();
      if ( !ThreadStressLog )
        return;
    }
    v12 = v6;
    ThreadStressLog::LogMsg(ThreadStressLog, v6, a3, a4, va);
    Format = a4;
  }
  else
  {
    v12 = a2;
  }
  if ( Microsoft_Windows_DotNETRuntimeStressHandle
    && dword_140027184
    && (v7 <= (unsigned __int8)byte_140027188 || !byte_140027188)
    && (!v12 || (v12 & qword_140027170) != 0 && (v12 & qword_140027178) == qword_140027178) )
  {
    v13 = _local_stdio_printf_options();
    v14 = __stdio_common_vsnprintf_s(*v13, Buffer, 0x100u, 0xFFu, Format, 0, va);
    if ( v14 < 0 )
      LOWORD(v14) = -1;
    if ( (unsigned __int16)v14 < 0x100u )
    {
      if ( (unsigned __int16)v14 >= 0x100uLL )
        _report_rangecheckfailure();
      Buffer[(unsigned __int16)v14] = 0;
    }
    Buffer[255] = 0;
    if ( (Microsoft_Windows_DotNETRuntimeStressEnableBits & 1) != 0 )
    {
      LOBYTE(v16) = v7;
      CoTemplate_qcsh(0xFFFF, v15, v6, v16, (__int64)Buffer, g_nClrInstanceId);
    }
  }
}

```

## disassembly

```asm
0x14000f8e0  mov     r11, rsp
0x14000f8e3  mov     [r11+20h], r9
0x14000f8e7  push    rbx
0x14000f8e8  push    rbp
0x14000f8e9  push    rsi
0x14000f8ea  push    rdi
0x14000f8eb  push    r14
0x14000f8ed  push    r15
0x14000f8ef  sub     rsp, 168h
0x14000f8f6  mov     rax, cs:__security_cookie
0x14000f8fd  xor     rax, rsp
0x14000f900  mov     [rsp+198h+var_48], rax
0x14000f908  test    cs:?theLog@StressLog@@2V1@A, edx; StressLog StressLog::theLog
0x14000f90e  lea     rbp, [r11+28h]
0x14000f912  mov     [rsp+198h+var_158], rbp
0x14000f917  mov     r14, r9
0x14000f91a  mov     r15d, r8d
0x14000f91d  mov     edi, edx
0x14000f91f  mov     esi, ecx
0x14000f921  jz      loc_14000F9A7
0x14000f927  cmp     ecx, cs:dword_140027114
0x14000f92d  ja      short loc_14000F9A7
0x14000f92f  mov     ebx, cs:dword_140027130
0x14000f935  mov     rax, cs:?__ClrFlsGetBlock@@3P6APEAXXZEA; void * (*__ClrFlsGetBlock)(void)
0x14000f93c  call    cs:__guard_dispatch_icall_fptr
0x14000f942  test    rax, rax
0x14000f945  jz      short loc_14000F94D
0x14000f947  mov     rax, [rax+rbx*8]
0x14000f94b  jmp     short loc_14000F967
0x14000f94d  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x14000f952  mov     r8, rax
0x14000f955  mov     edx, ebx
0x14000f957  mov     rcx, [rax]
0x14000f95a  mov     rax, [rcx+28h]
0x14000f95e  mov     rcx, r8
0x14000f961  call    cs:__guard_dispatch_icall_fptr
0x14000f967  test    rax, rax
0x14000f96a  jnz     short loc_14000F97A
0x14000f96c  call    ?CreateThreadStressLog@StressLog@@SAPEAVThreadStressLog@@XZ; StressLog::CreateThreadStressLog(void)
0x14000f971  test    rax, rax
0x14000f974  jz      loc_14000FA7B
0x14000f97a  mov     rbp, [rsp+198h+var_158]
0x14000f97f  mov     r8d, r15d; int
0x14000f982  mov     r9, [rsp+198h+arg_18]; char *
0x14000f98a  mov     rdx, rdi; unsigned __int64
0x14000f98d  mov     rcx, rax; this
0x14000f990  mov     [rsp+198h+Format], rbp; char *
0x14000f995  mov     rbx, rdi
0x14000f998  call    ?LogMsg@ThreadStressLog@@QEAAX_KHPEBDPEAD@Z; ThreadStressLog::LogMsg(unsigned __int64,int,char const *,char *)
0x14000f99d  mov     r14, [rsp+198h+arg_18]
0x14000f9a5  jmp     short loc_14000F9AA
0x14000f9a7  mov     rbx, rdi
0x14000f9aa  cmp     cs:Microsoft_Windows_DotNETRuntimeStressHandle, 0
0x14000f9b2  jz      loc_14000FA7B
0x14000f9b8  cmp     cs:dword_140027184, 0
0x14000f9bf  jz      loc_14000FA7B
0x14000f9c5  mov     al, cs:byte_140027188
0x14000f9cb  cmp     sil, al
0x14000f9ce  jbe     short loc_14000F9D8
0x14000f9d0  test    al, al
0x14000f9d2  jnz     loc_14000FA7B
0x14000f9d8  test    rbx, rbx
0x14000f9db  jz      short loc_14000F9FD
0x14000f9dd  test    cs:qword_140027170, rbx
0x14000f9e4  jz      loc_14000FA7B
0x14000f9ea  mov     rax, cs:qword_140027178
0x14000f9f1  and     rax, rbx
0x14000f9f4  cmp     rax, cs:qword_140027178
0x14000f9fb  jnz     short loc_14000FA7B
0x14000f9fd  call    __local_stdio_printf_options
0x14000fa02  mov     ebx, 100h
0x14000fa07  mov     [rsp+198h+ArgList], rbp; ArgList
0x14000fa0c  and     [rsp+198h+var_170], 0
0x14000fa12  lea     rdx, [rsp+198h+Buffer]; Buffer
0x14000fa17  mov     r8d, ebx; BufferCount
0x14000fa1a  mov     [rsp+198h+Format], r14; Format
0x14000fa1f  mov     rcx, [rax]; Options
0x14000fa22  lea     r9d, [rbx-1]; MaxCount
0x14000fa26  call    cs:__imp___stdio_common_vsnprintf_s
0x14000fa2c  test    eax, eax
0x14000fa2e  mov     ecx, 0FFFFh
0x14000fa33  cmovs   ax, cx
0x14000fa37  cmp     ax, bx
0x14000fa3a  jnb     short loc_14000FA49
0x14000fa3c  movzx   eax, ax
0x14000fa3f  cmp     rax, rbx
0x14000fa42  jnb     short loc_14000FA9B
0x14000fa44  mov     [rsp+rax+198h+Buffer], 0
0x14000fa49  test    cs:Microsoft_Windows_DotNETRuntimeStressEnableBits, 1
0x14000fa50  mov     [rsp+198h+var_49], 0
0x14000fa58  jz      short loc_14000FA7B
0x14000fa5a  movzx   eax, cs:?g_nClrInstanceId@@3IA; uint g_nClrInstanceId
0x14000fa61  mov     r9b, sil
0x14000fa64  mov     word ptr [rsp+198h+var_170], ax
0x14000fa69  mov     r8d, edi
0x14000fa6c  lea     rax, [rsp+198h+Buffer]
0x14000fa71  mov     [rsp+198h+Format], rax
0x14000fa76  call    CoTemplate_qcsh
0x14000fa7b  mov     rcx, [rsp+198h+var_48]
0x14000fa83  xor     rcx, rsp; StackCookie
0x14000fa86  call    __security_check_cookie
0x14000fa8b  add     rsp, 168h
0x14000fa92  pop     r15
0x14000fa94  pop     r14
0x14000fa96  pop     rdi
0x14000fa97  pop     rsi
0x14000fa98  pop     rbp
0x14000fa99  pop     rbx
0x14000fa9a  retn
0x14000fa9b  call    __report_rangecheckfailure
```
