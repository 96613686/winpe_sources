# TextCreateExportFile

- ea: `0x1001ede0`
- end: `0x1001ee62`
- name: `TextCreateExportFile`
- size: `130`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1001ee70`

## callees

- `0x1000b410`
- `0x1000b5f0`
- `0x1000b600`
- `0x1001d4b0`
- `0x1001ede0`

## pseudocode

```c
int __stdcall TextCreateExportFile(LPCWSTR lpFileName, _DWORD *a2, int a3)
{
  int v3; // eax
  int v4; // ecx
  int result; // eax
  bool v6; // zf
  int v7; // eax

  if ( !DOSFileExists(lpFileName) )
    DOSFileDelete(lpFileName);
  if ( a3 == 3 )
  {
    v3 = BFCreateFile(lpFileName, 18, a2 + 1);
    v4 = v3;
    if ( !v3 )
      return 0;
    if ( v3 == -1 )
      return -1807;
    v6 = v3 == -2;
  }
  else
  {
    v7 = DOSCreateFile(lpFileName, a2);
    v4 = v7;
    if ( !v7 )
      return 0;
    if ( v7 == -4 )
      return -1807;
    v6 = v7 == -5;
  }
  if ( v6 )
    return -1032;
  result = -5036;
  if ( v4 == -3 )
    return -1023;
  return result;
}

```

## disassembly

```asm
0x1001ede0  push    esi
0x1001ede1  mov     esi, [esp+4+lpFileName]
0x1001ede5  push    esi; lpFileName
0x1001ede6  call    _DOSFileExists@4; DOSFileExists(x)
0x1001edeb  test    eax, eax
0x1001eded  jnz     short loc_1001EDF5
0x1001edef  push    esi
0x1001edf0  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1001edf5  cmp     [esp+4+arg_8], 3
0x1001edfa  jnz     short loc_1001EE2B
0x1001edfc  mov     eax, [esp+4+arg_4]
0x1001ee00  add     eax, 4
0x1001ee03  push    eax; int
0x1001ee04  push    12h; int
0x1001ee06  push    esi; lpFileName
0x1001ee07  call    _BFCreateFile@12; BFCreateFile(x,x,x)
0x1001ee0c  mov     ecx, eax
0x1001ee0e  test    ecx, ecx
0x1001ee10  jnz     short loc_1001EE18
0x1001ee12  xor     eax, eax
0x1001ee14  pop     esi
0x1001ee15  retn    0Ch
0x1001ee18  cmp     ecx, 0FFFFFFFFh
0x1001ee1b  jnz     short loc_1001EE26
0x1001ee1d  mov     eax, 0FFFFF8F1h
0x1001ee22  pop     esi
0x1001ee23  retn    0Ch
0x1001ee26  cmp     ecx, 0FFFFFFFEh
0x1001ee29  jmp     short loc_1001EE43
0x1001ee2b  push    [esp+4+arg_4]; int
0x1001ee2f  push    esi; lpFileName
0x1001ee30  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x1001ee35  mov     ecx, eax
0x1001ee37  test    ecx, ecx
0x1001ee39  jz      short loc_1001EE12
0x1001ee3b  cmp     ecx, 0FFFFFFFCh
0x1001ee3e  jz      short loc_1001EE1D
0x1001ee40  cmp     ecx, 0FFFFFFFBh
0x1001ee43  jnz     short loc_1001EE4E
0x1001ee45  mov     eax, 0FFFFFBF8h
0x1001ee4a  pop     esi
0x1001ee4b  retn    0Ch
0x1001ee4e  cmp     ecx, 0FFFFFFFDh
0x1001ee51  mov     eax, 0FFFFEC54h
0x1001ee56  mov     edx, 0FFFFFC01h
0x1001ee5b  cmovz   eax, edx
0x1001ee5e  pop     esi
0x1001ee5f  retn    0Ch
```
