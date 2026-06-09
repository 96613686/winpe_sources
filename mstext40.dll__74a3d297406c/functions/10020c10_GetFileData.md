# GetFileData

- ea: `0x10020c10`
- end: `0x10020e08`
- name: `GetFileData`
- size: `504`
- prototype: `int __stdcall(DWORD NumberOfBytesRead, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100208a0`
- `0x10021670`

## callees

- `0x1000b070`
- `0x10020c10`
- `0x10022740`
- `0x100295f0`
- `0x1002ba60`

## import_xrefs

- `KERNEL32!ReadFile` at `0x10020c55`
- `KERNEL32!ReadFile` at `0x10020c55`
- `KERNEL32!SetFilePointer` at `0x10020c23`
- `KERNEL32!SetFilePointer` at `0x10020cd0`
- `KERNEL32!SetFilePointer` at `0x10020c23`
- `KERNEL32!SetFilePointer` at `0x10020cd0`

## pseudocode

```c
int __stdcall GetFileData(DWORD NumberOfBytesRead, int a2)
{
  DWORD v2; // esi
  DWORD v3; // ebp
  unsigned int v4; // ebx
  int result; // eax
  DWORD v6; // edi
  DWORD v7; // ebx
  DWORD v8; // eax
  int v9; // ecx
  unsigned int v10; // eax
  size_t v11; // edi
  unsigned int v12; // eax
  int v13; // eax
  DWORD v14; // [esp+10h] [ebp-8h] BYREF
  int v15; // [esp+14h] [ebp-4h] BYREF

  v2 = NumberOfBytesRead;
  v3 = SetFilePointer(*(HANDLE *)NumberOfBytesRead, 0, 0, 1u);
  if ( v3 == -1 )
    return -1;
  *(_DWORD *)(v2 + 8320) = v3;
  *(_DWORD *)(v2 + 11428) = 0;
  if ( !ReadFile(*(HANDLE *)v2, (LPVOID)(v2 + 11492), 0x1000u, &NumberOfBytesRead, 0) )
  {
    *(_DWORD *)(v2 + 11428) = 0;
    return -1;
  }
  v6 = NumberOfBytesRead;
  if ( NumberOfBytesRead < 0x1000 )
    *(_DWORD *)(v2 + 11428) = 1;
  if ( !v6 )
    return -1603;
  if ( a2 == 54936 )
  {
    v14 = v6;
    v4 = ValidateBufferForGb18030Characters(v2 + 11492, &v14);
    if ( v4 )
      return v4;
    v7 = v14;
    if ( v14 != v6 )
    {
      v8 = SetFilePointer(*(HANDLE *)v2, v14 - v6, 0, 1u);
      v3 = v8;
      if ( v8 == -1 )
        return -1;
      v6 = v7;
      *(_DWORD *)(v2 + 8320) = v8;
      NumberOfBytesRead = v7;
    }
  }
  v15 = 4096;
  if ( !v3 )
  {
    *(_DWORD *)(v2 + 11468) = 0;
    *(_DWORD *)(v2 + 11472) = 0;
  }
  v9 = *(_DWORD *)(v2 + 11472);
  if ( v9 )
  {
    v6 += v9;
    NumberOfBytesRead = v6;
  }
  *(_DWORD *)(v2 + 11444) = *(_DWORD *)(v2 + 11468);
  *(_DWORD *)(v2 + 11448) = v9;
  if ( v9 )
    *(__m128i *)(v2 + 11452) = _mm_loadu_si128((const __m128i *)(v2 + 11476));
  v10 = TextConvertToUnicode(
          a2,
          (int *)(v2 + 11468),
          (char *)(v2 - v9 + 11492),
          &NumberOfBytesRead,
          (LPWSTR)(v2 + 36),
          (int)&v15,
          *(_DWORD *)(v2 + 16));
  v11 = v6 - NumberOfBytesRead;
  v4 = v10;
  *(_DWORD *)(v2 + 11472) = v11;
  if ( v11 )
    memcpy((void *)(v2 - v11 + 11492), (const void *)(v2 - v11 + 15588), v11);
  if ( v4 )
    return -1;
  v12 = v15;
  *(_DWORD *)(v2 + 8232) = v15;
  if ( v12 >= 0x1000 )
    *(_DWORD *)(v2 + 8360) = -1;
  else
    *(_DWORD *)(v2 + 8360) = v12;
  if ( *(_DWORD *)(v2 + 8228) )
    return v4;
  v13 = MemAllocate(0x2000u);
  *(_DWORD *)(v2 + 8228) = v13;
  if ( !v13 )
    return -1011;
  *(_DWORD *)(v2 + 8240) = 4096;
  result = 0;
  *(_DWORD *)(v2 + 8360) = -1;
  return result;
}

```

