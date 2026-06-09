# WebBrowser::Create(uint,uint,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x140009a04`
- end: `0x140009bc8`
- name: `?Create@WebBrowser@@SAJIIPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `452`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009c30`

## callees

- `0x140008f64`
- `0x140009a04`
- `0x140020420`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140009afd`
- `KERNEL32!GetCurrentThreadId` at `0x140009afd`
- `KERNEL32!GetLastError` at `0x140009a35`
- `KERNEL32!GetLastError` at `0x140009b30`
- `KERNEL32!GetLastError` at `0x140009a35`
- `KERNEL32!GetLastError` at `0x140009b30`
- `KERNEL32!TlsAlloc` at `0x140009a22`
- `KERNEL32!TlsAlloc` at `0x140009a22`
- `KERNEL32!TlsFree` at `0x140009a67`
- `KERNEL32!TlsFree` at `0x140009a67`
- `KERNEL32!TlsSetValue` at `0x140009af1`
- `KERNEL32!TlsSetValue` at `0x140009af1`
- `USER32!SetWindowsHookExW` at `0x140009b18`
- `USER32!SetWindowsHookExW` at `0x140009b18`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x140009ace`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x140009ace`
- `DUI70!??0HWNDHost@DirectUI@@QEAA@XZ` at `0x140009a8c`
- `DUI70!??0HWNDHost@DirectUI@@QEAA@XZ` at `0x140009a8c`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x140009b74`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x140009b74`

## string_xrefs

- `0x140009b53`: `WebBrowser::Create`
- `0x140009b99`: `WebBrowser::Create`

## pseudocode

```c
__int64 __fastcall WebBrowser::Create(
        __int64 a1,
        unsigned __int64 a2,
        struct DirectUI::Element *a3,
        unsigned int *a4,
        struct DirectUI::Element **a5)
{
  DWORD v7; // ecx
  signed int LastError; // eax
  unsigned int v9; // ebx
  int v10; // r9d
  DirectUI::HWNDHost *v11; // rax
  DirectUI::HWNDHost *v12; // rdi
  int v13; // eax
  int v14; // r9d
  DWORD CurrentThreadId; // eax
  HHOOK v16; // rax
  signed int v17; // eax

  if ( !g_dwTlsBrowserMessageHook )
  {
    v7 = TlsAlloc();
    if ( v7 == -1 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v10 = 788;
      goto LABEL_18;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwTlsBrowserMessageHook, v7, 0) )
      TlsFree(v7);
  }
  v11 = (DirectUI::HWNDHost *)DirectUI::HAllocAndZero((DirectUI *)0x160, a2);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    v10 = 799;
LABEL_18:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WebBrowser::Create", v10, v9);
    return v9;
  }
  DirectUI::HWNDHost::HWNDHost(v11);
  *((_QWORD *)v12 + 40) = 0;
  *((_QWORD *)v12 + 41) = 0;
  *(_QWORD *)v12 = &WebBrowser::`vftable';
  v13 = DirectUI::HWNDHost::Initialize(v12, 7u, 3u, a3, a4);
  v9 = v13;
  if ( v13 >= 0 )
  {
    TlsSetValue(g_dwTlsBrowserMessageHook, v12);
    CurrentThreadId = GetCurrentThreadId();
    v16 = SetWindowsHookExW(3, WebBrowser::s_MessageHook, 0, CurrentThreadId);
    *((_QWORD *)v12 + 41) = v16;
    if ( v16 )
    {
      v9 = 0;
      *a5 = v12;
      return v9;
    }
    v17 = GetLastError();
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    v14 = 813;
    v13 = v9;
  }
  else
  {
    v14 = 802;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WebBrowser::Create", v14, v13);
  DirectUI::Element::Destroy(v12, 1);
  return v9;
}

```

## disassembly

