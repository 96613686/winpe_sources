# TXmlParsedFile_NoCache::`scalar deleting destructor'(uint)

- ea: `0x180010f80`
- end: `0x180010fb0`
- name: `??_GTXmlParsedFile_NoCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TXmlParsedFile_NoCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180010f14`
- `0x180010f80`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010f9c`
- `ole32!CoTaskMemFree` at `0x180010f9c`

## pseudocode

```c
TXmlParsedFile_NoCache *__fastcall TXmlParsedFile_NoCache::`scalar deleting destructor'(
        TXmlParsedFile_NoCache *this,
        char a2)
{
  TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180010f80  mov     [rsp+arg_0], rbx
0x180010f85  push    rdi
0x180010f86  sub     rsp, 20h
0x180010f8a  mov     ebx, edx
0x180010f8c  mov     rdi, rcx
0x180010f8f  call    ??1TXmlParsedFile_NoCache@@UEAA@XZ; TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache(void)
0x180010f94  test    bl, 1
0x180010f97  jz      short loc_180010FA2
0x180010f99  mov     rcx, rdi; pv
0x180010f9c  call    cs:__imp_CoTaskMemFree
0x180010fa2  mov     rbx, [rsp+28h+arg_0]
0x180010fa7  mov     rax, rdi
0x180010faa  add     rsp, 20h
0x180010fae  pop     rdi
0x180010faf  retn
```
