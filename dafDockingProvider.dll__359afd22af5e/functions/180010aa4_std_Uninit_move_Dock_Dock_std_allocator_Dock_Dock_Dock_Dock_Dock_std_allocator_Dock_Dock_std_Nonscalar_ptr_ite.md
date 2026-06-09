# std::_Uninit_move<Dock *,Dock *,std::allocator<Dock>,Dock>(Dock *,Dock *,Dock *,std::allocator<Dock> &,Dock *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180010aa4`
- end: `0x180010b02`
- name: `??$_Uninit_move@PEAVDock@@PEAV1@V?$allocator@VDock@@@std@@V1@@std@@YAPEAVDock@@PEAV1@00AEAV?$allocator@VDock@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `94`
- prototype: `Dock *__fastcall(struct Dock *, const struct Dock *, Dock *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013390`

## callees

- `0x180010aa4`
- `0x180010b08`

## pseudocode

```c
Dock *__fastcall std::_Uninit_move<Dock *,Dock *,std::allocator<Dock>,Dock>(
        struct Dock *a1,
        const struct Dock *a2,
        Dock *a3)
{
  Dock *v3; // rbx
  const struct Dock *v5; // rdi
  Dock *result; // rax
  Dock *i; // rbx
  Dock *v8; // [rsp+40h] [rbp+18h]

  v8 = a3;
  v3 = a3;
  v5 = a1;
  try
  {
    while ( v5 != a2 )
    {
      Dock::Dock(v3, v5);
      v3 = (Dock *)((char *)v3 + 2936);
      v8 = v3;
      v5 = (const struct Dock *)((char *)v5 + 2936);
    }
    result = v3;
  }
  catch ( ... )
  {
    for ( i = a3; i != v8; i = (Dock *)((char *)i + 2936) )
      std::_Dest_val<std::allocator<Dock>,Dock>(a1, i);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180010aa4  mov     rax, rsp
0x180010aa7  mov     [rax+8], rbx
0x180010aab  mov     [rax+10h], rsi
0x180010aaf  mov     [rax+20h], r9
0x180010ab3  mov     [rax+18h], r8
0x180010ab7  push    rdi
0x180010ab8  sub     rsp, 20h
0x180010abc  mov     rbx, r8
0x180010abf  mov     rsi, rdx
0x180010ac2  mov     rdi, rcx
0x180010ac5  mov     [rsp+28h+arg_18], rbx
0x180010aca  cmp     rdi, rsi
0x180010acd  jz      short loc_180010AEF
0x180010acf  mov     rdx, rdi; struct Dock *
0x180010ad2  mov     rcx, rbx; this
0x180010ad5  call    ??0Dock@@QEAA@AEBV0@@Z; Dock::Dock(Dock const &)
0x180010ada  add     rbx, 0B78h
0x180010ae1  mov     [rsp+28h+arg_10], rbx
0x180010ae6  add     rdi, 0B78h
0x180010aed  jmp     short loc_180010ACA
0x180010aef  mov     rax, rbx
0x180010af2  mov     rbx, [rsp+28h+arg_0]
0x180010af7  mov     rsi, [rsp+28h+arg_8]
0x180010afc  add     rsp, 20h
0x180010b00  pop     rdi
0x180010b01  retn
```
