# std::make_unique<uus::Session,ushort const * &,0>(ushort const * &)

- ea: `0x180003b68`
- end: `0x180003bd3`
- name: `??$make_unique@USession@uus@@AEAPEBG$0A@@std@@YA?AV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@0@AEAPEBG@Z`
- size: `107`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003448`

## callees

- `0x180003590`
- `0x180005438`
- `0x1800087c0`

## pseudocode

```c
_QWORD *__fastcall std::make_unique<uus::Session,unsigned short const * &,0>(_QWORD *a1, __int64 *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  _QWORD *v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = a1;
  v4 = operator new(0x10u);
  v7 = v4;
  v5 = *a2;
  *v4 = &uus::Session::`vftable';
  v4[1] = uus::Utility::GetFirstBrainSession<uus::Brain3>(v5);
  v7 = 0;
  *a1 = v4;
  std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(&v7);
  return a1;
}

```

## disassembly

```asm
0x180003b68  mov     [rsp+arg_8], rbx
0x180003b6d  mov     [rsp+arg_10], rsi
0x180003b72  mov     [rsp+arg_0], rcx
0x180003b77  push    rdi
0x180003b78  sub     rsp, 30h
0x180003b7c  mov     rbx, rdx
0x180003b7f  mov     rsi, rcx
0x180003b82  mov     ecx, 10h; Size
0x180003b87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b8c  mov     rdi, rax
0x180003b8f  mov     [rsp+38h+arg_0], rax
0x180003b94  mov     rcx, [rbx]
0x180003b97  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180003b9e  mov     [rdi], rax
0x180003ba1  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x180003ba6  mov     [rdi+8], rax
0x180003baa  mov     [rsp+38h+arg_0], 0
0x180003bb3  mov     [rsi], rdi
0x180003bb6  lea     rcx, [rsp+38h+arg_0]
0x180003bbb  call    ??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ; std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(void)
0x180003bc0  mov     rax, rsi
0x180003bc3  mov     rbx, [rsp+38h+arg_8]
0x180003bc8  mov     rsi, [rsp+38h+arg_10]
0x180003bcd  add     rsp, 30h
0x180003bd1  pop     rdi
0x180003bd2  retn
```
