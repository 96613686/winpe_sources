# CMFSourceMPEG2TSPin::OnThreadCreate(void)

- ea: `0x18008f1d0`
- end: `0x18008f2d2`
- name: `?OnThreadCreate@CMFSourceMPEG2TSPin@@MEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CMFSourceMPEG2TSPin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180090b50`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180074160`
- `0x18008f1d0`
- `0x180092898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f288`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008f255`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008f255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f243`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008f299`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008f299`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18008f270`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18008f270`

## string_xrefs

- `0x18008f1f4`: `CMFSourceMPEG2TSPin::OnThreadCreate`

## pseudocode

```c
__int64 __fastcall CMFSourceMPEG2TSPin::OnThreadCreate(const WCHAR *this)
{
  HANDLE CurrentThread; // rsi
  int ThreadPriority; // eax
  int v4; // ebp
  HANDLE v5; // rax
  _BYTE v7[4]; // [rsp+20h] [rbp-28h] BYREF
  DWORD TaskIndex; // [rsp+24h] [rbp-24h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v7, "CMFSourceMPEG2TSPin::OnThreadCreate", 3843);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 56, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids);
  if ( this[316] )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    TaskIndex = 0;
    v4 = ThreadPriority;
    v5 = AvSetMmThreadCharacteristicsW(this + 316, &TaskIndex);
    *((_QWORD *)this + 78) = v5;
    if ( !v5 )
    {
      GetLastError();
      SetThreadPriority(CurrentThread, v4);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v7);
  return 0;
}

```

## disassembly

```asm
0x18008f1d0  mov     [rsp+arg_8], rbx
0x18008f1d5  mov     [rsp+arg_10], rbp
0x18008f1da  push    rsi
0x18008f1db  push    rdi
0x18008f1dc  push    r14
0x18008f1de  sub     rsp, 30h
0x18008f1e2  mov     rax, cs:__security_cookie
0x18008f1e9  xor     rax, rsp
0x18008f1ec  mov     [rsp+48h+var_20], rax
0x18008f1f1  mov     rdi, rcx
0x18008f1f4  lea     rdx, aCmfsourcempeg2_10; "CMFSourceMPEG2TSPin::OnThreadCreate"
0x18008f1fb  lea     rcx, [rsp+48h+var_28]; this
0x18008f200  mov     r8d, 0F03h; int
0x18008f206  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008f20b  cmp     cs:byte_1800EACCB, 8
0x18008f212  jb      short loc_18008F233
0x18008f214  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f21b  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x18008f222  mov     edx, 38h ; '8'
0x18008f227  mov     rcx, [rcx+88h]
0x18008f22e  call    WPP_SF_
0x18008f233  lea     rbx, [rdi+278h]
0x18008f23a  xor     r14d, r14d
0x18008f23d  cmp     [rbx], r14w
0x18008f241  jz      short loc_18008F2A5
0x18008f243  call    cs:__imp_GetCurrentThread
0x18008f24a  nop     dword ptr [rax+rax+00h]
0x18008f24f  mov     rcx, rax; hThread
0x18008f252  mov     rsi, rax
0x18008f255  call    cs:__imp_GetThreadPriority
0x18008f25c  nop     dword ptr [rax+rax+00h]
0x18008f261  lea     rdx, [rsp+48h+TaskIndex]; TaskIndex
0x18008f266  mov     [rsp+48h+TaskIndex], r14d
0x18008f26b  mov     rcx, rbx; TaskName
0x18008f26e  mov     ebp, eax
0x18008f270  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18008f277  nop     dword ptr [rax+rax+00h]
0x18008f27c  mov     [rdi+270h], rax
0x18008f283  test    rax, rax
0x18008f286  jnz     short loc_18008F2A5
0x18008f288  call    cs:__imp_GetLastError
0x18008f28f  nop     dword ptr [rax+rax+00h]
0x18008f294  mov     edx, ebp; nPriority
0x18008f296  mov     rcx, rsi; hThread
0x18008f299  call    cs:__imp_SetThreadPriority
0x18008f2a0  nop     dword ptr [rax+rax+00h]
0x18008f2a5  lea     rcx, [rsp+48h+var_28]; this
0x18008f2aa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008f2af  xor     eax, eax
0x18008f2b1  mov     rcx, [rsp+48h+var_20]
0x18008f2b6  xor     rcx, rsp; StackCookie
0x18008f2b9  call    __security_check_cookie
0x18008f2be  mov     rbx, [rsp+48h+arg_8]
0x18008f2c3  mov     rbp, [rsp+48h+arg_10]
0x18008f2c8  add     rsp, 30h
0x18008f2cc  pop     r14
0x18008f2ce  pop     rdi
0x18008f2cf  pop     rsi
0x18008f2d0  retn
```
