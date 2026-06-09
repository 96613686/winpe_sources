# CCmstpLua::`scalar deleting destructor'(uint)

- ea: `0x180001a60`
- end: `0x180001abb`
- name: `??_GCCmstpLua@@UEAAPEAXI@Z`
- size: `91`
- prototype: `void *__fastcall(CCmstpLua *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a60`
- `0x180003010`

## import_xrefs

- `cmutil!CmFree` at `0x180001aa6`
- `cmutil!CmFree` at `0x180001aa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CCmstpLua *__fastcall CCmstpLua::`scalar deleting destructor'(CCmstpLua *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CCmstpLua::`vftable';
  _InterlockedDecrement(&dword_180006640);
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 2) = 0;
  }
  if ( (a2 & 1) != 0 )
    CmFree(this);
  return this;
}

```

## disassembly

```asm
0x180001a60  mov     [rsp+arg_0], rbx
0x180001a65  push    rdi
0x180001a66  sub     rsp, 20h
0x180001a6a  mov     edi, edx
0x180001a6c  mov     rbx, rcx
0x180001a6f  lea     rax, ??_7CCmstpLua@@6B@; const CCmstpLua::`vftable'
0x180001a76  mov     [rcx], rax
0x180001a79  lock dec cs:dword_180006640
0x180001a80  mov     rcx, [rcx+10h]
0x180001a84  test    rcx, rcx
0x180001a87  jz      short loc_180001A9D
0x180001a89  mov     rax, [rcx]
0x180001a8c  mov     rax, [rax+10h]
0x180001a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a95  mov     qword ptr [rbx+10h], 0
0x180001a9d  test    dil, 1
0x180001aa1  jz      short loc_180001AAD
0x180001aa3  mov     rcx, rbx
0x180001aa6  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180001aac  nop
0x180001aad  mov     rax, rbx
0x180001ab0  mov     rbx, [rsp+28h+arg_0]
0x180001ab5  add     rsp, 20h
0x180001ab9  pop     rdi
0x180001aba  retn
```
