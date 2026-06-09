# CSettingsManager::GetDword(DwmSettingType,ushort const *,ulong *)

- ea: `0x1400036e4`
- end: `0x140003813`
- name: `?GetDword@CSettingsManager@@AEAAJW4DwmSettingType@@PEBGPEAK@Z`
- size: `303`
- prototype: `int __high(enum DwmSettingType, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003680`
- `0x1400036d0`
- `0x14000d650`

## callees

- `0x1400036e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000370d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000370d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003786`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000377a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400037d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000377a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400037d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003737`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003808`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003737`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003808`

## pseudocode

```c
__int64 __fastcall CSettingsManager::GetDword(__int64 a1, int a2, const WCHAR *a3, BYTE *a4)
{
  LSTATUS v8; // ebx
  LSTATUS ValueW; // eax
  HKEY v11; // rcx
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF

  cbData = 4;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
  if ( !a2 )
  {
    v8 = RegQueryValueExW(*(HKEY *)(a1 + 8), a3, 0, 0, a4, &cbData);
    if ( !v8 )
      goto LABEL_5;
    cbData = 4;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\DWM", a3, 0x20000010u, 0, a4, &cbData);
    goto LABEL_4;
  }
  v8 = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\DWM", a3, 0x20000010u, 0, a4, &cbData);
  if ( v8 )
  {
    v11 = *(HKEY *)(a1 + 16);
    cbData = 4;
    ValueW = RegQueryValueExW(v11, a3, 0, 0, a4, &cbData);
LABEL_4:
    v8 = ValueW;
  }
LABEL_5:
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400036e4  mov     [rsp+arg_0], rbx
0x1400036e9  mov     [rsp+arg_10], rbp
0x1400036ee  push    rsi
0x1400036ef  push    rdi
0x1400036f0  push    r14
0x1400036f2  sub     rsp, 40h
0x1400036f6  mov     rbp, rcx
0x1400036f9  mov     [rsp+58h+cbData], 4
0x140003701  add     rcx, 30h ; '0'; SRWLock
0x140003705  mov     rdi, r9
0x140003708  mov     rsi, r8
0x14000370b  mov     ebx, edx
0x14000370d  call    cs:__imp_AcquireSRWLockShared
0x140003713  lea     rax, [rsp+58h+cbData]
0x140003718  test    ebx, ebx
0x14000371a  jnz     loc_1400037AE
0x140003720  mov     rcx, [rbp+8]; hKey
0x140003724  xor     r9d, r9d; lpType
0x140003727  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14000372c  xor     r8d, r8d; lpReserved
0x14000372f  mov     rdx, rsi; lpValueName
0x140003732  mov     [rsp+58h+lpData], rdi; lpData
0x140003737  call    cs:__imp_RegQueryValueExW
0x14000373d  mov     ebx, eax
0x14000373f  test    eax, eax
0x140003741  jz      short loc_140003782
0x140003743  lea     rax, [rsp+58h+cbData]
0x140003748  mov     [rsp+58h+cbData], 4
0x140003750  mov     [rsp+58h+pcbData], rax; pcbData
0x140003755  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\DWM"
0x14000375c  mov     [rsp+58h+lpcbData], rdi; pvData
0x140003761  mov     r9d, 20000010h; dwFlags
0x140003767  mov     r8, rsi; lpValue
0x14000376a  mov     [rsp+58h+lpData], 0; pdwType
0x140003773  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000377a  call    cs:__imp_RegGetValueW
0x140003780  mov     ebx, eax
0x140003782  lea     rcx, [rbp+30h]; SRWLock
0x140003786  call    cs:__imp_ReleaseSRWLockShared
0x14000378c  test    ebx, ebx
0x14000378e  jle     short loc_140003799
0x140003790  movzx   ebx, bx
0x140003793  or      ebx, 80070000h
0x140003799  mov     rbp, [rsp+58h+arg_10]
0x14000379e  mov     eax, ebx
0x1400037a0  mov     rbx, [rsp+58h+arg_0]
0x1400037a5  add     rsp, 40h
0x1400037a9  pop     r14
0x1400037ab  pop     rdi
0x1400037ac  pop     rsi
0x1400037ad  retn
0x1400037ae  mov     [rsp+58h+pcbData], rax; pcbData
0x1400037b3  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1400037ba  mov     [rsp+58h+lpcbData], rdi; pvData
0x1400037bf  mov     r9d, 20000010h; dwFlags
0x1400037c5  mov     r8, rsi; lpValue
0x1400037c8  mov     [rsp+58h+lpData], 0; pdwType
0x1400037d1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400037d8  call    cs:__imp_RegGetValueW
0x1400037de  mov     ebx, eax
0x1400037e0  test    eax, eax
0x1400037e2  jz      short loc_140003782
0x1400037e4  mov     rcx, [rbp+10h]; hKey
0x1400037e8  lea     rax, [rsp+58h+cbData]
0x1400037ed  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1400037f2  xor     r9d, r9d; lpType
0x1400037f5  xor     r8d, r8d; lpReserved
0x1400037f8  mov     [rsp+58h+lpData], rdi; lpData
0x1400037fd  mov     rdx, rsi; lpValueName
0x140003800  mov     [rsp+58h+cbData], 4
0x140003808  call    cs:__imp_RegQueryValueExW
0x14000380e  jmp     loc_140003780
```
