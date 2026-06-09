# CWMWriter::DeleteProfile(void)

- ea: `0x18000f6ac`
- end: `0x18000f730`
- name: `?DeleteProfile@CWMWriter@@QEAAXXZ`
- size: `132`
- prototype: `void __fastcall(CWMWriter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e238`
- `0x18000ea00`

## callees

- `0x18000f6ac`
- `0x18001f010`

## pseudocode

```c
void __fastcall CWMWriter::DeleteProfile(CWMWriter *this)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = *((_QWORD *)this + 51);
  if ( v1 )
  {
    do
    {
      v3 = *(_QWORD *)(v1 + 16);
      v4 = *(_QWORD *)(v1 + 8);
      v5 = *(_QWORD *)(v3 + 416);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *(_QWORD *)(v3 + 416) = 0;
      }
      v1 = v4;
    }
    while ( v4 );
  }
  v6 = *((_QWORD *)this + 43);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 43) = 0;
  }
}

```

## disassembly

```asm
0x18000f6ac  mov     [rsp+arg_0], rbx
0x18000f6b1  mov     [rsp+arg_8], rsi
0x18000f6b6  push    rdi
0x18000f6b7  sub     rsp, 20h
0x18000f6bb  mov     rax, [rcx+198h]
0x18000f6c2  mov     rbx, rcx
0x18000f6c5  test    rax, rax
0x18000f6c8  jz      short loc_18000F6FD
0x18000f6ca  mov     rsi, [rax+10h]
0x18000f6ce  mov     rdi, [rax+8]
0x18000f6d2  mov     rcx, [rsi+1A0h]
0x18000f6d9  test    rcx, rcx
0x18000f6dc  jz      short loc_18000F6F5
0x18000f6de  mov     rax, [rcx]
0x18000f6e1  mov     rax, [rax+10h]
0x18000f6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ea  mov     qword ptr [rsi+1A0h], 0
0x18000f6f5  mov     rax, rdi
0x18000f6f8  test    rdi, rdi
0x18000f6fb  jnz     short loc_18000F6CA
0x18000f6fd  mov     rcx, [rbx+158h]
0x18000f704  test    rcx, rcx
0x18000f707  jz      short loc_18000F720
0x18000f709  mov     rax, [rcx]
0x18000f70c  mov     rax, [rax+10h]
0x18000f710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f715  mov     qword ptr [rbx+158h], 0
0x18000f720  mov     rbx, [rsp+28h+arg_0]
0x18000f725  mov     rsi, [rsp+28h+arg_8]
0x18000f72a  add     rsp, 20h
0x18000f72e  pop     rdi
0x18000f72f  retn
```
