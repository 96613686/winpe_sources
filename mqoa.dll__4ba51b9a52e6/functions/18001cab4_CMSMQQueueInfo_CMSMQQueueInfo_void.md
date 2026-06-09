# CMSMQQueueInfo::~CMSMQQueueInfo(void)

- ea: `0x18001cab4`
- end: `0x18001cb43`
- name: `??1CMSMQQueueInfo@@UEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CMSMQQueueInfo *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ac18`
- `0x18000b008`
- `0x18000b5c0`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x180003848`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001cb25`
- `KERNEL32!DeleteCriticalSection` at `0x18001cb25`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cac4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cad1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cade`
- `OLEAUT32!__imp_SysFreeString` at `0x18001caeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001caf8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb05`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cac4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cad1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cade`
- `OLEAUT32!__imp_SysFreeString` at `0x18001caeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001caf8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQQueueInfo::~CMSMQQueueInfo(CMSMQQueueInfo *this)
{
  SysFreeString(*((BSTR *)this + 29));
  SysFreeString(*((BSTR *)this + 20));
  SysFreeString(*((BSTR *)this + 22));
  SysFreeString(*((BSTR *)this + 17));
  SysFreeString(*((BSTR *)this + 18));
  SysFreeString(*((BSTR *)this + 19));
  operator delete(*((void **)this + 15));
  operator delete(*((void **)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  R<IADs>::~R<IADs>((char *)this + 72);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQQueueInfo *)((char *)this + 24));
}

```

## disassembly

```asm
0x18001cab4  push    rbx
0x18001cab6  sub     rsp, 20h
0x18001caba  mov     rbx, rcx
0x18001cabd  mov     rcx, [rcx+0E8h]; bstrString
0x18001cac4  call    cs:__imp_SysFreeString
0x18001caca  mov     rcx, [rbx+0A0h]; bstrString
0x18001cad1  call    cs:__imp_SysFreeString
0x18001cad7  mov     rcx, [rbx+0B0h]; bstrString
0x18001cade  call    cs:__imp_SysFreeString
0x18001cae4  mov     rcx, [rbx+88h]; bstrString
0x18001caeb  call    cs:__imp_SysFreeString
0x18001caf1  mov     rcx, [rbx+90h]; bstrString
0x18001caf8  call    cs:__imp_SysFreeString
0x18001cafe  mov     rcx, [rbx+98h]; bstrString
0x18001cb05  call    cs:__imp_SysFreeString
0x18001cb0b  mov     rcx, [rbx+78h]; Block
0x18001cb0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb14  mov     rcx, [rbx+80h]; Block
0x18001cb1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb20  nop
0x18001cb21  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001cb25  call    cs:__imp_DeleteCriticalSection
0x18001cb2b  nop
0x18001cb2c  lea     rcx, [rbx+48h]
0x18001cb30  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18001cb35  lea     rcx, [rbx+18h]; this
0x18001cb39  add     rsp, 20h
0x18001cb3d  pop     rbx
0x18001cb3e  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
