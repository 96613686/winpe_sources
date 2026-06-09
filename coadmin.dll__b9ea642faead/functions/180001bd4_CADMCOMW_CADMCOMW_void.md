# CADMCOMW::~CADMCOMW(void)

- ea: `0x180001bd4`
- end: `0x180001c35`
- name: `??1CADMCOMW@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CADMCOMW *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008430`

## callees

- `0x180009920`
- `0x18000d6a4`

## import_xrefs

- `IisRTL!??1STRU@@QEAA@XZ` at `0x180001c2e`

## pseudocode

```c
void __fastcall CADMCOMW::~CADMCOMW(CADMCOMW *this)
{
  *(_QWORD *)this = &CADMCOMW::`vftable';
  CADMCOMW::Terminate(this, 0);
  *((_QWORD *)this + 105) = &COConnectionPoint::`vftable';
  COConnectionPoint::Terminate((CADMCOMW *)((char *)this + 840), 0);
  *((_QWORD *)this + 102) = &CADMCOMW::CImpIConnectionPointContainer::`vftable';
  *((_QWORD *)this + 98) = &CADMCOMW::CImpExpHelp::`vftable';
  STRU::~STRU((CADMCOMW *)((char *)this + 200));
}

```

## disassembly

```asm
0x180001bd4  push    rbx
0x180001bd6  sub     rsp, 20h
0x180001bda  lea     rax, ??_7CADMCOMW@@6B@; const CADMCOMW::`vftable'
0x180001be1  xor     edx, edx; int
0x180001be3  mov     [rcx], rax
0x180001be6  mov     rbx, rcx
0x180001be9  call    ?Terminate@CADMCOMW@@AEAAXH@Z; CADMCOMW::Terminate(int)
0x180001bee  lea     rcx, [rbx+348h]; this
0x180001bf5  xor     edx, edx; int
0x180001bf7  lea     rax, ??_7COConnectionPoint@@6B@; const COConnectionPoint::`vftable'
0x180001bfe  mov     [rcx], rax
0x180001c01  call    ?Terminate@COConnectionPoint@@QEAAJH@Z; COConnectionPoint::Terminate(int)
0x180001c06  lea     rax, ??_7CImpIConnectionPointContainer@CADMCOMW@@6B@; const CADMCOMW::CImpIConnectionPointContainer::`vftable'
0x180001c0d  mov     [rbx+330h], rax
0x180001c14  lea     rcx, [rbx+0C8h]
0x180001c1b  lea     rax, ??_7CImpExpHelp@CADMCOMW@@6B@; const CADMCOMW::CImpExpHelp::`vftable'
0x180001c22  mov     [rbx+310h], rax
0x180001c29  add     rsp, 20h
0x180001c2d  pop     rbx
0x180001c2e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
