# Command::~Command(void)

- ea: `0x14000a190`
- end: `0x14000a214`
- name: `??1Command@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(Command *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007c70`
- `0x140007dd8`
- `0x140007e3c`
- `0x1400094b0`
- `0x14000aba2`

## callees

- `0x14000a190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1f2`

## pseudocode

```c
void __fastcall Command::~Command(void **this)
{
  if ( (unsigned __int64)this[11] >= 8 )
    operator delete(this[8]);
  this[10] = 0;
  this[11] = (void *)7;
  *((_WORD *)this + 32) = 0;
  if ( (unsigned __int64)this[7] >= 8 )
    operator delete(this[4]);
  this[7] = (void *)7;
  this[6] = 0;
  *((_WORD *)this + 16) = 0;
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x14000a190  mov     [rsp+arg_0], rbx
0x14000a195  push    rsi
0x14000a196  sub     rsp, 20h
0x14000a19a  cmp     qword ptr [rcx+58h], 8
0x14000a19f  mov     rbx, rcx
0x14000a1a2  jb      short loc_14000A1AE
0x14000a1a4  mov     rcx, [rcx+40h]
0x14000a1a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a1ae  xor     eax, eax
0x14000a1b0  mov     qword ptr [rbx+50h], 0
0x14000a1b8  mov     esi, 7
0x14000a1bd  mov     [rbx+58h], rsi
0x14000a1c1  mov     [rbx+40h], ax
0x14000a1c5  cmp     qword ptr [rbx+38h], 8
0x14000a1ca  jb      short loc_14000A1D6
0x14000a1cc  mov     rcx, [rbx+20h]
0x14000a1d0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a1d6  xor     eax, eax
0x14000a1d8  mov     [rbx+38h], rsi
0x14000a1dc  mov     qword ptr [rbx+30h], 0
0x14000a1e4  mov     [rbx+20h], ax
0x14000a1e8  cmp     qword ptr [rbx+18h], 8
0x14000a1ed  jb      short loc_14000A1F8
0x14000a1ef  mov     rcx, [rbx]
0x14000a1f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a1f8  mov     [rbx+18h], rsi
0x14000a1fc  xor     eax, eax
0x14000a1fe  mov     qword ptr [rbx+10h], 0
0x14000a206  mov     [rbx], ax
0x14000a209  mov     rbx, [rsp+28h+arg_0]
0x14000a20e  add     rsp, 20h
0x14000a212  pop     rsi
0x14000a213  retn
```
