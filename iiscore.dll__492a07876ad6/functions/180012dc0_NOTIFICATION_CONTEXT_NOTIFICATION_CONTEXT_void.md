# NOTIFICATION_CONTEXT::~NOTIFICATION_CONTEXT(void)

- ea: `0x180012dc0`
- end: `0x180012eb6`
- name: `??1NOTIFICATION_CONTEXT@@UEAA@XZ`
- size: `246`
- prototype: `void __fastcall(NOTIFICATION_CONTEXT *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012cd0`
- `0x180012d20`
- `0x180012d80`
- `0x180021430`
- `0x180028ee0`

## callees

- `0x180012dc0`
- `0x18001761c`
- `0x18001ab70`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e7a`
- `iisutil!WriteRefTraceLog` at `0x180012e91`
- `iisutil!WriteRefTraceLog` at `0x180012e91`

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
0x180012dc0  mov     [rsp+arg_18], rsi
0x180012dc5  push    rdi
0x180012dc6  sub     rsp, 20h
0x180012dca  mov     [rsp+28h+arg_0], rbx
0x180012dcf  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180012dd6  mov     [rsp+28h+arg_8], rbp
0x180012ddb  mov     rsi, rcx
0x180012dde  xor     ebp, ebp
0x180012de0  mov     [rcx], rax
0x180012de3  cmp     [rcx+60h], ebp
0x180012de6  jz      short loc_180012E34
0x180012de8  mov     rax, [rcx+50h]
0x180012dec  mov     ebx, ebp
0x180012dee  mov     [rsp+28h+arg_10], r14
0x180012df3  mov     r14, [rcx+58h]
0x180012df7  cmp     [rax+30h], ebx
0x180012dfa  jbe     short loc_180012E2C
0x180012dfc  nop     dword ptr [rax+00h]
0x180012e00  mov     eax, ebx
0x180012e02  mov     rcx, [r14+rax*8]
0x180012e06  lea     rdi, [r14+rax*8]
0x180012e0a  test    rcx, rcx
0x180012e0d  jz      short loc_180012E21
0x180012e0f  mov     rax, [rcx]
0x180012e12  mov     rax, [rax+0E8h]
0x180012e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e1e  mov     [rdi], rbp
0x180012e21  mov     rax, [rsi+50h]
0x180012e25  inc     ebx
0x180012e27  cmp     ebx, [rax+30h]
0x180012e2a  jb      short loc_180012E00
0x180012e2c  mov     r14, [rsp+28h+arg_10]
0x180012e31  mov     [rsi+60h], ebp
0x180012e34  mov     rcx, [rsi+40h]; hObject
0x180012e38  test    rcx, rcx
0x180012e3b  jnz     short loc_180012E7A
0x180012e3d  mov     rdi, [rsi+18h]
0x180012e41  mov     ebx, 0FFFFFFFFh
0x180012e46  lock xadd [rdi+4Ch], ebx
0x180012e4b  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180012e52  dec     ebx
0x180012e54  mov     rbp, [rsp+28h+arg_8]
0x180012e59  test    rcx, rcx
0x180012e5c  jnz     short loc_180012E8C
0x180012e5e  test    ebx, ebx
0x180012e60  mov     rbx, [rsp+28h+arg_0]
0x180012e65  jz      short loc_180012E9F
0x180012e67  mov     dword ptr [rsi+20h], 7863746Eh
0x180012e6e  mov     rsi, [rsp+28h+arg_18]
0x180012e73  add     rsp, 20h
0x180012e77  pop     rdi
0x180012e78  retn
0x180012e7a  call    cs:__imp_CloseHandle
0x180012e81  nop     dword ptr [rax+rax+00h]
0x180012e86  mov     [rsi+40h], rbp
0x180012e8a  jmp     short loc_180012E3D
0x180012e8c  mov     r8, rdi
0x180012e8f  mov     edx, ebx
0x180012e91  call    cs:__imp_WriteRefTraceLog
0x180012e98  nop     dword ptr [rax+rax+00h]
0x180012e9d  jmp     short loc_180012E5E
0x180012e9f  test    rdi, rdi
0x180012ea2  jz      short loc_180012E67
0x180012ea4  mov     rcx, rdi; this
0x180012ea7  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x180012eac  mov     rcx, rdi; Block
0x180012eaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012eb4  jmp     short loc_180012E67
```
