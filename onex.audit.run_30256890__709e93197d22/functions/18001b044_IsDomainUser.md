# IsDomainUser

- ea: `0x18001b044`
- end: `0x18001b358`
- name: `IsDomainUser`
- size: `788`
- prototype: `__int64 __fastcall(DWORD SessionId)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001bbd8`
- `0x18001d208`
- `0x180029414`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x18001b044`
- `0x180020ce0`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b231`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b2a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b2cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b2a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b2cf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001b199`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001b227`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001b199`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001b227`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001b2f1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001b2f1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18001b107`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18001b107`
- `MobileNetworking!AllocateMemory` at `0x18001b161`
- `MobileNetworking!AllocateMemory` at `0x18001b1f1`
- `MobileNetworking!AllocateMemory` at `0x18001b161`
- `MobileNetworking!AllocateMemory` at `0x18001b1f1`
- `MobileNetworking!FreeMemory` at `0x18001b1d0`
- `MobileNetworking!FreeMemory` at `0x18001b316`
- `MobileNetworking!FreeMemory` at `0x18001b1d0`
- `MobileNetworking!FreeMemory` at `0x18001b316`

## pseudocode

```c
__int64 __fastcall IsDomainUser(DWORD SessionId, int *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD LastError; // eax
  int v9; // edi
  LPWSTR lpBuffer; // [rsp+30h] [rbp-10h] BYREF
  LPWSTR ppBuffer; // [rsp+38h] [rbp-8h] BYREF
  DWORD nSize; // [rsp+80h] [rbp+40h] BYREF
  DWORD pBytesReturned; // [rsp+88h] [rbp+48h] BYREF

  ppBuffer = 0;
  pBytesReturned = 0;
  lpBuffer = 0;
  nSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
  if ( (unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    if ( !WTSQuerySessionInformationW(0, SessionId, WTSDomainName, &ppBuffer, &pBytesReturned) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_39;
        v6 = 59;
        goto LABEL_14;
      }
    }
    nSize = 16;
    LastError = AllocateMemory(32, &lpBuffer, "IsDomainUser", 1015);
    v4 = LastError;
    if ( LastError )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_39;
      v6 = 60;
      goto LABEL_14;
    }
    v9 = 1;
    if ( !GetComputerNameW(lpBuffer, &nSize) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError == 234 )
      {
        FreeMemory(&lpBuffer, "IsDomainUser", 1023);
        ++nSize;
        LastError = AllocateMemory(2 * nSize, &lpBuffer, "IsDomainUser", 1028);
        v4 = LastError;
        if ( LastError )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_39;
          v6 = 61;
          goto LABEL_14;
        }
        if ( !GetComputerNameW(lpBuffer, &nSize) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_39;
            v6 = 62;
            goto LABEL_14;
          }
        }
      }
      else if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_39;
        v6 = 63;
LABEL_14:
        v7 = LastError;
        goto LABEL_8;
      }
    }
    if ( CompareStringW(0x7Fu, 1u, ppBuffer, -1, lpBuffer, -1) == 2
      || CompareStringW(0x7Fu, 1u, ppBuffer, -1, L".", -1) == 2 )
    {
      v9 = 0;
    }
    *a2 = v9;
    goto LABEL_38;
  }
  v4 = 50;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v6 = 58;
    v7 = 50;
LABEL_8:
    WPP_SF_d(v5[7], v6, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v7);
LABEL_38:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( ppBuffer )
  {
    WTSFreeMemory(ppBuffer);
    v5 = WPP_GLOBAL_Control;
  }
  if ( lpBuffer )
  {
    FreeMemory(&lpBuffer, "IsDomainUser", 1055);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_D(v5[7], 64, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18001b044  mov     [rsp-28h+arg_0], rbx
0x18001b049  push    rbp
0x18001b04a  push    rsi
0x18001b04b  push    rdi
0x18001b04c  push    r12
0x18001b04e  push    r15
0x18001b050  mov     rbp, rsp
0x18001b053  sub     rsp, 40h
0x18001b057  mov     rsi, rdx
0x18001b05a  mov     [rbp+ppBuffer], 0
0x18001b062  mov     ebx, ecx
0x18001b064  mov     [rbp+arg_18], 0
0x18001b06b  mov     [rbp+lpBuffer], 0
0x18001b073  mov     [rbp+nSize], 0
0x18001b07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b081  lea     r15, WPP_GLOBAL_Control
0x18001b088  lea     r12, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18001b08f  cmp     rcx, r15
0x18001b092  jz      short loc_18001B0AE
0x18001b094  test    dword ptr [rcx+44h], 800h
0x18001b09b  jz      short loc_18001B0AE
0x18001b09d  mov     rcx, [rcx+38h]
0x18001b0a1  mov     edx, 39h ; '9'
0x18001b0a6  mov     r8, r12
0x18001b0a9  call    WPP_SF_
0x18001b0ae  call    IsWTSQueryUserTokenPresent
0x18001b0b3  test    al, al
0x18001b0b5  jnz     short loc_18001B0F0
0x18001b0b7  mov     ebx, 32h ; '2'
0x18001b0bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0c3  cmp     rcx, r15
0x18001b0c6  jz      loc_18001B2E5
0x18001b0cc  lea     edi, [rbx-31h]
0x18001b0cf  test    [rcx+44h], dil
0x18001b0d3  jz      loc_18001B2E5
0x18001b0d9  lea     edx, [rbx+8]
0x18001b0dc  mov     r9d, ebx
0x18001b0df  mov     rcx, [rcx+38h]
0x18001b0e3  mov     r8, r12
0x18001b0e6  call    WPP_SF_d
0x18001b0eb  jmp     loc_18001B2DE
0x18001b0f0  lea     rax, [rbp+arg_18]
0x18001b0f4  mov     r8d, 7; WTSInfoClass
0x18001b0fa  lea     r9, [rbp+ppBuffer]; ppBuffer
0x18001b0fe  mov     [rsp+40h+pBytesReturned], rax; pBytesReturned
0x18001b103  mov     edx, ebx; SessionId
0x18001b105  xor     ecx, ecx; hServer
0x18001b107  call    cs:__imp_WTSQuerySessionInformationW
0x18001b10d  test    eax, eax
0x18001b10f  jnz     short loc_18001B144
0x18001b111  call    cs:__imp_GetLastError
0x18001b117  mov     ebx, eax
0x18001b119  test    eax, eax
0x18001b11b  jz      short loc_18001B144
0x18001b11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b124  cmp     rcx, r15
0x18001b127  jz      loc_18001B2E5
0x18001b12d  mov     edi, 1
0x18001b132  test    [rcx+44h], dil
0x18001b136  jz      loc_18001B2E5
0x18001b13c  lea     edx, [rdi+3Ah]
0x18001b13f  mov     r9d, eax
0x18001b142  jmp     short loc_18001B0DF
0x18001b144  mov     r9d, 3F7h
0x18001b14a  mov     [rbp+nSize], 10h
0x18001b151  lea     r8, aIsdomainuser; "IsDomainUser"
0x18001b158  mov     ecx, 20h ; ' '
0x18001b15d  lea     rdx, [rbp+lpBuffer]
0x18001b161  call    cs:__imp_AllocateMemory
0x18001b167  mov     ebx, eax
0x18001b169  test    eax, eax
0x18001b16b  jz      short loc_18001B191
0x18001b16d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b174  cmp     rcx, r15
0x18001b177  jz      loc_18001B2E5
0x18001b17d  mov     edi, 1
0x18001b182  test    [rcx+44h], dil
0x18001b186  jz      loc_18001B2E5
0x18001b18c  lea     edx, [rdi+3Bh]
0x18001b18f  jmp     short loc_18001B13F
0x18001b191  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x18001b195  lea     rdx, [rbp+nSize]; nSize
0x18001b199  call    cs:__imp_GetComputerNameW
0x18001b19f  mov     edi, 1
0x18001b1a4  test    eax, eax
0x18001b1a6  jnz     loc_18001B281
0x18001b1ac  call    cs:__imp_GetLastError
0x18001b1b2  mov     ebx, eax
0x18001b1b4  cmp     eax, 0EAh
0x18001b1b9  jnz     loc_18001B261
0x18001b1bf  mov     r8d, 3FFh
0x18001b1c5  lea     rdx, aIsdomainuser; "IsDomainUser"
0x18001b1cc  lea     rcx, [rbp+lpBuffer]
0x18001b1d0  call    cs:__imp_FreeMemory
0x18001b1d6  mov     ecx, [rbp+nSize]
0x18001b1d9  lea     r8, aIsdomainuser; "IsDomainUser"
0x18001b1e0  add     ecx, edi
0x18001b1e2  lea     rdx, [rbp+lpBuffer]
0x18001b1e6  mov     [rbp+nSize], ecx
0x18001b1e9  mov     r9d, 404h
0x18001b1ef  add     ecx, ecx
0x18001b1f1  call    cs:__imp_AllocateMemory
0x18001b1f7  mov     ebx, eax
0x18001b1f9  test    eax, eax
0x18001b1fb  jz      short loc_18001B21F
0x18001b1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b204  cmp     rcx, r15
0x18001b207  jz      loc_18001B2E5
0x18001b20d  test    [rcx+44h], dil
0x18001b211  jz      loc_18001B2E5
0x18001b217  lea     edx, [rdi+3Ch]
0x18001b21a  jmp     loc_18001B13F
0x18001b21f  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x18001b223  lea     rdx, [rbp+nSize]; nSize
0x18001b227  call    cs:__imp_GetComputerNameW
0x18001b22d  test    eax, eax
0x18001b22f  jnz     short loc_18001B281
0x18001b231  call    cs:__imp_GetLastError
0x18001b237  mov     ebx, eax
0x18001b239  test    eax, eax
0x18001b23b  jz      short loc_18001B281
0x18001b23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b244  cmp     rcx, r15
0x18001b247  jz      loc_18001B2E5
0x18001b24d  test    [rcx+44h], dil
0x18001b251  jz      loc_18001B2E5
0x18001b257  mov     edx, 3Eh ; '>'
0x18001b25c  jmp     loc_18001B13F
0x18001b261  test    eax, eax
0x18001b263  jz      short loc_18001B281
0x18001b265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b26c  cmp     rcx, r15
0x18001b26f  jz      short loc_18001B2E5
0x18001b271  test    [rcx+44h], dil
0x18001b275  jz      short loc_18001B2E5
0x18001b277  mov     edx, 3Fh ; '?'
0x18001b27c  jmp     loc_18001B13F
0x18001b281  mov     rax, [rbp+lpBuffer]
0x18001b285  or      r9d, 0FFFFFFFFh; cchCount1
0x18001b289  mov     r8, [rbp+ppBuffer]; lpString1
0x18001b28d  mov     edx, edi; dwCmpFlags
0x18001b28f  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001b297  mov     ecx, 7Fh; Locale
0x18001b29c  mov     [rsp+40h+pBytesReturned], rax; lpString2
0x18001b2a1  call    cs:__imp_CompareStringW
0x18001b2a7  cmp     eax, 2
0x18001b2aa  jz      short loc_18001B2DA
0x18001b2ac  mov     r8, [rbp+ppBuffer]; lpString1
0x18001b2b0  lea     rax, String2; "."
0x18001b2b7  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001b2bf  or      r9d, 0FFFFFFFFh; cchCount1
0x18001b2c3  mov     edx, edi; dwCmpFlags
0x18001b2c5  mov     [rsp+40h+pBytesReturned], rax; lpString2
0x18001b2ca  mov     ecx, 7Fh; Locale
0x18001b2cf  call    cs:__imp_CompareStringW
0x18001b2d5  cmp     eax, 2
0x18001b2d8  jnz     short loc_18001B2DC
0x18001b2da  xor     edi, edi
0x18001b2dc  mov     [rsi], edi
0x18001b2de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2e5  mov     rax, [rbp+ppBuffer]
0x18001b2e9  test    rax, rax
0x18001b2ec  jz      short loc_18001B2FE
0x18001b2ee  mov     rcx, rax; pMemory
0x18001b2f1  call    cs:__imp_WTSFreeMemory
0x18001b2f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2fe  cmp     [rbp+lpBuffer], 0
0x18001b303  jz      short loc_18001B323
0x18001b305  mov     r8d, 41Fh
0x18001b30b  lea     rdx, aIsdomainuser; "IsDomainUser"
0x18001b312  lea     rcx, [rbp+lpBuffer]
0x18001b316  call    cs:__imp_FreeMemory
0x18001b31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b323  cmp     rcx, r15
0x18001b326  jz      short loc_18001B345
0x18001b328  test    dword ptr [rcx+44h], 800h
0x18001b32f  jz      short loc_18001B345
0x18001b331  mov     rcx, [rcx+38h]
0x18001b335  mov     edx, 40h ; '@'
0x18001b33a  mov     r9d, ebx
0x18001b33d  mov     r8, r12
0x18001b340  call    WPP_SF_D
0x18001b345  mov     eax, ebx
0x18001b347  mov     rbx, [rsp+40h+arg_0]
0x18001b34c  add     rsp, 40h
0x18001b350  pop     r15
0x18001b352  pop     r12
0x18001b354  pop     rdi
0x18001b355  pop     rsi
0x18001b356  pop     rbp
0x18001b357  retn
```
