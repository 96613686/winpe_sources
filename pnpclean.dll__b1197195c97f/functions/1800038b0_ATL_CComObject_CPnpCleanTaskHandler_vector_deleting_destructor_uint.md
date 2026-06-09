# ATL::CComObject<CPnpCleanTaskHandler>::`vector deleting destructor'(uint)

- ea: `0x1800038b0`
- end: `0x180003906`
- name: `??_E?$CComObject@VCPnpCleanTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: `CWinTaskHandler *__fastcall(CWinTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001160`
- `0x18000383c`
- `0x1800038b0`
- `0x18000a010`

## pseudocode

```c
CWinTaskHandler *__fastcall ATL::CComObject<CPnpCleanTaskHandler>::`vector deleting destructor'(
        CWinTaskHandler *this,
        char a2)
{
  *((_DWORD *)this + 14) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CPnpCleanTaskHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800038b0  mov     [rsp+arg_0], rbx
0x1800038b5  push    rdi
0x1800038b6  sub     rsp, 20h
0x1800038ba  mov     dword ptr [rcx+38h], 0C0000001h
0x1800038c1  lea     rax, ??_7?$CComObject@VCPnpCleanTaskHandler@@@ATL@@6B@; const ATL::CComObject<CPnpCleanTaskHandler>::`vftable'
0x1800038c8  mov     [rcx], rax
0x1800038cb  mov     rdi, rcx
0x1800038ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800038d5  mov     ebx, edx
0x1800038d7  mov     rax, [rcx]
0x1800038da  mov     rax, [rax+10h]
0x1800038de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e3  mov     rcx, rdi; this
0x1800038e6  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800038eb  test    bl, 1
0x1800038ee  jz      short loc_1800038F8
0x1800038f0  mov     rcx, rdi; Block
0x1800038f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038f8  mov     rbx, [rsp+28h+arg_0]
0x1800038fd  mov     rax, rdi
0x180003900  add     rsp, 20h
0x180003904  pop     rdi
0x180003905  retn
```
