# WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)

- ea: `0x180036d50`
- end: `0x180036e67`
- name: `??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z`
- size: `279`
- prototype: `_QWORD(WcmCommon::details::TPEnvironment *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800369d8`
- `0x18007f0b0`

## callees

- `0x180036d50`
- `0x1800a9738`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180036e06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180036e06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180036df5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180036df5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180036dca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180036dca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036e30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PTP_POOL *__fastcall WcmCommon::details::TPEnvironment::TPEnvironment(PTP_POOL *this, DWORD a2, DWORD a3)
{
  struct _TP_POOL *Threadpool; // rsi
  const char *v7; // r9
  struct _TP_POOL *v8; // rbp
  const char *v9; // r9
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  memset_0(this, 0, 0x48u);
  this[9] = 0;
  *(_DWORD *)this = 3;
  this[1] = 0;
  this[2] = 0;
  this[3] = 0;
  this[4] = 0;
  this[5] = 0;
  this[6] = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  Threadpool = CreateThreadpool(0);
  v8 = this[9];
  if ( v8 )
  {
    LastError = GetLastError();
    CloseThreadpool(v8);
    SetLastError(LastError);
  }
  this[9] = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\net\\inc\\wcm_work_queue.h",
      v7);
  if ( !SetThreadpoolThreadMinimum(Threadpool, a2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\net\\inc\\wcm_work_queue.h",
      v9);
  SetThreadpoolThreadMaximum(this[9], a3);
  this[1] = this[9];
  return this;
}

```

## disassembly

```asm
0x180036d50  mov     [rsp+arg_0], rcx
0x180036d55  push    rbx
0x180036d56  push    rbp
0x180036d57  push    rsi
0x180036d58  push    rdi
0x180036d59  push    r14
0x180036d5b  push    r15
0x180036d5d  sub     rsp, 28h
0x180036d61  mov     r14d, r8d
0x180036d64  mov     r15d, edx
0x180036d67  mov     rdi, rcx
0x180036d6a  mov     ebx, 48h ; 'H'
0x180036d6f  mov     r8d, ebx; Size
0x180036d72  xor     edx, edx; Val
0x180036d74  call    memset_0
0x180036d79  mov     qword ptr [rdi+48h], 0
0x180036d81  mov     dword ptr [rdi], 3
0x180036d87  mov     qword ptr [rdi+8], 0
0x180036d8f  mov     qword ptr [rdi+10h], 0
0x180036d97  mov     qword ptr [rdi+18h], 0
0x180036d9f  mov     qword ptr [rdi+20h], 0
0x180036da7  mov     qword ptr [rdi+28h], 0
0x180036daf  mov     qword ptr [rdi+30h], 0
0x180036db7  mov     dword ptr [rdi+38h], 0
0x180036dbe  mov     dword ptr [rdi+3Ch], 1
0x180036dc5  mov     [rdi+40h], ebx
0x180036dc8  xor     ecx, ecx; reserved
0x180036dca  call    cs:__imp_CreateThreadpool
0x180036dd0  mov     rsi, rax
0x180036dd3  mov     rbp, [rdi+48h]
0x180036dd7  test    rbp, rbp
0x180036dda  jnz     short loc_180036E24
0x180036ddc  mov     [rdi+48h], rsi
0x180036de0  mov     rcx, [rsp+58h]; this
0x180036de5  test    rsi, rsi
0x180036de8  jz      short loc_180036E40
0x180036dea  mov     rbx, [rsp+58h]
0x180036def  mov     edx, r15d; cthrdMic
0x180036df2  mov     rcx, rsi; ptpp
0x180036df5  call    cs:__imp_SetThreadpoolThreadMinimum
0x180036dfb  test    eax, eax
0x180036dfd  jz      short loc_180036E52
0x180036dff  mov     edx, r14d; cthrdMost
0x180036e02  mov     rcx, [rdi+48h]; ptpp
0x180036e06  call    cs:__imp_SetThreadpoolThreadMaximum
0x180036e0c  mov     rax, [rdi+48h]
0x180036e10  mov     [rdi+8], rax
0x180036e14  mov     rax, rdi
0x180036e17  add     rsp, 28h
0x180036e1b  pop     r15
0x180036e1d  pop     r14
0x180036e1f  pop     rdi
0x180036e20  pop     rsi
0x180036e21  pop     rbp
0x180036e22  pop     rbx
0x180036e23  retn
0x180036e24  call    cs:__imp_GetLastError
0x180036e2a  nop
0x180036e2b  mov     ebx, eax
0x180036e2d  mov     rcx, rbp; ptpp
0x180036e30  call    cs:__imp_CloseThreadpool
0x180036e36  mov     ecx, ebx; dwErrCode
0x180036e38  call    cs:__imp_SetLastError
0x180036e3e  jmp     short loc_180036DDC
0x180036e40  lea     r8, aOnecoreNetIncW_1; "onecore\\net\\inc\\wcm_work_queue.h"
0x180036e47  mov     edx, 6Ah ; 'j'; void *
0x180036e4c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036e52  lea     r8, aOnecoreNetIncW_1; "onecore\\net\\inc\\wcm_work_queue.h"
0x180036e59  mov     edx, 6Dh ; 'm'; void *
0x180036e5e  mov     rcx, rbx; this
0x180036e61  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
