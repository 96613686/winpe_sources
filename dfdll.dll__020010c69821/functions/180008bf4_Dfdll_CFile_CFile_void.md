# Dfdll::CFile::~CFile(void)

- ea: `0x180008bf4`
- end: `0x180008c2c`
- name: `??1CFile@Dfdll@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(Dfdll::CFile *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f416`

## callees

- `0x180008bf4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008c11`
- `KERNEL32!CloseHandle` at `0x180008c11`

## pseudocode

```c
void __fastcall Dfdll::CFile::~CFile(Dfdll::CFile *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &Dfdll::CFile::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = -1;
  }
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008bf4  push    rbx
0x180008bf6  sub     rsp, 20h
0x180008bfa  mov     rbx, rcx
0x180008bfd  lea     rax, ??_7CFile@Dfdll@@6B@; const Dfdll::CFile::`vftable'
0x180008c04  mov     [rcx], rax
0x180008c07  mov     rcx, [rcx+8]; hObject
0x180008c0b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008c0f  jz      short loc_180008C1C
0x180008c11  call    cs:__imp_CloseHandle
0x180008c17  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180008c1c  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008c23  mov     [rbx], rax
0x180008c26  add     rsp, 20h
0x180008c2a  pop     rbx
0x180008c2b  retn
```
