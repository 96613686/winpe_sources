# CloudDataRestoreOobe::_CleanupBackupData(void)

- ea: `0x18001947c`
- end: `0x1800194d2`
- name: `?_CleanupBackupData@CloudDataRestoreOobe@@CAJXZ`
- size: `86`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800179d0`

## callees

- `0x18000b098`
- `0x18001947c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180019495`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180019495`

## string_xrefs

- `0x1800194b3`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`

## pseudocode

```c
__int64 CloudDataRestoreOobe::_CleanupBackupData(void)
{
  int v0; // eax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = RegDeleteKeyValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SystemMetaData",
         L"CloudRestoreProfileId");
  if ( v0 > 0 )
    v0 = (unsigned __int16)v0 | 0x80070000;
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
      (const char *)(unsigned int)v0,
      v2);
  return 0;
}

```

## disassembly

```asm
0x18001947c  sub     rsp, 28h
0x180019480  lea     r8, aCloudrestorepr; "CloudRestoreProfileId"
0x180019487  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001948e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180019495  call    cs:__imp_RegDeleteKeyValueW
0x18001949b  test    eax, eax
0x18001949d  jle     short loc_1800194A7
0x18001949f  movzx   eax, ax
0x1800194a2  or      eax, 80070000h
0x1800194a7  mov     rcx, [rsp+28h]; this
0x1800194ac  test    eax, eax
0x1800194ae  jns     short loc_1800194C4
0x1800194b0  mov     r9d, eax; char *
0x1800194b3  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800194ba  mov     edx, 86h; void *
0x1800194bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800194c4  xor     eax, eax
0x1800194c6  jmp     short loc_1800194CC
0x1800194c8  mov     eax, [rsp+28h+arg_0]
0x1800194cc  add     rsp, 28h
0x1800194d0  retn
```
