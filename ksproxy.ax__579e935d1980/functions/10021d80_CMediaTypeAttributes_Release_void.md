# CMediaTypeAttributes::Release(void)

- ea: `0x10021d80`
- end: `0x10021db6`
- name: `?Release@CMediaTypeAttributes@@UAGKXZ`
- size: `54`
- prototype: `unsigned int __stdcall(CMediaTypeAttributes *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x10021d80`
- `0x1003af9d`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x10021d9e`
- `ole32!CoTaskMemFree` at `0x10021d9e`

## pseudocode

```c
signed __int32 __stdcall CMediaTypeAttributes::Release(CMediaTypeAttributes *this)
{
  signed __int32 v1; // edi

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 )
  {
    if ( *((_DWORD *)this + 1) )
      CoTaskMemFree(*((LPVOID *)this + 1));
    operator delete(this, 0xCu);
  }
  return v1;
}

```

## disassembly

```asm
0x10021d80  mov     edi, edi
0x10021d82  push    ebp
0x10021d83  mov     ebp, esp
0x10021d85  push    esi
0x10021d86  mov     esi, [ebp+Block]
0x10021d89  push    edi
0x10021d8a  or      edi, 0FFFFFFFFh
0x10021d8d  lock xadd [esi+8], edi
0x10021d92  dec     edi
0x10021d93  jnz     short loc_10021DAE
0x10021d95  cmp     dword ptr [esi+4], 0
0x10021d99  jz      short loc_10021DA4
0x10021d9b  push    dword ptr [esi+4]; pv
0x10021d9e  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10021da4  push    0Ch; unsigned int
0x10021da6  push    esi; Block
0x10021da7  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10021dac  pop     ecx
0x10021dad  pop     ecx
0x10021dae  mov     eax, edi
0x10021db0  pop     edi
0x10021db1  pop     esi
0x10021db2  pop     ebp
0x10021db3  retn    4
```
