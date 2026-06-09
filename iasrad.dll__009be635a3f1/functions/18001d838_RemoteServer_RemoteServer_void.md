# RemoteServer::~RemoteServer(void)

- ea: `0x18001d838`
- end: `0x18001d889`
- name: `??1RemoteServer@@MEAA@XZ`
- size: `81`
- prototype: `void __fastcall(RemoteServer *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d76c`
- `0x18001d8d0`
- `0x18002f328`

## import_xrefs

- `msvcrt!free` at `0x18001d85f`
- `msvcrt!free` at `0x18001d869`
- `msvcrt!free` at `0x18001d873`
- `msvcrt!free` at `0x18001d85f`
- `msvcrt!free` at `0x18001d869`
- `msvcrt!free` at `0x18001d873`
- `msvcrt!free` at `0x18001d882`
- `KERNEL32!DeleteCriticalSection` at `0x18001d852`
- `KERNEL32!DeleteCriticalSection` at `0x18001d852`

## pseudocode

```c
void __fastcall RemoteServer::~RemoteServer(RemoteServer *this)
{
  *(_QWORD *)this = &RemoteServer::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  free(*((void **)this + 25));
  free(*((void **)this + 6));
  free(*((void **)this + 5));
  free(*((void **)this + 4));
}

```

## disassembly

```asm
0x18001d838  push    rbx
0x18001d83a  sub     rsp, 20h
0x18001d83e  lea     rax, ??_7RemoteServer@@6B@; const RemoteServer::`vftable'
0x18001d845  mov     rbx, rcx
0x18001d848  mov     [rcx], rax
0x18001d84b  add     rcx, 180h; lpCriticalSection
0x18001d852  call    cs:__imp_DeleteCriticalSection
0x18001d858  mov     rcx, [rbx+0C8h]; Block
0x18001d85f  call    cs:__imp_free
0x18001d865  mov     rcx, [rbx+30h]; Block
0x18001d869  call    cs:__imp_free
0x18001d86f  mov     rcx, [rbx+28h]; Block
0x18001d873  call    cs:__imp_free
0x18001d879  mov     rcx, [rbx+20h]
0x18001d87d  add     rsp, 20h
0x18001d881  pop     rbx
0x18001d882  jmp     cs:__imp_free
```
