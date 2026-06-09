# CMemoryTable::CleanupWriteCache(void)

- ea: `0x18000e948`
- end: `0x18000e9c0`
- name: `?CleanupWriteCache@CMemoryTable@@AEAAXXZ`
- size: `120`
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

- `0x18000e948`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e973`
- `ole32!CoTaskMemFree` at `0x18000e973`

## pseudocode

```c
void __fastcall CMemoryTable::CleanupWriteCache(CMemoryTable *this)
{
  void *v2; // rcx

  if ( (*((_DWORD *)this + 8) & 0x1000000) != 0 || (*((_DWORD *)this + 23) & 0x20000) == 0 )
  {
    v2 = (void *)*((_QWORD *)this + 19);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)this + 19) = 0;
    }
    *((_DWORD *)this + 23) &= ~0x20000u;
  }
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x18000e948  mov     [rsp+arg_0], rbx
0x18000e94d  push    rdi
0x18000e94e  sub     rsp, 20h
0x18000e952  test    dword ptr [rcx+20h], 1000000h
0x18000e959  mov     rbx, rcx
0x18000e95c  jnz     short loc_18000E967
0x18000e95e  test    dword ptr [rcx+5Ch], 20000h
0x18000e965  jnz     short loc_18000E989
0x18000e967  mov     rcx, [rcx+98h]; pv
0x18000e96e  test    rcx, rcx
0x18000e971  jz      short loc_18000E984
0x18000e973  call    cs:__imp_CoTaskMemFree
0x18000e979  mov     qword ptr [rbx+98h], 0
0x18000e984  btr     dword ptr [rbx+5Ch], 11h
0x18000e989  mov     qword ptr [rbx+88h], 0
0x18000e994  mov     qword ptr [rbx+98h], 0
0x18000e99f  mov     qword ptr [rbx+90h], 0
0x18000e9aa  mov     qword ptr [rbx+0A0h], 0
0x18000e9b5  mov     rbx, [rsp+28h+arg_0]
0x18000e9ba  add     rsp, 20h
0x18000e9be  pop     rdi
0x18000e9bf  retn
```
