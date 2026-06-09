# CTempBuffer<char,512>::CTempBuffer<char,512>(int)

- ea: `0x140003aec`
- end: `0x140003b3e`
- name: `??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400078f0`

## callees

- `0x140003883`
- `0x140003aec`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140003b0c`
- `KERNEL32!GlobalAlloc` at `0x140003b0c`

## pseudocode

```c
__int64 __fastcall CTempBuffer<char,512>::CTempBuffer<char,512>(__int64 a1, int a2)
{
  HGLOBAL v3; // rax
  __int64 v4; // rbx

  *(_DWORD *)(a1 + 8) = a2;
  if ( a2 <= 512 )
  {
    v4 = a1 + 16;
    memset_0((void *)(a1 + 16), 0, 0x200u);
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
0x140003aec  mov     [rsp+arg_0], rbx
0x140003af1  push    rdi
0x140003af2  sub     rsp, 20h
0x140003af6  mov     r8d, 200h; Size
0x140003afc  mov     [rcx+8], edx
0x140003aff  mov     rdi, rcx
0x140003b02  cmp     edx, r8d
0x140003b05  jle     short loc_140003B1F
0x140003b07  movsxd  rdx, edx; dwBytes
0x140003b0a  xor     ecx, ecx; uFlags
0x140003b0c  call    cs:__imp_GlobalAlloc
0x140003b12  mov     [rdi], rax
0x140003b15  test    rax, rax
0x140003b18  jnz     short loc_140003B30
0x140003b1a  mov     [rdi+8], eax
0x140003b1d  jmp     short loc_140003B30
0x140003b1f  lea     rbx, [rcx+10h]
0x140003b23  xor     edx, edx; Val
0x140003b25  mov     rcx, rbx; void *
0x140003b28  call    memset_0
0x140003b2d  mov     [rdi], rbx
0x140003b30  mov     rbx, [rsp+28h+arg_0]
0x140003b35  mov     rax, rdi
0x140003b38  add     rsp, 20h
0x140003b3c  pop     rdi
0x140003b3d  retn
```
