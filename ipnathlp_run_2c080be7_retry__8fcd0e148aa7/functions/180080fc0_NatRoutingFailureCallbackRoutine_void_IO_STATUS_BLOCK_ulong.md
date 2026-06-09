# NatRoutingFailureCallbackRoutine(void *,_IO_STATUS_BLOCK *,ulong)

- ea: `0x180080fc0`
- end: `0x180081320`
- name: `?NatRoutingFailureCallbackRoutine@@YAXPEAXPEAU_IO_STATUS_BLOCK@@K@Z`
- size: `864`
- prototype: `void __stdcall(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000fde0`
- `0x180033910`
- `0x180051f30`
- `0x180052bf4`
- `0x1800533e8`
- `0x180056438`
- `0x180080fc0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008105d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008125e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008105d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008125e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800810bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800812ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800810bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800812ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081209`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081248`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081248`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800811eb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800811eb`
- `ntdll!NtDeviceIoControlFile` at `0x1800812bf`
- `ntdll!NtDeviceIoControlFile` at `0x1800812bf`
- `WS2_32!WSAAddressToStringA` at `0x180081152`
- `WS2_32!WSAAddressToStringA` at `0x180081152`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetAutodialAddressA` at `0x1800811c8`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetAutodialAddressA` at `0x1800811c8`

## string_xrefs

- `0x1800811e4`: `RASADHLP.DLL`
- `0x1800811ff`: `WSAttemptAutodialAddr`

## pseudocode

```c
void __fastcall NatRoutingFailureCallbackRoutine(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HMODULE LibraryA; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  int InputBuffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwAddressStringLength; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v11; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v12; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v13; // [rsp+60h] [rbp-A0h] BYREF
  struct sockaddr a; // [rsp+70h] [rbp-90h] BYREF
  CHAR szAddressString[80]; // [rsp+F0h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  memset_0(szAddressString, 0, 0x41u);
  dwAddressStringLength = 65;
  memset_0(&a, 0, 0x80u);
  InputBuffer = 0;
  EnterCriticalSection(&NatInterfaceLock);
  if ( NatConnectionNotifyEvent )
  {
    LeaveCriticalSection(&NatInterfaceLock);
    if ( AcquireComponentReference(&NatComponentReference) )
    {
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
      INETADDR_SETSOCKADDR(2u, &a, &NatpRoutingFailureNotification, scopeid_unspecified, 0);
      WSAAddressToStringA(&a, 0x80u, 0, szAddressString, &dwAddressStringLength);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids,
          szAddressString);
      }
      if ( IoStatusBlock->Status >= 0 )
      {
        v11 = 0;
        v12 = 0;
        if ( (unsigned __int8)IsRasQuerySharedAutoDialPresent()
          && RasGetAutodialAddressA(szAddressString, 0, 0, &v12, &v11) == 603
          && NatpRoutingFailureNotification )
        {
          LibraryA = LoadLibraryA("RASADHLP.DLL");
          v7 = LibraryA;
          if ( LibraryA )
          {
            ProcAddress = GetProcAddress(LibraryA, "WSAttemptAutodialAddr");
            if ( ProcAddress )
            {
              v13 = 0;
              LOWORD(v13) = 2;
              DWORD1(v13) = NatpRoutingFailureNotification;
              ((void (__fastcall *)(__int128 *, __int64))ProcAddress)(&v13, 16);
            }
            FreeLibrary(v7);
          }
        }
        else
        {
          NhDialSharedConnection();
        }
      }
      EnterCriticalSection(&NatInterfaceLock);
      InputBuffer = 0;
      NtDeviceIoControlFile(
        NatFileHandle,
        0,
        NatRoutingFailureCallbackRoutine,
        0,
        &NatRoutingFailureIoStatus,
        0x128004u,
        &InputBuffer,
        4u,
        &NatpRoutingFailureNotification,
        8u);
      LeaveCriticalSection(&NatInterfaceLock);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v5 = 170;
        goto LABEL_32;
      }
    }
    else
    {
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v5 = 168;
        goto LABEL_32;
      }
    }
  }
  else
  {
    LeaveCriticalSection(&NatInterfaceLock);
    ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v5 = 167;
LABEL_32:
      WPP_SF_(v4[2], v5, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x180080fc0  push    rbp
0x180080fc2  push    rbx
0x180080fc3  push    rsi
0x180080fc4  push    r12
0x180080fc6  push    r13
0x180080fc8  push    r14
0x180080fca  lea     rbp, [rsp-58h]
0x180080fcf  sub     rsp, 158h
0x180080fd6  mov     rax, cs:__security_cookie
0x180080fdd  xor     rax, rsp
0x180080fe0  mov     [rbp+80h+var_40], rax
0x180080fe4  mov     rbx, rdx
0x180080fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180080fee  lea     r12, WPP_GLOBAL_Control
0x180080ff5  lea     r14, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180080ffc  mov     esi, 200h
0x180081001  cmp     rcx, r12
0x180081004  jz      short loc_180081022
0x180081006  test    [rcx+1Ch], esi
0x180081009  jz      short loc_180081022
0x18008100b  cmp     byte ptr [rcx+19h], 6
0x18008100f  jb      short loc_180081022
0x180081011  mov     rcx, [rcx+10h]
0x180081015  mov     edx, 0A6h
0x18008101a  mov     r8, r14
0x18008101d  call    WPP_SF_
0x180081022  xor     edx, edx; Val
0x180081024  lea     rcx, [rbp+80h+szAddressString]; void *
0x180081028  lea     r8d, [rdx+41h]; Size
0x18008102c  call    memset_0
0x180081031  xor     edx, edx; Val
0x180081033  mov     [rsp+180h+dwAddressStringLength], 41h ; 'A'
0x18008103b  mov     r8d, 80h; Size
0x180081041  lea     rcx, [rsp+180h+a]; void *
0x180081046  call    memset_0
0x18008104b  lea     r13, NatInterfaceLock
0x180081052  mov     [rsp+180h+var_130], 0
0x18008105a  mov     rcx, r13; lpCriticalSection
0x18008105d  call    cs:__imp_EnterCriticalSection
0x180081064  nop     dword ptr [rax+rax+00h]
0x180081069  cmp     cs:NatConnectionNotifyEvent, 0
0x180081071  mov     rcx, r13; lpCriticalSection
0x180081074  jnz     short loc_1800810BB
0x180081076  call    cs:__imp_LeaveCriticalSection
0x18008107d  nop     dword ptr [rax+rax+00h]
0x180081082  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180081089  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18008108e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081095  cmp     rcx, r12
0x180081098  jz      loc_180081302
0x18008109e  test    [rcx+1Ch], esi
0x1800810a1  jz      loc_180081302
0x1800810a7  cmp     byte ptr [rcx+19h], 6
0x1800810ab  jb      loc_180081302
0x1800810b1  mov     edx, 0A7h
0x1800810b6  jmp     loc_1800812F6
0x1800810bb  call    cs:__imp_LeaveCriticalSection
0x1800810c2  nop     dword ptr [rax+rax+00h]
0x1800810c7  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800810ce  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800810d3  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800810da  test    al, al
0x1800810dc  jnz     short loc_180081110
0x1800810de  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800810e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800810ea  cmp     rcx, r12
0x1800810ed  jz      loc_180081302
0x1800810f3  test    [rcx+1Ch], esi
0x1800810f6  jz      loc_180081302
0x1800810fc  cmp     byte ptr [rcx+19h], 6
0x180081100  jb      loc_180081302
0x180081106  mov     edx, 0A8h
0x18008110b  jmp     loc_1800812F6
0x180081110  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180081115  mov     r9d, dword ptr cs:scopeid_unspecified; scope
0x18008111c  lea     r8, ?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; addr
0x180081123  xor     eax, eax
0x180081125  lea     rdx, [rsp+180h+a]; a
0x18008112a  mov     [rsp+180h+port], ax; port
0x18008112f  lea     ecx, [rax+2]; af
0x180081132  call    INETADDR_SETSOCKADDR
0x180081137  lea     rax, [rsp+180h+dwAddressStringLength]
0x18008113c  xor     r8d, r8d; lpProtocolInfo
0x18008113f  lea     r9, [rbp+80h+szAddressString]; lpszAddressString
0x180081143  mov     qword ptr [rsp+180h+port], rax; lpdwAddressStringLength
0x180081148  mov     edx, 80h; dwAddressLength
0x18008114d  lea     rcx, [rsp+180h+a]; lpsaAddress
0x180081152  call    cs:__imp_WSAAddressToStringA
0x180081159  nop     dword ptr [rax+rax+00h]
0x18008115e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081165  cmp     rcx, r12
0x180081168  jz      short loc_18008118A
0x18008116a  test    [rcx+1Ch], esi
0x18008116d  jz      short loc_18008118A
0x18008116f  cmp     byte ptr [rcx+19h], 4
0x180081173  jb      short loc_18008118A
0x180081175  mov     rcx, [rcx+10h]
0x180081179  lea     r9, [rbp+80h+szAddressString]
0x18008117d  mov     edx, 0A9h
0x180081182  mov     r8, r14
0x180081185  call    WPP_SF_s
0x18008118a  cmp     dword ptr [rbx], 0
0x18008118d  jl      loc_18008125B
0x180081193  mov     [rsp+180h+var_128], 0
0x18008119b  mov     [rsp+180h+var_124], 0
0x1800811a3  call    IsRasQuerySharedAutoDialPresent
0x1800811a8  test    al, al
0x1800811aa  jz      loc_180081256
0x1800811b0  lea     rax, [rsp+180h+var_128]
0x1800811b5  xor     r8d, r8d; struct tagRASAUTODIALENTRYA *
0x1800811b8  lea     r9, [rsp+180h+var_124]; LPDWORD
0x1800811bd  mov     qword ptr [rsp+180h+port], rax; LPDWORD
0x1800811c2  xor     edx, edx; LPDWORD
0x1800811c4  lea     rcx, [rbp+80h+szAddressString]; LPCSTR
0x1800811c8  call    cs:__imp_RasGetAutodialAddressA
0x1800811cf  nop     dword ptr [rax+rax+00h]
0x1800811d4  cmp     eax, 25Bh
0x1800811d9  jnz     short loc_180081256
0x1800811db  cmp     cs:?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A, 0; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x1800811e2  jz      short loc_180081256
0x1800811e4  lea     rcx, aRasadhlpDll; "RASADHLP.DLL"
0x1800811eb  call    cs:__imp_LoadLibraryA
0x1800811f2  nop     dword ptr [rax+rax+00h]
0x1800811f7  mov     rbx, rax
0x1800811fa  test    rax, rax
0x1800811fd  jz      short loc_18008125B
0x1800811ff  lea     rdx, aWsattemptautod; "WSAttemptAutodialAddr"
0x180081206  mov     rcx, rax; hModule
0x180081209  call    cs:__imp_GetProcAddress
0x180081210  nop     dword ptr [rax+rax+00h]
0x180081215  test    rax, rax
0x180081218  jz      short loc_180081245
0x18008121a  mov     ecx, 2
0x18008121f  xorps   xmm0, xmm0
0x180081222  movups  [rsp+180h+var_120], xmm0
0x180081227  mov     word ptr [rsp+180h+var_120], cx
0x18008122c  mov     edx, 10h
0x180081231  mov     ecx, cs:?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x180081237  mov     dword ptr [rsp+180h+var_120+4], ecx
0x18008123b  lea     rcx, [rsp+180h+var_120]
0x180081240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081245  mov     rcx, rbx; hLibModule
0x180081248  call    cs:__imp_FreeLibrary
0x18008124f  nop     dword ptr [rax+rax+00h]
0x180081254  jmp     short loc_18008125B
0x180081256  call    ?NhDialSharedConnection@@YAKXZ; NhDialSharedConnection(void)
0x18008125b  mov     rcx, r13; lpCriticalSection
0x18008125e  call    cs:__imp_EnterCriticalSection
0x180081265  nop     dword ptr [rax+rax+00h]
0x18008126a  mov     rcx, cs:NatFileHandle; FileHandle
0x180081271  lea     rax, ?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x180081278  mov     [rsp+180h+OutputBufferLength], 8; OutputBufferLength
0x180081280  lea     r8, ?NatRoutingFailureCallbackRoutine@@YAXPEAXPEAU_IO_STATUS_BLOCK@@K@Z; ApcRoutine
0x180081287  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x18008128c  xor     r9d, r9d; ApcContext
0x18008128f  mov     [rsp+180h+InputBufferLength], 4; InputBufferLength
0x180081297  lea     rax, [rsp+180h+var_130]
0x18008129c  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x1800812a1  xor     edx, edx; Event
0x1800812a3  lea     rax, ?NatRoutingFailureIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK NatRoutingFailureIoStatus
0x1800812aa  mov     [rsp+180h+IoControlCode], 128004h; IoControlCode
0x1800812b2  mov     qword ptr [rsp+180h+port], rax; IoStatusBlock
0x1800812b7  mov     [rsp+180h+var_130], 0
0x1800812bf  call    cs:__imp_NtDeviceIoControlFile
0x1800812c6  nop     dword ptr [rax+rax+00h]
0x1800812cb  mov     rcx, r13; lpCriticalSection
0x1800812ce  call    cs:__imp_LeaveCriticalSection
0x1800812d5  nop     dword ptr [rax+rax+00h]
0x1800812da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812e1  cmp     rcx, r12
0x1800812e4  jz      short loc_180081302
0x1800812e6  test    [rcx+1Ch], esi
0x1800812e9  jz      short loc_180081302
0x1800812eb  cmp     byte ptr [rcx+19h], 6
0x1800812ef  jb      short loc_180081302
0x1800812f1  mov     edx, 0AAh
0x1800812f6  mov     rcx, [rcx+10h]
0x1800812fa  mov     r8, r14
0x1800812fd  call    WPP_SF_
0x180081302  mov     rcx, [rbp+80h+var_40]
0x180081306  xor     rcx, rsp; StackCookie
0x180081309  call    __security_check_cookie
0x18008130e  add     rsp, 158h
0x180081315  pop     r14
0x180081317  pop     r13
0x180081319  pop     r12
0x18008131b  pop     rsi
0x18008131c  pop     rbx
0x18008131d  pop     rbp
0x18008131e  retn
```
