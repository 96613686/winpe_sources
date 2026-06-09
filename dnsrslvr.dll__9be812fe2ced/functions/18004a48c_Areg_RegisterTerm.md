# Areg_RegisterTerm

- ea: `0x18004a48c`
- end: `0x18004a5fa`
- name: `Areg_RegisterTerm`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800505e8`

## callees

- `0x18004a48c`
- `0x18004aa68`
- `0x180086700`

## import_xrefs

- `DNSAPI!Security_ContextListTimeout` at `0x18004a5d0`
- `DNSAPI!Security_ContextListTimeout` at `0x18004a5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a58f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a58f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a523`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a523`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004a540`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004a540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a5e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a5e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a4f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a4f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a579`

## pseudocode

```c
__int64 Areg_RegisterTerm()
{
  char v0; // al
  unsigned int v1; // ebx
  __int64 v3; // rdx

  v0 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_(1035, 24, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    v0 = BYTE1(xmmword_1800AB5A0);
  }
  v1 = 0;
  if ( !g_fAregInitialized )
    return 1359;
  if ( (v0 & 8) != 0 )
    WPP_SF_(1035, 25, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  EnterCriticalSection(&g_AregThreadCs);
  if ( !g_hAregThread )
    goto LABEL_22;
  ++g_AregThreadWaitCount;
  g_fAregThreadStop = 1;
  if ( g_hAregWakeEvent )
    SetEvent(g_hAregWakeEvent);
  LeaveCriticalSection(&g_AregThreadCs);
  if ( WaitForSingleObject(g_hAregThread, 0xFFFFFFFF) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_16;
    v3 = 27;
  }
  else
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_16;
    v3 = 26;
  }
  WPP_SF_(1035, v3, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
LABEL_16:
  EnterCriticalSection(&g_AregThreadCs);
  if ( !--g_AregThreadWaitCount )
  {
    CloseHandle(g_hAregThread);
    g_hAregThread = 0;
  }
  if ( !g_fAregThreadRunning )
  {
LABEL_22:
    if ( !g_fVelocityRpcUpdate )
      Security_ContextListTimeout(1);
    areg_CleanupGlobals();
    goto LABEL_25;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 28, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  v1 = 1359;
LABEL_25:
  LeaveCriticalSection(&g_AregThreadCs);
  return v1;
}

```

## disassembly

```asm
0x18004a48c  mov     [rsp+arg_8], rbx
0x18004a491  mov     [rsp+arg_10], rbp
0x18004a496  push    rsi
0x18004a497  sub     rsp, 20h
0x18004a49b  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004a4a1  lea     rbp, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18004a4a8  mov     esi, 40Bh
0x18004a4ad  test    al, 8
0x18004a4af  jz      short loc_18004A4C6
0x18004a4b1  mov     edx, 18h
0x18004a4b6  mov     ecx, esi
0x18004a4b8  mov     r8, rbp
0x18004a4bb  call    WPP_SF_
0x18004a4c0  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004a4c6  xor     ebx, ebx
0x18004a4c8  cmp     cs:g_fAregInitialized, ebx
0x18004a4ce  jnz     short loc_18004A4DA
0x18004a4d0  mov     eax, 54Fh
0x18004a4d5  jmp     loc_18004A5EA
0x18004a4da  test    al, 8
0x18004a4dc  jz      short loc_18004A4ED
0x18004a4de  mov     edx, 19h
0x18004a4e3  mov     ecx, esi
0x18004a4e5  mov     r8, rbp
0x18004a4e8  call    WPP_SF_
0x18004a4ed  lea     rcx, g_AregThreadCs; lpCriticalSection
0x18004a4f4  call    cs:__imp_EnterCriticalSection
0x18004a4fa  cmp     cs:g_hAregThread, rbx
0x18004a501  jz      loc_18004A5C3
0x18004a507  inc     cs:g_AregThreadWaitCount
0x18004a50d  mov     rcx, cs:g_hAregWakeEvent; hEvent
0x18004a514  mov     cs:g_fAregThreadStop, 1
0x18004a51e  test    rcx, rcx
0x18004a521  jz      short loc_18004A529
0x18004a523  call    cs:__imp_SetEvent
0x18004a529  lea     rcx, g_AregThreadCs; lpCriticalSection
0x18004a530  call    cs:__imp_LeaveCriticalSection
0x18004a536  mov     rcx, cs:g_hAregThread; hHandle
0x18004a53d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004a540  call    cs:__imp_WaitForSingleObject
0x18004a546  test    eax, eax
0x18004a548  jz      short loc_18004A55A
0x18004a54a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004a551  jz      short loc_18004A572
0x18004a553  mov     edx, 1Bh
0x18004a558  jmp     short loc_18004A568
0x18004a55a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004a561  jz      short loc_18004A572
0x18004a563  mov     edx, 1Ah
0x18004a568  mov     r8, rbp
0x18004a56b  mov     ecx, esi
0x18004a56d  call    WPP_SF_
0x18004a572  lea     rcx, g_AregThreadCs; lpCriticalSection
0x18004a579  call    cs:__imp_EnterCriticalSection
0x18004a57f  sub     cs:g_AregThreadWaitCount, 1
0x18004a586  jnz     short loc_18004A59C
0x18004a588  mov     rcx, cs:g_hAregThread; hObject
0x18004a58f  call    cs:__imp_CloseHandle
0x18004a595  mov     cs:g_hAregThread, rbx
0x18004a59c  cmp     cs:g_fAregThreadRunning, ebx
0x18004a5a2  jz      short loc_18004A5C3
0x18004a5a4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004a5ab  jz      short loc_18004A5BC
0x18004a5ad  mov     edx, 1Ch
0x18004a5b2  mov     ecx, esi
0x18004a5b4  mov     r8, rbp
0x18004a5b7  call    WPP_SF_
0x18004a5bc  mov     ebx, 54Fh
0x18004a5c1  jmp     short loc_18004A5DB
0x18004a5c3  cmp     cs:g_fVelocityRpcUpdate, ebx
0x18004a5c9  jnz     short loc_18004A5D6
0x18004a5cb  mov     ecx, 1
0x18004a5d0  call    cs:__imp_Security_ContextListTimeout
0x18004a5d6  call    areg_CleanupGlobals
0x18004a5db  lea     rcx, g_AregThreadCs; lpCriticalSection
0x18004a5e2  call    cs:__imp_LeaveCriticalSection
0x18004a5e8  mov     eax, ebx
0x18004a5ea  mov     rbx, [rsp+28h+arg_8]
0x18004a5ef  mov     rbp, [rsp+28h+arg_10]
0x18004a5f4  add     rsp, 20h
0x18004a5f8  pop     rsi
0x18004a5f9  retn
```
