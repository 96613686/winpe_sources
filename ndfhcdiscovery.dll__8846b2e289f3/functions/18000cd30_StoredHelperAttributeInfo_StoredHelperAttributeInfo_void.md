# StoredHelperAttributeInfo::~StoredHelperAttributeInfo(void)

- ea: `0x18000cd30`
- end: `0x18000cdf8`
- name: `??1StoredHelperAttributeInfo@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(StoredHelperAttributeInfo *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c538`
- `0x18000ca90`
- `0x18000e2a0`
- `0x180010c18`
- `0x1800141fa`

## callees

- `0x18000cd30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cda5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cdce`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cda5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cdce`

## pseudocode

```c
void __fastcall StoredHelperAttributeInfo::~StoredHelperAttributeInfo(void **this)
{
  if ( (unsigned __int64)this[16] >= 8 )
    operator delete(this[13]);
  this[15] = 0;
  this[16] = (void *)7;
  *((_WORD *)this + 52) = 0;
  if ( (unsigned __int64)this[12] >= 8 )
    operator delete(this[9]);
  this[12] = (void *)7;
  this[11] = 0;
  *((_WORD *)this + 36) = 0;
  if ( (unsigned __int64)this[8] >= 8 )
    operator delete(this[5]);
  this[8] = (void *)7;
  this[7] = 0;
  *((_WORD *)this + 20) = 0;
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x18000cd30  mov     [rsp+arg_0], rbx
0x18000cd35  push    rsi
0x18000cd36  sub     rsp, 20h
0x18000cd3a  cmp     qword ptr [rcx+80h], 8
0x18000cd42  mov     rbx, rcx
0x18000cd45  jb      short loc_18000CD57
0x18000cd47  mov     rcx, [rcx+68h]
0x18000cd4b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd52  nop     dword ptr [rax+rax+00h]
0x18000cd57  xor     eax, eax
0x18000cd59  mov     qword ptr [rbx+78h], 0
0x18000cd61  mov     esi, 7
0x18000cd66  mov     [rbx+80h], rsi
0x18000cd6d  mov     [rbx+68h], ax
0x18000cd71  cmp     qword ptr [rbx+60h], 8
0x18000cd76  jb      short loc_18000CD88
0x18000cd78  mov     rcx, [rbx+48h]
0x18000cd7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd83  nop     dword ptr [rax+rax+00h]
0x18000cd88  xor     eax, eax
0x18000cd8a  mov     [rbx+60h], rsi
0x18000cd8e  mov     qword ptr [rbx+58h], 0
0x18000cd96  mov     [rbx+48h], ax
0x18000cd9a  cmp     qword ptr [rbx+40h], 8
0x18000cd9f  jb      short loc_18000CDB1
0x18000cda1  mov     rcx, [rbx+28h]
0x18000cda5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cdac  nop     dword ptr [rax+rax+00h]
0x18000cdb1  xor     eax, eax
0x18000cdb3  mov     [rbx+40h], rsi
0x18000cdb7  mov     qword ptr [rbx+38h], 0
0x18000cdbf  mov     [rbx+28h], ax
0x18000cdc3  cmp     qword ptr [rbx+20h], 8
0x18000cdc8  jb      short loc_18000CDDA
0x18000cdca  mov     rcx, [rbx+8]
0x18000cdce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cdd5  nop     dword ptr [rax+rax+00h]
0x18000cdda  mov     [rbx+20h], rsi
0x18000cdde  xor     eax, eax
0x18000cde0  mov     qword ptr [rbx+18h], 0
0x18000cde8  mov     [rbx+8], ax
0x18000cdec  mov     rbx, [rsp+28h+arg_0]
0x18000cdf1  add     rsp, 20h
0x18000cdf5  pop     rsi
0x18000cdf6  retn
```
