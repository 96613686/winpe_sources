# DbgGetAdditionalSenseCodeStr

- ea: `0x140038b84`
- end: `0x140038e99`
- name: `DbgGetAdditionalSenseCodeStr`
- size: `789`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000de10`
- `0x140014aa0`

## callees

- `0x140038b84`

## string_xrefs

- `0x140038d6b`: `SCSI_ADSENSE_LUN_NOT_READY`
- `0x140038ddc`: `SCSI_ADSENSE_ILLEGAL_COMMAND`
- `0x140038dac`: `SCSI_ADSENSE_WRITE_PROTECT`
- `0x140038e87`: `SCSI_ADSENSE_COPY_PROTECTION_FAILURE`

## pseudocode

```c
const char *__fastcall DbgGetAdditionalSenseCodeStr(__int64 a1)
{
  const char *v1; // rdx
  bool v3; // bl
  _BYTE *v4; // r8
  unsigned int v5; // esi
  __int64 v6; // rdi
  char v7; // bp
  __int64 v8; // rcx
  unsigned __int64 v9; // r11
  __int64 v10; // r10
  int v11; // ecx
  int v12; // ecx
  unsigned __int8 v13; // r10
  unsigned int v14; // ebp
  __int64 v15; // rsi
  char v16; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rdi
  __int64 v19; // r11
  int v20; // ecx
  int v21; // ecx
  unsigned __int8 v22; // r9
  _BYTE *v23; // rcx
  _BYTE *v24; // rax
  unsigned int v25; // eax

  v1 = "?";
  if ( *(char *)(a1 + 3) < 0 )
  {
    v3 = 1;
    if ( *(_BYTE *)(a1 + 2) == 40 )
    {
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
      if ( *(_DWORD *)(a1 + 20) )
        goto LABEL_36;
      v14 = *(_DWORD *)(a1 + 56);
      if ( !v14 )
        goto LABEL_36;
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
    v13 = *(_BYTE *)(a1 + 11);
    v4 = *(_BYTE **)(a1 + 32);
LABEL_36:
    if ( v4 && v13 )
    {
      v22 = 0;
      v23 = &v4[v13];
      v24 = v4 + 8;
      if ( (unsigned __int8)((*v4 & 0x7F) - 114) <= 1u )
      {
        if ( v24 <= v23 )
          v22 = v4[2];
        v3 = v24 <= v23;
      }
      else if ( v24 > v23 )
      {
        v3 = 0;
      }
      else
      {
        v25 = v13;
        if ( (unsigned int)(unsigned __int8)v4[7] + 8 <= v13 )
          v25 = (unsigned __int8)v4[7] + 8;
        if ( v4 + 13 <= &v4[v25] )
          v22 = v4[12];
      }
      if ( v3 )
      {
        if ( v22 > 0x28u )
        {
          if ( v22 > 0x5Du )
          {
            switch ( v22 )
            {
              case 0x6Fu:
                return "SCSI_ADSENSE_COPY_PROTECTION_FAILURE";
              case 0x80u:
                return "SCSI_ADSENSE_VENDOR_UNIQUE";
              case 0xA0u:
                return "SCSI_ADSENSE_MUSIC_AREA";
              case 0xA1u:
                return "SCSI_ADSENSE_DATA_AREA";
              case 0xA7u:
                return "SCSI_ADSENSE_VOLUME_OVERFLOW";
            }
          }
          else
          {
            switch ( v22 )
            {
              case ']':
                return "SCSI_ADSENSE_FAILURE_PREDICTION_THRESHOLD_EXCEEDED";
              case ')':
                return "SCSI_ADSENSE_BUS_RESET";
              case '0':
                return "SCSI_ADSENSE_INVALID_MEDIA";
              case ':':
                return "SCSI_ADSENSE_NO_MEDIA_IN_DEVICE";
              case ';':
                return "SCSI_ADSENSE_POSITION_ERROR";
              case 'Z':
                return "SCSI_ADSENSE_OPERATOR_REQUEST";
            }
          }
        }
        else if ( v22 == 40 )
        {
          return "SCSI_ADSENSE_MEDIUM_CHANGED";
        }
        else if ( v22 > 0x18u )
        {
          switch ( v22 )
          {
            case ' ':
              return "SCSI_ADSENSE_ILLEGAL_COMMAND";
            case '!':
              return "SCSI_ADSENSE_ILLEGAL_BLOCK";
            case '$':
              return "SCSI_ADSENSE_INVALID_CDB";
            case '%':
              return "SCSI_ADSENSE_INVALID_LUN";
            case '\'':
              return "SCSI_ADSENSE_WRITE_PROTECT";
          }
        }
        else if ( v22 == 24 )
        {
          return "SCSI_ADSENSE_REC_DATA_ECC";
        }
        else if ( v22 )
        {
          switch ( v22 )
          {
            case 4u:
              return "SCSI_ADSENSE_LUN_NOT_READY";
            case 0x14u:
              return "SCSI_ADSENSE_TRACK_ERROR";
            case 0x15u:
              return "SCSI_ADSENSE_SEEK_ERROR";
            case 0x17u:
              return "SCSI_ADSENSE_REC_DATA_NOECC";
          }
        }
        else
        {
          return "SCSI_ADSENSE_NO_SENSE";
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140038b84  push    rbx
0x140038b86  push    rbp
0x140038b87  push    rsi
0x140038b88  push    rdi
0x140038b89  push    r14
0x140038b8b  cmp     byte ptr [rcx+3], 0
0x140038b8f  lea     rdx, asc_140045638; "?"
0x140038b96  mov     r9, rcx
0x140038b99  jge     loc_140038E8E
0x140038b9f  cmp     byte ptr [rcx+2], 28h ; '('
0x140038ba3  mov     ebx, 1
0x140038ba8  jnz     loc_140038C9B
0x140038bae  xor     r8d, r8d
0x140038bb1  cmp     [rcx+14h], r8d
0x140038bb5  jnz     short loc_140038C2B
0x140038bb7  mov     esi, [rcx+38h]
0x140038bba  test    esi, esi
0x140038bbc  jz      short loc_140038C2B
0x140038bbe  xor     edi, edi
0x140038bc0  xor     bpl, bpl
0x140038bc3  mov     ecx, [r9+rdi*4+78h]
0x140038bc8  cmp     ecx, 80h
0x140038bce  jb      short loc_140038C1E
0x140038bd0  mov     r11d, [r9+10h]
0x140038bd4  cmp     ecx, r11d
0x140038bd7  jnb     short loc_140038C1E
0x140038bd9  mov     r10d, ecx
0x140038bdc  mov     ecx, [rcx+r9]
0x140038be0  sub     ecx, 40h ; '@'
0x140038be3  jz      short loc_140038C10
0x140038be5  sub     ecx, ebx
0x140038be7  jz      short loc_140038BFD
0x140038be9  cmp     ecx, ebx
0x140038beb  jnz     short loc_140038C19
0x140038bed  lea     rcx, [r10+28h]
0x140038bf1  cmp     rcx, r11
0x140038bf4  ja      short loc_140038C19
0x140038bf6  mov     r8, [r10+r9+18h]
0x140038bfb  jmp     short loc_140038C2B
0x140038bfd  lea     rcx, [r10+38h]
0x140038c01  cmp     rcx, r11
0x140038c04  ja      short loc_140038C19
0x140038c06  mov     r8, [r10+r9+10h]
0x140038c0b  mov     bpl, bl
0x140038c0e  jmp     short loc_140038C19
0x140038c10  lea     rcx, [r10+28h]
0x140038c14  cmp     rcx, r11
0x140038c17  jbe     short loc_140038C26
0x140038c19  test    bpl, bpl
0x140038c1c  jnz     short loc_140038C2B
0x140038c1e  add     edi, ebx
0x140038c20  cmp     edi, esi
0x140038c22  jb      short loc_140038BC3
0x140038c24  jmp     short loc_140038C2B
0x140038c26  mov     r8, [r10+r9+10h]
0x140038c2b  xor     r10b, r10b
0x140038c2e  cmp     dword ptr [r9+14h], 0
0x140038c33  jnz     short loc_140038CA3
0x140038c35  mov     ebp, [r9+38h]
0x140038c39  test    ebp, ebp
0x140038c3b  jz      short loc_140038CA3
0x140038c3d  xor     esi, esi
0x140038c3f  xor     r14b, r14b
0x140038c42  mov     ecx, [r9+rsi*4+78h]
0x140038c47  cmp     ecx, 80h
0x140038c4d  jb      short loc_140038C79
0x140038c4f  mov     edi, [r9+10h]
0x140038c53  cmp     ecx, edi
0x140038c55  jnb     short loc_140038C79
0x140038c57  mov     r11d, ecx
0x140038c5a  mov     ecx, [rcx+r9]
0x140038c5e  sub     ecx, 40h ; '@'
0x140038c61  jz      short loc_140038C6B
0x140038c63  sub     ecx, ebx
0x140038c65  jz      short loc_140038C81
0x140038c67  cmp     ecx, ebx
0x140038c69  jnz     short loc_140038C74
0x140038c6b  lea     rcx, [r11+28h]
0x140038c6f  cmp     rcx, rdi
0x140038c72  jbe     short loc_140038C94
0x140038c74  test    r14b, r14b
0x140038c77  jnz     short loc_140038CA3
0x140038c79  add     esi, ebx
0x140038c7b  cmp     esi, ebp
0x140038c7d  jb      short loc_140038C42
0x140038c7f  jmp     short loc_140038CA3
0x140038c81  lea     rcx, [r11+38h]
0x140038c85  cmp     rcx, rdi
0x140038c88  ja      short loc_140038C74
0x140038c8a  mov     r10b, [r11+r9+9]
0x140038c8f  mov     r14b, bl
0x140038c92  jmp     short loc_140038C74
0x140038c94  mov     r10b, [r11+r9+9]
0x140038c99  jmp     short loc_140038CA3
0x140038c9b  mov     r10b, [rcx+0Bh]
0x140038c9f  mov     r8, [rcx+20h]
0x140038ca3  test    r8, r8
0x140038ca6  jz      loc_140038E8E
0x140038cac  test    r10b, r10b
0x140038caf  jz      loc_140038E8E
0x140038cb5  mov     al, [r8]
0x140038cb8  xor     r9b, r9b
0x140038cbb  and     al, 7Fh
0x140038cbd  movzx   ecx, r10b
0x140038cc1  sub     al, 72h ; 'r'
0x140038cc3  add     rcx, r8
0x140038cc6  cmp     al, bl
0x140038cc8  lea     rax, [r8+8]
0x140038ccc  jbe     short loc_140038CFC
0x140038cce  cmp     rax, rcx
0x140038cd1  ja      short loc_140038CF8
0x140038cd3  movzx   ecx, byte ptr [r8+7]
0x140038cd8  add     ecx, 8
0x140038cdb  movzx   eax, r10b
0x140038cdf  cmp     ecx, eax
0x140038ce1  cmovbe  eax, ecx
0x140038ce4  mov     ecx, eax
0x140038ce6  lea     rax, [r8+0Dh]
0x140038cea  add     rcx, r8
0x140038ced  cmp     rax, rcx
0x140038cf0  ja      short loc_140038D08
0x140038cf2  mov     r9b, [r8+0Ch]
0x140038cf6  jmp     short loc_140038D08
0x140038cf8  xor     bl, bl
0x140038cfa  jmp     short loc_140038D08
0x140038cfc  cmp     rax, rcx
0x140038cff  ja      short loc_140038D05
0x140038d01  mov     r9b, [r8+2]
0x140038d05  setbe   bl
0x140038d08  test    bl, bl
0x140038d0a  jz      loc_140038E8E
0x140038d10  movzx   ecx, r9b
0x140038d14  cmp     ecx, 28h ; '('
0x140038d17  ja      loc_140038DF4
0x140038d1d  jz      loc_140038DE8
0x140038d23  cmp     ecx, 18h
0x140038d26  ja      short loc_140038D8F
0x140038d28  jz      short loc_140038D83
0x140038d2a  test    r9b, r9b
0x140038d2d  jz      short loc_140038D77
0x140038d2f  sub     ecx, 4
0x140038d32  jz      short loc_140038D6B
0x140038d34  sub     ecx, 10h
0x140038d37  jz      short loc_140038D5F
0x140038d39  sub     ecx, 1
0x140038d3c  jz      short loc_140038D53
0x140038d3e  cmp     ecx, 2
0x140038d41  jnz     loc_140038E8E
0x140038d47  lea     rdx, aScsiAdsenseRec; "SCSI_ADSENSE_REC_DATA_NOECC"
0x140038d4e  jmp     loc_140038E8E
0x140038d53  lea     rdx, aScsiAdsenseSee; "SCSI_ADSENSE_SEEK_ERROR"
0x140038d5a  jmp     loc_140038E8E
0x140038d5f  lea     rdx, aScsiAdsenseTra; "SCSI_ADSENSE_TRACK_ERROR"
0x140038d66  jmp     loc_140038E8E
0x140038d6b  lea     rdx, aScsiAdsenseLun; "SCSI_ADSENSE_LUN_NOT_READY"
0x140038d72  jmp     loc_140038E8E
0x140038d77  lea     rdx, aScsiAdsenseNoS; "SCSI_ADSENSE_NO_SENSE"
0x140038d7e  jmp     loc_140038E8E
0x140038d83  lea     rdx, aScsiAdsenseRec_0; "SCSI_ADSENSE_REC_DATA_ECC"
0x140038d8a  jmp     loc_140038E8E
0x140038d8f  sub     ecx, 20h ; ' '
0x140038d92  jz      short loc_140038DDC
0x140038d94  sub     ecx, 1
0x140038d97  jz      short loc_140038DD0
0x140038d99  sub     ecx, 3
0x140038d9c  jz      short loc_140038DC4
0x140038d9e  sub     ecx, 1
0x140038da1  jz      short loc_140038DB8
0x140038da3  cmp     ecx, 2
0x140038da6  jnz     loc_140038E8E
0x140038dac  lea     rdx, aScsiAdsenseWri; "SCSI_ADSENSE_WRITE_PROTECT"
0x140038db3  jmp     loc_140038E8E
0x140038db8  lea     rdx, aScsiAdsenseInv; "SCSI_ADSENSE_INVALID_LUN"
0x140038dbf  jmp     loc_140038E8E
0x140038dc4  lea     rdx, aScsiAdsenseInv_0; "SCSI_ADSENSE_INVALID_CDB"
0x140038dcb  jmp     loc_140038E8E
0x140038dd0  lea     rdx, aScsiAdsenseIll; "SCSI_ADSENSE_ILLEGAL_BLOCK"
0x140038dd7  jmp     loc_140038E8E
0x140038ddc  lea     rdx, aScsiAdsenseIll_0; "SCSI_ADSENSE_ILLEGAL_COMMAND"
0x140038de3  jmp     loc_140038E8E
0x140038de8  lea     rdx, aScsiAdsenseMed; "SCSI_ADSENSE_MEDIUM_CHANGED"
0x140038def  jmp     loc_140038E8E
0x140038df4  cmp     ecx, 5Dh ; ']'
0x140038df7  ja      short loc_140038E4A
0x140038df9  jz      short loc_140038E41
0x140038dfb  sub     ecx, 29h ; ')'
0x140038dfe  jz      short loc_140038E38
0x140038e00  sub     ecx, 7
0x140038e03  jz      short loc_140038E2F
0x140038e05  sub     ecx, 0Ah
0x140038e08  jz      short loc_140038E26
0x140038e0a  sub     ecx, 1
0x140038e0d  jz      short loc_140038E1D
0x140038e0f  cmp     ecx, 1Fh
0x140038e12  jnz     short loc_140038E8E
0x140038e14  lea     rdx, aScsiAdsenseOpe; "SCSI_ADSENSE_OPERATOR_REQUEST"
0x140038e1b  jmp     short loc_140038E8E
0x140038e1d  lea     rdx, aScsiAdsensePos; "SCSI_ADSENSE_POSITION_ERROR"
0x140038e24  jmp     short loc_140038E8E
0x140038e26  lea     rdx, aScsiAdsenseNoM; "SCSI_ADSENSE_NO_MEDIA_IN_DEVICE"
0x140038e2d  jmp     short loc_140038E8E
0x140038e2f  lea     rdx, aScsiAdsenseInv_1; "SCSI_ADSENSE_INVALID_MEDIA"
0x140038e36  jmp     short loc_140038E8E
0x140038e38  lea     rdx, aScsiAdsenseBus; "SCSI_ADSENSE_BUS_RESET"
0x140038e3f  jmp     short loc_140038E8E
0x140038e41  lea     rdx, aScsiAdsenseFai; "SCSI_ADSENSE_FAILURE_PREDICTION_THRESHO"...
0x140038e48  jmp     short loc_140038E8E
0x140038e4a  sub     ecx, 6Fh ; 'o'
0x140038e4d  jz      short loc_140038E87
0x140038e4f  sub     ecx, 11h
0x140038e52  jz      short loc_140038E7E
0x140038e54  sub     ecx, 20h ; ' '
0x140038e57  jz      short loc_140038E75
0x140038e59  sub     ecx, 1
0x140038e5c  jz      short loc_140038E6C
0x140038e5e  cmp     ecx, 6
0x140038e61  jnz     short loc_140038E8E
0x140038e63  lea     rdx, aScsiAdsenseVol; "SCSI_ADSENSE_VOLUME_OVERFLOW"
0x140038e6a  jmp     short loc_140038E8E
0x140038e6c  lea     rdx, aScsiAdsenseDat; "SCSI_ADSENSE_DATA_AREA"
0x140038e73  jmp     short loc_140038E8E
0x140038e75  lea     rdx, aScsiAdsenseMus; "SCSI_ADSENSE_MUSIC_AREA"
0x140038e7c  jmp     short loc_140038E8E
0x140038e7e  lea     rdx, aScsiAdsenseVen; "SCSI_ADSENSE_VENDOR_UNIQUE"
0x140038e85  jmp     short loc_140038E8E
0x140038e87  lea     rdx, aScsiAdsenseCop; "SCSI_ADSENSE_COPY_PROTECTION_FAILURE"
0x140038e8e  mov     rax, rdx
0x140038e91  pop     r14
0x140038e93  pop     rdi
0x140038e94  pop     rsi
0x140038e95  pop     rbp
0x140038e96  pop     rbx
0x140038e97  retn
```
