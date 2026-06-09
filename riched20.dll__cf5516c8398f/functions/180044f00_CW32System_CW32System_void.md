# CW32System::~CW32System(void)

- ea: `0x180044f00`
- end: `0x180044f42`
- name: `??1CW32System@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022d48`

## callees

- `0x180023010`
- `0x180044f00`
- `0x180044f48`
- `0x180044ff4`

## import_xrefs

- `KERNEL32!TlsFree` at `0x180044f14`
- `KERNEL32!TlsFree` at `0x180044f14`
- `GDI32!DeleteDC` at `0x180044f37`
- `GDI32!DeleteDC` at `0x180044f37`

## pseudocode

```c
void __fastcall CW32System::~CW32System(CW32System *this)
{
  CW32System::FreeIME();
  if ( CThreadData::_dwTlsIndex != -1 )
    TlsFree(CThreadData::_dwTlsIndex);
  CW32System::FreePv(CW32System::_pNotCountingSingleton);
  CW32System::FreeOle();
  if ( CW32System::_hdcScreen )
    DeleteDC(CW32System::_hdcScreen);
}

```

## disassembly

```asm
0x180044f00  sub     rsp, 28h
0x180044f04  call    ?FreeIME@CW32System@@SAXXZ; CW32System::FreeIME(void)
0x180044f09  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x180044f0f  cmp     ecx, 0FFFFFFFFh
0x180044f12  jz      short loc_180044F1A
0x180044f14  call    cs:__imp_TlsFree
0x180044f1a  mov     rcx, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; lpMem
0x180044f21  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180044f26  call    ?FreeOle@CW32System@@SAXXZ; CW32System::FreeOle(void)
0x180044f2b  mov     rcx, cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA; hdc
0x180044f32  test    rcx, rcx
0x180044f35  jz      short loc_180044F3D
0x180044f37  call    cs:__imp_DeleteDC
0x180044f3d  add     rsp, 28h
0x180044f41  retn
```
