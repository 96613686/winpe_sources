# TSTR::~TSTR(void)

- ea: `0x18000243c`
- end: `0x18000246c`
- name: `??1TSTR@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(TSTR *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012f36`
- `0x180013180`
- `0x180013192`
- `0x1800131a4`
- `0x1800134ea`
- `0x1800138a2`
- `0x1800138b4`
- `0x1800138da`

## callees

- `0x18000243c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000244f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000244f`

## pseudocode

```c
void __fastcall TSTR::~TSTR(void **this)
{
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x18000243c  push    rbx
0x18000243e  sub     rsp, 20h
0x180002442  cmp     qword ptr [rcx+18h], 8
0x180002447  mov     rbx, rcx
0x18000244a  jb      short loc_180002455
0x18000244c  mov     rcx, [rcx]
0x18000244f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002455  xor     eax, eax
0x180002457  mov     qword ptr [rbx+18h], 7
0x18000245f  mov     [rbx+10h], rax
0x180002463  mov     [rbx], ax
0x180002466  add     rsp, 20h
0x18000246a  pop     rbx
0x18000246b  retn
```
