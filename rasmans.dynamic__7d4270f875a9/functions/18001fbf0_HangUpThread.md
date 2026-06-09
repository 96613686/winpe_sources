# HangUpThread

- ea: `0x18001fbf0`
- end: `0x18001feaa`
- name: `HangUpThread`
- size: `698`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18001fbf0`
- `0x180057bc8`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fe99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fe99`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001fdb0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001fdb0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001fc60`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001fc60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fc93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fc93`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fcf5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd35`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fcf5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd35`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18001fd96`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18001fd96`

## pseudocode

```c
void __fastcall HangUpThread(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)
{
  __int64 v4; // rdi
  HRASCONN *v5; // rsi
  unsigned int v6; // ecx
  __int64 v7; // rbx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 i; // rbx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  WCHAR lpWideCharStr[264]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR WideCharStr[264]; // [rsp+240h] [rbp-258h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 178, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  v4 = 0;
  v5 = (HRASCONN *)GlobalAlloc(0x40u, 8LL * (unsigned int)MaxPorts);
  EnterCriticalSection(&g_csSubmitRequest);
  SetThreadpoolWait(g_hangUpThreadPool, g_hangUpEvent, 0);
  v6 = MaxPorts;
  v7 = 0;
  if ( !MaxPorts )
  {
LABEL_13:
    LeaveCriticalSection(&g_csSubmitRequest);
    for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
      RasHangUpW(v5[i]);
    goto LABEL_15;
  }
  while ( 1 )
  {
    v8 = *((_QWORD *)Pcb + v7);
    if ( !v8 || !*(_DWORD *)(v8 + 1376) )
      goto LABEL_12;
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)(v8 + 1200), -1, WideCharStr, 261) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v12 = 179;
          goto LABEL_36;
        }
      }
      goto LABEL_37;
    }
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)(*((_QWORD *)Pcb + v7) + 1208LL), -1, lpWideCharStr, 257) )
      break;
    LastError = RasGetEntryHrasconnW(WideCharStr, lpWideCharStr, &v5[v4]);
    if ( LastError )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = 181;
LABEL_36:
        WPP_SF_d(v11[1].Flink, v12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
    v6 = MaxPorts;
    v4 = (unsigned int)(v4 + 1);
LABEL_12:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= v6 )
      goto LABEL_13;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v12 = 180;
      goto LABEL_36;
    }
  }
LABEL_37:
  LeaveCriticalSection(&g_csSubmitRequest);
LABEL_15:
  if ( v5 )
    GlobalFree(v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 182, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
}

```

## disassembly

