# RearmRegistryNotify(HKEY__ *,void *)

- ea: `0x180011398`
- end: `0x18001141b`
- name: `?RearmRegistryNotify@@YAJPEAUHKEY__@@PEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(HKEY, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011690`

## callees

- `0x180011398`
- `0x18001bc10`
- `0x18001bd24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113ca`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800113b6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800113b6`

## string_xrefs

- `0x1800113f1`: `RearmRegistryNotify`

## pseudocode

```c
__int64 __fastcall RearmRegistryNotify(HKEY a1, void *a2)
{
  LSTATUS v2; // ebx
  CConfigLockLogger *Logger; // rdi
  signed int LastError; // eax

  v2 = RegNotifyChangeKeyValue(a1, 1, 0x10000005u, a2, 1);
  if ( !v2 )
    return 0;
  Logger = CConfigLockLogger::GetLogger();
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  CConfigLockLogger::LogGenericFailure(
    Logger,
    L"RearmRegistryNotify",
    L"RegNotifyChangeKeyValue",
    L"failed to set regnotify",
    LastError);
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180011398  mov     [rsp+arg_0], rbx
0x18001139d  push    rdi
0x18001139e  sub     rsp, 30h
0x1800113a2  mov     eax, 1
0x1800113a7  mov     r9, rdx; hEvent
0x1800113aa  mov     edx, eax; bWatchSubtree
0x1800113ac  mov     [rsp+38h+fAsynchronous], eax; fAsynchronous
0x1800113b0  mov     r8d, 10000005h; dwNotifyFilter
0x1800113b6  call    cs:__imp_RegNotifyChangeKeyValue
0x1800113bc  mov     ebx, eax
0x1800113be  test    eax, eax
0x1800113c0  jz      short loc_18001140E
0x1800113c2  call    ?GetLogger@CConfigLockLogger@@SAPEAV1@XZ; CConfigLockLogger::GetLogger(void)
0x1800113c7  mov     rdi, rax
0x1800113ca  call    cs:__imp_GetLastError
0x1800113d0  test    eax, eax
0x1800113d2  jle     short loc_1800113DC
0x1800113d4  movzx   eax, ax
0x1800113d7  or      eax, 80070000h
0x1800113dc  lea     r9, aFailedToSetReg; "failed to set regnotify"
0x1800113e3  mov     [rsp+38h+fAsynchronous], eax; int
0x1800113e7  lea     r8, aRegnotifychang; "RegNotifyChangeKeyValue"
0x1800113ee  mov     rcx, rdi; this
0x1800113f1  lea     rdx, aRearmregistryn; "RearmRegistryNotify"
0x1800113f8  call    ?LogGenericFailure@CConfigLockLogger@@QEAAXPEBG00J@Z; CConfigLockLogger::LogGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800113fd  test    ebx, ebx
0x1800113ff  jle     short loc_18001140A
0x180011401  movzx   ebx, bx
0x180011404  or      ebx, 80070000h
0x18001140a  mov     eax, ebx
0x18001140c  jmp     short loc_180011410
0x18001140e  xor     eax, eax
0x180011410  mov     rbx, [rsp+38h+arg_0]
0x180011415  add     rsp, 30h
0x180011419  pop     rdi
0x18001141a  retn
```
