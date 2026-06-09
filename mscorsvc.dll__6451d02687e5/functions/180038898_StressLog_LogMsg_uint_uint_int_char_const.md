# StressLog::LogMsg(uint,uint,int,char const *,...)

- ea: `0x180038898`
- end: `0x180038a59`
- name: `?LogMsg@StressLog@@SAXIIHPEBDZZ`
- size: `449`
- prototype: `static void(unsigned int, unsigned int, int, const char *, ...)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180005cec`
- `0x180034fd4`
- `0x1800350c4`
- `0x180038f14`

## callees

- `0x1800177e8`
- `0x1800305a4`
- `0x18003816c`
- `0x180038258`
- `0x180038760`
- `0x180038898`
- `0x18003dc30`
- `0x18003e114`
- `0x18003f280`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800389de`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800389de`

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
  __int64 v15; // rdx
  char Buffer[256]; // [rsp+50h] [rbp-148h] BYREF
  va_list va; // [rsp+1C0h] [rbp+28h] BYREF

  va_start(va, a4);
  Format = a4;
  v6 = a2;
  v7 = a1;
  if ( (a2 & StressLog::theLog) != 0 && a1 <= dword_18006F2F4 )
  {
    v8 = dword_18006F310;
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
    && dword_18006F3B4
    && (v7 <= (unsigned __int8)byte_18006F3B8 || !byte_18006F3B8)
    && (!v12 || (v12 & qword_18006F3A0) != 0 && (v12 & qword_18006F3A8) == qword_18006F3A8) )
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
      CoTemplate_qcsh(0xFFFF, v15, v6, v7, Buffer, g_nClrInstanceId);
  }
}

