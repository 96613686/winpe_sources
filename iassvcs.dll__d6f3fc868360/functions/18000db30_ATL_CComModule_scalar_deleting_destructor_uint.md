# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x18000db30`
- end: `0x18000db6a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000db30`
- `0x180011f80`

## import_xrefs

- `msvcrt!free` at `0x18000db56`
- `msvcrt!free` at `0x18000db56`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, char a2)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000db30  mov     [rsp+arg_0], rbx
0x18000db35  push    rdi
0x18000db36  sub     rsp, 20h
0x18000db3a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18000db41  mov     ebx, edx
0x18000db43  mov     [rcx], rax
0x18000db46  mov     rdi, rcx
0x18000db49  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000db4e  test    bl, 1
0x18000db51  jz      short loc_18000DB5C
0x18000db53  mov     rcx, rdi; Block
0x18000db56  call    cs:__imp_free
0x18000db5c  mov     rbx, [rsp+28h+arg_0]
0x18000db61  mov     rax, rdi
0x18000db64  add     rsp, 20h
0x18000db68  pop     rdi
0x18000db69  retn
```
