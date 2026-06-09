# CDpUrlAccessor::~CDpUrlAccessor(void)

- ea: `0x180003034`
- end: `0x180003113`
- name: `??1CDpUrlAccessor@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(CDpUrlAccessor *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003260`
- `0x180003330`

## callees

- `0x180003034`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003052`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003089`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800030b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800030de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003052`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003089`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800030b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800030de`
- `KERNEL32!DeleteCriticalSection` at `0x180003102`
- `KERNEL32!DeleteCriticalSection` at `0x180003102`

## pseudocode

```c
void __fastcall CDpUrlAccessor::~CDpUrlAccessor(CDpUrlAccessor *this)
{
  if ( *((_QWORD *)this + 26) >= 8u )
    operator delete(*((void **)this + 23));
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 7;
  *((_WORD *)this + 92) = 0;
  if ( *((_QWORD *)this + 21) >= 8u )
    operator delete(*((void **)this + 18));
  *((_QWORD *)this + 21) = 7;
  *((_QWORD *)this + 20) = 0;
  *((_WORD *)this + 72) = 0;
  if ( *((_QWORD *)this + 16) >= 8u )
    operator delete(*((void **)this + 13));
  *((_QWORD *)this + 16) = 7;
  *((_QWORD *)this + 15) = 0;
  *((_WORD *)this + 52) = 0;
  if ( *((_QWORD *)this + 11) >= 8u )
    operator delete(*((void **)this + 8));
  *((_QWORD *)this + 11) = 7;
  *((_QWORD *)this + 10) = 0;
  *((_WORD *)this + 32) = 0;
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180003034  mov     [rsp+arg_0], rbx
0x180003039  push    rsi
0x18000303a  sub     rsp, 20h
0x18000303e  cmp     qword ptr [rcx+0D0h], 8
0x180003046  mov     rbx, rcx
0x180003049  jb      short loc_180003058
0x18000304b  mov     rcx, [rcx+0B8h]
0x180003052  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003058  xor     eax, eax
0x18000305a  mov     qword ptr [rbx+0C8h], 0
0x180003065  mov     esi, 7
0x18000306a  mov     [rbx+0D0h], rsi
0x180003071  mov     [rbx+0B8h], ax
0x180003078  cmp     qword ptr [rbx+0A8h], 8
0x180003080  jb      short loc_18000308F
0x180003082  mov     rcx, [rbx+90h]
0x180003089  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000308f  xor     eax, eax
0x180003091  mov     [rbx+0A8h], rsi
0x180003098  mov     qword ptr [rbx+0A0h], 0
0x1800030a3  mov     [rbx+90h], ax
0x1800030aa  cmp     qword ptr [rbx+80h], 8
0x1800030b2  jb      short loc_1800030BE
0x1800030b4  mov     rcx, [rbx+68h]
0x1800030b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800030be  xor     eax, eax
0x1800030c0  mov     [rbx+80h], rsi
0x1800030c7  mov     qword ptr [rbx+78h], 0
0x1800030cf  mov     [rbx+68h], ax
0x1800030d3  cmp     qword ptr [rbx+58h], 8
0x1800030d8  jb      short loc_1800030E4
0x1800030da  mov     rcx, [rbx+40h]
0x1800030de  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800030e4  xor     eax, eax
0x1800030e6  mov     [rbx+58h], rsi
0x1800030ea  mov     qword ptr [rbx+50h], 0
0x1800030f2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800030f6  mov     [rbx+40h], ax
0x1800030fa  cmp     [rcx+28h], al
0x1800030fd  jz      short loc_180003108
0x1800030ff  mov     [rcx+28h], al
0x180003102  call    cs:__imp_DeleteCriticalSection
0x180003108  mov     rbx, [rsp+28h+arg_0]
0x18000310d  add     rsp, 20h
0x180003111  pop     rsi
0x180003112  retn
```
