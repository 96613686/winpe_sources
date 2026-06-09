# CW32System::~CW32System(void)

- ea: `0x180046008`
- end: `0x180046057`
- name: `??1CW32System@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026f28`

## callees

- `0x18002720c`
- `0x180046008`
- `0x180046060`
- `0x180046124`

## import_xrefs

- `KERNEL32!TlsFree` at `0x18004601c`
- `KERNEL32!TlsFree` at `0x18004601c`
- `GDI32!DeleteDC` at `0x180046045`
- `GDI32!DeleteDC` at `0x180046045`

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
0x180046008  sub     rsp, 28h
0x18004600c  call    ?FreeIME@CW32System@@SAXXZ; CW32System::FreeIME(void)
0x180046011  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x180046017  cmp     ecx, 0FFFFFFFFh
0x18004601a  jz      short loc_180046028
0x18004601c  call    cs:__imp_TlsFree
0x180046023  nop     dword ptr [rax+rax+00h]
0x180046028  mov     rcx, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; lpMem
0x18004602f  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180046034  call    ?FreeOle@CW32System@@SAXXZ; CW32System::FreeOle(void)
0x180046039  mov     rcx, cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA; hdc
0x180046040  test    rcx, rcx
0x180046043  jz      short loc_180046051
0x180046045  call    cs:__imp_DeleteDC
0x18004604c  nop     dword ptr [rax+rax+00h]
0x180046051  add     rsp, 28h
0x180046055  retn
```
