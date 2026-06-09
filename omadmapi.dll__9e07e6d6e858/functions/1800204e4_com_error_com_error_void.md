# _com_error::~_com_error(void)

- ea: `0x1800204e4`
- end: `0x180020529`
- name: `??1_com_error@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800204e4`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020515`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020515`

## pseudocode

```c
void __fastcall _com_error::~_com_error(_com_error *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x1800204e4  push    rbx
0x1800204e6  sub     rsp, 20h
0x1800204ea  mov     rbx, rcx
0x1800204ed  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800204f4  mov     [rcx], rax
0x1800204f7  mov     rcx, [rcx+10h]
0x1800204fb  test    rcx, rcx
0x1800204fe  jz      short loc_18002050C
0x180020500  mov     rax, [rcx]
0x180020503  mov     rax, [rax+10h]
0x180020507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002050c  mov     rcx, [rbx+18h]; hMem
0x180020510  test    rcx, rcx
0x180020513  jz      short loc_180020522
0x180020515  call    cs:__imp_LocalFree
0x18002051c  nop     dword ptr [rax+rax+00h]
0x180020521  nop
0x180020522  add     rsp, 20h
0x180020526  pop     rbx
0x180020527  retn
```
