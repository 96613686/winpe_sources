# FastEncoderMoveWindows

- ea: `0x180001b90`
- end: `0x180001c37`
- name: `FastEncoderMoveWindows`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001b90`
- `0x180006ac9`

## pseudocode

```c
__int64 __fastcall FastEncoderMoveWindows(__int64 a1)
{
  char *v2; // rcx
  char *v3; // rdi
  char *v4; // rbx
  __int64 i; // rdx
  __int16 v6; // ax
  __int64 result; // rax
  __int16 v8; // cx

  v2 = *(char **)(a1 + 96);
  v3 = v2 + 33546;
  v4 = v2 + 16646;
  memcpy_0(v2, &v2[*(_DWORD *)(a1 + 32) - 0x2000], 0x2000u);
  for ( i = 0; i != 2048; ++i )
  {
    v6 = 0;
    if ( *(unsigned __int16 *)&v3[2 * i] - 0x2000 > 0 )
      v6 = *(_WORD *)&v3[2 * i] - 0x2000;
    *(_WORD *)&v3[2 * i] = v6;
  }
  for ( result = 0; result != 0x2000; ++result )
  {
    v8 = 0;
    if ( *(unsigned __int16 *)&v4[2 * result] - 0x2000 > 0 )
      v8 = *(_WORD *)&v4[2 * result] - 0x2000;
    *(_WORD *)&v4[2 * result] = v8;
  }
  *(_DWORD *)(a1 + 32) = 0x2000;
  *(_DWORD *)(a1 + 36) = 0x2000;
  return result;
}

```

## disassembly

```asm
0x180001b90  mov     [rsp+arg_0], rbx
0x180001b95  mov     [rsp+arg_8], rsi
0x180001b9a  push    rdi
0x180001b9b  sub     rsp, 20h
0x180001b9f  mov     rsi, rcx
0x180001ba2  mov     r8d, 2000h; Size
0x180001ba8  mov     rcx, [rcx+60h]; void *
0x180001bac  mov     eax, [rsi+20h]
0x180001baf  sub     eax, 2000h
0x180001bb4  lea     rdi, [rcx+830Ah]
0x180001bbb  movsxd  rdx, eax
0x180001bbe  lea     rbx, [rcx+4106h]
0x180001bc5  add     rdx, rcx; Src
0x180001bc8  call    memcpy_0
0x180001bcd  xor     edx, edx
0x180001bcf  nop
0x180001bd0  movzx   ecx, word ptr [rdi+rdx*2]
0x180001bd4  xor     eax, eax
0x180001bd6  add     ecx, 0FFFFE000h
0x180001bdc  test    ecx, ecx
0x180001bde  cmovg   ax, cx
0x180001be2  mov     [rdi+rdx*2], ax
0x180001be6  inc     rdx
0x180001be9  cmp     rdx, 800h
0x180001bf0  jnz     short loc_180001BD0
0x180001bf2  xor     eax, eax
0x180001bf4  nop     dword ptr [rax+00h]
0x180001bf8  nop     dword ptr [rax+rax+00000000h]
0x180001c00  movzx   edx, word ptr [rbx+rax*2]
0x180001c04  xor     ecx, ecx
0x180001c06  add     edx, 0FFFFE000h
0x180001c0c  test    edx, edx
0x180001c0e  cmovg   cx, dx
0x180001c12  mov     [rbx+rax*2], cx
0x180001c16  inc     rax
0x180001c19  cmp     rax, 2000h
0x180001c1f  jnz     short loc_180001C00
0x180001c21  mov     rbx, [rsp+28h+arg_0]
0x180001c26  mov     [rsi+20h], eax
0x180001c29  mov     [rsi+24h], eax
0x180001c2c  mov     rsi, [rsp+28h+arg_8]
0x180001c31  add     rsp, 20h
0x180001c35  pop     rdi
0x180001c36  retn
```
