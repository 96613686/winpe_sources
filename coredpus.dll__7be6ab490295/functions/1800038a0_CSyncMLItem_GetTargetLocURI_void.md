# CSyncMLItem::GetTargetLocURI(void)

- ea: `0x1800038a0`
- end: `0x1800038d3`
- name: `?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ`
- size: `51`
- prototype: `struct IConfigManager2URI *__fastcall(CSyncMLItem *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e490`
- `0x18001ef60`
- `0x18001f290`
- `0x18001f5a0`
- `0x18001f7a0`
- `0x18001fee0`

## callees

- `0x1800038a0`
- `0x180030010`

## pseudocode

```c
struct IConfigManager2URI *__fastcall CSyncMLItem::GetTargetLocURI(CSyncMLItem *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 9);
  if ( !v2 )
    return 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  return (struct IConfigManager2URI *)*((_QWORD *)this + 9);
}

```

## disassembly

```asm
0x1800038a0  push    rbx
0x1800038a2  sub     rsp, 20h
0x1800038a6  mov     rbx, rcx
0x1800038a9  mov     rcx, [rcx+48h]
0x1800038ad  test    rcx, rcx
0x1800038b0  jz      short loc_1800038C9
0x1800038b2  mov     rax, [rcx]
0x1800038b5  mov     rax, [rax+8]
0x1800038b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038be  mov     rax, [rbx+48h]
0x1800038c2  add     rsp, 20h
0x1800038c6  pop     rbx
0x1800038c7  retn
0x1800038c9  mov     rax, rcx
0x1800038cc  add     rsp, 20h
0x1800038d0  pop     rbx
0x1800038d1  retn
```
