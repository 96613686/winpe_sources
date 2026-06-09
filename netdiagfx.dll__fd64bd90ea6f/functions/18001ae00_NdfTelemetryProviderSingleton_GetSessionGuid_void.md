# NdfTelemetryProviderSingleton::GetSessionGuid(void)

- ea: `0x18001ae00`
- end: `0x18001aee3`
- name: `?GetSessionGuid@NdfTelemetryProviderSingleton@@QEAAAEBU_GUID@@XZ`
- size: `227`
- prototype: `const struct _GUID *__fastcall(NdfTelemetryProviderSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018ae4`

## callees

- `0x18001ae00`
- `0x18001c930`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ae66`
- `KERNEL32!GetLastError` at `0x18001ae92`
- `KERNEL32!GetLastError` at `0x18001ae66`
- `KERNEL32!GetLastError` at `0x18001ae92`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001aeb2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001aeb2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001aecd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001aecd`
- `KERNEL32!CloseHandle` at `0x18001ae7e`
- `KERNEL32!CloseHandle` at `0x18001ae7e`
- `KERNEL32!OpenFileMappingW` at `0x18001ae25`
- `KERNEL32!OpenFileMappingW` at `0x18001ae25`
- `KERNEL32!MapViewOfFile` at `0x18001ae47`
- `KERNEL32!MapViewOfFile` at `0x18001ae47`
- `KERNEL32!UnmapViewOfFile` at `0x18001ae5e`
- `KERNEL32!UnmapViewOfFile` at `0x18001ae5e`

## pseudocode

```c
const struct _GUID *__fastcall NdfTelemetryProviderSingleton::GetSessionGuid(NdfTelemetryProviderSingleton *this)
{
  __int64 v1; // rbp
  __int64 v2; // rbx
  HANDLE v3; // rax
  NdfTelemetryProviderSingleton *v4; // rcx
  void *v5; // rsi
  __int64 *v6; // rax
  signed int v7; // edi
  signed int LastError; // eax
  signed int v9; // eax

  v1 = *(_QWORD *)&GUID_NULL.Data1;
  v2 = *(_QWORD *)GUID_NULL.Data4;
  v3 = OpenFileMappingW(4u, 0, L"NdfSessionFile");
  v5 = v3;
  if ( v3 )
  {
    v6 = (__int64 *)MapViewOfFile(v3, 4u, 0, 0, 0x10000u);
    if ( v6 )
    {
      v1 = *v6;
      v7 = 0;
      v2 = v6[1];
      UnmapViewOfFile(v6);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v5);
  }
  else
  {
    NdfTelemetryProviderSingleton::SetSessionGuid(v4, &pguid);
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( v7 >= 0 )
  {
    AcquireSRWLockExclusive(&stru_180041D18);
    *(_QWORD *)&pguid.Data1 = v1;
    *(_QWORD *)pguid.Data4 = v2;
    ReleaseSRWLockExclusive(&stru_180041D18);
  }
  return &pguid;
}

```

## disassembly

```asm
0x18001ae00  push    rbx
0x18001ae02  push    rbp
0x18001ae03  push    rsi
0x18001ae04  push    rdi
0x18001ae05  sub     rsp, 38h
0x18001ae09  mov     rbp, qword ptr cs:GUID_NULL.Data1
0x18001ae10  lea     r8, Name; "NdfSessionFile"
0x18001ae17  mov     rbx, qword ptr cs:GUID_NULL.Data4
0x18001ae1e  xor     edx, edx; bInheritHandle
0x18001ae20  lea     edi, [rdx+4]
0x18001ae23  mov     ecx, edi; dwDesiredAccess
0x18001ae25  call    cs:__imp_OpenFileMappingW
0x18001ae2b  mov     rsi, rax
0x18001ae2e  test    rax, rax
0x18001ae31  jz      short loc_18001AE86
0x18001ae33  xor     r9d, r9d; dwFileOffsetLow
0x18001ae36  mov     [rsp+58h+dwNumberOfBytesToMap], 10000h; dwNumberOfBytesToMap
0x18001ae3f  xor     r8d, r8d; dwFileOffsetHigh
0x18001ae42  mov     edx, edi; dwDesiredAccess
0x18001ae44  mov     rcx, rax; hFileMappingObject
0x18001ae47  call    cs:__imp_MapViewOfFile
0x18001ae4d  test    rax, rax
0x18001ae50  jz      short loc_18001AE66
0x18001ae52  mov     rbp, [rax]
0x18001ae55  xor     edi, edi
0x18001ae57  mov     rbx, [rax+8]
0x18001ae5b  mov     rcx, rax; lpBaseAddress
0x18001ae5e  call    cs:__imp_UnmapViewOfFile
0x18001ae64  jmp     short loc_18001AE7B
0x18001ae66  call    cs:__imp_GetLastError
0x18001ae6c  mov     edi, eax
0x18001ae6e  test    eax, eax
0x18001ae70  jle     short loc_18001AE7B
0x18001ae72  movzx   edi, ax
0x18001ae75  or      edi, 80070000h
0x18001ae7b  mov     rcx, rsi; hObject
0x18001ae7e  call    cs:__imp_CloseHandle
0x18001ae84  jmp     short loc_18001AEA7
0x18001ae86  lea     rdx, pguid; struct _GUID *
0x18001ae8d  call    ?SetSessionGuid@NdfTelemetryProviderSingleton@@QEAAXAEAU_GUID@@@Z; NdfTelemetryProviderSingleton::SetSessionGuid(_GUID &)
0x18001ae92  call    cs:__imp_GetLastError
0x18001ae98  mov     edi, eax
0x18001ae9a  test    eax, eax
0x18001ae9c  jle     short loc_18001AEA7
0x18001ae9e  movzx   edi, ax
0x18001aea1  or      edi, 80070000h
0x18001aea7  test    edi, edi
0x18001aea9  js      short loc_18001AED3
0x18001aeab  lea     rcx, stru_180041D18; SRWLock
0x18001aeb2  call    cs:__imp_AcquireSRWLockExclusive
0x18001aeb8  lea     rcx, stru_180041D18; SRWLock
0x18001aebf  mov     qword ptr cs:pguid.Data1, rbp
0x18001aec6  mov     qword ptr cs:pguid.Data4, rbx
0x18001aecd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001aed3  lea     rax, pguid
0x18001aeda  add     rsp, 38h
0x18001aede  pop     rdi
0x18001aedf  pop     rsi
0x18001aee0  pop     rbp
0x18001aee1  pop     rbx
0x18001aee2  retn
```
