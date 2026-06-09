# DbgGetSrbStatusStr

- ea: `0x140039aa0`
- end: `0x14003a2c5`
- name: `DbgGetSrbStatusStr`
- size: `2085`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000de10`
- `0x140014aa0`

## callees

- `0x140039aa0`

## string_xrefs

- `0x140039ba3`: `SRB_STATUS_INVALID_PATH_ID`
- `0x140039da7`: `SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_QUEUE_FROZEN`
- `0x140039fbd`: `SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_AUTOSENSE_VALID`
- `0x14003a172`: `SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID`
- `0x140039b73`: `SRB_STATUS_COMMAND_TIMEOUT`
- `0x140039d77`: `SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_QUEUE_FROZEN`
- `0x140039f8d`: `SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_AUTOSENSE_VALID`
- `0x14003a1bb`: `SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID`

## pseudocode

```c
const char *__fastcall DbgGetSrbStatusStr(__int64 a1)
{
  unsigned int v1; // edx
  const char *v2; // r8
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // edx
  unsigned int v33; // edx
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // edx
  unsigned int v37; // edx
  unsigned int v38; // edx
  unsigned int v39; // edx
  unsigned int v40; // edx
  unsigned int v41; // edx
  unsigned int v42; // edx
  unsigned int v43; // edx
  unsigned int v44; // edx
  unsigned int v45; // edx
  unsigned int v46; // edx
  unsigned int v47; // edx
  unsigned int v48; // edx
  unsigned int v49; // edx
  unsigned int v50; // edx
  unsigned int v51; // edx
  unsigned int v52; // edx
  unsigned int v53; // edx
  unsigned int v54; // edx
  unsigned int v55; // edx
  unsigned int v56; // edx
  unsigned int v57; // edx
  unsigned int v58; // edx
  unsigned int v59; // edx
  unsigned int v60; // edx
  unsigned int v61; // edx
  unsigned int v62; // edx
  unsigned int v63; // edx
  unsigned int v64; // edx
  unsigned int v65; // edx
  unsigned int v66; // edx
  unsigned int v67; // edx
  unsigned int v68; // edx
  unsigned int v69; // edx
  unsigned int v70; // edx
  unsigned int v71; // edx
  unsigned int v72; // edx
  unsigned int v73; // edx
  unsigned int v74; // edx
  unsigned int v75; // edx
  unsigned int v76; // edx
  unsigned int v77; // edx
  unsigned int v78; // edx
  unsigned int v79; // edx
  unsigned int v80; // edx
  unsigned int v81; // edx
  unsigned int v82; // edx

  v1 = *(unsigned __int8 *)(a1 + 3);
  v2 = "?";
  if ( v1 > 0x30 )
  {
    if ( v1 > 0x70 )
    {
      if ( v1 > 0xB0 )
      {
        if ( v1 > 0xCF )
        {
          if ( v1 > 0xD6 )
          {
            v78 = v1 - 224;
            if ( v78 )
            {
              v79 = v78 - 1;
              if ( v79 )
              {
                v80 = v79 - 1;
                if ( v80 )
                {
                  v81 = v80 - 1;
                  if ( v81 )
                  {
                    v82 = v81 - 1;
                    if ( v82 )
                    {
                      if ( v82 == 12 )
                        return "SRB_STATUS_INTERNAL_ERROR|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                    else
                    {
                      return "SRB_STATUS_NOT_POWERED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                  }
                  else
                  {
                    return "SRB_STATUS_ERROR_RECOVERY|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_BAD_FUNCTION|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_INVALID_TARGET_ID|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_INVALID_LUN|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else if ( v1 == 214 )
          {
            return "SRB_STATUS_REQUEST_FLUSHED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
          }
          else
          {
            v73 = v1 - 208;
            if ( v73 )
            {
              v74 = v73 - 1;
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
                      if ( v77 == 1 )
                        return "SRB_STATUS_BAD_SRB_BLOCK_LENGTH|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                    else
                    {
                      return "SRB_STATUS_PHASE_SEQUENCE_FAILURE|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                  }
                  else
                  {
                    return "SRB_STATUS_UNEXPECTED_BUS_FREE|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_DATA_OVERRUN|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_NO_HBA|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_REQUEST_SENSE_FAILED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
        }
        else if ( v1 == 207 )
        {
          return "SRB_STATUS_PARITY_ERROR|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
        }
        else if ( v1 > 0xC7 )
        {
          v68 = v1 - 200;
          if ( v68 )
          {
            v69 = v68 - 1;
            if ( v69 )
            {
              v70 = v69 - 1;
              if ( v70 )
              {
                v71 = v70 - 1;
                if ( v71 )
                {
                  v72 = v71 - 2;
                  if ( v72 )
                  {
                    if ( v72 == 1 )
                      return "SRB_STATUS_BUS_RESET|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                  }
                  else
                  {
                    return "SRB_STATUS_MESSAGE_REJECTED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_SELECTION_TIMEOUT|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_TIMEOUT|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_NO_DEVICE|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
        else if ( v1 == 199 )
        {
          return "SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
        }
        else
        {
          v62 = v1 - 192;
          if ( v62 )
          {
            v63 = v62 - 1;
            if ( v63 )
            {
              v64 = v63 - 1;
              if ( v64 )
              {
                v65 = v64 - 1;
                if ( v65 )
                {
                  v66 = v65 - 1;
                  if ( v66 )
                  {
                    v67 = v66 - 1;
                    if ( v67 )
                    {
                      if ( v67 == 1 )
                        return "SRB_STATUS_INVALID_REQUEST|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                    else
                    {
                      return "SRB_STATUS_BUSY|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                    }
                  }
                  else
                  {
                    return "SRB_STATUS_ERROR|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_ABORT_FAILED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_ABORTED|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_SUCCESS|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_PENDING|SRB_STATUS_QUEUE_FROZEN|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
      }
      else if ( v1 == 176 )
      {
        return "SRB_STATUS_INTERNAL_ERROR|SRB_STATUS_AUTOSENSE_VALID";
      }
      else if ( v1 > 0x8E )
      {
        if ( v1 > 0x95 )
        {
          v57 = v1 - 150;
          if ( v57 )
          {
            v58 = v57 - 10;
            if ( v58 )
            {
              v59 = v58 - 1;
              if ( v59 )
              {
                v60 = v59 - 1;
                if ( v60 )
                {
                  v61 = v60 - 1;
                  if ( v61 )
                  {
                    if ( v61 == 1 )
                      return "SRB_STATUS_NOT_POWERED|SRB_STATUS_AUTOSENSE_VALID";
                  }
                  else
                  {
                    return "SRB_STATUS_ERROR_RECOVERY|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_BAD_FUNCTION|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_INVALID_TARGET_ID|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_INVALID_LUN|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_REQUEST_FLUSHED|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
        else if ( v1 == 149 )
        {
          return "SRB_STATUS_BAD_SRB_BLOCK_LENGTH|SRB_STATUS_AUTOSENSE_VALID";
        }
        else
        {
          v52 = v1 - 143;
          if ( v52 )
          {
            v53 = v52 - 1;
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
                      return "SRB_STATUS_PHASE_SEQUENCE_FAILURE|SRB_STATUS_AUTOSENSE_VALID";
                  }
                  else
                  {
                    return "SRB_STATUS_UNEXPECTED_BUS_FREE|SRB_STATUS_AUTOSENSE_VALID";
                  }
                }
                else
                {
                  return "SRB_STATUS_DATA_OVERRUN|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_NO_HBA|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_REQUEST_SENSE_FAILED|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_PARITY_ERROR|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
      }
      else if ( v1 == 142 )
      {
        return "SRB_STATUS_BUS_RESET|SRB_STATUS_AUTOSENSE_VALID";
      }
      else if ( v1 > 0x86 )
      {
        v47 = v1 - 135;
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
                  if ( v51 == 2 )
                    return "SRB_STATUS_MESSAGE_REJECTED|SRB_STATUS_AUTOSENSE_VALID";
                }
                else
                {
                  return "SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_SELECTION_TIMEOUT|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_TIMEOUT|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_NO_DEVICE|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
        else
        {
          return "SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_AUTOSENSE_VALID";
        }
      }
      else if ( v1 == 134 )
      {
        return "SRB_STATUS_INVALID_REQUEST|SRB_STATUS_AUTOSENSE_VALID";
      }
      else
      {
        v42 = v1 - 128;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 1;
            if ( v44 )
            {
              v45 = v44 - 1;
              if ( v45 )
              {
                v46 = v45 - 1;
                if ( v46 )
                {
                  if ( v46 == 1 )
                    return "SRB_STATUS_BUSY|SRB_STATUS_AUTOSENSE_VALID";
                }
                else
                {
                  return "SRB_STATUS_ERROR|SRB_STATUS_AUTOSENSE_VALID";
                }
              }
              else
              {
                return "SRB_STATUS_ABORT_FAILED|SRB_STATUS_AUTOSENSE_VALID";
              }
            }
            else
            {
              return "SRB_STATUS_ABORTED|SRB_STATUS_AUTOSENSE_VALID";
            }
          }
          else
          {
            return "SRB_STATUS_SUCCESS|SRB_STATUS_AUTOSENSE_VALID";
          }
        }
        else
        {
          return "SRB_STATUS_PENDING|SRB_STATUS_AUTOSENSE_VALID";
        }
      }
    }
    else if ( v1 == 112 )
    {
      return "SRB_STATUS_INTERNAL_ERROR|SRB_STATUS_QUEUE_FROZEN";
    }
    else if ( v1 > 0x4E )
    {
      if ( v1 > 0x55 )
      {
        v37 = v1 - 86;
        if ( v37 )
        {
          v38 = v37 - 10;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( v39 )
            {
              v40 = v39 - 1;
              if ( v40 )
              {
                v41 = v40 - 1;
                if ( v41 )
                {
                  if ( v41 == 1 )
                    return "SRB_STATUS_NOT_POWERED|SRB_STATUS_QUEUE_FROZEN";
                }
                else
                {
                  return "SRB_STATUS_ERROR_RECOVERY|SRB_STATUS_QUEUE_FROZEN";
                }
              }
              else
              {
                return "SRB_STATUS_BAD_FUNCTION|SRB_STATUS_QUEUE_FROZEN";
              }
            }
            else
            {
              return "SRB_STATUS_INVALID_TARGET_ID|SRB_STATUS_QUEUE_FROZEN";
            }
          }
          else
          {
            return "SRB_STATUS_INVALID_LUN|SRB_STATUS_QUEUE_FROZEN";
          }
        }
        else
        {
          return "SRB_STATUS_REQUEST_FLUSHED|SRB_STATUS_QUEUE_FROZEN";
        }
      }
      else if ( v1 == 85 )
      {
        return "SRB_STATUS_BAD_SRB_BLOCK_LENGTH|SRB_STATUS_QUEUE_FROZEN";
      }
      else
      {
        v32 = v1 - 79;
        if ( v32 )
        {
          v33 = v32 - 1;
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
                  if ( v36 == 1 )
                    return "SRB_STATUS_PHASE_SEQUENCE_FAILURE|SRB_STATUS_QUEUE_FROZEN";
                }
                else
                {
                  return "SRB_STATUS_UNEXPECTED_BUS_FREE|SRB_STATUS_QUEUE_FROZEN";
                }
              }
              else
              {
                return "SRB_STATUS_DATA_OVERRUN|SRB_STATUS_QUEUE_FROZEN";
              }
            }
            else
            {
              return "SRB_STATUS_NO_HBA|SRB_STATUS_QUEUE_FROZEN";
            }
          }
          else
          {
            return "SRB_STATUS_REQUEST_SENSE_FAILED|SRB_STATUS_QUEUE_FROZEN";
          }
        }
        else
        {
          return "SRB_STATUS_PARITY_ERROR|SRB_STATUS_QUEUE_FROZEN";
        }
      }
    }
    else if ( v1 == 78 )
    {
      return "SRB_STATUS_BUS_RESET|SRB_STATUS_QUEUE_FROZEN";
    }
    else if ( v1 > 0x46 )
    {
      v27 = v1 - 71;
      if ( v27 )
      {
        v28 = v27 - 1;
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
                if ( v31 == 2 )
                  return "SRB_STATUS_MESSAGE_REJECTED|SRB_STATUS_QUEUE_FROZEN";
              }
              else
              {
                return "SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_QUEUE_FROZEN";
              }
            }
            else
            {
              return "SRB_STATUS_SELECTION_TIMEOUT|SRB_STATUS_QUEUE_FROZEN";
            }
          }
          else
          {
            return "SRB_STATUS_TIMEOUT|SRB_STATUS_QUEUE_FROZEN";
          }
        }
        else
        {
          return "SRB_STATUS_NO_DEVICE|SRB_STATUS_QUEUE_FROZEN";
        }
      }
      else
      {
        return "SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_QUEUE_FROZEN";
      }
    }
    else if ( v1 == 70 )
    {
      return "SRB_STATUS_INVALID_REQUEST|SRB_STATUS_QUEUE_FROZEN";
    }
    else
    {
      v22 = v1 - 64;
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
                if ( v26 == 1 )
                  return "SRB_STATUS_BUSY|SRB_STATUS_QUEUE_FROZEN";
              }
              else
              {
                return "SRB_STATUS_ERROR|SRB_STATUS_QUEUE_FROZEN";
              }
            }
            else
            {
              return "SRB_STATUS_ABORT_FAILED|SRB_STATUS_QUEUE_FROZEN";
            }
          }
          else
          {
            return "SRB_STATUS_ABORTED|SRB_STATUS_QUEUE_FROZEN";
          }
        }
        else
        {
          return "SRB_STATUS_SUCCESS|SRB_STATUS_QUEUE_FROZEN";
        }
      }
      else
      {
        return "SRB_STATUS_PENDING|SRB_STATUS_QUEUE_FROZEN";
      }
    }
  }
  else if ( v1 == 48 )
  {
    return "SRB_STATUS_INTERNAL_ERROR";
  }
  else if ( v1 > 0xE )
  {
    if ( v1 > 0x15 )
    {
      v17 = v1 - 22;
      if ( v17 )
      {
        v18 = v17 - 10;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 1;
              if ( v21 )
              {
                if ( v21 == 1 )
                  return "SRB_STATUS_NOT_POWERED";
              }
              else
              {
                return "SRB_STATUS_ERROR_RECOVERY";
              }
            }
            else
            {
              return "SRB_STATUS_BAD_FUNCTION";
            }
          }
          else
          {
            return "SRB_STATUS_INVALID_TARGET_ID";
          }
        }
        else
        {
          return "SRB_STATUS_INVALID_LUN";
        }
      }
      else
      {
        return "SRB_STATUS_REQUEST_FLUSHED";
      }
    }
    else if ( v1 == 21 )
    {
      return "SRB_STATUS_BAD_SRB_BLOCK_LENGTH";
    }
    else
    {
      v12 = v1 - 15;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
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
                  return "SRB_STATUS_PHASE_SEQUENCE_FAILURE";
              }
              else
              {
                return "SRB_STATUS_UNEXPECTED_BUS_FREE";
              }
            }
            else
            {
              return "SRB_STATUS_DATA_OVERRUN";
            }
          }
          else
          {
            return "SRB_STATUS_NO_HBA";
          }
        }
        else
        {
          return "SRB_STATUS_REQUEST_SENSE_FAILED";
        }
      }
      else
      {
        return "SRB_STATUS_PARITY_ERROR";
      }
    }
  }
  else if ( v1 == 14 )
  {
    return "SRB_STATUS_BUS_RESET";
  }
  else if ( v1 > 6 )
  {
    v7 = v1 - 7;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 2 )
                return "SRB_STATUS_MESSAGE_REJECTED";
            }
            else
            {
              return "SRB_STATUS_COMMAND_TIMEOUT";
            }
          }
          else
          {
            return "SRB_STATUS_SELECTION_TIMEOUT";
          }
        }
        else
        {
          return "SRB_STATUS_TIMEOUT";
        }
      }
      else
      {
        return "SRB_STATUS_NO_DEVICE";
      }
    }
    else
    {
      return "SRB_STATUS_INVALID_PATH_ID";
    }
  }
  else if ( v1 == 6 )
  {
    return "SRB_STATUS_INVALID_REQUEST";
  }
  else if ( *(_BYTE *)(a1 + 3) )
  {
    v3 = v1 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            if ( v6 == 1 )
              return "SRB_STATUS_BUSY";
          }
          else
          {
            return "SRB_STATUS_ERROR";
          }
        }
        else
        {
          return "SRB_STATUS_ABORT_FAILED";
        }
      }
      else
      {
        return "SRB_STATUS_ABORTED";
      }
    }
    else
    {
      return "SRB_STATUS_SUCCESS";
    }
  }
  else
  {
    return "SRB_STATUS_PENDING";
  }
  return v2;
}

