# W3_CONTEXT_BASE::PostCompletion(ulong,ulong)

- ea: `0x180025c78`
- end: `0x180025d39`
- name: `?PostCompletion@W3_CONTEXT_BASE@@QEAAJKK@Z`
- size: `193`
- prototype: `__int64 __fastcall(W3_CONTEXT_BASE *__hidden this, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001b60`
- `0x180004710`
- `0x180021af0`
- `0x180025d40`
- `0x180028974`
- `0x180029ac8`

## callees

- `0x18001ab30`
- `0x180025c78`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d0f`
- `W3TP!ThreadPoolPostCompletion` at `0x180025cff`
- `W3TP!ThreadPoolPostCompletion` at `0x180025cff`

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
0x180025c78  mov     [rsp+arg_8], rbx
0x180025c7d  push    rbp
0x180025c7e  push    rsi
0x180025c7f  push    rdi
0x180025c80  sub     rsp, 40h
0x180025c84  mov     rdi, rcx
0x180025c87  mov     [rsp+58h+arg_0], 0
0x180025c8f  mov     ecx, 10h; Size
0x180025c94  mov     [rsp+58h+arg_18], 0
0x180025c9d  mov     esi, r8d
0x180025ca0  mov     ebp, edx
0x180025ca2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025ca7  mov     rbx, rax
0x180025caa  test    rax, rax
0x180025cad  jz      short loc_180025CB7
0x180025caf  mov     [rax], rdi
0x180025cb2  mov     [rax+8], esi
0x180025cb5  jmp     short loc_180025CB9
0x180025cb7  xor     ebx, ebx
0x180025cb9  mov     rax, [rdi]
0x180025cbc  lea     r9, [rsp+58h+arg_18]
0x180025cc1  mov     [rsp+58h+var_28], 0
0x180025cca  lea     rdx, [rsp+58h+arg_0]
0x180025ccf  mov     [rsp+58h+var_30], 0
0x180025cd8  xor     r8d, r8d
0x180025cdb  mov     rcx, rdi
0x180025cde  mov     [rsp+58h+var_38], 0
0x180025ce7  mov     rax, [rax+108h]
0x180025cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cf3  mov     r8, rbx
0x180025cf6  lea     rdx, ?OnPostedCompletion@W3_CONTEXT_BASE@@SAXKKPEAU_OVERLAPPED@@@Z; W3_CONTEXT_BASE::OnPostedCompletion(ulong,ulong,_OVERLAPPED *)
0x180025cfd  mov     ecx, ebp
0x180025cff  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180025d06  nop     dword ptr [rax+rax+00h]
0x180025d0b  test    eax, eax
0x180025d0d  jnz     short loc_180025D29
0x180025d0f  call    cs:__imp_GetLastError
0x180025d16  nop     dword ptr [rax+rax+00h]
0x180025d1b  test    eax, eax
0x180025d1d  jle     short loc_180025D2B
0x180025d1f  movzx   eax, ax
0x180025d22  or      eax, 80070000h
0x180025d27  jmp     short loc_180025D2B
0x180025d29  xor     eax, eax
0x180025d2b  mov     rbx, [rsp+58h+arg_8]
0x180025d30  add     rsp, 40h
0x180025d34  pop     rdi
0x180025d35  pop     rsi
0x180025d36  pop     rbp
0x180025d37  retn
```
