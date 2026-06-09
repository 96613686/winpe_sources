# _DllEntryPoint

- ea: `0x1800032d8`
- end: `0x180003310`
- name: `_DllEntryPoint`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032a4`

## callees

- `0x18000318c`
- `0x1800032d8`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x1800032ea`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1800032ea`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  int v3; // ecx

  if ( !a2 )
  {
    v3 = 0;
    goto LABEL_5;
  }
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    v3 = 1;
    g_hInst = a1;
LABEL_5:
    DllInitClasses(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x1800032d8  push    rbx
0x1800032da  sub     rsp, 20h
0x1800032de  mov     rbx, rcx
0x1800032e1  test    edx, edx
0x1800032e3  jz      short loc_1800032FE
0x1800032e5  cmp     edx, 1
0x1800032e8  jnz     short loc_180003305
0x1800032ea  call    cs:__imp_DisableThreadLibraryCalls
0x1800032f0  mov     ecx, 1
0x1800032f5  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x1800032fc  jmp     short loc_180003300
0x1800032fe  xor     ecx, ecx; int
0x180003300  call    ?DllInitClasses@@YAXH@Z; DllInitClasses(int)
0x180003305  mov     eax, 1
0x18000330a  add     rsp, 20h
0x18000330e  pop     rbx
0x18000330f  retn
```
