# GUIDVarInfo::~GUIDVarInfo(void)

- ea: `0x18000ccc0`
- end: `0x18000cd2a`
- name: `??1GUIDVarInfo@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(GUIDVarInfo *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c528`
- `0x18000ca20`
- `0x18000d670`
- `0x180010b18`
- `0x1800141c4`

## callees

- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ccd4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd01`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ccd4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd01`

## pseudocode

```c
void __fastcall GUIDVarInfo::~GUIDVarInfo(void **this)
{
  if ( (unsigned __int64)this[9] >= 8 )
    operator delete(this[6]);
  this[9] = (void *)7;
  this[8] = 0;
  *((_WORD *)this + 24) = 0;
  if ( (unsigned __int64)this[5] >= 8 )
    operator delete(this[2]);
  this[5] = (void *)7;
  this[4] = 0;
  *((_WORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x18000ccc0  push    rbx
0x18000ccc2  sub     rsp, 20h
0x18000ccc6  cmp     qword ptr [rcx+48h], 8
0x18000cccb  mov     rbx, rcx
0x18000ccce  jb      short loc_18000CCE0
0x18000ccd0  mov     rcx, [rcx+30h]
0x18000ccd4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ccdb  nop     dword ptr [rax+rax+00h]
0x18000cce0  xor     eax, eax
0x18000cce2  mov     qword ptr [rbx+48h], 7
0x18000ccea  mov     qword ptr [rbx+40h], 0
0x18000ccf2  mov     [rbx+30h], ax
0x18000ccf6  cmp     qword ptr [rbx+28h], 8
0x18000ccfb  jb      short loc_18000CD0D
0x18000ccfd  mov     rcx, [rbx+10h]
0x18000cd01  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd08  nop     dword ptr [rax+rax+00h]
0x18000cd0d  xor     eax, eax
0x18000cd0f  mov     qword ptr [rbx+28h], 7
0x18000cd17  mov     qword ptr [rbx+20h], 0
0x18000cd1f  mov     [rbx+10h], ax
0x18000cd23  add     rsp, 20h
0x18000cd27  pop     rbx
0x18000cd28  retn
```