```

## disassembly

```asm
0x180038898  mov     r11, rsp
0x18003889b  mov     [r11+20h], r9
0x18003889f  push    rbx
0x1800388a0  push    rbp
0x1800388a1  push    rsi
0x1800388a2  push    rdi
0x1800388a3  push    r14
0x1800388a5  push    r15
0x1800388a7  sub     rsp, 168h
0x1800388ae  mov     rax, cs:__security_cookie
0x1800388b5  xor     rax, rsp
0x1800388b8  mov     [rsp+198h+var_48], rax
0x1800388c0  test    cs:?theLog@StressLog@@2V1@A, edx; StressLog StressLog::theLog
0x1800388c6  lea     rbp, [r11+28h]
0x1800388ca  mov     [rsp+198h+var_158], rbp
0x1800388cf  mov     r14, r9
0x1800388d2  mov     r15d, r8d
0x1800388d5  mov     edi, edx
0x1800388d7  mov     esi, ecx
0x1800388d9  jz      loc_18003895F
0x1800388df  cmp     ecx, cs:dword_18006F2F4
0x1800388e5  ja      short loc_18003895F
0x1800388e7  mov     ebx, cs:dword_18006F310
0x1800388ed  mov     rax, cs:?__ClrFlsGetBlock@@3P6APEAXXZEA; void * (*__ClrFlsGetBlock)(void)
0x1800388f4  call    cs:__guard_dispatch_icall_fptr
0x1800388fa  test    rax, rax
0x1800388fd  jz      short loc_180038905
0x1800388ff  mov     rax, [rax+rbx*8]
0x180038903  jmp     short loc_18003891F
0x180038905  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x18003890a  mov     r8, rax
0x18003890d  mov     edx, ebx
0x18003890f  mov     rcx, [rax]
0x180038912  mov     rax, [rcx+28h]
0x180038916  mov     rcx, r8
0x180038919  call    cs:__guard_dispatch_icall_fptr
0x18003891f  test    rax, rax
0x180038922  jnz     short loc_180038932
0x180038924  call    ?CreateThreadStressLog@StressLog@@SAPEAVThreadStressLog@@XZ; StressLog::CreateThreadStressLog(void)
0x180038929  test    rax, rax
0x18003892c  jz      loc_180038A33
0x180038932  mov     rbp, [rsp+198h+var_158]
0x180038937  mov     r8d, r15d; int
0x18003893a  mov     r9, [rsp+198h+arg_18]; char *
0x180038942  mov     rdx, rdi; unsigned __int64
0x180038945  mov     rcx, rax; this
0x180038948  mov     [rsp+198h+Format], rbp; char *
0x18003894d  mov     rbx, rdi
0x180038950  call    ?LogMsg@ThreadStressLog@@QEAAX_KHPEBDPEAD@Z; ThreadStressLog::LogMsg(unsigned __int64,int,char const *,char *)
0x180038955  mov     r14, [rsp+198h+arg_18]
0x18003895d  jmp     short loc_180038962
0x18003895f  mov     rbx, rdi
0x180038962  cmp     cs:Microsoft_Windows_DotNETRuntimeStressHandle, 0
0x18003896a  jz      loc_180038A33
0x180038970  cmp     cs:dword_18006F3B4, 0
0x180038977  jz      loc_180038A33
0x18003897d  mov     al, cs:byte_18006F3B8
0x180038983  cmp     sil, al
0x180038986  jbe     short loc_180038990
0x180038988  test    al, al
0x18003898a  jnz     loc_180038A33
0x180038990  test    rbx, rbx
0x180038993  jz      short loc_1800389B5
0x180038995  test    cs:qword_18006F3A0, rbx
0x18003899c  jz      loc_180038A33
0x1800389a2  mov     rax, cs:qword_18006F3A8
0x1800389a9  and     rax, rbx
0x1800389ac  cmp     rax, cs:qword_18006F3A8
0x1800389b3  jnz     short loc_180038A33
0x1800389b5  call    __local_stdio_printf_options
0x1800389ba  mov     ebx, 100h
0x1800389bf  mov     [rsp+198h+ArgList], rbp; ArgList
0x1800389c4  and     [rsp+198h+var_170], 0
0x1800389ca  lea     rdx, [rsp+198h+Buffer]; Buffer
0x1800389cf  mov     r8d, ebx; BufferCount
0x1800389d2  mov     [rsp+198h+Format], r14; Format
0x1800389d7  mov     rcx, [rax]; Options
0x1800389da  lea     r9d, [rbx-1]; MaxCount
0x1800389de  call    cs:__imp___stdio_common_vsnprintf_s
0x1800389e4  test    eax, eax
0x1800389e6  mov     ecx, 0FFFFh
0x1800389eb  cmovs   ax, cx
0x1800389ef  cmp     ax, bx
0x1800389f2  jnb     short loc_180038A01
0x1800389f4  movzx   eax, ax
0x1800389f7  cmp     rax, rbx
0x1800389fa  jnb     short loc_180038A53
0x1800389fc  mov     [rsp+rax+198h+Buffer], 0
0x180038a01  test    cs:Microsoft_Windows_DotNETRuntimeStressEnableBits, 1
0x180038a08  mov     [rsp+198h+var_49], 0
0x180038a10  jz      short loc_180038A33
0x180038a12  movzx   eax, cs:?g_nClrInstanceId@@3IA; uint g_nClrInstanceId
0x180038a19  mov     r9b, sil
0x180038a1c  mov     word ptr [rsp+198h+var_170], ax
0x180038a21  mov     r8d, edi
0x180038a24  lea     rax, [rsp+198h+Buffer]
0x180038a29  mov     [rsp+198h+Format], rax
0x180038a2e  call    CoTemplate_qcsh
0x180038a33  mov     rcx, [rsp+198h+var_48]
0x180038a3b  xor     rcx, rsp; StackCookie
0x180038a3e  call    __security_check_cookie
0x180038a43  add     rsp, 168h
0x180038a4a  pop     r15
0x180038a4c  pop     r14
0x180038a4e  pop     rdi
0x180038a4f  pop     rsi
0x180038a50  pop     rbp
0x180038a51  pop     rbx
0x180038a52  retn
0x180038a53  call    __report_rangecheckfailure
```
