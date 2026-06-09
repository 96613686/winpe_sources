# CCabItemList::GetState(void)

- ea: `0x18000e848`
- end: `0x18000e85d`
- name: `?GetState@CCabItemList@@QEAAIXZ`
- size: `21`
- prototype: `unsigned int __fastcall(CCabItemList *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b42c`
- `0x18000b884`
- `0x18000c480`
- `0x18000eb9c`
- `0x18000ec68`
- `0x180010c80`

## callees

- `0x18000e848`

## pseudocode

```c
__int64 __fastcall CCabItemList::GetState(CCabItemList *this)
{
  if ( *(_DWORD *)this )
    return 0;
  else
    return 2 - (unsigned int)(*((_QWORD *)this + 1) != 0);
}

```

## disassembly

```asm
0x18000e848  cmp     dword ptr [rcx], 0
0x18000e84b  jnz     short loc_18000E85A
0x18000e84d  mov     rax, [rcx+8]
0x18000e851  neg     rax
0x18000e854  sbb     eax, eax
0x18000e856  add     eax, 2
0x18000e859  retn
0x18000e85a  xor     eax, eax
0x18000e85c  retn
```
