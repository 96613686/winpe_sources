# WBTUpdate(x,x,x,x,x)

- ea: `0x1002ce20`
- end: `0x1002ce9f`
- name: `_WBTUpdate@20`
- size: `127`
- prototype: `int __stdcall(int, int, int, size_t Size, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1002acaf`
- `0x1002c79f`
- `0x1002cbc4`
- `0x1002ce20`

## pseudocode

```c
int __stdcall WBTUpdate(int a1, int a2, void *a3, size_t Size, _DWORD *a5)
{
  int v5; // eax
  _DWORD *v6; // ecx
  int v8; // eax
  int v10; // ecx

  if ( a5 )
    *a5 = 0;
  v5 = ISAMDBFindCursor(a1, a2);
  v6 = (_DWORD *)v5;
  if ( !v5 )
    return -1310;
  if ( *(_BYTE *)(v5 + 28) == 1 )
    return -1809;
  v8 = *(_DWORD *)(v5 + 48);
  if ( v8 == 1 || v8 == 2 )
    return RecordInsert(Size, (int)a5);
  if ( v8 != 3 )
  {
    v10 = -1609;
    if ( v8 == 4 )
      return -5034;
    return v10;
  }
  return RecordReplace(v6, a3, Size, a5);
}

```

## disassembly

```asm
0x1002ce20  mov     edi, edi
0x1002ce22  push    ebp
0x1002ce23  mov     ebp, esp
0x1002ce25  push    esi
0x1002ce26  mov     esi, [ebp+arg_10]
0x1002ce29  test    esi, esi
0x1002ce2b  jz      short loc_1002CE33
0x1002ce2d  mov     dword ptr [esi], 0
0x1002ce33  mov     edx, [ebp+arg_4]
0x1002ce36  mov     ecx, [ebp+arg_0]
0x1002ce39  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002ce3e  mov     ecx, eax
0x1002ce40  test    ecx, ecx
0x1002ce42  jnz     short loc_1002CE4B
0x1002ce44  mov     eax, 0FFFFFAE2h
0x1002ce49  jmp     short loc_1002CE9A
0x1002ce4b  cmp     byte ptr [ecx+1Ch], 1
0x1002ce4f  jnz     short loc_1002CE58
0x1002ce51  mov     eax, 0FFFFF8EFh
0x1002ce56  jmp     short loc_1002CE9A
0x1002ce58  mov     eax, [ecx+30h]
0x1002ce5b  cmp     eax, 1
0x1002ce5e  jz      short loc_1002CE8A
0x1002ce60  cmp     eax, 2
0x1002ce63  jz      short loc_1002CE8A
0x1002ce65  cmp     eax, 3
0x1002ce68  jnz     short loc_1002CE78
0x1002ce6a  mov     edx, [ebp+arg_8]
0x1002ce6d  push    esi
0x1002ce6e  push    [ebp+Size]
0x1002ce71  call    RecordReplace
0x1002ce76  jmp     short loc_1002CE96
0x1002ce78  cmp     eax, 4
0x1002ce7b  mov     ecx, 0FFFFF9B7h
0x1002ce80  mov     edx, 0FFFFEC56h
0x1002ce85  cmovz   ecx, edx
0x1002ce88  jmp     short loc_1002CE98
0x1002ce8a  mov     edx, [ebp+arg_8]
0x1002ce8d  push    esi; int
0x1002ce8e  push    [ebp+Size]; Size
0x1002ce91  call    RecordInsert
0x1002ce96  mov     ecx, eax
0x1002ce98  mov     eax, ecx
0x1002ce9a  pop     esi
0x1002ce9b  pop     ebp
0x1002ce9c  retn    14h
```
