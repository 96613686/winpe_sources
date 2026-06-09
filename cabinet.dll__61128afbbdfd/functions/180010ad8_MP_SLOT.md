# MP_SLOT

- ea: `0x180010ad8`
- end: `0x180010b10`
- name: `MP_SLOT`
- size: `56`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f50c`
- `0x18000fa50`
- `0x18000fe40`
- `0x180010064`
- `0x180010130`

## callees

- `0x180010ad8`

## pseudocode

```c
char __fastcall MP_SLOT(__int64 a1, int a2)
{
  if ( a2 < 1024 )
    return *(_BYTE *)(a2 + a1 + 1148);
  if ( a2 >= 0x80000 )
    return ((unsigned int)a2 >> 17) + 34;
  return *(_BYTE *)(((unsigned __int64)a2 >> 9) + a1 + 1148) + 18;
}

```

## disassembly

```asm
0x180010ad8  cmp     edx, 400h
0x180010ade  jge     short loc_180010AED
0x180010ae0  movsxd  rax, edx
0x180010ae3  mov     dl, [rax+rcx+47Ch]
0x180010aea  mov     al, dl
0x180010aec  retn
0x180010aed  cmp     edx, 80000h
0x180010af3  jge     short loc_180010B08
0x180010af5  movsxd  rax, edx
0x180010af8  shr     rax, 9
0x180010afc  mov     dl, [rax+rcx+47Ch]
0x180010b03  add     dl, 12h
0x180010b06  jmp     short loc_180010AEA
0x180010b08  shr     edx, 11h
0x180010b0b  add     dl, 22h ; '"'
0x180010b0e  jmp     short loc_180010AEA
```
