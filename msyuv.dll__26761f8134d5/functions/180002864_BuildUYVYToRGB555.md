# BuildUYVYToRGB555

- ea: `0x180002864`
- end: `0x1800029c9`
- name: `BuildUYVYToRGB555`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021c8`

## callees

- `0x180002864`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000288f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000288f`

## pseudocode

```c
_WORD *__fastcall BuildUYVYToRGB555(__int64 a1)
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
            LOBYTE(v8) = 0;
        }
        else
        {
          LOBYTE(v8) = -1;
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
        *v3++ = ((unsigned int)v10 >> 3) & 0x1F | (4 * (v9 & 0xF8 | (32 * (v8 & 0xF8))));
      }
      while ( v2 < 0x8000u );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002864  push    rbx
0x180002866  push    rbp
0x180002867  push    rsi
0x180002868  push    rdi
0x180002869  push    r13
0x18000286b  push    r14
0x18000286d  sub     rsp, 28h
0x180002871  mov     rax, [rcx+8]
0x180002875  test    rax, rax
0x180002878  jnz     loc_1800029BC
0x18000287e  mov     edx, 10000h; dwSize
0x180002883  lea     r9d, [rax+4]; flProtect
0x180002887  xor     ecx, ecx; lpAddress
0x180002889  mov     r8d, 3000h; flAllocationType
0x18000288f  call    cs:__imp_VirtualAlloc
0x180002895  mov     [rsp+58h+arg_0], rax
0x18000289a  test    rax, rax
0x18000289d  jz      loc_1800029BC
0x1800028a3  xor     edi, edi
0x1800028a5  mov     ebp, 0FFh
0x1800028aa  mov     rsi, rax
0x1800028ad  lea     r11d, [rdi+1Fh]
0x1800028b1  lea     r14d, [rbp-7]
0x1800028b5  lea     r13d, [rdi+10h]
0x1800028b9  movzx   r8d, di
0x1800028bd  mov     ebx, r8d
0x1800028c0  mov     ecx, r8d
0x1800028c3  shr     ebx, 2
0x1800028c6  and     ecx, r11d
0x1800028c9  shr     r8d, 7
0x1800028cd  and     ebx, r14d
0x1800028d0  and     r8d, r14d
0x1800028d3  cmp     r8d, 0EBh
0x1800028da  jbe     short loc_1800028E4
0x1800028dc  mov     r8d, 0EBh
0x1800028e2  jmp     short loc_1800028EB
0x1800028e4  cmp     r8d, r13d
0x1800028e7  cmovb   r8d, r13d
0x1800028eb  shl     r8d, 0Ah
0x1800028ef  lea     eax, [rcx-10h]
0x1800028f2  imul    eax, 2BE0h
0x1800028f8  add     eax, r8d
0x1800028fb  cdq
0x1800028fc  and     edx, 3FFh
0x180002902  add     eax, edx
0x180002904  sar     eax, 0Ah
0x180002907  mov     r9d, eax
0x18000290a  cmp     eax, ebp
0x18000290c  jle     short loc_180002913
0x18000290e  mov     r9d, ebp
0x180002911  jmp     short loc_18000291C
0x180002913  xor     eax, eax
0x180002915  test    r9d, r9d
0x180002918  cmovs   r9d, eax
0x18000291c  imul    eax, ecx, 1658h
0x180002922  imul    ecx, ebx, 0FFFFFEA8h
0x180002928  sub     ecx, eax
0x18000292a  lea     eax, [rcx+21180h]
0x180002930  add     eax, r8d
0x180002933  cdq
0x180002934  and     edx, 3FFh
0x18000293a  add     eax, edx
0x18000293c  sar     eax, 0Ah
0x18000293f  mov     r10d, eax
0x180002942  cmp     eax, ebp
0x180002944  jle     short loc_18000294B
0x180002946  mov     r10d, ebp
0x180002949  jmp     short loc_180002954
0x18000294b  xor     eax, eax
0x18000294d  test    r10d, r10d
0x180002950  cmovs   r10d, eax
0x180002954  lea     eax, [rbx-80h]
0x180002957  imul    eax, 6EEh
0x18000295d  add     eax, r8d
0x180002960  cdq
0x180002961  and     edx, 3FFh
0x180002967  add     eax, edx
0x180002969  sar     eax, 0Ah
0x18000296c  mov     ecx, eax
0x18000296e  cmp     eax, ebp
0x180002970  jle     short loc_180002976
0x180002972  mov     ecx, ebp
0x180002974  jmp     short loc_18000297D
0x180002976  xor     eax, eax
0x180002978  test    ecx, ecx
0x18000297a  cmovs   ecx, eax
0x18000297d  and     r9w, r14w
0x180002981  shr     ecx, 3
0x180002984  shl     r9w, 5
0x180002989  and     r10w, r14w
0x18000298d  or      r9w, r10w
0x180002991  and     cx, r11w
0x180002995  shl     r9w, 2
0x18000299a  inc     di
0x18000299d  or      r9w, cx
0x1800029a1  mov     eax, 8000h
0x1800029a6  mov     [rsi], r9w
0x1800029aa  add     rsi, 2
0x1800029ae  cmp     di, ax
0x1800029b1  jb      loc_1800028B9
0x1800029b7  mov     rax, [rsp+58h+arg_0]
0x1800029bc  add     rsp, 28h
0x1800029c0  pop     r14
0x1800029c2  pop     r13
0x1800029c4  pop     rdi
0x1800029c5  pop     rsi
0x1800029c6  pop     rbp
0x1800029c7  pop     rbx
0x1800029c8  retn
```
