# IpTlsDeleteInterface

- ea: `0x180042b38`
- end: `0x180042e99`
- name: `IpTlsDeleteInterface`
- size: `865`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800028d4`
- `0x180003ce4`
- `0x180019de0`
- `0x18003587c`
- `0x180042840`
- `0x1800601c4`

## callees

- `0x180004c54`
- `0x18000a6f4`
- `0x18000d7b0`
- `0x180013570`
- `0x180030d24`
- `0x18003ada0`
- `0x180040dd0`
- `0x180042b38`
- `0x18004b630`
- `0x180061694`
- `0x180062f50`
- `0x1800681e8`
- `0x18006909c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042ba4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d7c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d7c`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042d91`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042d91`
- `FirewallAPI!FWIndicatePortInUse` at `0x180042dc8`
- `FirewallAPI!FWIndicatePortInUse` at `0x180042dc8`

## string_xrefs

- `0x180042c86`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042cfe`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042e21`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042e45`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042b54`: `IpTlsDeleteInterface`
- `0x180042e69`: `Done IpTlsDeleteInterface`

## pseudocode

```c
__int64 __fastcall IpTlsDeleteInterface(__int64 *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // r8
  __int64 *v4; // rcx
  __int64 **v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rcx
  __int64 *v9; // rbx
  _QWORD *v10; // r8
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int i; // esi
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v23; // [rsp+20h] [rbp-68h]
  __int64 v24; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v25[16]; // [rsp+38h] [rbp-50h] BYREF
  __int64 *v26; // [rsp+48h] [rbp-40h]
  __int64 v27; // [rsp+50h] [rbp-38h]

  EventWrite0(0x10000000, L"IpTlsDeleteInterface");
  IpTlsAcquireLock(g_IpTlsDeletedInterfaceListLock);
  v2 = (_QWORD *)qword_1800CC3A8;
  if ( *(__int64 **)qword_1800CC3A8 != &g_IpTlsDeletedInterfaceList
    || (a1[2] = (__int64)&g_IpTlsDeletedInterfaceList,
        a1[3] = (__int64)v2,
        *v2 = a1 + 2,
        qword_1800CC3A8 = (__int64)(a1 + 2),
        ReleaseMutex(g_IpTlsDeletedInterfaceListLock),
        v4 = (__int64 *)*a1,
        *(__int64 **)(*a1 + 8) != a1)
    || (v5 = (__int64 **)a1[1], *v5 != a1) )
  {
LABEL_38:
    __fastfail(3u);
  }
  *v5 = v4;
  v4[1] = (__int64)v5;
  *((_BYTE *)a1 + 1032) |= 2u;
  v6 = a1[145];
  v7 = (_QWORD *)a1[147];
  a1[147] = 0;
  if ( v6 && IpHlpSvcEtwEnabled == 1 && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
  {
    v24 = v6;
    v27 = 8;
    v26 = &v24;
    McGenEventWrite_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_CANARY,
      v3,
      2,
      v25);
  }
  while ( v7 )
  {
    v8 = v7 - 6;
    v7 = (_QWORD *)*v7;
    FREE(v8);
    _InterlockedDecrement((volatile signed __int32 *)a1 + 297);
  }
  v9 = a1 + 143;
  while ( 1 )
  {
    v10 = (_QWORD *)*v9;
    if ( (__int64 *)*v9 == v9 )
      break;
    if ( (__int64 *)v10[1] != v9 )
      goto LABEL_38;
    v11 = *v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 )
      goto LABEL_38;
    *v9 = v11;
    *(_QWORD *)(v11 + 8) = v9;
    LODWORD(v23) = 1366;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      v10 - 8,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
      v23);
    v12 = (_QWORD *)*v9;
    if ( *(__int64 **)(*v9 + 8) != v9 )
      goto LABEL_38;
    v13 = *v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_38;
    *v9 = v13;
    *(_QWORD *)(v13 + 8) = v9;
    IpTlsDereferenceBufferEx(v12 - 8);
  }
  v14 = g_IpTlsNumReceiveQueues;
  for ( i = 0; i < v14; ++i )
  {
    v16 = a1[146];
    if ( *(_QWORD *)(v16 + 16LL * i) )
    {
      do
      {
        v17 = *(_QWORD **)(v16 + 16LL * i);
        LODWORD(v23) = 1376;
        v18 = v17 - 6;
        *(_QWORD *)(v16 + 16LL * i) = *v17;
        EventWrite0(
          0x20000000,
          L"(Dereference IPTLS Buffer(%p)%S:%d",
          v17 - 6,
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
          v23);
        IpTlsDereferenceBufferEx(v18);
        v16 = a1[146];
      }
      while ( *(_QWORD *)(v16 + 16LL * i) );
      v14 = g_IpTlsNumReceiveQueues;
    }
  }
  if ( a1[134] != -1 && (a1[135] & 1) == 0 )
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)a1 + 270) == 1 )
      SetEvent((HANDLE)a1[136]);
    CancelIoEx((HANDLE)a1[134], 0);
    *((_BYTE *)a1 + 1032) |= 0x20u;
  }
  if ( !*((_DWORD *)a1 + 253) )
    SplTunMgrTunnelDisconnect();
  FWIndicatePortInUse(3 - (unsigned int)(*((_DWORD *)a1 + 253) != 0), *((unsigned __int16 *)a1 + 504), 0);
  v19 = a1[138];
  if ( v19 != -1 )
  {
    if ( *((_DWORD *)a1 + 253) )
      StopServer(v19);
    else
      IpTlsShutdownClient();
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DELETED,
      a1 + 7,
      0);
  LODWORD(v23) = 1417;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference IPTLS interface %S:%d",
    a1 + 7,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
    v23);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v21,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE,
      (_DWORD)a1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
      137);
  LOBYTE(v20) = 1;
  IpTlsDereferenceInterfaceEx(a1, v20);
  return EventWrite0(0x10000000, L"Done IpTlsDeleteInterface");
}

