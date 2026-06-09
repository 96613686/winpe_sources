# ATL::CComAggObject<CServiceProvider>::`vector deleting destructor'(uint)

- ea: `0x180005470`
- end: `0x1800054c7`
- name: `??_E?$CComAggObject@VCServiceProvider@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180005470`
- `0x180009990`
- `0x180014010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CServiceProvider>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CServiceProvider>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CServiceProvider::~CServiceProvider((CServiceProvider *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005470  mov     [rsp+arg_0], rbx
0x180005475  push    rdi
0x180005476  sub     rsp, 20h
0x18000547a  mov     dword ptr [rcx+8], 0C0000001h
0x180005481  lea     rax, ??_7?$CComAggObject@VCServiceProvider@@@ATL@@6B@; const ATL::CComAggObject<CServiceProvider>::`vftable'
0x180005488  mov     [rcx], rax
0x18000548b  mov     rdi, rcx
0x18000548e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005495  mov     ebx, edx
0x180005497  mov     rax, [rcx]
0x18000549a  mov     rax, [rax+10h]
0x18000549e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a3  lea     rcx, [rdi+18h]; this
0x1800054a7  call    ??1CServiceProvider@@UEAA@XZ; CServiceProvider::~CServiceProvider(void)
0x1800054ac  test    bl, 1
0x1800054af  jz      short loc_1800054B9
0x1800054b1  mov     rcx, rdi; Block
0x1800054b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800054b9  mov     rbx, [rsp+28h+arg_0]
0x1800054be  mov     rax, rdi
0x1800054c1  add     rsp, 20h
0x1800054c5  pop     rdi
0x1800054c6  retn
```
