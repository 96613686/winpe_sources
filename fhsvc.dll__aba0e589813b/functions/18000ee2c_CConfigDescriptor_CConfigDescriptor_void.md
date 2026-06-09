# CConfigDescriptor::~CConfigDescriptor(void)

- ea: `0x18000ee2c`
- end: `0x18000ee6d`
- name: `??1CConfigDescriptor@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CConfigDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ef64`

## callees

- `0x180007644`
- `0x18000ac14`
- `0x18000ee10`
- `0x18000ee2c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ee3e`
- `KERNEL32!CloseHandle` at `0x18000ee3e`

## pseudocode

```c
void __fastcall CConfigDescriptor::~CConfigDescriptor(CConfigDescriptor *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::Empty(this);
  SmartPtr<CWorkerThread>::~SmartPtr<CWorkerThread>((_QWORD *)this + 17);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(this);
}

```

## disassembly

```asm
0x18000ee2c  push    rbx
0x18000ee2e  sub     rsp, 20h
0x18000ee32  mov     rbx, rcx
0x18000ee35  mov     rcx, [rcx+8]; hObject
0x18000ee39  test    rcx, rcx
0x18000ee3c  jz      short loc_18000EE4C
0x18000ee3e  call    cs:__imp_CloseHandle
0x18000ee44  mov     qword ptr [rbx+8], 0
0x18000ee4c  mov     rcx, rbx
0x18000ee4f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000ee54  lea     rcx, [rbx+88h]
0x18000ee5b  call    ??1?$SmartPtr@VCWorkerThread@@@@QEAA@XZ; SmartPtr<CWorkerThread>::~SmartPtr<CWorkerThread>(void)
0x18000ee60  mov     rcx, rbx
0x18000ee63  add     rsp, 20h
0x18000ee67  pop     rbx
0x18000ee68  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
