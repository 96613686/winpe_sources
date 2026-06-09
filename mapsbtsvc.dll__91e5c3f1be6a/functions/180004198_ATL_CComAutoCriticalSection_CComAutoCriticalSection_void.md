# ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)

- ea: `0x180004198`
- end: `0x1800041cb`
- name: `??0CComAutoCriticalSection@ATL@@QEAA@XZ`
- size: `51`
- prototype: `ATL::CComAutoCriticalSection *__fastcall(ATL::CComAutoCriticalSection *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800018e0`
- `0x18000aee8`

## callees

- `0x18000303c`
- `0x18000395c`
- `0x180004198`

## pseudocode

```c
ATL::CComAutoCriticalSection *__fastcall ATL::CComAutoCriticalSection::CComAutoCriticalSection(
        ATL::CComAutoCriticalSection *this)
{
  int v2; // eax

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  v2 = ATL::CComCriticalSection::Init(this);
  if ( v2 < 0 )
    ATL::AtlThrowImpl(v2);
  return this;
}

```

## disassembly

```asm
0x180004198  push    rbx
0x18000419a  sub     rsp, 20h
0x18000419e  xorps   xmm0, xmm0
0x1800041a1  xor     eax, eax
0x1800041a3  movups  xmmword ptr [rcx], xmm0
0x1800041a6  mov     rbx, rcx
0x1800041a9  movups  xmmword ptr [rcx+10h], xmm0
0x1800041ad  mov     [rcx+20h], rax
0x1800041b1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800041b6  test    eax, eax
0x1800041b8  jns     short loc_1800041C2
0x1800041ba  mov     ecx, eax; int
0x1800041bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800041c2  mov     rax, rbx
0x1800041c5  add     rsp, 20h
0x1800041c9  pop     rbx
0x1800041ca  retn
```
