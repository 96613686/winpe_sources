# CHECK_ACCESS_HANDLER::CleanupStoredContext(void)

- ea: `0x180001ad0`
- end: `0x180001b0c`
- name: `?CleanupStoredContext@CHECK_ACCESS_HANDLER@@UEAAXXZ`
- size: `60`
- prototype: `void __fastcall(CHECK_ACCESS_HANDLER *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001ad0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180001af6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001af6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b00`

## pseudocode

```c
void __fastcall CHECK_ACCESS_HANDLER::CleanupStoredContext(CHECK_ACCESS_HANDLER *this)
{
  if ( this )
  {
    *((_QWORD *)this + 2) = 0;
    *(_QWORD *)this = &CHECK_ACCESS_HANDLER::`vftable';
    STRA::~STRA((CHECK_ACCESS_HANDLER *)((char *)this + 248));
    STRU::~STRU((CHECK_ACCESS_HANDLER *)((char *)this + 64));
  }
}

```

## disassembly

```asm
0x180001ad0  test    rcx, rcx
0x180001ad3  jz      short locret_180001B0B
0x180001ad5  push    rbx
0x180001ad6  sub     rsp, 20h
0x180001ada  lea     rax, ??_7CHECK_ACCESS_HANDLER@@6B@; const CHECK_ACCESS_HANDLER::`vftable'
0x180001ae1  mov     qword ptr [rcx+10h], 0
0x180001ae9  mov     [rcx], rax
0x180001aec  mov     rbx, rcx
0x180001aef  add     rcx, 0F8h
0x180001af6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001afc  lea     rcx, [rbx+40h]
0x180001b00  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001b06  add     rsp, 20h
0x180001b0a  pop     rbx
0x180001b0b  retn
```
