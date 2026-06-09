# MUTX::~MUTX(void)

- ea: `0x18000c8f4`
- end: `0x18000c910`
- name: `??1MUTX@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(MUTX *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b9ac`
- `0x1800161e0`
- `0x180016728`
- `0x18003c3b4`
- `0x18004e454`
- `0x180051354`
- `0x180082238`

## callees

- `0x18000c8f4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c8fe`
- `KERNEL32!DeleteCriticalSection` at `0x18000c8fe`

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
0x18000c8f4  sub     rsp, 28h
0x18000c8f8  cmp     byte ptr [rcx+29h], 0
0x18000c8fc  jz      short loc_18000C90A
0x18000c8fe  call    cs:__imp_DeleteCriticalSection
0x18000c905  nop     dword ptr [rax+rax+00h]
0x18000c90a  add     rsp, 28h
0x18000c90e  retn
```
