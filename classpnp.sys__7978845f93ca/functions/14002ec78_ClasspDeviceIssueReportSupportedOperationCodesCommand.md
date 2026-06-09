# ClasspDeviceIssueReportSupportedOperationCodesCommand

- ea: `0x14002ec78`
- end: `0x14002ee5d`
- name: `ClasspDeviceIssueReportSupportedOperationCodesCommand`
- size: `485`
- prototype: `__int64 __fastcall(int, int, int, int, char, int, PVOID BufferAddress)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033780`

## callees

- `0x14000de10`
- `0x14002ec78`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceIssueReportSupportedOperationCodesCommand(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int a6,
        PVOID BufferAddress)
{
  int v7; // eax
  bool v9; // zf
  int v10; // eax
  char v11; // r11
  __int64 i; // r10
  __int64 v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // r8
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // r9
  unsigned int v19; // ebx
  __int64 v20; // r11
  char v21; // di
  __int64 v22; // rcx
  unsigned __int64 v23; // r10
  __int64 v24; // r8
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // rcx
  char v28; // al
  char v29; // al

  v7 = *(_DWORD *)(a1 + 584);
  v9 = *(_BYTE *)(a2 + 2) == 40;
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    *(_DWORD *)(a2 + 40) = v7;
    *(_DWORD *)(a2 + 32) = 255;
    *(_WORD *)(a2 + 38) = 32;
  }
  else
  {
    *(_DWORD *)(a2 + 20) = v7;
    *(_WORD *)(a2 + 8) = 8447;
  }
  v10 = *(_DWORD *)(a1 + 592);
  if ( v9 )
  {
    v9 = *(_DWORD *)(a2 + 20) == 0;
    *(_DWORD *)(a2 + 24) = v10;
    if ( v9 )
    {
      v11 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v13 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v13 >= 0x80 )
        {
          v14 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v13 < (unsigned int)v14 )
          {
            v15 = (unsigned int)v13;
            v16 = *(_DWORD *)(v13 + a2) - 64;
            if ( v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                if ( v17 == 1 && v15 + 40 <= v14 )
                  break;
              }
              else if ( v15 + 56 <= v14 )
              {
                v11 = 1;
                *(_BYTE *)(v15 + a2 + 10) = 12;
              }
            }
            else if ( v15 + 40 <= v14 )
            {
              *(_BYTE *)(v15 + a2 + 10) = 12;
              break;
            }
            if ( v11 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(a2 + 12) = v10;
    *(_BYTE *)(a2 + 10) = 12;
  }
  if ( *(_BYTE *)(a2 + 2) != 40 )
  {
    v18 = a2 + 72;
    goto LABEL_45;
  }
  v18 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v19 = *(_DWORD *)(a2 + 56);
    if ( v19 )
    {
      v20 = 0;
      v21 = 0;
      do
      {
        v22 = *(unsigned int *)(a2 + 4 * v20 + 120);
        if ( (unsigned int)v22 >= 0x80 )
        {
          v23 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v22 < (unsigned int)v23 )
          {
            v24 = (unsigned int)v22;
            v25 = *(_DWORD *)(v22 + a2) - 64;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 == 1 && v24 + 40 <= v23 )
                {
                  v27 = v24 + a2 + 32;
                  if ( !*(_DWORD *)(v24 + a2 + 12) )
                    v27 = v18;
                  v18 = v27;
                  break;
                }
              }
              else if ( v24 + 56 <= v23 )
              {
                if ( !*(_BYTE *)(v24 + a2 + 10) )
                  break;
                v21 = 1;
                v18 = v24 + a2 + 24;
              }
            }
            else if ( v24 + 40 <= v23 )
            {
              if ( *(_BYTE *)(v24 + a2 + 10) )
                v18 = v24 + a2 + 24;
              break;
            }
            if ( v21 )
              break;
          }
        }
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < v19 );
    }
  }
