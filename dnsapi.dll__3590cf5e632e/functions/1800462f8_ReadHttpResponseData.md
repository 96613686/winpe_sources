# ReadHttpResponseData

- ea: `0x1800462f8`
- end: `0x18004648b`
- name: `ReadHttpResponseData`
- size: `403`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180045bdc`
- `0x180045e6c`

## callees

- `0x1800462f8`
- `0x180046494`
- `0x1800464e4`
- `0x180083954`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046319`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004640e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004640e`
- `WINHTTP!WinHttpReadData` at `0x180046388`
- `WINHTTP!WinHttpReadData` at `0x180046388`

## pseudocode

```c
__int64 __fastcall ReadHttpResponseData(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  void **v3; // rsi
  _DWORD *v4; // rdi
  void *v5; // r14
  unsigned int v6; // ebx
  DWORD LastError; // eax

  if ( *(_DWORD *)(a1 + 44) > *(_DWORD *)(a1 + 40) )
  {
    v6 = 14;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 18, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, 14);
  }
  else
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    if ( *(_DWORD *)(a1 + 52) )
    {
      v6 = 995;
      LeaveCriticalSection(v2);
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 56) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v3 = (void **)(a1 + 144);
      v4 = (_DWORD *)(a1 + 136);
      if ( !*(_QWORD *)(a1 + 144) || !*v4 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      AddRefWinhttpSession(a1 + 136);
      v5 = *v3;
      LeaveCriticalSection(v2);
      if ( WinHttpReadData(
             v5,
             (LPVOID)(*(_QWORD *)(a1 + 72) + *(unsigned int *)(a1 + 44)),
             *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 44),
             0) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError != 997 && LastError || (MicrosoftTelemetryAssertTriggeredNoArgs(), v6) )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_d(1035, 19, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, v6);
        }
      }
      if ( v5 )
      {
        if ( !*v3 || !*v4 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v5 != *v3 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        DeRefDnsWinhttpHandle(v4);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800462f8  push    rbx
0x1800462fa  push    rbp
0x1800462fb  push    rsi
0x1800462fc  push    rdi
0x1800462fd  push    r14
0x1800462ff  sub     rsp, 20h
0x180046303  mov     eax, [rcx+28h]
0x180046306  mov     rbx, rcx
0x180046309  cmp     [rcx+2Ch], eax
0x18004630c  ja      loc_1800463D5
0x180046312  lea     rbp, [rcx+58h]
0x180046316  mov     rcx, rbp; lpCriticalSection
0x180046319  call    cs:__imp_EnterCriticalSection
0x180046320  nop     dword ptr [rax+rax+00h]
0x180046325  cmp     dword ptr [rbx+34h], 0
0x180046329  jnz     loc_180046406
0x18004632f  cmp     dword ptr [rbx+38h], 0
0x180046333  jz      loc_18004641C
0x180046339  lea     rsi, [rbx+90h]
0x180046340  cmp     qword ptr [rsi], 0
0x180046344  lea     rdi, [rbx+88h]
0x18004634b  jz      loc_1800463FC
0x180046351  cmp     dword ptr [rdi], 0
0x180046354  jz      loc_1800463FC
0x18004635a  mov     rcx, rdi
0x18004635d  call    AddRefWinhttpSession
0x180046362  mov     r14, [rsi]
0x180046365  mov     rcx, rbp; lpCriticalSection
0x180046368  call    cs:__imp_LeaveCriticalSection
0x18004636f  nop     dword ptr [rax+rax+00h]
0x180046374  mov     edx, [rbx+2Ch]
0x180046377  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18004637a  mov     r8d, [rbx+28h]
0x18004637e  mov     rcx, r14; hRequest
0x180046381  sub     r8d, edx; dwNumberOfBytesToRead
0x180046384  add     rdx, [rbx+48h]; lpBuffer
0x180046388  call    cs:__imp_WinHttpReadData
0x18004638f  nop     dword ptr [rax+rax+00h]
0x180046394  test    eax, eax
0x180046396  jz      loc_180046426
0x18004639c  xor     ebx, ebx
0x18004639e  test    r14, r14
0x1800463a1  jz      short loc_1800463C7
0x1800463a3  cmp     qword ptr [rsi], 0
0x1800463a7  jz      loc_180046477
0x1800463ad  cmp     dword ptr [rdi], 0
0x1800463b0  jz      loc_180046477
0x1800463b6  cmp     r14, [rsi]
0x1800463b9  jnz     loc_180046481
0x1800463bf  mov     rcx, rdi
0x1800463c2  call    DeRefDnsWinhttpHandle
0x1800463c7  mov     eax, ebx
0x1800463c9  add     rsp, 20h
0x1800463cd  pop     r14
0x1800463cf  pop     rdi
0x1800463d0  pop     rsi
0x1800463d1  pop     rbp
0x1800463d2  pop     rbx
0x1800463d3  retn
0x1800463d5  mov     ebx, 0Eh
0x1800463da  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800463e1  jz      short loc_1800463C7
0x1800463e3  lea     edx, [rbx+4]
0x1800463e6  mov     ecx, 40Bh
0x1800463eb  mov     r9d, ebx
0x1800463ee  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x1800463f5  call    WPP_SF_d
0x1800463fa  jmp     short loc_1800463C7
0x1800463fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046401  jmp     loc_18004635A
0x180046406  mov     rcx, rbp; lpCriticalSection
0x180046409  mov     ebx, 3E3h
0x18004640e  call    cs:__imp_LeaveCriticalSection
0x180046415  nop     dword ptr [rax+rax+00h]
0x18004641a  jmp     short loc_1800463C7
0x18004641c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046421  jmp     loc_180046339
0x180046426  call    cs:__imp_GetLastError
0x18004642d  nop     dword ptr [rax+rax+00h]
0x180046432  mov     ebx, eax
0x180046434  cmp     eax, 3E5h
0x180046439  jz      short loc_18004643F
0x18004643b  test    eax, eax
0x18004643d  jnz     short loc_18004644C
0x18004643f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046444  test    ebx, ebx
0x180046446  jz      loc_18004639E
0x18004644c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180046453  jz      loc_18004639E
0x180046459  mov     edx, 13h
0x18004645e  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180046465  mov     ecx, 40Bh
0x18004646a  mov     r9d, ebx
0x18004646d  call    WPP_SF_d
0x180046472  jmp     loc_18004639E
0x180046477  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004647c  jmp     loc_1800463B6
0x180046481  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046486  jmp     loc_1800463BF
```
