# AttemptWrite

- ea: `0x180023cb0`
- end: `0x180023dee`
- name: `AttemptWrite`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180023be4`
- `0x180067300`

## callees

- `0x180023cb0`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180023d59`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180023d59`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023d97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023dc8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023d97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023dc8`

## pseudocode

```c
__int64 __fastcall AttemptWrite(__int64 a1, unsigned int a2, const void *a3)
{
  size_t v4; // rdi
  __int64 v5; // rcx
  unsigned int v7; // eax
  unsigned int v8; // edx
  void *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v13; // esi
  HLOCAL v14; // rax
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  v5 = *(unsigned int *)(a1 + 20);
  NumberOfBytesWritten = 0;
  v7 = v5 + a2;
  if ( (unsigned int)v5 + a2 < (unsigned int)v5 )
    goto LABEL_9;
  v8 = *(_DWORD *)(a1 + 16);
  if ( *(_WORD *)(a1 + 24) == 2 )
  {
    if ( v7 > v8 )
    {
      if ( !WriteFile(*(HANDLE *)(a1 + 8), *(LPCVOID *)a1, v5, &NumberOfBytesWritten, 0)
        || NumberOfBytesWritten != *(_DWORD *)(a1 + 20) )
      {
        goto LABEL_9;
      }
      *(_DWORD *)(a1 + 20) = 0;
      v5 = 0;
    }
    if ( (unsigned int)(v5 + v4) > *(_DWORD *)(a1 + 16) )
    {
      if ( !WriteFile(*(HANDLE *)(a1 + 8), a3, v4, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != (_DWORD)v4 )
        goto LABEL_9;
      goto LABEL_7;
    }
  }
  else
  {
    if ( v7 > v8 )
    {
      if ( v8 >= 0xFFFFBFFF )
        goto LABEL_9;
      if ( v8 + 0x4000 >= ~(_DWORD)v4 )
        goto LABEL_9;
      v13 = v8 + 0x4000 + (v4 & 0xFFFFC000);
      v14 = LocalReAlloc(*(HLOCAL *)a1, v13, 2u);
      if ( !v14 )
        goto LABEL_9;
      *(_QWORD *)a1 = v14;
      *(_DWORD *)(a1 + 16) = v13;
    }
    v5 = *(unsigned int *)(a1 + 20);
  }
  v9 = (void *)(*(_QWORD *)a1 + v5);
  if ( (unsigned __int64)v9 < *(_QWORD *)a1 )
    goto LABEL_9;
  memcpy_0(v9, a3, v4);
  *(_DWORD *)(a1 + 20) += v4;
LABEL_7:
  v10 = *(_DWORD *)(a1 + 30);
  v11 = ((unsigned int)v4 >> 1) + v10;
  if ( v11 >= v10 )
  {
    *(_DWORD *)(a1 + 30) = v11;
    return 1;
  }
LABEL_9:
  *(_WORD *)(a1 + 42) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x180023cb0  push    rbx
0x180023cb2  push    rbp
0x180023cb3  push    rsi
0x180023cb4  push    rdi
0x180023cb5  sub     rsp, 38h
0x180023cb9  mov     rbx, rcx
0x180023cbc  mov     edi, edx
0x180023cbe  mov     ecx, [rcx+14h]
0x180023cc1  mov     rbp, r8
0x180023cc4  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180023ccc  lea     eax, [rcx+rdi]
0x180023ccf  cmp     eax, ecx
0x180023cd1  jb      short loc_180023D21
0x180023cd3  mov     edx, [rbx+10h]
0x180023cd6  mov     r8d, 2; uFlags
0x180023cdc  cmp     [rbx+18h], r8w
0x180023ce1  jz      loc_180023D6F
0x180023ce7  cmp     eax, edx
0x180023ce9  ja      short loc_180023D2E
0x180023ceb  mov     ecx, [rbx+14h]
0x180023cee  add     rcx, [rbx]; void *
0x180023cf1  cmp     rcx, [rbx]
0x180023cf4  jb      short loc_180023D21
0x180023cf6  mov     r8, rdi; Size
0x180023cf9  mov     rdx, rbp; Src
0x180023cfc  call    memcpy_0
0x180023d01  add     [rbx+14h], edi
0x180023d04  mov     eax, [rbx+1Eh]
0x180023d07  shr     edi, 1
0x180023d09  lea     ecx, [rdi+rax]
0x180023d0c  cmp     ecx, eax
0x180023d0e  jb      short loc_180023D21
0x180023d10  mov     [rbx+1Eh], ecx
0x180023d13  mov     eax, 1
0x180023d18  add     rsp, 38h
0x180023d1c  pop     rdi
0x180023d1d  pop     rsi
0x180023d1e  pop     rbp
0x180023d1f  pop     rbx
0x180023d20  retn
0x180023d21  mov     eax, 1
0x180023d26  or      [rbx+2Ah], ax
0x180023d2a  xor     eax, eax
0x180023d2c  jmp     short loc_180023D18
0x180023d2e  cmp     edx, 0FFFFBFFFh
0x180023d34  jnb     short loc_180023D21
0x180023d36  mov     eax, edi
0x180023d38  lea     ecx, [rdx+4000h]
0x180023d3e  not     eax
0x180023d40  cmp     ecx, eax
0x180023d42  jnb     short loc_180023D21
0x180023d44  mov     rcx, [rbx]; hMem
0x180023d47  add     edx, 4000h
0x180023d4d  mov     esi, edi
0x180023d4f  and     esi, 0FFFFC000h
0x180023d55  add     esi, edx
0x180023d57  mov     edx, esi; uBytes
0x180023d59  call    cs:__imp_LocalReAlloc
0x180023d5f  test    rax, rax
0x180023d62  jz      short loc_180023D21
0x180023d64  mov     [rbx], rax
0x180023d67  mov     [rbx+10h], esi
0x180023d6a  jmp     loc_180023CEB
0x180023d6f  cmp     eax, edx
0x180023d71  ja      short loc_180023DB0
0x180023d73  lea     eax, [rcx+rdi]
0x180023d76  cmp     eax, [rbx+10h]
0x180023d79  jbe     loc_180023CEE
0x180023d7f  mov     rcx, [rbx+8]; hFile
0x180023d83  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023d88  mov     r8d, edi; nNumberOfBytesToWrite
0x180023d8b  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180023d94  mov     rdx, rbp; lpBuffer
0x180023d97  call    cs:__imp_WriteFile
0x180023d9d  test    eax, eax
0x180023d9f  jz      short loc_180023D21
0x180023da1  cmp     [rsp+58h+NumberOfBytesWritten], edi
0x180023da5  jz      loc_180023D04
0x180023dab  jmp     loc_180023D21
0x180023db0  mov     rdx, [rbx]; lpBuffer
0x180023db3  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023db8  mov     r8d, ecx; nNumberOfBytesToWrite
0x180023dbb  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180023dc4  mov     rcx, [rbx+8]; hFile
0x180023dc8  call    cs:__imp_WriteFile
0x180023dce  test    eax, eax
0x180023dd0  jz      loc_180023D21
0x180023dd6  mov     eax, [rbx+14h]
0x180023dd9  cmp     [rsp+58h+NumberOfBytesWritten], eax
0x180023ddd  jnz     loc_180023D21
0x180023de3  mov     dword ptr [rbx+14h], 0
0x180023dea  xor     ecx, ecx
0x180023dec  jmp     short loc_180023D73
```
