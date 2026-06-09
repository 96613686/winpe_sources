# CDirectMusicEmulatePort::~CDirectMusicEmulatePort(void)

- ea: `0x18001abc8`
- end: `0x18001ac08`
- name: `??1CDirectMusicEmulatePort@@UEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CDirectMusicEmulatePort *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ac70`
- `0x18001bb44`
- `0x18001c458`
- `0x180021bc1`
- `0x180021bf6`

## callees

- `0x18001ada0`

## pseudocode

```c
void __fastcall CDirectMusicEmulatePort::~CDirectMusicEmulatePort(CDirectMusicEmulatePort *this)
{
  CDirectMusicEmulatePort *v2; // rcx

  *(_QWORD *)this = &CDirectMusicEmulatePort::`vftable'{for `IDirectMusicPort'};
  *((_QWORD *)this + 1) = &CDirectMusicEmulatePort::`vftable'{for `IDirectMusicThru'};
  v2 = (CDirectMusicEmulatePort *)((char *)this + 16);
  *(_QWORD *)v2 = &CDirectMusicEmulatePort::`vftable'{for `IDirectMusicPortPrivate'};
  *((_QWORD *)this + 3) = &CDirectMusicEmulateInPort::`vftable'{for `IKsControl'};
  CDirectMusicEmulatePort::Close(v2);
}

```

## disassembly

```asm
0x18001abc8  sub     rsp, 28h
0x18001abcc  mov     rax, rcx
0x18001abcf  lea     rcx, ??_7CDirectMusicEmulatePort@@6BIDirectMusicPort@@@; const CDirectMusicEmulatePort::`vftable'{for `IDirectMusicPort'}
0x18001abd6  mov     [rax], rcx
0x18001abd9  lea     rcx, ??_7CDirectMusicEmulatePort@@6BIDirectMusicThru@@@; const CDirectMusicEmulatePort::`vftable'{for `IDirectMusicThru'}
0x18001abe0  mov     [rax+8], rcx
0x18001abe4  lea     rcx, [rax+10h]; this
0x18001abe8  lea     rdx, ??_7CDirectMusicEmulatePort@@6BIDirectMusicPortPrivate@@@; const CDirectMusicEmulatePort::`vftable'{for `IDirectMusicPortPrivate'}
0x18001abef  mov     [rcx], rdx
0x18001abf2  lea     rdx, ??_7CDirectMusicEmulateInPort@@6BIKsControl@@@; const CDirectMusicEmulateInPort::`vftable'{for `IKsControl'}
0x18001abf9  mov     [rax+18h], rdx
0x18001abfd  call    ?Close@CDirectMusicEmulatePort@@UEAAJXZ; CDirectMusicEmulatePort::Close(void)
0x18001ac02  nop
0x18001ac03  add     rsp, 28h
0x18001ac07  retn
```
