# CDynamicCountedObjectArray::Remove(ulong)

- ea: `0x180005ee0`
- end: `0x180005f1d`
- name: `?Remove@CDynamicCountedObjectArray@@UEAAHK@Z`
- size: `61`
- prototype: `__int64 __fastcall(CDynamicCountedObjectArray *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004dc4`
- `0x180005da0`
- `0x180005ee0`

## pseudocode

```c
__int64 __fastcall CDynamicCountedObjectArray::Remove(CDynamicCountedObjectArray *this, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 result; // rax
  __int64 v4; // rdx

  v2 = a2;
  result = 0;
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    if ( (unsigned int)v2 < *((_DWORD *)this + 4) )
    {
      CCountedObject::Release(*(CCountedObject **)(v4 + 8 * v2));
      return CDynamicArray::Remove(this, v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005ee0  mov     [rsp+arg_0], rbx
0x180005ee5  push    rdi
0x180005ee6  sub     rsp, 20h
0x180005eea  mov     edi, edx
0x180005eec  xor     eax, eax
0x180005eee  mov     rdx, [rcx+18h]
0x180005ef2  mov     rbx, rcx
0x180005ef5  test    rdx, rdx
0x180005ef8  jz      short loc_180005F12
0x180005efa  cmp     edi, [rcx+10h]
0x180005efd  jnb     short loc_180005F12
0x180005eff  mov     rcx, [rdx+rdi*8]; this
0x180005f03  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180005f08  mov     edx, edi; unsigned int
0x180005f0a  mov     rcx, rbx; this
0x180005f0d  call    ?Remove@CDynamicArray@@UEAAHK@Z; CDynamicArray::Remove(ulong)
0x180005f12  mov     rbx, [rsp+28h+arg_0]
0x180005f17  add     rsp, 20h
0x180005f1b  pop     rdi
0x180005f1c  retn
```
