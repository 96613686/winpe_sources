# NativeMsh::PwrshCommon::~PwrshCommon(void)

- ea: `0x180007730`
- end: `0x18000778b`
- name: `??1PwrshCommon@NativeMsh@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(NativeMsh::PwrshCommon *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800020a0`
- `0x180005230`
- `0x18000529c`
- `0x180009e68`
- `0x18000a150`

## callees

- `0x180007730`
- `0x18000b010`

## pseudocode

```c
void __fastcall NativeMsh::PwrshCommon::~PwrshCommon(NativeMsh::PwrshCommon *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &NativeMsh::PwrshCommon::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180007730  push    rbx
0x180007732  sub     rsp, 20h
0x180007736  lea     rax, ??_7PwrshCommon@NativeMsh@@6B@; const NativeMsh::PwrshCommon::`vftable'
0x18000773d  mov     rbx, rcx
0x180007740  mov     [rcx], rax
0x180007743  mov     rcx, [rcx+8]
0x180007747  test    rcx, rcx
0x18000774a  jz      short loc_180007764
0x18000774c  mov     rax, [rcx]
0x18000774f  mov     edx, 1
0x180007754  mov     rax, [rax]
0x180007757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775c  mov     qword ptr [rbx+8], 0
0x180007764  mov     rcx, [rbx+10h]
0x180007768  test    rcx, rcx
0x18000776b  jz      short loc_180007785
0x18000776d  mov     rax, [rcx]
0x180007770  mov     edx, 1
0x180007775  mov     rax, [rax]
0x180007778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777d  mov     qword ptr [rbx+10h], 0
0x180007785  add     rsp, 20h
0x180007789  pop     rbx
0x18000778a  retn
```
