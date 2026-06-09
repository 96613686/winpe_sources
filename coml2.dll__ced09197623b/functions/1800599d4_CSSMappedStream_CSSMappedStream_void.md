# CSSMappedStream::~CSSMappedStream(void)

- ea: `0x1800599d4`
- end: `0x180059a0c`
- name: `??1CSSMappedStream@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CSSMappedStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059b10`

## callees

- `0x1800599d4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800599eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800599eb`

## pseudocode

```c
void __fastcall CSSMappedStream::~CSSMappedStream(LPVOID *this)
{
  LPVOID v2; // rcx

  *this = &CSSMappedStream::`vftable';
  CoTaskMemFree(this[3]);
  v2 = this[2];
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x1800599d4  push    rbx
0x1800599d6  sub     rsp, 20h
0x1800599da  lea     rax, ??_7CSSMappedStream@@6B@; const CSSMappedStream::`vftable'
0x1800599e1  mov     rbx, rcx
0x1800599e4  mov     [rcx], rax
0x1800599e7  mov     rcx, [rcx+18h]; pv
0x1800599eb  call    cs:__imp_CoTaskMemFree
0x1800599f1  mov     rcx, [rbx+10h]
0x1800599f5  test    rcx, rcx
0x1800599f8  jz      short loc_180059A06
0x1800599fa  mov     rax, [rcx]
0x1800599fd  mov     rax, [rax+10h]
0x180059a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a06  add     rsp, 20h
0x180059a0a  pop     rbx
0x180059a0b  retn
```
