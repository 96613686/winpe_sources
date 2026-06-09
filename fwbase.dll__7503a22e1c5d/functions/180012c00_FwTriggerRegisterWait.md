# FwTriggerRegisterWait

- ea: `0x180012c00`
- end: `0x180012d94`
- name: `FwTriggerRegisterWait`
- size: `404`
- prototype: `__int64 __fastcall(PTP_WAIT_CALLBACK pfnwa, PVOID pv)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004870`
- `0x18000ccd4`
- `0x180012c00`
- `0x180017d1c`
- `0x18002b1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012cc0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180012cf9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180012cf9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012d56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012d56`

## pseudocode

```c
__int64 __fastcall FwTriggerRegisterWait(PTP_WAIT_CALLBACK pfnwa, PVOID pv, __int64 *a3)
{
  _BYTE *v6; // rcx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v7 = 0;
    v8 = 87;
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[28] & 1) == 0 )
      goto LABEL_23;
    v9 = 11;
    goto LABEL_8;
  }
  v7 = FwAlloc(24, pv);
  if ( !v7 )
  {
    v8 = 14;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v9 = 12;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v6 + 2), v9, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, v8);
LABEL_23:
    FwTriggerUnregisterWait(v7);
LABEL_25:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(v7 + 8) = EventW;
  if ( EventW )
  {
    ThreadpoolWait = CreateThreadpoolWait(pfnwa, pv, 0);
    *(_QWORD *)v7 = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v8 = 0;
      SetThreadpoolWait(ThreadpoolWait, *(HANDLE *)(v7 + 8), 0);
      *a3 = v7;
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 14;
      goto LABEL_21;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 13;
LABEL_21:
      WPP_SF_d(v12[2], v13, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, LastError);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( v8 )
    goto LABEL_23;
LABEL_26:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(v12[2], 15, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180012c00  push    rbx
0x180012c02  push    rbp
0x180012c03  push    rsi
0x180012c04  push    rdi
0x180012c05  push    r14
0x180012c07  push    r15
0x180012c09  sub     rsp, 28h
0x180012c0d  mov     rsi, r8
0x180012c10  mov     rbx, rdx
0x180012c13  mov     rbp, rcx
0x180012c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c1d  lea     r14, WPP_GLOBAL_Control
0x180012c24  lea     r15, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids
0x180012c2b  cmp     rcx, r14
0x180012c2e  jz      short loc_180012C4E
0x180012c30  test    byte ptr [rcx+1Ch], 8
0x180012c34  jz      short loc_180012C4E
0x180012c36  mov     rcx, [rcx+10h]
0x180012c3a  mov     edx, 0Ah
0x180012c3f  mov     r8, r15
0x180012c42  call    WPP_SF_
0x180012c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c4e  test    rsi, rsi
0x180012c51  jnz     short loc_180012C82
0x180012c53  xor     edi, edi
0x180012c55  lea     ebx, [rsi+57h]
0x180012c58  cmp     rcx, r14
0x180012c5b  jz      loc_180012D40
0x180012c61  test    byte ptr [rcx+1Ch], 1
0x180012c65  jz      loc_180012D40
0x180012c6b  lea     edx, [rsi+0Bh]
0x180012c6e  mov     rcx, [rcx+10h]
0x180012c72  mov     r9d, ebx
0x180012c75  mov     r8, r15
0x180012c78  call    WPP_SF_d
0x180012c7d  jmp     loc_180012D40
0x180012c82  mov     ecx, 18h
0x180012c87  call    FwAlloc
0x180012c8c  mov     rdi, rax
0x180012c8f  test    rax, rax
0x180012c92  jnz     short loc_180012CB6
0x180012c94  lea     ebx, [rax+0Eh]
0x180012c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c9e  cmp     rcx, r14
0x180012ca1  jz      loc_180012D40
0x180012ca7  test    byte ptr [rcx+1Ch], 1
0x180012cab  jz      loc_180012D40
0x180012cb1  lea     edx, [rax+0Ch]
0x180012cb4  jmp     short loc_180012C6E
0x180012cb6  xor     r9d, r9d; lpName
0x180012cb9  xor     r8d, r8d; bInitialState
0x180012cbc  xor     edx, edx; bManualReset
0x180012cbe  xor     ecx, ecx; lpEventAttributes
0x180012cc0  call    cs:__imp_CreateEventW
0x180012cc6  mov     [rdi+8], rax
0x180012cca  test    rax, rax
0x180012ccd  jnz     short loc_180012CF0
0x180012ccf  call    cs:__imp_GetLastError
0x180012cd5  mov     ebx, eax
0x180012cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cde  cmp     rcx, r14
0x180012ce1  jz      short loc_180012D3C
0x180012ce3  test    byte ptr [rcx+1Ch], 1
0x180012ce7  jz      short loc_180012D3C
0x180012ce9  mov     edx, 0Dh
0x180012cee  jmp     short loc_180012D26
0x180012cf0  xor     r8d, r8d; pcbe
0x180012cf3  mov     rdx, rbx; pv
0x180012cf6  mov     rcx, rbp; pfnwa
0x180012cf9  call    cs:__imp_CreateThreadpoolWait
0x180012cff  mov     [rdi], rax
0x180012d02  test    rax, rax
0x180012d05  jnz     short loc_180012D4A
0x180012d07  call    cs:__imp_GetLastError
0x180012d0d  mov     ebx, eax
0x180012d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d16  cmp     rcx, r14
0x180012d19  jz      short loc_180012D3C
0x180012d1b  test    byte ptr [rcx+1Ch], 1
0x180012d1f  jz      short loc_180012D3C
0x180012d21  mov     edx, 0Eh
0x180012d26  mov     rcx, [rcx+10h]
0x180012d2a  mov     r9d, eax
0x180012d2d  mov     r8, r15
0x180012d30  call    WPP_SF_d
0x180012d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d3c  test    ebx, ebx
0x180012d3e  jz      short loc_180012D66
0x180012d40  mov     rcx, rdi
0x180012d43  call    FwTriggerUnregisterWait
0x180012d48  jmp     short loc_180012D5F
0x180012d4a  mov     rdx, [rdi+8]; h
0x180012d4e  xor     ebx, ebx
0x180012d50  xor     r8d, r8d; pftTimeout
0x180012d53  mov     rcx, rax; pwa
0x180012d56  call    cs:__imp_SetThreadpoolWait
0x180012d5c  mov     [rsi], rdi
0x180012d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d66  cmp     rcx, r14
0x180012d69  jz      short loc_180012D85
0x180012d6b  test    byte ptr [rcx+1Ch], 8
0x180012d6f  jz      short loc_180012D85
0x180012d71  mov     rcx, [rcx+10h]
0x180012d75  mov     edx, 0Fh
0x180012d7a  mov     r9d, ebx
0x180012d7d  mov     r8, r15
0x180012d80  call    WPP_SF_d
0x180012d85  mov     eax, ebx
0x180012d87  add     rsp, 28h
0x180012d8b  pop     r15
0x180012d8d  pop     r14
0x180012d8f  pop     rdi
0x180012d90  pop     rsi
0x180012d91  pop     rbp
0x180012d92  pop     rbx
0x180012d93  retn
```
