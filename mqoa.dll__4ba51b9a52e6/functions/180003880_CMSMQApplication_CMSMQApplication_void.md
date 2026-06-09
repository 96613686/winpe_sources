# CMSMQApplication::~CMSMQApplication(void)

- ea: `0x180003880`
- end: `0x1800038b9`
- name: `??1CMSMQApplication@@UEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CMSMQApplication *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aa30`
- `0x18000ad90`
- `0x18000b400`

## callees

- `0x1800033ec`
- `0x180003848`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000389b`
- `KERNEL32!DeleteCriticalSection` at `0x18000389b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003890`
- `OLEAUT32!__imp_SysFreeString` at `0x180003890`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQApplication::~CMSMQApplication(CMSMQApplication *this)
{
  SysFreeString(*((BSTR *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  R<IADs>::~R<IADs>((char *)this + 72);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQApplication *)((char *)this + 24));
}

```

## disassembly

```asm
0x180003880  push    rbx
0x180003882  sub     rsp, 20h
0x180003886  mov     rbx, rcx
0x180003889  mov     rcx, [rcx+80h]; bstrString
0x180003890  call    cs:__imp_SysFreeString
0x180003896  nop
0x180003897  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000389b  call    cs:__imp_DeleteCriticalSection
0x1800038a1  nop
0x1800038a2  lea     rcx, [rbx+48h]
0x1800038a6  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x1800038ab  lea     rcx, [rbx+18h]; this
0x1800038af  add     rsp, 20h
0x1800038b3  pop     rbx
0x1800038b4  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
