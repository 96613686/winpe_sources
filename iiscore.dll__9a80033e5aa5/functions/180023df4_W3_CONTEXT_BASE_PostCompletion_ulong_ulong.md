# W3_CONTEXT_BASE::PostCompletion(ulong,ulong)

- ea: `0x180023df4`
- end: `0x180023ea8`
- name: `?PostCompletion@W3_CONTEXT_BASE@@QEAAJKK@Z`
- size: `180`
- prototype: `__int64 __fastcall(W3_CONTEXT_BASE *__hidden this, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001acc`
- `0x180004340`
- `0x18001ff10`
- `0x180023eb0`
- `0x1800268d0`
- `0x1800278e8`

## callees

- `0x180019558`
- `0x180023df4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e85`
- `W3TP!ThreadPoolPostCompletion` at `0x180023e7b`
- `W3TP!ThreadPoolPostCompletion` at `0x180023e7b`

## pseudocode

```c
signed int __fastcall W3_CONTEXT_BASE::PostCompletion(W3_CONTEXT_BASE *this, unsigned int a2, int a3)
{
  struct _OVERLAPPED *v6; // rax
  struct _OVERLAPPED *v7; // rbx
  signed int result; // eax
  int v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  v6 = (struct _OVERLAPPED *)operator new(0x10u);
  v7 = v6;
  if ( v6 )
  {
    v6->Internal = (ULONG_PTR)this;
    LODWORD(v6->InternalHigh) = a3;
  }
  else
  {
    v7 = 0;
  }
  (*(void (__fastcall **)(W3_CONTEXT_BASE *, int *, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 264LL))(
    this,
    &v9,
    0,
    &v10,
    0,
    0,
    0);
  if ( ThreadPoolPostCompletion(
         a2,
         (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))W3_CONTEXT_BASE::OnPostedCompletion,
         v7) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023df4  mov     [rsp+arg_8], rbx
0x180023df9  push    rbp
0x180023dfa  push    rsi
0x180023dfb  push    rdi
0x180023dfc  sub     rsp, 40h
0x180023e00  mov     rdi, rcx
0x180023e03  mov     [rsp+58h+arg_0], 0
0x180023e0b  mov     ecx, 10h; Size
0x180023e10  mov     [rsp+58h+arg_18], 0
0x180023e19  mov     esi, r8d
0x180023e1c  mov     ebp, edx
0x180023e1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023e23  mov     rbx, rax
0x180023e26  test    rax, rax
0x180023e29  jz      short loc_180023E33
0x180023e2b  mov     [rax], rdi
0x180023e2e  mov     [rax+8], esi
0x180023e31  jmp     short loc_180023E35
0x180023e33  xor     ebx, ebx
0x180023e35  mov     rax, [rdi]
0x180023e38  lea     r9, [rsp+58h+arg_18]
0x180023e3d  mov     [rsp+58h+var_28], 0
0x180023e46  lea     rdx, [rsp+58h+arg_0]
0x180023e4b  mov     [rsp+58h+var_30], 0
0x180023e54  xor     r8d, r8d
0x180023e57  mov     rcx, rdi
0x180023e5a  mov     [rsp+58h+var_38], 0
0x180023e63  mov     rax, [rax+108h]
0x180023e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e6f  mov     r8, rbx
0x180023e72  lea     rdx, ?OnPostedCompletion@W3_CONTEXT_BASE@@SAXKKPEAU_OVERLAPPED@@@Z; W3_CONTEXT_BASE::OnPostedCompletion(ulong,ulong,_OVERLAPPED *)
0x180023e79  mov     ecx, ebp
0x180023e7b  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180023e81  test    eax, eax
0x180023e83  jnz     short loc_180023E99
0x180023e85  call    cs:__imp_GetLastError
0x180023e8b  test    eax, eax
0x180023e8d  jle     short loc_180023E9B
0x180023e8f  movzx   eax, ax
0x180023e92  or      eax, 80070000h
0x180023e97  jmp     short loc_180023E9B
0x180023e99  xor     eax, eax
0x180023e9b  mov     rbx, [rsp+58h+arg_8]
0x180023ea0  add     rsp, 40h
0x180023ea4  pop     rdi
0x180023ea5  pop     rsi
0x180023ea6  pop     rbp
0x180023ea7  retn
```