```asm
0x140009a04  mov     [rsp+arg_0], rbx
0x140009a09  mov     [rsp+arg_10], rsi
0x140009a0e  push    rdi
0x140009a0f  sub     rsp, 30h
0x140009a13  cmp     cs:?g_dwTlsBrowserMessageHook@@3KA, 0; ulong g_dwTlsBrowserMessageHook
0x140009a1a  mov     rbx, r9
0x140009a1d  mov     rsi, r8
0x140009a20  jnz     short loc_140009A73
0x140009a22  call    cs:__imp_TlsAlloc
0x140009a29  nop     dword ptr [rax+rax+00h]
0x140009a2e  mov     ecx, eax; dwTlsIndex
0x140009a30  cmp     eax, 0FFFFFFFFh
0x140009a33  jnz     short loc_140009A5B
0x140009a35  call    cs:__imp_GetLastError
0x140009a3c  nop     dword ptr [rax+rax+00h]
0x140009a41  mov     ebx, eax
0x140009a43  test    eax, eax
0x140009a45  jle     short loc_140009A50
0x140009a47  movzx   ebx, ax
0x140009a4a  or      ebx, 80070000h
0x140009a50  mov     r9d, 314h
0x140009a56  jmp     loc_140009B99
0x140009a5b  xor     eax, eax
0x140009a5d  lock cmpxchg cs:?g_dwTlsBrowserMessageHook@@3KA, ecx; ulong g_dwTlsBrowserMessageHook
0x140009a65  jz      short loc_140009A73
0x140009a67  call    cs:__imp_TlsFree
0x140009a6e  nop     dword ptr [rax+rax+00h]
0x140009a73  mov     ecx, 160h; this
0x140009a78  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x140009a7d  mov     rdi, rax
0x140009a80  test    rax, rax
0x140009a83  jz      loc_140009B8E
0x140009a89  mov     rcx, rax
0x140009a8c  call    cs:__imp_??0HWNDHost@DirectUI@@QEAA@XZ; DirectUI::HWNDHost::HWNDHost(void)
0x140009a93  nop     dword ptr [rax+rax+00h]
0x140009a98  mov     r9, rsi
0x140009a9b  mov     qword ptr [rdi+140h], 0
0x140009aa6  mov     esi, 3
0x140009aab  mov     qword ptr [rdi+148h], 0
0x140009ab6  lea     rax, ??_7WebBrowser@@6B@; const WebBrowser::`vftable'
0x140009abd  mov     [rsp+38h+var_18], rbx
0x140009ac2  mov     r8d, esi
0x140009ac5  mov     [rdi], rax
0x140009ac8  mov     rcx, rdi
0x140009acb  lea     edx, [rsi+4]
0x140009ace  call    cs:__imp_?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z; DirectUI::HWNDHost::Initialize(uint,uint,DirectUI::Element *,ulong *)
0x140009ad5  nop     dword ptr [rax+rax+00h]
0x140009ada  mov     ebx, eax
0x140009adc  test    eax, eax
0x140009ade  jns     short loc_140009AE8
0x140009ae0  mov     r9d, 322h
0x140009ae6  jmp     short loc_140009B53
0x140009ae8  mov     ecx, cs:?g_dwTlsBrowserMessageHook@@3KA; dwTlsIndex
0x140009aee  mov     rdx, rdi; lpTlsValue
0x140009af1  call    cs:__imp_TlsSetValue
0x140009af8  nop     dword ptr [rax+rax+00h]
0x140009afd  call    cs:__imp_GetCurrentThreadId
0x140009b04  nop     dword ptr [rax+rax+00h]
0x140009b09  xor     r8d, r8d; hmod
0x140009b0c  lea     rdx, ?s_MessageHook@WebBrowser@@SA_JH_K_J@Z; lpfn
0x140009b13  mov     r9d, eax; dwThreadId
0x140009b16  mov     ecx, esi; idHook
0x140009b18  call    cs:__imp_SetWindowsHookExW
0x140009b1f  nop     dword ptr [rax+rax+00h]
0x140009b24  mov     [rdi+148h], rax
0x140009b2b  test    rax, rax
0x140009b2e  jnz     short loc_140009B82
0x140009b30  call    cs:__imp_GetLastError
0x140009b37  nop     dword ptr [rax+rax+00h]
0x140009b3c  mov     ebx, eax
0x140009b3e  test    eax, eax
0x140009b40  jle     short loc_140009B4B
0x140009b42  movzx   ebx, ax
0x140009b45  or      ebx, 80070000h
0x140009b4b  mov     r9d, 32Dh
0x140009b51  mov     eax, ebx
0x140009b53  lea     r8, aWebbrowserCrea; "WebBrowser::Create"
0x140009b5a  mov     dword ptr [rsp+38h+var_18], eax
0x140009b5e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140009b65  mov     ecx, 1; Level
0x140009b6a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140009b6f  mov     dl, 1
0x140009b71  mov     rcx, rdi
0x140009b74  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x140009b7b  nop     dword ptr [rax+rax+00h]
0x140009b80  jmp     short loc_140009BB5
0x140009b82  mov     rax, [rsp+38h+arg_20]
0x140009b87  xor     ebx, ebx
0x140009b89  mov     [rax], rdi
0x140009b8c  jmp     short loc_140009BB5
0x140009b8e  mov     ebx, 8007000Eh
0x140009b93  mov     r9d, 31Fh
0x140009b99  lea     r8, aWebbrowserCrea; "WebBrowser::Create"
0x140009ba0  mov     dword ptr [rsp+38h+var_18], ebx
0x140009ba4  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140009bab  mov     ecx, 1; Level
0x140009bb0  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140009bb5  mov     rsi, [rsp+38h+arg_10]
0x140009bba  mov     eax, ebx
0x140009bbc  mov     rbx, [rsp+38h+arg_0]
0x140009bc1  add     rsp, 30h
0x140009bc5  pop     rdi
0x140009bc6  retn
```
