# DevAuthGetDeviceInfo

- ea: `0x180001450`
- end: `0x1800015ea`
- name: `DevAuthGetDeviceInfo`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001700`

## callees

- `0x180001450`
- `0x180001cf4`
- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall DevAuthGetDeviceInfo(_QWORD *a1, __int64 a2)
{
  unsigned int SessionDataIndex; // eax
  __int64 v5; // r11
  __int64 v6; // rbx
  __int64 v7; // rax
  _OWORD *v8; // rcx
  _OWORD *v9; // rdx
  __int128 v10; // xmm1
  size_t v11; // r8
  int v12; // eax

  if ( !a2 )
    return 3221225485LL;
  *(_DWORD *)a2 = 1;
  SessionDataIndex = SDT_GetSessionDataIndex((__int64)P, a1);
  if ( SessionDataIndex != -1 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL * SessionDataIndex);
    if ( v6 )
    {
      if ( *(_BYTE *)(v6 + 32) == 1 )
      {
        if ( *(_BYTE *)(v6 + 40) == 2 )
        {
          *(_DWORD *)(a2 + 4) = 1;
          *(_WORD *)(a2 + 8) = *(_WORD *)(v6 + 1256);
          *(_WORD *)(a2 + 10) = *(_WORD *)(v6 + 1258);
          memmove((void *)(a2 + 20), (const void *)(v6 + 166), *(unsigned int *)(v6 + 1192));
          *(_DWORD *)(a2 + 16) = *(_DWORD *)(v6 + 1192);
          v12 = *(_DWORD *)(v6 + 1192) + 84;
LABEL_14:
          *(_DWORD *)(a2 + 12) = v12;
          return 0;
        }
      }
      else
      {
        if ( *(_BYTE *)(v6 + 32) != 2 )
          return 3221225485LL;
        v7 = 2;
        if ( *(_BYTE *)(v6 + 40) == 2 )
        {
          *(_DWORD *)(a2 + 4) = 2;
          v8 = (_OWORD *)(a2 + 156);
          v9 = (_OWORD *)(v6 + 320);
          do
          {
            *v8 = *v9;
            v8[1] = v9[1];
            v8[2] = v9[2];
            v8[3] = v9[3];
            v8[4] = v9[4];
            v8[5] = v9[5];
            v8[6] = v9[6];
            v10 = v9[7];
            v9 += 8;
            v8[7] = v10;
            v8 += 8;
            --v7;
          }
          while ( v7 );
          *(_WORD *)(a2 + 8) = *(unsigned __int8 *)(v6 + 325);
          *(_WORD *)(a2 + 10) = *(unsigned __int8 *)(v6 + 326);
          *(_DWORD *)(a2 + 16) = *(_DWORD *)(v6 + 120);
          *(_DWORD *)(a2 + 20) = *(_DWORD *)(v6 + 124);
          v11 = (unsigned int)(32 * *(_DWORD *)(v6 + 124));
          *(_DWORD *)(a2 + 24) = v11;
          memmove((void *)(a2 + 28), (const void *)(v6 + 128), v11);
          v12 = 480;
          *(_OWORD *)(a2 + 124) = *(_OWORD *)(v6 + 224);
          *(_OWORD *)(a2 + 140) = *(_OWORD *)(v6 + 240);
          goto LABEL_14;
        }
      }
      return 3221225701LL;
    }
  }
  return 3221225524LL;
}

```

## disassembly

