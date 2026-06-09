# ComputeFormat12CmapData

- ea: `0x18000d808`
- end: `0x18000d8dc`
- name: `ComputeFormat12CmapData`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a688`
- `0x1800118bc`

## callees

- `0x18000d808`
- `0x18001a2cc`

## pseudocode

```c
__int64 __fastcall ComputeFormat12CmapData(_DWORD *a1, __int64 a2, _DWORD *a3, __int64 a4, unsigned int a5)
{
  unsigned int v5; // r10d
  __int64 v6; // rdi
  unsigned int v9; // ebp
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 result; // rax
  unsigned int v16; // ecx

  v5 = 0;
  v6 = 0;
  *a3 = 0;
  if ( a5 )
  {
    v9 = a5 - 1;
    do
    {
      v10 = v5;
      if ( v5 < v9 )
      {
        do
        {
          v11 = v5 + 1;
          if ( *(_DWORD *)(a4 + 8LL * v5) + 1 != *(_DWORD *)(a4 + 8 * v11) )
            break;
          if ( *(_DWORD *)(a4 + 8LL * v5 + 4) + 1 != *(_DWORD *)(a4 + 8 * v11 + 4) )
            break;
          ++v5;
        }
        while ( (unsigned int)v11 < v9 );
      }
      v12 = 3 * v6;
      *(_DWORD *)(a2 + 4 * v12) = *(_DWORD *)(a4 + 8 * v10);
      v13 = v5++;
      v6 = (unsigned int)(v6 + 1);
      *(_DWORD *)(a2 + 4 * v12 + 4) = *(_DWORD *)(a4 + 8 * v13);
      *(_DWORD *)(a2 + 4 * v12 + 8) = *(_DWORD *)(a4 + 8 * v10 + 4);
    }
    while ( v5 < a5 );
    *a3 = v6;
  }
  *a1 = 12;
  v14 = v6 * (unsigned __int16)GetGenericSize(&FORMAT12_GROUPS_CONTROL);
  result = GetGenericSize(&CMAP_FORMAT12_CONTROL);
  v16 = v14 + (unsigned __int16)result;
  a1[1] = v16;
  if ( v16 < (unsigned int)v6 )
  {
    a1[1] = 0;
    LODWORD(v6) = 0;
  }
  a1[3] = v6;
  return result;
}

```

## disassembly

```asm
0x18000d808  push    rbx
0x18000d80a  push    rbp
0x18000d80b  push    rsi
0x18000d80c  push    rdi
0x18000d80d  push    r14
0x18000d80f  push    r15
0x18000d811  sub     rsp, 28h
0x18000d815  mov     r11d, [rsp+58h+arg_20]
0x18000d81d  xor     r10d, r10d
0x18000d820  xor     edi, edi
0x18000d822  mov     [r8], r10d
0x18000d825  mov     r14, rdx
0x18000d828  mov     rsi, rcx
0x18000d82b  test    r11d, r11d
0x18000d82e  jz      short loc_18000D893
0x18000d830  lea     ebp, [r11-1]
0x18000d834  mov     r15d, r10d
0x18000d837  cmp     r10d, ebp
0x18000d83a  jnb     short loc_18000D864
0x18000d83c  mov     edx, r10d
0x18000d83f  lea     ecx, [r10+1]
0x18000d843  mov     eax, [r9+rdx*8]
0x18000d847  inc     eax
0x18000d849  cmp     eax, [r9+rcx*8]
0x18000d84d  jnz     short loc_18000D864
0x18000d84f  mov     eax, [r9+rdx*8+4]
0x18000d854  inc     eax
0x18000d856  cmp     eax, [r9+rcx*8+4]
0x18000d85b  jnz     short loc_18000D864
0x18000d85d  mov     r10d, ecx
0x18000d860  cmp     ecx, ebp
0x18000d862  jb      short loc_18000D83C
0x18000d864  mov     eax, [r9+r15*8]
0x18000d868  lea     rdx, [rdi+rdi*2]
0x18000d86c  mov     [r14+rdx*4], eax
0x18000d870  mov     ecx, r10d
0x18000d873  inc     r10d
0x18000d876  inc     edi
0x18000d878  mov     ecx, [r9+rcx*8]
0x18000d87c  mov     [r14+rdx*4+4], ecx
0x18000d881  mov     eax, [r9+r15*8+4]
0x18000d886  mov     [r14+rdx*4+8], eax
0x18000d88b  cmp     r10d, r11d
0x18000d88e  jb      short loc_18000D834
0x18000d890  mov     [r8], edi
0x18000d893  lea     rcx, FORMAT12_GROUPS_CONTROL
0x18000d89a  mov     dword ptr [rsi], 0Ch
0x18000d8a0  call    GetGenericSize
0x18000d8a5  movzx   ebx, ax
0x18000d8a8  lea     rcx, CMAP_FORMAT12_CONTROL
0x18000d8af  imul    ebx, edi
0x18000d8b2  call    GetGenericSize
0x18000d8b7  movzx   ecx, ax
0x18000d8ba  add     ecx, ebx
0x18000d8bc  mov     [rsi+4], ecx
0x18000d8bf  cmp     ecx, edi
0x18000d8c1  jnb     short loc_18000D8CC
0x18000d8c3  mov     dword ptr [rsi+4], 0
0x18000d8ca  xor     edi, edi
0x18000d8cc  mov     [rsi+0Ch], edi
0x18000d8cf  add     rsp, 28h
0x18000d8d3  pop     r15
0x18000d8d5  pop     r14
0x18000d8d7  pop     rdi
0x18000d8d8  pop     rsi
0x18000d8d9  pop     rbp
0x18000d8da  pop     rbx
0x18000d8db  retn
```
