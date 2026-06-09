# EapHostPeerUninitialize

- ea: `0x18000a8f0`
- end: `0x18000ab54`
- name: `EapHostPeerUninitialize`
- size: `612`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x18000a8f0`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000cae8`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000a98b`
- `ntdll!EtwEventEnabled` at `0x18000aa4f`
- `ntdll!EtwEventEnabled` at `0x18000a98b`
- `ntdll!EtwEventEnabled` at `0x18000aa4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a916`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a928`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a928`

## pseudocode

```c
void __stdcall EapHostPeerUninitialize()
{
  unsigned __int64 v0; // rbx
  DWORD TickCount; // eax
  __int64 v2; // r8
  unsigned __int64 v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rax
  EapHost::Peer::PeerProxy *v7; // rcx
  __int64 v8; // r8
  unsigned __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-C8h] BYREF
  char *v11; // [rsp+48h] [rbp-B8h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  char v13[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v0 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v3 = v0 | TickCount;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v9 = v0 | TickCount;
    v11 = (char *)&v9;
    v12 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)UnInitializeStart, v2, 2, (__int64)v10);
  }
  v4 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "EapHostPeerUninitialize Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v13[v6] );
    v12 = (unsigned int)(v6 + 1);
    v11 = v13;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v5, 2, (__int64)v10);
  }
  v7 = (EapHost::Peer::PeerProxy *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  EapHost::Peer::PeerProxy::UninitComEnv(v7);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "EapHostPeerUninitialize Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v4;
    while ( v13[v4] );
    v12 = (unsigned int)(v4 + 1);
    v11 = v13;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v8, 2, (__int64)v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v9 = v3;
    v11 = (char *)&v9;
    v12 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)UnInitializeEnd, v8, 2, (__int64)v10);
  }
}

