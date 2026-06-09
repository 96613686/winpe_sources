# CWMWriter::ReleaseWMWriter(void)

- ea: `0x180011304`
- end: `0x1800113e5`
- name: `?ReleaseWMWriter@CWMWriter@@QEAAXXZ`
- size: `225`
- prototype: `void __fastcall(CWMWriter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e238`
- `0x18000f414`

## callees

- `0x180011304`
- `0x18001f010`

## pseudocode

```c
void __fastcall CWMWriter::ReleaseWMWriter(CWMWriter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *((_QWORD *)this + 42);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 42) = 0;
  }
  v3 = *((_QWORD *)this + 44);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 44) = 0;
  }
  v4 = *((_QWORD *)this + 40);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 40) = 0;
  }
  v5 = *((_QWORD *)this + 41);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 41) = 0;
  }
  v6 = *((_QWORD *)this + 50);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 50) = 0;
  }
  v7 = *((_QWORD *)this + 39);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 39) = 0;
  }
}

```

## disassembly

```asm
0x180011304  push    rbx
0x180011306  sub     rsp, 20h
0x18001130a  mov     rbx, rcx
0x18001130d  mov     rcx, [rcx+150h]
0x180011314  test    rcx, rcx
0x180011317  jz      short loc_180011330
0x180011319  mov     rax, [rcx]
0x18001131c  mov     rax, [rax+10h]
0x180011320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011325  mov     qword ptr [rbx+150h], 0
0x180011330  mov     rcx, [rbx+160h]
0x180011337  test    rcx, rcx
0x18001133a  jz      short loc_180011353
0x18001133c  mov     rax, [rcx]
0x18001133f  mov     rax, [rax+10h]
0x180011343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011348  mov     qword ptr [rbx+160h], 0
0x180011353  mov     rcx, [rbx+140h]
0x18001135a  test    rcx, rcx
0x18001135d  jz      short loc_180011376
0x18001135f  mov     rax, [rcx]
0x180011362  mov     rax, [rax+10h]
0x180011366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001136b  mov     qword ptr [rbx+140h], 0
0x180011376  mov     rcx, [rbx+148h]
0x18001137d  test    rcx, rcx
0x180011380  jz      short loc_180011399
0x180011382  mov     rax, [rcx]
0x180011385  mov     rax, [rax+10h]
0x180011389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001138e  mov     qword ptr [rbx+148h], 0
0x180011399  mov     rcx, [rbx+190h]
0x1800113a0  test    rcx, rcx
0x1800113a3  jz      short loc_1800113BC
0x1800113a5  mov     rax, [rcx]
0x1800113a8  mov     rax, [rax+10h]
0x1800113ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b1  mov     qword ptr [rbx+190h], 0
0x1800113bc  mov     rcx, [rbx+138h]
0x1800113c3  test    rcx, rcx
0x1800113c6  jz      short loc_1800113DF
0x1800113c8  mov     rax, [rcx]
0x1800113cb  mov     rax, [rax+10h]
0x1800113cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113d4  mov     qword ptr [rbx+138h], 0
0x1800113df  add     rsp, 20h
0x1800113e3  pop     rbx
0x1800113e4  retn
```
