# ATL::CComAggObject<CMSDiscMasterObj>::`scalar deleting destructor'(uint)

- ea: `0x180007f70`
- end: `0x180007fdb`
- name: `??_G?$CComAggObject@VCMSDiscMasterObj@@@ATL@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x180007f70`
- `0x18000b394`
- `0x18000c080`
- `0x180019010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CMSDiscMasterObj>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CMSDiscMasterObj>::`vftable';
  CMSDiscMasterObj::FinalRelease((CMSDiscMasterObj *)(Block + 6));
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMSDiscMasterObj::~CMSDiscMasterObj((CMSDiscMasterObj *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007f70  mov     [rsp+arg_0], rbx
0x180007f75  mov     [rsp+arg_8], rsi
0x180007f7a  push    rdi
0x180007f7b  sub     rsp, 20h
0x180007f7f  lea     rax, ??_7?$CComAggObject@VCMSDiscMasterObj@@@ATL@@6B@; const ATL::CComAggObject<CMSDiscMasterObj>::`vftable'
0x180007f86  mov     dword ptr [rcx+8], 0C0000001h
0x180007f8d  mov     [rcx], rax
0x180007f90  mov     rsi, rcx
0x180007f93  add     rcx, 18h; this
0x180007f97  mov     edi, edx
0x180007f99  call    ?FinalRelease@CMSDiscMasterObj@@QEAAXXZ; CMSDiscMasterObj::FinalRelease(void)
0x180007f9e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007fa5  mov     rax, [rcx]
0x180007fa8  mov     rax, [rax+10h]
0x180007fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb1  lea     rcx, [rsi+18h]; this
0x180007fb5  call    ??1CMSDiscMasterObj@@QEAA@XZ; CMSDiscMasterObj::~CMSDiscMasterObj(void)
0x180007fba  test    dil, 1
0x180007fbe  jz      short loc_180007FC8
0x180007fc0  mov     rcx, rsi; Block
0x180007fc3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007fc8  mov     rbx, [rsp+28h+arg_0]
0x180007fcd  mov     rax, rsi
0x180007fd0  mov     rsi, [rsp+28h+arg_8]
0x180007fd5  add     rsp, 20h
0x180007fd9  pop     rdi
0x180007fda  retn
```
