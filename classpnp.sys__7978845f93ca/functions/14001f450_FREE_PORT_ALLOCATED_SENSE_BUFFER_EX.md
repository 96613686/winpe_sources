# FREE_PORT_ALLOCATED_SENSE_BUFFER_EX

- ea: `0x14001f450`
- end: `0x14001f62d`
- name: `FREE_PORT_ALLOCATED_SENSE_BUFFER_EX`
- size: `477`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004300`
- `0x14000de10`
- `0x140012a00`
- `0x140014aa0`
- `0x14001ccb0`

## callees

- `0x140012e18`
- `0x14001f450`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4f9`

## pseudocode

```c
UCHAR __fastcall FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, __int64 a2)
{
  _DWORD *v2; // rsi
  void *v5; // r8
  unsigned int v6; // r11d
  __int64 v7; // r10
  char v8; // di
  __int64 v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // ecx
  _SENSE_DATA *SenseData; // r9
  char v15; // r11
  __int64 i; // r10
  __int64 v17; // rcx
  unsigned __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  UCHAR result; // al
  char v23; // r11
  __int64 v24; // r9
  __int64 v25; // rcx
  unsigned __int64 v26; // r10
  __int64 v27; // rdx
  int v28; // ecx
  int v29; // ecx

  v2 = (_DWORD *)(a2 + 20);
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    v5 = 0;
    if ( !*v2 )
    {
      v6 = *(_DWORD *)(a2 + 56);
      if ( v6 )
      {
        v7 = 0;
        v8 = 0;
        do
        {
          v9 = *(unsigned int *)(a2 + 4 * v7 + 120);
          if ( (unsigned int)v9 >= 0x80 )
          {
            v10 = *(unsigned int *)(a2 + 16);
            if ( (unsigned int)v9 < (unsigned int)v10 )
            {
              v11 = (unsigned int)v9;
              v12 = *(_DWORD *)(v9 + a2) - 64;
              if ( v12 )
              {
                v13 = v12 - 1;
                if ( v13 )
                {
                  if ( v13 == 1 && v11 + 40 <= v10 )
                  {
                    v5 = *(void **)(v11 + a2 + 24);
                    break;
                  }
                }
                else if ( v11 + 56 <= v10 )
                {
                  v5 = *(void **)(v11 + a2 + 16);
                  v8 = 1;
                }
              }
              else if ( v11 + 40 <= v10 )
              {
                v5 = *(void **)(v11 + a2 + 16);
                break;
              }
              if ( v8 )
                break;
            }
          }
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < v6 );
      }
    }
  }
  else
  {
    v5 = *(void **)(a2 + 32);
  }
  ExFreePoolWithTag(v5, 0);
  SenseData = FdoExtension->SenseData;
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    if ( !*v2 )
    {
      v15 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v17 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v17 >= 0x80 )
        {
          v18 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v17 < (unsigned int)v18 )
          {
            v19 = (unsigned int)v17;
            v20 = *(_DWORD *)(v17 + a2) - 64;
            if ( v20 )
            {
              v21 = v20 - 1;
              if ( v21 )
              {
                if ( v21 == 1 && v19 + 40 <= v18 )
                {
                  *(_QWORD *)(v19 + a2 + 24) = SenseData;
                  break;
                }
              }
              else if ( v19 + 56 <= v18 )
              {
                v15 = 1;
                *(_QWORD *)(v19 + a2 + 16) = SenseData;
              }
            }
            else if ( v19 + 40 <= v18 )
            {
              *(_QWORD *)(v19 + a2 + 16) = SenseData;
              break;
            }
            if ( v15 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_QWORD *)(a2 + 32) = SenseData;
  }
  result = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(FdoExtension);
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    if ( *v2 )
      goto LABEL_54;
    v23 = 0;
    v24 = 0;
    if ( !*(_DWORD *)(a2 + 56) )
      goto LABEL_54;
    while ( 1 )
    {
      v25 = *(unsigned int *)(a2 + 4 * v24 + 120);
      if ( (unsigned int)v25 >= 0x80 )
      {
        v26 = *(unsigned int *)(a2 + 16);
        if ( (unsigned int)v25 < (unsigned int)v26 )
          break;
      }
LABEL_48:
      v24 = (unsigned int)(v24 + 1);
      if ( (unsigned int)v24 >= *(_DWORD *)(a2 + 56) )
        goto LABEL_54;
    }
    v27 = (unsigned int)v25;
    v28 = *(_DWORD *)(v25 + a2) - 64;
    if ( !v28 )
      goto LABEL_46;
    v29 = v28 - 1;
    if ( v29 )
    {
      if ( v29 == 1 )
      {
LABEL_46:
        if ( v27 + 40 <= v26 )
        {
          *(_BYTE *)(v27 + a2 + 9) = result;
          goto LABEL_54;
        }
      }
    }
    else if ( v27 + 56 <= v26 )
    {
      v23 = 1;
      *(_BYTE *)(v27 + a2 + 9) = result;
    }
    if ( v23 )
      goto LABEL_54;
    goto LABEL_48;
  }
  *(_BYTE *)(a2 + 11) = result;
LABEL_54:
  if ( *(_BYTE *)(a2 + 2) == 40 )
    *(_DWORD *)(a2 + 24) &= ~0x400u;
  else
    *(_DWORD *)(a2 + 12) &= ~0x400u;
  return result;
}

```

