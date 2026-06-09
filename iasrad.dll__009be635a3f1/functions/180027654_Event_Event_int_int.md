# Event::Event(int,int)

- ea: `0x180027654`
- end: `0x1800276bc`
- name: `??0Event@@QEAA@HH@Z`
- size: `104`
- prototype: `Event *__fastcall(Event *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800207ac`

## callees

- `0x1800020f4`
- `0x180027654`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18002768f`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18002768f`
- `KERNEL32!CreateEventW` at `0x180027665`
- `KERNEL32!CreateEventW` at `0x180027665`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Event *__fastcall Event::Event(Event *this, BOOL a2)
{
  HANDLE EventW; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF
  const char *v6; // [rsp+50h] [rbp+8h] BYREF

  EventW = CreateEventW(0, a2, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW )
  {
    v6 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v6, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180027654  push    rbx
0x180027656  sub     rsp, 40h
0x18002765a  mov     rbx, rcx
0x18002765d  xor     r9d, r9d; lpName
0x180027660  xor     r8d, r8d; bInitialState
0x180027663  xor     ecx, ecx; lpEventAttributes
0x180027665  call    cs:__imp_CreateEventW
0x18002766b  mov     [rbx], rax
0x18002766e  test    rax, rax
0x180027671  jnz     short loc_1800276B3
0x180027673  lea     rax, aBadAllocation; "bad allocation"
0x18002767a  mov     [rsp+48h+arg_0], rax
0x18002767f  mov     r8d, 1
0x180027685  lea     rdx, [rsp+48h+arg_0]
0x18002768a  lea     rcx, [rsp+48h+pExceptionObject]
0x18002768f  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180027695  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002769c  mov     [rsp+48h+pExceptionObject], rax
0x1800276a1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800276a8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800276ad  call    _CxxThrowException_0
0x1800276b3  mov     rax, rbx
0x1800276b6  add     rsp, 40h
0x1800276ba  pop     rbx
0x1800276bb  retn
```
