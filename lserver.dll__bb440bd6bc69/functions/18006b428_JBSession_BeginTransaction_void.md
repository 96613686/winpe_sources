# JBSession::BeginTransaction(void)

- ea: `0x18006b428`
- end: `0x18006b48a`
- name: `?BeginTransaction@JBSession@@QEAAHXZ`
- size: `98`
- prototype: `__int64 __fastcall(JBSession *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18003c130`
- `0x18003c200`
- `0x18003c2d0`
- `0x18003c3a0`
- `0x18003c470`
- `0x18003c540`
- `0x18003c610`
- `0x180042304`
- `0x180084bc0`

## callees

- `0x18006b428`

## import_xrefs

- `ESENT!JetBeginTransaction` at `0x18006b458`
- `ESENT!JetBeginTransaction` at `0x18006b458`
- `KERNEL32!GetCurrentThreadId` at `0x18006b448`
- `KERNEL32!GetCurrentThreadId` at `0x18006b46d`
- `KERNEL32!GetCurrentThreadId` at `0x18006b448`
- `KERNEL32!GetCurrentThreadId` at `0x18006b46d`

## pseudocode

```c
_BOOL8 __fastcall JBSession::BeginTransaction(JBSession *this)
{
  JET_ERR v3; // eax

  if ( *((_QWORD *)this + 2) == -1 )
  {
    *(_DWORD *)this = -1029;
    return 0;
  }
  else
  {
    if ( *((_DWORD *)this + 8) )
      GetCurrentThreadId();
    v3 = JetBeginTransaction(*((_QWORD *)this + 2));
    *(_DWORD *)this = v3;
    if ( v3 >= 0 )
      ++*((_DWORD *)this + 6);
    *((_DWORD *)this + 8) = GetCurrentThreadId();
    return *(_DWORD *)this >= 0;
  }
}

```

## disassembly

```asm
0x18006b428  push    rbx
0x18006b42a  sub     rsp, 20h
0x18006b42e  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18006b433  mov     rbx, rcx
0x18006b436  jnz     short loc_18006B442
0x18006b438  mov     dword ptr [rcx], 0FFFFFBFBh
0x18006b43e  xor     eax, eax
0x18006b440  jmp     short loc_18006B483
0x18006b442  cmp     dword ptr [rcx+20h], 0
0x18006b446  jz      short loc_18006B454
0x18006b448  call    cs:__imp_GetCurrentThreadId
0x18006b44f  nop     dword ptr [rax+rax+00h]
0x18006b454  mov     rcx, [rbx+10h]; sesid
0x18006b458  call    cs:__imp_JetBeginTransaction
0x18006b45f  nop     dword ptr [rax+rax+00h]
0x18006b464  mov     [rbx], eax
0x18006b466  test    eax, eax
0x18006b468  js      short loc_18006B46D
0x18006b46a  inc     dword ptr [rbx+18h]
0x18006b46d  call    cs:__imp_GetCurrentThreadId
0x18006b474  nop     dword ptr [rax+rax+00h]
0x18006b479  mov     [rbx+20h], eax
0x18006b47c  mov     eax, [rbx]
0x18006b47e  not     eax
0x18006b480  shr     eax, 1Fh
0x18006b483  add     rsp, 20h
0x18006b487  pop     rbx
0x18006b488  retn
```
