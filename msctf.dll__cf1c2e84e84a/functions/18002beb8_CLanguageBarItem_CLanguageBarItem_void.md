# CLanguageBarItem::~CLanguageBarItem(void)

- ea: `0x18002beb8`
- end: `0x18002bf4f`
- name: `??1CLanguageBarItem@@UEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CLanguageBarItem *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002be58`
- `0x18002be80`
- `0x1800afac4`

## callees

- `0x18002beb8`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002beca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002beca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf2b`
- `USER32!DestroyIcon` at `0x18002bee8`
- `USER32!DestroyIcon` at `0x18002bee8`
- `GDI32!DeleteObject` at `0x18002bf3f`
- `GDI32!DeleteObject` at `0x18002bf47`
- `GDI32!DeleteObject` at `0x18002bf3f`
- `GDI32!DeleteObject` at `0x18002bf47`

## pseudocode

```c
void __fastcall CLanguageBarItem::~CLanguageBarItem(CLanguageBarItem *this)
{
  void *v2; // rcx
  void *v3; // rcx
  HICON v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx

  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
    LocalFree(v2);
  v3 = (void *)*((_QWORD *)this + 13);
  if ( v3 )
    LocalFree(v3);
  v4 = (HICON)*((_QWORD *)this + 14);
  if ( v4 )
    DestroyIcon(v4);
  v5 = (void *)*((_QWORD *)this + 16);
  if ( v5 )
    DeleteObject(v5);
  v6 = (void *)*((_QWORD *)this + 17);
  if ( v6 )
    DeleteObject(v6);
  v7 = *((_QWORD *)this + 19);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *((_DWORD *)this + 20) &= ~1u;
  v8 = (void *)*((_QWORD *)this + 11);
  if ( v8 )
  {
    LocalFree(v8);
    *((_QWORD *)this + 11) = 0;
  }
}

```

## disassembly

```asm
0x18002beb8  push    rbx
0x18002beba  sub     rsp, 20h
0x18002bebe  mov     rbx, rcx
0x18002bec1  mov     rcx, [rcx+60h]; hMem
0x18002bec5  test    rcx, rcx
0x18002bec8  jz      short loc_18002BED0
0x18002beca  call    cs:__imp_LocalFree
0x18002bed0  mov     rcx, [rbx+68h]; hMem
0x18002bed4  test    rcx, rcx
0x18002bed7  jz      short loc_18002BEDF
0x18002bed9  call    cs:__imp_LocalFree
0x18002bedf  mov     rcx, [rbx+70h]; hIcon
0x18002bee3  test    rcx, rcx
0x18002bee6  jz      short loc_18002BEEE
0x18002bee8  call    cs:__imp_DestroyIcon
0x18002beee  mov     rcx, [rbx+80h]; ho
0x18002bef5  test    rcx, rcx
0x18002bef8  jnz     short loc_18002BF3F
0x18002befa  mov     rcx, [rbx+88h]; ho
0x18002bf01  test    rcx, rcx
0x18002bf04  jnz     short loc_18002BF47
0x18002bf06  mov     rcx, [rbx+98h]
0x18002bf0d  test    rcx, rcx
0x18002bf10  jz      short loc_18002BF1E
0x18002bf12  mov     rax, [rcx]
0x18002bf15  mov     rax, [rax+10h]
0x18002bf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf1e  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x18002bf22  mov     rcx, [rbx+58h]; hMem
0x18002bf26  test    rcx, rcx
0x18002bf29  jz      short loc_18002BF39
0x18002bf2b  call    cs:__imp_LocalFree
0x18002bf31  mov     qword ptr [rbx+58h], 0
0x18002bf39  add     rsp, 20h
0x18002bf3d  pop     rbx
0x18002bf3e  retn
0x18002bf3f  call    cs:__imp_DeleteObject
0x18002bf45  jmp     short loc_18002BEFA
0x18002bf47  call    cs:__imp_DeleteObject
0x18002bf4d  jmp     short loc_18002BF06
```
