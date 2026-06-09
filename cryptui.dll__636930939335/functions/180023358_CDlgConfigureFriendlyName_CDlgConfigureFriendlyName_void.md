# CDlgConfigureFriendlyName::~CDlgConfigureFriendlyName(void)

- ea: `0x180023358`
- end: `0x180023387`
- name: `??1CDlgConfigureFriendlyName@@UEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CDlgConfigureFriendlyName *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180023480`
- `0x180024560`
- `0x18004020a`

## callees

- `0x18001342c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023373`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023373`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDlgConfigureFriendlyName::~CDlgConfigureFriendlyName(HLOCAL *this)
{
  *this = &CDlgConfigureFriendlyName::`vftable';
  LocalFree(this[9]);
  ATL::CWindowImplRoot<WTL::CListViewCtrlT<ATL::CWindow>>::~CWindowImplRoot<WTL::CListViewCtrlT<ATL::CWindow>>(this);
}

```

## disassembly

```asm
0x180023358  mov     [rsp+arg_0], rcx
0x18002335d  push    rbx
0x18002335e  sub     rsp, 20h
0x180023362  mov     rbx, rcx
0x180023365  lea     rax, ??_7CDlgConfigureFriendlyName@@6B@; const CDlgConfigureFriendlyName::`vftable'
0x18002336c  mov     [rcx], rax
0x18002336f  mov     rcx, [rcx+48h]; hMem
0x180023373  call    cs:__imp_LocalFree
0x180023379  nop
0x18002337a  mov     rcx, rbx
0x18002337d  add     rsp, 20h
0x180023381  pop     rbx
0x180023382  jmp     ??1?$CWindowImplRoot@V?$CListViewCtrlT@VCWindow@ATL@@@WTL@@@ATL@@UEAA@XZ; ATL::CWindowImplRoot<WTL::CListViewCtrlT<ATL::CWindow>>::~CWindowImplRoot<WTL::CListViewCtrlT<ATL::CWindow>>(void)
```
