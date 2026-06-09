# NGENService::ResetDirtyRootStore(void)

- ea: `0x1800039ac`
- end: `0x180003a52`
- name: `?ResetDirtyRootStore@NGENService@@YAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800046c4`
- `0x180005688`

## callees

- `0x1800039ac`
- `0x18002e1d0`
- `0x180037340`
- `0x1800373e0`

## import_xrefs

- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180003a2b`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180003a2b`
- `KERNEL32!ResetEvent` at `0x1800039b9`
- `KERNEL32!ResetEvent` at `0x1800039b9`

## string_xrefs

- `0x180003a35`: `ResetDirtyRootStore(): Failed to hook up registry notifier\n`

## pseudocode

```c
__int64 __fastcall NGENService::ResetDirtyRootStore(NGENService *this)
{
  DWORD v1; // edx
  const unsigned __int16 *v2; // r8
  unsigned __int16 *v3; // r8
  int Long; // eax
  const unsigned __int16 *v5; // rdx
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx

  ResetEvent(NGENService::g_hRootStoreDirtyEvent);
  if ( (unsigned int)REGUTIL::GetLong(L"RootstoreDirty", v1, v2, NGENService::g_hkNGENServiceListenedState)
    && (Long = REGUTIL::SetOrCreateLong(L"RootstoreDirty", 0, v3, NGENService::g_hkNGENServiceListenedState)) != 0 )
  {
    v6 = (unsigned __int16)Long | 0x80070000;
    if ( Long <= 0 )
      v6 = Long;
    NGENService::DebugLog((NGENService *)L"ResetDirtyRootStore(): Failed to clear root store dirty flag\n", v5);
  }
  else if ( RegNotifyChangeKeyValue(
              NGENService::g_hkNGENServiceListenedState,
              0,
              4u,
              NGENService::g_hRootStoreDirtyEvent,
              1) )
  {
    NGENService::DebugLog((NGENService *)L"ResetDirtyRootStore(): Failed to hook up registry notifier\n", v7);
    return (unsigned int)-2147467259;
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800039ac  push    rbx
0x1800039ae  sub     rsp, 30h
0x1800039b2  mov     rcx, cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA; hEvent
0x1800039b9  call    cs:__imp_ResetEvent
0x1800039bf  mov     r9, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x1800039c6  lea     rcx, aRootstoredirty; "RootstoreDirty"
0x1800039cd  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x1800039d2  test    eax, eax
0x1800039d4  jz      short loc_180003A0F
0x1800039d6  mov     r9, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x1800039dd  lea     rcx, aRootstoredirty; "RootstoreDirty"
0x1800039e4  xor     edx, edx; int
0x1800039e6  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x1800039eb  test    eax, eax
0x1800039ed  jz      short loc_180003A0F
0x1800039ef  movzx   ebx, ax
0x1800039f2  or      ebx, 80070000h
0x1800039f8  test    eax, eax
0x1800039fa  cmovle  ebx, eax
0x1800039fd  test    ebx, ebx
0x1800039ff  jns     short loc_180003A0F
0x180003a01  lea     rcx, aResetdirtyroot; "ResetDirtyRootStore(): Failed to clear "...
0x180003a08  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180003a0d  jmp     short loc_180003A4A
0x180003a0f  mov     r9, cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA; hEvent
0x180003a16  xor     edx, edx; bWatchSubtree
0x180003a18  mov     rcx, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; hKey
0x180003a1f  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180003a27  lea     r8d, [rdx+4]; dwNotifyFilter
0x180003a2b  call    cs:__imp_RegNotifyChangeKeyValue
0x180003a31  test    eax, eax
0x180003a33  jz      short loc_180003A48
0x180003a35  lea     rcx, aResetdirtyroot_0; "ResetDirtyRootStore(): Failed to hook u"...
0x180003a3c  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180003a41  mov     ebx, 80004005h
0x180003a46  jmp     short loc_180003A4A
0x180003a48  xor     ebx, ebx
0x180003a4a  mov     eax, ebx
0x180003a4c  add     rsp, 30h
0x180003a50  pop     rbx
0x180003a51  retn
```
