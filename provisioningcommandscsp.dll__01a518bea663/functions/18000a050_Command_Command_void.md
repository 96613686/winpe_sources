# Command::~Command(void)

- ea: `0x18000a050`
- end: `0x18000a0d4`
- name: `??1Command@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(void **this)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006b10`
- `0x180007d24`
- `0x180007e48`
- `0x1800089c0`
- `0x180009fa0`
- `0x18000a0dc`
- `0x18000bb0c`
- `0x18000cf0a`
- `0x18000d1e3`
- `0x18000d34a`

## callees

- `0x18000a050`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a068`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a090`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a0b2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a068`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a090`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a0b2`

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
0x18000a050  mov     [rsp+arg_0], rbx
0x18000a055  push    rsi
0x18000a056  sub     rsp, 20h
0x18000a05a  cmp     qword ptr [rcx+58h], 8
0x18000a05f  mov     rbx, rcx
0x18000a062  jb      short loc_18000A06E
0x18000a064  mov     rcx, [rcx+40h]
0x18000a068  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a06e  xor     eax, eax
0x18000a070  mov     qword ptr [rbx+50h], 0
0x18000a078  mov     esi, 7
0x18000a07d  mov     [rbx+58h], rsi
0x18000a081  mov     [rbx+40h], ax
0x18000a085  cmp     qword ptr [rbx+38h], 8
0x18000a08a  jb      short loc_18000A096
0x18000a08c  mov     rcx, [rbx+20h]
0x18000a090  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a096  xor     eax, eax
0x18000a098  mov     [rbx+38h], rsi
0x18000a09c  mov     qword ptr [rbx+30h], 0
0x18000a0a4  mov     [rbx+20h], ax
0x18000a0a8  cmp     qword ptr [rbx+18h], 8
0x18000a0ad  jb      short loc_18000A0B8
0x18000a0af  mov     rcx, [rbx]
0x18000a0b2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a0b8  mov     [rbx+18h], rsi
0x18000a0bc  xor     eax, eax
0x18000a0be  mov     qword ptr [rbx+10h], 0
0x18000a0c6  mov     [rbx], ax
0x18000a0c9  mov     rbx, [rsp+28h+arg_0]
0x18000a0ce  add     rsp, 20h
0x18000a0d2  pop     rsi
0x18000a0d3  retn
```
