# CMSMQManagement::~CMSMQManagement(void)

- ea: `0x180022974`
- end: `0x1800229c9`
- name: `??1CMSMQManagement@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CMSMQManagement *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab18`
- `0x18000aed0`
- `0x18000b500`

## callees

- `0x1800033ec`
- `0x180003848`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800229ab`
- `KERNEL32!DeleteCriticalSection` at `0x1800229ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180022984`
- `OLEAUT32!__imp_SysFreeString` at `0x180022992`
- `OLEAUT32!__imp_SysFreeString` at `0x1800229a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180022984`
- `OLEAUT32!__imp_SysFreeString` at `0x180022992`
- `OLEAUT32!__imp_SysFreeString` at `0x1800229a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQManagement::~CMSMQManagement(CMSMQManagement *this)
{
  SysFreeString(*((BSTR *)this + 20));
  SysFreeString(*((BSTR *)this + 19));
  SysFreeString(*((BSTR *)this + 18));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  R<IADs>::~R<IADs>((char *)this + 88);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQManagement *)((char *)this + 40));
}

```

## disassembly

```asm
0x180022974  push    rbx
0x180022976  sub     rsp, 20h
0x18002297a  mov     rbx, rcx
0x18002297d  mov     rcx, [rcx+0A0h]; bstrString
0x180022984  call    cs:__imp_SysFreeString
0x18002298a  nop
0x18002298b  mov     rcx, [rbx+98h]; bstrString
0x180022992  call    cs:__imp_SysFreeString
0x180022998  nop
0x180022999  mov     rcx, [rbx+90h]; bstrString
0x1800229a0  call    cs:__imp_SysFreeString
0x1800229a6  nop
0x1800229a7  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800229ab  call    cs:__imp_DeleteCriticalSection
0x1800229b1  nop
0x1800229b2  lea     rcx, [rbx+58h]
0x1800229b6  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x1800229bb  lea     rcx, [rbx+28h]; this
0x1800229bf  add     rsp, 20h
0x1800229c3  pop     rbx
0x1800229c4  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
