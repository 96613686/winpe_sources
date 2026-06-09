# CMVCellularV2::~CMVCellularV2(void)

- ea: `0x180008fb4`
- end: `0x180008fde`
- name: `??1CMVCellularV2@@MEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CMVCellularV2 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008fcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008fcb`

## pseudocode

```c
void __fastcall CMVCellularV2::~CMVCellularV2(CMVCellularV2 *this)
{
  *(_QWORD *)this = &CMVCellularV2::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180008fb4  push    rbx
0x180008fb6  sub     rsp, 20h
0x180008fba  lea     rax, ??_7CMVCellularV2@@6B@; const CMVCellularV2::`vftable'
0x180008fc1  mov     rbx, rcx
0x180008fc4  mov     [rcx], rax
0x180008fc7  add     rcx, 10h; lpCriticalSection
0x180008fcb  call    cs:__imp_DeleteCriticalSection
0x180008fd1  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180008fd8  add     rsp, 20h
0x180008fdc  pop     rbx
0x180008fdd  retn
```
