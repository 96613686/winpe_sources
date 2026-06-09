# HsmpAcquireReparseUpdateLock

- ea: `0x14006f16c`
- end: `0x14006f1a0`
- name: `HsmpAcquireReparseUpdateLock`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: `reparse_path, installer_update`

## callers

- `0x140002aec`
- `0x140003cf0`
- `0x14004348c`
- `0x140043bac`
- `0x140047b30`
- `0x14004caa0`
- `0x14004ded0`
- `0x14005fcc4`
- `0x14006e5f4`
- `0x14007814c`
- `0x14007b5ec`
- `0x14007f994`
- `0x1400843f8`

## callees

- `0x14006f16c`

## import_xrefs

- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f17e`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f17e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f192`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f192`

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
0x14006f16c  sub     rsp, 28h
0x14006f170  mov     rcx, [rcx+10h]
0x14006f174  add     rcx, 18h
0x14006f178  test    dl, dl
0x14006f17a  jnz     short loc_14006F190
0x14006f17c  xor     edx, edx
0x14006f17e  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f185  nop     dword ptr [rax+rax+00h]
0x14006f18a  add     rsp, 28h
0x14006f18e  retn
0x14006f190  xor     edx, edx
0x14006f192  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006f199  nop     dword ptr [rax+rax+00h]
0x14006f19e  jmp     short loc_14006F18A
```
