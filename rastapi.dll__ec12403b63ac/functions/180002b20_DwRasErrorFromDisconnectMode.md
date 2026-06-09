# DwRasErrorFromDisconnectMode

- ea: `0x180002b20`
- end: `0x180002e14`
- name: `DwRasErrorFromDisconnectMode`
- size: `756`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cb80`
- `0x180010330`

## callees

- `0x180002b20`
- `0x18000d92c`
- `0x180024b38`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x180002ba3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x180002ba3`

## pseudocode

```c
__int64 __fastcall DwRasErrorFromDisconnectMode(DWORD dwCallStateMode, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // ecx
  int v9; // eax
  unsigned int v10; // eax
  int v11; // ecx
  linecallstatus_tag CallStatus; // [rsp+20h] [rbp-E8h] BYREF

  v2 = 0;
  if ( a2 )
  {
    v5 = *(_QWORD *)(a2 + 216);
    if ( v5 )
    {
      v6 = *(_QWORD *)(v5 + 40);
      if ( v6 )
        v2 = v6 + 48;
    }
  }
  if ( !dwCallStateMode )
  {
    if ( !a2 )
      goto LABEL_15;
    memset_0(&CallStatus.dwNeededSize, 0, 0xC4u);
    v7 = *(_QWORD *)(a2 + 216);
    v8 = *(_DWORD *)(a2 + 232);
    CallStatus.dwTotalSize = 200;
    v9 = *(_DWORD *)(v7 + 60) ? RasLineGetCallStatus(v8, (__int64)&CallStatus) : lineGetCallStatus(v8, &CallStatus);
    if ( v9 || CallStatus.dwCallState != 0x4000 )
      goto LABEL_15;
    RasTapiTrace("RASDiag: DwRasErrorFromDisconnectMode: New dwCallStateMode found 0x%x", CallStatus.dwCallStateMode);
    dwCallStateMode = CallStatus.dwCallStateMode;
  }
  if ( dwCallStateMode > 0x400 )
  {
    switch ( dwCallStateMode )
    {
      case 0x1000u:
        return 680;
      case 0x2000u:
        return 773;
      case 0x4000u:
        return 777;
      case 0x8000u:
        return 774;
      case 0x20000u:
        return 775;
      case 0x40000u:
        return 776;
      case 0x80000u:
        return 631;
    }
    goto LABEL_56;
  }
  if ( dwCallStateMode != 1024 )
  {
LABEL_15:
    switch ( dwCallStateMode )
    {
      case 2u:
        if ( v2 && *(_WORD *)(v2 + 48) == 8 )
        {
          dwCallStateMode = 807;
          RasTapiTrace(
            "RASDiag: Mapping to new error code: %d (ERROR_VPN_DISCONNECT) instead of %d (ERROR_FROM_DEVICE)",
            807,
            651);
          return dwCallStateMode;
        }
        return 651;
      case 4u:
        return 770;
      case 0x20u:
        if ( v2 )
        {
          v11 = *(_DWORD *)(v2 + 48);
          if ( (_WORD)v11 == 9 )
          {
            dwCallStateMode = 807;
            RasTapiTrace(
              "RASDiag: Mapping to new error code: %d (ERROR_VPN_DISCONNECT) instead of %d (ERROR_LINE_BUSY)",
              807,
              676);
            return dwCallStateMode;
          }
          if ( (v11 & 0xFFFF0000) == 0x80000 )
          {
            dwCallStateMode = 815;
            RasTapiTrace(
              "RASDiag: Mapping to new error code: %d (ERROR_BROADBAND_TIMEOUT) instead of %d (ERROR_LINE_BUSY)",
              815,
              676);
            return dwCallStateMode;
          }
        }
        return 676;
      case 0x40u:
        if ( v2 )
        {
          v10 = *(_DWORD *)(v2 + 48) & 0xFFFF0000;
          if ( v10 == 0x10000 )
          {
            dwCallStateMode = 809;
            RasTapiTrace(
              "RASDiag: Mapping to new error code: %d (ERROR_VPN_TIMEOUT) instead of %d (ERROR_NO_ANSWER)",
              809,
              678);
            return dwCallStateMode;
          }
          if ( v10 == 0x80000 )
          {
            dwCallStateMode = 815;
            RasTapiTrace(
              "RASDiag: Mapping to new error code: %d (ERROR_BROADBAND_TIMEOUT) instead of %d (ERROR_NO_ANSWER)",
              815,
              678);
            return dwCallStateMode;
          }
        }
        return 678;
    }
    if ( dwCallStateMode != 128 )
    {
      if ( dwCallStateMode != 256 )
      {
        if ( dwCallStateMode == 512 )
          return 771;
LABEL_56:
        if ( v2 && *(_WORD *)(v2 + 48) == 14 )
        {
          if ( (dwCallStateMode & 0x1FFF0000) == 0x530000 )
            return (unsigned __int16)dwCallStateMode;
          return dwCallStateMode;
        }
        return 651;
      }
      if ( v2 && (*(_DWORD *)(v2 + 48) & 0xFFFF0000) == 0x80000 )
      {
        dwCallStateMode = 814;
        RasTapiTrace(
          "RASDiag: Mapping to new error code: %d (ERROR_BROADBAND_NO_NIC) instead of %d (ERROR_BAD_ADDRESS_SPECIFIED)",
          814,
          769);
        return dwCallStateMode;
      }
    }
    return 769;
  }
  if ( v2 && *(_WORD *)(v2 + 48) == 8 )
  {
    dwCallStateMode = 808;
    RasTapiTrace("RASDiag: Mapping to new error code: %d (ERROR_VPN_REFUSED) instead of %d (ERROR_NO_ANSWER)", 808, 678);
  }
  else
  {
    return 772;
  }
  return dwCallStateMode;
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_0], rbx
0x180002b25  mov     [rsp+arg_10], rsi
0x180002b2a  push    rdi
0x180002b2b  sub     rsp, 100h
0x180002b32  mov     rax, cs:__security_cookie
0x180002b39  xor     rax, rsp
0x180002b3c  mov     [rsp+108h+var_18], rax
0x180002b44  xor     edi, edi
0x180002b46  mov     rsi, rdx
0x180002b49  mov     ebx, ecx
0x180002b4b  test    rdx, rdx
0x180002b4e  jz      short loc_180002B69
0x180002b50  mov     rax, [rdx+0D8h]
0x180002b57  test    rax, rax
0x180002b5a  jz      short loc_180002B69
0x180002b5c  mov     rcx, [rax+28h]
0x180002b60  test    rcx, rcx
0x180002b63  jz      short loc_180002B69
0x180002b65  lea     rdi, [rcx+30h]
0x180002b69  test    ebx, ebx
0x180002b6b  jnz     short loc_180002BD2
0x180002b6d  test    rsi, rsi
0x180002b70  jz      short loc_180002BE5
0x180002b72  xor     edx, edx; Val
0x180002b74  lea     rcx, [rsp+108h+CallStatus.dwNeededSize]; void *
0x180002b79  mov     r8d, 0C4h; Size
0x180002b7f  call    memset_0
0x180002b84  mov     rax, [rsi+0D8h]
0x180002b8b  lea     rdx, [rsp+108h+CallStatus]; lpCallStatus
0x180002b90  mov     ecx, [rsi+0E8h]; hCall
0x180002b96  mov     [rsp+108h+CallStatus.dwTotalSize], 0C8h
0x180002b9e  cmp     [rax+3Ch], ebx
0x180002ba1  jnz     short loc_180002BAB
0x180002ba3  call    cs:__imp_lineGetCallStatus
0x180002ba9  jmp     short loc_180002BB0
0x180002bab  call    RasLineGetCallStatus
0x180002bb0  test    eax, eax
0x180002bb2  jnz     short loc_180002BE5
0x180002bb4  cmp     [rsp+108h+CallStatus.dwCallState], 4000h
0x180002bbc  jnz     short loc_180002BE5
0x180002bbe  mov     edx, [rsp+108h+CallStatus.dwCallStateMode]
0x180002bc2  lea     rcx, aRasdiagDwraser; "RASDiag: DwRasErrorFromDisconnectMode: "...
0x180002bc9  call    RasTapiTrace
0x180002bce  mov     ebx, [rsp+108h+CallStatus.dwCallStateMode]
0x180002bd2  mov     eax, 400h
0x180002bd7  cmp     ebx, eax
0x180002bd9  ja      loc_180002D67
0x180002bdf  jz      loc_180002D3A
0x180002be5  mov     eax, ebx
0x180002be7  sub     eax, 2
0x180002bea  jz      loc_180002D0D
0x180002bf0  sub     eax, 2
0x180002bf3  jz      loc_180002D03
0x180002bf9  sub     eax, 1Ch
0x180002bfc  jz      loc_180002CAF
0x180002c02  sub     eax, 20h ; ' '
0x180002c05  jz      short loc_180002C62
0x180002c07  sub     eax, 40h ; '@'
0x180002c0a  jz      short loc_180002C58
0x180002c0c  sub     eax, 80h
0x180002c11  jz      short loc_180002C28
0x180002c13  cmp     eax, 100h
0x180002c18  jnz     loc_180002D9F
0x180002c1e  mov     ebx, 303h
0x180002c23  jmp     loc_180002DED
0x180002c28  test    rdi, rdi
0x180002c2b  jz      short loc_180002C58
0x180002c2d  mov     eax, [rdi+30h]
0x180002c30  and     eax, 0FFFF0000h
0x180002c35  cmp     eax, 80000h
0x180002c3a  jnz     short loc_180002C58
0x180002c3c  mov     ebx, 32Eh
0x180002c41  lea     rcx, aRasdiagMapping_3; "RASDiag: Mapping to new error code: %d "...
0x180002c48  lea     r8d, [rbx-2Dh]
0x180002c4c  mov     edx, ebx
0x180002c4e  call    RasTapiTrace
0x180002c53  jmp     loc_180002DED
0x180002c58  mov     ebx, 301h
0x180002c5d  jmp     loc_180002DED
0x180002c62  test    rdi, rdi
0x180002c65  jz      short loc_180002CA5
0x180002c67  mov     eax, [rdi+30h]
0x180002c6a  and     eax, 0FFFF0000h
0x180002c6f  cmp     eax, 10000h
0x180002c74  jnz     short loc_180002C8A
0x180002c76  mov     ebx, 329h
0x180002c7b  lea     rcx, aRasdiagMapping_2; "RASDiag: Mapping to new error code: %d "...
0x180002c82  mov     r8d, 2A6h
0x180002c88  jmp     short loc_180002C4C
0x180002c8a  cmp     eax, 80000h
0x180002c8f  jnz     short loc_180002CA5
0x180002c91  mov     ebx, 32Fh
0x180002c96  lea     rcx, aRasdiagMapping_1; "RASDiag: Mapping to new error code: %d "...
0x180002c9d  mov     r8d, 2A6h
0x180002ca3  jmp     short loc_180002C4C
0x180002ca5  mov     ebx, 2A6h
0x180002caa  jmp     loc_180002DED
0x180002caf  test    rdi, rdi
0x180002cb2  jz      short loc_180002CF9
0x180002cb4  mov     ecx, [rdi+30h]
0x180002cb7  cmp     cx, 9
0x180002cbb  jnz     short loc_180002CD4
0x180002cbd  mov     ebx, 327h
0x180002cc2  lea     rcx, aRasdiagMapping_0; "RASDiag: Mapping to new error code: %d "...
0x180002cc9  mov     r8d, 2A4h
0x180002ccf  jmp     loc_180002C4C
0x180002cd4  and     ecx, 0FFFF0000h
0x180002cda  cmp     ecx, 80000h
0x180002ce0  jnz     short loc_180002CF9
0x180002ce2  mov     ebx, 32Fh
0x180002ce7  lea     rcx, aRasdiagMapping_4; "RASDiag: Mapping to new error code: %d "...
0x180002cee  mov     r8d, 2A4h
0x180002cf4  jmp     loc_180002C4C
0x180002cf9  mov     ebx, 2A4h
0x180002cfe  jmp     loc_180002DED
0x180002d03  mov     ebx, 302h
0x180002d08  jmp     loc_180002DED
0x180002d0d  test    rdi, rdi
0x180002d10  jz      short loc_180002D30
0x180002d12  cmp     word ptr [rdi+30h], 8
0x180002d17  jnz     short loc_180002D30
0x180002d19  mov     ebx, 327h
0x180002d1e  lea     rcx, aRasdiagMapping; "RASDiag: Mapping to new error code: %d "...
0x180002d25  mov     r8d, 28Bh
0x180002d2b  jmp     loc_180002C4C
0x180002d30  mov     ebx, 28Bh
0x180002d35  jmp     loc_180002DED
0x180002d3a  test    rdi, rdi
0x180002d3d  jz      short loc_180002D5D
0x180002d3f  cmp     word ptr [rdi+30h], 8
0x180002d44  jnz     short loc_180002D5D
0x180002d46  mov     ebx, 328h
0x180002d4b  lea     rcx, aRasdiagMapping_5; "RASDiag: Mapping to new error code: %d "...
0x180002d52  mov     r8d, 2A6h
0x180002d58  jmp     loc_180002C4C
0x180002d5d  mov     ebx, 304h
0x180002d62  jmp     loc_180002DED
0x180002d67  cmp     ebx, 1000h
0x180002d6d  jz      short loc_180002DE8
0x180002d6f  cmp     ebx, 2000h
0x180002d75  jz      short loc_180002DE1
0x180002d77  cmp     ebx, 4000h
0x180002d7d  jz      short loc_180002DDA
0x180002d7f  cmp     ebx, 8000h
0x180002d85  jz      short loc_180002DD3
0x180002d87  cmp     ebx, 20000h
0x180002d8d  jz      short loc_180002DCC
0x180002d8f  cmp     ebx, 40000h
0x180002d95  jz      short loc_180002DC5
0x180002d97  cmp     ebx, 80000h
0x180002d9d  jz      short loc_180002DBE
0x180002d9f  test    rdi, rdi
0x180002da2  jz      short loc_180002D30
0x180002da4  cmp     word ptr [rdi+30h], 0Eh
0x180002da9  jnz     short loc_180002D30
0x180002dab  mov     eax, ebx
0x180002dad  and     eax, 1FFF0000h
0x180002db2  cmp     eax, 530000h
0x180002db7  jnz     short loc_180002DED
0x180002db9  movzx   ebx, bx
0x180002dbc  jmp     short loc_180002DED
0x180002dbe  mov     ebx, 277h
0x180002dc3  jmp     short loc_180002DED
0x180002dc5  mov     ebx, 308h
0x180002dca  jmp     short loc_180002DED
0x180002dcc  mov     ebx, 307h
0x180002dd1  jmp     short loc_180002DED
0x180002dd3  mov     ebx, 306h
0x180002dd8  jmp     short loc_180002DED
0x180002dda  mov     ebx, 309h
0x180002ddf  jmp     short loc_180002DED
0x180002de1  mov     ebx, 305h
0x180002de6  jmp     short loc_180002DED
0x180002de8  mov     ebx, 2A8h
0x180002ded  mov     eax, ebx
0x180002def  mov     rcx, [rsp+108h+var_18]
0x180002df7  xor     rcx, rsp; StackCookie
0x180002dfa  call    __security_check_cookie
0x180002dff  lea     r11, [rsp+108h+var_8]
0x180002e07  mov     rbx, [r11+10h]
0x180002e0b  mov     rsi, [r11+20h]
0x180002e0f  mov     rsp, r11
0x180002e12  pop     rdi
0x180002e13  retn
```