LABEL_45:
  v28 = *(_BYTE *)(v18 + 1) & 0xE0 | 0xC;
  *(_BYTE *)v18 = -93;
  *(_BYTE *)(v18 + 1) = v28;
  v29 = *(_BYTE *)(v18 + 2) & 0x78;
  *(_DWORD *)(v18 + 6) = 83886080;
  *(_WORD *)(v18 + 4) = 0;
  *(_BYTE *)(v18 + 2) = v29 | 1;
  *(_BYTE *)(v18 + 3) = a5;
  return ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(a1 + 8), (PSCSI_REQUEST_BLOCK)a2, BufferAddress, 5u, 0);
}

```

## disassembly

```asm
0x14002ec78  mov     [rsp+arg_0], rbx
0x14002ec7d  mov     [rsp+arg_8], rsi
0x14002ec82  push    rdi
0x14002ec83  sub     rsp, 30h
0x14002ec87  mov     eax, [rcx+248h]
0x14002ec8d  mov     bl, 28h ; '('
0x14002ec8f  mov     rsi, rcx
0x14002ec92  cmp     [rdx+2], bl
0x14002ec95  jnz     short loc_14002ECA9
0x14002ec97  mov     [rdx+28h], eax
0x14002ec9a  mov     dword ptr [rdx+20h], 0FFh
0x14002eca1  mov     word ptr [rdx+26h], 20h ; ' '
0x14002eca7  jmp     short loc_14002ECB2
0x14002eca9  mov     [rdx+14h], eax
0x14002ecac  mov     word ptr [rdx+8], 20FFh
0x14002ecb2  mov     eax, [rcx+250h]
0x14002ecb8  jnz     loc_14002ED3E
0x14002ecbe  cmp     dword ptr [rdx+14h], 0
0x14002ecc2  mov     [rdx+18h], eax
0x14002ecc5  jnz     short loc_14002ED45
0x14002ecc7  xor     r11b, r11b
0x14002ecca  xor     r10d, r10d
0x14002eccd  cmp     [rdx+38h], r10d
0x14002ecd1  jbe     short loc_14002ED45
0x14002ecd3  mov     ecx, [rdx+r10*4+78h]
0x14002ecd8  cmp     ecx, 80h
0x14002ecde  jb      short loc_14002ED2B
0x14002ece0  mov     r9d, [rdx+10h]
0x14002ece4  cmp     ecx, r9d
0x14002ece7  jnb     short loc_14002ED2B
0x14002ece9  mov     r8d, ecx
0x14002ecec  mov     ecx, [rcx+rdx]
0x14002ecef  sub     ecx, 40h ; '@'
0x14002ecf2  jz      short loc_14002ED1D
0x14002ecf4  sub     ecx, 1
0x14002ecf7  jz      short loc_14002ED09
0x14002ecf9  cmp     ecx, 1
0x14002ecfc  jnz     short loc_14002ED26
0x14002ecfe  lea     rcx, [r8+28h]
0x14002ed02  cmp     rcx, r9
0x14002ed05  jbe     short loc_14002ED45
0x14002ed07  jmp     short loc_14002ED26
0x14002ed09  lea     rcx, [r8+38h]
0x14002ed0d  cmp     rcx, r9
0x14002ed10  ja      short loc_14002ED26
0x14002ed12  mov     r11b, 1
0x14002ed15  mov     byte ptr [r8+rdx+0Ah], 0Ch
0x14002ed1b  jmp     short loc_14002ED26
0x14002ed1d  lea     rcx, [r8+28h]
0x14002ed21  cmp     rcx, r9
0x14002ed24  jbe     short loc_14002ED36
0x14002ed26  test    r11b, r11b
0x14002ed29  jnz     short loc_14002ED45
0x14002ed2b  inc     r10d
0x14002ed2e  cmp     r10d, [rdx+38h]
0x14002ed32  jb      short loc_14002ECD3
0x14002ed34  jmp     short loc_14002ED45
0x14002ed36  mov     byte ptr [r8+rdx+0Ah], 0Ch
0x14002ed3c  jmp     short loc_14002ED45
0x14002ed3e  mov     [rdx+0Ch], eax
0x14002ed41  mov     byte ptr [rdx+0Ah], 0Ch
0x14002ed45  cmp     [rdx+2], bl
0x14002ed48  jnz     loc_14002EDFC
0x14002ed4e  xor     r9d, r9d
0x14002ed51  cmp     [rdx+14h], r9d
0x14002ed55  jnz     loc_14002EE00
0x14002ed5b  mov     ebx, [rdx+38h]
0x14002ed5e  test    ebx, ebx
0x14002ed60  jz      loc_14002EE00
0x14002ed66  xor     r11d, r11d
0x14002ed69  xor     dil, dil
0x14002ed6c  mov     ecx, [rdx+r11*4+78h]
0x14002ed71  cmp     ecx, 80h
0x14002ed77  jb      short loc_14002EDE1
0x14002ed79  mov     r10d, [rdx+10h]
0x14002ed7d  cmp     ecx, r10d
0x14002ed80  jnb     short loc_14002EDE1
0x14002ed82  mov     r8d, ecx
0x14002ed85  mov     ecx, [rcx+rdx]
0x14002ed88  sub     ecx, 40h ; '@'
0x14002ed8b  jz      short loc_14002EDD3
0x14002ed8d  sub     ecx, 1
0x14002ed90  jz      short loc_14002EDB6
0x14002ed92  cmp     ecx, 1
0x14002ed95  jnz     short loc_14002EDDC
0x14002ed97  lea     rcx, [r8+28h]
0x14002ed9b  cmp     rcx, r10
0x14002ed9e  ja      short loc_14002EDDC
0x14002eda0  lea     rcx, [rdx+20h]
0x14002eda4  add     rcx, r8
0x14002eda7  cmp     dword ptr [r8+rdx+0Ch], 0
0x14002edad  cmovz   rcx, r9
0x14002edb1  mov     r9, rcx
0x14002edb4  jmp     short loc_14002EE00
0x14002edb6  lea     rcx, [r8+38h]
0x14002edba  cmp     rcx, r10
0x14002edbd  ja      short loc_14002EDDC
0x14002edbf  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002edc5  jbe     short loc_14002EE00
0x14002edc7  lea     r9, [rdx+18h]
0x14002edcb  mov     dil, 1
0x14002edce  add     r9, r8
0x14002edd1  jmp     short loc_14002EDDC
0x14002edd3  lea     rcx, [r8+28h]
0x14002edd7  cmp     rcx, r10
0x14002edda  jbe     short loc_14002EDEB
0x14002eddc  test    dil, dil
0x14002eddf  jnz     short loc_14002EE00
0x14002ede1  inc     r11d
0x14002ede4  cmp     r11d, ebx
0x14002ede7  jb      short loc_14002ED6C
0x14002ede9  jmp     short loc_14002EE00
0x14002edeb  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002edf1  jbe     short loc_14002EE00
0x14002edf3  lea     r9, [rdx+18h]
0x14002edf7  add     r9, r8
0x14002edfa  jmp     short loc_14002EE00
0x14002edfc  lea     r9, [rdx+48h]
0x14002ee00  mov     al, [r9+1]
0x14002ee04  mov     r8, [rsp+38h+BufferAddress]; BufferAddress
0x14002ee09  and     al, 0ECh
0x14002ee0b  or      al, 0Ch
0x14002ee0d  mov     byte ptr [r9], 0A3h
0x14002ee11  mov     [r9+1], al
0x14002ee15  mov     al, [r9+2]
0x14002ee19  and     al, 78h
0x14002ee1b  mov     dword ptr [r9+6], 5000000h
0x14002ee23  or      al, 1
0x14002ee25  mov     word ptr [r9+4], 0
0x14002ee2c  mov     [r9+2], al
0x14002ee30  mov     al, [rsp+38h+arg_20]
0x14002ee34  mov     [r9+3], al
0x14002ee38  mov     r9d, 5; BufferLength
0x14002ee3e  mov     rcx, [rsi+8]; DeviceObject
0x14002ee42  mov     [rsp+38h+WriteToDevice], 0; WriteToDevice
0x14002ee47  call    ClassSendSrbSynchronous
0x14002ee4c  mov     rbx, [rsp+38h+arg_0]
0x14002ee51  mov     rsi, [rsp+38h+arg_8]
0x14002ee56  add     rsp, 30h
0x14002ee5a  pop     rdi
0x14002ee5b  retn
```
