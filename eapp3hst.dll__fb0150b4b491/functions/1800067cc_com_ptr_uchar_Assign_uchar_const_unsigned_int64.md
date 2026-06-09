# com_ptr<uchar>::Assign(uchar const *,unsigned __int64)

- ea: `0x1800067cc`
- end: `0x180006841`
- name: `?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD *, void *, size_t)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180007fe0`
- `0x18000d430`
- `0x18000d6e0`
- `0x18000d9c0`
- `0x18000dd50`
- `0x18000df60`
- `0x18000e250`
- `0x18001fb30`

## callees

- `0x18000503c`
- `0x1800067cc`
- `0x180006c0c`
- `0x180012a00`
- `0x180012a70`

## string_xrefs

- `0x180006815`: `com_ptr::Assign NULL pointer`
- `0x18000680e`: `com_ptr::Assign Wrong length`
- `0x1800067f9`: `com_ptr::Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800067cc  mov     [rsp+arg_0], rbx
0x1800067d1  push    rdi
0x1800067d2  sub     rsp, 20h
0x1800067d6  mov     rax, rdx
0x1800067d9  mov     rbx, rcx
0x1800067dc  test    rdx, rdx
0x1800067df  jnz     short loc_180006806
0x1800067e1  test    r8, r8
0x1800067e4  jnz     short loc_18000680B
0x1800067e6  mov     rdx, r8; Size
0x1800067e9  mov     rcx, rax; Src
0x1800067ec  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x1800067f1  mov     rdi, rax
0x1800067f4  test    rax, rax
0x1800067f7  jnz     short loc_18000682B
0x1800067f9  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180006800  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180006806  test    r8, r8
0x180006809  jnz     short loc_1800067E6
0x18000680b  test    r8, r8
0x18000680e  lea     rax, aComPtrAssignWr; "com_ptr::Assign Wrong length"
0x180006815  lea     rcx, aComPtrAssignNu; "com_ptr::Assign NULL pointer"
0x18000681c  mov     edx, 800700A0h; int
0x180006821  cmovz   rcx, rax; wchar_t *
0x180006825  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18000682b  mov     rcx, rbx
0x18000682e  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180006833  mov     [rbx], rdi
0x180006836  mov     rbx, [rsp+28h+arg_0]
0x18000683b  add     rsp, 20h
0x18000683f  pop     rdi
0x180006840  retn
```
