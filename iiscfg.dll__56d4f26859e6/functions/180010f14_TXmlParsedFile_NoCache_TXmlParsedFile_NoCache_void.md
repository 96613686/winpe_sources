# TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache(void)

- ea: `0x180010f14`
- end: `0x180010f49`
- name: `??1TXmlParsedFile_NoCache@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(TXmlParsedFile_NoCache *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000593c`
- `0x180010f80`
- `0x180017e84`
- `0x18002ed95`

## callees

- `0x180005870`
- `0x1800116c8`

## pseudocode

```c
void __fastcall TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache(LPVOID *this)
{
  *this = &TXmlParsedFile_NoCache::`vftable';
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(this + 9);
  TFileMapping::Unload((TFileMapping *)(this + 2));
  *this = &_unknown<IXMLNodeFactory>::`vftable';
}

```

## disassembly

```asm
0x180010f14  push    rbx
0x180010f16  sub     rsp, 20h
0x180010f1a  lea     rax, ??_7TXmlParsedFile_NoCache@@6B@; const TXmlParsedFile_NoCache::`vftable'
0x180010f21  mov     rbx, rcx
0x180010f24  mov     [rcx], rax
0x180010f27  add     rcx, 48h ; 'H'; void *
0x180010f2b  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180010f30  lea     rcx, [rbx+10h]; this
0x180010f34  call    ?Unload@TFileMapping@@QEAAJXZ; TFileMapping::Unload(void)
0x180010f39  lea     rax, ??_7?$_unknown@UIXMLNodeFactory@@@@6B@; const _unknown<IXMLNodeFactory>::`vftable'
0x180010f40  mov     [rbx], rax
0x180010f43  add     rsp, 20h
0x180010f47  pop     rbx
0x180010f48  retn
```