```

## disassembly

```asm
0x18000a8f0  push    rbp
0x18000a8f2  push    rbx
0x18000a8f3  push    rdi
0x18000a8f4  push    r13
0x18000a8f6  lea     rbp, [rsp-778h]
0x18000a8fe  sub     rsp, 878h
0x18000a905  mov     rax, cs:__security_cookie
0x18000a90c  xor     rax, rsp
0x18000a90f  mov     [rbp+790h+var_30], rax
0x18000a916  call    cs:__imp_GetCurrentThreadId
0x18000a91d  nop     dword ptr [rax+rax+00h]
0x18000a922  mov     ebx, eax
0x18000a924  shl     rbx, 20h
0x18000a928  call    cs:__imp_GetTickCount
0x18000a92f  nop     dword ptr [rax+rax+00h]
0x18000a934  mov     edi, eax
0x18000a936  or      rdi, rbx
0x18000a939  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000a940  jge     short loc_18000A97D
0x18000a942  lea     rax, [rsp+890h+var_860]
0x18000a947  mov     [rsp+890h+var_860], rdi
0x18000a94c  mov     [rsp+890h+var_848], rax
0x18000a951  lea     rdx, UnInitializeStart
0x18000a958  lea     rax, [rsp+890h+var_858]
0x18000a95d  mov     [rsp+890h+var_840], 8
0x18000a966  mov     r9d, 2
0x18000a96c  mov     [rsp+890h+var_870], rax
0x18000a971  lea     rcx, eaphost_Context
0x18000a978  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a97d  mov     rcx, cs:eaphost_Context
0x18000a984  lea     rdx, DebugInfoEvent
0x18000a98b  call    cs:__imp_EtwEventEnabled
0x18000a992  nop     dword ptr [rax+rax+00h]
0x18000a997  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a99b  test    al, al
0x18000a99d  jz      short loc_18000AA0E
0x18000a99f  lea     r8, aEaphostpeeruni_0; "EapHostPeerUninitialize Entry"
0x18000a9a6  mov     edx, 800h; unsigned __int64
0x18000a9ab  lea     rcx, [rsp+890h+var_830]; char *
0x18000a9b0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a9b5  test    eax, eax
0x18000a9b7  js      short loc_18000AA0E
0x18000a9b9  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000a9c0  jge     short loc_18000AA0E
0x18000a9c2  lea     rcx, [rsp+890h+var_830]
0x18000a9c7  mov     rax, rbx
0x18000a9ca  inc     rax
0x18000a9cd  cmp     byte ptr [rcx+rax], 0
0x18000a9d1  jnz     short loc_18000A9CA
0x18000a9d3  inc     eax
0x18000a9d5  mov     dword ptr [rsp+890h+var_840+4], 0
0x18000a9dd  lea     rcx, [rsp+890h+var_830]
0x18000a9e2  mov     dword ptr [rsp+890h+var_840], eax
0x18000a9e6  lea     rax, [rsp+890h+var_858]
0x18000a9eb  mov     [rsp+890h+var_848], rcx
0x18000a9f0  mov     r9d, 2
0x18000a9f6  mov     [rsp+890h+var_870], rax
0x18000a9fb  lea     rdx, DebugInfoEvent
0x18000aa02  lea     rcx, eaphost_Context
0x18000aa09  call    McGenEventWrite_EtwEventWriteTransfer
0x18000aa0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa15  lea     r13, WPP_GLOBAL_Control
0x18000aa1c  cmp     rcx, r13
0x18000aa1f  jz      short loc_18000AA3C
0x18000aa21  test    byte ptr [rcx+1Ch], 4
0x18000aa25  jz      short loc_18000AA3C
0x18000aa27  mov     rcx, [rcx+10h]
0x18000aa2b  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000aa32  mov     edx, 0Ch
0x18000aa37  call    WPP_SF_
0x18000aa3c  call    ?UninitComEnv@PeerProxy@Peer@EapHost@@QEAAXXZ; EapHost::Peer::PeerProxy::UninitComEnv(void)
0x18000aa41  mov     rcx, cs:eaphost_Context
0x18000aa48  lea     rdx, DebugInfoEvent
0x18000aa4f  call    cs:__imp_EtwEventEnabled
0x18000aa56  nop     dword ptr [rax+rax+00h]
0x18000aa5b  test    al, al
0x18000aa5d  jz      short loc_18000AACC
0x18000aa5f  lea     r8, aEaphostpeeruni_1; "EapHostPeerUninitialize Exit"
0x18000aa66  mov     edx, 800h; unsigned __int64
0x18000aa6b  lea     rcx, [rsp+890h+var_830]; char *
0x18000aa70  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000aa75  test    eax, eax
0x18000aa77  js      short loc_18000AACC
0x18000aa79  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000aa80  jge     short loc_18000AACC
0x18000aa82  lea     rax, [rsp+890h+var_830]
0x18000aa87  inc     rbx
0x18000aa8a  cmp     byte ptr [rax+rbx], 0
0x18000aa8e  jnz     short loc_18000AA87
0x18000aa90  lea     eax, [rbx+1]
0x18000aa93  mov     dword ptr [rsp+890h+var_840+4], 0
0x18000aa9b  lea     rcx, [rsp+890h+var_830]
0x18000aaa0  mov     dword ptr [rsp+890h+var_840], eax
0x18000aaa4  lea     rax, [rsp+890h+var_858]
0x18000aaa9  mov     [rsp+890h+var_848], rcx
0x18000aaae  mov     r9d, 2
0x18000aab4  mov     [rsp+890h+var_870], rax
0x18000aab9  lea     rdx, DebugInfoEvent
0x18000aac0  lea     rcx, eaphost_Context
0x18000aac7  call    McGenEventWrite_EtwEventWriteTransfer
0x18000aacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aad3  cmp     rcx, r13
0x18000aad6  jz      short loc_18000AAF3
0x18000aad8  test    byte ptr [rcx+1Ch], 4
0x18000aadc  jz      short loc_18000AAF3
0x18000aade  mov     rcx, [rcx+10h]
0x18000aae2  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000aae9  mov     edx, 0Dh
0x18000aaee  call    WPP_SF_
0x18000aaf3  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000aafa  jge     short loc_18000AB37
0x18000aafc  lea     rax, [rsp+890h+var_860]
0x18000ab01  mov     [rsp+890h+var_860], rdi
0x18000ab06  mov     [rsp+890h+var_848], rax
0x18000ab0b  lea     rdx, UnInitializeEnd
0x18000ab12  lea     rax, [rsp+890h+var_858]
0x18000ab17  mov     [rsp+890h+var_840], 8
0x18000ab20  mov     r9d, 2
0x18000ab26  mov     [rsp+890h+var_870], rax
0x18000ab2b  lea     rcx, eaphost_Context
0x18000ab32  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ab37  mov     rcx, [rbp+790h+var_30]
0x18000ab3e  xor     rcx, rsp; StackCookie
0x18000ab41  call    __security_check_cookie
0x18000ab46  add     rsp, 878h
0x18000ab4d  pop     r13
0x18000ab4f  pop     rdi
0x18000ab50  pop     rbx
0x18000ab51  pop     rbp
0x18000ab52  retn
```
