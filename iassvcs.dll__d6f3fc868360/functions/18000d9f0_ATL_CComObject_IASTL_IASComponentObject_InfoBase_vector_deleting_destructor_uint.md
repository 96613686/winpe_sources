# ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vector deleting destructor'(uint)

- ea: `0x18000d9f0`
- end: `0x18000da5b`
- name: `??_E?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@UEAAPEAXI@Z`
- size: `107`
- prototype: `IASTL::IASComponent *__fastcall(IASTL::IASComponent *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d904`
- `0x18000d9f0`
- `0x180016474`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000da47`
- `msvcrt!free` at `0x18000da47`

## pseudocode

```c
IASTL::IASComponent *__fastcall ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vector deleting destructor'(
        IASTL::IASComponent *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IASTL::IASComponent'};
  *((_QWORD *)this + 9) = &ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IAuditSink'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  InfoShare::~InfoShare((IASTL::IASComponent *)((char *)this + 80));
  IASTL::IASComponent::~IASComponent(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000d9f0  mov     [rsp+arg_0], rbx
0x18000d9f5  push    rdi
0x18000d9f6  sub     rsp, 20h
0x18000d9fa  mov     dword ptr [rcx+8], 0C0000001h
0x18000da01  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@6BIASComponent@IASTL@@@; const ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IASTL::IASComponent'}
0x18000da08  mov     [rcx], rax
0x18000da0b  mov     rdi, rcx
0x18000da0e  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IAuditSink'}
0x18000da15  mov     ebx, edx
0x18000da17  mov     [rcx+48h], rax
0x18000da1b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000da22  mov     rax, [rcx]
0x18000da25  mov     rax, [rax+10h]
0x18000da29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da2e  lea     rcx, [rdi+50h]; this
0x18000da32  call    ??1InfoShare@@QEAA@XZ; InfoShare::~InfoShare(void)
0x18000da37  mov     rcx, rdi; this
0x18000da3a  call    ??1IASComponent@IASTL@@QEAA@XZ; IASTL::IASComponent::~IASComponent(void)
0x18000da3f  test    bl, 1
0x18000da42  jz      short loc_18000DA4D
0x18000da44  mov     rcx, rdi; Block
0x18000da47  call    cs:__imp_free
0x18000da4d  mov     rbx, [rsp+28h+arg_0]
0x18000da52  mov     rax, rdi
0x18000da55  add     rsp, 20h
0x18000da59  pop     rdi
0x18000da5a  retn
```
