# SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE(void)

- ea: `0x180003b7c`
- end: `0x180003c1e`
- name: `??1SSI_INCLUDE_FILE@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(SSI_INCLUDE_FILE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033c8`
- `0x180003c24`

## callees

- `0x180003b7c`
- `0x180006010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180003bfe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003bfe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c17`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003bf1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003bf1`

## pseudocode

```c
void __fastcall SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE(SSI_INCLUDE_FILE *this)
{
  __int64 v1; // rsi
  int v3; // ebx
  __int64 v4; // rcx

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
  {
    v3 = *(_DWORD *)(v1 + 40);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 16) + 16LL))(*(_QWORD *)(v1 + 16));
    if ( !v3 )
      (**(void (__fastcall ***)(__int64))v1)(v1);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = *((_QWORD *)this + 86);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 256LL))(v4);
    *((_QWORD *)this + 86) = 0;
  }
  STRA::~STRA((SSI_INCLUDE_FILE *)((char *)this + 704));
  STRU::~STRU((SSI_INCLUDE_FILE *)((char *)this + 368));
  STRU::~STRU((SSI_INCLUDE_FILE *)((char *)this + 48));
}

```

## disassembly

```asm
0x180003b7c  mov     [rsp+arg_0], rbx
0x180003b81  mov     [rsp+arg_8], rsi
0x180003b86  push    rdi
0x180003b87  sub     rsp, 20h
0x180003b8b  mov     rsi, [rcx+20h]
0x180003b8f  mov     rdi, rcx
0x180003b92  test    rsi, rsi
0x180003b95  jz      short loc_180003BC4
0x180003b97  mov     ebx, [rsi+28h]
0x180003b9a  mov     rcx, [rsi+10h]
0x180003b9e  mov     rax, [rcx]
0x180003ba1  mov     rax, [rax+10h]
0x180003ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003baa  test    ebx, ebx
0x180003bac  jnz     short loc_180003BBC
0x180003bae  mov     rax, [rsi]
0x180003bb1  mov     rcx, rsi
0x180003bb4  mov     rax, [rax]
0x180003bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbc  mov     qword ptr [rdi+20h], 0
0x180003bc4  mov     rcx, [rdi+2B0h]
0x180003bcb  test    rcx, rcx
0x180003bce  jz      short loc_180003BEA
0x180003bd0  mov     rax, [rcx]
0x180003bd3  mov     rax, [rax+100h]
0x180003bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bdf  mov     qword ptr [rdi+2B0h], 0
0x180003bea  lea     rcx, [rdi+2C0h]
0x180003bf1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003bf7  lea     rcx, [rdi+170h]
0x180003bfe  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c04  lea     rcx, [rdi+30h]
0x180003c08  mov     rbx, [rsp+28h+arg_0]
0x180003c0d  mov     rsi, [rsp+28h+arg_8]
0x180003c12  add     rsp, 20h
0x180003c16  pop     rdi
0x180003c17  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
