# CLruCache::Fetch(void *,void *,ulong)

- ea: `0x180017e00`
- end: `0x180017e92`
- name: `?Fetch@CLruCache@@UEAAJPEAX0K@Z`
- size: `146`
- prototype: `__int64 __fastcall(CLruCache *__hidden this, void *, void *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c368`
- `0x18000d798`
- `0x18000e208`
- `0x180017ee4`
- `0x180019c40`

## callees

- `0x180017e00`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017e2a`
- `KERNEL32!EnterCriticalSection` at `0x180017e2a`
- `KERNEL32!LeaveCriticalSection` at `0x180017e77`
- `KERNEL32!LeaveCriticalSection` at `0x180017e77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLruCache::Fetch(CLruCache *this, void *a2, void *a3, unsigned int a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD *i; // rdi
  unsigned int v10; // edi

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  for ( i = (_QWORD *)*((_QWORD *)this + 2); i; i = (_QWORD *)i[1] )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD *, void *))(*i + 8LL))(i, a2) )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD *, void *, _QWORD))(*i + 24LL))(i, a3, a4);
      goto LABEL_7;
    }
  }
  v10 = 1;
LABEL_7:
  LeaveCriticalSection(v8);
  return v10;
}

```

## disassembly

```asm
0x180017e00  mov     [rsp+arg_8], rbx
0x180017e05  mov     [rsp+arg_10], rbp
0x180017e0a  push    rsi
0x180017e0b  push    rdi
0x180017e0c  push    r14
0x180017e0e  sub     rsp, 20h
0x180017e12  mov     ebp, r9d
0x180017e15  mov     r14, r8
0x180017e18  mov     rsi, rdx
0x180017e1b  mov     rdi, rcx
0x180017e1e  lea     rbx, [rcx+18h]
0x180017e22  mov     [rsp+38h+arg_0], rbx
0x180017e27  mov     rcx, rbx; lpCriticalSection
0x180017e2a  call    cs:__imp_EnterCriticalSection
0x180017e30  nop
0x180017e31  mov     rdi, [rdi+10h]
0x180017e35  test    rdi, rdi
0x180017e38  jz      short loc_180017E6F
0x180017e3a  mov     rax, [rdi]
0x180017e3d  mov     rdx, rsi
0x180017e40  mov     rcx, rdi
0x180017e43  mov     rax, [rax+8]
0x180017e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e4c  test    eax, eax
0x180017e4e  jnz     short loc_180017E56
0x180017e50  mov     rdi, [rdi+8]
0x180017e54  jmp     short loc_180017E35
0x180017e56  mov     rax, [rdi]
0x180017e59  mov     r8d, ebp
0x180017e5c  mov     rdx, r14
0x180017e5f  mov     rcx, rdi
0x180017e62  mov     rax, [rax+18h]
0x180017e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e6b  mov     edi, eax
0x180017e6d  jmp     short loc_180017E74
0x180017e6f  mov     edi, 1
0x180017e74  mov     rcx, rbx; lpCriticalSection
0x180017e77  call    cs:__imp_LeaveCriticalSection
0x180017e7d  mov     eax, edi
0x180017e7f  mov     rbx, [rsp+38h+arg_8]
0x180017e84  mov     rbp, [rsp+38h+arg_10]
0x180017e89  add     rsp, 20h
0x180017e8d  pop     r14
0x180017e8f  pop     rdi
0x180017e90  pop     rsi
0x180017e91  retn
```
