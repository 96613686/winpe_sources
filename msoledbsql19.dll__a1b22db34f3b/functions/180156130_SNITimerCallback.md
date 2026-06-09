# SNITimerCallback

- ea: `0x180156130`
- end: `0x180156263`
- name: `SNITimerCallback`
- size: `307`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x180156130`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180156225`
- `KERNEL32!GetLastError` at `0x180156225`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18015621b`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18015621b`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18015620a`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18015620a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SNITimerCallback(_QWORD *a1, unsigned __int8 a2)
{
  int v3; // ebx
  int v4; // ebx
  ULONG v5; // r8d
  ULONG DueTime; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+34h] [rbp-24h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802667C8[0] )
    bidScopeEnterW(&v8, off_1802667C8[0], a1, a2);
  DueTime = 0;
  v7 = 0;
  v3 = ((__int64 (__fastcall *)(_QWORD, ULONG *, int *))a1[1])(*a1, &DueTime, &v7);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263EA8[0] )
    bidTraceW(off_180260B60[0], 2478080, off_180263EA8[0], a1[2]);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      v5 = DueTime;
      *((_DWORD *)a1 + 6) = DueTime;
      ChangeTimerQueueTimer(0, (HANDLE)a1[2], v5, 0);
    }
  }
  else if ( DeleteTimerQueueTimer(0, (HANDLE)a1[2], 0) || GetLastError() == 997 )
  {
    operator delete(a1, 0x20u);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
}

```

## disassembly

```asm
0x180156130  mov     [rsp+arg_10], rbx
0x180156135  push    rdi
0x180156136  sub     rsp, 50h
0x18015613a  mov     rax, cs:__security_cookie
0x180156141  xor     rax, rsp
0x180156144  mov     [rsp+58h+var_18], rax
0x180156149  mov     rdi, rcx
0x18015614c  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFFh
0x180156155  mov     eax, cs:_bidGblFlags
0x18015615b  and     eax, 20004h
0x180156160  cmp     eax, 20004h
0x180156165  jnz     short loc_18015618B
0x180156167  mov     rax, cs:off_1802667C8; "<SNITimerCallback|API|SNI> lpParameter:"...
0x18015616e  test    rax, rax
0x180156171  jz      short loc_18015618B
0x180156173  movzx   r9d, dl
0x180156177  mov     r8, rcx
0x18015617a  mov     rdx, cs:off_1802667C8; "<SNITimerCallback|API|SNI> lpParameter:"...
0x180156181  lea     rcx, [rsp+58h+var_20]
0x180156186  call    _bidScopeEnterW
0x18015618b  xor     eax, eax
0x18015618d  mov     [rsp+58h+DueTime], eax
0x180156191  mov     [rsp+58h+var_24], eax
0x180156195  lea     r8, [rsp+58h+var_24]
0x18015619a  lea     rdx, [rsp+58h+DueTime]
0x18015619f  mov     rcx, [rdi]
0x1801561a2  mov     rax, [rdi+8]
0x1801561a6  call    cs:__guard_dispatch_icall_fptr
0x1801561ac  mov     ebx, eax
0x1801561ae  mov     ecx, cs:_bidGblFlags
0x1801561b4  and     ecx, 20002h
0x1801561ba  cmp     ecx, 20002h
0x1801561c0  jnz     short loc_1801561EE
0x1801561c2  mov     rcx, cs:off_180263EA8; "<SNITimerCallback|SNI> timerHandle: %p{"...
0x1801561c9  test    rcx, rcx
0x1801561cc  jz      short loc_1801561EE
0x1801561ce  mov     [rsp+58h+var_38], eax
0x1801561d2  mov     r9, [rdi+10h]
0x1801561d6  mov     r8, cs:off_180263EA8; "<SNITimerCallback|SNI> timerHandle: %p{"...
0x1801561dd  mov     edx, 25D000h
0x1801561e2  mov     rcx, cs:off_180260B60; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801561e9  call    _bidTraceW
0x1801561ee  sub     ebx, 1
0x1801561f1  jz      short loc_180156212
0x1801561f3  cmp     ebx, 1
0x1801561f6  jnz     short loc_180156240
0x1801561f8  mov     r8d, [rsp+58h+DueTime]; DueTime
0x1801561fd  mov     [rdi+18h], r8d
0x180156201  xor     r9d, r9d; Period
0x180156204  mov     rdx, [rdi+10h]; Timer
0x180156208  xor     ecx, ecx; TimerQueue
0x18015620a  call    cs:__imp_ChangeTimerQueueTimer
0x180156210  jmp     short loc_180156240
0x180156212  xor     r8d, r8d; CompletionEvent
0x180156215  mov     rdx, [rdi+10h]; Timer
0x180156219  xor     ecx, ecx; TimerQueue
0x18015621b  call    cs:__imp_DeleteTimerQueueTimer
0x180156221  test    eax, eax
0x180156223  jnz     short loc_180156232
0x180156225  call    cs:__imp_GetLastError
0x18015622b  cmp     eax, 3E5h
0x180156230  jnz     short loc_180156240
0x180156232  mov     edx, 20h ; ' '; unsigned __int64
0x180156237  mov     rcx, rdi; void *
0x18015623a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18015623f  nop
0x180156240  lea     rcx, [rsp+58h+var_20]; this
0x180156245  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015624a  nop
0x18015624b  mov     rcx, [rsp+58h+var_18]
0x180156250  xor     rcx, rsp; StackCookie
0x180156253  call    __security_check_cookie
0x180156258  mov     rbx, [rsp+58h+arg_10]
0x18015625d  add     rsp, 50h
0x180156261  pop     rdi
0x180156262  retn
```
