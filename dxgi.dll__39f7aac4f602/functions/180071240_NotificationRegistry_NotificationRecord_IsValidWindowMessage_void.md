# NotificationRegistry::NotificationRecord::IsValidWindowMessage(void)

- ea: `0x180071240`
- end: `0x180071286`
- name: `?IsValidWindowMessage@NotificationRecord@NotificationRegistry@@QEBA_NXZ`
- size: `70`
- prototype: `bool __fastcall(NotificationRegistry::NotificationRecord *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001d41c`
- `0x18002e778`

## callees

- `0x180071240`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007126f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007126f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180071269`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180071269`

## pseudocode

```c
bool __fastcall NotificationRegistry::NotificationRecord::IsValidWindowMessage(
        NotificationRegistry::NotificationRecord *this)
{
  HWND v1; // rcx
  bool result; // al
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  if ( *((_DWORD *)this + 1) )
  {
    v1 = (HWND)*((_QWORD *)this + 1);
    if ( v1 )
    {
      if ( v1 != HWND_BROADCAST )
      {
        dwProcessId = 0;
        GetWindowThreadProcessId(v1, &dwProcessId);
        if ( dwProcessId == GetCurrentProcessId() )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180071240  sub     rsp, 28h
0x180071244  cmp     dword ptr [rcx+4], 0
0x180071248  jz      short loc_18007127F
0x18007124a  mov     rcx, [rcx+8]; hWnd
0x18007124e  test    rcx, rcx
0x180071251  jz      short loc_18007127F
0x180071253  cmp     rcx, 0FFFFh
0x18007125a  jz      short loc_18007127F
0x18007125c  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180071261  mov     [rsp+28h+dwProcessId], 0
0x180071269  call    cs:__imp_GetWindowThreadProcessId
0x18007126f  call    cs:__imp_GetCurrentProcessId
0x180071275  cmp     [rsp+28h+dwProcessId], eax
0x180071279  jnz     short loc_18007127F
0x18007127b  mov     al, 1
0x18007127d  jmp     short loc_180071281
0x18007127f  xor     al, al
0x180071281  add     rsp, 28h
0x180071285  retn
```
