# CIISVssWriter::~CIISVssWriter(void)

- ea: `0x1800037a4`
- end: `0x180003811`
- name: `??1CIISVssWriter@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CIISVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003820`

## callees

- `0x1800037a4`
- `0x180005010`

## pseudocode

```c
void __fastcall CIISVssWriter::~CIISVssWriter(CIISVssWriter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CIISVssWriter::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = *((_QWORD *)this + 1);
  *(_QWORD *)this = &CVssWriter::`vftable';
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1800037a4  push    rbx
0x1800037a6  sub     rsp, 20h
0x1800037aa  lea     rax, ??_7CIISVssWriter@@6B@; const CIISVssWriter::`vftable'
0x1800037b1  mov     rbx, rcx
0x1800037b4  mov     [rcx], rax
0x1800037b7  mov     rcx, [rcx+10h]
0x1800037bb  test    rcx, rcx
0x1800037be  jz      short loc_1800037D4
0x1800037c0  mov     rax, [rcx]
0x1800037c3  mov     rax, [rax+10h]
0x1800037c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037cc  mov     qword ptr [rbx+10h], 0
0x1800037d4  mov     rcx, [rbx+8]
0x1800037d8  lea     rax, ??_7CVssWriter@@6B@; const CVssWriter::`vftable'
0x1800037df  mov     [rbx], rax
0x1800037e2  test    rcx, rcx
0x1800037e5  jz      short loc_18000380B
0x1800037e7  mov     rax, [rcx]
0x1800037ea  mov     rax, [rax+30h]
0x1800037ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f3  mov     rcx, [rbx+8]
0x1800037f7  mov     rax, [rcx]
0x1800037fa  mov     rax, [rax+10h]
0x1800037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003803  mov     qword ptr [rbx+8], 0
0x18000380b  add     rsp, 20h
0x18000380f  pop     rbx
0x180003810  retn
```