```asm
0x180001450  mov     [rsp+arg_0], rbx
0x180001455  push    rdi
0x180001456  sub     rsp, 20h
0x18000145a  mov     rdi, rdx
0x18000145d  test    rdx, rdx
0x180001460  jnz     short loc_18000146C
0x180001462  mov     eax, 0C000000Dh
0x180001467  jmp     loc_1800015DE
0x18000146c  mov     dword ptr [rdx], 1
0x180001472  mov     rdx, rcx
0x180001475  mov     r11, qword ptr cs:P
0x18000147c  mov     rcx, r11
0x18000147f  call    _SDT_GetSessionDataIndex
0x180001484  cmp     eax, 0FFFFFFFFh
0x180001487  jz      loc_1800015D9
0x18000148d  mov     ecx, eax
0x18000148f  mov     rax, [r11+8]
0x180001493  mov     rbx, [rax+rcx*8]
0x180001497  test    rbx, rbx
0x18000149a  jz      loc_1800015D9
0x1800014a0  movzx   ecx, byte ptr [rbx+20h]
0x1800014a4  sub     ecx, 1
0x1800014a7  jz      loc_18000157B
0x1800014ad  cmp     ecx, 1
0x1800014b0  jnz     short loc_180001462
0x1800014b2  lea     eax, [rcx+1]
0x1800014b5  cmp     [rbx+28h], al
0x1800014b8  jnz     loc_180001585
0x1800014be  mov     [rdi+4], eax
0x1800014c1  lea     rcx, [rdi+9Ch]
0x1800014c8  lea     rdx, [rbx+140h]
0x1800014cf  lea     r8d, [rax+7Eh]
0x1800014d3  movups  xmm0, xmmword ptr [rdx]
0x1800014d6  movups  xmmword ptr [rcx], xmm0
0x1800014d9  movups  xmm1, xmmword ptr [rdx+10h]
0x1800014dd  movups  xmmword ptr [rcx+10h], xmm1
0x1800014e1  movups  xmm0, xmmword ptr [rdx+20h]
0x1800014e5  movups  xmmword ptr [rcx+20h], xmm0
0x1800014e9  movups  xmm1, xmmword ptr [rdx+30h]
0x1800014ed  movups  xmmword ptr [rcx+30h], xmm1
0x1800014f1  movups  xmm0, xmmword ptr [rdx+40h]
0x1800014f5  movups  xmmword ptr [rcx+40h], xmm0
0x1800014f9  movups  xmm1, xmmword ptr [rdx+50h]
0x1800014fd  movups  xmmword ptr [rcx+50h], xmm1
0x180001501  movups  xmm0, xmmword ptr [rdx+60h]
0x180001505  movups  xmmword ptr [rcx+60h], xmm0
0x180001509  movups  xmm1, xmmword ptr [rdx+70h]
0x18000150d  add     rdx, r8
0x180001510  movups  xmmword ptr [rcx+70h], xmm1
0x180001514  add     rcx, r8
0x180001517  sub     rax, 1
0x18000151b  jnz     short loc_1800014D3
0x18000151d  movzx   eax, byte ptr [rbx+145h]
0x180001524  lea     rdx, [rbx+80h]; Src
0x18000152b  mov     [rdi+8], ax
0x18000152f  lea     rcx, [rdi+1Ch]; void *
0x180001533  movzx   eax, byte ptr [rbx+146h]
0x18000153a  mov     [rdi+0Ah], ax
0x18000153e  mov     eax, [rbx+78h]
0x180001541  mov     [rdi+10h], eax
0x180001544  mov     eax, [rbx+7Ch]
0x180001547  mov     [rdi+14h], eax
0x18000154a  mov     r8d, [rbx+7Ch]
0x18000154e  shl     r8d, 5; Size
0x180001552  mov     [rdi+18h], r8d
0x180001556  call    memmove
0x18000155b  movups  xmm0, xmmword ptr [rbx+0E0h]
0x180001562  mov     eax, 1E0h
0x180001567  movups  xmmword ptr [rdi+7Ch], xmm0
0x18000156b  movups  xmm1, xmmword ptr [rbx+0F0h]
0x180001572  movups  xmmword ptr [rdi+8Ch], xmm1
0x180001579  jmp     short loc_1800015D2
0x18000157b  mov     eax, 2
0x180001580  cmp     [rbx+28h], al
0x180001583  jz      short loc_18000158C
0x180001585  mov     eax, 0C00000E5h
0x18000158a  jmp     short loc_1800015DE
0x18000158c  mov     dword ptr [rdi+4], 1
0x180001593  lea     rdx, [rbx+0A6h]; Src
0x18000159a  movzx   eax, word ptr [rbx+4E8h]
0x1800015a1  lea     rcx, [rdi+14h]; void *
0x1800015a5  mov     [rdi+8], ax
0x1800015a9  movzx   eax, word ptr [rbx+4EAh]
0x1800015b0  mov     [rdi+0Ah], ax
0x1800015b4  mov     r8d, [rbx+4A8h]; Size
0x1800015bb  call    memmove
0x1800015c0  mov     eax, [rbx+4A8h]
0x1800015c6  mov     [rdi+10h], eax
0x1800015c9  mov     eax, [rbx+4A8h]
0x1800015cf  add     eax, 54h ; 'T'
0x1800015d2  mov     [rdi+0Ch], eax
0x1800015d5  xor     eax, eax
0x1800015d7  jmp     short loc_1800015DE
0x1800015d9  mov     eax, 0C0000034h
0x1800015de  mov     rbx, [rsp+28h+arg_0]
0x1800015e3  add     rsp, 20h
0x1800015e7  pop     rdi
0x1800015e8  retn
```
