# SmartPtr<CWorkerThread>::~SmartPtr<CWorkerThread>(void)

- ea: `0x18000ee10`
- end: `0x18000ee26`
- name: `??1?$SmartPtr@VCWorkerThread@@@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee2c`

## callees

- `0x18000ee10`
- `0x18000f11c`

## pseudocode

```c
__int64 __fastcall SmartPtr<CWorkerThread>::~SmartPtr<CWorkerThread>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs();
  return result;
}

```

## disassembly

```asm
0x18000ee10  sub     rsp, 28h
0x18000ee14  mov     rcx, [rcx]
0x18000ee17  test    rcx, rcx
0x18000ee1a  jz      short loc_18000EE21
0x18000ee1c  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCWorkerThread@@@@QEAAHXZ; SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs(void)
0x18000ee21  add     rsp, 28h
0x18000ee25  retn
```
