# ServerBinding::~ServerBinding(void)

- ea: `0x18002113c`
- end: `0x180021181`
- name: `??1ServerBinding@@EEAA@XZ`
- size: `69`
- prototype: `void __fastcall(ServerBinding *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800213b0`

## callees

- `0x18001d9f8`
- `0x18002113c`

## import_xrefs

- `msvcrt!free` at `0x18002116b`
- `msvcrt!free` at `0x18002116b`
- `KERNEL32!DeleteCriticalSection` at `0x180021153`
- `KERNEL32!DeleteCriticalSection` at `0x180021153`

## pseudocode

```c
void __fastcall ServerBinding::~ServerBinding(ServerBinding *this)
{
  RemoteServer *v2; // rcx

  *(_QWORD *)this = &ServerBinding::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = (RemoteServer *)*((_QWORD *)this + 8);
  if ( v2 )
    RemoteServer::Release(v2);
  free(*((void **)this + 6));
  *(_QWORD *)this = &HashTableEntry::`vftable';
}

```

## disassembly

```asm
0x18002113c  push    rbx
0x18002113e  sub     rsp, 20h
0x180021142  lea     rax, ??_7ServerBinding@@6B@; const ServerBinding::`vftable'
0x180021149  mov     rbx, rcx
0x18002114c  mov     [rcx], rax
0x18002114f  add     rcx, 48h ; 'H'; lpCriticalSection
0x180021153  call    cs:__imp_DeleteCriticalSection
0x180021159  mov     rcx, [rbx+40h]; this
0x18002115d  test    rcx, rcx
0x180021160  jz      short loc_180021167
0x180021162  call    ?Release@RemoteServer@@QEAAXXZ; RemoteServer::Release(void)
0x180021167  mov     rcx, [rbx+30h]; Block
0x18002116b  call    cs:__imp_free
0x180021171  lea     rax, ??_7HashTableEntry@@6B@; const HashTableEntry::`vftable'
0x180021178  mov     [rbx], rax
0x18002117b  add     rsp, 20h
0x18002117f  pop     rbx
0x180021180  retn
```
