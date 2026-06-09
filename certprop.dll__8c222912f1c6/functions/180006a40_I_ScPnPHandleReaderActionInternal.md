# I_ScPnPHandleReaderActionInternal

- ea: `0x180006a40`
- end: `0x180006f31`
- name: `I_ScPnPHandleReaderActionInternal`
- size: `1265`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a190`

## callees

- `0x180004600`
- `0x180004fa0`
- `0x180006a40`
- `0x18000e4ac`
- `0x18000e7b8`
- `0x180018b58`
- `0x180018bb4`
- `0x18001913c`
- `0x180019dbc`
- `0x1800243e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ae4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ea9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006eba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ae4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ea9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006eba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006ac6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006ac6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ed5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cc2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180006cb4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180006cb4`

## pseudocode

```c
__int64 __fastcall I_ScPnPHandleReaderActionInternal(__int64 a1)
{
  int v1; // ebp
  LPVOID v2; // r14
  __int64 v3; // rsi
  unsigned __int16 *v4; // r10
  unsigned __int16 *i; // r9
  unsigned __int16 *v6; // rax
  int v7; // ecx
  int v8; // edx
  __int64 v9; // rcx
  LPVOID v10; // rbx
  int v11; // eax
  __int64 v12; // rcx
  DWORD LastError; // eax
  __int64 v14; // rcx
  char v15; // bl
  const wchar_t *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  char *v19; // rcx
  __int64 v20; // rcx
  __int64 result; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+8h] BYREF
  LPVOID lpInBuffer; // [rsp+78h] [rbp+10h] BYREF

  BytesReturned = 0;
  lpInBuffer = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 496));
  if ( WaitForSingleObject(*((HANDLE *)g_pScPnPState + 61), 0) == 258 )
  {
    v1 = I_ScPnPCreateThreadpoolWait(
           (__int64)I_ScPnPHandleReaderAction,
           0,
           *((void **)g_pScPnPState + 11),
           (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)g_pScPnPState + 400),
           (struct _TP_WAIT **)g_pScPnPState + 49);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 496));
    if ( v1 )
      goto LABEL_62;
    v2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 48));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
    v3 = *((_QWORD *)g_pScPnPState + 14);
    if ( !v3 )
    {
LABEL_61:
      I_ScPnPFreeDeviceList(*((LPVOID *)g_pScPnPState + 74));
      v19 = (char *)g_pScPnPState;
      *((_QWORD *)g_pScPnPState + 74) = v2;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 544));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 48));
      goto LABEL_62;
    }
    while ( 1 )
    {
      v4 = 0;
      lpInBuffer = 0;
      for ( i = (unsigned __int16 *)*((_QWORD *)g_pScPnPState + 74); ; i = (unsigned __int16 *)*((_QWORD *)i + 30) )
      {
        if ( !i )
          goto LABEL_20;
        v6 = i;
        do
        {
          v7 = *(unsigned __int16 *)((char *)v6 + *(_QWORD *)v3 - (_QWORD)i);
          v8 = *v6 - v7;
          if ( v8 )
            break;
          ++v6;
        }
        while ( v7 );
        if ( !v8 )
          break;
        v4 = i;
      }
      lpInBuffer = i;
      v9 = *((_QWORD *)i + 30);
      if ( v4 )
        *((_QWORD *)v4 + 30) = v9;
      else
        *((_QWORD *)g_pScPnPState + 74) = v9;
      v10 = lpInBuffer;
      if ( lpInBuffer )
        goto LABEL_27;
LABEL_20:
      v11 = I_ScPnPCreateNewListNodeByReaderName(*(_QWORD *)v3, &lpInBuffer);
      LOBYTE(v1) = v11;
      if ( !v11 )
        break;
      WppTraceIndent(v12, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          v1);
      }
      LOBYTE(v1) = 0;
LABEL_60:
      v3 = *(_QWORD *)(v3 + 240);
      if ( !v3 )
        goto LABEL_61;
    }
    I_ScPnPDeleteDeviceNodes((__int64)lpInBuffer);
    v10 = lpInBuffer;
