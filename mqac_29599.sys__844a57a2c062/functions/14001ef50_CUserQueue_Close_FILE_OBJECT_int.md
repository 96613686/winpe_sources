# CUserQueue::Close(_FILE_OBJECT *,int)

- ea: `0x14001ef50`
- end: `0x14001efba`
- name: `?Close@CUserQueue@@UEAAXPEAU_FILE_OBJECT@@H@Z`
- size: `106`
- prototype: `void(CUserQueue *__hidden this, struct _FILE_OBJECT *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001b870`
- `0x14001ca00`

## callees

- `0x14000c87c`
- `0x140019d90`
- `0x14001ef50`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14001efa2`
- `ntoskrnl!IoRemoveShareAccess` at `0x14001efa2`

## pseudocode

```c
void __fastcall CUserQueue::Close(CUserQueue *this, struct _FILE_OBJECT *a2, int a3)
{
  CUserQueue *v6; // rdi
  struct _FILE_OBJECT **v7; // rcx

  CQueueBase::Close(this, a2, a3);
  v6 = (CUserQueue *)*((_QWORD *)this + 9);
  while ( 1 )
  {
    v7 = 0;
    if ( (CUserQueue *)((char *)this + 72) != v6 )
      v7 = (struct _FILE_OBJECT **)((char *)v6 - 16);
    if ( !v7 )
      break;
    v6 = *(CUserQueue **)v6;
    if ( a3 || v7[6] == a2 )
      CCursor::Close((CCursor *)v7);
  }
  if ( a2 )
    IoRemoveShareAccess(a2, (PSHARE_ACCESS)((char *)this + 120));
}

```

## disassembly

```asm
0x14001ef50  push    rbx
0x14001ef52  push    rbp
0x14001ef53  push    rsi
0x14001ef54  push    rdi
0x14001ef55  push    r14
0x14001ef57  sub     rsp, 20h
0x14001ef5b  mov     ebp, r8d
0x14001ef5e  mov     rbx, rdx
0x14001ef61  mov     rsi, rcx
0x14001ef64  call    ?Close@CQueueBase@@UEAAXPEAU_FILE_OBJECT@@H@Z; CQueueBase::Close(_FILE_OBJECT *,int)
0x14001ef69  lea     r14, [rsi+48h]
0x14001ef6d  mov     rdi, [r14]
0x14001ef70  xor     ecx, ecx
0x14001ef72  lea     rax, [rdi-10h]
0x14001ef76  cmp     r14, rdi
0x14001ef79  cmovnz  rcx, rax; this
0x14001ef7d  test    rcx, rcx
0x14001ef80  jz      short loc_14001EF96
0x14001ef82  mov     rdi, [rdi]
0x14001ef85  test    ebp, ebp
0x14001ef87  jnz     short loc_14001EF8F
0x14001ef89  cmp     [rcx+30h], rbx
0x14001ef8d  jnz     short loc_14001EF70
0x14001ef8f  call    ?Close@CCursor@@QEAAXXZ; CCursor::Close(void)
0x14001ef94  jmp     short loc_14001EF70
0x14001ef96  test    rbx, rbx
0x14001ef99  jz      short loc_14001EFAE
0x14001ef9b  lea     rdx, [rsi+78h]; ShareAccess
0x14001ef9f  mov     rcx, rbx; FileObject
0x14001efa2  call    cs:__imp_IoRemoveShareAccess
0x14001efa9  nop     dword ptr [rax+rax+00h]
0x14001efae  add     rsp, 20h
0x14001efb2  pop     r14
0x14001efb4  pop     rdi
0x14001efb5  pop     rsi
0x14001efb6  pop     rbp
0x14001efb7  pop     rbx
0x14001efb8  retn
```
