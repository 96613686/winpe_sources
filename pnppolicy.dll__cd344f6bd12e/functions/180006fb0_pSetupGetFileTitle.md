# pSetupGetFileTitle

- ea: `0x180006fb0`
- end: `0x180006ffa`
- name: `pSetupGetFileTitle`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004658`
- `0x180005018`
- `0x1800054d4`
- `0x1800058a0`
- `0x180005970`

## callees

- `0x180006fb0`

## pseudocode

```c
unsigned __int16 *__fastcall pSetupGetFileTitle(unsigned __int16 *a1)
{
  unsigned __int16 v1; // dx
  unsigned __int16 *result; // rax

  v1 = *a1;
  if ( (unsigned __int16)(*a1 - 65) <= 0x19u )
    goto LABEL_11;
  if ( v1 < 0x61u )
  {
LABEL_13:
    result = a1;
    goto LABEL_9;
  }
  if ( v1 <= 0x7Au )
  {
LABEL_11:
    if ( a1[1] == 58 )
    {
      a1 += 2;
      v1 = *a1;
    }
    goto LABEL_13;
  }
  result = a1;
  do
  {
    ++a1;
    if ( v1 == 92 || v1 == 47 )
      result = a1;
    v1 = *a1;
LABEL_9:
    ;
  }
  while ( v1 );
  return result;
}

```

## disassembly

```asm
0x180006fb0  movzx   edx, word ptr [rcx]
0x180006fb3  lea     eax, [rdx-41h]
0x180006fb6  cmp     ax, 19h
0x180006fba  jbe     short loc_180006FE7
0x180006fbc  cmp     dx, 61h ; 'a'
0x180006fc0  jb      short loc_180006FF5
0x180006fc2  cmp     dx, 7Ah ; 'z'
0x180006fc6  jbe     short loc_180006FE7
0x180006fc8  mov     rax, rcx
0x180006fcb  add     rcx, 2
0x180006fcf  cmp     dx, 5Ch ; '\'
0x180006fd3  jz      short loc_180006FDB
0x180006fd5  cmp     dx, 2Fh ; '/'
0x180006fd9  jnz     short loc_180006FDE
0x180006fdb  mov     rax, rcx
0x180006fde  movzx   edx, word ptr [rcx]
0x180006fe1  test    dx, dx
0x180006fe4  jnz     short loc_180006FCB
0x180006fe6  retn
0x180006fe7  cmp     word ptr [rcx+2], 3Ah ; ':'
0x180006fec  jnz     short loc_180006FF5
0x180006fee  add     rcx, 4
0x180006ff2  movzx   edx, word ptr [rcx]
0x180006ff5  mov     rax, rcx
0x180006ff8  jmp     short loc_180006FE1
```
