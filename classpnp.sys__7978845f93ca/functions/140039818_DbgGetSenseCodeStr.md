# DbgGetSenseCodeStr

- ea: `0x140039818`
- end: `0x140039a98`
- name: `DbgGetSenseCodeStr`
- size: `640`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000de10`
- `0x140014aa0`

## callees

- `0x140039818`

## string_xrefs

- `0x140039a09`: `SCSI_SENSE_NOT_READY`
- `0x140039a7d`: `SCSI_SENSE_COPY_ABORTED`
- `0x140039a74`: `SCSI_SENSE_ABORTED_COMMAND`
- `0x140039a59`: `SCSI_SENSE_MISCOMPARE`

## pseudocode

```c
const char *__fastcall DbgGetSenseCodeStr(__int64 a1)
{
  const char *v1; // rdx
  char v3; // r11
  _BYTE *v4; // r9
  unsigned int v5; // esi
  __int64 v6; // rbx
  char v7; // bp
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 v10; // r10
  int v11; // ecx
  int v12; // ecx
  unsigned __int8 v13; // r10
  unsigned int v14; // ebp
  __int64 v15; // rsi
  char v16; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rdi
  __int64 v19; // rbx
  int v20; // ecx
  int v21; // ecx
  unsigned __int8 v22; // r8
  _BYTE *v23; // rcx
  _BYTE *v24; // rax
  char v25; // r8

  v1 = "?";
  if ( *(char *)(a1 + 3) < 0 )
  {
    v3 = 1;
    if ( *(_BYTE *)(a1 + 2) != 40 )
    {
      v13 = *(_BYTE *)(a1 + 11);
      v4 = *(_BYTE **)(a1 + 32);
      goto LABEL_36;
    }
    v4 = 0;
    if ( !*(_DWORD *)(a1 + 20) )
    {
      v5 = *(_DWORD *)(a1 + 56);
      if ( v5 )
      {
        v6 = 0;
        v7 = 0;
        do
        {
          v8 = *(unsigned int *)(a1 + 4 * v6 + 120);
          if ( (unsigned int)v8 >= 0x80 )
          {
            v9 = *(unsigned int *)(a1 + 16);
            if ( (unsigned int)v8 < (unsigned int)v9 )
            {
              v10 = (unsigned int)v8;
              v11 = *(_DWORD *)(v8 + a1) - 64;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  if ( v12 == 1 && v10 + 40 <= v9 )
                  {
                    v4 = *(_BYTE **)(v10 + a1 + 24);
                    break;
                  }
                }
                else if ( v10 + 56 <= v9 )
                {
                  v4 = *(_BYTE **)(v10 + a1 + 16);
                  v7 = 1;
                }
              }
              else if ( v10 + 40 <= v9 )
              {
                v4 = *(_BYTE **)(v10 + a1 + 16);
                break;
              }
              if ( v7 )
                break;
            }
          }
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < v5 );
      }
    }
    v13 = 0;
    if ( !*(_DWORD *)(a1 + 20) )
    {
      v14 = *(_DWORD *)(a1 + 56);
      if ( v14 )
      {
        v15 = 0;
        v16 = 0;
        while ( 1 )
        {
          v17 = *(unsigned int *)(a1 + 4 * v15 + 120);
          if ( (unsigned int)v17 >= 0x80 )
          {
            v18 = *(unsigned int *)(a1 + 16);
            if ( (unsigned int)v17 < (unsigned int)v18 )
              break;
          }
LABEL_30:
          v15 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v15 >= v14 )
            goto LABEL_36;
        }
        v19 = (unsigned int)v17;
        v20 = *(_DWORD *)(v17 + a1) - 64;
        if ( !v20 )
          goto LABEL_28;
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 == 1 )
          {
LABEL_28:
            if ( v19 + 40 <= v18 )
            {
              v13 = *(_BYTE *)(v19 + a1 + 9);
              goto LABEL_36;
            }
          }
        }
        else if ( v19 + 56 <= v18 )
        {
          v13 = *(_BYTE *)(v19 + a1 + 9);
          v16 = 1;
        }
        if ( v16 )
          goto LABEL_36;
        goto LABEL_30;
      }
    }
