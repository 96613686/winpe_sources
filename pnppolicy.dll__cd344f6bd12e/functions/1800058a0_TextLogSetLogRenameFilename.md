# TextLogSetLogRenameFilename

- ea: `0x1800058a0`
- end: `0x180005968`
- name: `TextLogSetLogRenameFilename`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800054d4`

## callees

- `0x180003820`
- `0x1800058a0`
- `0x180006fb0`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180005920`
- `ntdll!NtDeleteValueKey` at `0x180005920`
- `ntdll!RtlInitUnicodeString` at `0x180005911`
- `ntdll!RtlInitUnicodeString` at `0x180005911`
- `ntdll!NtClose` at `0x180005948`
- `ntdll!NtClose` at `0x180005948`
- `ntdll!RtlNtStatusToDosError` at `0x18000592c`
- `ntdll!RtlNtStatusToDosError` at `0x18000592c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005950`

## string_xrefs

- `0x1800058db`: `SYSTEM\Setup\SetupapiLogRename`

## pseudocode

```c
_BOOL8 __fastcall TextLogSetLogRenameFilename(__int64 a1, void *a2, __int64 a3)
{
  const WCHAR *FileTitle; // rdi
  ULONG v4; // eax
  ULONG v5; // ebx
  int v6; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp+10h] BYREF

  KeyHandle = a2;
  FileTitle = *(const WCHAR **)(a1 + 16);
  KeyHandle = 0;
  if ( !TextLogOffline )
    FileTitle = (const WCHAR *)pSetupGetFileTitle(FileTitle);
  v4 = pSetupOpenKey((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogRename", a3, 2u, &KeyHandle);
  v5 = 0;
  if ( v4 )
  {
    if ( v4 != 2 )
      v5 = v4;
  }
  else
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, FileTitle);
    v6 = NtDeleteValueKey((HANDLE)(unsigned int)KeyHandle, &DestinationString);
    if ( v6 < 0 )
      v5 = RtlNtStatusToDosError(v6);
    if ( v5 == 2 )
      v5 = 0;
  }
  if ( KeyHandle )
    NtClose((HANDLE)(unsigned int)KeyHandle);
  SetLastError(v5);
  return v5 == 0;
}

```

## disassembly

```asm
0x1800058a0  mov     [rsp+arg_0], rbx
0x1800058a5  mov     [rsp+KeyHandle], rdx
0x1800058aa  push    rdi
0x1800058ab  sub     rsp, 40h
0x1800058af  cmp     cs:TextLogOffline, 0
0x1800058b6  mov     rdi, [rcx+10h]
0x1800058ba  mov     [rsp+48h+KeyHandle], 0
0x1800058c3  jnz     short loc_1800058D0
0x1800058c5  mov     rcx, rdi
0x1800058c8  call    pSetupGetFileTitle
0x1800058cd  mov     rdi, rax
0x1800058d0  lea     rax, [rsp+48h+KeyHandle]
0x1800058d5  mov     r9d, 2
0x1800058db  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupapiLogRename"
0x1800058e2  mov     [rsp+48h+var_28], rax
0x1800058e7  mov     rcx, 0FFFFFFFF80000002h
0x1800058ee  call    pSetupOpenKey
0x1800058f3  xor     ebx, ebx
0x1800058f5  test    eax, eax
0x1800058f7  jz      short loc_180005901
0x1800058f9  cmp     eax, 2
0x1800058fc  cmovnz  ebx, eax
0x1800058ff  jmp     short loc_18000593C
0x180005901  xorps   xmm0, xmm0
0x180005904  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180005909  mov     rdx, rdi; SourceString
0x18000590c  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180005911  call    cs:__imp_RtlInitUnicodeString
0x180005917  mov     ecx, dword ptr [rsp+48h+KeyHandle]; KeyHandle
0x18000591b  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x180005920  call    cs:__imp_NtDeleteValueKey
0x180005926  test    eax, eax
0x180005928  jns     short loc_180005934
0x18000592a  mov     ecx, eax; Status
0x18000592c  call    cs:__imp_RtlNtStatusToDosError
0x180005932  mov     ebx, eax
0x180005934  xor     ecx, ecx
0x180005936  cmp     ebx, 2
0x180005939  cmovz   ebx, ecx
0x18000593c  cmp     [rsp+48h+KeyHandle], 0
0x180005942  jz      short loc_18000594E
0x180005944  mov     ecx, dword ptr [rsp+48h+KeyHandle]; Handle
0x180005948  call    cs:__imp_NtClose
0x18000594e  mov     ecx, ebx; dwErrCode
0x180005950  call    cs:__imp_SetLastError
0x180005956  xor     eax, eax
0x180005958  test    ebx, ebx
0x18000595a  mov     rbx, [rsp+48h+arg_0]
0x18000595f  setz    al
0x180005962  add     rsp, 40h
0x180005966  pop     rdi
0x180005967  retn
```
