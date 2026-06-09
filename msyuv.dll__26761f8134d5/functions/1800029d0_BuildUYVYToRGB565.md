# BuildUYVYToRGB565

- ea: `0x1800029d0`
- end: `0x180002b4d`
- name: `BuildUYVYToRGB565`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021c8`

## callees

- `0x1800029d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002a00`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002a00`

## pseudocode

```c
_WORD *__fastcall BuildUYVYToRGB565(__int64 a1)
{
  _WORD *result; // rax
  unsigned __int16 v2; // di
  _WORD *v3; // rsi
  int v4; // ecx
  int v5; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  int v10; // ecx

  result = *(_WORD **)(a1 + 8);
  if ( !result )
  {
    result = VirtualAlloc(0, 0x10000u, 0x3000u, 4u);
    if ( result )
    {
      v2 = 0;
      v3 = result;
      do
      {
        v4 = v2 & 0x1F;
        v5 = (v2 >> 2) & 0xF8;
        v6 = (v2 >> 7) & 0xF8;
        if ( v6 <= 0xEB )
        {
          if ( v6 < 0x10 )
            v6 = 16;
        }
        else
        {
          v6 = 235;
        }
        v7 = v6 << 10;
        v8 = (int)(v7 + 11232 * (v4 - 16)) / 1024;
        if ( v8 <= 255 )
        {
          if ( v8 < 0 )
            LOWORD(v8) = 0;
        }
        else
        {
          LOWORD(v8) = 255;
        }
        v9 = (int)(v7 + -344 * v5 - 5720 * v4 + 135552) / 1024;
        if ( v9 <= 255 )
        {
          if ( v9 < 0 )
            LOBYTE(v9) = 0;
        }
        else
        {
          LOBYTE(v9) = -1;
        }
        v10 = (int)(v7 + 1774 * (v5 - 128)) / 1024;
        if ( v10 <= 255 )
        {
          if ( v10 < 0 )
            v10 = 0;
        }
        else
        {
          v10 = 255;
        }
        ++v2;
        *v3++ = ((unsigned int)v10 >> 3) & 0x1F | (8 * (v9 & 0xFC | (32 * (v8 & 0xFFF8))));
      }
      while ( v2 < 0x8000u );
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_8], rbx
0x1800029d5  mov     [rsp+arg_10], rbp
0x1800029da  push    rsi
0x1800029db  push    rdi
0x1800029dc  push    r12
0x1800029de  sub     rsp, 20h
0x1800029e2  mov     rax, [rcx+8]
0x1800029e6  test    rax, rax
0x1800029e9  jnz     loc_180002B3A
0x1800029ef  mov     edx, 10000h; dwSize
0x1800029f4  lea     r9d, [rax+4]; flProtect
0x1800029f8  xor     ecx, ecx; lpAddress
0x1800029fa  mov     r8d, 3000h; flAllocationType
0x180002a00  call    cs:__imp_VirtualAlloc
0x180002a06  mov     [rsp+38h+arg_0], rax
0x180002a0b  test    rax, rax
0x180002a0e  jz      loc_180002B3A
0x180002a14  xor     edi, edi
0x180002a16  mov     rsi, rax
0x180002a19  mov     ebp, 0FFh
0x180002a1e  lea     r11d, [rdi+1Fh]
0x180002a22  lea     r12d, [rdi+10h]
0x180002a26  movzx   r8d, di
0x180002a2a  mov     ebx, r8d
0x180002a2d  mov     ecx, r8d
0x180002a30  shr     ebx, 2
0x180002a33  and     ecx, r11d
0x180002a36  shr     r8d, 7
0x180002a3a  and     ebx, 0F8h
0x180002a40  and     r8d, 0F8h
0x180002a47  cmp     r8d, 0EBh
0x180002a4e  jbe     short loc_180002A58
0x180002a50  mov     r8d, 0EBh
0x180002a56  jmp     short loc_180002A5F
0x180002a58  cmp     r8d, r12d
0x180002a5b  cmovb   r8d, r12d
0x180002a5f  shl     r8d, 0Ah
0x180002a63  lea     eax, [rcx-10h]
0x180002a66  imul    eax, 2BE0h
0x180002a6c  add     eax, r8d
0x180002a6f  cdq
0x180002a70  and     edx, 3FFh
0x180002a76  add     eax, edx
0x180002a78  sar     eax, 0Ah
0x180002a7b  mov     r9d, eax
0x180002a7e  cmp     eax, ebp
0x180002a80  jle     short loc_180002A87
0x180002a82  mov     r9d, ebp
0x180002a85  jmp     short loc_180002A90
0x180002a87  xor     eax, eax
0x180002a89  test    r9d, r9d
0x180002a8c  cmovs   r9d, eax
0x180002a90  imul    eax, ecx, 1658h
0x180002a96  imul    ecx, ebx, 0FFFFFEA8h
0x180002a9c  sub     ecx, eax
0x180002a9e  lea     eax, [rcx+21180h]
0x180002aa4  add     eax, r8d
0x180002aa7  cdq
0x180002aa8  and     edx, 3FFh
0x180002aae  add     eax, edx
0x180002ab0  sar     eax, 0Ah
0x180002ab3  mov     r10d, eax
0x180002ab6  cmp     eax, ebp
0x180002ab8  jle     short loc_180002ABF
0x180002aba  mov     r10d, ebp
0x180002abd  jmp     short loc_180002AC8
0x180002abf  xor     eax, eax
0x180002ac1  test    r10d, r10d
0x180002ac4  cmovs   r10d, eax
0x180002ac8  lea     eax, [rbx-80h]
0x180002acb  imul    eax, 6EEh
0x180002ad1  add     eax, r8d
0x180002ad4  cdq
0x180002ad5  and     edx, 3FFh
0x180002adb  add     eax, edx
0x180002add  sar     eax, 0Ah
0x180002ae0  mov     ecx, eax
0x180002ae2  cmp     eax, ebp
0x180002ae4  jle     short loc_180002AEA
0x180002ae6  mov     ecx, ebp
0x180002ae8  jmp     short loc_180002AF1
0x180002aea  xor     eax, eax
0x180002aec  test    ecx, ecx
0x180002aee  cmovs   ecx, eax
0x180002af1  mov     eax, 0FFF8h
0x180002af6  shr     ecx, 3
0x180002af9  and     r9w, ax
0x180002afd  and     cx, r11w
0x180002b01  shl     r9w, 5
0x180002b06  mov     eax, 0FCh
0x180002b0b  and     r10w, ax
0x180002b0f  inc     di
0x180002b12  or      r9w, r10w
0x180002b16  mov     eax, 8000h
0x180002b1b  shl     r9w, 3
0x180002b20  or      r9w, cx
0x180002b24  mov     [rsi], r9w
0x180002b28  add     rsi, 2
0x180002b2c  cmp     di, ax
0x180002b2f  jb      loc_180002A26
0x180002b35  mov     rax, [rsp+38h+arg_0]
0x180002b3a  mov     rbx, [rsp+38h+arg_8]
0x180002b3f  mov     rbp, [rsp+38h+arg_10]
0x180002b44  add     rsp, 20h
0x180002b48  pop     r12
0x180002b4a  pop     rdi
0x180002b4b  pop     rsi
0x180002b4c  retn
```