```

## disassembly

```asm
0x140039aa0  movzx   edx, byte ptr [rcx+3]
0x140039aa4  lea     r8, asc_140045638; "?"
0x140039aab  cmp     edx, 30h ; '0'
0x140039aae  ja      loc_140039CAE
0x140039ab4  jz      loc_140039CA2
0x140039aba  cmp     edx, 0Eh
0x140039abd  ja      loc_140039BBB
0x140039ac3  jz      loc_140039BAF
0x140039ac9  cmp     edx, 6
0x140039acc  ja      short loc_140039B45
0x140039ace  jz      short loc_140039B39
0x140039ad0  test    edx, edx
0x140039ad2  jz      short loc_140039B2D
0x140039ad4  sub     edx, 1
0x140039ad7  jz      short loc_140039B21
0x140039ad9  sub     edx, 1
0x140039adc  jz      short loc_140039B15
0x140039ade  sub     edx, 1
0x140039ae1  jz      short loc_140039B09
0x140039ae3  sub     edx, 1
0x140039ae6  jz      short loc_140039AFD
0x140039ae8  cmp     edx, 1
0x140039aeb  jnz     loc_14003A2C1
0x140039af1  lea     r8, aSrbStatusBusy; "SRB_STATUS_BUSY"
0x140039af8  jmp     loc_14003A2C1
0x140039afd  lea     r8, aSrbStatusError_5; "SRB_STATUS_ERROR"
0x140039b04  jmp     loc_14003A2C1
0x140039b09  lea     r8, aSrbStatusAbort_3; "SRB_STATUS_ABORT_FAILED"
0x140039b10  jmp     loc_14003A2C1
0x140039b15  lea     r8, aSrbStatusAbort_4; "SRB_STATUS_ABORTED"
0x140039b1c  jmp     loc_14003A2C1
0x140039b21  lea     r8, aSrbStatusSucce_1; "SRB_STATUS_SUCCESS"
0x140039b28  jmp     loc_14003A2C1
0x140039b2d  lea     r8, aSrbStatusPendi_0; "SRB_STATUS_PENDING"
0x140039b34  jmp     loc_14003A2C1
0x140039b39  lea     r8, aSrbStatusInval_3; "SRB_STATUS_INVALID_REQUEST"
0x140039b40  jmp     loc_14003A2C1
0x140039b45  sub     edx, 7
0x140039b48  jz      short loc_140039BA3
0x140039b4a  sub     edx, 1
0x140039b4d  jz      short loc_140039B97
0x140039b4f  sub     edx, 1
0x140039b52  jz      short loc_140039B8B
0x140039b54  sub     edx, 1
0x140039b57  jz      short loc_140039B7F
0x140039b59  sub     edx, 1
0x140039b5c  jz      short loc_140039B73
0x140039b5e  cmp     edx, 2
0x140039b61  jnz     loc_14003A2C1
0x140039b67  lea     r8, aSrbStatusMessa_2; "SRB_STATUS_MESSAGE_REJECTED"
0x140039b6e  jmp     loc_14003A2C1
0x140039b73  lea     r8, aSrbStatusComma_0; "SRB_STATUS_COMMAND_TIMEOUT"
0x140039b7a  jmp     loc_14003A2C1
0x140039b7f  lea     r8, aSrbStatusSelec_2; "SRB_STATUS_SELECTION_TIMEOUT"
0x140039b86  jmp     loc_14003A2C1
0x140039b8b  lea     r8, aSrbStatusTimeo; "SRB_STATUS_TIMEOUT"
0x140039b92  jmp     loc_14003A2C1
0x140039b97  lea     r8, aSrbStatusNoDev_1; "SRB_STATUS_NO_DEVICE"
0x140039b9e  jmp     loc_14003A2C1
0x140039ba3  lea     r8, aSrbStatusInval_6; "SRB_STATUS_INVALID_PATH_ID"
0x140039baa  jmp     loc_14003A2C1
0x140039baf  lea     r8, aSrbStatusBusRe; "SRB_STATUS_BUS_RESET"
0x140039bb6  jmp     loc_14003A2C1
0x140039bbb  cmp     edx, 15h
0x140039bbe  ja      short loc_140039C38
0x140039bc0  jz      short loc_140039C2C
0x140039bc2  sub     edx, 0Fh
0x140039bc5  jz      short loc_140039C20
0x140039bc7  sub     edx, 1
0x140039bca  jz      short loc_140039C14
0x140039bcc  sub     edx, 1
0x140039bcf  jz      short loc_140039C08
0x140039bd1  sub     edx, 1
0x140039bd4  jz      short loc_140039BFC
0x140039bd6  sub     edx, 1
0x140039bd9  jz      short loc_140039BF0
0x140039bdb  cmp     edx, 1
0x140039bde  jnz     loc_14003A2C1
0x140039be4  lea     r8, aSrbStatusPhase_2; "SRB_STATUS_PHASE_SEQUENCE_FAILURE"
0x140039beb  jmp     loc_14003A2C1
0x140039bf0  lea     r8, aSrbStatusUnexp_0; "SRB_STATUS_UNEXPECTED_BUS_FREE"
0x140039bf7  jmp     loc_14003A2C1
0x140039bfc  lea     r8, aSrbStatusDataO_0; "SRB_STATUS_DATA_OVERRUN"
0x140039c03  jmp     loc_14003A2C1
0x140039c08  lea     r8, aSrbStatusNoHba_0; "SRB_STATUS_NO_HBA"
0x140039c0f  jmp     loc_14003A2C1
0x140039c14  lea     r8, aSrbStatusReque_5; "SRB_STATUS_REQUEST_SENSE_FAILED"
0x140039c1b  jmp     loc_14003A2C1
0x140039c20  lea     r8, aSrbStatusParit_2; "SRB_STATUS_PARITY_ERROR"
0x140039c27  jmp     loc_14003A2C1
0x140039c2c  lea     r8, aSrbStatusBadSr_0; "SRB_STATUS_BAD_SRB_BLOCK_LENGTH"
0x140039c33  jmp     loc_14003A2C1
0x140039c38  sub     edx, 16h
0x140039c3b  jz      short loc_140039C96
0x140039c3d  sub     edx, 0Ah
0x140039c40  jz      short loc_140039C8A
0x140039c42  sub     edx, 1
0x140039c45  jz      short loc_140039C7E
0x140039c47  sub     edx, 1
0x140039c4a  jz      short loc_140039C72
0x140039c4c  sub     edx, 1
0x140039c4f  jz      short loc_140039C66
0x140039c51  cmp     edx, 1
0x140039c54  jnz     loc_14003A2C1
0x140039c5a  lea     r8, aSrbStatusNotPo; "SRB_STATUS_NOT_POWERED"
0x140039c61  jmp     loc_14003A2C1
0x140039c66  lea     r8, aSrbStatusError_1; "SRB_STATUS_ERROR_RECOVERY"
0x140039c6d  jmp     loc_14003A2C1
0x140039c72  lea     r8, aSrbStatusBadFu_1; "SRB_STATUS_BAD_FUNCTION"
0x140039c79  jmp     loc_14003A2C1
0x140039c7e  lea     r8, aSrbStatusInval_14; "SRB_STATUS_INVALID_TARGET_ID"
0x140039c85  jmp     loc_14003A2C1
0x140039c8a  lea     r8, aSrbStatusInval_8; "SRB_STATUS_INVALID_LUN"
0x140039c91  jmp     loc_14003A2C1
0x140039c96  lea     r8, aSrbStatusReque_4; "SRB_STATUS_REQUEST_FLUSHED"
0x140039c9d  jmp     loc_14003A2C1
0x140039ca2  lea     r8, aSrbStatusInter_0; "SRB_STATUS_INTERNAL_ERROR"
0x140039ca9  jmp     loc_14003A2C1
0x140039cae  cmp     edx, 70h ; 'p'
0x140039cb1  ja      loc_140039EB2
0x140039cb7  jz      loc_140039EA6
0x140039cbd  cmp     edx, 4Eh ; 'N'
0x140039cc0  ja      loc_140039DBF
0x140039cc6  jz      loc_140039DB3
0x140039ccc  cmp     edx, 46h ; 'F'
0x140039ccf  ja      short loc_140039D49
0x140039cd1  jz      short loc_140039D3D
0x140039cd3  sub     edx, 40h ; '@'
0x140039cd6  jz      short loc_140039D31
0x140039cd8  sub     edx, 1
0x140039cdb  jz      short loc_140039D25
0x140039cdd  sub     edx, 1
0x140039ce0  jz      short loc_140039D19
0x140039ce2  sub     edx, 1
0x140039ce5  jz      short loc_140039D0D
0x140039ce7  sub     edx, 1
0x140039cea  jz      short loc_140039D01
0x140039cec  cmp     edx, 1
0x140039cef  jnz     loc_14003A2C1
0x140039cf5  lea     r8, aSrbStatusBusyS_0; "SRB_STATUS_BUSY|SRB_STATUS_QUEUE_FROZEN"
0x140039cfc  jmp     loc_14003A2C1
0x140039d01  lea     r8, aSrbStatusError; "SRB_STATUS_ERROR|SRB_STATUS_QUEUE_FROZE"...
0x140039d08  jmp     loc_14003A2C1
0x140039d0d  lea     r8, aSrbStatusAbort_2; "SRB_STATUS_ABORT_FAILED|SRB_STATUS_QUEU"...
0x140039d14  jmp     loc_14003A2C1
0x140039d19  lea     r8, aSrbStatusAbort; "SRB_STATUS_ABORTED|SRB_STATUS_QUEUE_FRO"...
0x140039d20  jmp     loc_14003A2C1
0x140039d25  lea     r8, aSrbStatusSucce_0; "SRB_STATUS_SUCCESS|SRB_STATUS_QUEUE_FRO"...
0x140039d2c  jmp     loc_14003A2C1
0x140039d31  lea     r8, aSrbStatusPendi_2; "SRB_STATUS_PENDING|SRB_STATUS_QUEUE_FRO"...
0x140039d38  jmp     loc_14003A2C1
0x140039d3d  lea     r8, aSrbStatusInval_0; "SRB_STATUS_INVALID_REQUEST|SRB_STATUS_Q"...
0x140039d44  jmp     loc_14003A2C1
0x140039d49  sub     edx, 47h ; 'G'
0x140039d4c  jz      short loc_140039DA7
0x140039d4e  sub     edx, 1
0x140039d51  jz      short loc_140039D9B
0x140039d53  sub     edx, 1
0x140039d56  jz      short loc_140039D8F
0x140039d58  sub     edx, 1
0x140039d5b  jz      short loc_140039D83
0x140039d5d  sub     edx, 1
0x140039d60  jz      short loc_140039D77
0x140039d62  cmp     edx, 2
0x140039d65  jnz     loc_14003A2C1
0x140039d6b  lea     r8, aSrbStatusMessa; "SRB_STATUS_MESSAGE_REJECTED|SRB_STATUS_"...
0x140039d72  jmp     loc_14003A2C1
0x140039d77  lea     r8, aSrbStatusComma_1; "SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_Q"...
0x140039d7e  jmp     loc_14003A2C1
0x140039d83  lea     r8, aSrbStatusSelec_1; "SRB_STATUS_SELECTION_TIMEOUT|SRB_STATUS"...
0x140039d8a  jmp     loc_14003A2C1
0x140039d8f  lea     r8, aSrbStatusTimeo_0; "SRB_STATUS_TIMEOUT|SRB_STATUS_QUEUE_FRO"...
0x140039d96  jmp     loc_14003A2C1
0x140039d9b  lea     r8, aSrbStatusNoDev_0; "SRB_STATUS_NO_DEVICE|SRB_STATUS_QUEUE_F"...
0x140039da2  jmp     loc_14003A2C1
0x140039da7  lea     r8, aSrbStatusInval_2; "SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_Q"...
0x140039dae  jmp     loc_14003A2C1
0x140039db3  lea     r8, aSrbStatusBusRe_1; "SRB_STATUS_BUS_RESET|SRB_STATUS_QUEUE_F"...
0x140039dba  jmp     loc_14003A2C1
0x140039dbf  cmp     edx, 55h ; 'U'
0x140039dc2  ja      short loc_140039E3C
0x140039dc4  jz      short loc_140039E30
0x140039dc6  sub     edx, 4Fh ; 'O'
0x140039dc9  jz      short loc_140039E24
0x140039dcb  sub     edx, 1
0x140039dce  jz      short loc_140039E18
0x140039dd0  sub     edx, 1
0x140039dd3  jz      short loc_140039E0C
0x140039dd5  sub     edx, 1
0x140039dd8  jz      short loc_140039E00
0x140039dda  sub     edx, 1
0x140039ddd  jz      short loc_140039DF4
0x140039ddf  cmp     edx, 1
0x140039de2  jnz     loc_14003A2C1
0x140039de8  lea     r8, aSrbStatusPhase_0; "SRB_STATUS_PHASE_SEQUENCE_FAILURE|SRB_S"...
0x140039def  jmp     loc_14003A2C1
0x140039df4  lea     r8, aSrbStatusUnexp; "SRB_STATUS_UNEXPECTED_BUS_FREE|SRB_STAT"...
0x140039dfb  jmp     loc_14003A2C1
0x140039e00  lea     r8, aSrbStatusDataO_1; "SRB_STATUS_DATA_OVERRUN|SRB_STATUS_QUEU"...
0x140039e07  jmp     loc_14003A2C1
0x140039e0c  lea     r8, aSrbStatusNoHba_1; "SRB_STATUS_NO_HBA|SRB_STATUS_QUEUE_FROZ"...
0x140039e13  jmp     loc_14003A2C1
0x140039e18  lea     r8, aSrbStatusReque_0; "SRB_STATUS_REQUEST_SENSE_FAILED|SRB_STA"...
0x140039e1f  jmp     loc_14003A2C1
0x140039e24  lea     r8, aSrbStatusParit_0; "SRB_STATUS_PARITY_ERROR|SRB_STATUS_QUEU"...
0x140039e2b  jmp     loc_14003A2C1
0x140039e30  lea     r8, aSrbStatusBadSr; "SRB_STATUS_BAD_SRB_BLOCK_LENGTH|SRB_STA"...
0x140039e37  jmp     loc_14003A2C1
0x140039e3c  sub     edx, 56h ; 'V'
0x140039e3f  jz      short loc_140039E9A
0x140039e41  sub     edx, 0Ah
0x140039e44  jz      short loc_140039E8E
0x140039e46  sub     edx, 1
0x140039e49  jz      short loc_140039E82
0x140039e4b  sub     edx, 1
0x140039e4e  jz      short loc_140039E76
0x140039e50  sub     edx, 1
0x140039e53  jz      short loc_140039E6A
0x140039e55  cmp     edx, 1
0x140039e58  jnz     loc_14003A2C1
0x140039e5e  lea     r8, aSrbStatusNotPo_0; "SRB_STATUS_NOT_POWERED|SRB_STATUS_QUEUE"...
0x140039e65  jmp     loc_14003A2C1
0x140039e6a  lea     r8, aSrbStatusError_4; "SRB_STATUS_ERROR_RECOVERY|SRB_STATUS_QU"...
0x140039e71  jmp     loc_14003A2C1
0x140039e76  lea     r8, aSrbStatusBadFu; "SRB_STATUS_BAD_FUNCTION|SRB_STATUS_QUEU"...
0x140039e7d  jmp     loc_14003A2C1
0x140039e82  lea     r8, aSrbStatusInval_7; "SRB_STATUS_INVALID_TARGET_ID|SRB_STATUS"...
0x140039e89  jmp     loc_14003A2C1
0x140039e8e  lea     r8, aSrbStatusInval_11; "SRB_STATUS_INVALID_LUN|SRB_STATUS_QUEUE"...
0x140039e95  jmp     loc_14003A2C1
0x140039e9a  lea     r8, aSrbStatusReque_2; "SRB_STATUS_REQUEST_FLUSHED|SRB_STATUS_Q"...
0x140039ea1  jmp     loc_14003A2C1
0x140039ea6  lea     r8, aSrbStatusInter; "SRB_STATUS_INTERNAL_ERROR|SRB_STATUS_QU"...
0x140039ead  jmp     loc_14003A2C1
0x140039eb2  mov     eax, 0B0h
0x140039eb7  cmp     edx, eax
0x140039eb9  ja      loc_14003A0D2
0x140039ebf  jz      loc_14003A0C6
0x140039ec5  mov     eax, 8Eh
0x140039eca  cmp     edx, eax
0x140039ecc  ja      loc_140039FD5
0x140039ed2  jz      loc_140039FC9
0x140039ed8  mov     eax, 86h
0x140039edd  cmp     edx, eax
0x140039edf  ja      short loc_140039F5C
0x140039ee1  jz      short loc_140039F50
0x140039ee3  sub     edx, 80h
0x140039ee9  jz      short loc_140039F44
0x140039eeb  sub     edx, 1
0x140039eee  jz      short loc_140039F38
0x140039ef0  sub     edx, 1
0x140039ef3  jz      short loc_140039F2C
0x140039ef5  sub     edx, 1
0x140039ef8  jz      short loc_140039F20
0x140039efa  sub     edx, 1
0x140039efd  jz      short loc_140039F14
0x140039eff  cmp     edx, 1
0x140039f02  jnz     loc_14003A2C1
0x140039f08  lea     r8, aSrbStatusBusyS_1; "SRB_STATUS_BUSY|SRB_STATUS_AUTOSENSE_VA"...
0x140039f0f  jmp     loc_14003A2C1
0x140039f14  lea     r8, aSrbStatusError_6; "SRB_STATUS_ERROR|SRB_STATUS_AUTOSENSE_V"...
0x140039f1b  jmp     loc_14003A2C1
0x140039f20  lea     r8, aSrbStatusAbort_0; "SRB_STATUS_ABORT_FAILED|SRB_STATUS_AUTO"...
0x140039f27  jmp     loc_14003A2C1
0x140039f2c  lea     r8, aSrbStatusAbort_1; "SRB_STATUS_ABORTED|SRB_STATUS_AUTOSENSE"...
0x140039f33  jmp     loc_14003A2C1
0x140039f38  lea     r8, aSrbStatusSucce_2; "SRB_STATUS_SUCCESS|SRB_STATUS_AUTOSENSE"...
0x140039f3f  jmp     loc_14003A2C1
0x140039f44  lea     r8, aSrbStatusPendi; "SRB_STATUS_PENDING|SRB_STATUS_AUTOSENSE"...
0x140039f4b  jmp     loc_14003A2C1
0x140039f50  lea     r8, aSrbStatusInval_4; "SRB_STATUS_INVALID_REQUEST|SRB_STATUS_A"...
0x140039f57  jmp     loc_14003A2C1
0x140039f5c  sub     edx, 87h
0x140039f62  jz      short loc_140039FBD
0x140039f64  sub     edx, 1
0x140039f67  jz      short loc_140039FB1
0x140039f69  sub     edx, 1
0x140039f6c  jz      short loc_140039FA5
0x140039f6e  sub     edx, 1
0x140039f71  jz      short loc_140039F99
0x140039f73  sub     edx, 1
0x140039f76  jz      short loc_140039F8D
0x140039f78  cmp     edx, 2
0x140039f7b  jnz     loc_14003A2C1
0x140039f81  lea     r8, aSrbStatusMessa_0; "SRB_STATUS_MESSAGE_REJECTED|SRB_STATUS_"...
0x140039f88  jmp     loc_14003A2C1
0x140039f8d  lea     r8, aSrbStatusComma; "SRB_STATUS_COMMAND_TIMEOUT|SRB_STATUS_A"...
0x140039f94  jmp     loc_14003A2C1
0x140039f99  lea     r8, aSrbStatusSelec_0; "SRB_STATUS_SELECTION_TIMEOUT|SRB_STATUS"...
0x140039fa0  jmp     loc_14003A2C1
0x140039fa5  lea     r8, aSrbStatusTimeo_2; "SRB_STATUS_TIMEOUT|SRB_STATUS_AUTOSENSE"...
0x140039fac  jmp     loc_14003A2C1
0x140039fb1  lea     r8, aSrbStatusNoDev_2; "SRB_STATUS_NO_DEVICE|SRB_STATUS_AUTOSEN"...
0x140039fb8  jmp     loc_14003A2C1
0x140039fbd  lea     r8, aSrbStatusInval_1; "SRB_STATUS_INVALID_PATH_ID|SRB_STATUS_A"...
0x140039fc4  jmp     loc_14003A2C1
0x140039fc9  lea     r8, aSrbStatusBusRe_0; "SRB_STATUS_BUS_RESET|SRB_STATUS_AUTOSEN"...
0x140039fd0  jmp     loc_14003A2C1
0x140039fd5  mov     eax, 95h
0x140039fda  cmp     edx, eax
  ... truncated ...
```
