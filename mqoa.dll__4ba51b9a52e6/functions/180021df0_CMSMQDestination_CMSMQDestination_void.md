# CMSMQDestination::~CMSMQDestination(void)

- ea: `0x180021df0`
- end: `0x180021e4c`
- name: `??1CMSMQDestination@@UEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CMSMQDestination *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000aab0`
- `0x18000ae20`
- `0x18000b480`

## callees

- `0x1800033ec`
- `0x180003848`
- `0x180021e60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180021e2e`
- `KERNEL32!DeleteCriticalSection` at `0x180021e2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e09`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e16`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e23`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e09`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e16`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQDestination::~CMSMQDestination(CMSMQDestination *this)
{
  CMSMQDestination::Close((CMSMQDestination *)((char *)this + 8));
  SysFreeString(*((BSTR *)this + 18));
  SysFreeString(*((BSTR *)this + 16));
  SysFreeString(*((BSTR *)this + 17));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  R<IADs>::~R<IADs>((char *)this + 80);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQDestination *)((char *)this + 32));
}

```

## disassembly

```asm
0x180021df0  push    rbx
0x180021df2  sub     rsp, 20h
0x180021df6  mov     rbx, rcx
0x180021df9  add     rcx, 8; this
0x180021dfd  call    ?Close@CMSMQDestination@@UEAAJXZ; CMSMQDestination::Close(void)
0x180021e02  mov     rcx, [rbx+90h]; bstrString
0x180021e09  call    cs:__imp_SysFreeString
0x180021e0f  mov     rcx, [rbx+80h]; bstrString
0x180021e16  call    cs:__imp_SysFreeString
0x180021e1c  mov     rcx, [rbx+88h]; bstrString
0x180021e23  call    cs:__imp_SysFreeString
0x180021e29  nop
0x180021e2a  lea     rcx, [rbx+58h]; lpCriticalSection
0x180021e2e  call    cs:__imp_DeleteCriticalSection
0x180021e34  nop
0x180021e35  lea     rcx, [rbx+50h]
0x180021e39  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x180021e3e  lea     rcx, [rbx+20h]; this
0x180021e42  add     rsp, 20h
0x180021e46  pop     rbx
0x180021e47  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
