# PostInstError

- ea: `0x180004bac`
- end: `0x180004bd3`
- name: `PostInstError`
- size: `39`
- prototype: `__int64 __fastcall(int)`
- caller_count: `42`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017c0`
- `0x18000295c`
- `0x1800033bc`
- `0x180003bb8`
- `0x180003e10`
- `0x180004580`
- `0x180004800`
- `0x180005c00`
- `0x180005fd4`
- `0x180006184`
- `0x180006db8`
- `0x180007628`
- `0x180007c0c`
- `0x1800084c0`
- `0x1800085c8`
- `0x180008dc0`
- `0x180008e78`
- `0x180009050`
- `0x1800091f0`
- `0x180009280`
- `0x180009464`
- `0x1800097d0`
- `0x180009a88`
- `0x180009c30`
- `0x180009d40`
- `0x180009e8c`
- `0x18000a1b4`
- `0x18000b5f0`
- `0x18000f100`
- `0x180011d48`
- `0x180011ec4`
- `0x18001217c`
- `0x1800125cc`
- `0x180012a78`
- `0x180012b14`
- `0x180012c98`
- `0x180012e90`
- `0x180013270`
- `0x1800134d4`
- `0x1800135e4`
- `0x1800136b0`
- `0x180013fa8`

## callees

- `0x180004bac`

## pseudocode

```c
__int64 __fastcall PostInstError(int a1)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = (unsigned __int16)word_18001CA40;
  if ( (unsigned __int16)word_18001CA40 < 8u )
  {
    result = 2LL * (unsigned __int16)word_18001CA40++;
    LODWORD(qword_18001C9C0[2 * v1]) = a1;
  }
  return result;
}

```

## disassembly

```asm
0x180004bac  movzx   edx, cs:word_18001CA40
0x180004bb3  cmp     edx, 8
0x180004bb6  jnb     short locret_180004BD2
0x180004bb8  mov     eax, edx
0x180004bba  lea     r8, qword_18001C9C0
0x180004bc1  add     rax, rax
0x180004bc4  inc     dx
0x180004bc7  mov     cs:word_18001CA40, dx
0x180004bce  mov     [r8+rax*8], ecx
0x180004bd2  retn
```
