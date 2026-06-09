# Command::~Command(void)

- ea: `0x18000a554`
- end: `0x18000a5eb`
- name: `??1Command@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(Command *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006e40`
- `0x1800080bc`
- `0x1800081f0`
- `0x180008dd0`
- `0x18000a490`
- `0x18000a5f4`
- `0x18000c1d8`
- `0x18000d5d0`
- `0x18000d8af`
- `0x18000da16`

## callees

- `0x18000a554`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a56c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a59a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a56c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a59a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5c2`

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
0x18000a554  mov     [rsp+arg_0], rbx
0x18000a559  push    rsi
0x18000a55a  sub     rsp, 20h
0x18000a55e  cmp     qword ptr [rcx+58h], 8
0x18000a563  mov     rbx, rcx
0x18000a566  jb      short loc_18000A578
0x18000a568  mov     rcx, [rcx+40h]
0x18000a56c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a573  nop     dword ptr [rax+rax+00h]
0x18000a578  xor     eax, eax
0x18000a57a  mov     qword ptr [rbx+50h], 0
0x18000a582  mov     esi, 7
0x18000a587  mov     [rbx+58h], rsi
0x18000a58b  mov     [rbx+40h], ax
0x18000a58f  cmp     qword ptr [rbx+38h], 8
0x18000a594  jb      short loc_18000A5A6
0x18000a596  mov     rcx, [rbx+20h]
0x18000a59a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a5a1  nop     dword ptr [rax+rax+00h]
0x18000a5a6  xor     eax, eax
0x18000a5a8  mov     [rbx+38h], rsi
0x18000a5ac  mov     qword ptr [rbx+30h], 0
0x18000a5b4  mov     [rbx+20h], ax
0x18000a5b8  cmp     qword ptr [rbx+18h], 8
0x18000a5bd  jb      short loc_18000A5CE
0x18000a5bf  mov     rcx, [rbx]
0x18000a5c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a5c9  nop     dword ptr [rax+rax+00h]
0x18000a5ce  mov     [rbx+18h], rsi
0x18000a5d2  xor     eax, eax
0x18000a5d4  mov     qword ptr [rbx+10h], 0
0x18000a5dc  mov     [rbx], ax
0x18000a5df  mov     rbx, [rsp+28h+arg_0]
0x18000a5e4  add     rsp, 20h
0x18000a5e8  pop     rsi
0x18000a5e9  retn
```
