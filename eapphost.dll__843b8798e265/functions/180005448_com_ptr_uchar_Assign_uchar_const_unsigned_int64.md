# com_ptr<uchar>::Assign(uchar const *,unsigned __int64)

- ea: `0x180005448`
- end: `0x1800054be`
- name: `?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005f60`

## callees

- `0x180003a30`
- `0x180005448`
- `0x1800054c4`
- `0x18002fe84`
- `0x18002fef4`

## string_xrefs

- `0x180005491`: `com_ptr::Assign NULL pointer`
- `0x18000548a`: `com_ptr::Assign Wrong length`
- `0x180005475`: `com_ptr::Assign`

## pseudocode

```c
void __fastcall com_ptr<unsigned char>::Assign(void **a1, void *a2, size_t a3)
{
  void *v4; // rdi
  const wchar_t *v5; // rcx

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
  com_ptr<unsigned char>::Clear(a1);
  *a1 = v4;
}

```

## disassembly

```asm
0x180005448  mov     [rsp+arg_0], rbx
0x18000544d  push    rdi
0x18000544e  sub     rsp, 20h
0x180005452  mov     rax, rdx
0x180005455  mov     rbx, rcx
0x180005458  test    rdx, rdx
0x18000545b  jnz     short loc_180005482
0x18000545d  test    r8, r8
0x180005460  jnz     short loc_180005487
0x180005462  mov     rdx, r8; Size
0x180005465  mov     rcx, rax; Src
0x180005468  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x18000546d  mov     rdi, rax
0x180005470  test    rax, rax
0x180005473  jnz     short loc_1800054A7
0x180005475  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x18000547c  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180005482  test    r8, r8
0x180005485  jnz     short loc_180005462
0x180005487  test    r8, r8
0x18000548a  lea     rax, aComPtrAssignWr; "com_ptr::Assign Wrong length"
0x180005491  lea     rcx, aComPtrAssignNu; "com_ptr::Assign NULL pointer"
0x180005498  mov     edx, 800700A0h; int
0x18000549d  cmovz   rcx, rax; wchar_t *
0x1800054a1  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800054a7  mov     rcx, rbx
0x1800054aa  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x1800054af  mov     [rbx], rdi
0x1800054b2  mov     rbx, [rsp+28h+arg_0]
0x1800054b7  add     rsp, 20h
0x1800054bb  pop     rdi
0x1800054bc  retn
```
