# AttemptWrite

- ea: `0x18002cc34`
- end: `0x18002cd8c`
- name: `AttemptWrite`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002cb60`
- `0x18006b9e0`

## callees

- `0x18002cc34`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002ccde`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002ccde`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd5d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd5d`

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
0x18002cc34  push    rbx
0x18002cc36  push    rbp
0x18002cc37  push    rsi
0x18002cc38  push    rdi
0x18002cc39  sub     rsp, 38h
0x18002cc3d  mov     rbx, rcx
0x18002cc40  mov     edi, edx
0x18002cc42  mov     ecx, [rcx+14h]
0x18002cc45  mov     rbp, r8
0x18002cc48  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18002cc50  lea     eax, [rcx+rdi]
0x18002cc53  cmp     eax, ecx
0x18002cc55  jb      short loc_18002CCA6
0x18002cc57  mov     edx, [rbx+10h]
0x18002cc5a  mov     r8d, 2; uFlags
0x18002cc60  cmp     [rbx+18h], r8w
0x18002cc65  jz      loc_18002CCFA
0x18002cc6b  cmp     eax, edx
0x18002cc6d  ja      short loc_18002CCB3
0x18002cc6f  mov     ecx, [rbx+14h]
0x18002cc72  add     rcx, [rbx]; void *
0x18002cc75  cmp     rcx, [rbx]
0x18002cc78  jb      short loc_18002CCA6
0x18002cc7a  mov     r8, rdi; Size
0x18002cc7d  mov     rdx, rbp; Src
0x18002cc80  call    memcpy_0
0x18002cc85  add     [rbx+14h], edi
0x18002cc88  mov     eax, [rbx+1Eh]
0x18002cc8b  shr     edi, 1
0x18002cc8d  lea     ecx, [rdi+rax]
0x18002cc90  cmp     ecx, eax
0x18002cc92  jb      short loc_18002CCA6
0x18002cc94  mov     [rbx+1Eh], ecx
0x18002cc97  mov     eax, 1
0x18002cc9c  add     rsp, 38h
0x18002cca0  pop     rdi
0x18002cca1  pop     rsi
0x18002cca2  pop     rbp
0x18002cca3  pop     rbx
0x18002cca4  retn
0x18002cca6  mov     eax, 1
0x18002ccab  or      [rbx+2Ah], ax
0x18002ccaf  xor     eax, eax
0x18002ccb1  jmp     short loc_18002CC9C
0x18002ccb3  cmp     edx, 0FFFFBFFFh
0x18002ccb9  jnb     short loc_18002CCA6
0x18002ccbb  mov     eax, edi
0x18002ccbd  lea     ecx, [rdx+4000h]
0x18002ccc3  not     eax
0x18002ccc5  cmp     ecx, eax
0x18002ccc7  jnb     short loc_18002CCA6
0x18002ccc9  mov     rcx, [rbx]; hMem
0x18002cccc  add     edx, 4000h
0x18002ccd2  mov     esi, edi
0x18002ccd4  and     esi, 0FFFFC000h
0x18002ccda  add     esi, edx
0x18002ccdc  mov     edx, esi; uBytes
0x18002ccde  call    cs:__imp_LocalReAlloc
0x18002cce5  nop     dword ptr [rax+rax+00h]
0x18002ccea  test    rax, rax
0x18002cced  jz      short loc_18002CCA6
0x18002ccef  mov     [rbx], rax
0x18002ccf2  mov     [rbx+10h], esi
0x18002ccf5  jmp     loc_18002CC6F
0x18002ccfa  cmp     eax, edx
0x18002ccfc  ja      short loc_18002CD45
0x18002ccfe  lea     eax, [rcx+rdi]
0x18002cd01  cmp     eax, [rbx+10h]
0x18002cd04  jbe     loc_18002CC72
0x18002cd0a  mov     rcx, [rbx+8]; hFile
0x18002cd0e  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002cd13  mov     r8d, edi; nNumberOfBytesToWrite
0x18002cd16  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18002cd1f  mov     rdx, rbp; lpBuffer
0x18002cd22  call    cs:__imp_WriteFile
0x18002cd29  nop     dword ptr [rax+rax+00h]
0x18002cd2e  test    eax, eax
0x18002cd30  jz      loc_18002CCA6
0x18002cd36  cmp     [rsp+58h+NumberOfBytesWritten], edi
0x18002cd3a  jz      loc_18002CC88
0x18002cd40  jmp     loc_18002CCA6
0x18002cd45  mov     rdx, [rbx]; lpBuffer
0x18002cd48  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002cd4d  mov     r8d, ecx; nNumberOfBytesToWrite
0x18002cd50  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18002cd59  mov     rcx, [rbx+8]; hFile
0x18002cd5d  call    cs:__imp_WriteFile
0x18002cd64  nop     dword ptr [rax+rax+00h]
0x18002cd69  test    eax, eax
0x18002cd6b  jz      loc_18002CCA6
0x18002cd71  mov     eax, [rbx+14h]
0x18002cd74  cmp     [rsp+58h+NumberOfBytesWritten], eax
0x18002cd78  jnz     loc_18002CCA6
0x18002cd7e  mov     dword ptr [rbx+14h], 0
0x18002cd85  xor     ecx, ecx
0x18002cd87  jmp     loc_18002CCFE
```
