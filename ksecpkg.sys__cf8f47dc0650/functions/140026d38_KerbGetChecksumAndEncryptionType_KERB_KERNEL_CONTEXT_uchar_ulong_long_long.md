# KerbGetChecksumAndEncryptionType(_KERB_KERNEL_CONTEXT *,uchar,ulong,long *,long *)

- ea: `0x140026d38`
- end: `0x140026e33`
- name: `?KerbGetChecksumAndEncryptionType@@YAJPEAU_KERB_KERNEL_CONTEXT@@EKPEAJ1@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct _KERB_KERNEL_CONTEXT *, unsigned __int8, unsigned int, int *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400263c0`
- `0x140026f70`
- `0x1400276c0`

## callees

- `0x140026d38`

## pseudocode

```c
__int64 __fastcall KerbGetChecksumAndEncryptionType(struct _KERB_KERNEL_CONTEXT *a1, char a2, int a3, int *a4, int *a5)
{
  int v5; // r10d
  unsigned int v6; // r11d
  int v7; // eax

  v5 = *((_DWORD *)a1 + 28);
  v6 = 0;
  if ( v5 == -132 || (unsigned int)(v5 - 1) <= 2 )
  {
    *a5 = -132;
    switch ( a3 )
    {
      case 0:
        goto LABEL_24;
      case 1:
        *a4 = -135;
        return v6;
      case 2:
        goto LABEL_24;
      case 3:
        *a4 = -133;
        return v6;
      case -2147483647:
LABEL_24:
        *a4 = -134;
        return v6;
    }
    return (unsigned int)-1073741811;
  }
  else if ( v5 == 23 )
  {
    *a4 = -138;
    *a5 = -140;
  }
  else
  {
    if ( (unsigned int)(v5 - 17) <= 1 )
    {
      *a5 = v5;
      if ( v5 == 17 )
      {
        *a5 = -148;
        if ( !a2 || (v7 = -150, a3 == -2147483647) )
          v7 = 15;
      }
      else
      {
        if ( v5 != 18 )
          return v6;
        *a5 = -149;
        if ( !a2 || (v7 = -151, a3 == -2147483647) )
          v7 = 16;
      }
      *a4 = v7;
      return v6;
    }
    *a4 = -138;
    *a5 = -141;
  }
  return v6;
}

```

## disassembly

```asm
0x140026d38  mov     r10d, [rcx+70h]
0x140026d3c  xor     r11d, r11d
0x140026d3f  mov     ecx, 0FFFFFF7Ch
0x140026d44  cmp     r10d, ecx
0x140026d47  jz      loc_140026DE7
0x140026d4d  lea     eax, [r10-1]
0x140026d51  cmp     eax, 2
0x140026d54  jbe     loc_140026DE7
0x140026d5a  cmp     r10d, 17h
0x140026d5e  jnz     short loc_140026D77
0x140026d60  mov     rax, [rsp+arg_20]
0x140026d65  mov     dword ptr [r9], 0FFFFFF76h
0x140026d6c  mov     dword ptr [rax], 0FFFFFF74h
0x140026d72  jmp     loc_140026E2F
0x140026d77  lea     eax, [r10-11h]
0x140026d7b  cmp     eax, 1
0x140026d7e  mov     rax, [rsp+arg_20]
0x140026d83  jbe     short loc_140026D97
0x140026d85  mov     dword ptr [r9], 0FFFFFF76h
0x140026d8c  mov     dword ptr [rax], 0FFFFFF73h
0x140026d92  jmp     loc_140026E2F
0x140026d97  mov     [rax], r10d
0x140026d9a  cmp     r10d, 11h
0x140026d9e  jnz     short loc_140026DBF
0x140026da0  mov     dword ptr [rax], 0FFFFFF6Ch
0x140026da6  test    dl, dl
0x140026da8  jz      short loc_140026DB8
0x140026daa  mov     eax, 0FFFFFF6Ah
0x140026daf  cmp     r8d, 80000001h
0x140026db6  jnz     short loc_140026DE2
0x140026db8  mov     eax, 0Fh
0x140026dbd  jmp     short loc_140026DE2
0x140026dbf  cmp     r10d, 12h
0x140026dc3  jnz     short loc_140026E2F
0x140026dc5  mov     dword ptr [rax], 0FFFFFF6Bh
0x140026dcb  test    dl, dl
0x140026dcd  jz      short loc_140026DDD
0x140026dcf  mov     eax, 0FFFFFF69h
0x140026dd4  cmp     r8d, 80000001h
0x140026ddb  jnz     short loc_140026DE2
0x140026ddd  mov     eax, 10h
0x140026de2  mov     [r9], eax
0x140026de5  jmp     short loc_140026E2F
0x140026de7  mov     rax, [rsp+arg_20]
0x140026dec  mov     [rax], ecx
0x140026dee  test    r8d, r8d
0x140026df1  jz      short loc_140026E28
0x140026df3  cmp     r8d, 1
0x140026df7  jz      short loc_140026E1F
0x140026df9  cmp     r8d, 2
0x140026dfd  jz      short loc_140026E28
0x140026dff  cmp     r8d, 3
0x140026e03  jz      short loc_140026E16
0x140026e05  cmp     r8d, 80000001h
0x140026e0c  jz      short loc_140026E28
0x140026e0e  mov     r11d, 0C000000Dh
0x140026e14  jmp     short loc_140026E2F
0x140026e16  mov     dword ptr [r9], 0FFFFFF7Bh
0x140026e1d  jmp     short loc_140026E2F
0x140026e1f  mov     dword ptr [r9], 0FFFFFF79h
0x140026e26  jmp     short loc_140026E2F
0x140026e28  mov     dword ptr [r9], 0FFFFFF7Ah
0x140026e2f  mov     eax, r11d
0x140026e32  retn
```