LABEL_36:
    if ( v4 && v13 )
    {
      v22 = 0;
      v23 = &v4[v13];
      v24 = v4 + 8;
      if ( (unsigned __int8)((*v4 & 0x7F) - 114) <= 1u )
      {
        if ( v24 <= v23 )
        {
          v25 = v4[1];
          goto LABEL_43;
        }
      }
      else if ( v24 <= v23 )
      {
        v25 = v4[2];
LABEL_43:
        v22 = v25 & 0xF;
        goto LABEL_45;
      }
      v3 = 0;
LABEL_45:
      if ( v3 )
      {
        if ( v22 > 8u )
        {
          switch ( v22 )
          {
            case 9u:
              return "SCSI_SENSE_UNIQUE";
            case 0xAu:
              return "SCSI_SENSE_COPY_ABORTED";
            case 0xBu:
              return "SCSI_SENSE_ABORTED_COMMAND";
            case 0xCu:
              return "SCSI_SENSE_EQUAL";
            case 0xDu:
              return "SCSI_SENSE_VOL_OVERFLOW";
            case 0xEu:
              return "SCSI_SENSE_MISCOMPARE";
            case 0xFu:
              return "SCSI_SENSE_RESERVED";
          }
        }
        else if ( v22 == 8 )
        {
          return "SCSI_SENSE_BLANK_CHECK";
        }
        else if ( v22 )
        {
          switch ( v22 )
          {
            case 1u:
              return "SCSI_SENSE_RECOVERED_ERROR";
            case 2u:
              return "SCSI_SENSE_NOT_READY";
            case 3u:
              return "SCSI_SENSE_MEDIUM_ERROR";
            case 4u:
              return "SCSI_SENSE_HARDWARE_ERROR";
            case 5u:
              return "SCSI_SENSE_ILLEGAL_REQUEST";
            case 6u:
              return "SCSI_SENSE_UNIT_ATTENTION";
            case 7u:
              return "SCSI_SENSE_DATA_PROTECT";
          }
        }
        else
        {
          return "SCSI_SENSE_NO_SENSE";
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140039818  push    rbx
0x14003981a  push    rbp
0x14003981b  push    rsi
0x14003981c  push    rdi
0x14003981d  push    r14
0x14003981f  cmp     byte ptr [rcx+3], 0
0x140039823  lea     rdx, asc_140045638; "?"
0x14003982a  mov     r8, rcx
0x14003982d  jge     loc_140039A8D
0x140039833  cmp     byte ptr [rcx+2], 28h ; '('
0x140039837  mov     r11d, 1
0x14003983d  jnz     loc_140039934
0x140039843  xor     r9d, r9d
0x140039846  cmp     [rcx+14h], r9d
0x14003984a  jnz     short loc_1400398C2
0x14003984c  mov     esi, [rcx+38h]
0x14003984f  test    esi, esi
0x140039851  jz      short loc_1400398C2
0x140039853  xor     ebx, ebx
0x140039855  xor     bpl, bpl
0x140039858  mov     ecx, [r8+rbx*4+78h]
0x14003985d  cmp     ecx, 80h
0x140039863  jb      short loc_1400398B4
0x140039865  mov     edi, [r8+10h]
0x140039869  cmp     ecx, edi
0x14003986b  jnb     short loc_1400398B4
0x14003986d  mov     r10d, ecx
0x140039870  mov     ecx, [rcx+r8]
0x140039874  sub     ecx, 40h ; '@'
0x140039877  jz      short loc_1400398A6
0x140039879  sub     ecx, r11d
0x14003987c  jz      short loc_140039893
0x14003987e  cmp     ecx, r11d
0x140039881  jnz     short loc_1400398AF
0x140039883  lea     rcx, [r10+28h]
0x140039887  cmp     rcx, rdi
0x14003988a  ja      short loc_1400398AF
0x14003988c  mov     r9, [r10+r8+18h]
0x140039891  jmp     short loc_1400398C2
0x140039893  lea     rcx, [r10+38h]
0x140039897  cmp     rcx, rdi
0x14003989a  ja      short loc_1400398AF
0x14003989c  mov     r9, [r10+r8+10h]
0x1400398a1  mov     bpl, r11b
0x1400398a4  jmp     short loc_1400398AF
0x1400398a6  lea     rcx, [r10+28h]
0x1400398aa  cmp     rcx, rdi
0x1400398ad  jbe     short loc_1400398BD
0x1400398af  test    bpl, bpl
0x1400398b2  jnz     short loc_1400398C2
0x1400398b4  add     ebx, r11d
0x1400398b7  cmp     ebx, esi
0x1400398b9  jb      short loc_140039858
0x1400398bb  jmp     short loc_1400398C2
0x1400398bd  mov     r9, [r10+r8+10h]
0x1400398c2  xor     r10b, r10b
0x1400398c5  cmp     dword ptr [r8+14h], 0
0x1400398ca  jnz     short loc_14003993C
0x1400398cc  mov     ebp, [r8+38h]
0x1400398d0  test    ebp, ebp
0x1400398d2  jz      short loc_14003993C
0x1400398d4  xor     esi, esi
0x1400398d6  xor     r14b, r14b
0x1400398d9  mov     ecx, [r8+rsi*4+78h]
0x1400398de  cmp     ecx, 80h
0x1400398e4  jb      short loc_140039911
0x1400398e6  mov     edi, [r8+10h]
0x1400398ea  cmp     ecx, edi
0x1400398ec  jnb     short loc_140039911
0x1400398ee  mov     ebx, ecx
0x1400398f0  mov     ecx, [rcx+r8]
0x1400398f4  sub     ecx, 40h ; '@'
0x1400398f7  jz      short loc_140039903
0x1400398f9  sub     ecx, r11d
0x1400398fc  jz      short loc_14003991A
0x1400398fe  cmp     ecx, r11d
0x140039901  jnz     short loc_14003990C
0x140039903  lea     rcx, [rbx+28h]
0x140039907  cmp     rcx, rdi
0x14003990a  jbe     short loc_14003992D
0x14003990c  test    r14b, r14b
0x14003990f  jnz     short loc_14003993C
0x140039911  add     esi, r11d
0x140039914  cmp     esi, ebp
0x140039916  jb      short loc_1400398D9
0x140039918  jmp     short loc_14003993C
0x14003991a  lea     rcx, [rbx+38h]
0x14003991e  cmp     rcx, rdi
0x140039921  ja      short loc_14003990C
0x140039923  mov     r10b, [rbx+r8+9]
0x140039928  mov     r14b, r11b
0x14003992b  jmp     short loc_14003990C
0x14003992d  mov     r10b, [rbx+r8+9]
0x140039932  jmp     short loc_14003993C
0x140039934  mov     r10b, [rcx+0Bh]
0x140039938  mov     r9, [rcx+20h]
0x14003993c  test    r9, r9
0x14003993f  jz      loc_140039A8D
0x140039945  test    r10b, r10b
0x140039948  jz      loc_140039A8D
0x14003994e  mov     al, [r9]
0x140039951  xor     r8b, r8b
0x140039954  and     al, 7Fh
0x140039956  movzx   ecx, r10b
0x14003995a  sub     al, 72h ; 'r'
0x14003995c  add     rcx, r9
0x14003995f  cmp     al, r11b
0x140039962  lea     rax, [r9+8]
0x140039966  jbe     short loc_140039973
0x140039968  cmp     rax, rcx
0x14003996b  ja      short loc_140039982
0x14003996d  mov     r8b, [r9+2]
0x140039971  jmp     short loc_14003997C
0x140039973  cmp     rax, rcx
0x140039976  ja      short loc_140039982
0x140039978  mov     r8b, [r9+1]
0x14003997c  and     r8b, 0Fh
0x140039980  jmp     short loc_140039985
0x140039982  xor     r11b, r11b
0x140039985  test    r11b, r11b
0x140039988  jz      loc_140039A8D
0x14003998e  movzx   ecx, r8b
0x140039992  cmp     ecx, 8
0x140039995  ja      loc_140039A2D
0x14003999b  jz      loc_140039A24
0x1400399a1  test    r8b, r8b
0x1400399a4  jz      short loc_140039A1B
0x1400399a6  sub     ecx, 1
0x1400399a9  jz      short loc_140039A12
0x1400399ab  sub     ecx, 1
0x1400399ae  jz      short loc_140039A09
0x1400399b0  sub     ecx, 1
0x1400399b3  jz      short loc_1400399FD
0x1400399b5  sub     ecx, 1
0x1400399b8  jz      short loc_1400399F1
0x1400399ba  sub     ecx, 1
0x1400399bd  jz      short loc_1400399E5
0x1400399bf  sub     ecx, 1
0x1400399c2  jz      short loc_1400399D9
0x1400399c4  cmp     ecx, 1
0x1400399c7  jnz     loc_140039A8D
0x1400399cd  lea     rdx, aScsiSenseDataP; "SCSI_SENSE_DATA_PROTECT"
0x1400399d4  jmp     loc_140039A8D
0x1400399d9  lea     rdx, aScsiSenseUnitA; "SCSI_SENSE_UNIT_ATTENTION"
0x1400399e0  jmp     loc_140039A8D
0x1400399e5  lea     rdx, aScsiSenseIlleg; "SCSI_SENSE_ILLEGAL_REQUEST"
0x1400399ec  jmp     loc_140039A8D
0x1400399f1  lea     rdx, aScsiSenseHardw; "SCSI_SENSE_HARDWARE_ERROR"
0x1400399f8  jmp     loc_140039A8D
0x1400399fd  lea     rdx, aScsiSenseMediu; "SCSI_SENSE_MEDIUM_ERROR"
0x140039a04  jmp     loc_140039A8D
0x140039a09  lea     rdx, aScsiSenseNotRe; "SCSI_SENSE_NOT_READY"
0x140039a10  jmp     short loc_140039A8D
0x140039a12  lea     rdx, aScsiSenseRecov; "SCSI_SENSE_RECOVERED_ERROR"
0x140039a19  jmp     short loc_140039A8D
0x140039a1b  lea     rdx, aScsiSenseNoSen; "SCSI_SENSE_NO_SENSE"
0x140039a22  jmp     short loc_140039A8D
0x140039a24  lea     rdx, aScsiSenseBlank; "SCSI_SENSE_BLANK_CHECK"
0x140039a2b  jmp     short loc_140039A8D
0x140039a2d  sub     ecx, 9
0x140039a30  jz      short loc_140039A86
0x140039a32  sub     ecx, 1
0x140039a35  jz      short loc_140039A7D
0x140039a37  sub     ecx, 1
0x140039a3a  jz      short loc_140039A74
0x140039a3c  sub     ecx, 1
0x140039a3f  jz      short loc_140039A6B
0x140039a41  sub     ecx, 1
0x140039a44  jz      short loc_140039A62
0x140039a46  sub     ecx, 1
0x140039a49  jz      short loc_140039A59
0x140039a4b  cmp     ecx, 1
0x140039a4e  jnz     short loc_140039A8D
0x140039a50  lea     rdx, aScsiSenseReser; "SCSI_SENSE_RESERVED"
0x140039a57  jmp     short loc_140039A8D
0x140039a59  lea     rdx, aScsiSenseMisco; "SCSI_SENSE_MISCOMPARE"
0x140039a60  jmp     short loc_140039A8D
0x140039a62  lea     rdx, aScsiSenseVolOv; "SCSI_SENSE_VOL_OVERFLOW"
0x140039a69  jmp     short loc_140039A8D
0x140039a6b  lea     rdx, aScsiSenseEqual; "SCSI_SENSE_EQUAL"
0x140039a72  jmp     short loc_140039A8D
0x140039a74  lea     rdx, aScsiSenseAbort; "SCSI_SENSE_ABORTED_COMMAND"
0x140039a7b  jmp     short loc_140039A8D
0x140039a7d  lea     rdx, aScsiSenseCopyA; "SCSI_SENSE_COPY_ABORTED"
0x140039a84  jmp     short loc_140039A8D
0x140039a86  lea     rdx, aScsiSenseUniqu; "SCSI_SENSE_UNIQUE"
0x140039a8d  mov     rax, rdx
0x140039a90  pop     r14
0x140039a92  pop     rdi
0x140039a93  pop     rsi
0x140039a94  pop     rbp
0x140039a95  pop     rbx
0x140039a96  retn
```