```

## disassembly

```asm
0x180042b38  push    rbx
0x180042b3a  push    rsi
0x180042b3b  push    rdi
0x180042b3c  push    r14
0x180042b3e  sub     rsp, 68h
0x180042b42  mov     rax, cs:__security_cookie
0x180042b49  xor     rax, rsp
0x180042b4c  mov     [rsp+88h+var_30], rax
0x180042b51  mov     rdi, rcx
0x180042b54  lea     rdx, aIptlsdeleteint; "IpTlsDeleteInterface"
0x180042b5b  mov     ecx, 10000000h
0x180042b60  call    EventWrite0
0x180042b65  mov     rcx, cs:g_IpTlsDeletedInterfaceListLock
0x180042b6c  call    IpTlsAcquireLock
0x180042b71  mov     rcx, cs:qword_1800CC3A8
0x180042b78  lea     rdx, g_IpTlsDeletedInterfaceList
0x180042b7f  cmp     [rcx], rdx
0x180042b82  jnz     loc_180042E92
0x180042b88  lea     rax, [rdi+10h]
0x180042b8c  mov     [rax], rdx
0x180042b8f  mov     [rax+8], rcx
0x180042b93  mov     [rcx], rax
0x180042b96  mov     rcx, cs:g_IpTlsDeletedInterfaceListLock; hMutex
0x180042b9d  mov     cs:qword_1800CC3A8, rax
0x180042ba4  call    cs:__imp_ReleaseMutex
0x180042bab  nop     dword ptr [rax+rax+00h]
0x180042bb0  mov     rcx, [rdi]
0x180042bb3  cmp     [rcx+8], rdi
0x180042bb7  jnz     loc_180042E92
0x180042bbd  mov     rax, [rdi+8]
0x180042bc1  cmp     [rax], rdi
0x180042bc4  jnz     loc_180042E92
0x180042bca  mov     [rax], rcx
0x180042bcd  mov     r9d, 2
0x180042bd3  mov     [rcx+8], rax
0x180042bd7  or      [rdi+408h], r9b
0x180042bde  mov     rax, [rdi+488h]
0x180042be5  mov     rbx, [rdi+498h]
0x180042bec  mov     qword ptr [rdi+498h], 0
0x180042bf7  test    rax, rax
0x180042bfa  jz      short loc_180042C58
0x180042bfc  cmp     cs:IpHlpSvcEtwEnabled, 1
0x180042c03  jnz     short loc_180042C58
0x180042c05  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180042c0c  jz      short loc_180042C58
0x180042c0e  mov     [rsp+88h+var_58], rax
0x180042c13  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CANARY
0x180042c1a  lea     rax, [rsp+88h+var_58]
0x180042c1f  mov     [rsp+88h+var_38], 8
0x180042c28  mov     [rsp+88h+var_40], rax
0x180042c2d  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180042c34  lea     rax, [rsp+88h+var_50]
0x180042c39  mov     [rsp+88h+var_68], rax
0x180042c3e  call    McGenEventWrite_EventWriteTransfer
0x180042c43  jmp     short loc_180042C58
0x180042c45  lea     rcx, [rbx-30h]
0x180042c49  mov     rbx, [rbx]
0x180042c4c  call    FREE
0x180042c51  lock dec dword ptr [rdi+4A4h]
0x180042c58  test    rbx, rbx
0x180042c5b  jnz     short loc_180042C45
0x180042c5d  lea     rbx, [rdi+478h]
0x180042c64  mov     r8, [rbx]
0x180042c67  cmp     r8, rbx
0x180042c6a  jz      short loc_180042CDA
0x180042c6c  cmp     [r8+8], rbx
0x180042c70  jnz     loc_180042E92
0x180042c76  mov     rax, [r8]
0x180042c79  cmp     [rax+8], r8
0x180042c7d  jnz     loc_180042E92
0x180042c83  mov     [rbx], rax
0x180042c86  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042c8d  add     r8, 0FFFFFFFFFFFFFFC0h
0x180042c91  mov     [rax+8], rbx
0x180042c95  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180042c9c  mov     dword ptr [rsp+88h+var_68], 556h
0x180042ca4  mov     ecx, 20000000h
0x180042ca9  call    EventWrite0
0x180042cae  mov     rcx, [rbx]
0x180042cb1  cmp     [rcx+8], rbx
0x180042cb5  jnz     loc_180042E92
0x180042cbb  mov     rax, [rcx]
0x180042cbe  cmp     [rax+8], rcx
0x180042cc2  jnz     loc_180042E92
0x180042cc8  mov     [rbx], rax
0x180042ccb  add     rcx, 0FFFFFFFFFFFFFFC0h
0x180042ccf  mov     [rax+8], rbx
0x180042cd3  call    IpTlsDereferenceBufferEx
0x180042cd8  jmp     short loc_180042C64
0x180042cda  mov     eax, cs:g_IpTlsNumReceiveQueues
0x180042ce0  xor     esi, esi
0x180042ce2  test    eax, eax
0x180042ce4  jz      short loc_180042D4E
0x180042ce6  mov     rdx, [rdi+490h]
0x180042ced  mov     r14d, esi
0x180042cf0  add     r14, r14
0x180042cf3  cmp     qword ptr [rdx+r14*8], 0
0x180042cf8  jz      short loc_180042D48
0x180042cfa  mov     rcx, [rdx+r14*8]
0x180042cfe  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042d05  mov     dword ptr [rsp+88h+var_68], 560h
0x180042d0d  mov     rax, [rcx]
0x180042d10  lea     rbx, [rcx-30h]
0x180042d14  mov     [rdx+r14*8], rax
0x180042d18  mov     r8, rbx
0x180042d1b  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180042d22  mov     ecx, 20000000h
0x180042d27  call    EventWrite0
0x180042d2c  mov     rcx, rbx
0x180042d2f  call    IpTlsDereferenceBufferEx
0x180042d34  mov     rdx, [rdi+490h]
0x180042d3b  cmp     qword ptr [rdx+r14*8], 0
0x180042d40  jnz     short loc_180042CFA
0x180042d42  mov     eax, cs:g_IpTlsNumReceiveQueues
0x180042d48  inc     esi
0x180042d4a  cmp     esi, eax
0x180042d4c  jb      short loc_180042CE6
0x180042d4e  cmp     qword ptr [rdi+430h], 0FFFFFFFFFFFFFFFFh
0x180042d56  mov     bl, 20h ; ' '
0x180042d58  jz      short loc_180042DA3
0x180042d5a  test    byte ptr [rdi+438h], 1
0x180042d61  jnz     short loc_180042DA3
0x180042d63  or      eax, 0FFFFFFFFh
0x180042d66  lock xadd [rdi+438h], eax
0x180042d6e  dec     eax
0x180042d70  cmp     eax, 1
0x180042d73  jnz     short loc_180042D88
0x180042d75  mov     rcx, [rdi+440h]; hEvent
0x180042d7c  call    cs:__imp_SetEvent
0x180042d83  nop     dword ptr [rax+rax+00h]
0x180042d88  mov     rcx, [rdi+430h]; hFile
0x180042d8f  xor     edx, edx; lpOverlapped
0x180042d91  call    cs:__imp_CancelIoEx
0x180042d98  nop     dword ptr [rax+rax+00h]
0x180042d9d  or      [rdi+408h], bl
0x180042da3  cmp     dword ptr [rdi+3F4h], 0
0x180042daa  jnz     short loc_180042DB1
0x180042dac  call    SplTunMgrTunnelDisconnect
0x180042db1  mov     eax, [rdi+3F4h]
0x180042db7  movzx   edx, word ptr [rdi+3F0h]
0x180042dbe  neg     eax
0x180042dc0  sbb     ecx, ecx
0x180042dc2  xor     r8d, r8d
0x180042dc5  add     ecx, 3
0x180042dc8  call    cs:__imp_FWIndicatePortInUse
0x180042dcf  nop     dword ptr [rax+rax+00h]
0x180042dd4  mov     rcx, [rdi+450h]
0x180042ddb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042ddf  jz      short loc_180042DF6
0x180042de1  cmp     dword ptr [rdi+3F4h], 0
0x180042de8  jnz     short loc_180042DF1
0x180042dea  call    IpTlsShutdownClient
0x180042def  jmp     short loc_180042DF6
0x180042df1  call    StopServer
0x180042df6  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, bl
0x180042dfc  jz      short loc_180042E18
0x180042dfe  lea     r8, [rdi+38h]
0x180042e02  xor     r9d, r9d
0x180042e05  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DELETED
0x180042e0c  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180042e13  call    McTemplateU0zq_EventWriteTransfer
0x180042e18  mov     esi, 589h
0x180042e1d  lea     r8, [rdi+38h]
0x180042e21  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042e28  mov     dword ptr [rsp+88h+var_68], esi
0x180042e2c  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x180042e33  mov     ecx, 20000000h
0x180042e38  call    EventWrite0
0x180042e3d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, bl
0x180042e43  jz      short loc_180042E5F
0x180042e45  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042e4c  mov     dword ptr [rsp+88h+var_68], esi
0x180042e50  mov     r8, rdi
0x180042e53  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180042e5a  call    McTemplateU0psq_EventWriteTransfer
0x180042e5f  mov     dl, 1
0x180042e61  mov     rcx, rdi
0x180042e64  call    IpTlsDereferenceInterfaceEx
0x180042e69  lea     rdx, aDoneIptlsdelet; "Done IpTlsDeleteInterface"
0x180042e70  mov     ecx, 10000000h
0x180042e75  call    EventWrite0
0x180042e7a  mov     rcx, [rsp+88h+var_30]
0x180042e7f  xor     rcx, rsp; StackCookie
0x180042e82  call    __security_check_cookie
0x180042e87  add     rsp, 68h
0x180042e8b  pop     r14
0x180042e8d  pop     rdi
0x180042e8e  pop     rsi
0x180042e8f  pop     rbx
0x180042e90  retn
0x180042e92  mov     ecx, 3
0x180042e97  int     29h; Win8: RtlFailFast(ecx)
```