## disassembly

```asm
0x14001f450  push    rbx
0x14001f452  push    rbp
0x14001f453  push    rsi
0x14001f454  push    rdi
0x14001f455  sub     rsp, 28h
0x14001f459  cmp     byte ptr [rdx+2], 28h ; '('
0x14001f45d  lea     rsi, [rdx+14h]
0x14001f461  mov     rbx, rdx
0x14001f464  mov     rbp, rcx
0x14001f467  jnz     loc_14001F4F0
0x14001f46d  xor     r8d, r8d
0x14001f470  cmp     [rsi], r8d
0x14001f473  jnz     short loc_14001F4F4
0x14001f475  mov     r11d, [rdx+38h]
0x14001f479  test    r11d, r11d
0x14001f47c  jz      short loc_14001F4F4
0x14001f47e  xor     r10d, r10d
0x14001f481  xor     dil, dil
0x14001f484  mov     ecx, [rbx+r10*4+78h]
0x14001f489  cmp     ecx, 80h
0x14001f48f  jb      short loc_14001F4DF
0x14001f491  mov     r9d, [rbx+10h]
0x14001f495  cmp     ecx, r9d
0x14001f498  jnb     short loc_14001F4DF
0x14001f49a  mov     edx, ecx
0x14001f49c  mov     ecx, [rcx+rbx]
0x14001f49f  sub     ecx, 40h ; '@'
0x14001f4a2  jz      short loc_14001F4D1
0x14001f4a4  sub     ecx, 1
0x14001f4a7  jz      short loc_14001F4BE
0x14001f4a9  cmp     ecx, 1
0x14001f4ac  jnz     short loc_14001F4DA
0x14001f4ae  lea     rcx, [rdx+28h]
0x14001f4b2  cmp     rcx, r9
0x14001f4b5  ja      short loc_14001F4DA
0x14001f4b7  mov     r8, [rdx+rbx+18h]
0x14001f4bc  jmp     short loc_14001F4F4
0x14001f4be  lea     rcx, [rdx+38h]
0x14001f4c2  cmp     rcx, r9
0x14001f4c5  ja      short loc_14001F4DA
0x14001f4c7  mov     r8, [rdx+rbx+10h]
0x14001f4cc  mov     dil, 1
0x14001f4cf  jmp     short loc_14001F4DA
0x14001f4d1  lea     rcx, [rdx+28h]
0x14001f4d5  cmp     rcx, r9
0x14001f4d8  jbe     short loc_14001F4E9
0x14001f4da  test    dil, dil
0x14001f4dd  jnz     short loc_14001F4F4
0x14001f4df  inc     r10d
0x14001f4e2  cmp     r10d, r11d
0x14001f4e5  jb      short loc_14001F484
0x14001f4e7  jmp     short loc_14001F4F4
0x14001f4e9  mov     r8, [rdx+rbx+10h]
0x14001f4ee  jmp     short loc_14001F4F4
0x14001f4f0  mov     r8, [rdx+20h]
0x14001f4f4  xor     edx, edx; Tag
0x14001f4f6  mov     rcx, r8; P
0x14001f4f9  call    cs:__imp_ExFreePoolWithTag
0x14001f500  nop     dword ptr [rax+rax+00h]
0x14001f505  cmp     byte ptr [rbx+2], 28h ; '('
0x14001f509  mov     r9, [rbp+240h]
0x14001f510  jnz     short loc_14001F590
0x14001f512  cmp     dword ptr [rsi], 0
0x14001f515  jnz     short loc_14001F594
0x14001f517  xor     r11b, r11b
0x14001f51a  xor     r10d, r10d
0x14001f51d  cmp     [rbx+38h], r10d
0x14001f521  jbe     short loc_14001F594
0x14001f523  mov     ecx, [rbx+r10*4+78h]
0x14001f528  cmp     ecx, 80h
0x14001f52e  jb      short loc_14001F57E
0x14001f530  mov     r8d, [rbx+10h]
0x14001f534  cmp     ecx, r8d
0x14001f537  jnb     short loc_14001F57E
0x14001f539  mov     edx, ecx
0x14001f53b  mov     ecx, [rcx+rbx]
0x14001f53e  sub     ecx, 40h ; '@'
0x14001f541  jz      short loc_14001F570
0x14001f543  sub     ecx, 1
0x14001f546  jz      short loc_14001F55D
0x14001f548  cmp     ecx, 1
0x14001f54b  jnz     short loc_14001F579
0x14001f54d  lea     rcx, [rdx+28h]
0x14001f551  cmp     rcx, r8
0x14001f554  ja      short loc_14001F579
0x14001f556  mov     [rdx+rbx+18h], r9
0x14001f55b  jmp     short loc_14001F594
0x14001f55d  lea     rcx, [rdx+38h]
0x14001f561  cmp     rcx, r8
0x14001f564  ja      short loc_14001F579
0x14001f566  mov     r11b, 1
0x14001f569  mov     [rdx+rbx+10h], r9
0x14001f56e  jmp     short loc_14001F579
0x14001f570  lea     rcx, [rdx+28h]
0x14001f574  cmp     rcx, r8
0x14001f577  jbe     short loc_14001F589
0x14001f579  test    r11b, r11b
0x14001f57c  jnz     short loc_14001F594
0x14001f57e  inc     r10d
0x14001f581  cmp     r10d, [rbx+38h]
0x14001f585  jb      short loc_14001F523
0x14001f587  jmp     short loc_14001F594
0x14001f589  mov     [rdx+rbx+10h], r9
0x14001f58e  jmp     short loc_14001F594
0x14001f590  mov     [rbx+20h], r9
0x14001f594  mov     rcx, rbp; FdoExtension
0x14001f597  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x14001f59c  cmp     byte ptr [rbx+2], 28h ; '('
0x14001f5a0  jnz     short loc_14001F60E
0x14001f5a2  cmp     dword ptr [rsi], 0
0x14001f5a5  jnz     short loc_14001F611
0x14001f5a7  xor     r11b, r11b
0x14001f5aa  xor     r9d, r9d
0x14001f5ad  cmp     [rbx+38h], r9d
0x14001f5b1  jbe     short loc_14001F611
0x14001f5b3  mov     ecx, [rbx+r9*4+78h]
0x14001f5b8  cmp     ecx, 80h
0x14001f5be  jb      short loc_14001F5EB
0x14001f5c0  mov     r10d, [rbx+10h]
0x14001f5c4  cmp     ecx, r10d
0x14001f5c7  jnb     short loc_14001F5EB
0x14001f5c9  mov     edx, ecx
0x14001f5cb  mov     ecx, [rcx+rbx]
0x14001f5ce  sub     ecx, 40h ; '@'
0x14001f5d1  jz      short loc_14001F5DD
0x14001f5d3  sub     ecx, 1
0x14001f5d6  jz      short loc_14001F5F6
0x14001f5d8  cmp     ecx, 1
0x14001f5db  jnz     short loc_14001F5E6
0x14001f5dd  lea     rcx, [rdx+28h]
0x14001f5e1  cmp     rcx, r10
0x14001f5e4  jbe     short loc_14001F608
0x14001f5e6  test    r11b, r11b
0x14001f5e9  jnz     short loc_14001F611
0x14001f5eb  inc     r9d
0x14001f5ee  cmp     r9d, [rbx+38h]
0x14001f5f2  jb      short loc_14001F5B3
0x14001f5f4  jmp     short loc_14001F611
0x14001f5f6  lea     rcx, [rdx+38h]
0x14001f5fa  cmp     rcx, r10
0x14001f5fd  ja      short loc_14001F5E6
0x14001f5ff  mov     r11b, 1
0x14001f602  mov     [rdx+rbx+9], al
0x14001f606  jmp     short loc_14001F5E6
0x14001f608  mov     [rdx+rbx+9], al
0x14001f60c  jmp     short loc_14001F611
0x14001f60e  mov     [rbx+0Bh], al
0x14001f611  cmp     byte ptr [rbx+2], 28h ; '('
0x14001f615  jnz     short loc_14001F61E
0x14001f617  btr     dword ptr [rbx+18h], 0Ah
0x14001f61c  jmp     short loc_14001F623
0x14001f61e  btr     dword ptr [rbx+0Ch], 0Ah
0x14001f623  add     rsp, 28h
0x14001f627  pop     rdi
0x14001f628  pop     rsi
0x14001f629  pop     rbp
0x14001f62a  pop     rbx
0x14001f62b  retn
```
