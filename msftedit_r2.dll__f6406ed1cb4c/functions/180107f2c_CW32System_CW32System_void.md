# CW32System::~CW32System(void)

- ea: `0x180107f2c`
- end: `0x180108009`
- name: `??1CW32System@@QEAA@XZ`
- size: `221`
- prototype: `void __fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180107f00`

## callees

- `0x1800d97c0`
- `0x180107f2c`
- `0x180108010`
- `0x18013d250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180107f49`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180107f49`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180107f77`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180107fd7`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180107f77`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180107fd7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107ff0`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107ff0`

## pseudocode

```c
void __fastcall CW32System::~CW32System(CW32System *this)
{
  CArrayBase *v1; // rbx

  v1 = CW32System::_arTmpDisplayAttrib;
  if ( CW32System::_arTmpDisplayAttrib )
  {
    CArrayBase::Clear(CW32System::_arTmpDisplayAttrib, 2);
    operator delete(v1, 0x20u);
    CW32System::_arTmpDisplayAttrib = 0;
  }
  if ( CThreadData::_dwTlsIndex != -1 )
    TlsFree(CThreadData::_dwTlsIndex);
  operator delete(CW32System::_pNotCountingSingleton, 8u);
  CW32System::FreeOle();
  if ( CW32System::_hdcScreenIC )
  {
    DeleteDC(CW32System::_hdcScreenIC);
    CW32System::_hdcScreenIC = 0;
  }
  if ( CW32System::_hdcScreenDC )
  {
    DeleteDC((HDC)CW32System::_hdcScreenDC);
    CW32System::_hdcScreenDC = 0;
  }
  if ( CW32System::_hDefaultFont )
  {
    DeleteObject(CW32System::_hDefaultFont);
    CW32System::_hDefaultFont = 0;
  }
}

```

## disassembly

```asm
0x180107f2c  push    rbx
0x180107f2e  sub     rsp, 20h
0x180107f32  mov     rbx, cs:?_arTmpDisplayAttrib@CW32System@@2PEAVCTmpDisplayAttrArray@@EA; CTmpDisplayAttrArray * CW32System::_arTmpDisplayAttrib
0x180107f39  test    rbx, rbx
0x180107f3c  jnz     short loc_180107FAD
0x180107f3e  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x180107f44  cmp     ecx, 0FFFFFFFFh
0x180107f47  jz      short loc_180107F55
0x180107f49  call    cs:__imp_TlsFree
0x180107f50  nop     dword ptr [rax+rax+00h]
0x180107f55  mov     rcx, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; void *
0x180107f5c  mov     edx, 8; unsigned __int64
0x180107f61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180107f66  call    ?FreeOle@CW32System@@SAXXZ; CW32System::FreeOle(void)
0x180107f6b  mov     rcx, cs:?_hdcScreenIC@CW32System@@0PEAUHDC__@@EA; hdc
0x180107f72  test    rcx, rcx
0x180107f75  jz      short loc_180107F8E
0x180107f77  call    cs:__imp_DeleteDC
0x180107f7e  nop     dword ptr [rax+rax+00h]
0x180107f83  mov     cs:?_hdcScreenIC@CW32System@@0PEAUHDC__@@EA, 0; HDC__ * CW32System::_hdcScreenIC
0x180107f8e  mov     rcx, cs:?_hdcScreenDC@CW32System@@0PEAUHDC__@@EA; hdc
0x180107f95  test    rcx, rcx
0x180107f98  jnz     short loc_180107FD7
0x180107f9a  mov     rcx, cs:?_hDefaultFont@CW32System@@0PEAUHFONT__@@EA; ho
0x180107fa1  test    rcx, rcx
0x180107fa4  jnz     short loc_180107FF0
0x180107fa6  add     rsp, 20h
0x180107faa  pop     rbx
0x180107fab  retn
0x180107fad  mov     edx, 2
0x180107fb2  mov     rcx, rbx
0x180107fb5  call    ?Clear@CArrayBase@@QEAAXW4tagArrayFlag@@@Z; CArrayBase::Clear(tagArrayFlag)
0x180107fba  mov     edx, 20h ; ' '; unsigned __int64
0x180107fbf  mov     rcx, rbx; void *
0x180107fc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180107fc7  mov     cs:?_arTmpDisplayAttrib@CW32System@@2PEAVCTmpDisplayAttrArray@@EA, 0; CTmpDisplayAttrArray * CW32System::_arTmpDisplayAttrib
0x180107fd2  jmp     loc_180107F3E
0x180107fd7  call    cs:__imp_DeleteDC
0x180107fde  nop     dword ptr [rax+rax+00h]
0x180107fe3  mov     cs:?_hdcScreenDC@CW32System@@0PEAUHDC__@@EA, 0; HDC__ * CW32System::_hdcScreenDC
0x180107fee  jmp     short loc_180107F9A
0x180107ff0  call    cs:__imp_DeleteObject
0x180107ff7  nop     dword ptr [rax+rax+00h]
0x180107ffc  mov     cs:?_hDefaultFont@CW32System@@0PEAUHFONT__@@EA, 0; HFONT__ * CW32System::_hDefaultFont
0x180108007  jmp     short loc_180107FA6
```
