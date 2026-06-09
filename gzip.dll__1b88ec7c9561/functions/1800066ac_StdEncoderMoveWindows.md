# StdEncoderMoveWindows

- ea: `0x1800066ac`
- end: `0x180006751`
- name: `StdEncoderMoveWindows`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c40`

## callees

- `0x1800066ac`
- `0x180006ac9`

## pseudocode

```c
__int16 __fastcall StdEncoderMoveWindows(__int64 a1)
{
  int v1; // eax
  char *v3; // rdi
  __int64 i; // rdx
  __int16 v5; // ax
  __int64 j; // rdx

  v1 = *(_DWORD *)(a1 + 32);
  if ( v1 >= 0x10000 )
  {
    v3 = *(char **)(a1 + 80);
    memcpy_0(v3, &v3[v1 - 0x8000], 0x8000u);
    for ( i = 0; i != 0x2000; ++i )
    {
      v5 = 0;
      if ( *(unsigned __int16 *)&v3[2 * i + 131850] - 0x8000 > 0 )
        v5 = *(_WORD *)&v3[2 * i + 131850] + 0x8000;
      *(_WORD *)&v3[2 * i + 131850] = v5;
    }
    for ( j = 0; j != 0x8000; ++j )
    {
      LOWORD(v1) = 0;
      if ( *(unsigned __int16 *)&v3[2 * j + 65798] - 0x8000 > 0 )
        LOWORD(v1) = *(_WORD *)&v3[2 * j + 65798] + 0x8000;
      *(_WORD *)&v3[2 * j + 65798] = v1;
    }
    *(_DWORD *)(a1 + 32) = 0x8000;
    *(_DWORD *)(a1 + 36) = 0x8000;
  }
  return v1;
}

```

## disassembly

```asm
0x1800066ac  mov     [rsp+arg_0], rbx
0x1800066b1  mov     [rsp+arg_8], rsi
0x1800066b6  push    rdi
0x1800066b7  sub     rsp, 20h
0x1800066bb  mov     eax, [rcx+20h]
0x1800066be  mov     rbx, rcx
0x1800066c1  cmp     eax, 10000h
0x1800066c6  jl      short loc_180006741
0x1800066c8  mov     rdi, [rcx+50h]
0x1800066cc  add     eax, 0FFFF8000h
0x1800066d1  movsxd  rdx, eax
0x1800066d4  mov     esi, 8000h
0x1800066d9  add     rdx, rdi; Src
0x1800066dc  mov     r8d, esi; Size
0x1800066df  mov     rcx, rdi; void *
0x1800066e2  call    memcpy_0
0x1800066e7  xor     edx, edx
0x1800066e9  movzx   ecx, word ptr [rdi+rdx*2+2030Ah]
0x1800066f1  xor     eax, eax
0x1800066f3  add     ecx, 0FFFF8000h
0x1800066f9  test    ecx, ecx
0x1800066fb  cmovg   ax, cx
0x1800066ff  mov     [rdi+rdx*2+2030Ah], ax
0x180006707  inc     rdx
0x18000670a  cmp     rdx, 2000h
0x180006711  jnz     short loc_1800066E9
0x180006713  xor     edx, edx
0x180006715  movzx   ecx, word ptr [rdi+rdx*2+10106h]
0x18000671d  xor     eax, eax
0x18000671f  add     ecx, 0FFFF8000h
0x180006725  test    ecx, ecx
0x180006727  cmovg   ax, cx
0x18000672b  mov     [rdi+rdx*2+10106h], ax
0x180006733  inc     rdx
0x180006736  cmp     rdx, rsi
0x180006739  jnz     short loc_180006715
0x18000673b  mov     [rbx+20h], esi
0x18000673e  mov     [rbx+24h], esi
0x180006741  mov     rbx, [rsp+28h+arg_0]
0x180006746  mov     rsi, [rsp+28h+arg_8]
0x18000674b  add     rsp, 20h
0x18000674f  pop     rdi
0x180006750  retn
```
