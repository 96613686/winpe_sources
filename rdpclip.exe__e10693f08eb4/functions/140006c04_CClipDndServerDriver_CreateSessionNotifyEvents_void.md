# CClipDndServerDriver::CreateSessionNotifyEvents(void)

- ea: `0x140006c04`
- end: `0x140006d6b`
- name: `?CreateSessionNotifyEvents@CClipDndServerDriver@@IEAAJXZ`
- size: `359`
- prototype: `__int64 __fastcall(CClipDndServerDriver *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400077b0`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x140006c04`
- `0x140008bc8`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006caf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006d36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006caf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006d36`

## string_xrefs

- `0x140006c74`: `Failed to copy "RDPClip-Disconnect" event name!`
- `0x140006d1e`: `Failed to copy "RDPClip-Reconnect" event name!`

## pseudocode

```c
__int64 __fastcall CClipDndServerDriver::CreateSessionNotifyEvents(CClipDndServerDriver *this)
{
  int v2; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v8; // rax
  int v10; // [rsp+28h] [rbp-60h]
  WCHAR Name[32]; // [rsp+30h] [rbp-58h] BYREF

  v2 = StringCbCopyW(Name, 0x40u, L"RDPClip-Disconnect");
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 34;
      v5 = "Failed to copy \"RDPClip-Disconnect\" event name!";
LABEL_6:
      v10 = v2;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        (unsigned int)WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v5,
        v10);
      return (unsigned int)v2;
    }
    return (unsigned int)v2;
  }
  EventW = CreateEventW(0, 0, 0, Name);
  if ( !EventW )
  {
LABEL_8:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)v2;
  }
  *((_QWORD *)this + 6) = EventW;
  v2 = StringCbCopyW(Name, 0x40u, L"RDPClip-Reconnect");
  if ( v2 >= 0 )
  {
    v8 = CreateEventW(0, 0, 0, Name);
    if ( v8 )
    {
      *((_QWORD *)this + 7) = v8;
      return 0;
    }
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 35;
    v5 = "Failed to copy \"RDPClip-Reconnect\" event name!";
    goto LABEL_6;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140006c04  mov     [rsp+arg_8], rbx
0x140006c09  push    rdi
0x140006c0a  sub     rsp, 80h
0x140006c11  mov     rax, cs:__security_cookie
0x140006c18  xor     rax, rsp
0x140006c1b  mov     [rsp+88h+var_18], rax
0x140006c20  mov     rdi, rcx
0x140006c23  lea     r8, aRdpclipDisconn; "RDPClip-Disconnect"
0x140006c2a  lea     rcx, [rsp+88h+Name]; unsigned __int16 *
0x140006c2f  mov     edx, 40h ; '@'; unsigned __int64
0x140006c34  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140006c39  mov     ebx, eax
0x140006c3b  test    eax, eax
0x140006c3d  jns     short loc_140006CA3
0x140006c3f  mov     rax, cs:WPP_GLOBAL_Control
0x140006c46  lea     rcx, WPP_GLOBAL_Control
0x140006c4d  cmp     rax, rcx
0x140006c50  jz      loc_140006D4B
0x140006c56  test    byte ptr [rax+1Ch], 8
0x140006c5a  jz      loc_140006D4B
0x140006c60  cmp     byte ptr [rax+19h], 2
0x140006c64  jb      loc_140006D4B
0x140006c6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140006c6f  mov     edx, 22h ; '"'
0x140006c74  lea     rcx, aFailedToCopyRd_0; "Failed to copy \"RDPClip-Disconnect\" e"...
0x140006c7b  mov     [rsp+88h+var_60], ebx
0x140006c7f  lea     r8, WPP_ad1169c662ec3906d6bf4dc011936ead_Traceguids
0x140006c86  mov     [rsp+88h+var_68], rcx
0x140006c8b  mov     r9d, eax
0x140006c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c95  mov     rcx, [rcx+10h]
0x140006c99  call    WPP_SF_DsD
0x140006c9e  jmp     loc_140006D4B
0x140006ca3  lea     r9, [rsp+88h+Name]; lpName
0x140006ca8  xor     r8d, r8d; bInitialState
0x140006cab  xor     edx, edx; bManualReset
0x140006cad  xor     ecx, ecx; lpEventAttributes
0x140006caf  call    cs:__imp_CreateEventW
0x140006cb5  test    rax, rax
0x140006cb8  jnz     short loc_140006CD5
0x140006cba  call    cs:__imp_GetLastError
0x140006cc0  mov     ebx, eax
0x140006cc2  test    eax, eax
0x140006cc4  jle     loc_140006D4B
0x140006cca  movzx   ebx, ax
0x140006ccd  or      ebx, 80070000h
0x140006cd3  jmp     short loc_140006D4B
0x140006cd5  lea     r8, aRdpclipReconne; "RDPClip-Reconnect"
0x140006cdc  mov     [rdi+30h], rax
0x140006ce0  mov     edx, 40h ; '@'; unsigned __int64
0x140006ce5  lea     rcx, [rsp+88h+Name]; unsigned __int16 *
0x140006cea  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140006cef  mov     ebx, eax
0x140006cf1  test    eax, eax
0x140006cf3  jns     short loc_140006D2A
0x140006cf5  mov     rax, cs:WPP_GLOBAL_Control
0x140006cfc  lea     rcx, WPP_GLOBAL_Control
0x140006d03  cmp     rax, rcx
0x140006d06  jz      short loc_140006D4B
0x140006d08  test    byte ptr [rax+1Ch], 8
0x140006d0c  jz      short loc_140006D4B
0x140006d0e  cmp     byte ptr [rax+19h], 2
0x140006d12  jb      short loc_140006D4B
0x140006d14  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140006d19  mov     edx, 23h ; '#'
0x140006d1e  lea     rcx, aFailedToCopyRd; "Failed to copy \"RDPClip-Reconnect\" ev"...
0x140006d25  jmp     loc_140006C7B
0x140006d2a  lea     r9, [rsp+88h+Name]; lpName
0x140006d2f  xor     r8d, r8d; bInitialState
0x140006d32  xor     edx, edx; bManualReset
0x140006d34  xor     ecx, ecx; lpEventAttributes
0x140006d36  call    cs:__imp_CreateEventW
0x140006d3c  test    rax, rax
0x140006d3f  jz      loc_140006CBA
0x140006d45  mov     [rdi+38h], rax
0x140006d49  xor     ebx, ebx
0x140006d4b  mov     eax, ebx
0x140006d4d  mov     rcx, [rsp+88h+var_18]
0x140006d52  xor     rcx, rsp; StackCookie
0x140006d55  call    __security_check_cookie
0x140006d5a  mov     rbx, [rsp+88h+arg_8]
0x140006d62  add     rsp, 80h
0x140006d69  pop     rdi
0x140006d6a  retn
```
