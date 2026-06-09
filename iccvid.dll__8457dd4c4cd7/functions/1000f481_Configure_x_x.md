# Configure(x,x)

- ea: `0x1000f481`
- end: `0x1000f4c4`
- name: `_Configure@8`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100093a0`

## callees

- `0x1000f481`

## import_xrefs

- `USER32!DialogBoxParamA` at `0x1000f49c`
- `USER32!DialogBoxParamA` at `0x1000f49c`

## string_xrefs

- `0x1000f491`: `Configure`

## pseudocode

```c
int __fastcall Configure(int a1, HWND a2)
{
  INT_PTR v3; // eax
  int v4; // eax

  v3 = DialogBoxParamA(ghModule, "Configure", a2, (DLGPROC)ConfigureDlgProc, *(char *)(a1 + 5));
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
        return 0;
    }
    else
    {
      *(_BYTE *)(a1 + 5) = 1;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 5) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1000f481  mov     edi, edi
0x1000f483  push    esi
0x1000f484  mov     esi, ecx
0x1000f486  movsx   eax, byte ptr [esi+5]
0x1000f48a  push    eax; dwInitParam
0x1000f48b  push    offset _ConfigureDlgProc@16; lpDialogFunc
0x1000f490  push    edx; hWndParent
0x1000f491  push    offset aConfigure; "Configure"
0x1000f496  push    _ghModule; hInstance
0x1000f49c  call    ds:__imp__DialogBoxParamA@20; DialogBoxParamA(x,x,x,x,x)
0x1000f4a2  sub     eax, 0
0x1000f4a5  jz      short loc_1000F4BB
0x1000f4a7  sub     eax, 1
0x1000f4aa  jz      short loc_1000F4B5
0x1000f4ac  sub     eax, 1
0x1000f4af  jz      short loc_1000F4BF
0x1000f4b1  xor     eax, eax
0x1000f4b3  pop     esi
0x1000f4b4  retn
0x1000f4b5  mov     byte ptr [esi+5], 1
0x1000f4b9  jmp     short loc_1000F4BF
0x1000f4bb  mov     byte ptr [esi+5], 0
0x1000f4bf  xor     eax, eax
0x1000f4c1  inc     eax
0x1000f4c2  pop     esi
0x1000f4c3  retn
```
