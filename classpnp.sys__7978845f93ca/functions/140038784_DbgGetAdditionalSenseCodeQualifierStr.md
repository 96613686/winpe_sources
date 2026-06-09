# DbgGetAdditionalSenseCodeQualifierStr

- ea: `0x140038784`
- end: `0x140038b7c`
- name: `DbgGetAdditionalSenseCodeQualifierStr`
- size: `1016`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000de10`
- `0x140014aa0`

## callees

- `0x140038784`

## string_xrefs

- `0x140038b25`: `SCSI_SENSEQ_BECOMING_READY`
- `0x140038b1c`: `SCSI_SENSEQ_INIT_COMMAND_REQUIRED`
- `0x140038ae3`: `SCSI_SENSEQ_LONG_WRITE_IN_PROGRESS`
- `0x140038a8c`: `SCSI_SENSEQ_INCOMPATIBLE_MEDIA_INSTALLED`
- `0x140038a74`: `SCSI_SENSEQ_INCOMPATIBLE_FORMAT`
- `0x140038a68`: `SCSI_SENSEQ_CLEANING_CARTRIDGE_INSTALLED`
- `0x1400389fe`: `SCSI_SENSEQ_WRITE_PROTECT_ENABLE`
- `0x1400389f2`: `SCSI_SENSEQ_WRITE_PROTECT_DISABLE`
- `0x1400389a6`: `SCSI_SENSEQ_READ_OF_SCRAMBLED_SECTOR_WITHOUT_AUTHENTICATION`

## pseudocode

```c
const char *__fastcall DbgGetAdditionalSenseCodeQualifierStr(__int64 a1)
{
  const char *v1; // rdx
  char v3; // bl
  _BYTE *v4; // r8
  unsigned int v5; // esi
  __int64 v6; // r11
  char v7; // bp
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 v10; // r10
  int v11; // ecx
  int v12; // ecx
  unsigned __int8 v13; // r11
  unsigned int v14; // ebp
  __int64 v15; // rsi
  char v16; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rdi
  __int64 v19; // r10
  int v20; // ecx
  int v21; // ecx
  char v22; // r9
  char v23; // r10
  _BYTE *v24; // rcx
  _BYTE *v25; // rax
  char *v26; // r10
  unsigned int v27; // eax
  unsigned __int64 v28; // rcx

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
      v23 = 0;
      v24 = &v4[v13];
      v25 = v4 + 8;
      if ( (unsigned __int8)((*v4 & 0x7F) - 114) <= 1u )
      {
        if ( v25 <= v24 )
        {
          v22 = v4[2];
          v23 = v4[3];
          goto LABEL_50;
        }
      }
      else if ( v25 <= v24 )
      {
        v26 = v4 + 13;
        v27 = v13;
        if ( (unsigned int)(unsigned __int8)v4[7] + 8 <= v13 )
          v27 = (unsigned __int8)v4[7] + 8;
        v28 = (unsigned __int64)&v4[v27];
        if ( (unsigned __int64)v26 <= v28 )
          v22 = v4[12];
        if ( (unsigned __int64)(v4 + 14) > v28 )
          v23 = 0;
        else
          v23 = *v26;
        goto LABEL_50;
      }
      v3 = 0;
LABEL_50:
      if ( v3 )
      {
        if ( v22 )
        {
          switch ( v22 )
          {
            case 4:
              if ( v23 )
              {
                switch ( v23 )
                {
                  case 1:
                    return "SCSI_SENSEQ_BECOMING_READY";
                  case 2:
                    return "SCSI_SENSEQ_INIT_COMMAND_REQUIRED";
                  case 3:
                    return "SCSI_SENSEQ_MANUAL_INTERVENTION_REQUIRED";
                  case 4:
                    return "SCSI_SENSEQ_FORMAT_IN_PROGRESS";
                  case 5:
                    return "SCSI_SENSEQ_REBUILD_IN_PROGRESS";
                  case 6:
                    return "SCSI_SENSEQ_RECALCULATION_IN_PROGRESS";
                  case 7:
                    return "SCSI_SENSEQ_OPERATION_IN_PROGRESS";
                  case 8:
                    return "SCSI_SENSEQ_LONG_WRITE_IN_PROGRESS";
                }
              }
              else
              {
                return "SCSI_SENSEQ_CAUSE_NOT_REPORTABLE";
              }
              break;
            case 33:
              if ( v23 == 1 )
                return "SCSI_SENSEQ_ILLEGAL_ELEMENT_ADDR";
              break;
            case 48:
              if ( v23 )
              {
                switch ( v23 )
                {
                  case 1:
                    return "SCSI_SENSEQ_UNKNOWN_FORMAT";
                  case 2:
                    return "SCSI_SENSEQ_INCOMPATIBLE_FORMAT";
                  case 3:
                    return "SCSI_SENSEQ_CLEANING_CARTRIDGE_INSTALLED";
                }
              }
              else
              {
                return "SCSI_SENSEQ_INCOMPATIBLE_MEDIA_INSTALLED";
              }
              break;
            case 59:
              if ( v23 == 13 )
              {
                return "SCSI_SENSEQ_DESTINATION_FULL";
              }
              else if ( v23 == 14 )
              {
                return "SCSI_SENSEQ_SOURCE_EMPTY";
              }
              break;
            case 90:
              if ( v23 )
              {
                switch ( v23 )
                {
                  case 1:
                    return "SCSI_SENSEQ_MEDIUM_REMOVAL";
                  case 2:
                    return "SCSI_SENSEQ_WRITE_PROTECT_ENABLE";
                  case 3:
                    return "SCSI_SENSEQ_WRITE_PROTECT_DISABLE";
                }
              }
              else
              {
                return "SCSI_SENSEQ_STATE_CHANGE_INPUT";
              }
              break;
            case 111:
              if ( v23 )
              {
                switch ( v23 )
                {
                  case 1:
                    return "SCSI_SENSEQ_KEY_NOT_PRESENT";
                  case 2:
                    return "SCSI_SENSEQ_KEY_NOT_ESTABLISHED";
                  case 3:
                    return "SCSI_SENSEQ_READ_OF_SCRAMBLED_SECTOR_WITHOUT_AUTHENTICATION";
                  case 4:
                    return "SCSI_SENSEQ_MEDIA_CODE_MISMATCHED_TO_LOGICAL_UNIT";
                  case 5:
                    return "SCSI_SENSEQ_LOGICAL_UNIT_RESET_COUNT_ERROR";
                }
              }
              else
              {
                return "SCSI_SENSEQ_AUTHENTICATION_FAILURE";
              }
              break;
          }
        }
        else
        {
          switch ( v23 )
          {
            case 1:
              return "SCSI_SENSEQ_FILEMARK_DETECTED";
            case 2:
              return "SCSI_SENSEQ_END_OF_MEDIA_DETECTED";
            case 3:
              return "SCSI_SENSEQ_SETMARK_DETECTED";
            case 4:
              return "SCSI_SENSEQ_BEGINNING_OF_MEDIA_DETECTED";
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140038784  push    rbx
0x140038786  push    rbp
0x140038787  push    rsi
0x140038788  push    rdi
0x140038789  push    r14
0x14003878b  cmp     byte ptr [rcx+3], 0
0x14003878f  lea     rdx, asc_140045638; "?"
0x140038796  mov     r9, rcx
0x140038799  jge     loc_140038B71
0x14003879f  cmp     byte ptr [rcx+2], 28h ; '('
0x1400387a3  mov     ebx, 1
0x1400387a8  jnz     loc_14003889D
0x1400387ae  xor     r8d, r8d
0x1400387b1  cmp     [rcx+14h], r8d
0x1400387b5  jnz     short loc_14003882D
0x1400387b7  mov     esi, [rcx+38h]
0x1400387ba  test    esi, esi
0x1400387bc  jz      short loc_14003882D
0x1400387be  xor     r11d, r11d
0x1400387c1  xor     bpl, bpl
0x1400387c4  mov     ecx, [r9+r11*4+78h]
0x1400387c9  cmp     ecx, 80h
0x1400387cf  jb      short loc_14003881E
0x1400387d1  mov     edi, [r9+10h]
0x1400387d5  cmp     ecx, edi
0x1400387d7  jnb     short loc_14003881E
0x1400387d9  mov     r10d, ecx
0x1400387dc  mov     ecx, [rcx+r9]
0x1400387e0  sub     ecx, 40h ; '@'
0x1400387e3  jz      short loc_140038810
0x1400387e5  sub     ecx, ebx
0x1400387e7  jz      short loc_1400387FD
0x1400387e9  cmp     ecx, ebx
0x1400387eb  jnz     short loc_140038819
0x1400387ed  lea     rcx, [r10+28h]
0x1400387f1  cmp     rcx, rdi
0x1400387f4  ja      short loc_140038819
0x1400387f6  mov     r8, [r10+r9+18h]
0x1400387fb  jmp     short loc_14003882D
0x1400387fd  lea     rcx, [r10+38h]
0x140038801  cmp     rcx, rdi
0x140038804  ja      short loc_140038819
0x140038806  mov     r8, [r10+r9+10h]
0x14003880b  mov     bpl, bl
0x14003880e  jmp     short loc_140038819
0x140038810  lea     rcx, [r10+28h]
0x140038814  cmp     rcx, rdi
0x140038817  jbe     short loc_140038828
0x140038819  test    bpl, bpl
0x14003881c  jnz     short loc_14003882D
0x14003881e  add     r11d, ebx
0x140038821  cmp     r11d, esi
0x140038824  jb      short loc_1400387C4
0x140038826  jmp     short loc_14003882D
0x140038828  mov     r8, [r10+r9+10h]
0x14003882d  xor     r11b, r11b
0x140038830  cmp     dword ptr [r9+14h], 0
0x140038835  jnz     short loc_1400388A5
0x140038837  mov     ebp, [r9+38h]
0x14003883b  test    ebp, ebp
0x14003883d  jz      short loc_1400388A5
0x14003883f  xor     esi, esi
0x140038841  xor     r14b, r14b
0x140038844  mov     ecx, [r9+rsi*4+78h]
0x140038849  cmp     ecx, 80h
0x14003884f  jb      short loc_14003887B
0x140038851  mov     edi, [r9+10h]
0x140038855  cmp     ecx, edi
0x140038857  jnb     short loc_14003887B
0x140038859  mov     r10d, ecx
0x14003885c  mov     ecx, [rcx+r9]
0x140038860  sub     ecx, 40h ; '@'
0x140038863  jz      short loc_14003886D
0x140038865  sub     ecx, ebx
0x140038867  jz      short loc_140038883
0x140038869  cmp     ecx, ebx
0x14003886b  jnz     short loc_140038876
0x14003886d  lea     rcx, [r10+28h]
0x140038871  cmp     rcx, rdi
0x140038874  jbe     short loc_140038896
0x140038876  test    r14b, r14b
0x140038879  jnz     short loc_1400388A5
0x14003887b  add     esi, ebx
0x14003887d  cmp     esi, ebp
0x14003887f  jb      short loc_140038844
0x140038881  jmp     short loc_1400388A5
0x140038883  lea     rcx, [r10+38h]
0x140038887  cmp     rcx, rdi
0x14003888a  ja      short loc_140038876
0x14003888c  mov     r11b, [r10+r9+9]
0x140038891  mov     r14b, bl
0x140038894  jmp     short loc_140038876
0x140038896  mov     r11b, [r10+r9+9]
0x14003889b  jmp     short loc_1400388A5
0x14003889d  mov     r11b, [rcx+0Bh]
0x1400388a1  mov     r8, [rcx+20h]
0x1400388a5  test    r8, r8
0x1400388a8  jz      loc_140038B71
0x1400388ae  test    r11b, r11b
0x1400388b1  jz      loc_140038B71
0x1400388b7  mov     al, [r8]
0x1400388ba  xor     r9b, r9b
0x1400388bd  and     al, 7Fh
0x1400388bf  movzx   ecx, r11b
0x1400388c3  sub     al, 72h ; 'r'
0x1400388c5  xor     r10b, r10b
0x1400388c8  add     rcx, r8
0x1400388cb  cmp     al, bl
0x1400388cd  lea     rax, [r8+8]
0x1400388d1  jbe     short loc_14003890E
0x1400388d3  cmp     rax, rcx
0x1400388d6  ja      short loc_14003891D
0x1400388d8  movzx   ecx, byte ptr [r8+7]
0x1400388dd  lea     r10, [r8+0Dh]
0x1400388e1  add     ecx, 8
0x1400388e4  movzx   eax, r11b
0x1400388e8  cmp     ecx, eax
0x1400388ea  cmovbe  eax, ecx
0x1400388ed  mov     ecx, eax
0x1400388ef  add     rcx, r8
0x1400388f2  cmp     r10, rcx
0x1400388f5  ja      short loc_1400388FB
0x1400388f7  mov     r9b, [r8+0Ch]
0x1400388fb  lea     rax, [r8+0Eh]
0x1400388ff  cmp     rax, rcx
0x140038902  ja      short loc_140038909
0x140038904  mov     r10b, [r10]
0x140038907  jmp     short loc_14003891F
0x140038909  xor     r10b, r10b
0x14003890c  jmp     short loc_14003891F
0x14003890e  cmp     rax, rcx
0x140038911  ja      short loc_14003891D
0x140038913  mov     r9b, [r8+2]
0x140038917  mov     r10b, [r8+3]
0x14003891b  jmp     short loc_14003891F
0x14003891d  xor     bl, bl
0x14003891f  test    bl, bl
0x140038921  jz      loc_140038B71
0x140038927  test    r9b, r9b
0x14003892a  jz      loc_140038B37
0x140038930  cmp     r9b, 4
0x140038934  jz      loc_140038AAE
0x14003893a  cmp     r9b, 21h ; '!'
0x14003893e  jz      loc_140038A98
0x140038944  cmp     r9b, 30h ; '0'
0x140038948  jz      loc_140038A4C
0x14003894e  cmp     r9b, 3Bh ; ';'
0x140038952  jz      loc_140038A22
0x140038958  cmp     r9b, 5Ah ; 'Z'
0x14003895c  jz      short loc_1400389D6
0x14003895e  cmp     r9b, 6Fh ; 'o'
0x140038962  jnz     loc_140038B71
0x140038968  movzx   ecx, r10b
0x14003896c  test    r10b, r10b
0x14003896f  jz      short loc_1400389CA
0x140038971  sub     ecx, 1
0x140038974  jz      short loc_1400389BE
0x140038976  sub     ecx, 1
0x140038979  jz      short loc_1400389B2
0x14003897b  sub     ecx, 1
0x14003897e  jz      short loc_1400389A6
0x140038980  sub     ecx, 1
0x140038983  jz      short loc_14003899A
0x140038985  cmp     ecx, 1
0x140038988  jnz     loc_140038B71
0x14003898e  lea     rdx, aScsiSenseqLogi; "SCSI_SENSEQ_LOGICAL_UNIT_RESET_COUNT_ER"...
0x140038995  jmp     loc_140038B71
0x14003899a  lea     rdx, aScsiSenseqMedi; "SCSI_SENSEQ_MEDIA_CODE_MISMATCHED_TO_LO"...
0x1400389a1  jmp     loc_140038B71
0x1400389a6  lea     rdx, aScsiSenseqRead; "SCSI_SENSEQ_READ_OF_SCRAMBLED_SECTOR_WI"...
0x1400389ad  jmp     loc_140038B71
0x1400389b2  lea     rdx, aScsiSenseqKeyN; "SCSI_SENSEQ_KEY_NOT_ESTABLISHED"
0x1400389b9  jmp     loc_140038B71
0x1400389be  lea     rdx, aScsiSenseqKeyN_0; "SCSI_SENSEQ_KEY_NOT_PRESENT"
0x1400389c5  jmp     loc_140038B71
0x1400389ca  lea     rdx, aScsiSenseqAuth; "SCSI_SENSEQ_AUTHENTICATION_FAILURE"
0x1400389d1  jmp     loc_140038B71
0x1400389d6  movzx   ecx, r10b
0x1400389da  test    r10b, r10b
0x1400389dd  jz      short loc_140038A16
0x1400389df  sub     ecx, 1
0x1400389e2  jz      short loc_140038A0A
0x1400389e4  sub     ecx, 1
0x1400389e7  jz      short loc_1400389FE
0x1400389e9  cmp     ecx, 1
0x1400389ec  jnz     loc_140038B71
0x1400389f2  lea     rdx, aScsiSenseqWrit; "SCSI_SENSEQ_WRITE_PROTECT_DISABLE"
0x1400389f9  jmp     loc_140038B71
0x1400389fe  lea     rdx, aScsiSenseqWrit_0; "SCSI_SENSEQ_WRITE_PROTECT_ENABLE"
0x140038a05  jmp     loc_140038B71
0x140038a0a  lea     rdx, aScsiSenseqMedi_0; "SCSI_SENSEQ_MEDIUM_REMOVAL"
0x140038a11  jmp     loc_140038B71
0x140038a16  lea     rdx, aScsiSenseqStat; "SCSI_SENSEQ_STATE_CHANGE_INPUT"
0x140038a1d  jmp     loc_140038B71
0x140038a22  movzx   ecx, r10b
0x140038a26  sub     ecx, 0Dh
0x140038a29  jz      short loc_140038A40
0x140038a2b  cmp     ecx, 1
0x140038a2e  jnz     loc_140038B71
0x140038a34  lea     rdx, aScsiSenseqSour; "SCSI_SENSEQ_SOURCE_EMPTY"
0x140038a3b  jmp     loc_140038B71
0x140038a40  lea     rdx, aScsiSenseqDest; "SCSI_SENSEQ_DESTINATION_FULL"
0x140038a47  jmp     loc_140038B71
0x140038a4c  movzx   ecx, r10b
0x140038a50  test    r10b, r10b
0x140038a53  jz      short loc_140038A8C
0x140038a55  sub     ecx, 1
0x140038a58  jz      short loc_140038A80
0x140038a5a  sub     ecx, 1
0x140038a5d  jz      short loc_140038A74
0x140038a5f  cmp     ecx, 1
0x140038a62  jnz     loc_140038B71
0x140038a68  lea     rdx, aScsiSenseqClea; "SCSI_SENSEQ_CLEANING_CARTRIDGE_INSTALLE"...
0x140038a6f  jmp     loc_140038B71
0x140038a74  lea     rdx, aScsiSenseqInco_0; "SCSI_SENSEQ_INCOMPATIBLE_FORMAT"
0x140038a7b  jmp     loc_140038B71
0x140038a80  lea     rdx, aScsiSenseqUnkn; "SCSI_SENSEQ_UNKNOWN_FORMAT"
0x140038a87  jmp     loc_140038B71
0x140038a8c  lea     rdx, aScsiSenseqInco; "SCSI_SENSEQ_INCOMPATIBLE_MEDIA_INSTALLE"...
0x140038a93  jmp     loc_140038B71
0x140038a98  cmp     r10b, 1
0x140038a9c  jnz     loc_140038B71
0x140038aa2  lea     rdx, aScsiSenseqIlle; "SCSI_SENSEQ_ILLEGAL_ELEMENT_ADDR"
0x140038aa9  jmp     loc_140038B71
0x140038aae  movzx   ecx, r10b
0x140038ab2  test    r10b, r10b
0x140038ab5  jz      short loc_140038B2E
0x140038ab7  sub     ecx, 1
0x140038aba  jz      short loc_140038B25
0x140038abc  sub     ecx, 1
0x140038abf  jz      short loc_140038B1C
0x140038ac1  sub     ecx, 1
0x140038ac4  jz      short loc_140038B13
0x140038ac6  sub     ecx, 1
0x140038ac9  jz      short loc_140038B0A
0x140038acb  sub     ecx, 1
0x140038ace  jz      short loc_140038B01
0x140038ad0  sub     ecx, 1
0x140038ad3  jz      short loc_140038AF8
0x140038ad5  sub     ecx, 1
0x140038ad8  jz      short loc_140038AEF
0x140038ada  cmp     ecx, 1
0x140038add  jnz     loc_140038B71
0x140038ae3  lea     rdx, aScsiSenseqLong; "SCSI_SENSEQ_LONG_WRITE_IN_PROGRESS"
0x140038aea  jmp     loc_140038B71
0x140038aef  lea     rdx, aScsiSenseqOper; "SCSI_SENSEQ_OPERATION_IN_PROGRESS"
0x140038af6  jmp     short loc_140038B71
0x140038af8  lea     rdx, aScsiSenseqReca; "SCSI_SENSEQ_RECALCULATION_IN_PROGRESS"
0x140038aff  jmp     short loc_140038B71
0x140038b01  lea     rdx, aScsiSenseqRebu; "SCSI_SENSEQ_REBUILD_IN_PROGRESS"
0x140038b08  jmp     short loc_140038B71
0x140038b0a  lea     rdx, aScsiSenseqForm; "SCSI_SENSEQ_FORMAT_IN_PROGRESS"
0x140038b11  jmp     short loc_140038B71
0x140038b13  lea     rdx, aScsiSenseqManu; "SCSI_SENSEQ_MANUAL_INTERVENTION_REQUIRE"...
0x140038b1a  jmp     short loc_140038B71
0x140038b1c  lea     rdx, aScsiSenseqInit; "SCSI_SENSEQ_INIT_COMMAND_REQUIRED"
0x140038b23  jmp     short loc_140038B71
0x140038b25  lea     rdx, aScsiSenseqBeco; "SCSI_SENSEQ_BECOMING_READY"
0x140038b2c  jmp     short loc_140038B71
0x140038b2e  lea     rdx, aScsiSenseqCaus; "SCSI_SENSEQ_CAUSE_NOT_REPORTABLE"
0x140038b35  jmp     short loc_140038B71
0x140038b37  movzx   ecx, r10b
0x140038b3b  sub     ecx, 1
0x140038b3e  jz      short loc_140038B6A
0x140038b40  sub     ecx, 1
0x140038b43  jz      short loc_140038B61
0x140038b45  sub     ecx, 1
0x140038b48  jz      short loc_140038B58
0x140038b4a  cmp     ecx, 1
0x140038b4d  jnz     short loc_140038B71
0x140038b4f  lea     rdx, aScsiSenseqBegi; "SCSI_SENSEQ_BEGINNING_OF_MEDIA_DETECTED"
0x140038b56  jmp     short loc_140038B71
0x140038b58  lea     rdx, aScsiSenseqSetm; "SCSI_SENSEQ_SETMARK_DETECTED"
0x140038b5f  jmp     short loc_140038B71
0x140038b61  lea     rdx, aScsiSenseqEndO; "SCSI_SENSEQ_END_OF_MEDIA_DETECTED"
0x140038b68  jmp     short loc_140038B71
0x140038b6a  lea     rdx, aScsiSenseqFile; "SCSI_SENSEQ_FILEMARK_DETECTED"
0x140038b71  mov     rax, rdx
0x140038b74  pop     r14
0x140038b76  pop     rdi
0x140038b77  pop     rsi
0x140038b78  pop     rbp
0x140038b79  pop     rbx
0x140038b7a  retn
```
