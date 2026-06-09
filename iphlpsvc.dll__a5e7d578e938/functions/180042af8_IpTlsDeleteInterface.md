# IpTlsDeleteInterface

- ea: `0x180042af8`
- end: `0x180042e59`
- name: `IpTlsDeleteInterface`
- size: `865`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800028e4`
- `0x180003cf4`
- `0x180019df0`
- `0x18003588c`
- `0x180042800`
- `0x1800601e4`

## callees

- `0x180004c64`
- `0x18000a704`
- `0x18000d7c0`
- `0x180013580`
- `0x180030d34`
- `0x18003adb0`
- `0x180040d90`
- `0x180042af8`
- `0x18004b5f0`
- `0x1800616b4`
- `0x180062f70`
- `0x180068208`
- `0x1800690bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042b64`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d3c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d3c`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042d51`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042d51`
- `FirewallAPI!FWIndicatePortInUse` at `0x180042d88`
- `FirewallAPI!FWIndicatePortInUse` at `0x180042d88`

## string_xrefs

- `0x180042c46`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042cbe`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042de1`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042e05`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180042b14`: `IpTlsDeleteInterface`
- `0x180042e29`: `Done IpTlsDeleteInterface`

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
0x180042af8  push    rbx
0x180042afa  push    rsi
0x180042afb  push    rdi
0x180042afc  push    r14
0x180042afe  sub     rsp, 68h
0x180042b02  mov     rax, cs:__security_cookie
0x180042b09  xor     rax, rsp
0x180042b0c  mov     [rsp+88h+var_30], rax
0x180042b11  mov     rdi, rcx
0x180042b14  lea     rdx, aIptlsdeleteint; "IpTlsDeleteInterface"
0x180042b1b  mov     ecx, 10000000h
0x180042b20  call    EventWrite0
0x180042b25  mov     rcx, cs:g_IpTlsDeletedInterfaceListLock
0x180042b2c  call    IpTlsAcquireLock
0x180042b31  mov     rcx, cs:qword_1800CC3A8
0x180042b38  lea     rdx, g_IpTlsDeletedInterfaceList
0x180042b3f  cmp     [rcx], rdx
0x180042b42  jnz     loc_180042E52
0x180042b48  lea     rax, [rdi+10h]
0x180042b4c  mov     [rax], rdx
0x180042b4f  mov     [rax+8], rcx
0x180042b53  mov     [rcx], rax
0x180042b56  mov     rcx, cs:g_IpTlsDeletedInterfaceListLock; hMutex
0x180042b5d  mov     cs:qword_1800CC3A8, rax
0x180042b64  call    cs:__imp_ReleaseMutex
0x180042b6b  nop     dword ptr [rax+rax+00h]
0x180042b70  mov     rcx, [rdi]
0x180042b73  cmp     [rcx+8], rdi
0x180042b77  jnz     loc_180042E52
0x180042b7d  mov     rax, [rdi+8]
0x180042b81  cmp     [rax], rdi
0x180042b84  jnz     loc_180042E52
0x180042b8a  mov     [rax], rcx
0x180042b8d  mov     r9d, 2
0x180042b93  mov     [rcx+8], rax
0x180042b97  or      [rdi+408h], r9b
0x180042b9e  mov     rax, [rdi+488h]
0x180042ba5  mov     rbx, [rdi+498h]
0x180042bac  mov     qword ptr [rdi+498h], 0
0x180042bb7  test    rax, rax
0x180042bba  jz      short loc_180042C18
0x180042bbc  cmp     cs:IpHlpSvcEtwEnabled, 1
0x180042bc3  jnz     short loc_180042C18
0x180042bc5  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180042bcc  jz      short loc_180042C18
0x180042bce  mov     [rsp+88h+var_58], rax
0x180042bd3  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CANARY
0x180042bda  lea     rax, [rsp+88h+var_58]
0x180042bdf  mov     [rsp+88h+var_38], 8
0x180042be8  mov     [rsp+88h+var_40], rax
0x180042bed  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180042bf4  lea     rax, [rsp+88h+var_50]
0x180042bf9  mov     [rsp+88h+var_68], rax
0x180042bfe  call    McGenEventWrite_EventWriteTransfer
0x180042c03  jmp     short loc_180042C18
0x180042c05  lea     rcx, [rbx-30h]
0x180042c09  mov     rbx, [rbx]
0x180042c0c  call    FREE
0x180042c11  lock dec dword ptr [rdi+4A4h]
0x180042c18  test    rbx, rbx
0x180042c1b  jnz     short loc_180042C05
0x180042c1d  lea     rbx, [rdi+478h]
0x180042c24  mov     r8, [rbx]
0x180042c27  cmp     r8, rbx
0x180042c2a  jz      short loc_180042C9A
0x180042c2c  cmp     [r8+8], rbx
0x180042c30  jnz     loc_180042E52
0x180042c36  mov     rax, [r8]
0x180042c39  cmp     [rax+8], r8
0x180042c3d  jnz     loc_180042E52
0x180042c43  mov     [rbx], rax
0x180042c46  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042c4d  add     r8, 0FFFFFFFFFFFFFFC0h
0x180042c51  mov     [rax+8], rbx
0x180042c55  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180042c5c  mov     dword ptr [rsp+88h+var_68], 556h
0x180042c64  mov     ecx, 20000000h
0x180042c69  call    EventWrite0
0x180042c6e  mov     rcx, [rbx]
0x180042c71  cmp     [rcx+8], rbx
0x180042c75  jnz     loc_180042E52
0x180042c7b  mov     rax, [rcx]
0x180042c7e  cmp     [rax+8], rcx
0x180042c82  jnz     loc_180042E52
0x180042c88  mov     [rbx], rax
0x180042c8b  add     rcx, 0FFFFFFFFFFFFFFC0h
0x180042c8f  mov     [rax+8], rbx
0x180042c93  call    IpTlsDereferenceBufferEx
0x180042c98  jmp     short loc_180042C24
0x180042c9a  mov     eax, cs:g_IpTlsNumReceiveQueues
0x180042ca0  xor     esi, esi
0x180042ca2  test    eax, eax
0x180042ca4  jz      short loc_180042D0E
0x180042ca6  mov     rdx, [rdi+490h]
0x180042cad  mov     r14d, esi
0x180042cb0  add     r14, r14
0x180042cb3  cmp     qword ptr [rdx+r14*8], 0
0x180042cb8  jz      short loc_180042D08
0x180042cba  mov     rcx, [rdx+r14*8]
0x180042cbe  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042cc5  mov     dword ptr [rsp+88h+var_68], 560h
0x180042ccd  mov     rax, [rcx]
0x180042cd0  lea     rbx, [rcx-30h]
0x180042cd4  mov     [rdx+r14*8], rax
0x180042cd8  mov     r8, rbx
0x180042cdb  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180042ce2  mov     ecx, 20000000h
0x180042ce7  call    EventWrite0
0x180042cec  mov     rcx, rbx
0x180042cef  call    IpTlsDereferenceBufferEx
0x180042cf4  mov     rdx, [rdi+490h]
0x180042cfb  cmp     qword ptr [rdx+r14*8], 0
0x180042d00  jnz     short loc_180042CBA
0x180042d02  mov     eax, cs:g_IpTlsNumReceiveQueues
0x180042d08  inc     esi
0x180042d0a  cmp     esi, eax
0x180042d0c  jb      short loc_180042CA6
0x180042d0e  cmp     qword ptr [rdi+430h], 0FFFFFFFFFFFFFFFFh
0x180042d16  mov     bl, 20h ; ' '
0x180042d18  jz      short loc_180042D63
0x180042d1a  test    byte ptr [rdi+438h], 1
0x180042d21  jnz     short loc_180042D63
0x180042d23  or      eax, 0FFFFFFFFh
0x180042d26  lock xadd [rdi+438h], eax
0x180042d2e  dec     eax
0x180042d30  cmp     eax, 1
0x180042d33  jnz     short loc_180042D48
0x180042d35  mov     rcx, [rdi+440h]; hEvent
0x180042d3c  call    cs:__imp_SetEvent
0x180042d43  nop     dword ptr [rax+rax+00h]
0x180042d48  mov     rcx, [rdi+430h]; hFile
0x180042d4f  xor     edx, edx; lpOverlapped
0x180042d51  call    cs:__imp_CancelIoEx
0x180042d58  nop     dword ptr [rax+rax+00h]
0x180042d5d  or      [rdi+408h], bl
0x180042d63  cmp     dword ptr [rdi+3F4h], 0
0x180042d6a  jnz     short loc_180042D71
0x180042d6c  call    SplTunMgrTunnelDisconnect
0x180042d71  mov     eax, [rdi+3F4h]
0x180042d77  movzx   edx, word ptr [rdi+3F0h]
0x180042d7e  neg     eax
0x180042d80  sbb     ecx, ecx
0x180042d82  xor     r8d, r8d
0x180042d85  add     ecx, 3
0x180042d88  call    cs:__imp_FWIndicatePortInUse
0x180042d8f  nop     dword ptr [rax+rax+00h]
0x180042d94  mov     rcx, [rdi+450h]
0x180042d9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042d9f  jz      short loc_180042DB6
0x180042da1  cmp     dword ptr [rdi+3F4h], 0
0x180042da8  jnz     short loc_180042DB1
0x180042daa  call    IpTlsShutdownClient
0x180042daf  jmp     short loc_180042DB6
0x180042db1  call    StopServer
0x180042db6  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, bl
0x180042dbc  jz      short loc_180042DD8
0x180042dbe  lea     r8, [rdi+38h]
0x180042dc2  xor     r9d, r9d
0x180042dc5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DELETED
0x180042dcc  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180042dd3  call    McTemplateU0zq_EventWriteTransfer
0x180042dd8  mov     esi, 589h
0x180042ddd  lea     r8, [rdi+38h]
0x180042de1  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042de8  mov     dword ptr [rsp+88h+var_68], esi
0x180042dec  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x180042df3  mov     ecx, 20000000h
0x180042df8  call    EventWrite0
0x180042dfd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, bl
0x180042e03  jz      short loc_180042E1F
0x180042e05  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180042e0c  mov     dword ptr [rsp+88h+var_68], esi
0x180042e10  mov     r8, rdi
0x180042e13  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180042e1a  call    McTemplateU0psq_EventWriteTransfer
0x180042e1f  mov     dl, 1
0x180042e21  mov     rcx, rdi
0x180042e24  call    IpTlsDereferenceInterfaceEx
0x180042e29  lea     rdx, aDoneIptlsdelet; "Done IpTlsDeleteInterface"
0x180042e30  mov     ecx, 10000000h
0x180042e35  call    EventWrite0
0x180042e3a  mov     rcx, [rsp+88h+var_30]
0x180042e3f  xor     rcx, rsp; StackCookie
0x180042e42  call    __security_check_cookie
0x180042e47  add     rsp, 68h
0x180042e4b  pop     r14
0x180042e4d  pop     rdi
0x180042e4e  pop     rsi
0x180042e4f  pop     rbx
0x180042e50  retn
0x180042e52  mov     ecx, 3
0x180042e57  int     29h; Win8: RtlFailFast(ecx)
```
