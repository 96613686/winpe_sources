# com_ptr<uchar>::Assign(uchar const *,unsigned __int64)

- ea: `0x1800052f4`
- end: `0x180005369`
- name: `?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD *, void *, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005d30`

## callees

- `0x180003990`
- `0x1800052f4`
- `0x180005370`
- `0x18002ed84`
- `0x18002edf4`

## string_xrefs

- `0x18000533d`: `com_ptr::Assign NULL pointer`
- `0x180005336`: `com_ptr::Assign Wrong length`
- `0x180005321`: `com_ptr::Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall com_ptr<unsigned char>::Assign(_QWORD *a1, void *a2, size_t a3)
{
  void *v4; // rdi
  const wchar_t *v5; // rcx
  __int64 result; // rax

  if ( !a2 )
  {
    if ( !a3 )
      goto LABEL_3;
LABEL_6:
    v5 = L"com_ptr::Assign NULL pointer";
    if ( !a3 )
      v5 = L"com_ptr::Assign Wrong length";
    SystemError::ThrowHelper(v5, -2147024736);
  }
  if ( !a3 )
    goto LABEL_6;
LABEL_3:
  v4 = Copy<TaskAllocator>(a2, a3);
  if ( !v4 )
    LowMemoryError::Throw(L"com_ptr::Assign");
  result = com_ptr<unsigned char>::Clear(a1);
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800052f4  mov     [rsp+arg_0], rbx
0x1800052f9  push    rdi
0x1800052fa  sub     rsp, 20h
0x1800052fe  mov     rax, rdx
0x180005301  mov     rbx, rcx
0x180005304  test    rdx, rdx
0x180005307  jnz     short loc_18000532E
0x180005309  test    r8, r8
0x18000530c  jnz     short loc_180005333
0x18000530e  mov     rdx, r8; Size
0x180005311  mov     rcx, rax; Src
0x180005314  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180005319  mov     rdi, rax
0x18000531c  test    rax, rax
0x18000531f  jnz     short loc_180005353
0x180005321  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180005328  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18000532e  test    r8, r8
0x180005331  jnz     short loc_18000530E
0x180005333  test    r8, r8
0x180005336  lea     rax, aComPtrAssignWr; "com_ptr::Assign Wrong length"
0x18000533d  lea     rcx, aComPtrAssignNu; "com_ptr::Assign NULL pointer"
0x180005344  mov     edx, 800700A0h; int
0x180005349  cmovz   rcx, rax; wchar_t *
0x18000534d  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180005353  mov     rcx, rbx
0x180005356  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000535b  mov     [rbx], rdi
0x18000535e  mov     rbx, [rsp+28h+arg_0]
0x180005363  add     rsp, 20h
0x180005367  pop     rdi
0x180005368  retn
```
