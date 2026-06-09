# CIISModuleFactory::Terminate(void)

- ea: `0x180006ee0`
- end: `0x180006f29`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `73`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800058a0`
- `0x180006ee0`

## import_xrefs

- `iisutil!PuDeleteDebugPrintsObject` at `0x180006efe`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180006efe`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( g_pDebug && *(_DWORD *)(g_pDebug + 640) )
    g_pDebug = PuDeleteDebugPrintsObject();
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180006ee0  push    rbx
0x180006ee2  sub     rsp, 20h
0x180006ee6  mov     rbx, rcx
0x180006ee9  mov     rcx, cs:g_pDebug
0x180006ef0  test    rcx, rcx
0x180006ef3  jz      short loc_180006F0B
0x180006ef5  cmp     dword ptr [rcx+280h], 0
0x180006efc  jz      short loc_180006F0B
0x180006efe  call    cs:__imp_PuDeleteDebugPrintsObject
0x180006f04  mov     cs:g_pDebug, rax
0x180006f0b  test    rbx, rbx
0x180006f0e  jz      short loc_180006F23
0x180006f10  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180006f17  mov     rcx, rbx; Block
0x180006f1a  mov     [rbx+8], rax
0x180006f1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f23  add     rsp, 20h
0x180006f27  pop     rbx
0x180006f28  retn
```
