# EapHost::RawBuffer::~RawBuffer(void)

- ea: `0x18000d050`
- end: `0x18000d094`
- name: `??1RawBuffer@EapHost@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(EapHost::RawBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d067`

## pseudocode

```c
void __fastcall EapHost::RawBuffer::~RawBuffer(LPVOID *this)
{
  *this = &EapHost::RawBuffer::`vftable';
  CoTaskMemFree(this[2]);
  this[2] = 0;
  *this = &ReferenceCounted::`vftable';
  this[3] = 0;
}

```

## disassembly

```asm
0x18000d050  push    rbx
0x18000d052  sub     rsp, 20h
0x18000d056  lea     rax, ??_7RawBuffer@EapHost@@6B@; const EapHost::RawBuffer::`vftable'
0x18000d05d  mov     rbx, rcx
0x18000d060  mov     [rcx], rax
0x18000d063  mov     rcx, [rcx+10h]; pv
0x18000d067  call    cs:__imp_CoTaskMemFree
0x18000d06e  nop     dword ptr [rax+rax+00h]
0x18000d073  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18000d07a  mov     qword ptr [rbx+10h], 0
0x18000d082  mov     [rbx], rax
0x18000d085  mov     qword ptr [rbx+18h], 0
0x18000d08d  add     rsp, 20h
0x18000d091  pop     rbx
0x18000d092  retn
```
