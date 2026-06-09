# SSI_FILE::~SSI_FILE(void)

- ea: `0x18000256c`
- end: `0x1800025d5`
- name: `??1SSI_FILE@@EEAA@XZ`
- size: `105`
- prototype: `void __fastcall(SSI_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800025e0`

## callees

- `0x180001048`
- `0x18000256c`
- `0x180002b7c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002593`

## pseudocode

```c
void __fastcall SSI_FILE::~SSI_FILE(SSI_FILE *this)
{
  void *v2; // rcx
  SSI_ELEMENT_LIST *v3; // rdi

  *((_DWORD *)this + 2) = 1483302515;
  *(_QWORD *)this = &SSI_FILE::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (SSI_ELEMENT_LIST *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 2) = 0;
  if ( v3 )
  {
    SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST(v3);
    operator delete(v3);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x18000256c  mov     [rsp+arg_0], rbx
0x180002571  push    rdi
0x180002572  sub     rsp, 20h
0x180002576  lea     rax, ??_7SSI_FILE@@6B@; const SSI_FILE::`vftable'
0x18000257d  mov     dword ptr [rcx+8], 58696673h
0x180002584  mov     [rcx], rax
0x180002587  mov     rbx, rcx
0x18000258a  mov     rcx, [rcx+18h]; hMem
0x18000258e  test    rcx, rcx
0x180002591  jz      short loc_1800025A1
0x180002593  call    cs:__imp_LocalFree
0x180002599  mov     qword ptr [rbx+18h], 0
0x1800025a1  mov     rdi, [rbx+20h]
0x1800025a5  mov     qword ptr [rbx+10h], 0
0x1800025ad  test    rdi, rdi
0x1800025b0  jz      short loc_1800025CA
0x1800025b2  mov     rcx, rdi; this
0x1800025b5  call    ??1SSI_ELEMENT_LIST@@QEAA@XZ; SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST(void)
0x1800025ba  mov     rcx, rdi; Block
0x1800025bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025c2  mov     qword ptr [rbx+20h], 0
0x1800025ca  mov     rbx, [rsp+28h+arg_0]
0x1800025cf  add     rsp, 20h
0x1800025d3  pop     rdi
0x1800025d4  retn
```
