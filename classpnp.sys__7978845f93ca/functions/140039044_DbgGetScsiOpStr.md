# DbgGetScsiOpStr

- ea: `0x140039044`
- end: `0x140039811`
- name: `DbgGetScsiOpStr`
- size: `1997`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000de10`
- `0x14002a090`

## callees

- `0x140039044`

## string_xrefs

- `0x1400391b4`: `SCSIOP_TEST_UNIT_READY`
- `0x1400391c0`: `SCSIOP_READ_BLOCK_LIMITS`
- `0x1400392a9`: `SCSIOP_READ_REVERSE`
- `0x140039330`: `SCSIOP_COPY`
- `0x140039378`: `SCSIOP_READ_FORMATTED_CAPACITY`
- `0x14003936c`: `SCSIOP_READ_CAPACITY`
- `0x140039360`: `SCSIOP_READ`
- `0x140039390`: `SCSIOP_WRITE`
- `0x140039425`: `SCSIOP_WRITE_VERIFY`
- `0x1400393dd`: `SCSIOP_READ_POSITION`
- `0x1400393d1`: `SCSIOP_SYNCHRONIZE_CACHE`
- `0x14003943d`: `SCSIOP_COMPARE`
- `0x1400394fa`: `SCSIOP_COPY_COMPARE`
- `0x1400394ee`: `SCSIOP_WRITE_DATA_BUFF`
- `0x1400394e2`: `SCSIOP_READ_DATA_BUFF`
- `0x1400396b7`: `SCSIOP_READ_DATA_BUFF16`
- `0x1400394ca`: `SCSIOP_READ_SUB_CHANNEL`
- `0x1400394be`: `SCSIOP_READ_TOC`
- `0x1400394b2`: `SCSIOP_READ_HEADER`
- `0x140039506`: `SCSIOP_GET_CONFIGURATION`
- `0x140039600`: `SCSIOP_READ_DISK_INFORMATION`
- `0x1400395f4`: `SCSIOP_READ_TRACK_INFORMATION`
- `0x140039659`: `SCSIOP_READ_BUFFER_CAPACITY`
- `0x14003970a`: `SCSIOP_MOVE_MEDIUM`
- `0x1400396f2`: `SCSIOP_SET_READ_AHEAD`
- `0x140039752`: `SCSIOP_READ_DVD_STRUCTURE`
- `0x140039797`: `SCSIOP_READ_ELEMENT_STATUS`
- `0x14003978e`: `SCSIOP_READ_CD_MSF`
- `0x1400397e9`: `SCSIOP_READ_CD`
- `0x140039671`: `SCSIOP_READ16`
- `0x1400396ab`: `SCSIOP_WRITE16`
- `0x140039693`: `SCSIOP_SYNCHRONIZE_CACHE16`
- `0x140039746`: `SCSIOP_READ_CAPACITY16`

## pseudocode

```c
const char *__fastcall DbgGetScsiOpStr(__int64 a1)
{
  _BYTE *v2; // r9
  unsigned int v3; // ebx
  __int64 v4; // r10
  char v5; // di
  __int64 v6; // rcx
  unsigned __int64 v7; // r11
  __int64 v8; // r8
  int v9; // ecx
  int v10; // ecx
  _BYTE *v11; // rcx
  const char *v12; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx

  if ( *(_BYTE *)(a1 + 2) != 40 )
  {
    v2 = (_BYTE *)(a1 + 72);
    goto LABEL_24;
  }
  v2 = 0;
  if ( !*(_DWORD *)(a1 + 20) )
  {
    v3 = *(_DWORD *)(a1 + 56);
    if ( v3 )
    {
      v4 = 0;
      v5 = 0;
      do
      {
        v6 = *(unsigned int *)(a1 + 4 * v4 + 120);
        if ( (unsigned int)v6 >= 0x80 )
        {
          v7 = *(unsigned int *)(a1 + 16);
          if ( (unsigned int)v6 < (unsigned int)v7 )
          {
            v8 = (unsigned int)v6;
            v9 = *(_DWORD *)(v6 + a1) - 64;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                if ( v10 == 1 && v8 + 40 <= v7 )
                {
                  v11 = (_BYTE *)(v8 + a1 + 32);
                  if ( !*(_DWORD *)(v8 + a1 + 12) )
                    v11 = v2;
                  v2 = v11;
                  break;
                }
              }
              else if ( v8 + 56 <= v7 )
              {
                if ( !*(_BYTE *)(v8 + a1 + 10) )
                  break;
                v5 = 1;
                v2 = (_BYTE *)(v8 + a1 + 24);
              }
            }
            else if ( v8 + 40 <= v7 )
            {
              if ( *(_BYTE *)(v8 + a1 + 10) )
                v2 = (_BYTE *)(v8 + a1 + 24);
              break;
            }
            if ( v5 )
              break;
          }
        }
        v4 = (unsigned int)(v4 + 1);
      }
      while ( (unsigned int)v4 < v3 );
    }
  }
