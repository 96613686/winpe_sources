# CError::`scalar deleting destructor'(uint)

- ea: `0x1000ecc0`
- end: `0x1000ecfa`
- name: `??_GCError@@QAEPAXI@Z`
- size: `58`
- prototype: `void *__thiscall(CError *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000f8a0`

## callees

- `0x1000ecc0`
- `0x1004cea1`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1000ece5`
- `KERNEL32!DeleteCriticalSection` at `0x1000ece5`

## pseudocode

```c
CError *__thiscall CError::`scalar deleting destructor'(CError *this, unsigned int a2)
{
  _DWORD *v3; // eax

  v3 = (_DWORD *)*((_DWORD *)this + 3);
  *(_DWORD *)this = &CError::`vftable';
  if ( v3 )
  {
    *v3 = &CImpIErrorLookup::`vftable';
    operator delete(v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1000ecc0  mov     edi, edi
0x1000ecc2  push    esi
0x1000ecc3  mov     esi, ecx
0x1000ecc5  mov     eax, [esi+0Ch]
0x1000ecc8  mov     dword ptr [esi], offset ??_7CError@@6B@; const CError::`vftable'
0x1000ecce  test    eax, eax
0x1000ecd0  jz      short loc_1000ECE1
0x1000ecd2  push    eax; Block
0x1000ecd3  mov     dword ptr [eax], offset ??_7CImpIErrorLookup@@6B@; const CImpIErrorLookup::`vftable'
0x1000ecd9  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000ecde  add     esp, 4
0x1000ece1  lea     eax, [esi+10h]
0x1000ece4  push    eax; lpCriticalSection
0x1000ece5  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000eceb  push    esi; Block
0x1000ecec  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000ecf1  add     esp, 4
0x1000ecf4  mov     eax, esi
0x1000ecf6  pop     esi
0x1000ecf7  retn    4
```
