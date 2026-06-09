# VolumeTimerHandler

- ea: `0x180004a50`
- end: `0x18000502f`
- name: `VolumeTimerHandler`
- size: `1503`
- prototype: `BOOL __fastcall(unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002e40`

## callees

- `0x180004650`
- `0x180004794`
- `0x180004920`
- `0x180004a50`
- `0x180005308`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180004a93`
- `KERNEL32!WaitForSingleObject` at `0x180004a93`
- `KERNEL32!ReleaseMutex` at `0x180005028`
- `USER32!SetTimer` at `0x180004b0a`
- `USER32!SetTimer` at `0x180004b49`
- `USER32!SetTimer` at `0x180004b88`
- `USER32!SetTimer` at `0x180004bc7`
- `USER32!SetTimer` at `0x180004c06`
- `USER32!SetTimer` at `0x180004c45`
- `USER32!SetTimer` at `0x180004ca2`
- `USER32!SetTimer` at `0x180004ce3`
- `USER32!SetTimer` at `0x180004d24`
- `USER32!SetTimer` at `0x180004d65`
- `USER32!SetTimer` at `0x180004da6`
- `USER32!SetTimer` at `0x180004e2f`
- `USER32!SetTimer` at `0x180004e6e`
- `USER32!SetTimer` at `0x180004ead`
- `USER32!SetTimer` at `0x180004eec`
- `USER32!SetTimer` at `0x180004f28`
- `USER32!SetTimer` at `0x180004f64`
- `USER32!SetTimer` at `0x180004fa0`
- `USER32!SetTimer` at `0x180004fd5`
- `USER32!SetTimer` at `0x18000500f`
- `USER32!SetTimer` at `0x180004b0a`
- `USER32!SetTimer` at `0x180004b49`
- `USER32!SetTimer` at `0x180004b88`
- `USER32!SetTimer` at `0x180004bc7`
- `USER32!SetTimer` at `0x180004c06`
- `USER32!SetTimer` at `0x180004c45`
- `USER32!SetTimer` at `0x180004ca2`
- `USER32!SetTimer` at `0x180004ce3`
- `USER32!SetTimer` at `0x180004d24`
- `USER32!SetTimer` at `0x180004d65`
- `USER32!SetTimer` at `0x180004da6`
- `USER32!SetTimer` at `0x180004e2f`
- `USER32!SetTimer` at `0x180004e6e`
- `USER32!SetTimer` at `0x180004ead`
- `USER32!SetTimer` at `0x180004eec`
- `USER32!SetTimer` at `0x180004f28`
- `USER32!SetTimer` at `0x180004f64`
- `USER32!SetTimer` at `0x180004fa0`
- `USER32!SetTimer` at `0x180004fd5`
- `USER32!SetTimer` at `0x18000500f`

## pseudocode

```c
BOOL __fastcall VolumeTimerHandler(unsigned int a1, __int64 a2, __int64 a3)
{
  __int16 v4; // dx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, a3, a1);
  }
  WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
  if ( a1 > 0xD )
  {
    v12 = a1 - 14;
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
              v17 = v16 - 1;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  v19 = v18 - 1;
                  if ( v19 )
                  {
                    if ( v19 == 1 && qword_18000D898 )
                    {
                      SendAppCommand(0x32u);
                      qword_18000D898 = SetTimer(hWndHidServ, 0x16u, REPEAT_INTERVAL, 0);
                    }
                  }
                  else if ( qword_18000D890 )
                  {
                    SendAppCommand(0x31u);
                    qword_18000D890 = SetTimer(hWndHidServ, 0x15u, REPEAT_INTERVAL, 0);
                  }
                }
                else if ( qword_18000D888 )
                {
                  SendAppCommand(0x34u);
                  qword_18000D888 = SetTimer(hWndHidServ, 0x14u, REPEAT_INTERVAL, 0);
                }
              }
              else if ( qword_18000D880 )
              {
                SendAppCommand(0x33u);
                qword_18000D880 = SetTimer(hWndHidServ, 0x13u, REPEAT_INTERVAL, 0);
              }
            }
            else if ( qword_18000D878 )
            {
              SendChar(0x3Du, v4);
              qword_18000D878 = SetTimer(hWndHidServ, 0x12u, REPEAT_INTERVAL, 0);
            }
          }
          else if ( qword_18000D870 )
          {
            SendChar(0x40u, v4);
            qword_18000D870 = SetTimer(hWndHidServ, 0x11u, REPEAT_INTERVAL, 0);
          }
        }
        else if ( qword_18000D868 )
        {
          SendChar(0x29u, v4);
          qword_18000D868 = SetTimer(hWndHidServ, 0x10u, REPEAT_INTERVAL, 0);
        }
      }
      else if ( qword_18000D860 )
      {
        SendChar(0x28u, v4);
        qword_18000D860 = SetTimer(hWndHidServ, 0xFu, REPEAT_INTERVAL, 0);
      }
    }
    else if ( qword_18000D858 )
    {
      SendVK(0xAEu, 1);
      qword_18000D858 = SetTimer(hWndHidServ, 0xEu, REPEAT_INTERVAL, 0);
    }
  }
  else if ( a1 == 13 )
  {
    if ( qword_18000D850 )
    {
      SendVK(0xAFu, 1);
      qword_18000D850 = SetTimer(hWndHidServ, 0xDu, REPEAT_INTERVAL, 0);
    }
  }
  else if ( a1 > 8 )
  {
    v9 = a1 - 9;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 && qword_18000D848 )
          {
            SendVK(0xB0u, 1);
            qword_18000D848 = SetTimer(hWndHidServ, 0xCu, REPEAT_INTERVAL, 0);
          }
        }
        else if ( qword_18000D840 )
        {
          SendVK(0xB1u, 1);
          qword_18000D840 = SetTimer(hWndHidServ, 0xBu, REPEAT_INTERVAL, 0);
        }
      }
      else if ( qword_18000D838 )
      {
        SendVK(0xA7u, 1);
        qword_18000D838 = SetTimer(hWndHidServ, 0xAu, REPEAT_INTERVAL, 0);
      }
    }
    else if ( qword_18000D830 )
    {
      SendVK(0xA6u, 1);
      qword_18000D830 = SetTimer(hWndHidServ, 9u, REPEAT_INTERVAL, 0);
    }
  }
  else if ( a1 == 8 )
  {
    if ( qword_18000D828 )
    {
      SendAppCommand(0x16u);
      qword_18000D828 = SetTimer(hWndHidServ, 8u, REPEAT_INTERVAL, 0);
    }
  }
  else
  {
    v5 = a1 - 3;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 == 1 && qword_18000D820 )
            {
              SendAppCommand(0x17u);
              qword_18000D820 = SetTimer(hWndHidServ, 7u, REPEAT_INTERVAL, 0);
            }
          }
          else if ( qword_18000D818 )
          {
            SendAppCommand(0x13u);
            qword_18000D818 = SetTimer(hWndHidServ, 6u, REPEAT_INTERVAL, 0);
          }
        }
        else if ( qword_18000D810 )
        {
          SendAppCommand(0x15u);
          qword_18000D810 = SetTimer(hWndHidServ, 5u, REPEAT_INTERVAL, 0);
        }
      }
      else if ( qword_18000D808 )
      {
        SendAppCommand(9u);
        qword_18000D808 = SetTimer(hWndHidServ, 4u, REPEAT_INTERVAL, 0);
      }
    }
    else if ( OOC_State[0] )
    {
      SendAppCommand(0xAu);
      OOC_State[0] = SetTimer(hWndHidServ, 3u, REPEAT_INTERVAL, 0);
    }
  }
  return ReleaseMutex(hMutexOOC);
}

