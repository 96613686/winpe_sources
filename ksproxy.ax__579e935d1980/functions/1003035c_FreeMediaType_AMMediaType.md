# FreeMediaType(_AMMediaType &)

- ea: `0x1003035c`
- end: `0x1003037e`
- name: `?FreeMediaType@@YGXAAU_AMMediaType@@@Z`
- size: `34`
- prototype: `void __cdecl(struct _AMMediaType *)`
- caller_count: `15`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1000d790`
- `0x1000da20`
- `0x1000dcc0`
- `0x10010e48`
- `0x10011c70`
- `0x10014357`
- `0x10015b70`
- `0x1001c3e4`
- `0x1002dd14`
- `0x10030148`
- `0x100302a7`
- `0x10031400`
- `0x10031560`
- `0x10031712`
- `0x100336ea`

## callees

- `0x1003035c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1003036c`
- `ole32!CoTaskMemFree` at `0x1003036c`

## pseudocode

```c
void __thiscall FreeMediaType(int this)
{
  if ( *(_DWORD *)(this + 64) )
  {
    CoTaskMemFree(*(LPVOID *)(this + 68));
    *(_DWORD *)(this + 64) = 0;
    *(_DWORD *)(this + 68) = 0;
  }
  *(_DWORD *)(this + 60) = 0;
}

```

## disassembly

```asm
0x1003035c  mov     edi, edi
0x1003035e  push    esi
0x1003035f  mov     esi, ecx
0x10030361  push    edi
0x10030362  xor     edi, edi
0x10030364  cmp     [esi+40h], edi
0x10030367  jz      short loc_10030378
0x10030369  push    dword ptr [esi+44h]; pv
0x1003036c  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10030372  mov     [esi+40h], edi
0x10030375  mov     [esi+44h], edi
0x10030378  mov     [esi+3Ch], edi
0x1003037b  pop     edi
0x1003037c  pop     esi
0x1003037d  retn
```
