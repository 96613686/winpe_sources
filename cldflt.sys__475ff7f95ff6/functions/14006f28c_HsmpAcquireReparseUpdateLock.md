# HsmpAcquireReparseUpdateLock

- ea: `0x14006f28c`
- end: `0x14006f2c0`
- name: `HsmpAcquireReparseUpdateLock`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: `reparse_path, installer_update`

## callers

- `0x140002aec`
- `0x140003cf0`
- `0x14004357c`
- `0x140043c9c`
- `0x140047c20`
- `0x14004cb90`
- `0x14004dff0`
- `0x14005fde4`
- `0x14006e714`
- `0x14007828c`
- `0x14007b72c`
- `0x14007fb2c`
- `0x1400845b0`

## callees

- `0x14006f28c`

## import_xrefs

- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f29e`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f29e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f2b2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f2b2`

## pseudocode

```c
__int64 __fastcall HsmpAcquireReparseUpdateLock(__int64 a1, char a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 16) + 24LL;
  if ( a2 )
    return FltAcquirePushLockExclusiveEx(v2, 0);
  else
    return FltAcquirePushLockSharedEx(v2, 0);
}

```

## disassembly

```asm
0x14006f28c  sub     rsp, 28h
0x14006f290  mov     rcx, [rcx+10h]
0x14006f294  add     rcx, 18h
0x14006f298  test    dl, dl
0x14006f29a  jnz     short loc_14006F2B0
0x14006f29c  xor     edx, edx
0x14006f29e  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f2a5  nop     dword ptr [rax+rax+00h]
0x14006f2aa  add     rsp, 28h
0x14006f2ae  retn
0x14006f2b0  xor     edx, edx
0x14006f2b2  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006f2b9  nop     dword ptr [rax+rax+00h]
0x14006f2be  jmp     short loc_14006F2AA
```
