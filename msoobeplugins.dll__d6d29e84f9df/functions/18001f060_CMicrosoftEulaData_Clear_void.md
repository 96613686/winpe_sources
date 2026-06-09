# CMicrosoftEulaData::Clear(void)

- ea: `0x18001f060`
- end: `0x18001f0b5`
- name: `?Clear@CMicrosoftEulaData@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(CMicrosoftEulaData *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ea78`
- `0x180021b20`
- `0x180022b9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f06c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f06c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f094`

## pseudocode

```c
void __fastcall CMicrosoftEulaData::Clear(LPVOID *this)
{
  CoTaskMemFree(*this);
  CoTaskMemFree(this[1]);
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[4]);
  *this = 0;
  this[1] = 0;
  this[2] = 0;
  this[3] = 0;
  this[4] = 0;
}

```

## disassembly

```asm
0x18001f060  push    rbx
0x18001f062  sub     rsp, 20h
0x18001f066  mov     rbx, rcx
0x18001f069  mov     rcx, [rcx]; pv
0x18001f06c  call    cs:__imp_CoTaskMemFree
0x18001f072  mov     rcx, [rbx+8]; pv
0x18001f076  call    cs:__imp_CoTaskMemFree
0x18001f07c  mov     rcx, [rbx+10h]; pv
0x18001f080  call    cs:__imp_CoTaskMemFree
0x18001f086  mov     rcx, [rbx+18h]; pv
0x18001f08a  call    cs:__imp_CoTaskMemFree
0x18001f090  mov     rcx, [rbx+20h]; pv
0x18001f094  call    cs:__imp_CoTaskMemFree
0x18001f09a  xor     eax, eax
0x18001f09c  mov     [rbx], rax
0x18001f09f  mov     [rbx+8], rax
0x18001f0a3  mov     [rbx+10h], rax
0x18001f0a7  mov     [rbx+18h], rax
0x18001f0ab  mov     [rbx+20h], rax
0x18001f0af  add     rsp, 20h
0x18001f0b3  pop     rbx
0x18001f0b4  retn
```
