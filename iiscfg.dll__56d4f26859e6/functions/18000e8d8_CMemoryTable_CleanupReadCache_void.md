# CMemoryTable::CleanupReadCache(void)

- ea: `0x18000e8d8`
- end: `0x18000e941`
- name: `?CleanupReadCache@CMemoryTable@@AEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CMemoryTable *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e840`
- `0x18000e9d0`

## callees

- `0x18000e8d8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e900`
- `ole32!CoTaskMemFree` at `0x18000e900`

## pseudocode

```c
void __fastcall CMemoryTable::CleanupReadCache(CMemoryTable *this)
{
  void *v2; // rcx

  if ( (*((_DWORD *)this + 8) & 0x1000000) != 0 || (*((_DWORD *)this + 23) & 0x10000) == 0 )
  {
    v2 = (void *)*((_QWORD *)this + 15);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)this + 15) = 0;
    }
    *((_DWORD *)this + 23) &= ~0x10000u;
  }
  *(_QWORD *)((char *)this + 100) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x18000e8d8  mov     [rsp+arg_0], rbx
0x18000e8dd  push    rdi
0x18000e8de  sub     rsp, 20h
0x18000e8e2  test    dword ptr [rcx+20h], 1000000h
0x18000e8e9  mov     rbx, rcx
0x18000e8ec  jnz     short loc_18000E8F7
0x18000e8ee  test    dword ptr [rcx+5Ch], 10000h
0x18000e8f5  jnz     short loc_18000E913
0x18000e8f7  mov     rcx, [rcx+78h]; pv
0x18000e8fb  test    rcx, rcx
0x18000e8fe  jz      short loc_18000E90E
0x18000e900  call    cs:__imp_CoTaskMemFree
0x18000e906  mov     qword ptr [rbx+78h], 0
0x18000e90e  btr     dword ptr [rbx+5Ch], 10h
0x18000e913  mov     qword ptr [rbx+64h], 0
0x18000e91b  mov     qword ptr [rbx+78h], 0
0x18000e923  mov     qword ptr [rbx+70h], 0
0x18000e92b  mov     qword ptr [rbx+80h], 0
0x18000e936  mov     rbx, [rsp+28h+arg_0]
0x18000e93b  add     rsp, 20h
0x18000e93f  pop     rdi
0x18000e940  retn
```
