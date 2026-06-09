# CSettingsManager::SetDword(DwmSettingType,ushort const *,ulong)

- ea: `0x14000d744`
- end: `0x14000d7df`
- name: `?SetDword@CSettingsManager@@AEAAJW4DwmSettingType@@PEBGK@Z`
- size: `155`
- prototype: `int __high(enum DwmSettingType, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d7f0`

## callees

- `0x140002e6c`
- `0x14000d744`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d765`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d765`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000d7c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000d7c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d78a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d78a`

## pseudocode

```c
__int64 __fastcall CSettingsManager::SetDword(__int64 a1, __int64 a2, const WCHAR *a3, int a4)
{
  RTL_SRWLOCK *v4; // rsi
  LSTATUS v7; // eax
  signed int v8; // ebx
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  v4 = (RTL_SRWLOCK *)(a1 + 48);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
  v7 = RegSetValueExW(*(HKEY *)(a1 + 8), a3, 0, 4u, (const BYTE *)&Data, 4u);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0xE7u, 0);
  ReleaseSRWLockShared(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000d744  mov     [rsp+arg_0], rbx
0x14000d749  mov     [rsp+arg_8], rsi
0x14000d74e  mov     [rsp+Data], r9d
0x14000d753  push    rdi
0x14000d754  sub     rsp, 30h
0x14000d758  lea     rsi, [rcx+30h]
0x14000d75c  mov     rbx, rcx
0x14000d75f  mov     rcx, rsi; SRWLock
0x14000d762  mov     rdi, r8
0x14000d765  call    cs:__imp_AcquireSRWLockShared
0x14000d76b  mov     rcx, [rbx+8]; hKey
0x14000d76f  lea     rax, [rsp+38h+Data]
0x14000d774  mov     r9d, 4; dwType
0x14000d77a  xor     r8d, r8d; Reserved
0x14000d77d  mov     [rsp+38h+cbData], r9d; cbData
0x14000d782  mov     rdx, rdi; lpValueName
0x14000d785  mov     [rsp+38h+lpData], rax; lpData
0x14000d78a  call    cs:__imp_RegSetValueExW
0x14000d790  mov     ebx, eax
0x14000d792  test    eax, eax
0x14000d794  jle     short loc_14000D79F
0x14000d796  movzx   ebx, ax
0x14000d799  or      ebx, 80070000h
0x14000d79f  test    ebx, ebx
0x14000d7a1  jns     short loc_14000D7C4
0x14000d7a3  xor     edx, edx; int *
0x14000d7a5  mov     qword ptr [rsp+38h+cbData], 0; void *
0x14000d7ae  mov     r9d, ebx; int
0x14000d7b1  mov     dword ptr [rsp+38h+lpData], 0E7h; unsigned int
0x14000d7b9  xor     r8d, r8d; unsigned int
0x14000d7bc  lea     ecx, [rdx+14h]; unsigned int
0x14000d7bf  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000d7c4  mov     rcx, rsi; SRWLock
0x14000d7c7  call    cs:__imp_ReleaseSRWLockShared
0x14000d7cd  mov     rsi, [rsp+38h+arg_8]
0x14000d7d2  mov     eax, ebx
0x14000d7d4  mov     rbx, [rsp+38h+arg_0]
0x14000d7d9  add     rsp, 30h
0x14000d7dd  pop     rdi
0x14000d7de  retn
```
