# EapHostPeerClearConnection

- ea: `0x1800069e0`
- end: `0x180006d16`
- name: `EapHostPeerClearConnection`
- size: `822`
- prototype: `DWORD __stdcall(GUID *pConnectionId, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180002106`
- `0x180005450`
- `0x1800069e0`
- `0x18000ace0`
- `0x18000ae28`
- `0x18000b140`
- `0x18000c88c`
- `0x18000dec0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180006acf`
- `ntdll!EtwEventEnabled` at `0x180006be7`
- `ntdll!EtwEventEnabled` at `0x180006acf`
- `ntdll!EtwEventEnabled` at `0x180006be7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006bcd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006bcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006a47`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006ab5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006ab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __stdcall EapHostPeerClearConnection(GUID *pConnectionId, EAP_ERROR **ppEapError)
{
  DWORD v4; // esi
  unsigned __int64 v5; // rbx
  DWORD TickCount; // eax
  __int64 v7; // r8
  unsigned __int64 v8; // r15
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rax
  EapHost::Peer::PeerProxy *v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-B8h] BYREF
  char *v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  char v20[2048]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[1024]; // [rsp+8C0h] [rbp+7C0h] BYREF

  v4 = 0;
  memset_0(sz, 0, 0x4Eu);
  v5 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v8 = v5 | TickCount;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v15 = v5 | TickCount;
    v17 = (char *)&v15;
    v18 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)ClearConnectionStart, v7, 2, (__int64)v16);
  }
  v9 = -1;
  if ( pConnectionId )
  {
    StringFromGUID2(pConnectionId, sz, 39);
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v20, 0x800u, "EapHostPeerClearConnection Entry:\n connection ID(%ls)", sz) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v20[v11] );
      v17 = v20;
      v18 = (unsigned int)(v11 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v10, 2, (__int64)v16);
    }
    v12 = (EapHost::Peer::PeerProxy *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v10, sz);
    if ( *(_QWORD *)&pConnectionId->Data1 != *(_QWORD *)&GUID_NULL.Data1
      || *(_QWORD *)pConnectionId->Data4 != *(_QWORD *)GUID_NULL.Data4 )
    {
      if ( ppEapError )
        *ppEapError = 0;
      v4 = EapHost::Peer::PeerProxy::RemoveSessionwithClearConn(v12, pConnectionId, ppEapError);
    }
  }
  FormatMessageW(0x1200u, 0, v4, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v20,
              0x800u,
              "EapHostPeerClearConnection Exit:\n %ws\nReturned connection ID(%ls)",
              Buffer,
              sz) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v9;
    while ( v20[v9] );
    v17 = v20;
    v18 = (unsigned int)(v9 + 1);
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v13, 2, (__int64)v16);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v13, v4, (__int64)sz);
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v15 = v8;
    v17 = (char *)&v15;
    v18 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)ClearConnectionEnd, v13, 2, (__int64)v16);
  }
  return v4;
}

