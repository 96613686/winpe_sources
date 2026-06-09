# DfscIsErrorInList

- ea: `0x140021c10`
- end: `0x140021c57`
- name: `DfscIsErrorInList`
- size: `71`
- prototype: `char __fastcall(int, __int64, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140011c80`
- `0x14001a630`
- `0x14001abc0`
- `0x140021688`
- `0x1400219c0`
- `0x1400281ac`
- `0x140029160`

## callees

- `0x140021c10`

## pseudocode

```c
char __fastcall DfscIsErrorInList(int a1, __int64 a2, int a3)
{
  int v5; // r9d
  int v6; // r8d
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // eax

  if ( a1 >= 0 )
    return 0;
  v5 = 0;
  v6 = a3 - 1;
  while ( 1 )
  {
    v7 = (v6 + v5) / 2;
    v8 = *(_DWORD *)(a2 + 4LL * v7);
    if ( v8 == a1 )
      break;
    v9 = v7 - 1;
    if ( v8 <= a1 )
      v9 = v6;
    v10 = v7 + 1;
    v6 = v9;
    if ( v8 <= a1 )
      v5 = v10;
    if ( v5 > v9 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140021c10  mov     r11, rdx
0x140021c13  mov     r10d, ecx
0x140021c16  test    ecx, ecx
0x140021c18  jns     short loc_140021C50
0x140021c1a  xor     r9d, r9d
0x140021c1d  dec     r8d
0x140021c20  lea     eax, [r8+r9]
0x140021c24  test    eax, eax
0x140021c26  jns     short loc_140021C2A
0x140021c28  inc     eax
0x140021c2a  sar     eax, 1
0x140021c2c  movsxd  rcx, eax
0x140021c2f  mov     edx, [r11+rcx*4]
0x140021c33  cmp     edx, r10d
0x140021c36  jz      short loc_140021C54
0x140021c38  lea     ecx, [rax-1]
0x140021c3b  cmovle  ecx, r8d
0x140021c3f  inc     eax
0x140021c41  cmp     edx, r10d
0x140021c44  mov     r8d, ecx
0x140021c47  cmovle  r9d, eax
0x140021c4b  cmp     r9d, ecx
0x140021c4e  jle     short loc_140021C20
0x140021c50  xor     al, al
0x140021c52  retn
0x140021c54  mov     al, 1
0x140021c56  retn
```
