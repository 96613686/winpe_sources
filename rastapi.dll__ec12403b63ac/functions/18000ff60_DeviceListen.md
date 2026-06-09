# DeviceListen

- ea: `0x18000ff60`
- end: `0x1800101c4`
- name: `DeviceListen`
- size: `612`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cb80`

## callees

- `0x18000d92c`
- `0x18000ff60`
- `0x180012340`
- `0x180012f20`
- `0x180023610`
- `0x18002619c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001019b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001019b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800100d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010191`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800100d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010191`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001003c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001003c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x1800100ff`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x1800100ff`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000fff1`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000fff1`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180010095`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180010095`

## string_xrefs

- `0x18000ffb2`: `DeviceListen : open the line for listen`
- `0x180010042`: `DeviceListen: Opening line in owner mode`
- `0x1800100bd`: `DeviceListen: %s. lineOpen failed. 0x%x`

## pseudocode

```c
__int64 DeviceListen()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rbx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  DWORD *dwCallbackInstance; // rcx
  DWORD dwMediaModes; // r8d
  LONG v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax

  v2 = LookUpControlBlock();
  if ( !v2 )
  {
    RasTapiTrace("DeviceListen: hPort = 0x%x not found");
    return 615;
  }
  GetMutex(v1, v0, v3, v4);
  v6 = *(_QWORD *)(v2 + 216);
  if ( !*(_DWORD *)(v6 + 52) && (*(_BYTE *)(v6 + 48) & 2) != 0 )
  {
    RasTapiTrace("DeviceListen : open the line for listen");
    *(_DWORD *)(*(_QWORD *)(v2 + 216) + 48LL) &= ~2u;
    goto LABEL_6;
  }
  if ( *(_DWORD *)(v2 + 56) != 5 )
  {
LABEL_23:
    v14 = *(_QWORD *)(v2 + 216);
    if ( *(_DWORD *)(v14 + 16) != 2 )
      *(_DWORD *)(v14 + 16) = 2;
    RasTapiTrace("DeviceListen: Changing State for %s from %d -> %d");
    v15 = *(_QWORD *)(v2 + 216);
    *(_DWORD *)(v2 + 56) = 2;
    v16 = *(_DWORD *)(v15 + 48);
    if ( (v16 & 1) != 0 )
      *(_DWORD *)(v15 + 48) = v16 | 2;
    RasTapiTrace("DeviceListen: Changing Listen State for %s from %d -> %d");
    *(_DWORD *)(v2 + 60) = 0;
    *(_DWORD *)(v2 + 1092) = 0;
    *(_DWORD *)(v2 + 232) = -1;
    goto LABEL_28;
  }
  if ( *(_DWORD *)(v6 + 36) )
  {
    if ( (*(_BYTE *)(v2 + 1104) & 4) != 0 )
    {
      RasTapiTrace("DeviceListen: pending listen because lineDrop is pending on this port. %s");
      *(_DWORD *)(v2 + 1104) |= 8u;
LABEL_28:
      if ( !ReleaseMutex(RasTapiMutex) )
        GetLastError();
      v12 = 600;
      goto LABEL_31;
    }
    goto LABEL_23;
  }
LABEL_6:
  RasTapiTrace("DeviceListen: Hammering LineClosed!");
  RasTapiTrace("Closing line");
  v7 = *(_QWORD *)(v2 + 216);
  v8 = *(unsigned int *)(v7 + 12);
  if ( *(_DWORD *)(v7 + 60) )
    RasLineClose(v8);
  else
    lineClose(v8);
  Sleep(0x1Eu);
  RasTapiTrace("DeviceListen: Opening line in owner mode");
  dwCallbackInstance = *(DWORD **)(v2 + 216);
  dwMediaModes = dwCallbackInstance[14];
  if ( dwCallbackInstance[15] )
    v11 = RasLineOpen(
            dwCallbackInstance[2],
            4,
            dwMediaModes,
            (_DWORD)dwCallbackInstance,
            (__int64)(dwCallbackInstance + 3));
  else
    v11 = lineOpenA(
            RasLine,
            dwCallbackInstance[2],
            dwCallbackInstance + 3,
            dwCallbackInstance[6],
            dwCallbackInstance[7],
            (DWORD_PTR)dwCallbackInstance,
            4u,
            dwMediaModes,
            0);
  if ( !v11 )
  {
    v13 = *(_QWORD *)(v2 + 216);
    if ( !*(_DWORD *)(v13 + 60) && lineSetStatusMessages(*(_DWORD *)(v13 + 12), 2u, 0) )
      RasTapiTrace("DeviceListen: %s. Failed to post listen. %d");
    goto LABEL_23;
  }
  RasTapiTrace("DeviceListen: %s. lineOpen failed. 0x%x");
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  v12 = 651;
LABEL_31:
  RasTapiTrace(" ");
  return v12;
}

```

