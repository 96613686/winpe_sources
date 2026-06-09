# CUSTOM_ERROR_HANDLER::~CUSTOM_ERROR_HANDLER(void)

- ea: `0x1800029b8`
- end: `0x180002a0e`
- name: `??1CUSTOM_ERROR_HANDLER@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CUSTOM_ERROR_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002be0`

## callees

- `0x1800029b8`
- `0x180008010`

## pseudocode

```c
void __fastcall CUSTOM_ERROR_HANDLER::~CUSTOM_ERROR_HANDLER(CUSTOM_ERROR_HANDLER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CUSTOM_ERROR_HANDLER::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 256LL))(v3);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800029b8  push    rbx
0x1800029ba  sub     rsp, 20h
0x1800029be  lea     rax, ??_7CUSTOM_ERROR_HANDLER@@6B@; const CUSTOM_ERROR_HANDLER::`vftable'
0x1800029c5  mov     rbx, rcx
0x1800029c8  mov     [rcx], rax
0x1800029cb  mov     rcx, [rcx+8]
0x1800029cf  test    rcx, rcx
0x1800029d2  jz      short loc_1800029E8
0x1800029d4  mov     rax, [rcx]
0x1800029d7  mov     rax, [rax+10h]
0x1800029db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e0  mov     qword ptr [rbx+8], 0
0x1800029e8  mov     rcx, [rbx+10h]
0x1800029ec  test    rcx, rcx
0x1800029ef  jz      short loc_180002A08
0x1800029f1  mov     rax, [rcx]
0x1800029f4  mov     rax, [rax+100h]
0x1800029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a00  mov     qword ptr [rbx+10h], 0
0x180002a08  add     rsp, 20h
0x180002a0c  pop     rbx
0x180002a0d  retn
```
