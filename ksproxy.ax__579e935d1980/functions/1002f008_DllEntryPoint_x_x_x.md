# _DllEntryPoint(x,x,x)

- ea: `0x1002f008`
- end: `0x1002f037`
- name: `__DllEntryPoint@12`
- size: `47`
- prototype: `int __thiscall(HMODULE hLibModule, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1000816d`

## callees

- `0x1002ef9a`
- `0x1002f008`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x1002f018`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1002f018`

## pseudocode

```c
int __fastcall _DllEntryPoint(HMODULE hLibModule, int a2, int a3)
{
  int v5; // [esp+0h] [ebp-4h]

  if ( !a2 )
    goto LABEL_4;
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(hLibModule);
    g_hInst = hLibModule;
LABEL_4:
    DllInitClasses(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x1002f008  mov     edi, edi
0x1002f00a  push    esi; int
0x1002f00b  mov     esi, ecx
0x1002f00d  sub     edx, 0
0x1002f010  jz      short loc_1002F029
0x1002f012  sub     edx, 1
0x1002f015  jnz     short loc_1002F030
0x1002f017  push    esi; hLibModule
0x1002f018  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x1002f01e  xor     ecx, ecx
0x1002f020  mov     ?g_hInst@@3PAUHINSTANCE__@@A, esi; HINSTANCE__ * g_hInst
0x1002f026  inc     ecx
0x1002f027  jmp     short loc_1002F02B
0x1002f029  xor     ecx, ecx
0x1002f02b  call    ?DllInitClasses@@YGXH@Z; DllInitClasses(int)
0x1002f030  xor     eax, eax
0x1002f032  inc     eax
0x1002f033  pop     esi
0x1002f034  retn    4
```
