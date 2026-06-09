# CMFMediaBuffer::~CMFMediaBuffer(void)

- ea: `0x1800655d0`
- end: `0x180065604`
- name: `??1CMFMediaBuffer@@MEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CMFMediaBuffer *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180060174`
- `0x18006560c`
- `0x180065690`
- `0x18006fb37`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFMediaBuffer::~CMFMediaBuffer(CMFMediaBuffer *this)
{
  *(_QWORD *)this = &CMFMediaBuffer::`vftable'{for `IMFMediaBuffer'};
  *((_QWORD *)this + 1) = &CMFMediaBuffer::`vftable'{for `IMFMediaBufferInternal'};
  *((_QWORD *)this + 2) = &CMFMediaBuffer::`vftable'{for `CMFMultiBuffer'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x1800655d0  sub     rsp, 28h
0x1800655d4  lea     rax, ??_7CMFMediaBuffer@@6BIMFMediaBuffer@@@; const CMFMediaBuffer::`vftable'{for `IMFMediaBuffer'}
0x1800655db  mov     [rcx], rax
0x1800655de  lea     rax, ??_7CMFMediaBuffer@@6BIMFMediaBufferInternal@@@; const CMFMediaBuffer::`vftable'{for `IMFMediaBufferInternal'}
0x1800655e5  mov     [rcx+8], rax
0x1800655e9  lea     rax, ??_7CMFMediaBuffer@@6BCMFMultiBuffer@@@; const CMFMediaBuffer::`vftable'{for `CMFMultiBuffer'}
0x1800655f0  mov     [rcx+10h], rax
0x1800655f4  add     rcx, 38h ; '8'; lpCriticalSection
0x1800655f8  call    cs:__imp_DeleteCriticalSection
0x1800655fe  nop
0x1800655ff  add     rsp, 28h
0x180065603  retn
```
