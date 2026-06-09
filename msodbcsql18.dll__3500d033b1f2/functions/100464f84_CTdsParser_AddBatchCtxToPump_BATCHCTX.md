# CTdsParser::AddBatchCtxToPump(BATCHCTX *)

- ea: `0x100464f84`
- end: `0x100465094`
- name: `?AddBatchCtxToPump@CTdsParser@@QEAAJPEAVBATCHCTX@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(CTdsParser *__hidden this, struct BATCHCTX *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100467bc8`

## callees

- `0x100464f84`
- `0x100546a24`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x10046502a`
- `KERNEL32!CreateThread` at `0x10046502a`
- `KERNEL32!ResetEvent` at `0x100465001`
- `KERNEL32!ResetEvent` at `0x100465001`
- `KERNEL32!SetEvent` at `0x100464fe6`
- `KERNEL32!SetEvent` at `0x100464fe6`
- `KERNEL32!GetLastError` at `0x100464ff0`
- `KERNEL32!GetLastError` at `0x10046500b`
- `KERNEL32!GetLastError` at `0x100465039`
- `KERNEL32!GetLastError` at `0x100464ff0`
- `KERNEL32!GetLastError` at `0x10046500b`
- `KERNEL32!GetLastError` at `0x100465039`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTdsParser::AddBatchCtxToPump(CTdsParser *this, struct BATCHCTX *a2)
{
  char *v4; // rax
  __int64 v5; // rbx
  HANDLE Thread; // rax
  __int64 v7; // r9
  unsigned int v8; // edi

  v4 = (char *)this + 80;
  v5 = 0;
  if ( this != (CTdsParser *)-80LL )
  {
    v5 = *(_QWORD *)v4;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v4 + 32LL) + 8LL))(*(_QWORD *)v4 + 32LL);
  }
  *((_QWORD *)a2 + 190) = *((_QWORD *)this + 8);
  *(_QWORD *)(*((_QWORD *)this + 8) + 8LL) = (char *)a2 + 1520;
  *((_QWORD *)this + 8) = (char *)a2 + 1520;
  *((_QWORD *)a2 + 191) = (char *)this + 64;
  if ( !SetEvent(*((HANDLE *)this + 12)) )
    GetLastError();
  if ( *((_QWORD *)this + 15) )
    goto LABEL_13;
  if ( !ResetEvent(*((HANDLE *)this + 14)) )
    GetLastError();
  Thread = CreateThread(0, 0, BatchCtxPumpThreadProc, this, 0, 0);
  *((_QWORD *)this + 15) = Thread;
  if ( Thread || GetLastError() != 8 )
  {
LABEL_13:
    v8 = 0;
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    v8 = bidTraceHR(0, 299017, 2147942414LL, v7);
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v5 + 32) + 24LL))(v5 + 32);
  return v8;
}

```

## disassembly

```asm
0x100464f84  push    rdi
0x100464f86  sub     rsp, 40h
0x100464f8a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x100464f93  mov     [rsp+48h+arg_0], rbx
0x100464f98  mov     [rsp+48h+arg_8], rsi
0x100464f9d  mov     rsi, rdx
0x100464fa0  mov     rdi, rcx
0x100464fa3  lea     rax, [rcx+50h]
0x100464fa7  xor     ebx, ebx
0x100464fa9  test    rax, rax
0x100464fac  jz      short loc_100464FC3
0x100464fae  mov     rbx, [rax]
0x100464fb1  lea     rcx, [rbx+20h]
0x100464fb5  mov     rax, [rcx]
0x100464fb8  mov     rax, [rax+8]
0x100464fbc  call    cs:__guard_dispatch_icall_fptr
0x100464fc2  nop
0x100464fc3  lea     rdx, [rsi+5F0h]
0x100464fca  lea     rcx, [rdi+40h]
0x100464fce  mov     rax, [rcx]
0x100464fd1  mov     [rdx], rax
0x100464fd4  mov     rax, [rcx]
0x100464fd7  mov     [rax+8], rdx
0x100464fdb  mov     [rcx], rdx
0x100464fde  mov     [rdx+8], rcx
0x100464fe2  mov     rcx, [rdi+60h]; hEvent
0x100464fe6  call    cs:__imp_SetEvent
0x100464fec  test    eax, eax
0x100464fee  jnz     short loc_100464FF6
0x100464ff0  call    cs:__imp_GetLastError
0x100464ff6  cmp     qword ptr [rdi+78h], 0
0x100464ffb  jnz     short loc_10046506A
0x100464ffd  mov     rcx, [rdi+70h]; hEvent
0x100465001  call    cs:__imp_ResetEvent
0x100465007  test    eax, eax
0x100465009  jnz     short loc_100465011
0x10046500b  call    cs:__imp_GetLastError
0x100465011  and     [rsp+48h+var_20], 0
0x100465017  and     [rsp+48h+var_28], 0
0x10046501c  mov     r9, rdi; lpParameter
0x10046501f  lea     r8, ?BatchCtxPumpThreadProc@@YAKPEAX@Z; lpStartAddress
0x100465026  xor     edx, edx; dwStackSize
0x100465028  xor     ecx, ecx; lpThreadAttributes
0x10046502a  call    cs:__imp_CreateThread
0x100465030  mov     [rdi+78h], rax
0x100465034  test    rax, rax
0x100465037  jnz     short loc_10046506A
0x100465039  call    cs:__imp_GetLastError
0x10046503f  cmp     eax, 8
0x100465042  jnz     short loc_10046506A
0x100465044  test    byte ptr cs:_bidGblFlags, 2
0x10046504b  jz      short loc_100465063
0x10046504d  mov     edx, 49009h
0x100465052  xor     ecx, ecx
0x100465054  mov     r8d, 8007000Eh
0x10046505a  call    _bidTraceHR
0x10046505f  mov     edi, eax
0x100465061  jmp     short loc_10046506C
0x100465063  mov     edi, 8007000Eh
0x100465068  jmp     short loc_10046506C
0x10046506a  xor     edi, edi
0x10046506c  test    rbx, rbx
0x10046506f  jz      short loc_100465082
0x100465071  lea     rcx, [rbx+20h]
0x100465075  mov     rdx, [rcx]
0x100465078  mov     rax, [rdx+18h]
0x10046507c  call    cs:__guard_dispatch_icall_fptr
0x100465082  mov     eax, edi
0x100465084  mov     rbx, [rsp+48h+arg_0]
0x100465089  mov     rsi, [rsp+48h+arg_8]
0x10046508e  add     rsp, 40h
0x100465092  pop     rdi
0x100465093  retn
```
