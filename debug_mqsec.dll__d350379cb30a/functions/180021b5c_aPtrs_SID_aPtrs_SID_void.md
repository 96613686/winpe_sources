# aPtrs<_SID>::~aPtrs<_SID>(void)

- ea: `0x180021b5c`
- end: `0x180021b9f`
- name: `??1?$aPtrs@U_SID@@@@QEAA@XZ`
- size: `67`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180022a40`
- `0x180022d08`
- `0x180024b90`
- `0x180024dbc`
- `0x180030563`
- `0x180030575`
- `0x180030587`

## callees

- `0x180021b5c`

## import_xrefs

- `msvcrt!free` at `0x180021b7c`
- `msvcrt!free` at `0x180021b8d`
- `msvcrt!free` at `0x180021b7c`
- `msvcrt!free` at `0x180021b8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall aPtrs<_SID>::~aPtrs<_SID>(__int64 a1)
{
  __int64 i; // rbx
  void *v3; // rcx

  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
  {
    v3 = *(void **)(*(_QWORD *)a1 + 8 * i);
    if ( v3 )
      free(v3);
  }
  free(*(void **)a1);
}

```

## disassembly

```asm
0x180021b5c  mov     [rsp+arg_0], rbx
0x180021b61  push    rdi
0x180021b62  sub     rsp, 20h
0x180021b66  mov     rdi, rcx
0x180021b69  xor     ebx, ebx
0x180021b6b  cmp     [rcx+8], ebx
0x180021b6e  jbe     short loc_180021B8A
0x180021b70  mov     rax, [rdi]
0x180021b73  mov     rcx, [rax+rbx*8]; Block
0x180021b77  test    rcx, rcx
0x180021b7a  jz      short loc_180021B83
0x180021b7c  call    cs:__imp_free
0x180021b82  nop
0x180021b83  inc     ebx
0x180021b85  cmp     ebx, [rdi+8]
0x180021b88  jb      short loc_180021B70
0x180021b8a  mov     rcx, [rdi]; Block
0x180021b8d  call    cs:__imp_free
0x180021b93  nop
0x180021b94  mov     rbx, [rsp+28h+arg_0]
0x180021b99  add     rsp, 20h
0x180021b9d  pop     rdi
0x180021b9e  retn
```
