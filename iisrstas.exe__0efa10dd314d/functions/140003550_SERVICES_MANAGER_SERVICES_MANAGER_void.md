# SERVICES_MANAGER::~SERVICES_MANAGER(void)

- ea: `0x140003550`
- end: `0x1400035a0`
- name: `??1SERVICES_MANAGER@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(SERVICES_MANAGER *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140002ec0`
- `0x140003110`
- `0x1400031d0`
- `0x1400032a0`

## callees

- `0x140001054`
- `0x140003550`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x140003599`

## pseudocode

```c
void __fastcall SERVICES_MANAGER::~SERVICES_MANAGER(SERVICES_MANAGER *this)
{
  unsigned int v1; // esi
  unsigned int i; // edi
  unsigned int v4; // edx
  void *v5; // rcx

  v1 = *((_DWORD *)this + 2);
  for ( i = 0; i < v1; ++i )
  {
    v4 = *((_DWORD *)this + 2) - 1;
    v5 = *(void **)(*((_QWORD *)this + 6) + 8LL * v4);
    *((_DWORD *)this + 2) = v4;
    operator delete(v5);
  }
  BUFFER::~BUFFER((SERVICES_MANAGER *)((char *)this + 16));
}

```

## disassembly

```asm
0x140003550  mov     [rsp+arg_0], rbx
0x140003555  mov     [rsp+arg_8], rsi
0x14000355a  push    rdi
0x14000355b  sub     rsp, 20h
0x14000355f  mov     esi, [rcx+8]
0x140003562  xor     edi, edi
0x140003564  mov     rbx, rcx
0x140003567  test    esi, esi
0x140003569  jz      short loc_140003586
0x14000356b  mov     edx, [rbx+8]
0x14000356e  dec     edx
0x140003570  mov     rax, [rbx+30h]
0x140003574  mov     rcx, [rax+rdx*8]; Block
0x140003578  mov     [rbx+8], edx
0x14000357b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003580  inc     edi
0x140003582  cmp     edi, esi
0x140003584  jb      short loc_14000356B
0x140003586  lea     rcx, [rbx+10h]
0x14000358a  mov     rbx, [rsp+28h+arg_0]
0x14000358f  mov     rsi, [rsp+28h+arg_8]
0x140003594  add     rsp, 20h
0x140003598  pop     rdi
0x140003599  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