## disassembly

```asm
0x10020c10  sub     esp, 8
0x10020c13  push    ebx
0x10020c14  push    ebp
0x10020c15  push    esi
0x10020c16  mov     esi, [esp+14h+NumberOfBytesRead]
0x10020c1a  push    edi
0x10020c1b  push    1; dwMoveMethod
0x10020c1d  push    0; lpDistanceToMoveHigh
0x10020c1f  push    0; lDistanceToMove
0x10020c21  push    dword ptr [esi]; hFile
0x10020c23  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10020c29  mov     ebp, eax
0x10020c2b  cmp     ebp, 0FFFFFFFFh
0x10020c2e  jz      short loc_10020C65
0x10020c30  push    0; lpOverlapped
0x10020c32  lea     eax, [esp+1Ch+NumberOfBytesRead]
0x10020c36  mov     [esi+2080h], ebp
0x10020c3c  push    eax; lpNumberOfBytesRead
0x10020c3d  push    1000h; nNumberOfBytesToRead
0x10020c42  lea     ebx, [esi+2CE4h]
0x10020c48  mov     dword ptr [esi+2CA4h], 0
0x10020c52  push    ebx; lpBuffer
0x10020c53  push    dword ptr [esi]; hFile
0x10020c55  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10020c5b  test    eax, eax
0x10020c5d  jnz     short loc_10020C74
0x10020c5f  mov     [esi+2CA4h], eax
0x10020c65  or      ebx, 0FFFFFFFFh
0x10020c68  pop     edi
0x10020c69  pop     esi
0x10020c6a  pop     ebp
0x10020c6b  mov     eax, ebx
0x10020c6d  pop     ebx
0x10020c6e  add     esp, 8
0x10020c71  retn    8
0x10020c74  mov     edi, [esp+18h+NumberOfBytesRead]
0x10020c78  cmp     edi, 1000h
0x10020c7e  jnb     short loc_10020C8A
0x10020c80  mov     dword ptr [esi+2CA4h], 1
0x10020c8a  test    edi, edi
0x10020c8c  jnz     short loc_10020C9F
0x10020c8e  pop     edi
0x10020c8f  pop     esi
0x10020c90  mov     ebx, 0FFFFF9BDh
0x10020c95  pop     ebp
0x10020c96  mov     eax, ebx
0x10020c98  pop     ebx
0x10020c99  add     esp, 8
0x10020c9c  retn    8
0x10020c9f  cmp     [esp+18h+arg_4], 0D698h
0x10020ca7  jnz     short loc_10020CE9
0x10020ca9  lea     eax, [esp+18h+var_8]
0x10020cad  mov     [esp+18h+var_8], edi
0x10020cb1  push    eax
0x10020cb2  push    ebx
0x10020cb3  call    ValidateBufferForGb18030Characters
0x10020cb8  mov     ebx, eax
0x10020cba  test    ebx, ebx
0x10020cbc  jnz     short loc_10020C68
0x10020cbe  mov     ebx, [esp+18h+var_8]
0x10020cc2  cmp     ebx, edi
0x10020cc4  jz      short loc_10020CE9
0x10020cc6  push    1; dwMoveMethod
0x10020cc8  push    eax; lpDistanceToMoveHigh
0x10020cc9  mov     eax, ebx
0x10020ccb  sub     eax, edi
0x10020ccd  push    eax; lDistanceToMove
0x10020cce  push    dword ptr [esi]; hFile
0x10020cd0  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10020cd6  mov     ebp, eax
0x10020cd8  cmp     ebp, 0FFFFFFFFh
0x10020cdb  jz      short loc_10020C65
0x10020cdd  mov     edi, ebx
0x10020cdf  mov     [esi+2080h], ebp
0x10020ce5  mov     [esp+18h+NumberOfBytesRead], edi
0x10020ce9  mov     [esp+18h+var_4], 1000h
0x10020cf1  test    ebp, ebp
0x10020cf3  jnz     short loc_10020D01
0x10020cf5  mov     [esi+2CCCh], ebp
0x10020cfb  mov     [esi+2CD0h], ebp
0x10020d01  mov     ecx, [esi+2CD0h]
0x10020d07  test    ecx, ecx
0x10020d09  jz      short loc_10020D11
0x10020d0b  add     edi, ecx
0x10020d0d  mov     [esp+18h+NumberOfBytesRead], edi
0x10020d11  mov     eax, [esi+2CCCh]
0x10020d17  lea     edx, [esi+2CCCh]
0x10020d1d  mov     [esi+2CB4h], eax
0x10020d23  mov     [esi+2CB8h], ecx
0x10020d29  test    ecx, ecx
0x10020d2b  jz      short loc_10020D3D
0x10020d2d  movdqu  xmm0, xmmword ptr [esi+2CD4h]
0x10020d35  movdqu  xmmword ptr [esi+2CBCh], xmm0
0x10020d3d  push    dword ptr [esi+10h]; int
0x10020d40  lea     eax, [esp+1Ch+var_4]
0x10020d44  push    eax; int
0x10020d45  lea     eax, [esi+24h]
0x10020d48  push    eax; lpWideCharStr
0x10020d49  lea     eax, [esp+24h+NumberOfBytesRead]
0x10020d4d  push    eax; int
0x10020d4e  mov     eax, esi
0x10020d50  sub     eax, ecx
0x10020d52  add     eax, 2CE4h
0x10020d57  push    eax; Src
0x10020d58  push    edx; int
0x10020d59  push    [esp+30h+arg_4]; int
0x10020d5d  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x10020d62  sub     edi, [esp+18h+NumberOfBytesRead]
0x10020d66  mov     ebx, eax
0x10020d68  mov     [esi+2CD0h], edi
0x10020d6e  jz      short loc_10020D8B
0x10020d70  mov     ecx, esi
0x10020d72  sub     ecx, edi
0x10020d74  push    edi; Size
0x10020d75  lea     eax, [ecx+3CE4h]
0x10020d7b  push    eax; Src
0x10020d7c  lea     eax, [ecx+2CE4h]
0x10020d82  push    eax; void *
0x10020d83  call    _memcpy
0x10020d88  add     esp, 0Ch
0x10020d8b  test    ebx, ebx
0x10020d8d  jnz     loc_10020C65
0x10020d93  mov     eax, [esp+18h+var_4]
0x10020d97  mov     [esi+2028h], eax
0x10020d9d  cmp     eax, 1000h
0x10020da2  jnb     short loc_10020DAC
0x10020da4  mov     [esi+20A8h], eax
0x10020daa  jmp     short loc_10020DB6
0x10020dac  mov     dword ptr [esi+20A8h], 0FFFFFFFFh
0x10020db6  cmp     dword ptr [esi+2024h], 0
0x10020dbd  jnz     loc_10020C68
0x10020dc3  push    2000h; Size
0x10020dc8  call    _MemAllocate@4; MemAllocate(x)
0x10020dcd  mov     [esi+2024h], eax
0x10020dd3  test    eax, eax
0x10020dd5  jnz     short loc_10020DE8
0x10020dd7  pop     edi
0x10020dd8  pop     esi
0x10020dd9  mov     ebx, 0FFFFFC0Dh
0x10020dde  pop     ebp
0x10020ddf  mov     eax, ebx
0x10020de1  pop     ebx
0x10020de2  add     esp, 8
0x10020de5  retn    8
0x10020de8  pop     edi
0x10020de9  mov     dword ptr [esi+2030h], 1000h
0x10020df3  mov     eax, ebx
0x10020df5  mov     dword ptr [esi+20A8h], 0FFFFFFFFh
0x10020dff  pop     esi
0x10020e00  pop     ebp
0x10020e01  pop     ebx
0x10020e02  add     esp, 8
0x10020e05  retn    8
```
