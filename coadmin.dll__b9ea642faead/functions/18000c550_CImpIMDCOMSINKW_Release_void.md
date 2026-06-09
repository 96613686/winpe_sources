# CImpIMDCOMSINKW::Release(void)

- ea: `0x18000c550`
- end: `0x18000c57f`
- name: `?Release@CImpIMDCOMSINKW@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CImpIMDCOMSINKW *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800010a4`
- `0x18000c550`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::Release(CImpIMDCOMSINKW *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CImpIMDCOMSINKW::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x18000c550  push    rbx
0x18000c552  sub     rsp, 20h
0x18000c556  or      ebx, 0FFFFFFFFh
0x18000c559  lock xadd [rcx+10h], ebx
0x18000c55e  sub     ebx, 1
0x18000c561  jnz     short loc_18000C577
0x18000c563  test    rcx, rcx
0x18000c566  jz      short loc_18000C577
0x18000c568  lea     rax, ??_7CImpIMDCOMSINKW@@6B@; const CImpIMDCOMSINKW::`vftable'
0x18000c56f  mov     [rcx], rax
0x18000c572  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c577  mov     eax, ebx
0x18000c579  add     rsp, 20h
0x18000c57d  pop     rbx
0x18000c57e  retn
```