LABEL_27:
    if ( *(_BYTE *)(v3 + 76) )
    {
      v16 = *(const wchar_t **)(v3 + 80);
      if ( !v16 || !wcscmp_0(v16, L"Microsoft Base Smart Card Crypto Provider") )
      {
        if ( *((_DWORD *)v10 + 50) )
          goto LABEL_57;
        v17 = I_ScPnPCreateDeviceNode((STRSAFE_LPCWSTR)v10, v3 + 40, *(unsigned __int8 *)(v3 + 76));
        LOBYTE(v1) = v17;
        if ( v17 )
        {
          WppTraceIndent(v18, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
              WPP_pszIndent,
              v1);
          }
          LOBYTE(v1) = 0;
          *((_DWORD *)lpInBuffer + 50) = 0;
        }
        else if ( !*(_QWORD *)(v3 + 80) )
        {
          ++*((_DWORD *)g_pScPnPState + 150);
          *((_DWORD *)lpInBuffer + 51) = 1;
        }
      }
      else
      {
        *((_DWORD *)v10 + 50) = 0;
      }
LABEL_56:
      v10 = lpInBuffer;
LABEL_57:
      if ( v2 )
      {
        *((_QWORD *)v10 + 30) = v2;
        v2 = lpInBuffer;
      }
      else
      {
        v2 = v10;
        *((_QWORD *)v10 + 30) = 0;
      }
      goto LABEL_60;
    }
    if ( !*((_DWORD *)v10 + 50) )
      goto LABEL_57;
    if ( DeviceIoControl(*((HANDLE *)v10 + 24), 0x310FA4u, v10, 0xC0u, 0, 0, &BytesReturned, 0) )
      goto LABEL_42;
    LastError = GetLastError();
    v15 = LastError;
    switch ( LastError )
    {
      case 0u:
        goto LABEL_42;
      case 0xAAu:
        WppTraceIndent(v14, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent);
        }
        break;
      case 0x103u:
      case 0xC000000E:
LABEL_42:
        *((_DWORD *)lpInBuffer + 50) = 0;
        break;
      default:
        WppTraceIndent(v14, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent,
            v15);
        }
        break;
    }
    LOBYTE(v1) = 0;
    goto LABEL_56;
  }
  LOBYTE(v1) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 496));
LABEL_62:
  SetEvent(*((HANDLE *)g_pScPnPState + 12));
  result = WppTraceIndent(v20, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    return WPP_SF_sD(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             69,
             (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
             WPP_pszIndent,
             v1);
  }
  return result;
}

