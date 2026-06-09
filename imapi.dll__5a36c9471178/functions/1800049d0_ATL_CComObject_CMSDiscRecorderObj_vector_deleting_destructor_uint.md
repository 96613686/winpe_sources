# ATL::CComObject<CMSDiscRecorderObj>::`vector deleting destructor'(uint)

- ea: `0x1800049d0`
- end: `0x180004a31`
- name: `??_E?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAPEAXI@Z`
- size: `97`
- prototype: `__int64 __fastcall(CMSDiscRecorderObj *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x1800049d0`
- `0x18000e8d0`
- `0x180019010`

## pseudocode

```c
CMSDiscRecorderObj *__fastcall ATL::CComObject<CMSDiscRecorderObj>::`vector deleting destructor'(
        CMSDiscRecorderObj *this,
        char a2)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMSDiscRecorderObj::~CMSDiscRecorderObj(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800049d0  mov     [rsp+arg_0], rbx
0x1800049d5  push    rdi
0x1800049d6  sub     rsp, 20h
0x1800049da  mov     dword ptr [rcx+10h], 0C0000001h
0x1800049e1  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'}
0x1800049e8  mov     [rcx], rax
0x1800049eb  mov     rdi, rcx
0x1800049ee  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BIDiscRecorder@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'}
0x1800049f5  mov     ebx, edx
0x1800049f7  mov     [rcx+8], rax
0x1800049fb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a02  mov     rax, [rcx]
0x180004a05  mov     rax, [rax+10h]
0x180004a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0e  mov     rcx, rdi; this
0x180004a11  call    ??1CMSDiscRecorderObj@@QEAA@XZ; CMSDiscRecorderObj::~CMSDiscRecorderObj(void)
0x180004a16  test    bl, 1
0x180004a19  jz      short loc_180004A23
0x180004a1b  mov     rcx, rdi; Block
0x180004a1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004a23  mov     rbx, [rsp+28h+arg_0]
0x180004a28  mov     rax, rdi
0x180004a2b  add     rsp, 20h
0x180004a2f  pop     rdi
0x180004a30  retn
```
