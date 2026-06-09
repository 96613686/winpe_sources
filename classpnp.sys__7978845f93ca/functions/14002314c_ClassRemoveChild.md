# ClassRemoveChild

- ea: `0x14002314c`
- end: `0x1400231de`
- name: `ClassRemoveChild`
- size: `146`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400231f0`
- `0x140057820`

## callees

- `0x140023110`
- `0x14002314c`
- `0x1400559f0`

## pseudocode

```c
_PHYSICAL_DEVICE_EXTENSION *__fastcall ClassRemoveChild(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        _PHYSICAL_DEVICE_EXTENSION *a2,
        char a3)
{
  _PHYSICAL_DEVICE_EXTENSION *v6; // rbx
  PFUNCTIONAL_DEVICE_EXTENSION v7; // rax
  _PHYSICAL_DEVICE_EXTENSION *ChildList; // rcx

  if ( a3 )
    ClassAcquireChildLock(FdoExtension);
  if ( !FdoExtension->CommonExtension.ChildList )
    goto LABEL_4;
  v7 = FdoExtension;
  if ( !a2 )
    goto LABEL_9;
  do
  {
    ChildList = v7->CommonExtension.ChildList;
    if ( ChildList == a2 )
      break;
    v7 = (PFUNCTIONAL_DEVICE_EXTENSION)v7->CommonExtension.ChildList;
  }
  while ( ChildList );
  if ( v7 )
  {
LABEL_9:
    v6 = v7->CommonExtension.ChildList;
    v7->CommonExtension.ChildList = v6->CommonExtension.ChildList;
    v6->CommonExtension.ChildList = 0;
  }
  else
  {
LABEL_4:
    v6 = 0;
  }
  if ( a3 )
    ClassReleaseChildLock(FdoExtension);
  return v6;
}

```

## disassembly

```asm
0x14002314c  mov     [rsp+arg_0], rbx
0x140023151  mov     [rsp+arg_8], rsi
0x140023156  push    rdi
0x140023157  sub     rsp, 20h
0x14002315b  mov     sil, r8b
0x14002315e  mov     rbx, rdx
0x140023161  mov     rdi, rcx
0x140023164  test    r8b, r8b
0x140023167  jz      short loc_14002316E
0x140023169  call    ClassAcquireChildLock
0x14002316e  cmp     qword ptr [rdi+80h], 0
0x140023176  jnz     short loc_14002317C
0x140023178  xor     ebx, ebx
0x14002317a  jmp     short loc_1400231BD
0x14002317c  mov     rax, rdi
0x14002317f  test    rbx, rbx
0x140023182  jz      short loc_14002319D
0x140023184  mov     rcx, [rax+80h]
0x14002318b  cmp     rcx, rbx
0x14002318e  jz      short loc_140023198
0x140023190  mov     rax, rcx
0x140023193  test    rcx, rcx
0x140023196  jnz     short loc_140023184
0x140023198  test    rax, rax
0x14002319b  jz      short loc_140023178
0x14002319d  mov     rbx, [rax+80h]
0x1400231a4  mov     rcx, [rbx+80h]
0x1400231ab  mov     [rax+80h], rcx
0x1400231b2  mov     qword ptr [rbx+80h], 0
0x1400231bd  test    sil, sil
0x1400231c0  jz      short loc_1400231CA
0x1400231c2  mov     rcx, rdi; FdoExtension
0x1400231c5  call    ClassReleaseChildLock
0x1400231ca  mov     rsi, [rsp+28h+arg_8]
0x1400231cf  mov     rax, rbx
0x1400231d2  mov     rbx, [rsp+28h+arg_0]
0x1400231d7  add     rsp, 20h
0x1400231db  pop     rdi
0x1400231dc  retn
```
