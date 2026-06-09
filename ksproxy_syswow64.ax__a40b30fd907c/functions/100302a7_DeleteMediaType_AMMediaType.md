# DeleteMediaType(_AMMediaType *)

- ea: `0x100302a7`
- end: `0x100302be`
- name: `?DeleteMediaType@@YGXPAU_AMMediaType@@@Z`
- size: `23`
- prototype: `void __thiscall(void *this)`
- caller_count: `19`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10010350`
- `0x10012da0`
- `0x100147ad`
- `0x10016a04`
- `0x10017097`
- `0x100179f0`
- `0x10017af0`
- `0x10017be0`
- `0x1001b560`
- `0x1001b660`
- `0x1001c490`
- `0x1001c710`
- `0x1001e1f8`
- `0x1002c92d`
- `0x1002cd60`
- `0x100319b5`
- `0x100324ca`
- `0x10032910`
- `0x10032a10`

## callees

- `0x100302a7`
- `0x1003035c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x100302b6`
- `ole32!CoTaskMemFree` at `0x100302b6`

## pseudocode

```c
void __thiscall DeleteMediaType(void *this)
{
  struct _AMMediaType *v2; // [esp+0h] [ebp-4h]

  if ( this )
  {
    FreeMediaType(v2);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x100302a7  mov     edi, edi
0x100302a9  push    esi; struct _AMMediaType *
0x100302aa  mov     esi, ecx
0x100302ac  test    esi, esi
0x100302ae  jz      short loc_100302BC
0x100302b0  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x100302b5  push    esi; pv
0x100302b6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100302bc  pop     esi
0x100302bd  retn
```
