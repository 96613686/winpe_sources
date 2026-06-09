# TLinkedListDeallocator<CNDFHelperClass *>::~TLinkedListDeallocator<CNDFHelperClass *>(void)

- ea: `0x1800055d0`
- end: `0x180005636`
- name: `??1?$TLinkedListDeallocator@PEAVCNDFHelperClass@@@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005790`

## callees

- `0x1800055d0`
- `0x18000cb80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800055fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000560d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800055fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000560d`

## pseudocode

```c
void __fastcall TLinkedListDeallocator<CNDFHelperClass *>::~TLinkedListDeallocator<CNDFHelperClass *>(__int64 *a1)
{
  __int64 v1; // rbx
  CNDFHelperClass *v3; // rsi
  void *v4; // rcx

  v1 = *a1;
  while ( v1 )
  {
    v3 = *(CNDFHelperClass **)v1;
    if ( *(_QWORD *)v1 )
    {
      CNDFHelperClass::~CNDFHelperClass(*(CNDFHelperClass **)v1);
      operator delete(v3);
    }
    v4 = (void *)v1;
    v1 = *(_QWORD *)(v1 + 8);
    operator delete(v4);
  }
  *a1 = 0;
  a1[1] = 0;
}

```

## disassembly

```asm
0x1800055d0  mov     [rsp+arg_0], rbx
0x1800055d5  mov     [rsp+arg_8], rsi
0x1800055da  push    rdi
0x1800055db  sub     rsp, 20h
0x1800055df  mov     rbx, [rcx]
0x1800055e2  mov     rdi, rcx
0x1800055e5  jmp     short loc_180005619
0x1800055e7  mov     rsi, [rbx]
0x1800055ea  test    rsi, rsi
0x1800055ed  jz      short loc_180005606
0x1800055ef  mov     rcx, rsi; this
0x1800055f2  call    ??1CNDFHelperClass@@QEAA@XZ; CNDFHelperClass::~CNDFHelperClass(void)
0x1800055f7  mov     rcx, rsi
0x1800055fa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005601  nop     dword ptr [rax+rax+00h]
0x180005606  mov     rcx, rbx
0x180005609  mov     rbx, [rbx+8]
0x18000560d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005614  nop     dword ptr [rax+rax+00h]
0x180005619  test    rbx, rbx
0x18000561c  jnz     short loc_1800055E7
0x18000561e  mov     rsi, [rsp+28h+arg_8]
0x180005623  mov     [rdi], rbx
0x180005626  mov     [rdi+8], rbx
0x18000562a  mov     rbx, [rsp+28h+arg_0]
0x18000562f  add     rsp, 20h
0x180005633  pop     rdi
0x180005634  retn
```
