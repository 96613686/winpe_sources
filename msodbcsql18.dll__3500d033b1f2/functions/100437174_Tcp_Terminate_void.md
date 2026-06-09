# Tcp::Terminate(void)

- ea: `0x100437174`
- end: `0x100437314`
- name: `?Terminate@Tcp@@SAKXZ`
- size: `416`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x10041a500`

## callees

- `0x1004194b0`
- `0x100437174`
- `0x10043b698`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043728e`
- `KERNEL32!GetLastError` at `0x10043728e`
- `KERNEL32!FreeLibrary` at `0x100437284`
- `KERNEL32!FreeLibrary` at `0x100437284`
- `WS2_32!__imp_WSACleanup` at `0x100437266`
- `WS2_32!__imp_WSACleanup` at `0x100437266`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Tcp::Terminate(void)
{
  wchar_t *v0; // r8
  __int64 v1; // rdx
  unsigned int v2; // eax
  DWORD LastError; // eax
  __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D58[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v5,
      off_1005E7D58[0],
      0);
  if ( dword_1005D834C )
  {
    if ( g_hCleanupSendNotificationTimer )
    {
      v2 = SNIStopTimerTask((__int64)g_hCleanupSendNotificationTimer);
      g_hCleanupSendNotificationTimer = 0;
      if ( v2 != 997 && (bidGblFlags & 2) != 0 && off_1005E59A8[0] )
        bidTraceW(0, 3338240, off_1005E59A8[0], v2);
    }
    WSACleanup();
    dword_1005D834C = 0;
    SNI::detail::Transport::StaticTerminate();
    if ( Tcp::s_hWS2_32 )
    {
      if ( !FreeLibrary(Tcp::s_hWS2_32) )
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1005E59B0[0] )
            bidTraceW(0, 3353600, off_1005E59B0[0], LastError);
        }
      }
    }
    Tcp::s_hWS2_32 = 0;
    Tcp::s_pfnWSAPoll = 0;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E59B8[0] )
    {
      v0 = off_1005E59B8[0];
      v1 = 3360768;
      goto LABEL_22;
    }
  }
  else if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E59A0[0] )
  {
    v0 = off_1005E59A0[0];
    v1 = 3325952;
LABEL_22:
    bidTraceW(0, v1, v0, 0);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v5);
  return 0;
}

```

## disassembly

```asm
0x100437174  mov     r11, rsp
0x100437177  sub     rsp, 58h
0x10043717b  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100437183  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x100437188  mov     eax, cs:_bidGblFlags
0x10043718e  mov     ecx, 20004h
0x100437193  and     eax, ecx
0x100437195  cmp     eax, ecx
0x100437197  jnz     short loc_1004371DC
0x100437199  mov     rax, cs:off_1005E7D58; "<Tcp::Terminate|API|SNI> \n"
0x1004371a0  test    rax, rax
0x1004371a3  jz      short loc_1004371DC
0x1004371a5  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004371ad  jz      short loc_1004371DC
0x1004371af  mov     rax, cs:off_1005D39F0
0x1004371b6  and     qword ptr [r11-30h], 0
0x1004371bb  mov     rcx, cs:off_1005E7D58; "<Tcp::Terminate|API|SNI> \n"
0x1004371c2  mov     [r11-38h], rcx
0x1004371c6  lea     r9, [r11+8]
0x1004371ca  xor     r8d, r8d
0x1004371cd  xor     edx, edx
0x1004371cf  mov     rcx, cs:_bidID
0x1004371d6  call    cs:__guard_dispatch_icall_fptr
0x1004371dc  cmp     cs:dword_1005D834C, 0
0x1004371e3  jnz     short loc_10043721B
0x1004371e5  mov     eax, cs:_bidGblFlags
0x1004371eb  mov     ecx, 20002h
0x1004371f0  and     eax, ecx
0x1004371f2  cmp     eax, ecx
0x1004371f4  jnz     loc_100437303
0x1004371fa  mov     rax, cs:off_1005E59A0; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x100437201  test    rax, rax
0x100437204  jz      loc_100437303
0x10043720a  mov     r8, cs:off_1005E59A0; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x100437211  mov     edx, 32C000h
0x100437216  jmp     loc_1004372F8
0x10043721b  mov     rcx, cs:?g_hCleanupSendNotificationTimer@@3PEAXEA; void * g_hCleanupSendNotificationTimer
0x100437222  test    rcx, rcx
0x100437225  jz      short loc_100437266
0x100437227  call    SNIStopTimerTask
0x10043722c  and     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, 0; void * g_hCleanupSendNotificationTimer
0x100437234  cmp     eax, 3E5h
0x100437239  jz      short loc_100437266
0x10043723b  test    byte ptr cs:_bidGblFlags, 2
0x100437242  jz      short loc_100437266
0x100437244  mov     rcx, cs:off_1005E59A8; "<Tcp::Terminate|ERR|SNI> SNIStopTimerTa"...
0x10043724b  test    rcx, rcx
0x10043724e  jz      short loc_100437266
0x100437250  mov     r9d, eax
0x100437253  mov     r8, cs:off_1005E59A8; "<Tcp::Terminate|ERR|SNI> SNIStopTimerTa"...
0x10043725a  mov     edx, 32F000h
0x10043725f  xor     ecx, ecx
0x100437261  call    _bidTraceW
0x100437266  call    cs:__imp_WSACleanup
0x10043726c  and     cs:dword_1005D834C, 0
0x100437273  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x100437278  mov     rcx, cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; hLibModule
0x10043727f  test    rcx, rcx
0x100437282  jz      short loc_1004372BF
0x100437284  call    cs:__imp_FreeLibrary
0x10043728a  test    eax, eax
0x10043728c  jnz     short loc_1004372BF
0x10043728e  call    cs:__imp_GetLastError
0x100437294  test    byte ptr cs:_bidGblFlags, 2
0x10043729b  jz      short loc_1004372BF
0x10043729d  mov     rcx, cs:off_1005E59B0; "<Tcp::Terminate|ERR|SNI> FreeLibrary fo"...
0x1004372a4  test    rcx, rcx
0x1004372a7  jz      short loc_1004372BF
0x1004372a9  mov     r9d, eax
0x1004372ac  mov     r8, cs:off_1005E59B0; "<Tcp::Terminate|ERR|SNI> FreeLibrary fo"...
0x1004372b3  mov     edx, 332C00h
0x1004372b8  xor     ecx, ecx
0x1004372ba  call    _bidTraceW
0x1004372bf  and     cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Tcp::s_hWS2_32
0x1004372c7  and     cs:?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA, 0; int (*Tcp::s_pfnWSAPoll)(pollfd * const,ulong,int)
0x1004372cf  mov     eax, cs:_bidGblFlags
0x1004372d5  mov     ecx, 20002h
0x1004372da  and     eax, ecx
0x1004372dc  cmp     eax, ecx
0x1004372de  jnz     short loc_100437303
0x1004372e0  mov     rax, cs:off_1005E59B8; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x1004372e7  test    rax, rax
0x1004372ea  jz      short loc_100437303
0x1004372ec  mov     r8, cs:off_1005E59B8; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x1004372f3  mov     edx, 334800h
0x1004372f8  xor     r9d, r9d
0x1004372fb  xor     ecx, ecx
0x1004372fd  call    _bidTraceW
0x100437302  nop
0x100437303  lea     rcx, [rsp+58h+arg_0]; this
0x100437308  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10043730d  xor     eax, eax
0x10043730f  add     rsp, 58h
0x100437313  retn
```
