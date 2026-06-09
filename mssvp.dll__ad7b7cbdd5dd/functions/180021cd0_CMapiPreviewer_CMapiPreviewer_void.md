# CMapiPreviewer::CMapiPreviewer(void)

- ea: `0x180021cd0`
- end: `0x180021e40`
- name: `??0CMapiPreviewer@@QEAA@XZ`
- size: `368`
- prototype: `CMapiPreviewer *__fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009a34`
- `0x18000d0a4`

## callees

- `0x180007134`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021dff`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021e0c`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021e19`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021dff`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021e0c`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021e19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CMapiPreviewer *__fastcall CMapiPreviewer::CMapiPreviewer(CMapiPreviewer *this)
{
  *((_DWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 0;
  *(_QWORD *)this = &CMapiPreviewer::`vftable'{for `IInitializeWithItem'};
  *((_QWORD *)this + 1) = &CMapiPreviewer::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 2) = &CMapiPreviewer::`vftable'{for `IPreviewHandler'};
  *((_QWORD *)this + 3) = &CMapiPreviewer::`vftable'{for `IOleWindow'};
  *((_QWORD *)this + 4) = &CMapiPreviewer::`vftable'{for `IRichEditOleCallback'};
  *((_QWORD *)this + 5) = &CMapiPreviewer::`vftable'{for `IHlinkFrame'};
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 52) = 1;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 11;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 68) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  `eh vector constructor iterator'(
    (char *)this + 296,
    0x38u,
    0x10u,
    (void (*)(void *))CMapiPreviewer::HeaderLineData::HeaderLineData,
    (void (*)(void *))CMapiPreviewer::HeaderLineData::~HeaderLineData);
  *((_DWORD *)this + 298) = 0;
  *((_QWORD *)this + 150) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_QWORD *)this + 155) = 0;
  SetRectEmpty((LPRECT)this + 8);
  SetRectEmpty((LPRECT)this + 9);
  SetRectEmpty((LPRECT)this + 12);
  *((_OWORD *)this + 15) = 0;
  *((_QWORD *)this + 152) = 0;
  return this;
}

```

## disassembly

```asm
0x180021cd0  mov     [rsp+arg_8], rbx
0x180021cd5  mov     [rsp+arg_0], rcx
0x180021cda  push    rdi
0x180021cdb  sub     rsp, 30h
0x180021cdf  mov     rbx, rcx
0x180021ce2  xor     edi, edi
0x180021ce4  mov     [rcx+30h], edi
0x180021ce7  xorps   xmm0, xmm0
0x180021cea  xor     eax, eax
0x180021cec  movups  xmmword ptr [rcx+38h], xmm0
0x180021cf0  movups  xmmword ptr [rcx+48h], xmm0
0x180021cf4  mov     [rcx+58h], rax
0x180021cf8  mov     [rcx+60h], dil
0x180021cfc  lea     rax, ??_7CMapiPreviewer@@6BIInitializeWithItem@@@; const CMapiPreviewer::`vftable'{for `IInitializeWithItem'}
0x180021d03  mov     [rcx], rax
0x180021d06  lea     rax, ??_7CMapiPreviewer@@6BIObjectWithSite@@@; const CMapiPreviewer::`vftable'{for `IObjectWithSite'}
0x180021d0d  mov     [rcx+8], rax
0x180021d11  lea     rax, ??_7CMapiPreviewer@@6BIPreviewHandler@@@; const CMapiPreviewer::`vftable'{for `IPreviewHandler'}
0x180021d18  mov     [rcx+10h], rax
0x180021d1c  lea     rax, ??_7CMapiPreviewer@@6BIOleWindow@@@; const CMapiPreviewer::`vftable'{for `IOleWindow'}
0x180021d23  mov     [rcx+18h], rax
0x180021d27  lea     rax, ??_7CMapiPreviewer@@6BIRichEditOleCallback@@@; const CMapiPreviewer::`vftable'{for `IRichEditOleCallback'}
0x180021d2e  mov     [rcx+20h], rax
0x180021d32  lea     rax, ??_7CMapiPreviewer@@6BIHlinkFrame@@@; const CMapiPreviewer::`vftable'{for `IHlinkFrame'}
0x180021d39  mov     [rcx+28h], rax
0x180021d3d  mov     [rcx+68h], rdi
0x180021d41  mov     [rcx+70h], rdi
0x180021d45  mov     [rcx+78h], rdi
0x180021d49  mov     [rcx+0A0h], rdi
0x180021d50  mov     [rcx+0A8h], rdi
0x180021d57  mov     [rcx+0B0h], rdi
0x180021d5e  mov     [rcx+0B8h], rdi
0x180021d65  mov     dword ptr [rcx+0D0h], 1
0x180021d6f  mov     [rcx+0D8h], rdi
0x180021d76  mov     dword ptr [rcx+0E0h], 0Bh
0x180021d80  mov     [rcx+0E8h], rdi
0x180021d87  mov     [rcx+100h], rdi
0x180021d8e  mov     [rcx+108h], rdi
0x180021d95  mov     [rcx+110h], edi
0x180021d9b  mov     [rcx+118h], rdi
0x180021da2  mov     [rcx+120h], rdi
0x180021da9  add     rcx, 128h; void *
0x180021db0  lea     rax, ??1HeaderLineData@CMapiPreviewer@@QEAA@XZ; CMapiPreviewer::HeaderLineData::~HeaderLineData(void)
0x180021db7  mov     [rsp+38h+var_18], rax; void (*)(void *)
0x180021dbc  lea     r9, ??0HeaderLineData@CMapiPreviewer@@QEAA@XZ; void (*)(void *)
0x180021dc3  lea     edx, [rdi+38h]; unsigned __int64
0x180021dc6  lea     r8d, [rdi+10h]; unsigned __int64
0x180021dca  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180021dcf  mov     [rbx+4A8h], edi
0x180021dd5  mov     [rbx+4B0h], rdi
0x180021ddc  mov     [rbx+4B8h], rdi
0x180021de3  mov     [rbx+4C8h], rdi
0x180021dea  mov     [rbx+4D0h], rdi
0x180021df1  mov     [rbx+4D8h], rdi
0x180021df8  lea     rcx, [rbx+80h]; lprc
0x180021dff  call    cs:__imp_SetRectEmpty
0x180021e05  lea     rcx, [rbx+90h]; lprc
0x180021e0c  call    cs:__imp_SetRectEmpty
0x180021e12  lea     rcx, [rbx+0C0h]; lprc
0x180021e19  call    cs:__imp_SetRectEmpty
0x180021e1f  xorps   xmm0, xmm0
0x180021e22  movups  xmmword ptr [rbx+0F0h], xmm0
0x180021e29  xor     eax, eax
0x180021e2b  mov     [rbx+4C0h], rax
0x180021e32  mov     rax, rbx
0x180021e35  mov     rbx, [rsp+38h+arg_8]
0x180021e3a  add     rsp, 30h
0x180021e3e  pop     rdi
0x180021e3f  retn
```
