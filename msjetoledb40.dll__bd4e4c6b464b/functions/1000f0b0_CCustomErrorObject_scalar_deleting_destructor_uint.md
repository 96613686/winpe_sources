# CCustomErrorObject::`scalar deleting destructor'(uint)

- ea: `0x1000f0b0`
- end: `0x1000f0f8`
- name: `??_GCCustomErrorObject@@QAEPAXI@Z`
- size: `72`
- prototype: `void *__thiscall(CCustomErrorObject *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000f020`

## callees

- `0x1000f0b0`
- `0x1004cea1`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1000f0e3`
- `KERNEL32!DeleteCriticalSection` at `0x1000f0e3`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1000f0d9`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1000f0d9`

## pseudocode

```c
CCustomErrorObject *__thiscall CCustomErrorObject::`scalar deleting destructor'(
        CCustomErrorObject *this,
        unsigned int a2)
{
  _DWORD *v3; // eax

  v3 = (_DWORD *)*((_DWORD *)this + 3);
  *(_DWORD *)this = &CCustomErrorObject::`vftable';
  if ( v3 )
  {
    *v3 = &CImpISQLErrorInfo::`vftable';
    operator delete(v3);
  }
  if ( *((_DWORD *)this + 11) )
    SysFreeString(*((BSTR *)this + 11));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1000f0b0  mov     edi, edi
0x1000f0b2  push    esi
0x1000f0b3  mov     esi, ecx
0x1000f0b5  mov     eax, [esi+0Ch]
0x1000f0b8  mov     dword ptr [esi], offset ??_7CCustomErrorObject@@6B@; const CCustomErrorObject::`vftable'
0x1000f0be  test    eax, eax
0x1000f0c0  jz      short loc_1000F0D1
0x1000f0c2  push    eax; Block
0x1000f0c3  mov     dword ptr [eax], offset ??_7CImpISQLErrorInfo@@6B@; const CImpISQLErrorInfo::`vftable'
0x1000f0c9  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000f0ce  add     esp, 4
0x1000f0d1  mov     eax, [esi+2Ch]
0x1000f0d4  test    eax, eax
0x1000f0d6  jz      short loc_1000F0DF
0x1000f0d8  push    eax; bstrString
0x1000f0d9  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1000f0df  lea     eax, [esi+10h]
0x1000f0e2  push    eax; lpCriticalSection
0x1000f0e3  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000f0e9  push    esi; Block
0x1000f0ea  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000f0ef  add     esp, 4
0x1000f0f2  mov     eax, esi
0x1000f0f4  pop     esi
0x1000f0f5  retn    4
```
