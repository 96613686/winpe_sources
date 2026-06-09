# ClasspDeviceIssueReportZonesCommand

- ea: `0x14002ee64`
- end: `0x14002f0d4`
- name: `ClasspDeviceIssueReportZonesCommand`
- size: `624`
- prototype: `NTSTATUS __fastcall(__int64, __int64, char, char, __int64, PVOID BufferAddress, ULONG BufferLength)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400229f8`
- `0x1400327ac`

## callees

- `0x14000de10`
- `0x14002ee64`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceIssueReportZonesCommand(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        PVOID BufferAddress,
        ULONG BufferLength)
{
  char v7; // al
  int v8; // r10d
  int v12; // ecx
  bool v13; // zf
  char v14; // r11
  __int64 i; // r10
  __int64 v16; // rcx
  unsigned __int64 v17; // r9
  __int64 v18; // r8
  int v19; // ecx
  int v20; // ecx
  _BYTE *v21; // r10
  unsigned int v22; // ebx
  __int64 v23; // r11
  char v24; // di
  __int64 v25; // rcx
  unsigned __int64 v26; // r9
  __int64 v27; // r8
  int v28; // ecx
  int v29; // ecx
  _BYTE *v30; // rcx
  char v31; // al

  v7 = *(_BYTE *)(a2 + 2);
  v8 = *(_DWORD *)(a1 + 584);
  if ( v7 == 40 )
    *(_DWORD *)(a2 + 40) = v8;
  else
    *(_DWORD *)(a2 + 20) = v8;
  if ( a4 )
  {
    if ( v7 == 40 )
      goto LABEL_20;
LABEL_8:
    *(_BYTE *)(a2 + 9) = 32;
    goto LABEL_9;
  }
  if ( v7 != 40 )
  {
    *(_BYTE *)(a2 + 8) = -1;
    goto LABEL_8;
  }
  *(_DWORD *)(a2 + 32) = 255;
LABEL_20:
  *(_WORD *)(a2 + 38) = 32;
LABEL_9:
  v12 = *(_DWORD *)(a1 + 592);
  if ( v7 == 40 )
  {
    v13 = *(_DWORD *)(a2 + 20) == 0;
    *(_DWORD *)(a2 + 24) = v12;
    if ( v13 )
    {
      v14 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v16 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v16 >= 0x80 )
        {
          v17 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v16 < (unsigned int)v17 )
          {
            v18 = (unsigned int)v16;
            v19 = *(_DWORD *)(v16 + a2) - 64;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                if ( v20 == 1 && v18 + 40 <= v17 )
                  break;
              }
              else if ( v18 + 56 <= v17 )
              {
                v14 = 1;
                *(_BYTE *)(v18 + a2 + 10) = 16;
              }
            }
            else if ( v18 + 40 <= v17 )
            {
              *(_BYTE *)(v18 + a2 + 10) = 16;
              break;
            }
            if ( v14 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(a2 + 12) = v12;
    *(_BYTE *)(a2 + 10) = 16;
  }
  if ( *(_BYTE *)(a2 + 2) != 40 )
  {
    v21 = (_BYTE *)(a2 + 72);
    goto LABEL_52;
  }
  v21 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v22 = *(_DWORD *)(a2 + 56);
    if ( v22 )
    {
      v23 = 0;
      v24 = 0;
      do
      {
        v25 = *(unsigned int *)(a2 + 4 * v23 + 120);
        if ( (unsigned int)v25 >= 0x80 )
        {
          v26 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v25 < (unsigned int)v26 )
          {
            v27 = (unsigned int)v25;
            v28 = *(_DWORD *)(v25 + a2) - 64;
            if ( v28 )
            {
              v29 = v28 - 1;
              if ( v29 )
              {
                if ( v29 == 1 && v27 + 40 <= v26 )
                {
                  v30 = (_BYTE *)(v27 + a2 + 32);
                  if ( !*(_DWORD *)(v27 + a2 + 12) )
                    v30 = v21;
                  v21 = v30;
                  break;
                }
              }
              else if ( v27 + 56 <= v26 )
              {
                if ( !*(_BYTE *)(v27 + a2 + 10) )
                  break;
                v24 = 1;
                v21 = (_BYTE *)(v27 + a2 + 24);
              }
            }
            else if ( v27 + 40 <= v26 )
            {
              if ( *(_BYTE *)(v27 + a2 + 10) )
                v21 = (_BYTE *)(v27 + a2 + 24);
              break;
            }
            if ( v24 )
              break;
          }
        }
        v23 = (unsigned int)(v23 + 1);
      }
      while ( (unsigned int)v23 < v22 );
    }
  }
LABEL_52:
  v21[1] &= 0xE0u;
  v21[9] = a5;
  v21[8] = BYTE1(a5);
  v21[7] = BYTE2(a5);
  v21[6] = BYTE3(a5);
  v21[5] = BYTE4(a5);
  v21[4] = BYTE5(a5);
  v21[3] = BYTE6(a5);
  v21[2] = HIBYTE(a5);
  v21[12] = BYTE1(BufferLength);
  v21[11] = BYTE2(BufferLength);
  v21[10] = HIBYTE(BufferLength);
  v31 = a3 & 0x3F ^ v21[14] & 0x40;
  *v21 = -107;
  v21[13] = BufferLength;
  v21[14] = (a4 << 7) | v31;
  return ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(a1 + 8), (PSCSI_REQUEST_BLOCK)a2, BufferAddress, BufferLength, 0);
}

