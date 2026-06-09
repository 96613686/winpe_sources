# _attribute_t::FreeValue(void)

- ea: `0x18000d4d0`
- end: `0x18000d518`
- name: `?FreeValue@_attribute_t@@QEAAXXZ`
- size: `72`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d42c`
- `0x18000f17c`
- `0x18000f1c8`

## callees

- `0x18000d4d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4fd`

## pseudocode

```c
void __fastcall _attribute_t::FreeValue(LPVOID *this)
{
  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x18000d4d0  push    rbx
0x18000d4d2  sub     rsp, 20h
0x18000d4d6  cmp     dword ptr [rcx+8], 0Ah
0x18000d4da  mov     rbx, rcx
0x18000d4dd  jnz     short loc_18000D4F3
0x18000d4df  mov     rcx, [rcx+10h]; pv
0x18000d4e3  call    cs:__imp_CoTaskMemFree
0x18000d4e9  mov     qword ptr [rbx+10h], 0
0x18000d4f1  jmp     short loc_18000D512
0x18000d4f3  cmp     dword ptr [rcx+8], 0Eh
0x18000d4f7  jnz     short loc_18000D512
0x18000d4f9  mov     rcx, [rcx+18h]; pv
0x18000d4fd  call    cs:__imp_CoTaskMemFree
0x18000d503  mov     qword ptr [rbx+18h], 0
0x18000d50b  mov     dword ptr [rbx+10h], 0
0x18000d512  add     rsp, 20h
0x18000d516  pop     rbx
0x18000d517  retn
```
