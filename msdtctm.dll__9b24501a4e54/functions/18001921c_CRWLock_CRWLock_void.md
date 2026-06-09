# CRWLock::~CRWLock(void)

- ea: `0x18001921c`
- end: `0x180019283`
- name: `??1CRWLock@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CRWLock *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b899d`
- `0x1800bad10`

## callees

- `0x18001921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019276`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001923c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001924f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001923c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001924f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRWLock::~CRWLock(CRWLock *this)
{
  *(_QWORD *)this = &CRWLock::`vftable';
  if ( *((_QWORD *)this + 8) )
    CloseHandle(*((HANDLE *)this + 8));
  if ( *((_QWORD *)this + 9) )
    CloseHandle(*((HANDLE *)this + 9));
  *((_QWORD *)this + 16) = &UTStaticList2<CXaOpenState *>::`vftable';
  *((_QWORD *)this + 12) = &UTStaticList2<CXaOpenState *>::`vftable';
  *((_QWORD *)this + 1) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18001921c  push    rbx
0x18001921e  sub     rsp, 20h
0x180019222  mov     rbx, rcx
0x180019225  lea     rax, ??_7CRWLock@@6B@; const CRWLock::`vftable'
0x18001922c  mov     [rcx], rax
0x18001922f  mov     rax, [rcx+40h]
0x180019233  test    rax, rax
0x180019236  jz      short loc_180019242
0x180019238  mov     rcx, [rcx+40h]; hObject
0x18001923c  call    cs:__imp_CloseHandle
0x180019242  mov     rax, [rbx+48h]
0x180019246  test    rax, rax
0x180019249  jz      short loc_180019255
0x18001924b  mov     rcx, [rbx+48h]; hObject
0x18001924f  call    cs:__imp_CloseHandle
0x180019255  lea     rax, ??_7?$UTStaticList2@PEAVCXaOpenState@@@@6B@; const UTStaticList2<CXaOpenState *>::`vftable'
0x18001925c  mov     [rbx+80h], rax
0x180019263  mov     [rbx+60h], rax
0x180019267  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18001926e  mov     [rbx+8], rax
0x180019272  lea     rcx, [rbx+10h]; lpCriticalSection
0x180019276  call    cs:__imp_DeleteCriticalSection
0x18001927c  nop
0x18001927d  add     rsp, 20h
0x180019281  pop     rbx
0x180019282  retn
```
