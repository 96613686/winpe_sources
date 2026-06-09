# ASN1DEREncFlushBlkElement

- ea: `0x1800070f0`
- end: `0x180007253`
- name: `ASN1DEREncFlushBlkElement`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a7f0`

## callees

- `0x1800070f0`
- `0x180007260`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007218`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007218`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000723e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000723e`

## pseudocode

```c
__int64 __fastcall ASN1DEREncFlushBlkElement(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // eax
  unsigned int v4; // edx
  unsigned int i; // r9d
  __int64 v6; // rax
  unsigned int v7; // r8d
  unsigned __int8 *v8; // r11
  unsigned int v9; // esi
  unsigned __int8 *v10; // r10
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  __int64 result; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  unsigned int j; // r10d
  HLOCAL v18; // rax
  HLOCAL v19; // rsi

  v1 = *(_QWORD *)(a1 + 16);
  if ( !(unsigned int)ASN1BEREncFlush(v1) )
    return 0;
  v3 = *(_DWORD *)(a1 + 24);
  v4 = *(_DWORD *)(a1 + 28);
  if ( v4 >= v3 )
  {
    v18 = LocalAlloc(0x40u, 32LL * v3);
    v19 = v18;
    if ( v18 )
    {
      memcpy_0(v18, *(const void **)(a1 + 32), 16LL * *(unsigned int *)(a1 + 24));
      LocalFree(*(HLOCAL *)(a1 + 32));
      *(_DWORD *)(a1 + 24) *= 2;
      v4 = *(_DWORD *)(a1 + 28);
      *(_QWORD *)(a1 + 32) = v19;
      goto LABEL_3;
    }
    return 0;
  }
LABEL_3:
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) & 0x400) != 0 )
  {
    for ( i = 0; i < v4; ++i )
    {
      v6 = *(_QWORD *)(a1 + 32);
      v7 = *(_DWORD *)(v1 + 28);
      v8 = *(unsigned __int8 **)(v1 + 16);
      v9 = *(_DWORD *)(v6 + 16LL * i + 8);
      v10 = *(unsigned __int8 **)(v6 + 16LL * i);
      if ( v7 >= v9 )
        v7 = *(_DWORD *)(v6 + 16LL * i + 8);
      while ( v7 )
      {
        v11 = *v8;
        --v7;
        v12 = *v10;
        ++v8;
        ++v10;
        v13 = v11 - v12;
        if ( v13 )
          goto LABEL_10;
      }
      v13 = *(_DWORD *)(v1 + 28) - v9;
LABEL_10:
      if ( v13 <= 0 )
      {
        v16 = *(unsigned int *)(a1 + 28);
        for ( j = *(_DWORD *)(a1 + 28) - i; j; --j )
        {
          *(_OWORD *)(*(_QWORD *)(a1 + 32) + 16 * v16) = *(_OWORD *)(*(_QWORD *)(a1 + 32)
                                                                   + 16LL * (unsigned int)(v16 - 1));
          v16 = (unsigned int)(v16 - 1);
        }
        break;
      }
    }
  }
  else
  {
    i = v4;
  }
  result = 1;
  v15 = 2LL * i;
  *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v15) = *(_QWORD *)(v1 + 16);
  *(_DWORD *)(*(_QWORD *)(a1 + 32) + 8 * v15 + 8) = *(_DWORD *)(v1 + 28);
  ++*(_DWORD *)(a1 + 28);
  *(_QWORD *)(v1 + 40) = 0;
  *(_QWORD *)(v1 + 16) = 0;
  *(_QWORD *)(v1 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp+arg_0], rbx
0x1800070f5  mov     [rsp+arg_8], rsi
0x1800070fa  push    rdi
0x1800070fb  sub     rsp, 20h
0x1800070ff  mov     rdi, [rcx+10h]
0x180007103  mov     rbx, rcx
0x180007106  mov     rcx, rdi
0x180007109  call    ASN1BEREncFlush
0x18000710e  test    eax, eax
0x180007110  jz      loc_1800071CE
0x180007116  mov     eax, [rbx+18h]
0x180007119  mov     edx, [rbx+1Ch]
0x18000711c  cmp     edx, eax
0x18000711e  jnb     loc_18000720C
0x180007124  mov     rax, [rbx+8]
0x180007128  test    dword ptr [rax+34h], 400h
0x18000712f  jz      short loc_18000717D
0x180007131  xor     r9d, r9d
0x180007134  cmp     r9d, edx
0x180007137  jnb     short loc_180007180
0x180007139  mov     rax, [rbx+20h]
0x18000713d  mov     r8d, [rdi+1Ch]
0x180007141  mov     r11, [rdi+10h]
0x180007145  mov     ecx, r9d
0x180007148  add     rcx, rcx
0x18000714b  mov     esi, [rax+rcx*8+8]
0x18000714f  cmp     r8d, esi
0x180007152  mov     r10, [rax+rcx*8]
0x180007156  cmovnb  r8d, esi
0x18000715a  test    r8d, r8d
0x18000715d  jz      short loc_1800071D2
0x18000715f  movzx   ecx, byte ptr [r11]
0x180007163  dec     r8d
0x180007166  movzx   eax, byte ptr [r10]
0x18000716a  inc     r11
0x18000716d  inc     r10
0x180007170  sub     ecx, eax
0x180007172  jz      short loc_18000715A
0x180007174  test    ecx, ecx
0x180007176  jle     short loc_1800071D9
0x180007178  inc     r9d
0x18000717b  jmp     short loc_180007134
0x18000717d  mov     r9d, edx
0x180007180  mov     rdx, [rbx+20h]
0x180007184  mov     eax, 1
0x180007189  mov     rcx, [rdi+10h]
0x18000718d  mov     r8d, r9d
0x180007190  add     r8, r8
0x180007193  mov     [rdx+r8*8], rcx
0x180007197  mov     rdx, [rbx+20h]
0x18000719b  mov     ecx, [rdi+1Ch]
0x18000719e  mov     [rdx+r8*8+8], ecx
0x1800071a3  inc     dword ptr [rbx+1Ch]
0x1800071a6  mov     qword ptr [rdi+28h], 0
0x1800071ae  mov     qword ptr [rdi+10h], 0
0x1800071b6  mov     qword ptr [rdi+18h], 0
0x1800071be  mov     rbx, [rsp+28h+arg_0]
0x1800071c3  mov     rsi, [rsp+28h+arg_8]
0x1800071c8  add     rsp, 20h
0x1800071cc  pop     rdi
0x1800071cd  retn
0x1800071ce  xor     eax, eax
0x1800071d0  jmp     short loc_1800071BE
0x1800071d2  mov     ecx, [rdi+1Ch]
0x1800071d5  sub     ecx, esi
0x1800071d7  jmp     short loc_180007174
0x1800071d9  mov     eax, [rbx+1Ch]
0x1800071dc  mov     r10d, eax
0x1800071df  sub     r10d, r9d
0x1800071e2  jz      short loc_180007180
0x1800071e4  mov     rdx, [rbx+20h]
0x1800071e8  lea     r8d, [rax-1]
0x1800071ec  add     rax, rax
0x1800071ef  mov     ecx, r8d
0x1800071f2  add     rcx, rcx
0x1800071f5  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x1800071f9  movdqu  xmmword ptr [rdx+rax*8], xmm0
0x1800071fe  mov     eax, r8d
0x180007201  add     r10d, 0FFFFFFFFh
0x180007205  jnz     short loc_1800071E4
0x180007207  jmp     loc_180007180
0x18000720c  lea     edx, [rax+rax]
0x18000720f  mov     ecx, 40h ; '@'; uFlags
0x180007214  shl     rdx, 4; uBytes
0x180007218  call    cs:__imp_LocalAlloc
0x18000721e  mov     rsi, rax
0x180007221  test    rax, rax
0x180007224  jz      short loc_1800071CE
0x180007226  mov     r8d, [rbx+18h]
0x18000722a  mov     rcx, rax; void *
0x18000722d  mov     rdx, [rbx+20h]; Src
0x180007231  shl     r8, 4; Size
0x180007235  call    memcpy_0
0x18000723a  mov     rcx, [rbx+20h]; hMem
0x18000723e  call    cs:__imp_LocalFree
0x180007244  shl     dword ptr [rbx+18h], 1
0x180007247  mov     edx, [rbx+1Ch]
0x18000724a  mov     [rbx+20h], rsi
0x18000724e  jmp     loc_180007124
```
