# EapHostPeerInitialize

- ea: `0x180009b90`
- end: `0x180009e03`
- name: `EapHostPeerInitialize`
- size: `627`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x180009b90`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000ade4`
- `0x18000c280`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180009c2a`
- `ntdll!EtwEventEnabled` at `0x180009cf0`
- `ntdll!EtwEventEnabled` at `0x180009c2a`
- `ntdll!EtwEventEnabled` at `0x180009cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009bc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009bc7`

## pseudocode

```c
DWORD __stdcall EapHostPeerInitialize()
{
  unsigned __int64 v0; // rbx
  DWORD TickCount; // eax
  __int64 v2; // r8
  unsigned __int64 v3; // rsi
  int v4; // edx
  __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rax
  EapHost::Peer::PeerProxy *v8; // rcx
  DWORD inited; // edi
  __int64 v10; // r8
  unsigned __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-C8h] BYREF
  char *v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  char v16[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v0 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v3 = v0 | TickCount;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v12 = v0 | TickCount;
    v14 = (char *)&v12;
    v15 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)InitializeStart, v2, 2, (__int64)v13);
  }
  v5 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v16, 0x800u, "EapHostPeerInitialize Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v16[v7] );
    v15 = (unsigned int)(v7 + 1);
    v14 = v16;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v6, 2, (__int64)v13);
  }
  v8 = (EapHost::Peer::PeerProxy *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  inited = EapHost::Peer::PeerProxy::InitComEnv(v8, v4);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v16, 0x800u, "EapHostPeerInitialize Exit:\n returning(%x)", inited) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v5;
    while ( v16[v5] );
    v15 = (unsigned int)(v5 + 1);
    v14 = v16;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v10, 2, (__int64)v13);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e9255469090b376a053f3594056fdc10_Traceguids, inited);
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v12 = v3;
    v14 = (char *)&v12;
    v15 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)InitializeEnd, v10, 2, (__int64)v13);
  }
  return inited;
}

