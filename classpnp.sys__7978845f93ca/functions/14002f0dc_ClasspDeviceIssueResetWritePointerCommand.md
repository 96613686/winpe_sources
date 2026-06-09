# ClasspDeviceIssueResetWritePointerCommand

- ea: `0x14002f0dc`
- end: `0x14002f2ff`
- name: `ClasspDeviceIssueResetWritePointerCommand`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140032d74`

## callees

- `0x14000de10`
- `0x14002f0dc`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceIssueResetWritePointerCommand(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  int v4; // eax
  char v5; // bp
  bool v8; // zf
  int v9; // eax
  char v10; // r11
  __int64 i; // r10
  __int64 v12; // rcx
  unsigned __int64 v13; // r9
  __int64 v14; // r8
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // r9
  unsigned int v18; // ebx
  __int64 v19; // r11
  char v20; // di
  __int64 v21; // rcx
  unsigned __int64 v22; // r10
  __int64 v23; // r8
  int v24; // ecx
  int v25; // ecx
  __int64 v26; // rcx
  char v27; // al
  char v28; // al

  v4 = *(_DWORD *)(a1 + 584);
  v5 = a4;
  v8 = *(_BYTE *)(a2 + 2) == 40;
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    *(_DWORD *)(a2 + 40) = v4;
    *(_DWORD *)(a2 + 32) = 255;
    *(_WORD *)(a2 + 38) = 32;
  }
  else
  {
    *(_DWORD *)(a2 + 20) = v4;
    *(_WORD *)(a2 + 8) = 8447;
  }
  v9 = *(_DWORD *)(a1 + 592);
  if ( v8 )
  {
    v8 = *(_DWORD *)(a2 + 20) == 0;
    *(_DWORD *)(a2 + 24) = v9;
    if ( v8 )
    {
      v10 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v12 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v12 >= 0x80 )
        {
          v13 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v12 < (unsigned int)v13 )
          {
            v14 = (unsigned int)v12;
            v15 = *(_DWORD *)(v12 + a2) - 64;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 == 1 && v14 + 40 <= v13 )
                  break;
              }
              else if ( v14 + 56 <= v13 )
              {
                v10 = 1;
                *(_BYTE *)(v14 + a2 + 10) = 16;
              }
            }
            else if ( v14 + 40 <= v13 )
            {
              *(_BYTE *)(v14 + a2 + 10) = 16;
              break;
            }
            if ( v10 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(a2 + 12) = v9;
    *(_BYTE *)(a2 + 10) = 16;
  }
  if ( *(_BYTE *)(a2 + 2) != 40 )
  {
    v17 = a2 + 72;
    goto LABEL_45;
  }
  v17 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v18 = *(_DWORD *)(a2 + 56);
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      do
      {
        v21 = *(unsigned int *)(a2 + 4 * v19 + 120);
        if ( (unsigned int)v21 >= 0x80 )
        {
          v22 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v21 < (unsigned int)v22 )
          {
            v23 = (unsigned int)v21;
            v24 = *(_DWORD *)(v21 + a2) - 64;
            if ( v24 )
            {
              v25 = v24 - 1;
              if ( v25 )
              {
                if ( v25 == 1 && v23 + 40 <= v22 )
                {
                  v26 = v23 + a2 + 32;
                  if ( !*(_DWORD *)(v23 + a2 + 12) )
                    v26 = v17;
                  v17 = v26;
                  break;
                }
              }
              else if ( v23 + 56 <= v22 )
              {
                if ( !*(_BYTE *)(v23 + a2 + 10) )
                  break;
                v20 = 1;
                v17 = v23 + a2 + 24;
              }
            }
            else if ( v23 + 40 <= v22 )
            {
              if ( *(_BYTE *)(v23 + a2 + 10) )
                v17 = v23 + a2 + 24;
              break;
            }
            if ( v20 )
              break;
          }
        }
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < v18 );
    }
  }
LABEL_45:
  *(_OWORD *)v17 = 0;
  v27 = *(_BYTE *)(v17 + 1) & 0xE4;
  *(_BYTE *)v17 = -108;
  *(_BYTE *)(v17 + 1) = v27 | 4;
  v28 = *(_BYTE *)(v17 + 14);
  *(_BYTE *)(v17 + 9) = v5;
  *(_BYTE *)(v17 + 8) = BYTE1(a4);
  *(_BYTE *)(v17 + 7) = BYTE2(a4);
  *(_BYTE *)(v17 + 6) = BYTE3(a4);
  *(_BYTE *)(v17 + 5) = BYTE4(a4);
  *(_BYTE *)(v17 + 4) = BYTE5(a4);
  *(_BYTE *)(v17 + 3) = BYTE6(a4);
  *(_BYTE *)(v17 + 2) = HIBYTE(a4);
  *(_BYTE *)(v17 + 14) = v28 & 0xFE | (a3 != 0);
  return ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(a1 + 8), (PSCSI_REQUEST_BLOCK)a2, 0, 0, 0);
}

```

