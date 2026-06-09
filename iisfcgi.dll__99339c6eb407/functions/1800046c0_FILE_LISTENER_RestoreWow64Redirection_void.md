# FILE_LISTENER::RestoreWow64Redirection(void *)

- ea: `0x1800046c0`
- end: `0x1800046f8`
- name: `?RestoreWow64Redirection@FILE_LISTENER@@SAJPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000401c`
- `0x1800042f0`

## callees

- `0x1800046c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046db`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800046d1`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800046d1`

## pseudocode

```c
__int64 __fastcall FILE_LISTENER::RestoreWow64Redirection(void *a1)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( FILE_LISTENER::sm_fIsWow64 == 1 && !Wow64RevertWow64FsRedirection(a1) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1800046c0  push    rbx
0x1800046c2  sub     rsp, 20h
0x1800046c6  xor     ebx, ebx
0x1800046c8  cmp     cs:?sm_fIsWow64@FILE_LISTENER@@0HA, 1; int FILE_LISTENER::sm_fIsWow64
0x1800046cf  jnz     short loc_1800046F0
0x1800046d1  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1800046d7  test    eax, eax
0x1800046d9  jnz     short loc_1800046F0
0x1800046db  call    cs:__imp_GetLastError
0x1800046e1  mov     ebx, eax
0x1800046e3  test    eax, eax
0x1800046e5  jle     short loc_1800046F0
0x1800046e7  movzx   ebx, ax
0x1800046ea  or      ebx, 80070000h
0x1800046f0  mov     eax, ebx
0x1800046f2  add     rsp, 20h
0x1800046f6  pop     rbx
0x1800046f7  retn
```
