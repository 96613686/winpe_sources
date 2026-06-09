# CTempBuffer<char,256>::CTempBuffer<char,256>(int)

- ea: `0x140003a94`
- end: `0x140003ae6`
- name: `??0?$CTempBuffer@D$0BAA@@@QEAA@H@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011e4`

## callees

- `0x140003883`
- `0x140003a94`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140003ab4`
- `KERNEL32!GlobalAlloc` at `0x140003ab4`

## pseudocode

```c
__int64 __fastcall CTempBuffer<char,256>::CTempBuffer<char,256>(__int64 a1, int a2)
{
  HGLOBAL v3; // rax
  __int64 v4; // rbx

  *(_DWORD *)(a1 + 8) = a2;
  if ( a2 <= 256 )
  {
    v4 = a1 + 16;
    memset_0((void *)(a1 + 16), 0, 0x100u);
    *(_QWORD *)a1 = v4;
  }
  else
  {
    v3 = GlobalAlloc(0, a2);
    *(_QWORD *)a1 = v3;
    if ( !v3 )
      *(_DWORD *)(a1 + 8) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140003a94  mov     [rsp+arg_0], rbx
0x140003a99  push    rdi
0x140003a9a  sub     rsp, 20h
0x140003a9e  mov     r8d, 100h; Size
0x140003aa4  mov     [rcx+8], edx
0x140003aa7  mov     rdi, rcx
0x140003aaa  cmp     edx, r8d
0x140003aad  jle     short loc_140003AC7
0x140003aaf  movsxd  rdx, edx; dwBytes
0x140003ab2  xor     ecx, ecx; uFlags
0x140003ab4  call    cs:__imp_GlobalAlloc
0x140003aba  mov     [rdi], rax
0x140003abd  test    rax, rax
0x140003ac0  jnz     short loc_140003AD8
0x140003ac2  mov     [rdi+8], eax
0x140003ac5  jmp     short loc_140003AD8
0x140003ac7  lea     rbx, [rcx+10h]
0x140003acb  xor     edx, edx; Val
0x140003acd  mov     rcx, rbx; void *
0x140003ad0  call    memset_0
0x140003ad5  mov     [rdi], rbx
0x140003ad8  mov     rbx, [rsp+28h+arg_0]
0x140003add  mov     rax, rdi
0x140003ae0  add     rsp, 20h
0x140003ae4  pop     rdi
0x140003ae5  retn
```
