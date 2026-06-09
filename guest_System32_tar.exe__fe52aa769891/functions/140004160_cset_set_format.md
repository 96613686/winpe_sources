# cset_set_format

- ea: `0x140004160`
- end: `0x1400041a7`
- name: `cset_set_format`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f9c`
- `0x140003f80`
- `0x1400061dc`

## callees

- `0x140004160`
- `0x1400071a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140004170`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140004170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140004181`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140004181`

## pseudocode

```c
void __fastcall cset_set_format(void **a1, __int64 a2)
{
  __int64 v3; // rdi

  v3 = _o__strdup(a2);
  if ( !v3 )
    lafe_errc(1, 0, (__int64)"No memory");
  free(*a1);
  *a1 = (void *)v3;
}

```

## disassembly

```asm
0x140004160  mov     [rsp+arg_0], rbx
0x140004165  push    rdi
0x140004166  sub     rsp, 20h
0x14000416a  mov     rbx, rcx
0x14000416d  mov     rcx, rdx
0x140004170  call    cs:__imp__o__strdup
0x140004176  mov     rdi, rax
0x140004179  test    rax, rax
0x14000417c  jz      short loc_140004195
0x14000417e  mov     rcx, [rbx]; Block
0x140004181  call    cs:__imp_free
0x140004187  mov     [rbx], rdi
0x14000418a  mov     rbx, [rsp+28h+arg_0]
0x14000418f  add     rsp, 20h
0x140004193  pop     rdi
0x140004194  retn
0x140004195  xor     edx, edx
0x140004197  lea     r8, aNoMemory; "No memory"
0x14000419e  lea     ecx, [rdx+1]; Code
0x1400041a1  call    lafe_errc
```