LABEL_24:
  v12 = "?";
  if ( v2 )
  {
    v13 = (unsigned __int8)*v2;
    if ( v13 > 0xAD )
    {
      if ( v13 > 0xBB )
      {
        v74 = v13 - 188;
        if ( v74 )
        {
          v75 = v74 - 1;
          if ( v75 )
          {
            v76 = v75 - 1;
            if ( v76 )
            {
              v77 = v76 - 1;
              if ( v77 )
              {
                if ( v77 == 40 )
                  return "SCSIOP_INIT_ELEMENT_RANGE";
              }
              else
              {
                return "SCSIOP_SEND_DVD_STRUCTURE";
              }
            }
            else
            {
              return "SCSIOP_READ_CD";
            }
          }
          else
          {
            return "SCSIOP_MECHANISM_STATUS";
          }
        }
        else
        {
          return "SCSIOP_PLAY_CD";
        }
      }
      else if ( v13 == 187 )
      {
        return "SCSIOP_SET_CD_SPEED";
      }
      else
      {
        v70 = v13 - 181;
        if ( v70 )
        {
          v71 = v70 - 1;
          if ( v71 )
          {
            v72 = v71 - 2;
            if ( v72 )
            {
              v73 = v72 - 1;
              if ( v73 )
              {
                if ( v73 == 1 )
                  return "SCSIOP_SCAN_CD";
              }
              else
              {
                return "SCSIOP_READ_CD_MSF";
              }
            }
            else
            {
              return "SCSIOP_READ_ELEMENT_STATUS";
            }
          }
          else
          {
            return "SCSIOP_SEND_VOLUME_TAG";
          }
        }
        else
        {
          return "SCSIOP_REQUEST_VOL_ELEMENT";
        }
      }
    }
    else if ( v13 == 173 )
    {
      return "SCSIOP_READ_DVD_STRUCTURE";
    }
    else if ( v13 > 0x39 )
    {
      if ( v13 > 0x9B )
      {
        v63 = v13 - 158;
        if ( v63 )
        {
          v64 = v63 - 2;
          if ( v64 )
          {
            v65 = v64 - 1;
            if ( v65 )
            {
              v66 = v65 - 2;
              if ( v66 )
              {
                v67 = v66 - 1;
                if ( v67 )
                {
                  v68 = v67 - 1;
                  if ( v68 )
                  {
                    v69 = v68 - 1;
                    if ( v69 )
                    {
                      if ( v69 == 1 )
                        return "SCSIOP_SET_READ_AHEAD";
                    }
                    else
                    {
                      return "SCSIOP_LOAD_UNLOAD_SLOT";
                    }
                  }
                  else
                  {
                    return "SCSIOP_MOVE_MEDIUM";
                  }
                }
                else
                {
                  return "SCSIOP_REPORT_KEY";
                }
              }
              else
              {
                return "SCSIOP_SEND_KEY";
              }
            }
            else
            {
              return "SCSIOP_BLANK";
            }
          }
          else
          {
            return "SCSIOP_REPORT_LUNS";
          }
        }
        else
        {
          return "SCSIOP_READ_CAPACITY16";
        }
      }
      else if ( v13 == 155 )
      {
        return "SCSIOP_READ_DATA_BUFF16";
      }
      else if ( v13 > 0x4E )
      {
        if ( v13 > 0x88 )
        {
          v61 = v13 - 138;
          if ( v61 )
          {
            v62 = v61 - 5;
            if ( v62 )
            {
              if ( v62 == 2 )
                return "SCSIOP_SYNCHRONIZE_CACHE16";
            }
            else
            {
              return "SCSIOP_VERIFY16";
            }
          }
          else
          {
            return "SCSIOP_WRITE16";
          }
        }
        else if ( v13 == 136 )
        {
          return "SCSIOP_READ16";
        }
        else if ( v13 > 0x5A )
        {
          v57 = v13 - 91;
          if ( v57 )
          {
            v58 = v57 - 1;
            if ( v58 )
            {
              v59 = v58 - 1;
              if ( v59 )
              {
                v60 = v59 - 1;
                if ( v60 )
                {
                  if ( v60 == 1 )
                    return "SCSIOP_PERSISTENT_RESERVE_OUT";
                }
                else
                {
                  return "SCSIOP_PERSISTENT_RESERVE_IN";
                }
              }
              else
              {
                return "SCSIOP_SEND_CUE_SHEET";
              }
            }
            else
            {
              return "SCSIOP_READ_BUFFER_CAPACITY";
            }
          }
          else
          {
            return "SCSIOP_CLOSE_TRACK_SESSION";
          }
        }
        else if ( v13 == 90 )
        {
          return "SCSIOP_MODE_SENSE10";
        }
        else
        {
          v53 = v13 - 81;
          if ( v53 )
          {
            v54 = v53 - 1;
            if ( v54 )
            {
              v55 = v54 - 1;
              if ( v55 )
              {
                v56 = v55 - 1;
                if ( v56 )
                {
                  if ( v56 == 1 )
                    return "SCSIOP_MODE_SELECT10";
                }
                else
                {
                  return "SCSIOP_SEND_OPC_INFORMATION";
                }
              }
              else
              {
                return "SCSIOP_RESERVE_TRACK_RZONE";
              }
            }
            else
            {
              return "SCSIOP_READ_TRACK_INFORMATION";
            }
          }
          else
          {
            return "SCSIOP_READ_DISK_INFORMATION";
          }
        }
      }
      else if ( v13 == 78 )
      {
        return "SCSIOP_STOP_PLAY_SCAN";
      }
      else if ( v13 > 0x46 )
      {
        v47 = v13 - 71;
        if ( v47 )
        {
          v48 = v47 - 1;
          if ( v48 )
          {
            v49 = v48 - 1;
            if ( v49 )
            {
              v50 = v49 - 1;
              if ( v50 )
              {
                v51 = v50 - 1;
                if ( v51 )
                {
                  v52 = v51 - 1;
                  if ( v52 )
                  {
                    if ( v52 == 1 )
                      return "SCSIOP_LOG_SENSE";
                  }
                  else
                  {
                    return "SCSIOP_LOG_SELECT";
                  }
                }
                else
                {
                  return "SCSIOP_PAUSE_RESUME";
                }
              }
              else
              {
                return "SCSIOP_GET_EVENT_STATUS";
              }
            }
            else
            {
              return "SCSIOP_PLAY_TRACK_RELATIVE";
            }
          }
          else
          {
            return "SCSIOP_PLAY_TRACK_INDEX";
          }
        }
        else
        {
          return "SCSIOP_PLAY_AUDIO_MSF";
        }
      }
      else if ( v13 == 70 )
      {
        return "SCSIOP_GET_CONFIGURATION";
      }
      else
      {
        v40 = v13 - 58;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( v42 )
            {
              v43 = v42 - 4;
              if ( v43 )
              {
                v44 = v43 - 2;
                if ( v44 )
                {
                  v45 = v44 - 1;
                  if ( v45 )
                  {
                    v46 = v45 - 1;
                    if ( v46 )
                    {
                      if ( v46 == 1 )
                        return "SCSIOP_PLAY_AUDIO";
                    }
                    else
                    {
                      return "SCSIOP_READ_HEADER";
                    }
                  }
                  else
                  {
                    return "SCSIOP_READ_TOC";
                  }
                }
                else
                {
                  return "SCSIOP_READ_SUB_CHANNEL";
                }
              }
              else
              {
                return "SCSIOP_CHANGE_DEFINITION";
              }
            }
            else
            {
              return "SCSIOP_READ_DATA_BUFF";
            }
          }
          else
          {
            return "SCSIOP_WRITE_DATA_BUFF";
          }
        }
        else
        {
          return "SCSIOP_COPY_COMPARE";
        }
      }
    }
    else if ( v13 == 57 )
    {
      return "SCSIOP_COMPARE";
    }
    else if ( v13 > 0x17 )
    {
      if ( v13 > 0x2A )
      {
        v32 = v13 - 43;
        if ( v32 )
        {
          v33 = v32 - 3;
          if ( v33 )
          {
            v34 = v33 - 1;
            if ( v34 )
            {
              v35 = v34 - 1;
              if ( v35 )
              {
                v36 = v35 - 1;
                if ( v36 )
                {
                  v37 = v36 - 1;
                  if ( v37 )
                  {
                    v38 = v37 - 1;
                    if ( v38 )
                    {
                      v39 = v38 - 1;
                      if ( v39 )
                      {
                        if ( v39 == 1 )
                          return "SCSIOP_SYNCHRONIZE_CACHE";
                      }
                      else
                      {
                        return "SCSIOP_READ_POSITION";
                      }
                    }
                    else
                    {
                      return "SCSIOP_SET_LIMITS";
                    }
                  }
                  else
                  {
                    return "SCSIOP_SEARCH_DATA_LOW";
                  }
                }
                else
                {
                  return "SCSIOP_SEARCH_DATA_EQUAL";
                }
              }
              else
              {
                return "SCSIOP_SEARCH_DATA_HIGH";
              }
            }
            else
            {
              return "SCSIOP_VERIFY";
            }
          }
          else
          {
            return "SCSIOP_WRITE_VERIFY";
          }
        }
        else
        {
          return "SCSIOP_SEEK";
        }
      }
      else if ( v13 == 42 )
      {
        return "SCSIOP_WRITE";
      }
      else if ( v13 > 0x1D )
      {
        switch ( v13 )
        {
          case 0x1Eu:
            return "SCSIOP_MEDIUM_REMOVAL";
          case 0x23u:
            return "SCSIOP_READ_FORMATTED_CAPACITY";
          case 0x25u:
            return "SCSIOP_READ_CAPACITY";
          case 0x28u:
            return "SCSIOP_READ";
        }
      }
      else if ( v13 == 29 )
      {
        return "SCSIOP_SEND_DIAGNOSTIC";
      }
      else
      {
        v28 = v13 - 24;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                if ( v31 == 1 )
                  return "SCSIOP_RECEIVE_DIAGNOSTIC";
              }
              else
              {
                return "SCSIOP_START_STOP_UNIT";
              }
            }
            else
            {
              return "SCSIOP_MODE_SENSE";
            }
          }
          else
          {
            return "SCSIOP_ERASE";
          }
        }
        else
        {
          return "SCSIOP_COPY";
        }
      }
    }
    else if ( v13 == 23 )
    {
      return "SCSIOP_RELEASE_UNIT";
    }
    else if ( v13 > 0xC )
    {
      v20 = v13 - 13;
      if ( v20 )
      {
        v21 = v20 - 2;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                v25 = v24 - 1;
                if ( v25 )
                {
                  v26 = v25 - 1;
                  if ( v26 )
                  {
                    v27 = v26 - 1;
                    if ( v27 )
                    {
                      if ( v27 == 1 )
                        return "SCSIOP_RESERVE_UNIT";
                    }
                    else
                    {
                      return "SCSIOP_MODE_SELECT";
                    }
                  }
                  else
                  {
                    return "SCSIOP_RECOVER_BUF_DATA";
                  }
                }
                else
                {
                  return "SCSIOP_VERIFY6";
                }
              }
              else
              {
                return "SCSIOP_INQUIRY";
              }
            }
            else
            {
              return "SCSIOP_SPACE";
            }
          }
          else
          {
            return "SCSIOP_FLUSH_BUFFER";
          }
        }
        else
        {
          return "SCSIOP_READ_REVERSE";
        }
      }
      else
      {
        return "SCSIOP_PARTITION";
      }
    }
    else if ( v13 == 12 )
    {
      return "SCSIOP_SEEK_BLOCK";
    }
    else if ( v13 > 5 )
    {
      v17 = v13 - 7;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 2;
          if ( v19 )
          {
            if ( v19 == 1 )
              return "SCSIOP_SLEW_PRINT";
          }
          else
          {
            return "SCSIOP_SEND";
          }
        }
        else
        {
          return "SCSIOP_RECEIVE";
        }
      }
      else
      {
        return "SCSIOP_INIT_ELEMENT_STATUS";
      }
    }
    else if ( v13 == 5 )
    {
      return "SCSIOP_READ_BLOCK_LIMITS";
    }
    else if ( *v2 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 == 1 )
              return "SCSIOP_FORMAT_UNIT";
          }
          else
          {
            return "SCSIOP_REQUEST_SENSE";
          }
        }
        else
        {
          return "SCSIOP_REQUEST_BLOCK_ADDR";
        }
      }
      else
      {
        return "SCSIOP_REWIND";
      }
    }
    else
    {
      return "SCSIOP_TEST_UNIT_READY";
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140039044  mov     [rsp+arg_0], rbx
0x140039049  mov     [rsp+arg_8], rdi
0x14003904e  cmp     byte ptr [rcx+2], 28h ; '('
0x140039052  mov     rdx, rcx
0x140039055  jnz     loc_140039109
0x14003905b  xor     r9d, r9d
0x14003905e  cmp     [rcx+14h], r9d
0x140039062  jnz     loc_14003910D
0x140039068  mov     ebx, [rcx+38h]
0x14003906b  test    ebx, ebx
0x14003906d  jz      loc_14003910D
0x140039073  xor     r10d, r10d
0x140039076  xor     dil, dil
0x140039079  mov     ecx, [rdx+r10*4+78h]
0x14003907e  cmp     ecx, 80h
0x140039084  jb      short loc_1400390EE
0x140039086  mov     r11d, [rdx+10h]
0x14003908a  cmp     ecx, r11d
0x14003908d  jnb     short loc_1400390EE
0x14003908f  mov     r8d, ecx
0x140039092  mov     ecx, [rcx+rdx]
0x140039095  sub     ecx, 40h ; '@'
0x140039098  jz      short loc_1400390E0
0x14003909a  sub     ecx, 1
0x14003909d  jz      short loc_1400390C3
0x14003909f  cmp     ecx, 1
0x1400390a2  jnz     short loc_1400390E9
0x1400390a4  lea     rcx, [r8+28h]
0x1400390a8  cmp     rcx, r11
0x1400390ab  ja      short loc_1400390E9
0x1400390ad  lea     rcx, [rdx+20h]
0x1400390b1  add     rcx, r8
0x1400390b4  cmp     dword ptr [r8+rdx+0Ch], 0
0x1400390ba  cmovz   rcx, r9
0x1400390be  mov     r9, rcx
0x1400390c1  jmp     short loc_14003910D
0x1400390c3  lea     rcx, [r8+38h]
0x1400390c7  cmp     rcx, r11
0x1400390ca  ja      short loc_1400390E9
0x1400390cc  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400390d2  jbe     short loc_14003910D
0x1400390d4  lea     r9, [rdx+18h]
0x1400390d8  mov     dil, 1
0x1400390db  add     r9, r8
0x1400390de  jmp     short loc_1400390E9
0x1400390e0  lea     rcx, [r8+28h]
0x1400390e4  cmp     rcx, r11
0x1400390e7  jbe     short loc_1400390F8
0x1400390e9  test    dil, dil
0x1400390ec  jnz     short loc_14003910D
0x1400390ee  inc     r10d
0x1400390f1  cmp     r10d, ebx
0x1400390f4  jb      short loc_140039079
0x1400390f6  jmp     short loc_14003910D
0x1400390f8  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400390fe  jbe     short loc_14003910D
0x140039100  lea     r9, [rdx+18h]
0x140039104  add     r9, r8
0x140039107  jmp     short loc_14003910D
0x140039109  lea     r9, [rcx+48h]
0x14003910d  lea     rdx, asc_140045638; "?"
0x140039114  test    r9, r9
0x140039117  jz      loc_140039802
0x14003911d  movzx   ecx, byte ptr [r9]
0x140039121  mov     eax, 0ADh
0x140039126  cmp     ecx, eax
0x140039128  ja      loc_14003975E
0x14003912e  jz      loc_140039752
0x140039134  cmp     ecx, 39h ; '9'
0x140039137  ja      loc_140039449
0x14003913d  jz      loc_14003943D
0x140039143  cmp     ecx, 17h
0x140039146  ja      loc_1400392CD
0x14003914c  jz      loc_1400392C1
0x140039152  cmp     ecx, 0Ch
0x140039155  ja      loc_140039220
0x14003915b  jz      loc_140039214
0x140039161  cmp     ecx, 5
0x140039164  ja      short loc_1400391CC
0x140039166  jz      short loc_1400391C0
0x140039168  test    ecx, ecx
0x14003916a  jz      short loc_1400391B4
0x14003916c  sub     ecx, 1
0x14003916f  jz      short loc_1400391A8
0x140039171  sub     ecx, 1
0x140039174  jz      short loc_14003919C
0x140039176  sub     ecx, 1
0x140039179  jz      short loc_140039190
0x14003917b  cmp     ecx, 1
0x14003917e  jnz     loc_140039802
0x140039184  lea     rdx, aScsiopFormatUn; "SCSIOP_FORMAT_UNIT"
0x14003918b  jmp     loc_140039802
0x140039190  lea     rdx, aScsiopRequestS; "SCSIOP_REQUEST_SENSE"
0x140039197  jmp     loc_140039802
0x14003919c  lea     rdx, aScsiopRequestB; "SCSIOP_REQUEST_BLOCK_ADDR"
0x1400391a3  jmp     loc_140039802
0x1400391a8  lea     rdx, aScsiopRewind; "SCSIOP_REWIND"
0x1400391af  jmp     loc_140039802
0x1400391b4  lea     rdx, aScsiopTestUnit; "SCSIOP_TEST_UNIT_READY"
0x1400391bb  jmp     loc_140039802
0x1400391c0  lea     rdx, aScsiopReadBloc; "SCSIOP_READ_BLOCK_LIMITS"
0x1400391c7  jmp     loc_140039802
0x1400391cc  sub     ecx, 7
0x1400391cf  jz      short loc_140039208
0x1400391d1  sub     ecx, 1
0x1400391d4  jz      short loc_1400391FC
0x1400391d6  sub     ecx, 2
0x1400391d9  jz      short loc_1400391F0
0x1400391db  cmp     ecx, 1
0x1400391de  jnz     loc_140039802
0x1400391e4  lea     rdx, aScsiopSlewPrin; "SCSIOP_SLEW_PRINT"
0x1400391eb  jmp     loc_140039802
0x1400391f0  lea     rdx, aScsiopSend; "SCSIOP_SEND"
0x1400391f7  jmp     loc_140039802
0x1400391fc  lea     rdx, aScsiopReceive; "SCSIOP_RECEIVE"
0x140039203  jmp     loc_140039802
0x140039208  lea     rdx, aScsiopInitElem; "SCSIOP_INIT_ELEMENT_STATUS"
0x14003920f  jmp     loc_140039802
0x140039214  lea     rdx, aScsiopSeekBloc; "SCSIOP_SEEK_BLOCK"
0x14003921b  jmp     loc_140039802
0x140039220  sub     ecx, 0Dh
0x140039223  jz      loc_1400392B5
0x140039229  sub     ecx, 2
0x14003922c  jz      short loc_1400392A9
0x14003922e  sub     ecx, 1
0x140039231  jz      short loc_14003929D
0x140039233  sub     ecx, 1
0x140039236  jz      short loc_140039291
0x140039238  sub     ecx, 1
0x14003923b  jz      short loc_140039285
0x14003923d  sub     ecx, 1
0x140039240  jz      short loc_140039279
0x140039242  sub     ecx, 1
0x140039245  jz      short loc_14003926D
0x140039247  sub     ecx, 1
0x14003924a  jz      short loc_140039261
0x14003924c  cmp     ecx, 1
0x14003924f  jnz     loc_140039802
0x140039255  lea     rdx, aScsiopReserveU; "SCSIOP_RESERVE_UNIT"
0x14003925c  jmp     loc_140039802
0x140039261  lea     rdx, aScsiopModeSele; "SCSIOP_MODE_SELECT"
0x140039268  jmp     loc_140039802
0x14003926d  lea     rdx, aScsiopRecoverB; "SCSIOP_RECOVER_BUF_DATA"
0x140039274  jmp     loc_140039802
0x140039279  lea     rdx, aScsiopVerify6; "SCSIOP_VERIFY6"
0x140039280  jmp     loc_140039802
0x140039285  lea     rdx, aScsiopInquiry; "SCSIOP_INQUIRY"
0x14003928c  jmp     loc_140039802
0x140039291  lea     rdx, aScsiopSpace; "SCSIOP_SPACE"
0x140039298  jmp     loc_140039802
0x14003929d  lea     rdx, aScsiopFlushBuf; "SCSIOP_FLUSH_BUFFER"
0x1400392a4  jmp     loc_140039802
0x1400392a9  lea     rdx, aScsiopReadReve; "SCSIOP_READ_REVERSE"
0x1400392b0  jmp     loc_140039802
0x1400392b5  lea     rdx, aScsiopPartitio; "SCSIOP_PARTITION"
0x1400392bc  jmp     loc_140039802
0x1400392c1  lea     rdx, aScsiopReleaseU; "SCSIOP_RELEASE_UNIT"
0x1400392c8  jmp     loc_140039802
0x1400392cd  cmp     ecx, 2Ah ; '*'
0x1400392d0  ja      loc_14003939C
0x1400392d6  jz      loc_140039390
0x1400392dc  cmp     ecx, 1Dh
0x1400392df  ja      short loc_140039348
0x1400392e1  jz      short loc_14003933C
0x1400392e3  sub     ecx, 18h
0x1400392e6  jz      short loc_140039330
0x1400392e8  sub     ecx, 1
0x1400392eb  jz      short loc_140039324
0x1400392ed  sub     ecx, 1
0x1400392f0  jz      short loc_140039318
0x1400392f2  sub     ecx, 1
0x1400392f5  jz      short loc_14003930C
0x1400392f7  cmp     ecx, 1
0x1400392fa  jnz     loc_140039802
0x140039300  lea     rdx, aScsiopReceiveD; "SCSIOP_RECEIVE_DIAGNOSTIC"
0x140039307  jmp     loc_140039802
0x14003930c  lea     rdx, aScsiopStartSto; "SCSIOP_START_STOP_UNIT"
0x140039313  jmp     loc_140039802
0x140039318  lea     rdx, aScsiopModeSens; "SCSIOP_MODE_SENSE"
0x14003931f  jmp     loc_140039802
0x140039324  lea     rdx, aScsiopErase; "SCSIOP_ERASE"
0x14003932b  jmp     loc_140039802
0x140039330  lea     rdx, aScsiopCopy; "SCSIOP_COPY"
0x140039337  jmp     loc_140039802
0x14003933c  lea     rdx, aScsiopSendDiag; "SCSIOP_SEND_DIAGNOSTIC"
0x140039343  jmp     loc_140039802
0x140039348  cmp     ecx, 1Eh
0x14003934b  jz      short loc_140039384
0x14003934d  cmp     ecx, 23h ; '#'
0x140039350  jz      short loc_140039378
0x140039352  cmp     ecx, 25h ; '%'
0x140039355  jz      short loc_14003936C
0x140039357  cmp     ecx, 28h ; '('
0x14003935a  jnz     loc_140039802
0x140039360  lea     rdx, aScsiopRead; "SCSIOP_READ"
0x140039367  jmp     loc_140039802
0x14003936c  lea     rdx, aScsiopReadCapa; "SCSIOP_READ_CAPACITY"
0x140039373  jmp     loc_140039802
0x140039378  lea     rdx, aScsiopReadForm; "SCSIOP_READ_FORMATTED_CAPACITY"
0x14003937f  jmp     loc_140039802
0x140039384  lea     rdx, aScsiopMediumRe; "SCSIOP_MEDIUM_REMOVAL"
0x14003938b  jmp     loc_140039802
0x140039390  lea     rdx, aScsiopWrite; "SCSIOP_WRITE"
0x140039397  jmp     loc_140039802
0x14003939c  sub     ecx, 2Bh ; '+'
0x14003939f  jz      loc_140039431
0x1400393a5  sub     ecx, 3
0x1400393a8  jz      short loc_140039425
0x1400393aa  sub     ecx, 1
0x1400393ad  jz      short loc_140039419
0x1400393af  sub     ecx, 1
0x1400393b2  jz      short loc_14003940D
0x1400393b4  sub     ecx, 1
0x1400393b7  jz      short loc_140039401
0x1400393b9  sub     ecx, 1
0x1400393bc  jz      short loc_1400393F5
0x1400393be  sub     ecx, 1
0x1400393c1  jz      short loc_1400393E9
0x1400393c3  sub     ecx, 1
0x1400393c6  jz      short loc_1400393DD
0x1400393c8  cmp     ecx, 1
0x1400393cb  jnz     loc_140039802
0x1400393d1  lea     rdx, aScsiopSynchron; "SCSIOP_SYNCHRONIZE_CACHE"
0x1400393d8  jmp     loc_140039802
0x1400393dd  lea     rdx, aScsiopReadPosi; "SCSIOP_READ_POSITION"
0x1400393e4  jmp     loc_140039802
0x1400393e9  lea     rdx, aScsiopSetLimit; "SCSIOP_SET_LIMITS"
0x1400393f0  jmp     loc_140039802
0x1400393f5  lea     rdx, aScsiopSearchDa_1; "SCSIOP_SEARCH_DATA_LOW"
0x1400393fc  jmp     loc_140039802
0x140039401  lea     rdx, aScsiopSearchDa; "SCSIOP_SEARCH_DATA_EQUAL"
0x140039408  jmp     loc_140039802
0x14003940d  lea     rdx, aScsiopSearchDa_0; "SCSIOP_SEARCH_DATA_HIGH"
0x140039414  jmp     loc_140039802
0x140039419  lea     rdx, aScsiopVerify; "SCSIOP_VERIFY"
0x140039420  jmp     loc_140039802
0x140039425  lea     rdx, aScsiopWriteVer; "SCSIOP_WRITE_VERIFY"
0x14003942c  jmp     loc_140039802
0x140039431  lea     rdx, aScsiopSeek; "SCSIOP_SEEK"
0x140039438  jmp     loc_140039802
0x14003943d  lea     rdx, aScsiopCompare; "SCSIOP_COMPARE"
0x140039444  jmp     loc_140039802
0x140039449  mov     eax, 9Bh
0x14003944e  cmp     ecx, eax
0x140039450  ja      loc_1400396C3
0x140039456  jz      loc_1400396B7
0x14003945c  cmp     ecx, 4Eh ; 'N'
0x14003945f  ja      loc_140039599
0x140039465  jz      loc_14003958D
0x14003946b  cmp     ecx, 46h ; 'F'
0x14003946e  ja      loc_140039512
0x140039474  jz      loc_140039506
0x14003947a  sub     ecx, 3Ah ; ':'
0x14003947d  jz      short loc_1400394FA
0x14003947f  sub     ecx, 1
0x140039482  jz      short loc_1400394EE
0x140039484  sub     ecx, 1
0x140039487  jz      short loc_1400394E2
0x140039489  sub     ecx, 4
0x14003948c  jz      short loc_1400394D6
0x14003948e  sub     ecx, 2
0x140039491  jz      short loc_1400394CA
0x140039493  sub     ecx, 1
0x140039496  jz      short loc_1400394BE
0x140039498  sub     ecx, 1
0x14003949b  jz      short loc_1400394B2
0x14003949d  cmp     ecx, 1
0x1400394a0  jnz     loc_140039802
0x1400394a6  lea     rdx, aScsiopPlayAudi; "SCSIOP_PLAY_AUDIO"
0x1400394ad  jmp     loc_140039802
0x1400394b2  lea     rdx, aScsiopReadHead; "SCSIOP_READ_HEADER"
0x1400394b9  jmp     loc_140039802
0x1400394be  lea     rdx, aScsiopReadToc; "SCSIOP_READ_TOC"
0x1400394c5  jmp     loc_140039802
0x1400394ca  lea     rdx, aScsiopReadSubC; "SCSIOP_READ_SUB_CHANNEL"
0x1400394d1  jmp     loc_140039802
0x1400394d6  lea     rdx, aScsiopChangeDe; "SCSIOP_CHANGE_DEFINITION"
0x1400394dd  jmp     loc_140039802
0x1400394e2  lea     rdx, aScsiopReadData_0; "SCSIOP_READ_DATA_BUFF"
0x1400394e9  jmp     loc_140039802
0x1400394ee  lea     rdx, aScsiopWriteDat; "SCSIOP_WRITE_DATA_BUFF"
0x1400394f5  jmp     loc_140039802
0x1400394fa  lea     rdx, aScsiopCopyComp; "SCSIOP_COPY_COMPARE"
0x140039501  jmp     loc_140039802
0x140039506  lea     rdx, aScsiopGetConfi; "SCSIOP_GET_CONFIGURATION"
0x14003950d  jmp     loc_140039802
0x140039512  sub     ecx, 47h ; 'G'
0x140039515  jz      short loc_140039581
0x140039517  sub     ecx, 1
0x14003951a  jz      short loc_140039575
0x14003951c  sub     ecx, 1
0x14003951f  jz      short loc_140039569
0x140039521  sub     ecx, 1
0x140039524  jz      short loc_14003955D
0x140039526  sub     ecx, 1
0x140039529  jz      short loc_140039551
0x14003952b  sub     ecx, 1
0x14003952e  jz      short loc_140039545
0x140039530  cmp     ecx, 1
0x140039533  jnz     loc_140039802
  ... truncated ...
```
