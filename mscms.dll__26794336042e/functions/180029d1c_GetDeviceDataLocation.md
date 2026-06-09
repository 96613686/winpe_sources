# GetDeviceDataLocation

- ea: `0x180029d1c`
- end: `0x180029dea`
- name: `GetDeviceDataLocation`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001e774`
- `0x18001f9d4`
- `0x18004107c`

## callees

- `0x180029d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029d60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029d60`

## string_xrefs

- `0x180029d22`: `CopyFiles\ICM`

## pseudocode

```c
__int64 __fastcall GetDeviceDataLocation(int a1, int a2, _QWORD *a3, unsigned __int16 **a4)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax

  v4 = a2 - 1;
  if ( !v4 )
    goto LABEL_13;
  v5 = v4 - 1;
  if ( !v5 )
  {
    *a3 = gszICMDeviceDataKey;
    v11 = gszICMProfileEnumMode;
    goto LABEL_16;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    *a3 = gszICMDeviceDataKey;
    v11 = gszICMUsePerUserProfiles;
    goto LABEL_16;
  }
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_11;
  v8 = v7 - 1;
  if ( !v8 )
  {
    *a3 = gszICMProfileListKey;
    *a4 = gszICMProfileListValueAdvancedColor;
    if ( a1 == 1835955314 )
      return 1;
LABEL_13:
    v11 = gszFiles;
    if ( a1 != 1886549106 )
      v11 = gszICMProfileListValue;
    goto LABEL_15;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    *a3 = gszICMDeviceDataKey;
    *a4 = gszICMProfilesSnapshotValueAdvancedColor;
    if ( a1 != 1835955314 )
    {
LABEL_11:
      *a3 = gszICMDeviceDataKey;
      v11 = gszICMProfilesSnapshotValue;
LABEL_16:
      *a4 = v11;
    }
    return 1;
  }
  if ( v9 == 1 )
  {
    v11 = gszICMDefaultWideColor;
LABEL_15:
    *a3 = gszICMProfileListKey;
    goto LABEL_16;
  }
  v10 = 0;
  SetLastError(0x57u);
  return v10;
}

```

## disassembly

```asm
0x180029d1c  push    rbx
0x180029d1e  sub     rsp, 20h
0x180029d22  lea     r10, gszICMProfileListKey; "CopyFiles\\ICM"
0x180029d29  sub     edx, 1
0x180029d2c  jz      short loc_180029DA7
0x180029d2e  lea     rax, gszICMDeviceDataKey; "ICMData"
0x180029d35  sub     edx, 1
0x180029d38  jz      loc_180029DDE
0x180029d3e  sub     edx, 1
0x180029d41  jz      loc_180029DD2
0x180029d47  sub     edx, 1
0x180029d4a  jz      short loc_180029D86
0x180029d4c  sub     edx, 1
0x180029d4f  jz      short loc_180029D92
0x180029d51  sub     edx, 1
0x180029d54  jz      short loc_180029D71
0x180029d56  cmp     edx, 1
0x180029d59  jz      short loc_180029D68
0x180029d5b  xor     ebx, ebx
0x180029d5d  lea     ecx, [rbx+57h]; dwErrCode
0x180029d60  call    cs:__imp_SetLastError
0x180029d66  jmp     short loc_180029DCA
0x180029d68  lea     rax, gszICMDefaultWideColor; "ICMDefaultWideColor"
0x180029d6f  jmp     short loc_180029DBF
0x180029d71  mov     [r8], rax
0x180029d74  lea     rdx, gszICMProfilesSnapshotValueAdvancedColor; "ICMProfileSnapshotAC"
0x180029d7b  mov     [r9], rdx
0x180029d7e  cmp     ecx, 6D6E7472h
0x180029d84  jz      short loc_180029DC5
0x180029d86  mov     [r8], rax
0x180029d89  lea     rax, gszICMProfilesSnapshotValue; "ICMProfileSnapshot"
0x180029d90  jmp     short loc_180029DC2
0x180029d92  mov     [r8], r10
0x180029d95  lea     rax, gszICMProfileListValueAdvancedColor; "ICMProfileAC"
0x180029d9c  mov     [r9], rax
0x180029d9f  cmp     ecx, 6D6E7472h
0x180029da5  jz      short loc_180029DC5
0x180029da7  cmp     ecx, 70727472h
0x180029dad  lea     rax, gszFiles; "Files"
0x180029db4  lea     rdx, gszICMProfileListValue; "ICMProfile"
0x180029dbb  cmovnz  rax, rdx
0x180029dbf  mov     [r8], r10
0x180029dc2  mov     [r9], rax
0x180029dc5  mov     ebx, 1
0x180029dca  mov     eax, ebx
0x180029dcc  add     rsp, 20h
0x180029dd0  pop     rbx
0x180029dd1  retn
0x180029dd2  mov     [r8], rax
0x180029dd5  lea     rax, gszICMUsePerUserProfiles; "UsePerUserProfiles"
0x180029ddc  jmp     short loc_180029DC2
0x180029dde  mov     [r8], rax
0x180029de1  lea     rax, gszICMProfileEnumMode; "ProfileEnumMode"
0x180029de8  jmp     short loc_180029DC2
```
