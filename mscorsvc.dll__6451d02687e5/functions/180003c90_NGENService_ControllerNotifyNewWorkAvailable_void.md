# NGENService::ControllerNotifyNewWorkAvailable(void)

- ea: `0x180003c90`
- end: `0x180003d28`
- name: `?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(NGENService *this, HKEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180016fd4`
- `0x18001b038`

## callees

- `0x1800035bc`
- `0x180003874`
- `0x180003c90`
- `0x18002e1d0`
- `0x1800373e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003d1a`
- `ADVAPI32!RegCloseKey` at `0x180003d1a`

## string_xrefs

- `0x180003cac`: `ControllerNotifyNewWorkAvailable(): Failed to get NGENService state\n`

## pseudocode

```c
__int64 __fastcall NGENService::ControllerNotifyNewWorkAvailable(NGENService *this, HKEY *a2)
{
  const unsigned __int16 *v2; // rdx
  signed int v3; // ebx
  const unsigned __int16 *v4; // r8
  wchar_t *v5; // rcx
  int Long; // eax
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF

  hKey = 0;
  v3 = NGENService::NGENServiceDirtyStateKey(&hKey, a2);
  if ( v3 < 0 )
  {
    v5 = L"ControllerNotifyNewWorkAvailable(): Failed to get NGENService state\n";
LABEL_3:
    NGENService::DebugLog((NGENService *)v5, v2);
    goto LABEL_12;
  }
  if ( NGENService::g_bProcessNGENService )
  {
    v3 = NGENService::ControllerState::SetAccumulatedWaitIdleTime(0);
    if ( v3 < 0 )
    {
      v5 = L"ControllerNotifyNewWorkAvailable(): Failed to clear accumulated idle time wait\n";
      goto LABEL_3;
    }
  }
  else
  {
    Long = REGUTIL::SetOrCreateLong(L"RootstoreDirty", 1, v4, hKey);
    if ( Long )
    {
      v3 = (unsigned __int16)Long | 0x80070000;
      if ( Long <= 0 )
        v3 = Long;
      v5 = L"ControllerNotifyNewWorkAvailable(): Failed to mark root store as dirty\n";
      goto LABEL_3;
    }
  }
  v3 = 0;
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003c90  push    rbx
0x180003c92  sub     rsp, 20h
0x180003c96  and     [rsp+28h+hKey], 0
0x180003c9c  lea     rcx, [rsp+28h+hKey]; this
0x180003ca1  call    ?NGENServiceDirtyStateKey@NGENService@@YAJPEAPEAUHKEY__@@@Z; NGENService::NGENServiceDirtyStateKey(HKEY__ * *)
0x180003ca6  mov     ebx, eax
0x180003ca8  test    eax, eax
0x180003caa  jns     short loc_180003CBA
0x180003cac  lea     rcx, aControllernoti_1; "ControllerNotifyNewWorkAvailable(): Fai"...
0x180003cb3  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180003cb8  jmp     short loc_180003D10
0x180003cba  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, 0; bool NGENService::g_bProcessNGENService
0x180003cc1  jz      short loc_180003CD9
0x180003cc3  xor     ecx, ecx; unsigned int
0x180003cc5  call    ?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z; NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)
0x180003cca  mov     ebx, eax
0x180003ccc  test    eax, eax
0x180003cce  jns     short loc_180003D0E
0x180003cd0  lea     rcx, aControllernoti; "ControllerNotifyNewWorkAvailable(): Fai"...
0x180003cd7  jmp     short loc_180003CB3
0x180003cd9  mov     r9, [rsp+28h+hKey]; HKEY
0x180003cde  lea     rcx, aRootstoredirty; "RootstoreDirty"
0x180003ce5  mov     edx, 1; int
0x180003cea  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x180003cef  test    eax, eax
0x180003cf1  jz      short loc_180003D0E
0x180003cf3  movzx   ebx, ax
0x180003cf6  or      ebx, 80070000h
0x180003cfc  test    eax, eax
0x180003cfe  cmovle  ebx, eax
0x180003d01  test    ebx, ebx
0x180003d03  jns     short loc_180003D0E
0x180003d05  lea     rcx, aControllernoti_0; "ControllerNotifyNewWorkAvailable(): Fai"...
0x180003d0c  jmp     short loc_180003CB3
0x180003d0e  xor     ebx, ebx
0x180003d10  mov     rcx, [rsp+28h+hKey]; hKey
0x180003d15  test    rcx, rcx
0x180003d18  jz      short loc_180003D20
0x180003d1a  call    cs:__imp_RegCloseKey
0x180003d20  mov     eax, ebx
0x180003d22  add     rsp, 20h
0x180003d26  pop     rbx
0x180003d27  retn
```
