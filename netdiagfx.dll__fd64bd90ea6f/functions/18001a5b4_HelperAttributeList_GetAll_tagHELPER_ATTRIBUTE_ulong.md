# HelperAttributeList::GetAll(tagHELPER_ATTRIBUTE * *,ulong *)

- ea: `0x18001a5b4`
- end: `0x18001a660`
- name: `?GetAll@HelperAttributeList@@QEAAJPEAPEAUtagHELPER_ATTRIBUTE@@PEAK@Z`
- size: `172`
- prototype: `__int64 __fastcall(HelperAttributeList *__hidden this, struct tagHELPER_ATTRIBUTE **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180009f54`
- `0x18000bda4`
- `0x18001a5b4`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a5e2`

## pseudocode

```c
__int64 __fastcall HelperAttributeList::GetAll(
        HelperAttributeList *this,
        struct tagHELPER_ATTRIBUTE **a2,
        unsigned int *a3)
{
  struct tagHELPER_ATTRIBUTE *v7; // rdi
  __int64 v8; // rsi
  int v9; // ebp
  __int64 i; // rbx

  if ( !*((_DWORD *)this + 4) )
    return 2147942632LL;
  v7 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144LL * *((unsigned int *)this + 4));
  if ( !v7 )
    return 2147942414LL;
  memset_0(v7, 0, 144LL * *((unsigned int *)this + 4));
  v8 = *(_QWORD *)this;
  v9 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( !v8 )
    {
      *a2 = v7;
      *a3 = i;
      return (unsigned int)v9;
    }
    v9 = CopyHelperAttribute(&v7[i], *(const struct tagHELPER_ATTRIBUTE **)v8);
    if ( v9 < 0 )
      break;
    v8 = *(_QWORD *)(v8 + 8);
  }
  FreeHelperAttributes(v7, i, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a5b4  push    rbx
0x18001a5b6  push    rbp
0x18001a5b7  push    rsi
0x18001a5b8  push    rdi
0x18001a5b9  push    r14
0x18001a5bb  push    r15
0x18001a5bd  sub     rsp, 28h
0x18001a5c1  cmp     dword ptr [rcx+10h], 0
0x18001a5c5  mov     r14, r8
0x18001a5c8  mov     r15, rdx
0x18001a5cb  mov     rsi, rcx
0x18001a5ce  jnz     short loc_18001A5D7
0x18001a5d0  mov     eax, 800700E8h
0x18001a5d5  jmp     short loc_18001A641
0x18001a5d7  mov     eax, [rcx+10h]
0x18001a5da  lea     rcx, [rax+rax*8]
0x18001a5de  shl     rcx, 4; cb
0x18001a5e2  call    cs:__imp_CoTaskMemAlloc
0x18001a5e8  mov     rdi, rax
0x18001a5eb  test    rax, rax
0x18001a5ee  jnz     short loc_18001A5F7
0x18001a5f0  mov     eax, 8007000Eh
0x18001a5f5  jmp     short loc_18001A641
0x18001a5f7  mov     eax, [rsi+10h]
0x18001a5fa  xor     edx, edx; Val
0x18001a5fc  mov     rcx, rdi; void *
0x18001a5ff  lea     r8, [rax+rax*8]
0x18001a603  shl     r8, 4; Size
0x18001a607  call    memset_0
0x18001a60c  mov     rsi, [rsi]
0x18001a60f  xor     ebp, ebp
0x18001a611  xor     ebx, ebx
0x18001a613  jmp     short loc_18001A634
0x18001a615  mov     rdx, [rsi]; struct tagHELPER_ATTRIBUTE *
0x18001a618  lea     rcx, [rbx+rbx*8]
0x18001a61c  shl     rcx, 4
0x18001a620  add     rcx, rdi; struct tagHELPER_ATTRIBUTE *
0x18001a623  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18001a628  mov     ebp, eax
0x18001a62a  test    eax, eax
0x18001a62c  js      short loc_18001A64E
0x18001a62e  mov     rsi, [rsi+8]
0x18001a632  inc     ebx
0x18001a634  test    rsi, rsi
0x18001a637  jnz     short loc_18001A615
0x18001a639  mov     [r15], rdi
0x18001a63c  mov     [r14], ebx
0x18001a63f  mov     eax, ebp
0x18001a641  add     rsp, 28h
0x18001a645  pop     r15
0x18001a647  pop     r14
0x18001a649  pop     rdi
0x18001a64a  pop     rsi
0x18001a64b  pop     rbp
0x18001a64c  pop     rbx
0x18001a64d  retn
0x18001a64e  mov     r8d, 1; int
0x18001a654  mov     edx, ebx; unsigned int
0x18001a656  mov     rcx, rdi; pv
0x18001a659  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18001a65e  jmp     short loc_18001A63F
```
