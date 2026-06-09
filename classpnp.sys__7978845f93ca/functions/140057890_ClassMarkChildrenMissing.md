# ClassMarkChildrenMissing

- ea: `0x140057890`
- end: `0x1400578d5`
- name: `ClassMarkChildrenMissing`
- size: `69`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION Fdo)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400231f0`

## callees

- `0x140023110`
- `0x1400559f0`
- `0x140057820`
- `0x140057890`

## pseudocode

```c
void __stdcall ClassMarkChildrenMissing(PFUNCTIONAL_DEVICE_EXTENSION Fdo)
{
  _PHYSICAL_DEVICE_EXTENSION *ChildList; // rbx
  struct _PHYSICAL_DEVICE_EXTENSION *v3; // rcx

  ChildList = Fdo->CommonExtension.ChildList;
  ClassAcquireChildLock(Fdo);
  while ( ChildList )
  {
    v3 = ChildList;
    ChildList = ChildList->CommonExtension.ChildList;
    ClassMarkChildMissing(v3, 0);
  }
  ClassReleaseChildLock(Fdo);
}

```

## disassembly

```asm
0x140057890  mov     [rsp+arg_0], rbx
0x140057895  push    rdi
0x140057896  sub     rsp, 20h
0x14005789a  mov     rbx, [rcx+80h]
0x1400578a1  mov     rdi, rcx
0x1400578a4  call    ClassAcquireChildLock
0x1400578a9  jmp     short loc_1400578BC
0x1400578ab  mov     rcx, rbx; PdoExtension
0x1400578ae  xor     edx, edx; AcquireChildLock
0x1400578b0  mov     rbx, [rbx+80h]
0x1400578b7  call    ClassMarkChildMissing
0x1400578bc  test    rbx, rbx
0x1400578bf  jnz     short loc_1400578AB
0x1400578c1  mov     rcx, rdi; FdoExtension
0x1400578c4  call    ClassReleaseChildLock
0x1400578c9  mov     rbx, [rsp+28h+arg_0]
0x1400578ce  add     rsp, 20h
0x1400578d2  pop     rdi
0x1400578d3  retn
```
