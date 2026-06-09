# OSSetFilePosition

- ea: `0x10025bee`
- end: `0x10025c41`
- name: `OSSetFilePosition`
- size: `83`
- prototype: `int __fastcall(int, DWORD, int lDistanceToMove)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000dcc0`
- `0x1000dd90`
- `0x1000df70`
- `0x10011280`
- `0x10025df5`
- `0x10025e72`
- `0x10025ed1`
- `0x10025f86`
- `0x10026030`
- `0x100260bc`
- `0x10026233`
- `0x100264c2`

## callees

- `0x10025bee`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10025c05`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10025c05`

## pseudocode

```c
int __fastcall OSSetFilePosition(int a1, DWORD a2, int lDistanceToMove)
{
  if ( *(_DWORD *)(a1 + 12) )
    return -((*(int (__thiscall **)(_DWORD, _DWORD, int, int, DWORD, _DWORD))(**(_DWORD **)(a1 + 32) + 20))(
               *(_DWORD *)(**(_DWORD **)(a1 + 32) + 20),
               *(_DWORD *)(a1 + 32),
               lDistanceToMove,
               lDistanceToMove >> 31,
               a2,
               0) != 0);
  else
    return (SetFilePointer(*(HANDLE *)(a1 + 20), lDistanceToMove, 0, a2) != -1) - 1;
}

```

## disassembly

```asm
0x10025bee  mov     edi, edi
0x10025bf0  push    ebp
0x10025bf1  mov     ebp, esp
0x10025bf3  mov     eax, ecx
0x10025bf5  push    esi
0x10025bf6  cmp     dword ptr [eax+0Ch], 0
0x10025bfa  jnz     short loc_10025C18
0x10025bfc  push    edx; dwMoveMethod
0x10025bfd  push    0; lpDistanceToMoveHigh
0x10025bff  push    [ebp+lDistanceToMove]; lDistanceToMove
0x10025c02  push    dword ptr [eax+14h]; hFile
0x10025c05  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10025c0b  xor     ecx, ecx
0x10025c0d  cmp     eax, 0FFFFFFFFh
0x10025c10  setnz   cl
0x10025c13  lea     eax, [ecx-1]
0x10025c16  jmp     short loc_10025C3C
0x10025c18  mov     eax, [eax+20h]
0x10025c1b  mov     ecx, [ebp+lDistanceToMove]
0x10025c1e  push    0
0x10025c20  push    edx
0x10025c21  mov     esi, [eax]
0x10025c23  sar     ecx, 1Fh
0x10025c26  push    ecx
0x10025c27  push    [ebp+lDistanceToMove]
0x10025c2a  mov     esi, [esi+14h]
0x10025c2d  mov     ecx, esi
0x10025c2f  push    eax
0x10025c30  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025c36  call    esi
0x10025c38  neg     eax
0x10025c3a  sbb     eax, eax
0x10025c3c  pop     esi
0x10025c3d  pop     ebp
0x10025c3e  retn    4
```