```

## disassembly

```asm
0x180009b90  push    rbp
0x180009b92  push    rbx
0x180009b93  push    rsi
0x180009b94  push    rdi
0x180009b95  lea     rbp, [rsp-778h]
0x180009b9d  sub     rsp, 878h
0x180009ba4  mov     rax, cs:__security_cookie
0x180009bab  xor     rax, rsp
0x180009bae  mov     [rbp+790h+var_30], rax
0x180009bb5  call    cs:__imp_GetCurrentThreadId
0x180009bbc  nop     dword ptr [rax+rax+00h]
0x180009bc1  mov     ebx, eax
0x180009bc3  shl     rbx, 20h
0x180009bc7  call    cs:__imp_GetTickCount
0x180009bce  nop     dword ptr [rax+rax+00h]
0x180009bd3  mov     esi, eax
0x180009bd5  or      rsi, rbx
0x180009bd8  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180009bdf  jge     short loc_180009C1C
0x180009be1  lea     rax, [rsp+890h+var_860]
0x180009be6  mov     [rsp+890h+var_860], rsi
0x180009beb  mov     [rsp+890h+var_848], rax
0x180009bf0  lea     rdx, InitializeStart
0x180009bf7  lea     rax, [rsp+890h+var_858]
0x180009bfc  mov     [rsp+890h+var_840], 8
0x180009c05  mov     r9d, 2
0x180009c0b  mov     [rsp+890h+var_870], rax
0x180009c10  lea     rcx, eaphost_Context
0x180009c17  call    McGenEventWrite_EtwEventWriteTransfer
0x180009c1c  mov     rcx, cs:eaphost_Context
0x180009c23  lea     rdx, DebugInfoEvent
0x180009c2a  call    cs:__imp_EtwEventEnabled
0x180009c31  nop     dword ptr [rax+rax+00h]
0x180009c36  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009c3a  test    al, al
0x180009c3c  jz      short loc_180009CAD
0x180009c3e  lea     r8, aEaphostpeerini_1; "EapHostPeerInitialize Entry"
0x180009c45  mov     edx, 800h; unsigned __int64
0x180009c4a  lea     rcx, [rsp+890h+var_830]; char *
0x180009c4f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009c54  test    eax, eax
0x180009c56  js      short loc_180009CAD
0x180009c58  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180009c5f  jge     short loc_180009CAD
0x180009c61  lea     rcx, [rsp+890h+var_830]
0x180009c66  mov     rax, rbx
0x180009c69  inc     rax
0x180009c6c  cmp     byte ptr [rcx+rax], 0
0x180009c70  jnz     short loc_180009C69
0x180009c72  inc     eax
0x180009c74  mov     dword ptr [rsp+890h+var_840+4], 0
0x180009c7c  lea     rcx, [rsp+890h+var_830]
0x180009c81  mov     dword ptr [rsp+890h+var_840], eax
0x180009c85  lea     rax, [rsp+890h+var_858]
0x180009c8a  mov     [rsp+890h+var_848], rcx
0x180009c8f  mov     r9d, 2
0x180009c95  mov     [rsp+890h+var_870], rax
0x180009c9a  lea     rdx, DebugInfoEvent
0x180009ca1  lea     rcx, eaphost_Context
0x180009ca8  call    McGenEventWrite_EtwEventWriteTransfer
0x180009cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cb4  lea     rax, WPP_GLOBAL_Control
0x180009cbb  cmp     rcx, rax
0x180009cbe  jz      short loc_180009CDB
0x180009cc0  test    byte ptr [rcx+1Ch], 4
0x180009cc4  jz      short loc_180009CDB
0x180009cc6  mov     rcx, [rcx+10h]
0x180009cca  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180009cd1  mov     edx, 0Ah
0x180009cd6  call    WPP_SF_
0x180009cdb  call    ?InitComEnv@PeerProxy@Peer@EapHost@@QEAAJK@Z; EapHost::Peer::PeerProxy::InitComEnv(ulong)
0x180009ce0  mov     rcx, cs:eaphost_Context
0x180009ce7  lea     rdx, DebugInfoEvent
0x180009cee  mov     edi, eax
0x180009cf0  call    cs:__imp_EtwEventEnabled
0x180009cf7  nop     dword ptr [rax+rax+00h]
0x180009cfc  test    al, al
0x180009cfe  jz      short loc_180009D70
0x180009d00  mov     r9d, edi
0x180009d03  lea     r8, aEaphostpeerini_0; "EapHostPeerInitialize Exit:\n returning"...
0x180009d0a  mov     edx, 800h; unsigned __int64
0x180009d0f  lea     rcx, [rsp+890h+var_830]; char *
0x180009d14  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009d19  test    eax, eax
0x180009d1b  js      short loc_180009D70
0x180009d1d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180009d24  jge     short loc_180009D70
0x180009d26  lea     rax, [rsp+890h+var_830]
0x180009d2b  inc     rbx
0x180009d2e  cmp     byte ptr [rax+rbx], 0
0x180009d32  jnz     short loc_180009D2B
0x180009d34  lea     eax, [rbx+1]
0x180009d37  mov     dword ptr [rsp+890h+var_840+4], 0
0x180009d3f  lea     rcx, [rsp+890h+var_830]
0x180009d44  mov     dword ptr [rsp+890h+var_840], eax
0x180009d48  lea     rax, [rsp+890h+var_858]
0x180009d4d  mov     [rsp+890h+var_848], rcx
0x180009d52  mov     r9d, 2
0x180009d58  mov     [rsp+890h+var_870], rax
0x180009d5d  lea     rdx, DebugInfoEvent
0x180009d64  lea     rcx, eaphost_Context
0x180009d6b  call    McGenEventWrite_EtwEventWriteTransfer
0x180009d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d77  lea     rax, WPP_GLOBAL_Control
0x180009d7e  cmp     rcx, rax
0x180009d81  jz      short loc_180009DA1
0x180009d83  test    byte ptr [rcx+1Ch], 4
0x180009d87  jz      short loc_180009DA1
0x180009d89  mov     rcx, [rcx+10h]
0x180009d8d  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180009d94  mov     edx, 0Bh
0x180009d99  mov     r9d, edi
0x180009d9c  call    WPP_SF_d
0x180009da1  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180009da8  jge     short loc_180009DE5
0x180009daa  lea     rax, [rsp+890h+var_860]
0x180009daf  mov     [rsp+890h+var_860], rsi
0x180009db4  mov     [rsp+890h+var_848], rax
0x180009db9  lea     rdx, InitializeEnd
0x180009dc0  lea     rax, [rsp+890h+var_858]
0x180009dc5  mov     [rsp+890h+var_840], 8
0x180009dce  mov     r9d, 2
0x180009dd4  mov     [rsp+890h+var_870], rax
0x180009dd9  lea     rcx, eaphost_Context
0x180009de0  call    McGenEventWrite_EtwEventWriteTransfer
0x180009de5  mov     eax, edi
0x180009de7  mov     rcx, [rbp+790h+var_30]
0x180009dee  xor     rcx, rsp; StackCookie
0x180009df1  call    __security_check_cookie
0x180009df6  add     rsp, 878h
0x180009dfd  pop     rdi
0x180009dfe  pop     rsi
0x180009dff  pop     rbx
0x180009e00  pop     rbp
0x180009e01  retn
```