## disassembly

```asm
0x18000ff60  mov     [rsp+arg_0], rbx
0x18000ff65  mov     [rsp+arg_8], rbp
0x18000ff6a  push    rdi
0x18000ff6b  sub     rsp, 50h
0x18000ff6f  call    LookUpControlBlock
0x18000ff74  mov     rbx, rax
0x18000ff77  test    rax, rax
0x18000ff7a  jnz     short loc_18000FF95
0x18000ff7c  mov     rdx, rcx
0x18000ff7f  lea     rcx, aDevicelistenHp; "DeviceListen: hPort = 0x%x not found"
0x18000ff86  call    RasTapiTrace
0x18000ff8b  mov     eax, 267h
0x18000ff90  jmp     loc_1800101B4
0x18000ff95  call    GetMutex
0x18000ff9a  mov     rax, [rbx+0D8h]
0x18000ffa1  mov     ebp, 2
0x18000ffa6  cmp     dword ptr [rax+34h], 0
0x18000ffaa  jnz     short loc_18000FFF9
0x18000ffac  test    [rax+30h], bpl
0x18000ffb0  jz      short loc_18000FFF9
0x18000ffb2  lea     rcx, aDevicelistenOp_0; "DeviceListen : open the line for listen"
0x18000ffb9  call    RasTapiTrace
0x18000ffbe  mov     rax, [rbx+0D8h]
0x18000ffc5  and     dword ptr [rax+30h], 0FFFFFFFDh
0x18000ffc9  lea     rcx, aDevicelistenHa; "DeviceListen: Hammering LineClosed!"
0x18000ffd0  call    RasTapiTrace
0x18000ffd5  lea     rcx, aClosingLine; "Closing line"
0x18000ffdc  call    RasTapiTrace
0x18000ffe1  mov     rax, [rbx+0D8h]
0x18000ffe8  cmp     dword ptr [rax+3Ch], 0
0x18000ffec  mov     ecx, [rax+0Ch]; hLine
0x18000ffef  jnz     short loc_180010032
0x18000fff1  call    cs:__imp_lineClose
0x18000fff7  jmp     short loc_180010037
0x18000fff9  cmp     dword ptr [rbx+38h], 5
0x18000fffd  jnz     loc_18001011C
0x180010003  cmp     dword ptr [rax+24h], 0
0x180010007  jz      short loc_18000FFC9
0x180010009  test    byte ptr [rbx+450h], 4
0x180010010  jz      loc_18001011C
0x180010016  lea     rdx, [rbx+18h]
0x18001001a  lea     rcx, aDevicelistenPe; "DeviceListen: pending listen because li"...
0x180010021  call    RasTapiTrace
0x180010026  or      dword ptr [rbx+450h], 8
0x18001002d  jmp     loc_18001018A
0x180010032  call    RasLineClose
0x180010037  mov     ecx, 1Eh; dwMilliseconds
0x18001003c  call    cs:__imp_Sleep
0x180010042  lea     rcx, aDevicelistenOp; "DeviceListen: Opening line in owner mod"...
0x180010049  call    RasTapiTrace
0x18001004e  mov     rcx, [rbx+0D8h]
0x180010055  cmp     dword ptr [rcx+3Ch], 0
0x180010059  lea     rdx, [rcx+0Ch]
0x18001005d  mov     r8d, [rcx+38h]
0x180010061  jnz     short loc_18001009D
0x180010063  mov     eax, [rcx+1Ch]
0x180010066  mov     r9d, [rcx+18h]; dwAPIVersion
0x18001006a  mov     [rsp+58h+lpCallParams], 0; lpCallParams
0x180010073  mov     [rsp+58h+dwMediaModes], r8d; dwMediaModes
0x180010078  mov     r8, rdx; lphLine
0x18001007b  mov     edx, [rcx+8]; dwDeviceID
0x18001007e  mov     [rsp+58h+dwPrivileges], 4; dwPrivileges
0x180010086  mov     [rsp+58h+dwCallbackInstance], rcx; dwCallbackInstance
0x18001008b  mov     ecx, cs:RasLine; hLineApp
0x180010091  mov     [rsp+58h+dwExtVersion], eax; dwExtVersion
0x180010095  call    cs:__imp_lineOpenA
0x18001009b  jmp     short loc_1800100B2
0x18001009d  mov     qword ptr [rsp+58h+dwExtVersion], rdx
0x1800100a2  mov     r9, rcx
0x1800100a5  mov     ecx, [rcx+8]
0x1800100a8  mov     edx, 4
0x1800100ad  call    RasLineOpen
0x1800100b2  test    eax, eax
0x1800100b4  jz      short loc_1800100EA
0x1800100b6  lea     rdx, [rbx+18h]
0x1800100ba  mov     r8d, eax
0x1800100bd  lea     rcx, aDevicelistenSL; "DeviceListen: %s. lineOpen failed. 0x%x"
0x1800100c4  call    RasTapiTrace
0x1800100c9  mov     rcx, cs:RasTapiMutex; hMutex
0x1800100d0  call    cs:__imp_ReleaseMutex
0x1800100d6  test    eax, eax
0x1800100d8  jnz     short loc_1800100E0
0x1800100da  call    cs:__imp_GetLastError
0x1800100e0  mov     ebx, 28Bh
0x1800100e5  jmp     loc_1800101A6
0x1800100ea  mov     rcx, [rbx+0D8h]
0x1800100f1  cmp     dword ptr [rcx+3Ch], 0
0x1800100f5  jnz     short loc_18001011C
0x1800100f7  mov     ecx, [rcx+0Ch]; hLine
0x1800100fa  xor     r8d, r8d; dwAddressStates
0x1800100fd  mov     edx, ebp; dwLineStates
0x1800100ff  call    cs:__imp_lineSetStatusMessages
0x180010105  test    eax, eax
0x180010107  jz      short loc_18001011C
0x180010109  lea     rdx, [rbx+18h]
0x18001010d  mov     r8d, eax
0x180010110  lea     rcx, aDevicelistenSF; "DeviceListen: %s. Failed to post listen"...
0x180010117  call    RasTapiTrace
0x18001011c  mov     rax, [rbx+0D8h]
0x180010123  cmp     [rax+10h], ebp
0x180010126  jz      short loc_18001012B
0x180010128  mov     [rax+10h], ebp
0x18001012b  mov     r8d, [rbx+38h]
0x18001012f  lea     rdx, [rbx+18h]
0x180010133  mov     r9d, ebp
0x180010136  lea     rcx, aDevicelistenCh; "DeviceListen: Changing State for %s fro"...
0x18001013d  call    RasTapiTrace
0x180010142  mov     rcx, [rbx+0D8h]
0x180010149  mov     [rbx+38h], ebp
0x18001014c  mov     eax, [rcx+30h]
0x18001014f  test    al, 1
0x180010151  jz      short loc_180010158
0x180010153  or      eax, ebp
0x180010155  mov     [rcx+30h], eax
0x180010158  mov     r8d, [rbx+3Ch]
0x18001015c  lea     rdx, [rbx+18h]
0x180010160  mov     r9d, ebp
0x180010163  lea     rcx, aDevicelistenCh_0; "DeviceListen: Changing Listen State for"...
0x18001016a  call    RasTapiTrace
0x18001016f  mov     dword ptr [rbx+3Ch], 0
0x180010176  mov     dword ptr [rbx+444h], 0
0x180010180  mov     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x18001018a  mov     rcx, cs:RasTapiMutex; hMutex
0x180010191  call    cs:__imp_ReleaseMutex
0x180010197  test    eax, eax
0x180010199  jnz     short loc_1800101A1
0x18001019b  call    cs:__imp_GetLastError
0x1800101a1  mov     ebx, 258h
0x1800101a6  lea     rcx, asc_18002C0B8; " "
0x1800101ad  call    RasTapiTrace
0x1800101b2  mov     eax, ebx
0x1800101b4  mov     rbx, [rsp+58h+arg_0]
0x1800101b9  mov     rbp, [rsp+58h+arg_8]
0x1800101be  add     rsp, 50h
0x1800101c2  pop     rdi
0x1800101c3  retn
```
