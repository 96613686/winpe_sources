# CCommandImpl::`vector deleting destructor'(uint)

- ea: `0x180009580`
- end: `0x1800095c5`
- name: `??_ECCommandImpl@@MEAAPEAXI@Z`
- size: `69`
- prototype: `void *__fastcall(CCommandImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180004fbc`
- `0x180009580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000959d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000959d`

## pseudocode

```c
LPVOID *__fastcall CCommandImpl::`vector deleting destructor'(LPVOID *this, char a2)
{
  *this = &CCommandImpl::`vftable';
  CoTaskMemFree(this[1]);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009580  mov     [rsp+arg_0], rbx
0x180009585  push    rdi
0x180009586  sub     rsp, 20h
0x18000958a  lea     rax, ??_7CCommandImpl@@6B@; const CCommandImpl::`vftable'
0x180009591  mov     rdi, rcx
0x180009594  mov     [rcx], rax
0x180009597  mov     ebx, edx
0x180009599  mov     rcx, [rcx+8]; pv
0x18000959d  call    cs:__imp_CoTaskMemFree
0x1800095a4  nop     dword ptr [rax+rax+00h]
0x1800095a9  test    bl, 1
0x1800095ac  jz      short loc_1800095B6
0x1800095ae  mov     rcx, rdi; Block
0x1800095b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800095b6  mov     rbx, [rsp+28h+arg_0]
0x1800095bb  mov     rax, rdi
0x1800095be  add     rsp, 20h
0x1800095c2  pop     rdi
0x1800095c3  retn
```
