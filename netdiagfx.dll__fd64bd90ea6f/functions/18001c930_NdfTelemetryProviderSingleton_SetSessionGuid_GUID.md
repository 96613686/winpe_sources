# NdfTelemetryProviderSingleton::SetSessionGuid(_GUID &)

- ea: `0x18001c930`
- end: `0x18001c9ee`
- name: `?SetSessionGuid@NdfTelemetryProviderSingleton@@QEAAXAEAU_GUID@@@Z`
- size: `190`
- prototype: `void __fastcall(NdfTelemetryProviderSingleton *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001ae00`

## callees

- `0x18001c930`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c944`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c944`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c95c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c95c`
- `KERNEL32!OpenFileMappingW` at `0x18001c971`
- `KERNEL32!OpenFileMappingW` at `0x18001c971`
- `KERNEL32!MapViewOfFile` at `0x18001c9c4`
- `KERNEL32!MapViewOfFile` at `0x18001c9c4`
- `KERNEL32!UnmapViewOfFile` at `0x18001c9dd`
- `KERNEL32!UnmapViewOfFile` at `0x18001c9dd`
- `KERNEL32!CreateFileMappingW` at `0x18001c997`
- `KERNEL32!CreateFileMappingW` at `0x18001c997`

## pseudocode

```c
void __fastcall NdfTelemetryProviderSingleton::SetSessionGuid(NdfTelemetryProviderSingleton *this, struct _GUID *a2)
{
  HANDLE FileMappingW; // rax
  GUID *v4; // rax

  AcquireSRWLockExclusive(&stru_180041D18);
  pguid = *a2;
  ReleaseSRWLockExclusive(&stru_180041D18);
  if ( OpenFileMappingW(4u, 0, L"NdfSessionFile") )
  {
    FileMappingW = (HANDLE)qword_180041DA8;
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x10000u, L"NdfSessionFile");
    qword_180041DA8 = (__int64)FileMappingW;
  }
  if ( FileMappingW )
  {
    v4 = (GUID *)MapViewOfFile(FileMappingW, 2u, 0, 0, 0x10000u);
    if ( v4 )
    {
      *v4 = pguid;
      UnmapViewOfFile(v4);
    }
  }
}

```

## disassembly

```asm
0x18001c930  mov     [rsp+arg_0], rbx
0x18001c935  push    rsi
0x18001c936  sub     rsp, 30h
0x18001c93a  lea     rcx, stru_180041D18; SRWLock
0x18001c941  mov     rbx, rdx
0x18001c944  call    cs:__imp_AcquireSRWLockExclusive
0x18001c94a  movaps  xmm0, xmmword ptr [rbx]
0x18001c94d  lea     rcx, stru_180041D18; SRWLock
0x18001c954  movdqu  xmmword ptr cs:pguid.Data1, xmm0
0x18001c95c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c962  xor     edx, edx; bInheritHandle
0x18001c964  lea     rsi, Name; "NdfSessionFile"
0x18001c96b  mov     r8, rsi; lpName
0x18001c96e  lea     ecx, [rdx+4]; dwDesiredAccess
0x18001c971  call    cs:__imp_OpenFileMappingW
0x18001c977  mov     ebx, 10000h
0x18001c97c  test    rax, rax
0x18001c97f  jnz     short loc_18001C9A6
0x18001c981  mov     [rsp+38h+lpName], rsi; lpName
0x18001c986  lea     r8d, [rax+4]; flProtect
0x18001c98a  xor     r9d, r9d; dwMaximumSizeHigh
0x18001c98d  mov     [rsp+38h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18001c991  xor     edx, edx; lpFileMappingAttributes
0x18001c993  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001c997  call    cs:__imp_CreateFileMappingW
0x18001c99d  mov     cs:qword_180041DA8, rax
0x18001c9a4  jmp     short loc_18001C9AD
0x18001c9a6  mov     rax, cs:qword_180041DA8
0x18001c9ad  test    rax, rax
0x18001c9b0  jz      short loc_18001C9E3
0x18001c9b2  xor     r9d, r9d; dwFileOffsetLow
0x18001c9b5  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18001c9ba  xor     r8d, r8d; dwFileOffsetHigh
0x18001c9bd  mov     rcx, rax; hFileMappingObject
0x18001c9c0  lea     edx, [r9+2]; dwDesiredAccess
0x18001c9c4  call    cs:__imp_MapViewOfFile
0x18001c9ca  test    rax, rax
0x18001c9cd  jz      short loc_18001C9E3
0x18001c9cf  movaps  xmm0, xmmword ptr cs:pguid.Data1
0x18001c9d6  mov     rcx, rax; lpBaseAddress
0x18001c9d9  movdqu  xmmword ptr [rax], xmm0
0x18001c9dd  call    cs:__imp_UnmapViewOfFile
0x18001c9e3  mov     rbx, [rsp+38h+arg_0]
0x18001c9e8  add     rsp, 30h
0x18001c9ec  pop     rsi
0x18001c9ed  retn
```