```

## disassembly

```asm
0x180006a40  sub     rsp, 68h
0x180006a44  mov     [rsp+68h+var_18], r12
0x180006a49  xor     edx, edx
0x180006a4b  mov     [rsp+68h+var_28], r15
0x180006a50  xor     r15d, r15d
0x180006a53  mov     [rsp+68h+BytesReturned], r15d
0x180006a58  mov     [rsp+68h+lpInBuffer], r15
0x180006a5d  call    WppTraceIndent
0x180006a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a69  lea     r12, WPP_GLOBAL_Control
0x180006a70  cmp     rcx, r12
0x180006a73  jz      short loc_180006A9D
0x180006a75  test    byte ptr [rcx+1Ch], 2
0x180006a79  jz      short loc_180006A9D
0x180006a7b  cmp     byte ptr [rcx+19h], 5
0x180006a7f  jb      short loc_180006A9D
0x180006a81  mov     r9, cs:WPP_pszIndent
0x180006a88  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006a8f  mov     rcx, [rcx+10h]
0x180006a93  mov     edx, 40h ; '@'
0x180006a98  call    WPP_SF_s
0x180006a9d  mov     rcx, cs:g_pScPnPState
0x180006aa4  add     rcx, 1F0h; lpCriticalSection
0x180006aab  mov     [rsp+68h+var_8], rbp
0x180006ab0  call    cs:__imp_EnterCriticalSection
0x180006ab6  mov     rcx, cs:g_pScPnPState
0x180006abd  xor     edx, edx; dwMilliseconds
0x180006abf  mov     rcx, [rcx+1E8h]; hHandle
0x180006ac6  call    cs:__imp_WaitForSingleObject
0x180006acc  cmp     eax, 102h
0x180006ad1  jz      short loc_180006AEF
0x180006ad3  mov     rcx, cs:g_pScPnPState
0x180006ada  mov     ebp, r15d
0x180006add  add     rcx, 1F0h; lpCriticalSection
0x180006ae4  call    cs:__imp_LeaveCriticalSection
0x180006aea  jmp     loc_180006ECA
0x180006aef  mov     r8, cs:g_pScPnPState
0x180006af6  lea     rcx, I_ScPnPHandleReaderAction
0x180006afd  xor     edx, edx
0x180006aff  lea     rax, [r8+188h]
0x180006b06  lea     r9, [r8+190h]
0x180006b0d  mov     [rsp+68h+lpOutBuffer], rax
0x180006b12  mov     r8, [r8+58h]
0x180006b16  call    I_ScPnPCreateThreadpoolWait
0x180006b1b  mov     rcx, cs:g_pScPnPState
0x180006b22  mov     ebp, eax
0x180006b24  add     rcx, 1F0h; lpCriticalSection
0x180006b2b  call    cs:__imp_LeaveCriticalSection
0x180006b31  test    ebp, ebp
0x180006b33  jnz     loc_180006ECA
0x180006b39  mov     rcx, cs:g_pScPnPState
0x180006b40  mov     [rsp+68h+var_10], rsi
0x180006b45  add     rcx, 30h ; '0'; lpCriticalSection
0x180006b49  mov     [rsp+68h+var_20], r14
0x180006b4e  mov     r14, r15
0x180006b51  call    cs:__imp_EnterCriticalSection
0x180006b57  mov     rcx, cs:g_pScPnPState
0x180006b5e  add     rcx, 220h; lpCriticalSection
0x180006b65  call    cs:__imp_EnterCriticalSection
0x180006b6b  mov     rcx, cs:g_pScPnPState
0x180006b72  mov     rsi, [rcx+70h]
0x180006b76  test    rsi, rsi
0x180006b79  jz      loc_180006E7F
0x180006b7f  mov     [rsp+68h+arg_10], rbx
0x180006b87  nop     word ptr [rax+rax+00000000h]
0x180006b90  mov     r11, cs:g_pScPnPState
0x180006b97  mov     r10, r15
0x180006b9a  mov     [rsp+68h+lpInBuffer], r15
0x180006b9f  mov     r9, [r11+250h]
0x180006ba6  test    r9, r9
0x180006ba9  jz      short loc_180006C03
0x180006bab  mov     r8, [rsi]
0x180006bae  mov     rax, r9
0x180006bb1  sub     r8, r9
0x180006bb4  movzx   edx, word ptr [rax]
0x180006bb7  movzx   ecx, word ptr [rax+r8]
0x180006bbc  sub     edx, ecx
0x180006bbe  jnz     short loc_180006BC8
0x180006bc0  add     rax, 2
0x180006bc4  test    ecx, ecx
0x180006bc6  jnz     short loc_180006BB4
0x180006bc8  test    edx, edx
0x180006bca  jz      short loc_180006BD8
0x180006bcc  mov     r10, r9
0x180006bcf  mov     r9, [r9+0F0h]
0x180006bd6  jmp     short loc_180006BA6
0x180006bd8  mov     [rsp+68h+lpInBuffer], r9
0x180006bdd  mov     rcx, [r9+0F0h]
0x180006be4  test    r10, r10
0x180006be7  jnz     short loc_180006BF2
0x180006be9  mov     [r11+250h], rcx
0x180006bf0  jmp     short loc_180006BF9
0x180006bf2  mov     [r10+0F0h], rcx
0x180006bf9  mov     rbx, [rsp+68h+lpInBuffer]
0x180006bfe  test    rbx, rbx
0x180006c01  jnz     short loc_180006C6F
0x180006c03  mov     rcx, [rsi]
0x180006c06  lea     rdx, [rsp+68h+lpInBuffer]
0x180006c0b  call    I_ScPnPCreateNewListNodeByReaderName
0x180006c10  mov     ebp, eax
0x180006c12  test    eax, eax
0x180006c14  jz      short loc_180006C60
0x180006c16  mov     edx, 2
0x180006c1b  call    WppTraceIndent
0x180006c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c27  cmp     rcx, r12
0x180006c2a  jz      short loc_180006C58
0x180006c2c  test    byte ptr [rcx+1Ch], 1
0x180006c30  jz      short loc_180006C58
0x180006c32  cmp     byte ptr [rcx+19h], 2
0x180006c36  jb      short loc_180006C58
0x180006c38  mov     r9, cs:WPP_pszIndent
0x180006c3f  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006c46  mov     rcx, [rcx+10h]
0x180006c4a  mov     edx, 41h ; 'A'
0x180006c4f  mov     dword ptr [rsp+68h+lpOutBuffer], ebp
0x180006c53  call    WPP_SF_sD
0x180006c58  mov     ebp, r15d
0x180006c5b  jmp     loc_180006E67
0x180006c60  mov     rcx, [rsp+68h+lpInBuffer]
0x180006c65  call    I_ScPnPDeleteDeviceNodes
0x180006c6a  mov     rbx, [rsp+68h+lpInBuffer]
0x180006c6f  cmp     [rsi+4Ch], r15b
0x180006c73  jnz     loc_180006D87
0x180006c79  cmp     [rbx+0C8h], r15d
0x180006c80  jz      loc_180006E4A
0x180006c86  mov     rcx, [rbx+0C0h]; hDevice
0x180006c8d  lea     rax, [rsp+68h+BytesReturned]
0x180006c92  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x180006c97  mov     r9d, 0C0h; nInBufferSize
0x180006c9d  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180006ca2  mov     r8, rbx; lpInBuffer
0x180006ca5  mov     [rsp+68h+nOutBufferSize], r15d; nOutBufferSize
0x180006caa  mov     edx, 310FA4h; dwIoControlCode
0x180006caf  mov     [rsp+68h+lpOutBuffer], r15; lpOutBuffer
0x180006cb4  call    cs:__imp_DeviceIoControl
0x180006cba  test    eax, eax
0x180006cbc  jnz     loc_180006D73
0x180006cc2  call    cs:__imp_GetLastError
0x180006cc8  mov     ebx, eax
0x180006cca  test    eax, eax
0x180006ccc  jz      loc_180006D73
0x180006cd2  cmp     eax, 0AAh
0x180006cd7  jz      short loc_180006D33
0x180006cd9  cmp     eax, 103h
0x180006cde  jz      loc_180006D73
0x180006ce4  cmp     eax, 0C000000Eh
0x180006ce9  jz      loc_180006D73
0x180006cef  mov     edx, 2
0x180006cf4  call    WppTraceIndent
0x180006cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d00  cmp     rcx, r12
0x180006d03  jz      short loc_180006D7F
0x180006d05  test    byte ptr [rcx+1Ch], 1
0x180006d09  jz      short loc_180006D7F
0x180006d0b  cmp     byte ptr [rcx+19h], 2
0x180006d0f  jb      short loc_180006D7F
0x180006d11  mov     r9, cs:WPP_pszIndent
0x180006d18  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006d1f  mov     rcx, [rcx+10h]
0x180006d23  mov     edx, 43h ; 'C'
0x180006d28  mov     dword ptr [rsp+68h+lpOutBuffer], ebx
0x180006d2c  call    WPP_SF_sD
0x180006d31  jmp     short loc_180006D7F
0x180006d33  mov     edx, 2
0x180006d38  call    WppTraceIndent
0x180006d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d44  cmp     rcx, r12
0x180006d47  jz      short loc_180006D7F
0x180006d49  test    byte ptr [rcx+1Ch], 1
0x180006d4d  jz      short loc_180006D7F
0x180006d4f  cmp     byte ptr [rcx+19h], 4
0x180006d53  jb      short loc_180006D7F
0x180006d55  mov     r9, cs:WPP_pszIndent
0x180006d5c  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006d63  mov     rcx, [rcx+10h]
0x180006d67  mov     edx, 42h ; 'B'
0x180006d6c  call    WPP_SF_s
0x180006d71  jmp     short loc_180006D7F
0x180006d73  mov     rax, [rsp+68h+lpInBuffer]
0x180006d78  mov     [rax+0C8h], r15d
0x180006d7f  mov     ebp, r15d
0x180006d82  jmp     loc_180006E45
0x180006d87  mov     rcx, [rsi+50h]; String1
0x180006d8b  test    rcx, rcx
0x180006d8e  jz      short loc_180006DAC
0x180006d90  lea     rdx, aMicrosoftBaseS; "Microsoft Base Smart Card Crypto Provid"...
0x180006d97  call    wcscmp_0
0x180006d9c  test    eax, eax
0x180006d9e  jz      short loc_180006DAC
0x180006da0  mov     [rbx+0C8h], r15d
0x180006da7  jmp     loc_180006E45
0x180006dac  cmp     [rbx+0C8h], r15d
0x180006db3  jnz     loc_180006E4A
0x180006db9  movzx   r8d, byte ptr [rsi+4Ch]
0x180006dbe  lea     rdx, [rsi+28h]
0x180006dc2  mov     rcx, rbx; pszSrc
0x180006dc5  call    I_ScPnPCreateDeviceNode
0x180006dca  mov     ebp, eax
0x180006dcc  test    eax, eax
0x180006dce  jz      short loc_180006E23
0x180006dd0  mov     edx, 2
0x180006dd5  call    WppTraceIndent
0x180006dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180006de1  cmp     rcx, r12
0x180006de4  jz      short loc_180006E12
0x180006de6  test    byte ptr [rcx+1Ch], 1
0x180006dea  jz      short loc_180006E12
0x180006dec  cmp     byte ptr [rcx+19h], 2
0x180006df0  jb      short loc_180006E12
0x180006df2  mov     r9, cs:WPP_pszIndent
0x180006df9  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006e00  mov     rcx, [rcx+10h]
0x180006e04  mov     edx, 44h ; 'D'
0x180006e09  mov     dword ptr [rsp+68h+lpOutBuffer], ebp
0x180006e0d  call    WPP_SF_sD
0x180006e12  mov     rax, [rsp+68h+lpInBuffer]
0x180006e17  mov     ebp, r15d
0x180006e1a  mov     [rax+0C8h], r15d
0x180006e21  jmp     short loc_180006E45
0x180006e23  cmp     [rsi+50h], r15
0x180006e27  jnz     short loc_180006E45
0x180006e29  mov     rax, cs:g_pScPnPState
0x180006e30  inc     dword ptr [rax+258h]
0x180006e36  mov     rax, [rsp+68h+lpInBuffer]
0x180006e3b  mov     dword ptr [rax+0CCh], 1
0x180006e45  mov     rbx, [rsp+68h+lpInBuffer]
0x180006e4a  test    r14, r14
0x180006e4d  jnz     short loc_180006E5B
0x180006e4f  mov     r14, rbx
0x180006e52  mov     [rbx+0F0h], r15
0x180006e59  jmp     short loc_180006E67
0x180006e5b  mov     [rbx+0F0h], r14
0x180006e62  mov     r14, [rsp+68h+lpInBuffer]
0x180006e67  mov     rsi, [rsi+0F0h]
0x180006e6e  test    rsi, rsi
0x180006e71  jnz     loc_180006B90
0x180006e77  mov     rbx, [rsp+68h+arg_10]
0x180006e7f  mov     rcx, cs:g_pScPnPState
0x180006e86  xor     edx, edx
0x180006e88  mov     rcx, [rcx+250h]; lpMem
0x180006e8f  call    I_ScPnPFreeDeviceList
0x180006e94  mov     rcx, cs:g_pScPnPState
0x180006e9b  mov     [rcx+250h], r14
0x180006ea2  add     rcx, 220h; lpCriticalSection
0x180006ea9  call    cs:__imp_LeaveCriticalSection
0x180006eaf  mov     rcx, cs:g_pScPnPState
0x180006eb6  add     rcx, 30h ; '0'; lpCriticalSection
0x180006eba  call    cs:__imp_LeaveCriticalSection
0x180006ec0  mov     r14, [rsp+68h+var_20]
0x180006ec5  mov     rsi, [rsp+68h+var_10]
0x180006eca  mov     rcx, cs:g_pScPnPState
0x180006ed1  mov     rcx, [rcx+60h]; hEvent
0x180006ed5  call    cs:__imp_SetEvent
0x180006edb  mov     edx, 1
0x180006ee0  call    WppTraceIndent
0x180006ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eec  mov     r15, [rsp+68h+var_28]
0x180006ef1  cmp     rcx, r12
0x180006ef4  mov     r12, [rsp+68h+var_18]
0x180006ef9  jz      short loc_180006F27
0x180006efb  test    byte ptr [rcx+1Ch], 2
0x180006eff  jz      short loc_180006F27
0x180006f01  cmp     byte ptr [rcx+19h], 5
0x180006f05  jb      short loc_180006F27
0x180006f07  mov     r9, cs:WPP_pszIndent
0x180006f0e  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180006f15  mov     rcx, [rcx+10h]
0x180006f19  mov     edx, 45h ; 'E'
0x180006f1e  mov     dword ptr [rsp+68h+lpOutBuffer], ebp
0x180006f22  call    WPP_SF_sD
0x180006f27  mov     rbp, [rsp+68h+var_8]
0x180006f2c  add     rsp, 68h
0x180006f30  retn
```