```

## disassembly

```asm
0x14002ee64  push    rbx
0x14002ee66  push    rbp
0x14002ee67  push    rsi
0x14002ee68  push    rdi
0x14002ee69  push    r14
0x14002ee6b  sub     rsp, 30h
0x14002ee6f  mov     al, [rdx+2]
0x14002ee72  mov     bl, 28h ; '('
0x14002ee74  mov     r10d, [rcx+248h]
0x14002ee7b  mov     bpl, r9b
0x14002ee7e  mov     r14b, r8b
0x14002ee81  mov     rsi, rcx
0x14002ee84  cmp     al, bl
0x14002ee86  jnz     short loc_14002EE8E
0x14002ee88  mov     [rdx+28h], r10d
0x14002ee8c  jmp     short loc_14002EE92
0x14002ee8e  mov     [rdx+14h], r10d
0x14002ee92  test    bpl, bpl
0x14002ee95  jnz     short loc_14002EF09
0x14002ee97  cmp     al, bl
0x14002ee99  jnz     short loc_14002EEA4
0x14002ee9b  mov     dword ptr [rdx+20h], 0FFh
0x14002eea2  jmp     short loc_14002EF0D
0x14002eea4  mov     byte ptr [rdx+8], 0FFh
0x14002eea8  mov     byte ptr [rdx+9], 20h ; ' '
0x14002eeac  mov     ecx, [rcx+250h]
0x14002eeb2  cmp     al, bl
0x14002eeb4  jnz     loc_14002EF4A
0x14002eeba  cmp     dword ptr [rdx+14h], 0
0x14002eebe  mov     [rdx+18h], ecx
0x14002eec1  jnz     loc_14002EF51
0x14002eec7  xor     r11b, r11b
0x14002eeca  xor     r10d, r10d
0x14002eecd  cmp     [rdx+38h], r10d
0x14002eed1  jbe     short loc_14002EF51
0x14002eed3  mov     ecx, [rdx+r10*4+78h]
0x14002eed8  cmp     ecx, 80h
0x14002eede  jb      short loc_14002EF37
0x14002eee0  mov     r9d, [rdx+10h]
0x14002eee4  cmp     ecx, r9d
0x14002eee7  jnb     short loc_14002EF37
0x14002eee9  mov     r8d, ecx
0x14002eeec  mov     ecx, [rcx+rdx]
0x14002eeef  sub     ecx, 40h ; '@'
0x14002eef2  jz      short loc_14002EF29
0x14002eef4  sub     ecx, 1
0x14002eef7  jz      short loc_14002EF15
0x14002eef9  cmp     ecx, 1
0x14002eefc  jnz     short loc_14002EF32
0x14002eefe  lea     rcx, [r8+28h]
0x14002ef02  cmp     rcx, r9
0x14002ef05  jbe     short loc_14002EF51
0x14002ef07  jmp     short loc_14002EF32
0x14002ef09  cmp     al, bl
0x14002ef0b  jnz     short loc_14002EEA8
0x14002ef0d  mov     word ptr [rdx+26h], 20h ; ' '
0x14002ef13  jmp     short loc_14002EEAC
0x14002ef15  lea     rcx, [r8+38h]
0x14002ef19  cmp     rcx, r9
0x14002ef1c  ja      short loc_14002EF32
0x14002ef1e  mov     r11b, 1
0x14002ef21  mov     byte ptr [r8+rdx+0Ah], 10h
0x14002ef27  jmp     short loc_14002EF32
0x14002ef29  lea     rcx, [r8+28h]
0x14002ef2d  cmp     rcx, r9
0x14002ef30  jbe     short loc_14002EF42
0x14002ef32  test    r11b, r11b
0x14002ef35  jnz     short loc_14002EF51
0x14002ef37  inc     r10d
0x14002ef3a  cmp     r10d, [rdx+38h]
0x14002ef3e  jb      short loc_14002EED3
0x14002ef40  jmp     short loc_14002EF51
0x14002ef42  mov     byte ptr [r8+rdx+0Ah], 10h
0x14002ef48  jmp     short loc_14002EF51
0x14002ef4a  mov     [rdx+0Ch], ecx
0x14002ef4d  mov     byte ptr [rdx+0Ah], 10h
0x14002ef51  cmp     [rdx+2], bl
0x14002ef54  jnz     loc_14002F008
0x14002ef5a  xor     r10d, r10d
0x14002ef5d  cmp     [rdx+14h], r10d
0x14002ef61  jnz     loc_14002F00C
0x14002ef67  mov     ebx, [rdx+38h]
0x14002ef6a  test    ebx, ebx
0x14002ef6c  jz      loc_14002F00C
0x14002ef72  xor     r11d, r11d
0x14002ef75  xor     dil, dil
0x14002ef78  mov     ecx, [rdx+r11*4+78h]
0x14002ef7d  cmp     ecx, 80h
0x14002ef83  jb      short loc_14002EFED
0x14002ef85  mov     r9d, [rdx+10h]
0x14002ef89  cmp     ecx, r9d
0x14002ef8c  jnb     short loc_14002EFED
0x14002ef8e  mov     r8d, ecx
0x14002ef91  mov     ecx, [rcx+rdx]
0x14002ef94  sub     ecx, 40h ; '@'
0x14002ef97  jz      short loc_14002EFDF
0x14002ef99  sub     ecx, 1
0x14002ef9c  jz      short loc_14002EFC2
0x14002ef9e  cmp     ecx, 1
0x14002efa1  jnz     short loc_14002EFE8
0x14002efa3  lea     rcx, [r8+28h]
0x14002efa7  cmp     rcx, r9
0x14002efaa  ja      short loc_14002EFE8
0x14002efac  lea     rcx, [rdx+20h]
0x14002efb0  add     rcx, r8
0x14002efb3  cmp     dword ptr [r8+rdx+0Ch], 0
0x14002efb9  cmovz   rcx, r10
0x14002efbd  mov     r10, rcx
0x14002efc0  jmp     short loc_14002F00C
0x14002efc2  lea     rcx, [r8+38h]
0x14002efc6  cmp     rcx, r9
0x14002efc9  ja      short loc_14002EFE8
0x14002efcb  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002efd1  jbe     short loc_14002F00C
0x14002efd3  lea     r10, [rdx+18h]
0x14002efd7  mov     dil, 1
0x14002efda  add     r10, r8
0x14002efdd  jmp     short loc_14002EFE8
0x14002efdf  lea     rcx, [r8+28h]
0x14002efe3  cmp     rcx, r9
0x14002efe6  jbe     short loc_14002EFF7
0x14002efe8  test    dil, dil
0x14002efeb  jnz     short loc_14002F00C
0x14002efed  inc     r11d
0x14002eff0  cmp     r11d, ebx
0x14002eff3  jb      short loc_14002EF78
0x14002eff5  jmp     short loc_14002F00C
0x14002eff7  cmp     byte ptr [r8+rdx+0Ah], 0
0x14002effd  jbe     short loc_14002F00C
0x14002efff  lea     r10, [rdx+18h]
0x14002f003  add     r10, r8
0x14002f006  jmp     short loc_14002F00C
0x14002f008  lea     r10, [rdx+48h]
0x14002f00c  mov     al, byte ptr [rsp+58h+arg_20]
0x14002f013  and     r14b, 3Fh
0x14002f017  mov     r9d, [rsp+58h+BufferLength]; BufferLength
0x14002f01f  and     byte ptr [r10+1], 0E0h
0x14002f024  mov     r8, [rsp+58h+BufferAddress]; BufferAddress
0x14002f02c  mov     [r10+9], al
0x14002f030  mov     al, byte ptr [rsp+58h+arg_20+1]
0x14002f037  mov     [r10+8], al
0x14002f03b  mov     al, byte ptr [rsp+58h+arg_20+2]
0x14002f042  mov     [r10+7], al
0x14002f046  mov     al, byte ptr [rsp+58h+arg_20+3]
0x14002f04d  mov     [r10+6], al
0x14002f051  mov     al, byte ptr [rsp+58h+arg_20+4]
0x14002f058  mov     [r10+5], al
0x14002f05c  mov     al, byte ptr [rsp+58h+arg_20+5]
0x14002f063  mov     [r10+4], al
0x14002f067  mov     al, byte ptr [rsp+58h+arg_20+6]
0x14002f06e  mov     [r10+3], al
0x14002f072  mov     al, byte ptr [rsp+58h+arg_20+7]
0x14002f079  mov     [r10+2], al
0x14002f07d  mov     al, byte ptr [rsp+58h+BufferLength+1]
0x14002f084  mov     [r10+0Ch], al
0x14002f088  mov     al, byte ptr [rsp+58h+BufferLength+2]
0x14002f08f  mov     [r10+0Bh], al
0x14002f093  mov     al, byte ptr [rsp+58h+BufferLength+3]
0x14002f09a  mov     [r10+0Ah], al
0x14002f09e  mov     al, [r10+0Eh]
0x14002f0a2  and     al, 40h
0x14002f0a4  shl     bpl, 7
0x14002f0a8  xor     al, r14b
0x14002f0ab  mov     byte ptr [r10], 95h
0x14002f0af  or      al, bpl
0x14002f0b2  mov     [r10+0Dh], r9b
0x14002f0b6  mov     [r10+0Eh], al
0x14002f0ba  mov     rcx, [rsi+8]; DeviceObject
0x14002f0be  mov     [rsp+58h+WriteToDevice], 0; WriteToDevice
0x14002f0c3  call    ClassSendSrbSynchronous
0x14002f0c8  add     rsp, 30h
0x14002f0cc  pop     r14
0x14002f0ce  pop     rdi
0x14002f0cf  pop     rsi
0x14002f0d0  pop     rbp
0x14002f0d1  pop     rbx
0x14002f0d2  retn
```
