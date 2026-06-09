# InitializeMibHandler

- ea: `0x180020be4`
- end: `0x180021217`
- name: `InitializeMibHandler`
- size: `1587`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020238`

## callees

- `0x18000ac60`
- `0x18000ba80`
- `0x18000baa8`
- `0x180020be4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x180020cf1`
- `KERNEL32!HeapCreate` at `0x180020d60`
- `KERNEL32!HeapCreate` at `0x180020df5`
- `KERNEL32!HeapCreate` at `0x180020e88`
- `KERNEL32!HeapCreate` at `0x180020f1b`
- `KERNEL32!HeapCreate` at `0x180020fae`
- `KERNEL32!HeapCreate` at `0x180020cf1`
- `KERNEL32!HeapCreate` at `0x180020d60`
- `KERNEL32!HeapCreate` at `0x180020df5`
- `KERNEL32!HeapCreate` at `0x180020e88`
- `KERNEL32!HeapCreate` at `0x180020f1b`
- `KERNEL32!HeapCreate` at `0x180020fae`
- `KERNEL32!HeapDestroy` at `0x1800210e1`
- `KERNEL32!HeapDestroy` at `0x180021116`
- `KERNEL32!HeapDestroy` at `0x18002114b`
- `KERNEL32!HeapDestroy` at `0x180021180`
- `KERNEL32!HeapDestroy` at `0x1800211b5`
- `KERNEL32!HeapDestroy` at `0x1800211ce`
- `KERNEL32!HeapDestroy` at `0x1800589e7`
- `KERNEL32!HeapDestroy` at `0x180058a24`
- `KERNEL32!HeapDestroy` at `0x180058a61`
- `KERNEL32!HeapDestroy` at `0x180058a9e`
- `KERNEL32!HeapDestroy` at `0x180058adb`
- `KERNEL32!HeapDestroy` at `0x180058af9`
- `KERNEL32!HeapDestroy` at `0x1800210e1`
- `KERNEL32!HeapDestroy` at `0x180021116`
- `KERNEL32!HeapDestroy` at `0x18002114b`
- `KERNEL32!HeapDestroy` at `0x180021180`
- `KERNEL32!HeapDestroy` at `0x1800211b5`
- `KERNEL32!HeapDestroy` at `0x1800211ce`
- `KERNEL32!HeapDestroy` at `0x1800589e7`
- `KERNEL32!HeapDestroy` at `0x180058a24`
- `KERNEL32!HeapDestroy` at `0x180058a61`
- `KERNEL32!HeapDestroy` at `0x180058a9e`
- `KERNEL32!HeapDestroy` at `0x180058adb`
- `KERNEL32!HeapDestroy` at `0x180058af9`
- `KERNEL32!GetTickCount` at `0x180020c92`
- `KERNEL32!GetTickCount` at `0x180020c92`
- `KERNEL32!GetLastError` at `0x180020d03`
- `KERNEL32!GetLastError` at `0x180020d72`
- `KERNEL32!GetLastError` at `0x180020e07`
- `KERNEL32!GetLastError` at `0x180020e9a`
- `KERNEL32!GetLastError` at `0x180020f2d`
- `KERNEL32!GetLastError` at `0x180020fc0`
- `KERNEL32!GetLastError` at `0x180020d03`
- `KERNEL32!GetLastError` at `0x180020d72`
- `KERNEL32!GetLastError` at `0x180020e07`
- `KERNEL32!GetLastError` at `0x180020e9a`
- `KERNEL32!GetLastError` at `0x180020f2d`
- `KERNEL32!GetLastError` at `0x180020fc0`
- `KERNEL32!HeapFree` at `0x1800210cf`
- `KERNEL32!HeapFree` at `0x180021104`
- `KERNEL32!HeapFree` at `0x180021139`
- `KERNEL32!HeapFree` at `0x18002116e`
- `KERNEL32!HeapFree` at `0x1800211a3`
- `KERNEL32!HeapFree` at `0x1800589d4`
- `KERNEL32!HeapFree` at `0x180058a11`
- `KERNEL32!HeapFree` at `0x180058a4e`
- `KERNEL32!HeapFree` at `0x180058a8b`
- `KERNEL32!HeapFree` at `0x180058ac8`
- `KERNEL32!HeapFree` at `0x1800210cf`
- `KERNEL32!HeapFree` at `0x180021104`
- `KERNEL32!HeapFree` at `0x180021139`
- `KERNEL32!HeapFree` at `0x18002116e`
- `KERNEL32!HeapFree` at `0x1800211a3`
- `KERNEL32!HeapFree` at `0x1800589d4`
- `KERNEL32!HeapFree` at `0x180058a11`
- `KERNEL32!HeapFree` at `0x180058a4e`
- `KERNEL32!HeapFree` at `0x180058a8b`
- `KERNEL32!HeapFree` at `0x180058ac8`
- `KERNEL32!HeapAlloc` at `0x180020dab`
- `KERNEL32!HeapAlloc` at `0x180020e43`
- `KERNEL32!HeapAlloc` at `0x180020ed6`
- `KERNEL32!HeapAlloc` at `0x180020f69`
- `KERNEL32!HeapAlloc` at `0x180020ffc`
- `KERNEL32!HeapAlloc` at `0x180020dab`
- `KERNEL32!HeapAlloc` at `0x180020e43`
- `KERNEL32!HeapAlloc` at `0x180020ed6`
- `KERNEL32!HeapAlloc` at `0x180020f69`
- `KERNEL32!HeapAlloc` at `0x180020ffc`

## string_xrefs

- `0x18002107b`: `InitializeMibHandler: Couldnt update %hs Cache`

## pseudocode

```c
__int64 InitializeMibHandler()
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  const wchar_t *v2; // r8
  HANDLE v3; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  unsigned int i; // ebx
  __int64 v9; // rax
  _DWORD v11[3]; // [rsp+24h] [rbp-844h] BYREF
  _WORD v12[2]; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-834h] BYREF

  v11[0] = 0;
  v12[0] = 0;
  v12[1] = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v12[0] = 0;
    FormatRRASErrorString(v12, L"Entered: %ws", L"InitializeMibHandler");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v12);
  }
  GetTickCount();
  g_hIfHeap = 0;
  g_hUdpHeap = 0;
  g_UdpInfo = 0;
  g_hTcpHeap = 0;
  g_TcpInfo = 0;
  g_hIpAddrHeap = 0;
  g_IpInfo = 0;
  g_hIpForwardHeap = 0;
  qword_18008C7E8 = 0;
  g_hIpNetHeap = 0;
  qword_18008C7F0 = 0;
  g_hIfHeap = HeapCreate(1u, 0, 0);
  if ( !g_hIfHeap )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_48;
    v12[0] = 0;
    FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate IF Heap. Error %d", LastError);
    goto LABEL_7;
  }
  v3 = HeapCreate(1u, 0, 0);
  g_hUdpHeap = v3;
  if ( !v3 )
  {
    v1 = GetLastError();
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12[0] = 0;
      FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate UDP Heap. Error %d", v1);
LABEL_7:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_48;
      v2 = v12;
      goto LABEL_9;
    }
    goto LABEL_48;
  }
  g_UdpInfo = HeapAlloc(v3, 1u, 0x5Cu);
  if ( !g_UdpInfo )
  {
    v1 = 8;
    LOBYTE(v11[0]) = Microsoft_Windows_RRASEnableBits & 0x80;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_48;
    v2 = L"InitializeMibHandler: Couldnt allocate UDP table";
    goto LABEL_9;
  }
  dword_18008C7B8 = 10;
  v4 = HeapCreate(1u, 0, 0);
  g_hTcpHeap = v4;
  if ( v4 )
  {
    g_TcpInfo = HeapAlloc(v4, 1u, 0xD4u);
    if ( g_TcpInfo )
    {
      dword_18008C7C8 = 10;
      v5 = HeapCreate(1u, 0, 0);
      g_hIpAddrHeap = v5;
      if ( !v5 )
      {
        v1 = GetLastError();
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v12[0] = 0;
          FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate IP Addr Heap. Error %d", v1);
          goto LABEL_7;
        }
        goto LABEL_48;
      }
      g_IpInfo = HeapAlloc(v5, 1u, 0xFCu);
      if ( g_IpInfo )
      {
        dword_18008C7F8 = 10;
        v6 = HeapCreate(1u, 0, 0);
        g_hIpForwardHeap = v6;
        if ( !v6 )
        {
          v1 = GetLastError();
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v12[0] = 0;
            FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate IP Forward Heap. Error %d", v1);
            goto LABEL_7;
          }
          goto LABEL_48;
        }
        qword_18008C7E8 = HeapAlloc(v6, 1u, 0x23Cu);
        if ( qword_18008C7E8 )
        {
          dword_18008C7FC = 10;
          v7 = HeapCreate(1u, 0, 0);
          g_hIpNetHeap = v7;
          if ( !v7 )
          {
            v1 = GetLastError();
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v12[0] = 0;
              FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate IP Net Heap. Error %d", v1);
              goto LABEL_7;
            }
            goto LABEL_48;
          }
          qword_18008C7F0 = HeapAlloc(v7, 1u, 0xFCu);
          if ( qword_18008C7F0 )
          {
            dword_18008C800 = 10;
            for ( i = 0; ; ++i )
            {
              v11[1] = i;
              if ( i >= 6 )
                break;
              g_LastUpdateTable[i] = 0;
              if ( (unsigned int)UpdateCache(i, v11) )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v12[0] = 0;
                  v9 = CacheToA(i);
                  FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt update %hs Cache", v9);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v12);
                }
              }
            }
            v1 = 0;
            goto LABEL_48;
          }
          v1 = 8;
          LOBYTE(v11[0]) = Microsoft_Windows_RRASEnableBits & 0x80;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
            goto LABEL_48;
          v2 = L"InitializeMibHandler: Couldnt allocate IP Net table";
        }
        else
        {
          v1 = 8;
          LOBYTE(v11[0]) = Microsoft_Windows_RRASEnableBits & 0x80;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
            goto LABEL_48;
          v2 = L"InitializeMibHandler: Couldnt allocate IP Forward table";
        }
      }
      else
      {
        v1 = 8;
        LOBYTE(v11[0]) = Microsoft_Windows_RRASEnableBits & 0x80;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_48;
        v2 = L"InitializeMibHandler: Couldnt allocate IP Addr table.";
      }
    }
    else
    {
      v1 = 8;
      LOBYTE(v11[0]) = Microsoft_Windows_RRASEnableBits & 0x80;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_48;
      v2 = L"InitializeMibHandler: Couldnt allocate TCP table";
    }
