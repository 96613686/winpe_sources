# MUTX::~MUTX(void)

- ea: `0x18000f65c`
- end: `0x18000f671`
- name: `??1MUTX@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(MUTX *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e788`
- `0x1800191dc`
- `0x18001970c`
- `0x1800348e0`
- `0x18004d570`
- `0x1800502e8`
- `0x180080690`

## callees

- `0x18000f65c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000f666`
- `KERNEL32!DeleteCriticalSection` at `0x18000f666`

## pseudocode

```c
void __fastcall MUTX::~MUTX(struct _RTL_CRITICAL_SECTION *this)
{
  if ( BYTE1(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000f65c  sub     rsp, 28h
0x18000f660  cmp     byte ptr [rcx+29h], 0
0x18000f664  jz      short loc_18000F66C
0x18000f666  call    cs:__imp_DeleteCriticalSection
0x18000f66c  add     rsp, 28h
0x18000f670  retn
```
