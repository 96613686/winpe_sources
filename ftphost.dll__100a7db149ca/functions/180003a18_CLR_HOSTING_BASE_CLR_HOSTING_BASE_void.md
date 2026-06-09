# CLR_HOSTING_BASE::~CLR_HOSTING_BASE(void)

- ea: `0x180003a18`
- end: `0x180003a50`
- name: `??1CLR_HOSTING_BASE@@MEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CLR_HOSTING_BASE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a60`
- `0x180003ab0`

## callees

- `0x180003a18`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180003a3c`
- `KERNEL32!FreeLibrary` at `0x180003a3c`

## pseudocode

```c
void __fastcall CLR_HOSTING_BASE::~CLR_HOSTING_BASE(CLR_HOSTING_BASE *this)
{
  HMODULE v2; // rcx

  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &CLR_HOSTING_BASE::`vftable';
  v2 = (HMODULE)*((_QWORD *)this + 2);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180003a18  push    rbx
0x180003a1a  sub     rsp, 20h
0x180003a1e  lea     rax, ??_7CLR_HOSTING_BASE@@6B@; const CLR_HOSTING_BASE::`vftable'
0x180003a25  mov     qword ptr [rcx+18h], 0
0x180003a2d  mov     [rcx], rax
0x180003a30  mov     rbx, rcx
0x180003a33  mov     rcx, [rcx+10h]; hLibModule
0x180003a37  test    rcx, rcx
0x180003a3a  jz      short loc_180003A4A
0x180003a3c  call    cs:__imp_FreeLibrary
0x180003a42  mov     qword ptr [rbx+10h], 0
0x180003a4a  add     rsp, 20h
0x180003a4e  pop     rbx
0x180003a4f  retn
```
