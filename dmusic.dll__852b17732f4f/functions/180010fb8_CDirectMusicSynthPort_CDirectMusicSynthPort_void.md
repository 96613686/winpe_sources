# CDirectMusicSynthPort::~CDirectMusicSynthPort(void)

- ea: `0x180010fb8`
- end: `0x180011018`
- name: `??1CDirectMusicSynthPort@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CDirectMusicSynthPort *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011020`
- `0x1800162e8`
- `0x180016cd8`
- `0x180021b25`

## callees

- `0x18000f340`
- `0x180011170`

## pseudocode

```c
void __fastcall CDirectMusicSynthPort::~CDirectMusicSynthPort(CDirectMusicSynthPort *this)
{
  CDirectMusicSynthPort *v2; // rcx

  *(_QWORD *)this = &CDirectMusicSynthPort::`vftable'{for `CDirectMusicPortDownload'};
  *((_QWORD *)this + 47) = &CDirectMusicSynthPort::`vftable'{for `IDirectMusicPort'};
  *((_QWORD *)this + 48) = &CDirectMusicSynthPort7::`vftable'{for `IDirectMusicPortP'};
  v2 = (CDirectMusicSynthPort *)((char *)this + 392);
  *(_QWORD *)v2 = &CDirectMusicSynthPort::`vftable'{for `IDirectMusicPortPrivate'};
  *((_QWORD *)this + 50) = &CDirectMusicSynthPort8::`vftable'{for `IKsControl'};
  CDirectMusicSynthPort::Close(v2);
  CDirectMusicPortDownload::~CDirectMusicPortDownload(this);
}

```

## disassembly

```asm
0x180010fb8  push    rbx
0x180010fba  sub     rsp, 20h
0x180010fbe  mov     rbx, rcx
0x180010fc1  lea     rax, ??_7CDirectMusicSynthPort@@6BCDirectMusicPortDownload@@@; const CDirectMusicSynthPort::`vftable'{for `CDirectMusicPortDownload'}
0x180010fc8  mov     [rcx], rax
0x180010fcb  lea     rax, ??_7CDirectMusicSynthPort@@6BIDirectMusicPort@@@; const CDirectMusicSynthPort::`vftable'{for `IDirectMusicPort'}
0x180010fd2  mov     [rcx+178h], rax
0x180010fd9  lea     rax, ??_7CDirectMusicSynthPort7@@6BIDirectMusicPortP@@@; const CDirectMusicSynthPort7::`vftable'{for `IDirectMusicPortP'}
0x180010fe0  mov     [rcx+180h], rax
0x180010fe7  add     rcx, 188h; this
0x180010fee  lea     rax, ??_7CDirectMusicSynthPort@@6BIDirectMusicPortPrivate@@@; const CDirectMusicSynthPort::`vftable'{for `IDirectMusicPortPrivate'}
0x180010ff5  mov     [rcx], rax
0x180010ff8  lea     rax, ??_7CDirectMusicSynthPort8@@6BIKsControl@@@; const CDirectMusicSynthPort8::`vftable'{for `IKsControl'}
0x180010fff  mov     [rbx+190h], rax
0x180011006  call    ?Close@CDirectMusicSynthPort@@UEAAJXZ; CDirectMusicSynthPort::Close(void)
0x18001100b  mov     rcx, rbx; this
0x18001100e  add     rsp, 20h
0x180011012  pop     rbx
0x180011013  jmp     ??1CDirectMusicPortDownload@@UEAA@XZ; CDirectMusicPortDownload::~CDirectMusicPortDownload(void)
```
