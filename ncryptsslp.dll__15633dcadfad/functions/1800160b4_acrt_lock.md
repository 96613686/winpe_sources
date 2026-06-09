# __acrt_lock

- ea: `0x1800160b4`
- end: `0x1800160cd`
- name: `__acrt_lock`
- size: `25`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180015154`
- `0x18001519c`
- `0x180015540`
- `0x180015604`
- `0x1800158b0`
- `0x180015934`
- `0x180015fd4`
- `0x1800160f4`
- `0x180016490`
- `0x180016cb4`
- `0x180017770`
- `0x1800179e0`
- `0x180017a20`
- `0x18001b910`
- `0x18001ba80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800160c6`

## pseudocode

```c
void __fastcall _acrt_lock(int a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)&qword_18003DF10[5 * a1]);
}

```

## disassembly

```asm
0x1800160b4  movsxd  rax, ecx
0x1800160b7  lea     rcx, [rax+rax*4]
0x1800160bb  lea     rax, qword_18003DF10
0x1800160c2  lea     rcx, [rax+rcx*8]
0x1800160c6  jmp     cs:__imp_EnterCriticalSection
```