```

## disassembly

```asm
0x1800069e0  mov     [rsp-8+arg_10], rbx
0x1800069e5  mov     [rsp-8+arg_18], rsi
0x1800069ea  push    rbp
0x1800069eb  push    rdi
0x1800069ec  push    r12
0x1800069ee  push    r14
0x1800069f0  push    r15
0x1800069f2  lea     rbp, [rsp-0FD0h]
0x1800069fa  mov     eax, 10D0h
0x1800069ff  call    _alloca_probe
0x180006a04  sub     rsp, rax
0x180006a07  mov     rax, cs:__security_cookie
0x180006a0e  xor     rax, rsp
0x180006a11  mov     [rbp+0FF0h+var_30], rax
0x180006a18  mov     r14, rdx
0x180006a1b  mov     rdi, rcx
0x180006a1e  xor     r12d, r12d
0x180006a21  mov     esi, r12d
0x180006a24  xor     edx, edx; Val
0x180006a26  lea     r8d, [r12+4Eh]; Size
0x180006a2b  lea     rcx, [rsp+10F0h+sz]; void *
0x180006a30  call    memset_0
0x180006a35  call    cs:__imp_GetCurrentThreadId
0x180006a3c  nop     dword ptr [rax+rax+00h]
0x180006a41  mov     ebx, eax
0x180006a43  shl     rbx, 20h
0x180006a47  call    cs:__imp_GetTickCount
0x180006a4e  nop     dword ptr [rax+rax+00h]
0x180006a53  mov     r15d, eax
0x180006a56  or      r15, rbx
0x180006a59  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180006a60  jge     short loc_180006A9C
0x180006a62  mov     [rsp+10F0h+var_10B0], r15
0x180006a67  lea     rax, [rsp+10F0h+var_10B0]
0x180006a6c  mov     [rsp+10F0h+var_1098], rax
0x180006a71  mov     [rsp+10F0h+var_1090], 8
0x180006a7a  lea     rax, [rsp+10F0h+var_10A8]
0x180006a7f  mov     [rsp+10F0h+lpBuffer], rax
0x180006a84  lea     r9d, [r12+2]
0x180006a89  lea     rdx, ClearConnectionStart
0x180006a90  lea     rcx, eaphost_Context
0x180006a97  call    McGenEventWrite_EtwEventWriteTransfer
0x180006a9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006aa0  test    rdi, rdi
0x180006aa3  jz      loc_180006BA7
0x180006aa9  lea     r8d, [rbx+28h]; cchMax
0x180006aad  lea     rdx, [rsp+10F0h+sz]; lpsz
0x180006ab2  mov     rcx, rdi; rguid
0x180006ab5  call    cs:__imp_StringFromGUID2
0x180006abc  nop     dword ptr [rax+rax+00h]
0x180006ac1  lea     rdx, DebugInfoEvent
0x180006ac8  mov     rcx, cs:eaphost_Context
0x180006acf  call    cs:__imp_EtwEventEnabled
0x180006ad6  nop     dword ptr [rax+rax+00h]
0x180006adb  test    al, al
0x180006add  jz      short loc_180006B4D
0x180006adf  lea     r9, [rsp+10F0h+sz]
0x180006ae4  lea     r8, aEaphostpeercle_1; "EapHostPeerClearConnection Entry:\n con"...
0x180006aeb  mov     edx, 800h; unsigned __int64
0x180006af0  lea     rcx, [rbp+0FF0h+var_1030]; char *
0x180006af4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006af9  test    eax, eax
0x180006afb  js      short loc_180006B4D
0x180006afd  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180006b04  jge     short loc_180006B4D
0x180006b06  lea     rcx, [rbp+0FF0h+var_1030]
0x180006b0a  mov     rax, rbx
0x180006b0d  inc     rax
0x180006b10  cmp     [rcx+rax], r12b
0x180006b14  jnz     short loc_180006B0D
0x180006b16  inc     eax
0x180006b18  lea     rcx, [rbp+0FF0h+var_1030]
0x180006b1c  mov     [rsp+10F0h+var_1098], rcx
0x180006b21  mov     dword ptr [rsp+10F0h+var_1090], eax
0x180006b25  mov     dword ptr [rsp+10F0h+var_1090+4], r12d
0x180006b2a  lea     rax, [rsp+10F0h+var_10A8]
0x180006b2f  mov     [rsp+10F0h+lpBuffer], rax
0x180006b34  mov     r9d, 2
0x180006b3a  lea     rdx, DebugInfoEvent
0x180006b41  lea     rcx, eaphost_Context
0x180006b48  call    McGenEventWrite_EtwEventWriteTransfer
0x180006b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b54  lea     rax, WPP_GLOBAL_Control
0x180006b5b  cmp     rcx, rax
0x180006b5e  jz      short loc_180006B79
0x180006b60  test    byte ptr [rcx+1Ch], 4
0x180006b64  jz      short loc_180006B79
0x180006b66  mov     edx, 32h ; '2'
0x180006b6b  lea     r9, [rsp+10F0h+sz]
0x180006b70  mov     rcx, [rcx+10h]
0x180006b74  call    WPP_SF_S
0x180006b79  mov     rax, [rdi]
0x180006b7c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180006b83  jnz     short loc_180006B92
0x180006b85  mov     rax, [rdi+8]
0x180006b89  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180006b90  jz      short loc_180006BA7
0x180006b92  test    r14, r14
0x180006b95  jz      short loc_180006B9A
0x180006b97  mov     [r14], r12
0x180006b9a  mov     r8, r14; struct _EAP_ERROR **
0x180006b9d  mov     rdx, rdi; struct _GUID *
0x180006ba0  call    ?RemoveSessionwithClearConn@PeerProxy@Peer@EapHost@@QEAAKAEBU_GUID@@PEAPEAU_EAP_ERROR@@@Z; EapHost::Peer::PeerProxy::RemoveSessionwithClearConn(_GUID const &,_EAP_ERROR * *)
0x180006ba5  mov     esi, eax
0x180006ba7  mov     [rsp+10F0h+Arguments], r12; Arguments
0x180006bac  mov     [rsp+10F0h+nSize], 400h; nSize
0x180006bb4  lea     rax, [rbp+0FF0h+Buffer]
0x180006bbb  mov     [rsp+10F0h+lpBuffer], rax; lpBuffer
0x180006bc0  xor     r9d, r9d; dwLanguageId
0x180006bc3  mov     r8d, esi; dwMessageId
0x180006bc6  xor     edx, edx; lpSource
0x180006bc8  mov     ecx, 1200h; dwFlags
0x180006bcd  call    cs:__imp_FormatMessageW
0x180006bd4  nop     dword ptr [rax+rax+00h]
0x180006bd9  lea     rdx, DebugInfoEvent
0x180006be0  mov     rcx, cs:eaphost_Context
0x180006be7  call    cs:__imp_EtwEventEnabled
0x180006bee  nop     dword ptr [rax+rax+00h]
0x180006bf3  test    al, al
0x180006bf5  jz      short loc_180006C6F
0x180006bf7  lea     rax, [rsp+10F0h+sz]
0x180006bfc  mov     [rsp+10F0h+lpBuffer], rax
0x180006c01  lea     r9, [rbp+0FF0h+Buffer]
0x180006c08  lea     r8, aEaphostpeercle_0; "EapHostPeerClearConnection Exit:\n %ws"...
0x180006c0f  mov     edx, 800h; unsigned __int64
0x180006c14  lea     rcx, [rbp+0FF0h+var_1030]; char *
0x180006c18  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006c1d  test    eax, eax
0x180006c1f  js      short loc_180006C6F
0x180006c21  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180006c28  jge     short loc_180006C6F
0x180006c2a  lea     rax, [rbp+0FF0h+var_1030]
0x180006c2e  inc     rbx
0x180006c31  cmp     [rax+rbx], r12b
0x180006c35  jnz     short loc_180006C2E
0x180006c37  lea     eax, [rbx+1]
0x180006c3a  lea     rcx, [rbp+0FF0h+var_1030]
0x180006c3e  mov     [rsp+10F0h+var_1098], rcx
0x180006c43  mov     dword ptr [rsp+10F0h+var_1090], eax
0x180006c47  mov     dword ptr [rsp+10F0h+var_1090+4], r12d
0x180006c4c  lea     rax, [rsp+10F0h+var_10A8]
0x180006c51  mov     [rsp+10F0h+lpBuffer], rax
0x180006c56  mov     r9d, 2
0x180006c5c  lea     rdx, DebugInfoEvent
0x180006c63  lea     rcx, eaphost_Context
0x180006c6a  call    McGenEventWrite_EtwEventWriteTransfer
0x180006c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c76  lea     rax, WPP_GLOBAL_Control
0x180006c7d  cmp     rcx, rax
0x180006c80  jz      short loc_180006CA3
0x180006c82  test    byte ptr [rcx+1Ch], 4
0x180006c86  jz      short loc_180006CA3
0x180006c88  mov     edx, 33h ; '3'
0x180006c8d  lea     rax, [rsp+10F0h+sz]
0x180006c92  mov     [rsp+10F0h+lpBuffer], rax
0x180006c97  mov     r9d, esi
0x180006c9a  mov     rcx, [rcx+10h]
0x180006c9e  call    WPP_SF_DS
0x180006ca3  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180006caa  jge     short loc_180006CE8
0x180006cac  mov     [rsp+10F0h+var_10B0], r15
0x180006cb1  lea     rax, [rsp+10F0h+var_10B0]
0x180006cb6  mov     [rsp+10F0h+var_1098], rax
0x180006cbb  mov     [rsp+10F0h+var_1090], 8
0x180006cc4  lea     rax, [rsp+10F0h+var_10A8]
0x180006cc9  mov     [rsp+10F0h+lpBuffer], rax
0x180006cce  mov     r9d, 2
0x180006cd4  lea     rdx, ClearConnectionEnd
0x180006cdb  lea     rcx, eaphost_Context
0x180006ce2  call    McGenEventWrite_EtwEventWriteTransfer
0x180006ce7  nop
0x180006ce8  mov     eax, esi
0x180006cea  mov     rcx, [rbp+0FF0h+var_30]
0x180006cf1  xor     rcx, rsp; StackCookie
0x180006cf4  call    __security_check_cookie
0x180006cf9  lea     r11, [rsp+10F0h+var_20]
0x180006d01  mov     rbx, [r11+40h]
0x180006d05  mov     rsi, [r11+48h]
0x180006d09  mov     rsp, r11
0x180006d0c  pop     r15
0x180006d0e  pop     r14
0x180006d10  pop     r12
0x180006d12  pop     rdi
0x180006d13  pop     rbp
0x180006d14  retn
```
