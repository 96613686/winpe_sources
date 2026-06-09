# ATL::CRegObject::~CRegObject(void)

- ea: `0x140002174`
- end: `0x1400021dd`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `105`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022d0`
- `0x140004f48`

## callees

- `0x140002174`
- `0x140002cc0`

## import_xrefs

- `msvcrt!free` at `0x1400021a7`
- `msvcrt!free` at `0x1400021bd`
- `msvcrt!free` at `0x1400021a7`
- `msvcrt!free` at `0x1400021bd`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this, unsigned int a2)
{
  ATL::CExpansionVector *v3; // rdi
  unsigned int v4; // edx
  void *v5; // rcx

  v3 = (ATL::CRegObject *)((char *)this + 8);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8), a2);
  ATL::CExpansionVector::ClearReplacements(v3, v4);
  if ( *(_QWORD *)v3 )
  {
    free(*(void **)v3);
    *(_QWORD *)v3 = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x140002174  mov     [rsp+arg_0], rbx
0x140002179  push    rdi
0x14000217a  sub     rsp, 20h
0x14000217e  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140002185  mov     rbx, rcx
0x140002188  lea     rdi, [rcx+8]
0x14000218c  mov     [rcx], rax
0x14000218f  mov     rcx, rdi; this
0x140002192  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140002197  mov     rcx, rdi; this
0x14000219a  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000219f  mov     rcx, [rdi]; Block
0x1400021a2  test    rcx, rcx
0x1400021a5  jz      short loc_1400021B4
0x1400021a7  call    cs:__imp_free
0x1400021ad  mov     qword ptr [rdi], 0
0x1400021b4  mov     rcx, [rbx+10h]; Block
0x1400021b8  test    rcx, rcx
0x1400021bb  jz      short loc_1400021CB
0x1400021bd  call    cs:__imp_free
0x1400021c3  mov     qword ptr [rbx+10h], 0
0x1400021cb  mov     dword ptr [rbx+18h], 0
0x1400021d2  mov     rbx, [rsp+28h+arg_0]
0x1400021d7  add     rsp, 20h
0x1400021db  pop     rdi
0x1400021dc  retn
```
