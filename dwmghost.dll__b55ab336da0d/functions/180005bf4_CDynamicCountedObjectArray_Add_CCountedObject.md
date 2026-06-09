# CDynamicCountedObjectArray::Add(CCountedObject *)

- ea: `0x180005bf4`
- end: `0x180005c2e`
- name: `?Add@CDynamicCountedObjectArray@@QEAAHPEAVCCountedObject@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(CDynamicCountedObjectArray *this, struct CCountedObject *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007c2c`
- `0x180007d0c`
- `0x1800083e8`
- `0x1800086b8`
- `0x180008eec`

## callees

- `0x180003850`
- `0x180004dc4`
- `0x180005b20`
- `0x180005bf4`

## pseudocode

```c
__int64 __fastcall CDynamicCountedObjectArray::Add(CDynamicCountedObjectArray *this, struct CCountedObject *a2)
{
  CDynamicArray *v2; // rax
  unsigned int v3; // ebx
  CCountedObject *v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  CCountedObject::AddRef(a2);
  v3 = CDynamicArray::Add(v2, &v5);
  if ( !v3 )
    CCountedObject::Release(v5);
  return v3;
}

```

## disassembly

```asm
0x180005bf4  mov     [rsp+arg_8], rdx
0x180005bf9  push    rbx
0x180005bfa  sub     rsp, 20h
0x180005bfe  mov     rax, rcx
0x180005c01  mov     rcx, rdx; this
0x180005c04  call    ?AddRef@CCountedObject@@QEAAXXZ; CCountedObject::AddRef(void)
0x180005c09  lea     rdx, [rsp+28h+arg_8]; void *
0x180005c0e  mov     rcx, rax; this
0x180005c11  call    ?Add@CDynamicArray@@UEAAHPEBX@Z; CDynamicArray::Add(void const *)
0x180005c16  mov     ebx, eax
0x180005c18  test    eax, eax
0x180005c1a  jnz     short loc_180005C26
0x180005c1c  mov     rcx, [rsp+28h+arg_8]; this
0x180005c21  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180005c26  mov     eax, ebx
0x180005c28  add     rsp, 20h
0x180005c2c  pop     rbx
0x180005c2d  retn
```
