# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180002430`
- end: `0x18000246a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002430`
- `0x1800059dc`

## import_xrefs

- `msvcrt!free` at `0x180002456`
- `msvcrt!free` at `0x180002456`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
  if ( (v2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x180002430  mov     [rsp+arg_0], rbx
0x180002435  push    rdi
0x180002436  sub     rsp, 20h
0x18000243a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002441  mov     ebx, edx
0x180002443  mov     [rcx], rax
0x180002446  mov     rdi, rcx
0x180002449  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000244e  test    bl, 1
0x180002451  jz      short loc_18000245C
0x180002453  mov     rcx, rdi; Block
0x180002456  call    cs:__imp_free
0x18000245c  mov     rbx, [rsp+28h+arg_0]
0x180002461  mov     rax, rdi
0x180002464  add     rsp, 20h
0x180002468  pop     rdi
0x180002469  retn
```
