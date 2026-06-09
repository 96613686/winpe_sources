# NatRoutingFailureCallbackRoutine(void *,_IO_STATUS_BLOCK *,ulong)

- ea: `0x18007ae40`
- end: `0x18007b15d`
- name: `?NatRoutingFailureCallbackRoutine@@YAXPEAXPEAU_IO_STATUS_BLOCK@@K@Z`
- size: `797`
- prototype: `void __stdcall(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000f250`
- `0x1800312e0`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18004f558`
- `0x180052410`
- `0x18007ae40`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b0ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b0ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aef0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007af2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aef0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007af2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b065`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b065`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b09e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b09e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007b04d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007b04d`
- `ntdll!NtDeviceIoControlFile` at `0x18007b109`
- `ntdll!NtDeviceIoControlFile` at `0x18007b109`
- `WS2_32!WSAAddressToStringA` at `0x18007afc0`
- `WS2_32!WSAAddressToStringA` at `0x18007afc0`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetAutodialAddressA` at `0x18007b030`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetAutodialAddressA` at `0x18007b030`

## string_xrefs

- `0x18007b046`: `RASADHLP.DLL`
- `0x18007b05b`: `WSAttemptAutodialAddr`

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
0x18007ae40  push    rbp
0x18007ae42  push    rbx
0x18007ae43  push    rsi
0x18007ae44  push    r12
0x18007ae46  push    r13
0x18007ae48  push    r14
0x18007ae4a  lea     rbp, [rsp-58h]
0x18007ae4f  sub     rsp, 158h
0x18007ae56  mov     rax, cs:__security_cookie
0x18007ae5d  xor     rax, rsp
0x18007ae60  mov     [rbp+80h+var_40], rax
0x18007ae64  mov     rbx, rdx
0x18007ae67  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae6e  lea     r12, WPP_GLOBAL_Control
0x18007ae75  lea     r14, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007ae7c  mov     esi, 200h
0x18007ae81  cmp     rcx, r12
0x18007ae84  jz      short loc_18007AEA2
0x18007ae86  test    [rcx+1Ch], esi
0x18007ae89  jz      short loc_18007AEA2
0x18007ae8b  cmp     byte ptr [rcx+19h], 6
0x18007ae8f  jb      short loc_18007AEA2
0x18007ae91  mov     rcx, [rcx+10h]
0x18007ae95  mov     edx, 0A6h
0x18007ae9a  mov     r8, r14
0x18007ae9d  call    WPP_SF_
0x18007aea2  xor     edx, edx; Val
0x18007aea4  lea     rcx, [rbp+80h+szAddressString]; void *
0x18007aea8  lea     r8d, [rdx+41h]; Size
0x18007aeac  call    memset_0
0x18007aeb1  xor     edx, edx; Val
0x18007aeb3  mov     [rsp+180h+dwAddressStringLength], 41h ; 'A'
0x18007aebb  mov     r8d, 80h; Size
0x18007aec1  lea     rcx, [rsp+180h+a]; void *
0x18007aec6  call    memset_0
0x18007aecb  lea     r13, NatInterfaceLock
0x18007aed2  mov     [rsp+180h+var_130], 0
0x18007aeda  mov     rcx, r13; lpCriticalSection
0x18007aedd  call    cs:__imp_EnterCriticalSection
0x18007aee3  cmp     cs:NatConnectionNotifyEvent, 0
0x18007aeeb  mov     rcx, r13; lpCriticalSection
0x18007aeee  jnz     short loc_18007AF2F
0x18007aef0  call    cs:__imp_LeaveCriticalSection
0x18007aef6  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18007aefd  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18007af02  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af09  cmp     rcx, r12
0x18007af0c  jz      loc_18007B140
0x18007af12  test    [rcx+1Ch], esi
0x18007af15  jz      loc_18007B140
0x18007af1b  cmp     byte ptr [rcx+19h], 6
0x18007af1f  jb      loc_18007B140
0x18007af25  mov     edx, 0A7h
0x18007af2a  jmp     loc_18007B134
0x18007af2f  call    cs:__imp_LeaveCriticalSection
0x18007af35  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18007af3c  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18007af41  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18007af48  test    al, al
0x18007af4a  jnz     short loc_18007AF7E
0x18007af4c  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18007af51  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af58  cmp     rcx, r12
0x18007af5b  jz      loc_18007B140
0x18007af61  test    [rcx+1Ch], esi
0x18007af64  jz      loc_18007B140
0x18007af6a  cmp     byte ptr [rcx+19h], 6
0x18007af6e  jb      loc_18007B140
0x18007af74  mov     edx, 0A8h
0x18007af79  jmp     loc_18007B134
0x18007af7e  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18007af83  mov     r9d, dword ptr cs:scopeid_unspecified; scope
0x18007af8a  lea     r8, ?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; addr
0x18007af91  xor     eax, eax
0x18007af93  lea     rdx, [rsp+180h+a]; a
0x18007af98  mov     [rsp+180h+port], ax; port
0x18007af9d  lea     ecx, [rax+2]; af
0x18007afa0  call    INETADDR_SETSOCKADDR
0x18007afa5  lea     rax, [rsp+180h+dwAddressStringLength]
0x18007afaa  xor     r8d, r8d; lpProtocolInfo
0x18007afad  lea     r9, [rbp+80h+szAddressString]; lpszAddressString
0x18007afb1  mov     qword ptr [rsp+180h+port], rax; lpdwAddressStringLength
0x18007afb6  mov     edx, 80h; dwAddressLength
0x18007afbb  lea     rcx, [rsp+180h+a]; lpsaAddress
0x18007afc0  call    cs:__imp_WSAAddressToStringA
0x18007afc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007afcd  cmp     rcx, r12
0x18007afd0  jz      short loc_18007AFF2
0x18007afd2  test    [rcx+1Ch], esi
0x18007afd5  jz      short loc_18007AFF2
0x18007afd7  cmp     byte ptr [rcx+19h], 4
0x18007afdb  jb      short loc_18007AFF2
0x18007afdd  mov     rcx, [rcx+10h]
0x18007afe1  lea     r9, [rbp+80h+szAddressString]
0x18007afe5  mov     edx, 0A9h
0x18007afea  mov     r8, r14
0x18007afed  call    WPP_SF_s
0x18007aff2  cmp     dword ptr [rbx], 0
0x18007aff5  jl      loc_18007B0AB
0x18007affb  mov     [rsp+180h+var_128], 0
0x18007b003  mov     [rsp+180h+var_124], 0
0x18007b00b  call    IsRasQuerySharedAutoDialPresent
0x18007b010  test    al, al
0x18007b012  jz      loc_18007B0A6
0x18007b018  lea     rax, [rsp+180h+var_128]
0x18007b01d  xor     r8d, r8d; struct tagRASAUTODIALENTRYA *
0x18007b020  lea     r9, [rsp+180h+var_124]; LPDWORD
0x18007b025  mov     qword ptr [rsp+180h+port], rax; LPDWORD
0x18007b02a  xor     edx, edx; LPDWORD
0x18007b02c  lea     rcx, [rbp+80h+szAddressString]; LPCSTR
0x18007b030  call    cs:__imp_RasGetAutodialAddressA
0x18007b036  cmp     eax, 25Bh
0x18007b03b  jnz     short loc_18007B0A6
0x18007b03d  cmp     cs:?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A, 0; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x18007b044  jz      short loc_18007B0A6
0x18007b046  lea     rcx, aRasadhlpDll; "RASADHLP.DLL"
0x18007b04d  call    cs:__imp_LoadLibraryA
0x18007b053  mov     rbx, rax
0x18007b056  test    rax, rax
0x18007b059  jz      short loc_18007B0AB
0x18007b05b  lea     rdx, aWsattemptautod; "WSAttemptAutodialAddr"
0x18007b062  mov     rcx, rax; hModule
0x18007b065  call    cs:__imp_GetProcAddress
0x18007b06b  test    rax, rax
0x18007b06e  jz      short loc_18007B09B
0x18007b070  mov     ecx, 2
0x18007b075  xorps   xmm0, xmm0
0x18007b078  movups  [rsp+180h+var_120], xmm0
0x18007b07d  mov     word ptr [rsp+180h+var_120], cx
0x18007b082  mov     edx, 10h
0x18007b087  mov     ecx, cs:?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x18007b08d  mov     dword ptr [rsp+180h+var_120+4], ecx
0x18007b091  lea     rcx, [rsp+180h+var_120]
0x18007b096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b09b  mov     rcx, rbx; hLibModule
0x18007b09e  call    cs:__imp_FreeLibrary
0x18007b0a4  jmp     short loc_18007B0AB
0x18007b0a6  call    ?NhDialSharedConnection@@YAKXZ; NhDialSharedConnection(void)
0x18007b0ab  mov     rcx, r13; lpCriticalSection
0x18007b0ae  call    cs:__imp_EnterCriticalSection
0x18007b0b4  mov     rcx, cs:NatFileHandle; FileHandle
0x18007b0bb  lea     rax, ?NatpRoutingFailureNotification@@3U_IP_NAT_ROUTING_FAILURE_NOTIFICATION@@A; _IP_NAT_ROUTING_FAILURE_NOTIFICATION NatpRoutingFailureNotification
0x18007b0c2  mov     [rsp+180h+OutputBufferLength], 8; OutputBufferLength
0x18007b0ca  lea     r8, ?NatRoutingFailureCallbackRoutine@@YAXPEAXPEAU_IO_STATUS_BLOCK@@K@Z; ApcRoutine
0x18007b0d1  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x18007b0d6  xor     r9d, r9d; ApcContext
0x18007b0d9  mov     [rsp+180h+InputBufferLength], 4; InputBufferLength
0x18007b0e1  lea     rax, [rsp+180h+var_130]
0x18007b0e6  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x18007b0eb  xor     edx, edx; Event
0x18007b0ed  lea     rax, ?NatRoutingFailureIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK NatRoutingFailureIoStatus
0x18007b0f4  mov     [rsp+180h+IoControlCode], 128004h; IoControlCode
0x18007b0fc  mov     qword ptr [rsp+180h+port], rax; IoStatusBlock
0x18007b101  mov     [rsp+180h+var_130], 0
0x18007b109  call    cs:__imp_NtDeviceIoControlFile
0x18007b10f  mov     rcx, r13; lpCriticalSection
0x18007b112  call    cs:__imp_LeaveCriticalSection
0x18007b118  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b11f  cmp     rcx, r12
0x18007b122  jz      short loc_18007B140
0x18007b124  test    [rcx+1Ch], esi
0x18007b127  jz      short loc_18007B140
0x18007b129  cmp     byte ptr [rcx+19h], 6
0x18007b12d  jb      short loc_18007B140
0x18007b12f  mov     edx, 0AAh
0x18007b134  mov     rcx, [rcx+10h]
0x18007b138  mov     r8, r14
0x18007b13b  call    WPP_SF_
0x18007b140  mov     rcx, [rbp+80h+var_40]
0x18007b144  xor     rcx, rsp; StackCookie
0x18007b147  call    __security_check_cookie
0x18007b14c  add     rsp, 158h
0x18007b153  pop     r14
0x18007b155  pop     r13
0x18007b157  pop     r12
0x18007b159  pop     rsi
0x18007b15a  pop     rbx
0x18007b15b  pop     rbp
0x18007b15c  retn
```