```

## disassembly

```asm
0x180004a50  push    rbx
0x180004a52  sub     rsp, 20h
0x180004a56  mov     rbx, rcx
0x180004a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a60  lea     rax, WPP_GLOBAL_Control
0x180004a67  cmp     rcx, rax
0x180004a6a  jz      short loc_180004A89
0x180004a6c  test    byte ptr [rcx+1Ch], 10h
0x180004a70  jz      short loc_180004A89
0x180004a72  cmp     byte ptr [rcx+19h], 4
0x180004a76  jb      short loc_180004A89
0x180004a78  mov     rcx, [rcx+10h]
0x180004a7c  mov     r9d, ebx
0x180004a7f  mov     edx, 28h ; '('
0x180004a84  call    WPP_SF_d
0x180004a89  mov     rcx, cs:hMutexOOC; hHandle
0x180004a90  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004a93  call    cs:__imp_WaitForSingleObject
0x180004a99  cmp     ebx, 0Dh
0x180004a9c  ja      loc_180004DB8
0x180004aa2  jz      loc_180004D77
0x180004aa8  cmp     ebx, 8
0x180004aab  ja      loc_180004C57
0x180004ab1  jz      loc_180004C18
0x180004ab7  sub     ebx, 3
0x180004aba  jz      loc_180004BD9
0x180004ac0  sub     ebx, 1
0x180004ac3  jz      loc_180004B9A
0x180004ac9  sub     ebx, 1
0x180004acc  jz      loc_180004B5B
0x180004ad2  sub     ebx, 1
0x180004ad5  jz      short loc_180004B1C
0x180004ad7  cmp     ebx, 1
0x180004ada  jnz     loc_18000501C
0x180004ae0  cmp     cs:qword_18000D820, 0
0x180004ae8  jz      loc_18000501C
0x180004aee  lea     ecx, [rbx+16h]
0x180004af1  call    SendAppCommand
0x180004af6  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004afd  lea     edx, [rbx+6]; nIDEvent
0x180004b00  mov     rcx, cs:hWndHidServ; hWnd
0x180004b07  xor     r9d, r9d; lpTimerFunc
0x180004b0a  call    cs:__imp_SetTimer
0x180004b10  mov     cs:qword_18000D820, rax
0x180004b17  jmp     loc_18000501C
0x180004b1c  cmp     cs:qword_18000D818, 0
0x180004b24  jz      loc_18000501C
0x180004b2a  mov     ecx, 13h
0x180004b2f  call    SendAppCommand
0x180004b34  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004b3b  xor     r9d, r9d; lpTimerFunc
0x180004b3e  mov     rcx, cs:hWndHidServ; hWnd
0x180004b45  lea     edx, [r9+6]; nIDEvent
0x180004b49  call    cs:__imp_SetTimer
0x180004b4f  mov     cs:qword_18000D818, rax
0x180004b56  jmp     loc_18000501C
0x180004b5b  cmp     cs:qword_18000D810, 0
0x180004b63  jz      loc_18000501C
0x180004b69  mov     ecx, 15h
0x180004b6e  call    SendAppCommand
0x180004b73  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004b7a  xor     r9d, r9d; lpTimerFunc
0x180004b7d  mov     rcx, cs:hWndHidServ; hWnd
0x180004b84  lea     edx, [r9+5]; nIDEvent
0x180004b88  call    cs:__imp_SetTimer
0x180004b8e  mov     cs:qword_18000D810, rax
0x180004b95  jmp     loc_18000501C
0x180004b9a  cmp     cs:qword_18000D808, 0
0x180004ba2  jz      loc_18000501C
0x180004ba8  mov     ecx, 9
0x180004bad  call    SendAppCommand
0x180004bb2  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004bb9  xor     r9d, r9d; lpTimerFunc
0x180004bbc  mov     rcx, cs:hWndHidServ; hWnd
0x180004bc3  lea     edx, [r9+4]; nIDEvent
0x180004bc7  call    cs:__imp_SetTimer
0x180004bcd  mov     cs:qword_18000D808, rax
0x180004bd4  jmp     loc_18000501C
0x180004bd9  cmp     cs:OOC_State, 0
0x180004be1  jz      loc_18000501C
0x180004be7  mov     ecx, 0Ah
0x180004bec  call    SendAppCommand
0x180004bf1  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004bf8  xor     r9d, r9d; lpTimerFunc
0x180004bfb  mov     rcx, cs:hWndHidServ; hWnd
0x180004c02  lea     edx, [r9+3]; nIDEvent
0x180004c06  call    cs:__imp_SetTimer
0x180004c0c  mov     cs:OOC_State, rax
0x180004c13  jmp     loc_18000501C
0x180004c18  cmp     cs:qword_18000D828, 0
0x180004c20  jz      loc_18000501C
0x180004c26  mov     ecx, 16h
0x180004c2b  call    SendAppCommand
0x180004c30  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004c37  xor     r9d, r9d; lpTimerFunc
0x180004c3a  mov     rcx, cs:hWndHidServ; hWnd
0x180004c41  lea     edx, [r9+8]; nIDEvent
0x180004c45  call    cs:__imp_SetTimer
0x180004c4b  mov     cs:qword_18000D828, rax
0x180004c52  jmp     loc_18000501C
0x180004c57  sub     ebx, 9
0x180004c5a  jz      loc_180004D36
0x180004c60  sub     ebx, 1
0x180004c63  jz      loc_180004CF5
0x180004c69  sub     ebx, 1
0x180004c6c  jz      short loc_180004CB4
0x180004c6e  cmp     ebx, 1
0x180004c71  jnz     loc_18000501C
0x180004c77  cmp     cs:qword_18000D848, 0
0x180004c7f  jz      loc_18000501C
0x180004c85  mov     edx, ebx
0x180004c87  mov     cl, 0B0h
0x180004c89  call    SendVK
0x180004c8e  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004c95  lea     edx, [rbx+0Bh]; nIDEvent
0x180004c98  mov     rcx, cs:hWndHidServ; hWnd
0x180004c9f  xor     r9d, r9d; lpTimerFunc
0x180004ca2  call    cs:__imp_SetTimer
0x180004ca8  mov     cs:qword_18000D848, rax
0x180004caf  jmp     loc_18000501C
0x180004cb4  cmp     cs:qword_18000D840, 0
0x180004cbc  jz      loc_18000501C
0x180004cc2  mov     edx, 1
0x180004cc7  mov     cl, 0B1h
0x180004cc9  call    SendVK
0x180004cce  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004cd5  xor     r9d, r9d; lpTimerFunc
0x180004cd8  mov     rcx, cs:hWndHidServ; hWnd
0x180004cdf  lea     edx, [r9+0Bh]; nIDEvent
0x180004ce3  call    cs:__imp_SetTimer
0x180004ce9  mov     cs:qword_18000D840, rax
0x180004cf0  jmp     loc_18000501C
0x180004cf5  cmp     cs:qword_18000D838, 0
0x180004cfd  jz      loc_18000501C
0x180004d03  mov     edx, 1
0x180004d08  mov     cl, 0A7h
0x180004d0a  call    SendVK
0x180004d0f  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004d16  xor     r9d, r9d; lpTimerFunc
0x180004d19  mov     rcx, cs:hWndHidServ; hWnd
0x180004d20  lea     edx, [r9+0Ah]; nIDEvent
0x180004d24  call    cs:__imp_SetTimer
0x180004d2a  mov     cs:qword_18000D838, rax
0x180004d31  jmp     loc_18000501C
0x180004d36  cmp     cs:qword_18000D830, 0
0x180004d3e  jz      loc_18000501C
0x180004d44  mov     edx, 1
0x180004d49  mov     cl, 0A6h
0x180004d4b  call    SendVK
0x180004d50  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004d57  xor     r9d, r9d; lpTimerFunc
0x180004d5a  mov     rcx, cs:hWndHidServ; hWnd
0x180004d61  lea     edx, [r9+9]; nIDEvent
0x180004d65  call    cs:__imp_SetTimer
0x180004d6b  mov     cs:qword_18000D830, rax
0x180004d72  jmp     loc_18000501C
0x180004d77  cmp     cs:qword_18000D850, 0
0x180004d7f  jz      loc_18000501C
0x180004d85  mov     edx, 1
0x180004d8a  mov     cl, 0AFh
0x180004d8c  call    SendVK
0x180004d91  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004d98  xor     r9d, r9d; lpTimerFunc
0x180004d9b  mov     rcx, cs:hWndHidServ; hWnd
0x180004da2  lea     edx, [r9+0Dh]; nIDEvent
0x180004da6  call    cs:__imp_SetTimer
0x180004dac  mov     cs:qword_18000D850, rax
0x180004db3  jmp     loc_18000501C
0x180004db8  sub     ebx, 0Eh
0x180004dbb  jz      loc_180004FE4
0x180004dc1  sub     ebx, 1
0x180004dc4  jz      loc_180004FAF
0x180004dca  sub     ebx, 1
0x180004dcd  jz      loc_180004F76
0x180004dd3  sub     ebx, 1
0x180004dd6  jz      loc_180004F3A
0x180004ddc  sub     ebx, 1
0x180004ddf  jz      loc_180004EFE
0x180004de5  sub     ebx, 1
0x180004de8  jz      loc_180004EBF
0x180004dee  sub     ebx, 1
0x180004df1  jz      loc_180004E80
0x180004df7  sub     ebx, 1
0x180004dfa  jz      short loc_180004E41
0x180004dfc  cmp     ebx, 1
0x180004dff  jnz     loc_18000501C
0x180004e05  cmp     cs:qword_18000D898, 0
0x180004e0d  jz      loc_18000501C
0x180004e13  lea     ecx, [rbx+31h]
0x180004e16  call    SendAppCommand
0x180004e1b  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004e22  lea     edx, [rbx+15h]; nIDEvent
0x180004e25  mov     rcx, cs:hWndHidServ; hWnd
0x180004e2c  xor     r9d, r9d; lpTimerFunc
0x180004e2f  call    cs:__imp_SetTimer
0x180004e35  mov     cs:qword_18000D898, rax
0x180004e3c  jmp     loc_18000501C
0x180004e41  cmp     cs:qword_18000D890, 0
0x180004e49  jz      loc_18000501C
0x180004e4f  mov     ecx, 31h ; '1'
0x180004e54  call    SendAppCommand
0x180004e59  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004e60  xor     r9d, r9d; lpTimerFunc
0x180004e63  mov     rcx, cs:hWndHidServ; hWnd
0x180004e6a  lea     edx, [r9+15h]; nIDEvent
0x180004e6e  call    cs:__imp_SetTimer
0x180004e74  mov     cs:qword_18000D890, rax
0x180004e7b  jmp     loc_18000501C
0x180004e80  cmp     cs:qword_18000D888, 0
0x180004e88  jz      loc_18000501C
0x180004e8e  mov     ecx, 34h ; '4'
0x180004e93  call    SendAppCommand
0x180004e98  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004e9f  xor     r9d, r9d; lpTimerFunc
0x180004ea2  mov     rcx, cs:hWndHidServ; hWnd
0x180004ea9  lea     edx, [r9+14h]; nIDEvent
0x180004ead  call    cs:__imp_SetTimer
0x180004eb3  mov     cs:qword_18000D888, rax
0x180004eba  jmp     loc_18000501C
0x180004ebf  cmp     cs:qword_18000D880, 0
0x180004ec7  jz      loc_18000501C
0x180004ecd  mov     ecx, 33h ; '3'
0x180004ed2  call    SendAppCommand
0x180004ed7  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004ede  xor     r9d, r9d; lpTimerFunc
0x180004ee1  mov     rcx, cs:hWndHidServ; hWnd
0x180004ee8  lea     edx, [r9+13h]; nIDEvent
0x180004eec  call    cs:__imp_SetTimer
0x180004ef2  mov     cs:qword_18000D880, rax
0x180004ef9  jmp     loc_18000501C
0x180004efe  cmp     cs:qword_18000D878, 0
0x180004f06  jz      loc_18000501C
0x180004f0c  mov     cl, 3Dh ; '='
0x180004f0e  call    SendChar
0x180004f13  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004f1a  xor     r9d, r9d; lpTimerFunc
0x180004f1d  mov     rcx, cs:hWndHidServ; hWnd
0x180004f24  lea     edx, [r9+12h]; nIDEvent
0x180004f28  call    cs:__imp_SetTimer
0x180004f2e  mov     cs:qword_18000D878, rax
0x180004f35  jmp     loc_18000501C
0x180004f3a  cmp     cs:qword_18000D870, 0
0x180004f42  jz      loc_18000501C
0x180004f48  mov     cl, 40h ; '@'
0x180004f4a  call    SendChar
0x180004f4f  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004f56  xor     r9d, r9d; lpTimerFunc
0x180004f59  mov     rcx, cs:hWndHidServ; hWnd
0x180004f60  lea     edx, [r9+11h]; nIDEvent
0x180004f64  call    cs:__imp_SetTimer
0x180004f6a  mov     cs:qword_18000D870, rax
0x180004f71  jmp     loc_18000501C
0x180004f76  cmp     cs:qword_18000D868, 0
0x180004f7e  jz      loc_18000501C
0x180004f84  mov     cl, 29h ; ')'
0x180004f86  call    SendChar
0x180004f8b  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004f92  xor     r9d, r9d; lpTimerFunc
0x180004f95  mov     rcx, cs:hWndHidServ; hWnd
0x180004f9c  lea     edx, [r9+10h]; nIDEvent
0x180004fa0  call    cs:__imp_SetTimer
0x180004fa6  mov     cs:qword_18000D868, rax
0x180004fad  jmp     short loc_18000501C
0x180004faf  cmp     cs:qword_18000D860, 0
0x180004fb7  jz      short loc_18000501C
0x180004fb9  mov     cl, 28h ; '('
0x180004fbb  call    SendChar
0x180004fc0  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180004fc7  xor     r9d, r9d; lpTimerFunc
0x180004fca  mov     rcx, cs:hWndHidServ; hWnd
0x180004fd1  lea     edx, [r9+0Fh]; nIDEvent
0x180004fd5  call    cs:__imp_SetTimer
0x180004fdb  mov     cs:qword_18000D860, rax
0x180004fe2  jmp     short loc_18000501C
0x180004fe4  cmp     cs:qword_18000D858, 0
0x180004fec  jz      short loc_18000501C
0x180004fee  mov     edx, 1
0x180004ff3  mov     cl, 0AEh
0x180004ff5  call    SendVK
0x180004ffa  mov     r8d, cs:REPEAT_INTERVAL; uElapse
0x180005001  xor     r9d, r9d; lpTimerFunc
0x180005004  mov     rcx, cs:hWndHidServ; hWnd
0x18000500b  lea     edx, [r9+0Eh]; nIDEvent
0x18000500f  call    cs:__imp_SetTimer
0x180005015  mov     cs:qword_18000D858, rax
0x18000501c  mov     rcx, cs:hMutexOOC
0x180005023  add     rsp, 20h
0x180005027  pop     rbx
0x180005028  jmp     cs:__imp_ReleaseMutex
```
