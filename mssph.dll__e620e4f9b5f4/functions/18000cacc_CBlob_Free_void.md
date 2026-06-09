# CBlob::Free(void)

- ea: `0x18000cacc`
- end: `0x18000cb00`
- name: `?Free@CBlob@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022700`
- `0x180022cc8`

## callees

- `0x18000cacc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cadf`

## pseudocode

```c
void __fastcall CBlob::Free(LPVOID *this)
{
  if ( *((_DWORD *)this + 2) )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
    *((_DWORD *)this + 2) = 0;
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000cacc  push    rbx
0x18000cace  sub     rsp, 20h
0x18000cad2  cmp     dword ptr [rcx+8], 0
0x18000cad6  mov     rbx, rcx
0x18000cad9  jz      short loc_18000CAFA
0x18000cadb  mov     rcx, [rcx+10h]; pv
0x18000cadf  call    cs:__imp_CoTaskMemFree
0x18000cae5  mov     qword ptr [rbx+10h], 0
0x18000caed  mov     dword ptr [rbx+8], 0
0x18000caf4  mov     dword ptr [rbx], 0
0x18000cafa  add     rsp, 20h
0x18000cafe  pop     rbx
0x18000caff  retn
```
