# CLogCache::_FreeResources(void)

- ea: `0x180015a14`
- end: `0x180015a80`
- name: `?_FreeResources@CLogCache@@AEAAXXZ`
- size: `108`
- prototype: `void __fastcall(CLogCache *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015684`
- `0x180015724`

## callees

- `0x1800153ac`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015a2a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015a43`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015a2a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015a43`

## pseudocode

```c
void __fastcall CLogCache::_FreeResources(void **this)
{
  void *v2; // rcx

  CEventLog::Close((CEventLog *)(this + 1));
  operator delete[](this[3]);
  v2 = this[5];
  this[3] = 0;
  *((_DWORD *)this + 8) = 0;
  operator delete[](v2);
  this[5] = 0;
  *((_WORD *)this + 42) = 0;
  this[8] = 0;
  this[6] = 0;
  this[7] = 0;
  this[9] = 0;
  *((_DWORD *)this + 20) = 4;
}

```

## disassembly

```asm
0x180015a14  push    rbx
0x180015a16  sub     rsp, 20h
0x180015a1a  mov     rbx, rcx
0x180015a1d  add     rcx, 8; this
0x180015a21  call    ?Close@CEventLog@@QEAAXXZ; CEventLog::Close(void)
0x180015a26  mov     rcx, [rbx+18h]
0x180015a2a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015a30  mov     rcx, [rbx+28h]
0x180015a34  mov     qword ptr [rbx+18h], 0
0x180015a3c  mov     dword ptr [rbx+20h], 0
0x180015a43  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015a49  xor     eax, eax
0x180015a4b  mov     qword ptr [rbx+28h], 0
0x180015a53  mov     [rbx+54h], ax
0x180015a57  mov     [rbx+40h], rax
0x180015a5b  mov     qword ptr [rbx+30h], 0
0x180015a63  mov     qword ptr [rbx+38h], 0
0x180015a6b  mov     qword ptr [rbx+48h], 0
0x180015a73  mov     dword ptr [rbx+50h], 4
0x180015a7a  add     rsp, 20h
0x180015a7e  pop     rbx
0x180015a7f  retn
```
