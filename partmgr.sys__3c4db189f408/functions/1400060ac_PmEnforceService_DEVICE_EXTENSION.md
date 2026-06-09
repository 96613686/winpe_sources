# PmEnforceService(_DEVICE_EXTENSION *)

- ea: `0x1400060ac`
- end: `0x1400060d9`
- name: `?PmEnforceService@@YAEPEAU_DEVICE_EXTENSION@@@Z`
- size: `45`
- prototype: `unsigned __int8 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140007674`
- `0x140007bcc`
- `0x140020778`

## callees

- `0x1400060ac`

## pseudocode

```c
bool __fastcall PmEnforceService(struct _DEVICE_EXTENSION *a1)
{
  bool result; // al

  result = 0;
  if ( *((_BYTE *)PmControlObject->DeviceExtension + 170) )
    return (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 0x40001) == 0;
  return result;
}

```

## disassembly

```asm
0x1400060ac  mov     rdx, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400060b3  xor     al, al
0x1400060b5  mov     r8, [rdx+40h]
0x1400060b9  cmp     [r8+0AAh], al
0x1400060c0  jz      short locret_1400060D8
0x1400060c2  mov     rcx, [rcx+8]
0x1400060c6  movzx   eax, al
0x1400060c9  test    dword ptr [rcx+34h], 40001h
0x1400060d0  mov     ecx, 1
0x1400060d5  cmovz   eax, ecx
0x1400060d8  retn
```
