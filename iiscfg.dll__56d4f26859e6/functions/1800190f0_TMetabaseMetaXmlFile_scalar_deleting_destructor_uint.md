# TMetabaseMetaXmlFile::`scalar deleting destructor'(uint)

- ea: `0x1800190f0`
- end: `0x180019120`
- name: `??_GTMetabaseMetaXmlFile@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x18001565c`
- `0x1800190f0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001910c`
- `ole32!CoTaskMemFree` at `0x18001910c`

## pseudocode

```c
TMetabaseMetaXmlFile *__fastcall TMetabaseMetaXmlFile::`scalar deleting destructor'(
        TMetabaseMetaXmlFile *this,
        char a2)
{
  TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800190f0  mov     [rsp+arg_0], rbx
0x1800190f5  push    rdi
0x1800190f6  sub     rsp, 20h
0x1800190fa  mov     ebx, edx
0x1800190fc  mov     rdi, rcx
0x1800190ff  call    ??1TMetabaseMetaXmlFile@@UEAA@XZ; TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile(void)
0x180019104  test    bl, 1
0x180019107  jz      short loc_180019112
0x180019109  mov     rcx, rdi; pv
0x18001910c  call    cs:__imp_CoTaskMemFree
0x180019112  mov     rax, rdi
0x180019115  mov     rbx, [rsp+28h+arg_0]
0x18001911a  add     rsp, 20h
0x18001911e  pop     rdi
0x18001911f  retn
```
