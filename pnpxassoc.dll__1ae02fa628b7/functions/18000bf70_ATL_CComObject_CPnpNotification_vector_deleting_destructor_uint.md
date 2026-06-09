# ATL::CComObject<CPnpNotification>::`vector deleting destructor'(uint)

- ea: `0x18000bf70`
- end: `0x18000bfc6`
- name: `??_E?$CComObject@VCPnpNotification@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: `__int64 __fastcall(CPnpNotification *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019b0`
- `0x18000bd8c`
- `0x18000bf70`
- `0x180014010`

## pseudocode

```c
CPnpNotification *__fastcall ATL::CComObject<CPnpNotification>::`vector deleting destructor'(
        CPnpNotification *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CPnpNotification>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPnpNotification::~CPnpNotification(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000bf70  mov     [rsp+arg_0], rbx
0x18000bf75  push    rdi
0x18000bf76  sub     rsp, 20h
0x18000bf7a  mov     dword ptr [rcx+8], 0C0000001h
0x18000bf81  lea     rax, ??_7?$CComObject@VCPnpNotification@@@ATL@@6B@; const ATL::CComObject<CPnpNotification>::`vftable'
0x18000bf88  mov     [rcx], rax
0x18000bf8b  mov     rdi, rcx
0x18000bf8e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bf95  mov     ebx, edx
0x18000bf97  mov     rax, [rcx]
0x18000bf9a  mov     rax, [rax+10h]
0x18000bf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa3  mov     rcx, rdi; this
0x18000bfa6  call    ??1CPnpNotification@@QEAA@XZ; CPnpNotification::~CPnpNotification(void)
0x18000bfab  test    bl, 1
0x18000bfae  jz      short loc_18000BFB8
0x18000bfb0  mov     rcx, rdi; Block
0x18000bfb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bfb8  mov     rbx, [rsp+28h+arg_0]
0x18000bfbd  mov     rax, rdi
0x18000bfc0  add     rsp, 20h
0x18000bfc4  pop     rdi
0x18000bfc5  retn
```
