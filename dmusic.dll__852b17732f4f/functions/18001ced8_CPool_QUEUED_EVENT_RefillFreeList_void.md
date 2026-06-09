# CPool<QUEUED_EVENT>::RefillFreeList(void)

- ea: `0x18001ced8`
- end: `0x18001cf84`
- name: `?RefillFreeList@?$CPool@UQUEUED_EVENT@@@@AEAA_NXZ`
- size: `172`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001c38c`
- `0x18001cdfc`
- `0x18001d3f8`
- `0x18001fb6c`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x18001ced8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ceea`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ceea`

## pseudocode

```c
char __fastcall CPool<QUEUED_EVENT>::RefillFreeList(int *a1)
{
  _QWORD *v2; // rdi
  char result; // al
  void *v4; // rax
  __int64 v5; // rdx
  _QWORD *v6; // r8
  _QWORD *v7; // rdx
  _QWORD *i; // rcx

  v2 = malloc(0x10u);
  if ( !v2 )
    return 0;
  v4 = operator new[](saturated_mul(*a1, 0x20u));
  v2[1] = v4;
  if ( !v4 )
  {
    operator delete(v2);
    return 0;
  }
  *v2 = *((_QWORD *)a1 + 1);
  v5 = 32LL * *a1 - 32;
  *((_QWORD *)a1 + 1) = v2;
  v6 = (_QWORD *)v2[1];
  v7 = (_QWORD *)((char *)v6 + v5);
  for ( i = v6; i < v7; i += 4 )
    *i = i + 4;
  *v7 = *((_QWORD *)a1 + 3);
  a1[4] += *a1;
  result = 1;
  ++a1[1];
  *((_QWORD *)a1 + 3) = v6;
  return result;
}

```

## disassembly

```asm
0x18001ced8  mov     [rsp+arg_0], rbx
0x18001cedd  push    rdi
0x18001cede  sub     rsp, 20h
0x18001cee2  mov     rbx, rcx
0x18001cee5  mov     ecx, 10h; Size
0x18001ceea  call    cs:__imp_malloc
0x18001cef0  mov     rdi, rax
0x18001cef3  test    rax, rax
0x18001cef6  jnz     short loc_18001CEFC
0x18001cef8  xor     al, al
0x18001cefa  jmp     short loc_18001CF79
0x18001cefc  movsxd  rcx, dword ptr [rbx]
0x18001ceff  mov     eax, 20h ; ' '
0x18001cf04  mul     rcx
0x18001cf07  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cf0e  cmovb   rax, rcx
0x18001cf12  mov     rcx, rax; unsigned __int64
0x18001cf15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001cf1a  mov     [rdi+8], rax
0x18001cf1e  test    rax, rax
0x18001cf21  jnz     short loc_18001CF30
0x18001cf23  lea     edx, [rax+10h]; unsigned __int64
0x18001cf26  mov     rcx, rdi; void *
0x18001cf29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cf2e  jmp     short loc_18001CEF8
0x18001cf30  mov     rax, [rbx+8]
0x18001cf34  mov     [rdi], rax
0x18001cf37  movsxd  rdx, dword ptr [rbx]
0x18001cf3a  shl     rdx, 5
0x18001cf3e  add     rdx, 0FFFFFFFFFFFFFFE0h
0x18001cf42  mov     [rbx+8], rdi
0x18001cf46  mov     r8, [rdi+8]
0x18001cf4a  add     rdx, r8
0x18001cf4d  mov     rcx, r8
0x18001cf50  cmp     r8, rdx
0x18001cf53  jnb     short loc_18001CF64
0x18001cf55  lea     rax, [rcx+20h]
0x18001cf59  mov     [rcx], rax
0x18001cf5c  mov     rcx, rax
0x18001cf5f  cmp     rax, rdx
0x18001cf62  jb      short loc_18001CF55
0x18001cf64  mov     rax, [rbx+18h]
0x18001cf68  mov     [rdx], rax
0x18001cf6b  mov     eax, [rbx]
0x18001cf6d  add     [rbx+10h], eax
0x18001cf70  mov     al, 1
0x18001cf72  inc     dword ptr [rbx+4]
0x18001cf75  mov     [rbx+18h], r8
0x18001cf79  mov     rbx, [rsp+28h+arg_0]
0x18001cf7e  add     rsp, 20h
0x18001cf82  pop     rdi
0x18001cf83  retn
```
