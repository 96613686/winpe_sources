# CMemoryTable::CleanupErrorCache(void)

- ea: `0x18000e870`
- end: `0x18000e8d2`
- name: `?CleanupErrorCache@CMemoryTable@@AEAAXXZ`
- size: `98`
- prototype: `void __fastcall(CMemoryTable *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e840`
- `0x18000e9d0`
- `0x18000ee90`
- `0x18000ff00`

## callees

- `0x18000e870`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e89b`
- `ole32!CoTaskMemFree` at `0x18000e89b`

## pseudocode

```c
void __fastcall CMemoryTable::CleanupErrorCache(CMemoryTable *this)
{
  void *v2; // rcx

  if ( (*((_DWORD *)this + 8) & 0x1000000) != 0 || (*((_DWORD *)this + 23) & 0x40000) == 0 )
  {
    v2 = (void *)*((_QWORD *)this + 22);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)this + 22) = 0;
    }
    *((_DWORD *)this + 23) &= ~0x40000u;
  }
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
}

```

## disassembly

```asm
0x18000e870  mov     [rsp+arg_0], rbx
0x18000e875  push    rdi
0x18000e876  sub     rsp, 20h
0x18000e87a  test    dword ptr [rcx+20h], 1000000h
0x18000e881  mov     rbx, rcx
0x18000e884  jnz     short loc_18000E88F
0x18000e886  test    dword ptr [rcx+5Ch], 40000h
0x18000e88d  jnz     short loc_18000E8B1
0x18000e88f  mov     rcx, [rcx+0B0h]; pv
0x18000e896  test    rcx, rcx
0x18000e899  jz      short loc_18000E8AC
0x18000e89b  call    cs:__imp_CoTaskMemFree
0x18000e8a1  mov     qword ptr [rbx+0B0h], 0
0x18000e8ac  btr     dword ptr [rbx+5Ch], 12h
0x18000e8b1  mov     qword ptr [rbx+0A8h], 0
0x18000e8bc  mov     qword ptr [rbx+0B0h], 0
0x18000e8c7  mov     rbx, [rsp+28h+arg_0]
0x18000e8cc  add     rsp, 20h
0x18000e8d0  pop     rdi
0x18000e8d1  retn
```