```asm
0x18001fbf0  push    rbx
0x18001fbf2  push    rbp
0x18001fbf3  push    rsi
0x18001fbf4  push    rdi
0x18001fbf5  push    r12
0x18001fbf7  push    r14
0x18001fbf9  push    r15
0x18001fbfb  sub     rsp, 460h
0x18001fc02  mov     rax, cs:__security_cookie
0x18001fc09  xor     rax, rsp
0x18001fc0c  mov     [rsp+498h+var_48], rax
0x18001fc14  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc1b  lea     r15, WPP_GLOBAL_Control
0x18001fc22  lea     r12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001fc29  mov     r14d, 2000h
0x18001fc2f  cmp     rcx, r15
0x18001fc32  jz      short loc_18001FC51
0x18001fc34  test    [rcx+1Ch], r14d
0x18001fc38  jz      short loc_18001FC51
0x18001fc3a  cmp     byte ptr [rcx+19h], 6
0x18001fc3e  jb      short loc_18001FC51
0x18001fc40  mov     rcx, [rcx+10h]
0x18001fc44  mov     edx, 0B2h
0x18001fc49  mov     r8, r12
0x18001fc4c  call    WPP_SF_
0x18001fc51  mov     edx, cs:MaxPorts
0x18001fc57  xor     edi, edi
0x18001fc59  shl     rdx, 3; dwBytes
0x18001fc5d  lea     ecx, [rdi+40h]; uFlags
0x18001fc60  call    cs:__imp_GlobalAlloc
0x18001fc67  nop     dword ptr [rax+rax+00h]
0x18001fc6c  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001fc73  mov     rsi, rax
0x18001fc76  call    cs:__imp_EnterCriticalSection
0x18001fc7d  nop     dword ptr [rax+rax+00h]
0x18001fc82  mov     rdx, cs:g_hangUpEvent; h
0x18001fc89  xor     r8d, r8d; pftTimeout
0x18001fc8c  mov     rcx, cs:g_hangUpThreadPool; pwa
0x18001fc93  call    cs:__imp_SetThreadpoolWait
0x18001fc9a  nop     dword ptr [rax+rax+00h]
0x18001fc9f  mov     ecx, cs:MaxPorts
0x18001fca5  xor     ebx, ebx
0x18001fca7  test    ecx, ecx
0x18001fca9  jz      loc_18001FD79
0x18001fcaf  mov     rax, cs:Pcb
0x18001fcb6  mov     r8, [rax+rbx*8]
0x18001fcba  test    r8, r8
0x18001fcbd  jz      loc_18001FD6F
0x18001fcc3  cmp     dword ptr [r8+560h], 0
0x18001fccb  jz      loc_18001FD6F
0x18001fcd1  mov     r8, [r8+4B0h]; lpMultiByteStr
0x18001fcd8  lea     rax, [rsp+498h+WideCharStr]
0x18001fce0  mov     [rsp+498h+cchWideChar], 105h; cchWideChar
0x18001fce8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001fcec  xor     edx, edx; dwFlags
0x18001fcee  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001fcf3  xor     ecx, ecx; CodePage
0x18001fcf5  call    cs:__imp_MultiByteToWideChar
0x18001fcfc  nop     dword ptr [rax+rax+00h]
0x18001fd01  test    eax, eax
0x18001fd03  jz      loc_18001FE56
0x18001fd09  mov     rax, cs:Pcb
0x18001fd10  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001fd14  mov     [rsp+498h+cchWideChar], 101h; cchWideChar
0x18001fd1c  xor     edx, edx; dwFlags
0x18001fd1e  xor     ecx, ecx; CodePage
0x18001fd20  mov     r8, [rax+rbx*8]
0x18001fd24  lea     rax, [rsp+498h+var_468]
0x18001fd29  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001fd2e  mov     r8, [r8+4B8h]; lpMultiByteStr
0x18001fd35  call    cs:__imp_MultiByteToWideChar
0x18001fd3c  nop     dword ptr [rax+rax+00h]
0x18001fd41  test    eax, eax
0x18001fd43  jz      loc_18001FE27
0x18001fd49  lea     r8, [rsi+rdi*8]
0x18001fd4d  lea     rdx, [rsp+498h+var_468]
0x18001fd52  lea     rcx, [rsp+498h+WideCharStr]
0x18001fd5a  call    RasGetEntryHrasconnW
0x18001fd5f  test    eax, eax
0x18001fd61  jnz     loc_18001FE08
0x18001fd67  mov     ecx, cs:MaxPorts
0x18001fd6d  inc     edi
0x18001fd6f  inc     ebx
0x18001fd71  cmp     ebx, ecx
0x18001fd73  jb      loc_18001FCAF
0x18001fd79  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001fd80  call    cs:__imp_LeaveCriticalSection
0x18001fd87  nop     dword ptr [rax+rax+00h]
0x18001fd8c  xor     ebx, ebx
0x18001fd8e  test    edi, edi
0x18001fd90  jz      short loc_18001FDA8
0x18001fd92  mov     rcx, [rsi+rbx*8]; HRASCONN
0x18001fd96  call    cs:__imp_RasHangUpW
0x18001fd9d  nop     dword ptr [rax+rax+00h]
0x18001fda2  inc     ebx
0x18001fda4  cmp     ebx, edi
0x18001fda6  jb      short loc_18001FD92
0x18001fda8  test    rsi, rsi
0x18001fdab  jz      short loc_18001FDBC
0x18001fdad  mov     rcx, rsi; hMem
0x18001fdb0  call    cs:__imp_GlobalFree
0x18001fdb7  nop     dword ptr [rax+rax+00h]
0x18001fdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdc3  cmp     rcx, r15
0x18001fdc6  jz      short loc_18001FDE5
0x18001fdc8  test    [rcx+1Ch], r14d
0x18001fdcc  jz      short loc_18001FDE5
0x18001fdce  cmp     byte ptr [rcx+19h], 6
0x18001fdd2  jb      short loc_18001FDE5
0x18001fdd4  mov     rcx, [rcx+10h]
0x18001fdd8  mov     edx, 0B6h
0x18001fddd  mov     r8, r12
0x18001fde0  call    WPP_SF_
0x18001fde5  mov     rcx, [rsp+498h+var_48]
0x18001fded  xor     rcx, rsp; StackCookie
0x18001fdf0  call    __security_check_cookie
0x18001fdf5  add     rsp, 460h
0x18001fdfc  pop     r15
0x18001fdfe  pop     r14
0x18001fe00  pop     r12
0x18001fe02  pop     rdi
0x18001fe03  pop     rsi
0x18001fe04  pop     rbp
0x18001fe05  pop     rbx
0x18001fe06  retn
0x18001fe08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe0f  cmp     rcx, r15
0x18001fe12  jz      short loc_18001FE92
0x18001fe14  test    [rcx+1Ch], r14d
0x18001fe18  jz      short loc_18001FE92
0x18001fe1a  cmp     byte ptr [rcx+19h], 2
0x18001fe1e  jb      short loc_18001FE92
0x18001fe20  mov     edx, 0B5h
0x18001fe25  jmp     short loc_18001FE83
0x18001fe27  call    cs:__imp_GetLastError
0x18001fe2e  nop     dword ptr [rax+rax+00h]
0x18001fe33  test    eax, eax
0x18001fe35  jz      short loc_18001FE92
0x18001fe37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe3e  cmp     rcx, r15
0x18001fe41  jz      short loc_18001FE92
0x18001fe43  test    [rcx+1Ch], r14d
0x18001fe47  jz      short loc_18001FE92
0x18001fe49  cmp     byte ptr [rcx+19h], 2
0x18001fe4d  jb      short loc_18001FE92
0x18001fe4f  mov     edx, 0B4h
0x18001fe54  jmp     short loc_18001FE83
0x18001fe56  call    cs:__imp_GetLastError
0x18001fe5d  nop     dword ptr [rax+rax+00h]
0x18001fe62  test    eax, eax
0x18001fe64  jz      short loc_18001FE92
0x18001fe66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe6d  cmp     rcx, r15
0x18001fe70  jz      short loc_18001FE92
0x18001fe72  test    [rcx+1Ch], r14d
0x18001fe76  jz      short loc_18001FE92
0x18001fe78  cmp     byte ptr [rcx+19h], 2
0x18001fe7c  jb      short loc_18001FE92
0x18001fe7e  mov     edx, 0B3h
0x18001fe83  mov     rcx, [rcx+10h]
0x18001fe87  mov     r9d, eax
0x18001fe8a  mov     r8, r12
0x18001fe8d  call    WPP_SF_d
0x18001fe92  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001fe99  call    cs:__imp_LeaveCriticalSection
0x18001fea0  nop     dword ptr [rax+rax+00h]
0x18001fea5  jmp     loc_18001FDA8
```
