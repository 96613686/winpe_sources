# SH<void *,SH_HANDLE>::Reset(void)

- ea: `0x18002969c`
- end: `0x1800296c0`
- name: `?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(CNgscbToken *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180018a58`
- `0x180028380`
- `0x18002b75c`
- `0x18002b768`

## callees

- `0x18002969c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800296ad`
- `KERNEL32!CloseHandle` at `0x1800296ad`

## pseudocode

```c
BOOL __fastcall SH<void *,SH_HANDLE>::Reset(void **a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = CloseHandle(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002969c  push    rbx
0x18002969e  sub     rsp, 20h
0x1800296a2  mov     rbx, rcx
0x1800296a5  mov     rcx, [rcx]; hObject
0x1800296a8  test    rcx, rcx
0x1800296ab  jz      short loc_1800296BA
0x1800296ad  call    cs:__imp_CloseHandle
0x1800296b3  mov     qword ptr [rbx], 0
0x1800296ba  add     rsp, 20h
0x1800296be  pop     rbx
0x1800296bf  retn
```
