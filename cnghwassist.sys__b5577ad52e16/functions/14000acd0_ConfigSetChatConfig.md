# ConfigSetChatConfig

- ea: `0x14000acd0`
- end: `0x14000adcb`
- name: `ConfigSetChatConfig`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002670`
- `0x14000b1c0`

## callees

- `0x14000acd0`

## pseudocode

```c
__int64 __fastcall ConfigSetChatConfig(__int64 a1, unsigned int a2)
{
  unsigned int v4; // edx
  unsigned int v5; // r9d
  unsigned int v6; // r11d
  __int64 v7; // rbx
  int v8; // edi
  unsigned int v9; // ecx
  __int64 v10; // r14
  unsigned int v11; // esi
  unsigned int v12; // ebp
  int i; // r15d
  unsigned int v14; // eax
  unsigned __int64 v15; // rcx

  if ( (a2 & 0xF) == 0 && a2 && *(_DWORD *)a1 == -1 && !*(_DWORD *)(a1 + 4) && *(_QWORD *)(a1 + 8) == 1 )
  {
    v4 = 0;
    v5 = a2 >> 4;
    v6 = 1;
    if ( v5 > 1 )
    {
      v7 = 1;
      do
      {
        if ( *(_DWORD *)(a1 + 16 * v7 + 4) < 3u )
        {
          v8 = 0;
          do
          {
            v9 = *(_DWORD *)(a1 + 16 * v7);
            if ( ConfigSetting[4 * v8] == v9 && v9 < 0x50000 )
            {
              v10 = dword_140006064[4 * v8];
              if ( (int)v10 >= 0 )
              {
                v11 = *(_DWORD *)(a1 + 16 * v7 + 4);
                v12 = v11;
                for ( i = *(_DWORD *)(a1 + 16 * v7 + 8); ; *(int *)((char *)g_config + v10 + v15) = i )
                {
                  v14 = 3;
                  if ( v11 )
                    v14 = v11 + 1;
                  if ( v12 >= v14 )
                    break;
                  v15 = (unsigned __int64)v12++ << 6;
                }
              }
            }
            ++v8;
          }
          while ( ConfigSetting[4 * v8] );
        }
        ++v6;
        ++v7;
      }
      while ( v6 < v5 );
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x14000acd0  push    rbx
0x14000acd2  push    rbp
0x14000acd3  push    rsi
0x14000acd4  push    rdi
0x14000acd5  push    r13
0x14000acd7  push    r14
0x14000acd9  push    r15
0x14000acdb  mov     r9d, edx
0x14000acde  mov     r8, rcx
0x14000ace1  test    dl, 0Fh
0x14000ace4  jnz     loc_14000ADB8
0x14000acea  test    edx, edx
0x14000acec  jz      loc_14000ADB8
0x14000acf2  cmp     dword ptr [rcx], 0FFFFFFFFh
0x14000acf5  jnz     loc_14000ADB8
0x14000acfb  cmp     dword ptr [rcx+4], 0
0x14000acff  jnz     loc_14000ADB8
0x14000ad05  cmp     qword ptr [rcx+8], 1
0x14000ad0a  jnz     loc_14000ADB8
0x14000ad10  xor     edx, edx
0x14000ad12  shr     r9d, 4
0x14000ad16  lea     r11d, [rdx+1]
0x14000ad1a  cmp     r9d, r11d
0x14000ad1d  jbe     loc_14000ADBD
0x14000ad23  mov     ebx, r11d
0x14000ad26  lea     r13, cs:140000000h
0x14000ad2d  mov     r10, rbx
0x14000ad30  add     r10, r10
0x14000ad33  cmp     dword ptr [r8+r10*8+4], 3
0x14000ad39  jnb     short loc_14000ADA7
0x14000ad3b  xor     edi, edi
0x14000ad3d  mov     ecx, [r8+r10*8]
0x14000ad41  mov     eax, edi
0x14000ad43  add     rax, rax
0x14000ad46  cmp     ds:rva ConfigSetting[r13+rax*8], ecx
0x14000ad4e  jnz     short loc_14000AD96
0x14000ad50  cmp     ecx, 50000h
0x14000ad56  jnb     short loc_14000AD96
0x14000ad58  movsxd  r14, ds:rva dword_140006064[r13+rax*8]
0x14000ad60  test    r14d, r14d
0x14000ad63  js      short loc_14000AD96
0x14000ad65  mov     esi, [r8+r10*8+4]
0x14000ad6a  mov     ebp, esi
0x14000ad6c  mov     r15d, [r8+r10*8+8]
0x14000ad71  mov     eax, 3
0x14000ad76  test    esi, esi
0x14000ad78  jz      short loc_14000AD7D
0x14000ad7a  lea     eax, [rsi+1]
0x14000ad7d  cmp     ebp, eax
0x14000ad7f  jnb     short loc_14000AD96
0x14000ad81  mov     ecx, ebp
0x14000ad83  shl     rcx, 6
0x14000ad87  add     rcx, r14
0x14000ad8a  inc     ebp
0x14000ad8c  mov     [rcx+r13+77E0h], r15d
0x14000ad94  jmp     short loc_14000AD71
0x14000ad96  inc     edi
0x14000ad98  mov     eax, edi
0x14000ad9a  add     rax, rax
0x14000ad9d  cmp     ds:rva ConfigSetting[r13+rax*8], edx
0x14000ada5  jnz     short loc_14000AD3D
0x14000ada7  inc     r11d
0x14000adaa  inc     rbx
0x14000adad  cmp     r11d, r9d
0x14000adb0  jb      loc_14000AD2D
0x14000adb6  jmp     short loc_14000ADBD
0x14000adb8  mov     edx, 0C000000Dh
0x14000adbd  mov     eax, edx
0x14000adbf  pop     r15
0x14000adc1  pop     r14
0x14000adc3  pop     r13
0x14000adc5  pop     rdi
0x14000adc6  pop     rsi
0x14000adc7  pop     rbp
0x14000adc8  pop     rbx
0x14000adc9  retn
```
