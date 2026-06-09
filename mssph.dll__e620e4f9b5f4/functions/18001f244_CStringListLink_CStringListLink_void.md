# CStringListLink::~CStringListLink(void)

- ea: `0x18001f244`
- end: `0x18001f267`
- name: `??1CStringListLink@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CStringListLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f388`

## callees

- `0x18001f244`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f25c`

## pseudocode

```c
void __fastcall CStringListLink::~CStringListLink(CStringListLink *this)
{
  void *v1; // rax

  v1 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18001f244  sub     rsp, 28h
0x18001f248  mov     rax, [rcx+18h]
0x18001f24c  mov     qword ptr [rcx+18h], 0
0x18001f254  test    rax, rax
0x18001f257  jz      short loc_18001F262
0x18001f259  mov     rcx, rax; pv
0x18001f25c  call    cs:__imp_CoTaskMemFree
0x18001f262  add     rsp, 28h
0x18001f266  retn
```