## disassembly

```asm
0x14002f0dc  mov     [rsp+arg_0], rbx
0x14002f0e1  mov     [rsp+arg_8], rbp
0x14002f0e6  mov     [rsp+arg_18], r9
0x14002f0eb  push    rsi
0x14002f0ec  push    rdi
0x14002f0ed  push    r14
0x14002f0ef  sub     rsp, 30h
0x14002f0f3  mov     eax, [rcx+248h]
0x14002f0f9  mov     bl, 28h ; '('
0x14002f0fb  mov     rbp, r9
0x14002f0fe  mov     r14b, r8b
0x14002f101  mov     rsi, rcx
0x14002f104  cmp     [rdx+2], bl
0x14002f107  jnz     short loc_14002F11B
0x14002f109  mov     [rdx+28h], eax
0x14002f10c  mov     dword ptr [rdx+20h], 0FFh
0x14002f113  mov     word ptr [rdx+26h], 20h ; ' '
0x14002f119  jmp     short loc_14002F124
0x14002f11b  mov     [rdx+14h], eax
0x14002f11e  mov     word ptr [rdx+8], 20FFh
0x14002f124  mov     eax, [rcx+250h]
0x14002f12a  jnz     loc_14002F1B0
0x14002f130  cmp     dword ptr [rdx+14h], 0
0x14002f134  mov     [rdx+18h], eax
0x14002f137  jnz     short loc_14002F1B7
0x14002f139  xor     r11b, r11b
0x14002f13c  xor     r10d, r10d
0x14002f13f  cmp     [rdx+38h], r10d
0x14002f143  jbe     short loc_14002F1B7
0x14002f145  mov     ecx, [rdx+r10*4+78h]
0x14002f14a  cmp     ecx, 80h
0x14002f150  jb      short loc_14002F19D
0x14002f152  mov     r9d, [rdx+10h]
0x14002f156  cmp     ecx, r9d
0x14002f159  jnb     short loc_14002F19D
0x14002f15b  mov     r8d, ecx
0x14002f15e  mov     ecx, [rcx+rdx]
0x14002f161  sub     ecx, 40h ; '@'
0x14002f164  jz      short loc_14002F18F
0x14002f166  sub     ecx, 1
0x14002f169  jz      short loc_14002F17B
0x14002f16b  cmp     ecx, 1
0x14002f16e  jnz     short loc_14002F198
0x14002f170  lea     rcx, [r8+28h]
0x14002f174  cmp     rcx, r9
0x14002f177  jbe     short loc_14002F1B7
0x14002f179  jmp     short loc_14002F198
0x14002f17b  lea     rcx, [r8+38h]
0x14002f17f  cmp     rcx, r9
0x14002f182  ja      short loc_14002F198
0x14002f184  mov     r11b, 1
0x14002f187  mov     byte ptr [r8+rdx+0Ah], 10h
0x14002f18d  jmp     short loc_14002F198
0x14002f18f  lea     rcx, [r8+28h]
0x14002f193  cmp     rcx, r9
0x14002f196  jbe     short loc_14002F1A8
0x14002f198  test    r11b, r11b
0x14002f19b  jnz     short loc_14002F1B7
0x14002f19d  inc     r10d
0x14002f1a0  cmp     r10d, [rdx+38h]
0x14002f1a4  jb      short loc_14002F145
0x14002f1a6  jmp     short loc_14002F1B7
0x14002f1a8  mov     byte ptr [r8+rdx+0Ah], 10h
0x14002f1ae  jmp     short loc_14002F1B7
0x14002f1b0  mov     [rdx+0Ch], eax
0x14002f1b3  mov     byte ptr [rdx+0Ah], 10h
0x14002f1b7  cmp     [rdx+2], bl
0x14002f1ba  jnz     loc_14002F26E
0x14002f1c0  xor     r9d, r9d
0x14002f1c3  cmp     [rdx+14h], r9d
0x14002f1c7  jnz     loc_14002F272
0x14002f1cd  mov     ebx, [rdx+38h]
0x14002f1d0  test    ebx, ebx
0x14002f1d2  jz      loc_14002F272
0x14002f1d8  xor     r11d, r11d
0x14002f1db  xor     dil, dil
0x14002f1de  mov     ecx, [rdx+r11*4+78h]
0x14002f1e3  cmp     ecx, 80h
0x14002f1e9  jb      short loc_14002F253
0x14002f1eb  mov     r10d, [rdx+10h]
0x14002f1ef  cmp     ecx, r10d
0x14002f1f2  jnb     short loc_14002F253
0x14002f1f4  mov     r8d, ecx
0x14002f1f7  mov     ecx, [rcx+rdx]
0x14002f1fa  sub     ecx, 40h ; '@'
0x14002f1fd  jz      short loc_14002F245
0x14002f1ff  sub     ecx, 1
0x14002f202  jz      short loc_14002F228
0x14002f204  cmp     ecx, 1
0x14002f207  jnz     short loc_14002F24E
0x14002f209  lea     rcx, [r8+28h]
0x14002f20d  cmp     rcx, r10
0x14002f210  ja      short loc_14002F24E
0x14002f212  lea     rcx, [rdx+20h]
0x14002f216  add     rcx, r8
0x14002f219  cmp     dword ptr [r8+rdx+0Ch], 0
0x14002f21f  cmovz   rcx, r9
0x14002f223  mov     r9, rcx
0x14002f226  jmp     short loc_14002F272
0x14002f228  lea     rcx, [r8+38h]
0x14002f22c  cmp     rcx, r10
0x14002f22f  ja      short loc_14002F24E
0x14002f231  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002f237  jbe     short loc_14002F272
0x14002f239  lea     r9, [rdx+18h]
0x14002f23d  mov     dil, 1
0x14002f240  add     r9, r8
0x14002f243  jmp     short loc_14002F24E
0x14002f245  lea     rcx, [r8+28h]
0x14002f249  cmp     rcx, r10
0x14002f24c  jbe     short loc_14002F25D
0x14002f24e  test    dil, dil
0x14002f251  jnz     short loc_14002F272
0x14002f253  inc     r11d
0x14002f256  cmp     r11d, ebx
0x14002f259  jb      short loc_14002F1DE
0x14002f25b  jmp     short loc_14002F272
0x14002f25d  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002f263  jbe     short loc_14002F272
0x14002f265  lea     r9, [rdx+18h]
0x14002f269  add     r9, r8
0x14002f26c  jmp     short loc_14002F272
0x14002f26e  lea     r9, [rdx+48h]
0x14002f272  xorps   xmm0, xmm0
0x14002f275  mov     [rsp+48h+WriteToDevice], 0; WriteToDevice
0x14002f27a  movups  xmmword ptr [r9], xmm0
0x14002f27e  mov     al, [r9+1]
0x14002f282  and     al, 0E4h
0x14002f284  mov     byte ptr [r9], 94h
0x14002f288  or      al, 4
0x14002f28a  mov     [r9+1], al
0x14002f28e  test    r14b, r14b
0x14002f291  mov     al, [r9+0Eh]
0x14002f295  setnz   cl
0x14002f298  mov     [r9+9], bpl
0x14002f29c  and     al, 0FEh
0x14002f29e  xor     r8d, r8d; BufferAddress
0x14002f2a1  or      cl, al
0x14002f2a3  mov     al, byte ptr [rsp+48h+arg_18+1]
0x14002f2a7  mov     [r9+8], al
0x14002f2ab  mov     al, byte ptr [rsp+48h+arg_18+2]
0x14002f2af  mov     [r9+7], al
0x14002f2b3  mov     al, byte ptr [rsp+48h+arg_18+3]
0x14002f2b7  mov     [r9+6], al
0x14002f2bb  mov     al, byte ptr [rsp+48h+arg_18+4]
0x14002f2bf  mov     [r9+5], al
0x14002f2c3  mov     al, byte ptr [rsp+48h+arg_18+5]
0x14002f2c7  mov     [r9+4], al
0x14002f2cb  mov     al, byte ptr [rsp+48h+arg_18+6]
0x14002f2cf  mov     [r9+3], al
0x14002f2d3  mov     al, byte ptr [rsp+48h+arg_18+7]
0x14002f2d7  mov     [r9+2], al
0x14002f2db  mov     [r9+0Eh], cl
0x14002f2df  xor     r9d, r9d; BufferLength
0x14002f2e2  mov     rcx, [rsi+8]; DeviceObject
0x14002f2e6  call    ClassSendSrbSynchronous
0x14002f2eb  mov     rbx, [rsp+48h+arg_0]
0x14002f2f0  mov     rbp, [rsp+48h+arg_8]
0x14002f2f5  add     rsp, 30h
0x14002f2f9  pop     r14
0x14002f2fb  pop     rdi
0x14002f2fc  pop     rsi
0x14002f2fd  retn
```
