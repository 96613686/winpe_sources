# NOTIFICATION_CONTEXT::~NOTIFICATION_CONTEXT(void)

- ea: `0x180011eb0`
- end: `0x180011f99`
- name: `??1NOTIFICATION_CONTEXT@@UEAA@XZ`
- size: `233`
- prototype: `void __fastcall(NOTIFICATION_CONTEXT *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011dc0`
- `0x180011e10`
- `0x180011e70`
- `0x18001f830`
- `0x180026e30`

## callees

- `0x180011eb0`
- `0x180016394`
- `0x180019598`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f69`
- `iisutil!WriteRefTraceLog` at `0x180011f7a`
- `iisutil!WriteRefTraceLog` at `0x180011f7a`

## pseudocode

```c
void __fastcall NOTIFICATION_CONTEXT::~NOTIFICATION_CONTEXT(NOTIFICATION_CONTEXT *this)
{
  unsigned int v2; // ebx
  __int64 i; // r14
  __int64 v4; // rcx
  void *v5; // rcx
  volatile signed __int32 *v6; // rdi
  unsigned __int32 v7; // ebx

  *(_QWORD *)this = &NOTIFICATION_CONTEXT::`vftable';
  if ( *((_DWORD *)this + 24) )
  {
    v2 = 0;
    for ( i = *((_QWORD *)this + 11); v2 < *(_DWORD *)(*((_QWORD *)this + 10) + 48LL); ++v2 )
    {
      v4 = *(_QWORD *)(i + 8LL * v2);
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 232LL))(v4);
        *(_QWORD *)(i + 8LL * v2) = 0;
      }
    }
    *((_DWORD *)this + 24) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 8) = 0;
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  v7 = _InterlockedDecrement(v6 + 19);
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, v7, v6);
  if ( !v7 && v6 )
  {
    W3_CONTEXT_BASE::~W3_CONTEXT_BASE((W3_CONTEXT_BASE *)v6);
    operator delete((void *)v6);
  }
  *((_DWORD *)this + 8) = 2019783790;
}

```

## disassembly

```asm
0x180011eb0  mov     [rsp+arg_18], rsi
0x180011eb5  push    rdi
0x180011eb6  sub     rsp, 20h
0x180011eba  mov     [rsp+28h+arg_0], rbx
0x180011ebf  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180011ec6  mov     [rsp+28h+arg_8], rbp
0x180011ecb  mov     rsi, rcx
0x180011ece  xor     ebp, ebp
0x180011ed0  mov     [rcx], rax
0x180011ed3  cmp     [rcx+60h], ebp
0x180011ed6  jz      short loc_180011F24
0x180011ed8  mov     rax, [rcx+50h]
0x180011edc  mov     ebx, ebp
0x180011ede  mov     [rsp+28h+arg_10], r14
0x180011ee3  mov     r14, [rcx+58h]
0x180011ee7  cmp     [rax+30h], ebx
0x180011eea  jbe     short loc_180011F1C
0x180011eec  nop     dword ptr [rax+00h]
0x180011ef0  mov     eax, ebx
0x180011ef2  mov     rcx, [r14+rax*8]
0x180011ef6  lea     rdi, [r14+rax*8]
0x180011efa  test    rcx, rcx
0x180011efd  jz      short loc_180011F11
0x180011eff  mov     rax, [rcx]
0x180011f02  mov     rax, [rax+0E8h]
0x180011f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f0e  mov     [rdi], rbp
0x180011f11  mov     rax, [rsi+50h]
0x180011f15  inc     ebx
0x180011f17  cmp     ebx, [rax+30h]
0x180011f1a  jb      short loc_180011EF0
0x180011f1c  mov     r14, [rsp+28h+arg_10]
0x180011f21  mov     [rsi+60h], ebp
0x180011f24  mov     rcx, [rsi+40h]; hObject
0x180011f28  test    rcx, rcx
0x180011f2b  jnz     short loc_180011F69
0x180011f2d  mov     rdi, [rsi+18h]
0x180011f31  mov     ebx, 0FFFFFFFFh
0x180011f36  lock xadd [rdi+4Ch], ebx
0x180011f3b  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180011f42  dec     ebx
0x180011f44  mov     rbp, [rsp+28h+arg_8]
0x180011f49  test    rcx, rcx
0x180011f4c  jnz     short loc_180011F75
0x180011f4e  test    ebx, ebx
0x180011f50  mov     rbx, [rsp+28h+arg_0]
0x180011f55  jz      short loc_180011F82
0x180011f57  mov     dword ptr [rsi+20h], 7863746Eh
0x180011f5e  mov     rsi, [rsp+28h+arg_18]
0x180011f63  add     rsp, 20h
0x180011f67  pop     rdi
0x180011f68  retn
0x180011f69  call    cs:__imp_CloseHandle
0x180011f6f  mov     [rsi+40h], rbp
0x180011f73  jmp     short loc_180011F2D
0x180011f75  mov     r8, rdi
0x180011f78  mov     edx, ebx
0x180011f7a  call    cs:__imp_WriteRefTraceLog
0x180011f80  jmp     short loc_180011F4E
0x180011f82  test    rdi, rdi
0x180011f85  jz      short loc_180011F57
0x180011f87  mov     rcx, rdi; this
0x180011f8a  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x180011f8f  mov     rcx, rdi; Block
0x180011f92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f97  jmp     short loc_180011F57
```
