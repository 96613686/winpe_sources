# DRR_GetRoamingTokenFromSet

- ea: `0x18000d054`
- end: `0x18000d107`
- name: `DRR_GetRoamingTokenFromSet`
- size: `179`
- prototype: `const void *__fastcall(__int64, const void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004110`
- `0x180005a30`

## callees

- `0x18000d054`
- `0x18000d886`

## pseudocode

```c
const void *__fastcall DRR_GetRoamingTokenFromSet(__int64 a1, const void *a2)
{
  __int64 v2; // rbx
  int v4; // edi
  const void **v5; // r12
  int v6; // eax
  unsigned int v7; // edi
  const void *v8; // rsi
  int v9; // eax
  unsigned int v10; // esi
  const void *v11; // r14
  int v12; // eax

  v2 = 0;
  if ( a1 )
  {
    v4 = *(_DWORD *)(a1 + 8);
    if ( v4 )
    {
      v5 = *(const void ***)a1;
      v6 = memcmp_0(a2, **(const void ***)a1, 0x60u);
      if ( v6 )
      {
        if ( v6 > 0 )
        {
          v7 = v4 - 1;
          v8 = v5[v7];
          v9 = memcmp_0(a2, v8, 0x60u);
          if ( v9 )
          {
            if ( v9 < 0 )
            {
              v10 = 0;
              if ( v7 > 1 )
              {
                while ( 1 )
                {
                  v11 = v5[(v10 + v7) >> 1];
                  v12 = memcmp_0(a2, v11, 0x60u);
                  if ( !v12 )
                    break;
                  if ( v12 >= 0 )
                    v10 = (v10 + v7) >> 1;
                  else
                    v7 = (v10 + v7) >> 1;
                  if ( v10 + 1 >= v7 )
                    return (const void *)v2;
                }
                return v11;
              }
            }
          }
          else
          {
            return v8;
          }
        }
      }
      else
      {
        return *v5;
      }
    }
  }
  return (const void *)v2;
}

```

## disassembly

```asm
0x18000d054  push    rbx
0x18000d056  push    rbp
0x18000d057  push    rsi
0x18000d058  push    rdi
0x18000d059  push    r12
0x18000d05b  push    r13
0x18000d05d  push    r14
0x18000d05f  push    r15
0x18000d061  sub     rsp, 28h
0x18000d065  xor     ebx, ebx
0x18000d067  mov     r15, rdx
0x18000d06a  test    rcx, rcx
0x18000d06d  jz      loc_18000D0F3
0x18000d073  mov     edi, [rcx+8]
0x18000d076  test    edi, edi
0x18000d078  jz      short loc_18000D0F3
0x18000d07a  mov     r12, [rcx]
0x18000d07d  lea     r13d, [rbx+60h]
0x18000d081  mov     r8d, r13d; Size
0x18000d084  mov     rcx, r15; Buf1
0x18000d087  mov     rdx, [r12]; Buf2
0x18000d08b  call    memcmp_0
0x18000d090  test    eax, eax
0x18000d092  jnz     short loc_18000D09A
0x18000d094  mov     rbx, [r12]
0x18000d098  jmp     short loc_18000D0F3
0x18000d09a  jle     short loc_18000D0F3
0x18000d09c  dec     edi
0x18000d09e  mov     r8, r13; Size
0x18000d0a1  mov     rcx, r15; Buf1
0x18000d0a4  mov     rsi, [r12+rdi*8]
0x18000d0a8  mov     rdx, rsi; Buf2
0x18000d0ab  call    memcmp_0
0x18000d0b0  test    eax, eax
0x18000d0b2  jnz     short loc_18000D0B9
0x18000d0b4  mov     rbx, rsi
0x18000d0b7  jmp     short loc_18000D0F3
0x18000d0b9  jns     short loc_18000D0F3
0x18000d0bb  xor     esi, esi
0x18000d0bd  cmp     edi, 1
0x18000d0c0  jbe     short loc_18000D0F3
0x18000d0c2  lea     eax, [rsi+rdi]
0x18000d0c5  mov     r8, r13; Size
0x18000d0c8  shr     eax, 1
0x18000d0ca  mov     rcx, r15; Buf1
0x18000d0cd  mov     ebp, eax
0x18000d0cf  mov     r14, [r12+rax*8]
0x18000d0d3  mov     rdx, r14; Buf2
0x18000d0d6  call    memcmp_0
0x18000d0db  test    eax, eax
0x18000d0dd  jz      short loc_18000D0F0
0x18000d0df  jns     short loc_18000D0E5
0x18000d0e1  mov     edi, ebp
0x18000d0e3  jmp     short loc_18000D0E7
0x18000d0e5  mov     esi, ebp
0x18000d0e7  lea     eax, [rsi+1]
0x18000d0ea  cmp     eax, edi
0x18000d0ec  jb      short loc_18000D0C2
0x18000d0ee  jmp     short loc_18000D0F3
0x18000d0f0  mov     rbx, r14
0x18000d0f3  mov     rax, rbx
0x18000d0f6  add     rsp, 28h
0x18000d0fa  pop     r15
0x18000d0fc  pop     r14
0x18000d0fe  pop     r13
0x18000d100  pop     r12
0x18000d102  pop     rdi
0x18000d103  pop     rsi
0x18000d104  pop     rbp
0x18000d105  pop     rbx
0x18000d106  retn
```
