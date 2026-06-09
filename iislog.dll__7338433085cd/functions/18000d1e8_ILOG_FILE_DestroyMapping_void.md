# ILOG_FILE::DestroyMapping(void)

- ea: `0x18000d1e8`
- end: `0x18000d225`
- name: `?DestroyMapping@ILOG_FILE@@AEAAXXZ`
- size: `61`
- prototype: `void __fastcall(ILOG_FILE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d0e0`
- `0x18000d13c`
- `0x18000d598`

## callees

- `0x18000d1e8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000d211`
- `KERNEL32!CloseHandle` at `0x18000d211`
- `KERNEL32!UnmapViewOfFile` at `0x18000d1fa`
- `KERNEL32!UnmapViewOfFile` at `0x18000d1fa`

## pseudocode

```c
void __fastcall ILOG_FILE::DestroyMapping(ILOG_FILE *this)
{
  const void *v2; // rcx
  void *v3; // rcx

  v2 = (const void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    UnmapViewOfFile(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000d1e8  push    rbx
0x18000d1ea  sub     rsp, 20h
0x18000d1ee  mov     rbx, rcx
0x18000d1f1  mov     rcx, [rcx+18h]; lpBaseAddress
0x18000d1f5  test    rcx, rcx
0x18000d1f8  jz      short loc_18000D208
0x18000d1fa  call    cs:__imp_UnmapViewOfFile
0x18000d200  mov     qword ptr [rbx+18h], 0
0x18000d208  mov     rcx, [rbx+8]; hObject
0x18000d20c  test    rcx, rcx
0x18000d20f  jz      short loc_18000D21F
0x18000d211  call    cs:__imp_CloseHandle
0x18000d217  mov     qword ptr [rbx+8], 0
0x18000d21f  add     rsp, 20h
0x18000d223  pop     rbx
0x18000d224  retn
```
