# R<CTransaction>::~R<CTransaction>(void)

- ea: `0x14000d728`
- end: `0x14000d73f`
- name: `??1?$R@VCTransaction@@@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000df10`
- `0x14000df60`
- `0x140010984`
- `0x140012c14`
- `0x140014c48`
- `0x1400184cc`
- `0x140018644`
- `0x14001d320`
- `0x14001d390`

## callees

- `0x14000d728`
- `0x140012754`

## pseudocode

```c
__int64 __fastcall R<CTransaction>::~R<CTransaction>(CBaseObject **a1)
{
  CBaseObject *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return CBaseObject::Release(v1);
  return result;
}

```

## disassembly

```asm
0x14000d728  sub     rsp, 28h
0x14000d72c  mov     rcx, [rcx]; this
0x14000d72f  test    rcx, rcx
0x14000d732  jz      short loc_14000D739
0x14000d734  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000d739  add     rsp, 28h
0x14000d73d  retn
```
