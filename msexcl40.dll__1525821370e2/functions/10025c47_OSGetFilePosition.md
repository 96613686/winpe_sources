# OSGetFilePosition

- ea: `0x10025c47`
- end: `0x10025cad`
- name: `OSGetFilePosition`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10011280`
- `0x10026030`

## callees

- `0x10025c47`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10025c64`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10025c64`

## pseudocode

```c
int __fastcall OSGetFilePosition(int a1, DWORD *a2)
{
  DWORD v3; // ecx
  int result; // eax
  DWORD v5[2]; // [esp+10h] [ebp-8h] BYREF

  if ( *(_DWORD *)(a1 + 12) )
  {
    if ( (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD, int, DWORD *))(**(_DWORD **)(a1 + 32) + 20))(
           *(_DWORD *)(**(_DWORD **)(a1 + 32) + 20),
           *(_DWORD *)(a1 + 32),
           0,
           0,
           1,
           v5) )
    {
      return -1;
    }
    else
    {
      *a2 = v5[0];
      return 0;
    }
  }
  else
  {
    v3 = SetFilePointer(*(HANDLE *)(a1 + 20), 0, 0, 1u);
    result = -1;
    if ( v3 != -1 )
    {
      *a2 = v3;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10025c47  mov     edi, edi
0x10025c49  push    ebp
0x10025c4a  mov     ebp, esp
0x10025c4c  sub     esp, 0Ch
0x10025c4f  push    ebx
0x10025c50  push    esi
0x10025c51  push    edi
0x10025c52  mov     edi, edx
0x10025c54  xor     esi, esi
0x10025c56  mov     edx, ecx
0x10025c58  cmp     [edx+0Ch], esi
0x10025c5b  jnz     short loc_10025C79
0x10025c5d  push    1; dwMoveMethod
0x10025c5f  push    esi; lpDistanceToMoveHigh
0x10025c60  push    esi; lDistanceToMove
0x10025c61  push    dword ptr [edx+14h]; hFile
0x10025c64  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10025c6a  mov     ecx, eax
0x10025c6c  or      eax, 0FFFFFFFFh
0x10025c6f  cmp     ecx, eax
0x10025c71  jz      short loc_10025CA8
0x10025c73  mov     [edi], ecx
0x10025c75  mov     eax, esi
0x10025c77  jmp     short loc_10025CA8
0x10025c79  mov     edx, [edx+20h]
0x10025c7c  lea     ebx, [ebp+var_8]
0x10025c7f  push    ebx
0x10025c80  mov     eax, esi
0x10025c82  mov     ecx, esi
0x10025c84  push    1
0x10025c86  mov     esi, [edx]
0x10025c88  push    eax
0x10025c89  push    ecx
0x10025c8a  push    edx
0x10025c8b  mov     esi, [esi+14h]
0x10025c8e  mov     ecx, esi
0x10025c90  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025c96  call    esi
0x10025c98  test    eax, eax
0x10025c9a  jz      short loc_10025CA1
0x10025c9c  or      eax, 0FFFFFFFFh
0x10025c9f  jmp     short loc_10025CA8
0x10025ca1  mov     eax, [ebp+var_8]
0x10025ca4  mov     [edi], eax
0x10025ca6  xor     eax, eax
0x10025ca8  pop     edi
0x10025ca9  pop     esi
0x10025caa  pop     ebx
0x10025cab  leave
0x10025cac  retn
```
