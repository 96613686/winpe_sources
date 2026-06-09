# Mcast_Startup

- ea: `0x18003621c`
- end: `0x1800363d7`
- name: `Mcast_Startup`
- size: `443`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800495c0`

## callees

- `0x18003621c`
- `0x18004c884`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180036277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003630e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003637d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003630e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003637d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800362a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800362ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036323`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800362a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800362ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036323`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003636b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003636b`

## pseudocode

```c
__int64 Mcast_Startup()
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rdx
  DWORD v4; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 93, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids);
  if ( g_hMcastThread )
  {
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_(1055, 94, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids);
    return 183;
  }
  g_EnableLLMNRCopy = DnsGlobals[99];
  g_MulticastListenLevelCopy = DnsGlobals[96];
  g_McastStop = CreateEventW(0, 1, 0, 0);
  if ( g_McastStop )
  {
    g_McastUpdate = CreateEventW(0, 1, 0, 0);
    if ( !g_McastUpdate )
    {
      v1 = 14;
      if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
        goto LABEL_21;
      LastError = GetLastError();
      v3 = 96;
      goto LABEL_10;
    }
    g_McastVerify = CreateEventW(0, 1, 0, 0);
    if ( g_McastVerify )
    {
      v1 = 0;
      g_hMcastThread = CreateThread(0, 0, Mcast_Thread, 0, 0, &g_McastThreadId);
      if ( g_hMcastThread )
        goto LABEL_22;
      v4 = GetLastError();
      v1 = v4;
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_d(1055, 98, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v4);
      if ( !v1 )
        goto LABEL_22;
      goto LABEL_21;
    }
    v1 = 14;
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    {
      LastError = GetLastError();
      v3 = 97;
      goto LABEL_10;
    }
  }
  else
  {
    v1 = 14;
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    {
      LastError = GetLastError();
      v3 = 95;
LABEL_10:
      WPP_SF_d(1055, v3, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, LastError);
    }
  }
LABEL_21:
  Mcast_Shutdown();
LABEL_22:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 99, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18003621c  mov     [rsp+arg_0], rbx
0x180036221  push    rsi
0x180036222  sub     rsp, 30h
0x180036226  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003622d  lea     rsi, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids
0x180036234  jz      short loc_180036248
0x180036236  mov     edx, 5Dh ; ']'
0x18003623b  mov     ecx, 40Bh
0x180036240  mov     r8, rsi
0x180036243  call    WPP_SF_
0x180036248  cmp     cs:g_hMcastThread, 0
0x180036250  jz      short loc_180036277
0x180036252  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180036259  jge     short loc_18003626D
0x18003625b  mov     edx, 5Eh ; '^'
0x180036260  mov     ecx, 41Fh
0x180036265  mov     r8, rsi
0x180036268  call    WPP_SF_
0x18003626d  mov     eax, 0B7h
0x180036272  jmp     loc_1800363CC
0x180036277  mov     rcx, cs:__imp_DnsGlobals
0x18003627e  xor     r9d, r9d; lpName
0x180036281  xor     r8d, r8d; bInitialState
0x180036284  mov     eax, [rcx+18Ch]
0x18003628a  lea     ebx, [r9+1]
0x18003628e  mov     cs:g_EnableLLMNRCopy, eax
0x180036294  mov     edx, ebx; bManualReset
0x180036296  mov     eax, [rcx+180h]
0x18003629c  xor     ecx, ecx; lpEventAttributes
0x18003629e  mov     cs:g_MulticastListenLevelCopy, eax
0x1800362a4  call    cs:__imp_CreateEventW
0x1800362aa  mov     cs:g_McastStop, rax
0x1800362b1  test    rax, rax
0x1800362b4  jnz     short loc_1800362E3
0x1800362b6  lea     ebx, [rax+0Eh]
0x1800362b9  cmp     byte ptr cs:xmmword_1800AB5A0+3, al
0x1800362bf  jge     loc_1800363A7
0x1800362c5  call    cs:__imp_GetLastError
0x1800362cb  lea     edx, [rbx+51h]
0x1800362ce  mov     r9d, eax
0x1800362d1  mov     ecx, 41Fh
0x1800362d6  mov     r8, rsi
0x1800362d9  call    WPP_SF_d
0x1800362de  jmp     loc_1800363A7
0x1800362e3  xor     r9d, r9d; lpName
0x1800362e6  xor     r8d, r8d; bInitialState
0x1800362e9  mov     edx, ebx; bManualReset
0x1800362eb  xor     ecx, ecx; lpEventAttributes
0x1800362ed  call    cs:__imp_CreateEventW
0x1800362f3  mov     cs:g_McastUpdate, rax
0x1800362fa  test    rax, rax
0x1800362fd  jnz     short loc_180036319
0x1800362ff  lea     ebx, [rax+0Eh]
0x180036302  cmp     byte ptr cs:xmmword_1800AB5A0+3, al
0x180036308  jge     loc_1800363A7
0x18003630e  call    cs:__imp_GetLastError
0x180036314  lea     edx, [rbx+52h]
0x180036317  jmp     short loc_1800362CE
0x180036319  xor     r9d, r9d; lpName
0x18003631c  xor     r8d, r8d; bInitialState
0x18003631f  mov     edx, ebx; bManualReset
0x180036321  xor     ecx, ecx; lpEventAttributes
0x180036323  call    cs:__imp_CreateEventW
0x180036329  mov     cs:g_McastVerify, rax
0x180036330  test    rax, rax
0x180036333  jnz     short loc_18003634B
0x180036335  lea     ebx, [rax+0Eh]
0x180036338  cmp     byte ptr cs:xmmword_1800AB5A0+3, al
0x18003633e  jge     short loc_1800363A7
0x180036340  call    cs:__imp_GetLastError
0x180036346  lea     edx, [rbx+53h]
0x180036349  jmp     short loc_1800362CE
0x18003634b  lea     rax, g_McastThreadId
0x180036352  xor     ebx, ebx
0x180036354  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180036359  lea     r8, Mcast_Thread; lpStartAddress
0x180036360  xor     r9d, r9d; lpParameter
0x180036363  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180036367  xor     edx, edx; dwStackSize
0x180036369  xor     ecx, ecx; lpThreadAttributes
0x18003636b  call    cs:__imp_CreateThread
0x180036371  mov     cs:g_hMcastThread, rax
0x180036378  test    rax, rax
0x18003637b  jnz     short loc_1800363AC
0x18003637d  call    cs:__imp_GetLastError
0x180036383  mov     ebx, eax
0x180036385  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18003638c  jge     short loc_1800363A3
0x18003638e  mov     edx, 62h ; 'b'
0x180036393  mov     ecx, 41Fh
0x180036398  mov     r9d, eax
0x18003639b  mov     r8, rsi
0x18003639e  call    WPP_SF_d
0x1800363a3  test    ebx, ebx
0x1800363a5  jz      short loc_1800363AC
0x1800363a7  call    Mcast_Shutdown
0x1800363ac  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800363b3  jz      short loc_1800363CA
0x1800363b5  mov     edx, 63h ; 'c'
0x1800363ba  mov     ecx, 40Bh
0x1800363bf  mov     r9d, ebx
0x1800363c2  mov     r8, rsi
0x1800363c5  call    WPP_SF_d
0x1800363ca  mov     eax, ebx
0x1800363cc  mov     rbx, [rsp+38h+arg_0]
0x1800363d1  add     rsp, 30h
0x1800363d5  pop     rsi
0x1800363d6  retn
```