LABEL_9:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v2);
    goto LABEL_48;
  }
  v1 = GetLastError();
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v12[0] = 0;
    FormatRRASErrorString(v12, L"InitializeMibHandler: Couldnt allocate TCP Heap. Error %d", v1);
    goto LABEL_7;
  }
LABEL_48:
  if ( v1 )
  {
    if ( qword_18008C7F0 )
      HeapFree(g_hIpNetHeap, 1u, qword_18008C7F0);
    if ( g_hIpNetHeap )
      HeapDestroy(g_hIpNetHeap);
    g_hIpNetHeap = 0;
    if ( qword_18008C7E8 )
      HeapFree(g_hIpForwardHeap, 1u, qword_18008C7E8);
    if ( g_hIpForwardHeap )
      HeapDestroy(g_hIpForwardHeap);
    g_hIpForwardHeap = 0;
    if ( g_IpInfo )
      HeapFree(g_hIpAddrHeap, 1u, g_IpInfo);
    if ( g_hIpAddrHeap )
      HeapDestroy(g_hIpAddrHeap);
    g_hIpAddrHeap = 0;
    if ( g_TcpInfo )
      HeapFree(g_hTcpHeap, 1u, g_TcpInfo);
    if ( g_hTcpHeap )
      HeapDestroy(g_hTcpHeap);
    g_hTcpHeap = 0;
    if ( g_UdpInfo )
      HeapFree(g_hUdpHeap, 1u, g_UdpInfo);
    if ( g_hUdpHeap )
      HeapDestroy(g_hUdpHeap);
    g_hUdpHeap = 0;
    if ( g_hIfHeap )
      HeapDestroy(g_hIfHeap);
    g_hIfHeap = 0;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitializeMibHandler");
  return v1;
}

