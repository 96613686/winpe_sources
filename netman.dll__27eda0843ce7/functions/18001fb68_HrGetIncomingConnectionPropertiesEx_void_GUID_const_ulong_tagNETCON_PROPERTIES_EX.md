# HrGetIncomingConnectionPropertiesEx(void *,_GUID const *,ulong,tagNETCON_PROPERTIES_EX * *)

- ea: `0x18001fb68`
- end: `0x18001fd39`
- name: `?HrGetIncomingConnectionPropertiesEx@@YAJPEAXPEBU_GUID@@KPEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, unsigned int, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fdf0`

## callees

- `0x180001710`
- `0x180008168`
- `0x180019200`
- `0x18001fb68`
- `0x180029e08`
- `0x180030884`

## import_xrefs

- `MPRAPI!MprAdminBufferFree` at `0x18001fcd9`
- `MPRAPI!MprAdminBufferFree` at `0x18001fced`
- `MPRAPI!MprAdminBufferFree` at `0x18001fcd9`
- `MPRAPI!MprAdminBufferFree` at `0x18001fced`
- `MPRAPI!MprAdminServerConnect` at `0x18001fc04`
- `MPRAPI!MprAdminServerConnect` at `0x18001fc04`
- `MPRAPI!MprAdminPortEnum` at `0x18001fc6a`
- `MPRAPI!MprAdminPortEnum` at `0x18001fc6a`
- `MPRAPI!MprAdminConnectionGetInfo` at `0x18001fc24`
- `MPRAPI!MprAdminConnectionGetInfo` at `0x18001fc24`
- `MPRAPI!MprAdminServerDisconnect` at `0x18001fcf7`
- `MPRAPI!MprAdminServerDisconnect` at `0x18001fcf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrGetIncomingConnectionPropertiesEx(
        void *a1,
        const struct _GUID *a2,
        unsigned int a3,
        struct tagNETCON_PROPERTIES_EX **a4)
{
  signed int Info; // edi
  int Instance; // ebx
  MPR_SERVER_HANDLE phMprServer; // [rsp+40h] [rbp-30h] BYREF
  LPBYTE v12; // [rsp+48h] [rbp-28h] BYREF
  LPBYTE lpbBuffer; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwTotalEntries; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwEntriesRead; // [rsp+5Ch] [rbp-14h] BYREF
  struct INetConnection *v16; // [rsp+60h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids);
  phMprServer = 0;
  lpbBuffer = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  Info = MprAdminServerConnect(0, &phMprServer);
  if ( Info )
    goto LABEL_17;
  Instance = 0;
  Info = MprAdminConnectionGetInfo(phMprServer, 2u, a1, &lpbBuffer);
  if ( !Info )
  {
    dwEntriesRead = 0;
    dwTotalEntries = 0;
    v12 = 0;
    Info = MprAdminPortEnum(phMprServer, 0, a1, &v12, 0x310u, &dwEntriesRead, &dwTotalEntries, 0);
    if ( !Info )
    {
      v16 = 0;
      Instance = InboundConnection::CreateInstance(
                   0,
                   a1,
                   (const unsigned __int16 *)lpbBuffer + 4,
                   (const unsigned __int16 *)v12 + 48,
                   a3,
                   a2,
                   &IID_INetConnection,
                   (void **)&v16);
      if ( Instance >= 0 )
      {
        Instance = HrGetPropertiesExFromINetConnection(v16, a4);
        if ( Instance >= 0 )
          *((_DWORD *)*a4 + 10) = 2;
      }
      MprAdminBufferFree(v12);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    }
    MprAdminBufferFree(lpbBuffer);
  }
  MprAdminServerDisconnect(phMprServer);
  if ( Info )
  {
LABEL_17:
    if ( Info > 0 )
      return (unsigned __int16)Info | 0x80070000;
    else
      return (unsigned int)Info;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001fb68  mov     [rsp-28h+arg_8], rbx
0x18001fb6d  mov     [rsp-28h+arg_10], rsi
0x18001fb72  push    rbp
0x18001fb73  push    rdi
0x18001fb74  push    r12
0x18001fb76  push    r14
0x18001fb78  push    r15
0x18001fb7a  mov     rbp, rsp
0x18001fb7d  sub     rsp, 70h
0x18001fb81  mov     rax, cs:__security_cookie
0x18001fb88  xor     rax, rsp
0x18001fb8b  mov     [rbp+var_8], rax
0x18001fb8f  mov     rsi, r9
0x18001fb92  mov     r15d, r8d
0x18001fb95  mov     r12, rdx
0x18001fb98  mov     r14, rcx
0x18001fb9b  lea     rax, WPP_GLOBAL_Control
0x18001fba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fba9  cmp     rcx, rax
0x18001fbac  jz      short loc_18001FBC9
0x18001fbae  test    byte ptr [rcx+1Ch], 8
0x18001fbb2  jz      short loc_18001FBC9
0x18001fbb4  mov     edx, 1Bh
0x18001fbb9  lea     r8, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids
0x18001fbc0  mov     rcx, [rcx+10h]
0x18001fbc4  call    WPP_SF_
0x18001fbc9  mov     [rbp+phMprServer], 0
0x18001fbd1  mov     [rbp+lpbBuffer], 0
0x18001fbd9  test    r14, r14
0x18001fbdc  jnz     short loc_18001FBE8
0x18001fbde  mov     eax, 80070057h
0x18001fbe3  jmp     loc_18001FD14
0x18001fbe8  test    rsi, rsi
0x18001fbeb  jnz     short loc_18001FBF7
0x18001fbed  mov     eax, 80004003h
0x18001fbf2  jmp     loc_18001FD14
0x18001fbf7  mov     qword ptr [rsi], 0
0x18001fbfe  lea     rdx, [rbp+phMprServer]; phMprServer
0x18001fc02  xor     ecx, ecx; lpwsServerName
0x18001fc04  call    cs:__imp_MprAdminServerConnect
0x18001fc0a  mov     edi, eax
0x18001fc0c  test    eax, eax
0x18001fc0e  jnz     loc_18001FD01
0x18001fc14  xor     ebx, ebx
0x18001fc16  lea     r9, [rbp+lpbBuffer]; lplpbBuffer
0x18001fc1a  mov     r8, r14; hRasConnection
0x18001fc1d  lea     edx, [rax+2]; dwLevel
0x18001fc20  mov     rcx, [rbp+phMprServer]; hRasServer
0x18001fc24  call    cs:__imp_MprAdminConnectionGetInfo
0x18001fc2a  mov     edi, eax
0x18001fc2c  test    eax, eax
0x18001fc2e  jnz     loc_18001FCF3
0x18001fc34  mov     [rbp+dwEntriesRead], ebx
0x18001fc37  mov     [rbp+dwTotalEntries], ebx
0x18001fc3a  mov     [rbp+var_28], rbx
0x18001fc3e  mov     [rsp+70h+lpdwResumeHandle], rbx; lpdwResumeHandle
0x18001fc43  lea     rax, [rbp+dwTotalEntries]
0x18001fc47  mov     [rsp+70h+lpdwTotalEntries], rax; lpdwTotalEntries
0x18001fc4c  lea     rax, [rbp+dwEntriesRead]
0x18001fc50  mov     [rsp+70h+lpdwEntriesRead], rax; lpdwEntriesRead
0x18001fc55  mov     [rsp+70h+dwPrefMaxLen], 310h; dwPrefMaxLen
0x18001fc5d  lea     r9, [rbp+var_28]; lplpbBuffer
0x18001fc61  mov     r8, r14; hRasConnection
0x18001fc64  xor     edx, edx; dwLevel
0x18001fc66  mov     rcx, [rbp+phMprServer]; hRasServer
0x18001fc6a  call    cs:__imp_MprAdminPortEnum
0x18001fc70  mov     edi, eax
0x18001fc72  test    eax, eax
0x18001fc74  jnz     short loc_18001FCE9
0x18001fc76  mov     [rbp+var_10], rbx
0x18001fc7a  mov     r9, [rbp+var_28]
0x18001fc7e  add     r9, 60h ; '`'; unsigned __int16 *
0x18001fc82  mov     r8, [rbp+lpbBuffer]
0x18001fc86  add     r8, 8; unsigned __int16 *
0x18001fc8a  lea     rax, [rbp+var_10]
0x18001fc8e  mov     [rsp+70h+lpdwResumeHandle], rax; void **
0x18001fc93  lea     rax, IID_INetConnection
0x18001fc9a  mov     [rsp+70h+lpdwTotalEntries], rax; struct _GUID *
0x18001fc9f  mov     [rsp+70h+lpdwEntriesRead], r12; struct _GUID *
0x18001fca4  mov     [rsp+70h+dwPrefMaxLen], r15d; unsigned int
0x18001fca9  mov     rdx, r14; void *
0x18001fcac  xor     ecx, ecx; int
0x18001fcae  call    ?CreateInstance@InboundConnection@@SAJHPEAXPEBG1KPEBU_GUID@@AEBU2@PEAPEAX@Z; InboundConnection::CreateInstance(int,void *,ushort const *,ushort const *,ulong,_GUID const *,_GUID const &,void * *)
0x18001fcb3  mov     ebx, eax
0x18001fcb5  test    eax, eax
0x18001fcb7  js      short loc_18001FCD5
0x18001fcb9  mov     rdx, rsi; struct tagNETCON_PROPERTIES_EX **
0x18001fcbc  mov     rcx, [rbp+var_10]; struct INetConnection *
0x18001fcc0  call    ?HrGetPropertiesExFromINetConnection@@YAJPEAUINetConnection@@PEAPEAUtagNETCON_PROPERTIES_EX@@@Z; HrGetPropertiesExFromINetConnection(INetConnection *,tagNETCON_PROPERTIES_EX * *)
0x18001fcc5  mov     ebx, eax
0x18001fcc7  test    eax, eax
0x18001fcc9  js      short loc_18001FCD5
0x18001fccb  mov     rax, [rsi]
0x18001fcce  mov     dword ptr [rax+28h], 2
0x18001fcd5  mov     rcx, [rbp+var_28]; pBuffer
0x18001fcd9  call    cs:__imp_MprAdminBufferFree
0x18001fcdf  nop
0x18001fce0  lea     rcx, [rbp+var_10]
0x18001fce4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fce9  mov     rcx, [rbp+lpbBuffer]; pBuffer
0x18001fced  call    cs:__imp_MprAdminBufferFree
0x18001fcf3  mov     rcx, [rbp+phMprServer]; hMprServer
0x18001fcf7  call    cs:__imp_MprAdminServerDisconnect
0x18001fcfd  test    edi, edi
0x18001fcff  jz      short loc_18001FD12
0x18001fd01  test    edi, edi
0x18001fd03  jg      short loc_18001FD09
0x18001fd05  mov     ebx, edi
0x18001fd07  jmp     short loc_18001FD12
0x18001fd09  movzx   ebx, di
0x18001fd0c  or      ebx, 80070000h
0x18001fd12  mov     eax, ebx
0x18001fd14  mov     rcx, [rbp+var_8]
0x18001fd18  xor     rcx, rsp; StackCookie
0x18001fd1b  call    __security_check_cookie
0x18001fd20  lea     r11, [rsp+70h+var_s0]
0x18001fd25  mov     rbx, [r11+38h]
0x18001fd29  mov     rsi, [r11+40h]
0x18001fd2d  mov     rsp, r11
0x18001fd30  pop     r15
0x18001fd32  pop     r14
0x18001fd34  pop     r12
0x18001fd36  pop     rdi
0x18001fd37  pop     rbp
0x18001fd38  retn
```
