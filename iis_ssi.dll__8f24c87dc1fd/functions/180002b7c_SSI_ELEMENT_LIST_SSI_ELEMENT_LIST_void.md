# SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST(void)

- ea: `0x180002b7c`
- end: `0x180002c09`
- name: `??1SSI_ELEMENT_LIST@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(SSI_ELEMENT_LIST *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000256c`
- `0x180002978`

## callees

- `0x180001048`
- `0x180002b7c`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180002c02`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd6`

## pseudocode

```c
void __fastcall SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST(SSI_ELEMENT_LIST *this)
{
  _QWORD **v2; // r14
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rdi
  STRA *v7; // rsi

  *(_DWORD *)this = 1716274515;
  v2 = (_QWORD **)((char *)this + 8);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    v6 = v3 - 4;
    *(_QWORD *)(v4 + 8) = v5;
    *v3 = 0;
    if ( v3 != (_QWORD *)32 )
    {
      v7 = (STRA *)v6[2];
      *(_DWORD *)v6 = 1716077907;
      if ( v7 )
      {
        STRA::~STRA(v7);
        operator delete(v7);
      }
      operator delete(v6);
    }
  }
  STRU::~STRU((SSI_ELEMENT_LIST *)((char *)this + 32));
}

```

## disassembly

```asm
0x180002b7c  push    rbx
0x180002b7e  push    rsi
0x180002b7f  push    rdi
0x180002b80  push    r14
0x180002b82  sub     rsp, 28h
0x180002b86  mov     rbx, rcx
0x180002b89  mov     dword ptr [rcx], 664C4553h
0x180002b8f  lea     r14, [rcx+8]
0x180002b93  mov     rax, [r14]
0x180002b96  cmp     rax, r14
0x180002b99  jz      short loc_180002BF5
0x180002b9b  mov     rcx, [rax]
0x180002b9e  cmp     [rcx+8], rax
0x180002ba2  jnz     short loc_180002BEE
0x180002ba4  mov     rdx, [rax+8]
0x180002ba8  cmp     [rdx], rax
0x180002bab  jnz     short loc_180002BEE
0x180002bad  mov     [rdx], rcx
0x180002bb0  lea     rdi, [rax-20h]
0x180002bb4  mov     [rcx+8], rdx
0x180002bb8  mov     qword ptr [rax], 0
0x180002bbf  test    rdi, rdi
0x180002bc2  jz      short loc_180002B93
0x180002bc4  mov     rsi, [rdi+10h]
0x180002bc8  mov     dword ptr [rdi], 66494553h
0x180002bce  test    rsi, rsi
0x180002bd1  jz      short loc_180002BE4
0x180002bd3  mov     rcx, rsi
0x180002bd6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002bdc  mov     rcx, rsi; Block
0x180002bdf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002be4  mov     rcx, rdi; Block
0x180002be7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002bec  jmp     short loc_180002B93
0x180002bee  mov     ecx, 3
0x180002bf3  int     29h; Win8: RtlFailFast(ecx)
0x180002bf5  lea     rcx, [rbx+20h]
0x180002bf9  add     rsp, 28h
0x180002bfd  pop     r14
0x180002bff  pop     rdi
0x180002c00  pop     rsi
0x180002c01  pop     rbx
0x180002c02  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