```

## disassembly

```asm
0x180020be4  push    rbx
0x180020be6  push    rsi
0x180020be7  push    rdi
0x180020be8  push    r14
0x180020bea  push    r15
0x180020bec  sub     rsp, 840h
0x180020bf3  mov     rax, cs:__security_cookie
0x180020bfa  xor     rax, rsp
0x180020bfd  mov     [rsp+868h+var_38], rax
0x180020c05  xor     r14d, r14d
0x180020c08  mov     [rsp+868h+var_844], r14d
0x180020c0d  mov     [rsp+868h+var_838], r14w
0x180020c13  mov     eax, r14d
0x180020c16  mov     [rsp+868h+var_836], ax
0x180020c1b  xor     edx, edx; Val
0x180020c1d  mov     r8d, 7FCh; Size
0x180020c23  lea     rcx, [rsp+868h+var_834]; void *
0x180020c28  call    memset_0
0x180020c2d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020c34  jge     short loc_180020C7F
0x180020c36  mov     eax, r14d
0x180020c39  mov     [rsp+868h+var_838], ax
0x180020c3e  lea     r8, aInitializemibh_5; "InitializeMibHandler"
0x180020c45  lea     rdx, aEnteredWs; "Entered: %ws"
0x180020c4c  lea     rcx, [rsp+868h+var_838]
0x180020c51  call    FormatRRASErrorString
0x180020c56  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020c5d  jge     short loc_180020C7F
0x180020c5f  lea     r8, [rsp+868h+var_838]
0x180020c64  lea     rdi, RasRtrmgrTraceInfo
0x180020c6b  mov     rdx, rdi
0x180020c6e  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180020c75  mov     rcx, rsi
0x180020c78  call    McTemplateU0z_EventWriteTransfer
0x180020c7d  jmp     short loc_180020C8D
0x180020c7f  lea     rdi, RasRtrmgrTraceInfo
0x180020c86  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180020c8d  mov     [rsp+868h+var_848], r14d
0x180020c92  call    cs:__imp_GetTickCount
0x180020c98  mov     cs:g_hIfHeap, r14
0x180020c9f  mov     cs:g_hUdpHeap, r14
0x180020ca6  mov     cs:g_UdpInfo, r14
0x180020cad  mov     cs:g_hTcpHeap, r14
0x180020cb4  mov     cs:g_TcpInfo, r14
0x180020cbb  mov     cs:g_hIpAddrHeap, r14
0x180020cc2  mov     cs:g_IpInfo, r14
0x180020cc9  mov     cs:g_hIpForwardHeap, r14
0x180020cd0  mov     cs:qword_18008C7E8, r14
0x180020cd7  mov     cs:g_hIpNetHeap, r14
0x180020cde  mov     cs:qword_18008C7F0, r14
0x180020ce5  xor     r8d, r8d; dwMaximumSize
0x180020ce8  xor     edx, edx; dwInitialSize
0x180020cea  lea     r15d, [r8+1]
0x180020cee  mov     ecx, r15d; flOptions
0x180020cf1  call    cs:__imp_HeapCreate
0x180020cf7  mov     cs:g_hIfHeap, rax
0x180020cfe  test    rax, rax
0x180020d01  jnz     short loc_180020D58
0x180020d03  call    cs:__imp_GetLastError
0x180020d09  mov     ebx, eax
0x180020d0b  mov     [rsp+868h+var_848], eax
0x180020d0f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020d16  jge     loc_1800210B1
0x180020d1c  mov     [rsp+868h+var_838], r14w
0x180020d22  mov     r8d, eax
0x180020d25  lea     rdx, aInitializemibh_2; "InitializeMibHandler: Couldnt allocate "...
0x180020d2c  lea     rcx, [rsp+868h+var_838]
0x180020d31  call    FormatRRASErrorString
0x180020d36  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020d3d  jge     loc_1800210B1
0x180020d43  lea     r8, [rsp+868h+var_838]
0x180020d48  mov     rdx, rdi
0x180020d4b  mov     rcx, rsi
0x180020d4e  call    McTemplateU0z_EventWriteTransfer
0x180020d53  jmp     loc_1800210B1
0x180020d58  xor     r8d, r8d; dwMaximumSize
0x180020d5b  xor     edx, edx; dwInitialSize
0x180020d5d  mov     ecx, r15d; flOptions
0x180020d60  call    cs:__imp_HeapCreate
0x180020d66  mov     cs:g_hUdpHeap, rax
0x180020d6d  test    rax, rax
0x180020d70  jnz     short loc_180020D9F
0x180020d72  call    cs:__imp_GetLastError
0x180020d78  mov     ebx, eax
0x180020d7a  mov     [rsp+868h+var_848], eax
0x180020d7e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020d85  jge     loc_1800210B1
0x180020d8b  mov     eax, r14d
0x180020d8e  mov     [rsp+868h+var_838], ax
0x180020d93  mov     r8d, ebx
0x180020d96  lea     rdx, aInitializemibh_1; "InitializeMibHandler: Couldnt allocate "...
0x180020d9d  jmp     short loc_180020D2C
0x180020d9f  mov     r8d, 5Ch ; '\'; dwBytes
0x180020da5  mov     edx, r15d; dwFlags
0x180020da8  mov     rcx, rax; hHeap
0x180020dab  call    cs:__imp_HeapAlloc
0x180020db1  mov     cs:g_UdpInfo, rax
0x180020db8  test    rax, rax
0x180020dbb  jnz     short loc_180020DE2
0x180020dbd  lea     ebx, [rax+8]
0x180020dc0  mov     [rsp+868h+var_848], ebx
0x180020dc4  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180020dca  and     al, 80h
0x180020dcc  mov     byte ptr [rsp+868h+var_844], al
0x180020dd0  jz      loc_1800210B1
0x180020dd6  lea     r8, aInitializemibh_7; "InitializeMibHandler: Couldnt allocate "...
0x180020ddd  jmp     loc_180020D48
0x180020de2  mov     ebx, 0Ah
0x180020de7  mov     cs:dword_18008C7B8, ebx
0x180020ded  xor     r8d, r8d; dwMaximumSize
0x180020df0  xor     edx, edx; dwInitialSize
0x180020df2  mov     ecx, r15d; flOptions
0x180020df5  call    cs:__imp_HeapCreate
0x180020dfb  mov     cs:g_hTcpHeap, rax
0x180020e02  test    rax, rax
0x180020e05  jnz     short loc_180020E37
0x180020e07  call    cs:__imp_GetLastError
0x180020e0d  mov     ebx, eax
0x180020e0f  mov     [rsp+868h+var_848], eax
0x180020e13  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020e1a  jge     loc_1800210B1
0x180020e20  mov     eax, r14d
0x180020e23  mov     [rsp+868h+var_838], ax
0x180020e28  mov     r8d, ebx
0x180020e2b  lea     rdx, aInitializemibh_3; "InitializeMibHandler: Couldnt allocate "...
0x180020e32  jmp     loc_180020D2C
0x180020e37  mov     r8d, 0D4h; dwBytes
0x180020e3d  mov     edx, r15d; dwFlags
0x180020e40  mov     rcx, rax; hHeap
0x180020e43  call    cs:__imp_HeapAlloc
0x180020e49  mov     cs:g_TcpInfo, rax
0x180020e50  test    rax, rax
0x180020e53  jnz     short loc_180020E7A
0x180020e55  lea     ebx, [rax+8]
0x180020e58  mov     [rsp+868h+var_848], ebx
0x180020e5c  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180020e62  and     al, 80h
0x180020e64  mov     byte ptr [rsp+868h+var_844], al
0x180020e68  jz      loc_1800210B1
0x180020e6e  lea     r8, aInitializemibh; "InitializeMibHandler: Couldnt allocate "...
0x180020e75  jmp     loc_180020D48
0x180020e7a  mov     cs:dword_18008C7C8, ebx
0x180020e80  xor     r8d, r8d; dwMaximumSize
0x180020e83  xor     edx, edx; dwInitialSize
0x180020e85  mov     ecx, r15d; flOptions
0x180020e88  call    cs:__imp_HeapCreate
0x180020e8e  mov     cs:g_hIpAddrHeap, rax
0x180020e95  test    rax, rax
0x180020e98  jnz     short loc_180020ECA
0x180020e9a  call    cs:__imp_GetLastError
0x180020ea0  mov     ebx, eax
0x180020ea2  mov     [rsp+868h+var_848], eax
0x180020ea6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020ead  jge     loc_1800210B1
0x180020eb3  mov     eax, r14d
0x180020eb6  mov     [rsp+868h+var_838], ax
0x180020ebb  mov     r8d, ebx
0x180020ebe  lea     rdx, aInitializemibh_9; "InitializeMibHandler: Couldnt allocate "...
0x180020ec5  jmp     loc_180020D2C
0x180020eca  mov     r8d, 0FCh; dwBytes
0x180020ed0  mov     edx, r15d; dwFlags
0x180020ed3  mov     rcx, rax; hHeap
0x180020ed6  call    cs:__imp_HeapAlloc
0x180020edc  mov     cs:g_IpInfo, rax
0x180020ee3  test    rax, rax
0x180020ee6  jnz     short loc_180020F0D
0x180020ee8  lea     ebx, [rax+8]
0x180020eeb  mov     [rsp+868h+var_848], ebx
0x180020eef  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180020ef5  and     al, 80h
0x180020ef7  mov     byte ptr [rsp+868h+var_844], al
0x180020efb  jz      loc_1800210B1
0x180020f01  lea     r8, aInitializemibh_6; "InitializeMibHandler: Couldnt allocate "...
0x180020f08  jmp     loc_180020D48
0x180020f0d  mov     cs:dword_18008C7F8, ebx
0x180020f13  xor     r8d, r8d; dwMaximumSize
0x180020f16  xor     edx, edx; dwInitialSize
0x180020f18  mov     ecx, r15d; flOptions
0x180020f1b  call    cs:__imp_HeapCreate
0x180020f21  mov     cs:g_hIpForwardHeap, rax
0x180020f28  test    rax, rax
0x180020f2b  jnz     short loc_180020F5D
0x180020f2d  call    cs:__imp_GetLastError
0x180020f33  mov     ebx, eax
0x180020f35  mov     [rsp+868h+var_848], eax
0x180020f39  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020f40  jge     loc_1800210B1
0x180020f46  mov     eax, r14d
0x180020f49  mov     [rsp+868h+var_838], ax
0x180020f4e  mov     r8d, ebx
0x180020f51  lea     rdx, aInitializemibh_0; "InitializeMibHandler: Couldnt allocate "...
0x180020f58  jmp     loc_180020D2C
0x180020f5d  mov     r8d, 23Ch; dwBytes
0x180020f63  mov     edx, r15d; dwFlags
0x180020f66  mov     rcx, rax; hHeap
0x180020f69  call    cs:__imp_HeapAlloc
0x180020f6f  mov     cs:qword_18008C7E8, rax
0x180020f76  test    rax, rax
0x180020f79  jnz     short loc_180020FA0
0x180020f7b  lea     ebx, [rax+8]
0x180020f7e  mov     [rsp+868h+var_848], ebx
0x180020f82  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180020f88  and     al, 80h
0x180020f8a  mov     byte ptr [rsp+868h+var_844], al
0x180020f8e  jz      loc_1800210B1
0x180020f94  lea     r8, aInitializemibh_10; "InitializeMibHandler: Couldnt allocate "...
0x180020f9b  jmp     loc_180020D48
0x180020fa0  mov     cs:dword_18008C7FC, ebx
0x180020fa6  xor     r8d, r8d; dwMaximumSize
0x180020fa9  xor     edx, edx; dwInitialSize
0x180020fab  mov     ecx, r15d; flOptions
0x180020fae  call    cs:__imp_HeapCreate
0x180020fb4  mov     cs:g_hIpNetHeap, rax
0x180020fbb  test    rax, rax
0x180020fbe  jnz     short loc_180020FF0
0x180020fc0  call    cs:__imp_GetLastError
0x180020fc6  mov     ebx, eax
0x180020fc8  mov     [rsp+868h+var_848], eax
0x180020fcc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180020fd3  jge     loc_1800210B1
0x180020fd9  mov     eax, r14d
0x180020fdc  mov     [rsp+868h+var_838], ax
0x180020fe1  mov     r8d, ebx
0x180020fe4  lea     rdx, aInitializemibh_4; "InitializeMibHandler: Couldnt allocate "...
0x180020feb  jmp     loc_180020D2C
0x180020ff0  mov     r8d, 0FCh; dwBytes
0x180020ff6  mov     edx, r15d; dwFlags
0x180020ff9  mov     rcx, rax; hHeap
0x180020ffc  call    cs:__imp_HeapAlloc
0x180021002  mov     cs:qword_18008C7F0, rax
0x180021009  test    rax, rax
0x18002100c  jnz     short loc_180021033
0x18002100e  lea     ebx, [rax+8]
0x180021011  mov     [rsp+868h+var_848], ebx
0x180021015  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18002101b  and     al, 80h
0x18002101d  mov     byte ptr [rsp+868h+var_844], al
0x180021021  jz      loc_1800210B1
0x180021027  lea     r8, aInitializemibh_11; "InitializeMibHandler: Couldnt allocate "...
0x18002102e  jmp     loc_180020D48
0x180021033  mov     cs:dword_18008C800, ebx
0x180021039  mov     ebx, r14d
0x18002103c  mov     [rsp+868h+var_840], ebx
0x180021040  cmp     ebx, 6
0x180021043  jnb     short loc_1800210AA
0x180021045  mov     eax, ebx
0x180021047  lea     rcx, g_LastUpdateTable
0x18002104e  mov     [rcx+rax*4], r14d
0x180021052  lea     rdx, [rsp+868h+var_844]
0x180021057  mov     ecx, ebx
0x180021059  call    UpdateCache
0x18002105e  test    eax, eax
0x180021060  jz      short loc_1800210A5
0x180021062  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021069  jge     short loc_1800210A5
0x18002106b  mov     [rsp+868h+var_838], r14w
0x180021071  mov     ecx, ebx
0x180021073  call    CacheToA
0x180021078  mov     r8, rax
0x18002107b  lea     rdx, aInitializemibh_8; "InitializeMibHandler: Couldnt update %h"...
0x180021082  lea     rcx, [rsp+868h+var_838]
0x180021087  call    FormatRRASErrorString
0x18002108c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021093  jge     short loc_1800210A5
0x180021095  lea     r8, [rsp+868h+var_838]
0x18002109a  mov     rdx, rdi
0x18002109d  mov     rcx, rsi
0x1800210a0  call    McTemplateU0z_EventWriteTransfer
0x1800210a5  add     ebx, r15d
0x1800210a8  jmp     short loc_18002103C
0x1800210aa  mov     ebx, r14d
0x1800210ad  mov     [rsp+868h+var_848], ebx
0x1800210b1  test    ebx, ebx
0x1800210b3  jz      loc_1800211DB
0x1800210b9  mov     r8, cs:qword_18008C7F0; lpMem
0x1800210c0  test    r8, r8
0x1800210c3  jz      short loc_1800210D5
0x1800210c5  mov     edx, r15d; dwFlags
0x1800210c8  mov     rcx, cs:g_hIpNetHeap; hHeap
0x1800210cf  call    cs:__imp_HeapFree
0x1800210d5  mov     rcx, cs:g_hIpNetHeap; hHeap
0x1800210dc  test    rcx, rcx
0x1800210df  jz      short loc_1800210E7
0x1800210e1  call    cs:__imp_HeapDestroy
0x1800210e7  mov     cs:g_hIpNetHeap, r14
0x1800210ee  mov     r8, cs:qword_18008C7E8; lpMem
0x1800210f5  test    r8, r8
0x1800210f8  jz      short loc_18002110A
0x1800210fa  mov     edx, r15d; dwFlags
0x1800210fd  mov     rcx, cs:g_hIpForwardHeap; hHeap
0x180021104  call    cs:__imp_HeapFree
0x18002110a  mov     rcx, cs:g_hIpForwardHeap; hHeap
0x180021111  test    rcx, rcx
0x180021114  jz      short loc_18002111C
0x180021116  call    cs:__imp_HeapDestroy
0x18002111c  mov     cs:g_hIpForwardHeap, r14
0x180021123  mov     r8, cs:g_IpInfo; lpMem
0x18002112a  test    r8, r8
0x18002112d  jz      short loc_18002113F
0x18002112f  mov     edx, r15d; dwFlags
  ... truncated ...
```
