# CSettingsManager::RefreshPreferencesAndPolicies(void)

- ea: `0x140002988`
- end: `0x140002c13`
- name: `?RefreshPreferencesAndPolicies@CSettingsManager@@QEAAXXZ`
- size: `651`
- prototype: `void __fastcall(CSettingsManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002630`
- `0x140002850`
- `0x140002fbc`

## callees

- `0x140002988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002a54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002b2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002a54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002b2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002ba5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002ac2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002b66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002ac2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002b66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002a7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002b9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002a7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002b9a`

## pseudocode

```c
void __fastcall CSettingsManager::RefreshPreferencesAndPolicies(CSettingsManager *this)
{
  int v1; // edi
  RTL_SRWLOCK *v2; // r12
  __int64 v4; // rsi
  LSTATUS ValueW; // ebx
  const WCHAR *v6; // r8
  bool v7; // sf
  int v8; // ecx
  int v9; // eax
  __int64 v10; // rsi
  int v11; // edi
  LSTATUS v12; // ebx
  const WCHAR *v13; // rdx
  HKEY v14; // rcx
  bool v15; // sf
  int v16; // ecx
  int v17; // eax
  LPCWSTR lpValue; // [rsp+40h] [rbp-39h]
  _QWORD v19[5]; // [rsp+48h] [rbp-31h]
  LPCWSTR lpValueName; // [rsp+70h] [rbp-9h]
  int v21; // [rsp+78h] [rbp-1h]
  int v22; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v23; // [rsp+80h] [rbp+7h]
  __int64 v24; // [rsp+88h] [rbp+Fh]
  const wchar_t *v25; // [rsp+90h] [rbp+17h]
  __int64 v26; // [rsp+98h] [rbp+1Fh]
  const wchar_t *v27; // [rsp+A0h] [rbp+27h]
  __int64 v28; // [rsp+A8h] [rbp+2Fh]
  DWORD cbData; // [rsp+E0h] [rbp+67h] BYREF
  int Data; // [rsp+E8h] [rbp+6Fh] BYREF

  v1 = *((_DWORD *)this + 16);
  lpValueName = L"UseDPIScaling";
  v2 = (RTL_SRWLOCK *)((char *)this + 48);
  v21 = 1;
  v23 = L"AnimationsShiftKey";
  v22 = 1;
  v25 = L"DisableLockingMemory";
  v4 = 0;
  v24 = 2;
  v27 = L"ModeChangeCurtainUseDebugColor";
  lpValue = L"DisallowAnimations";
  v19[1] = L"DisallowColorizationColorChanges";
  v19[3] = L"DefaultColorizationColorState";
  v26 = 64;
  v28 = 128;
  v19[0] = 1;
  v19[2] = 2;
  v19[4] = 4;
  do
  {
    Data = 0;
    cbData = 4;
    AcquireSRWLockShared(v2);
    ValueW = RegQueryValueExW(*((HKEY *)this + 1), (&lpValueName)[2 * v4], 0, 0, (LPBYTE)&Data, &cbData);
    if ( ValueW )
    {
      v6 = (&lpValueName)[2 * v4];
      cbData = 4;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\DWM",
                 v6,
                 0x20000010u,
                 0,
                 &Data,
                 &cbData);
    }
    ReleaseSRWLockShared(v2);
    v7 = ValueW < 0;
    if ( ValueW > 0 )
      v7 = 1;
    if ( v7 )
      v8 = *(&v22 + 4 * v4);
    else
      v8 = Data;
    v9 = *(&v21 + 4 * v4);
    if ( v8 )
      v1 |= v9;
    else
      v1 &= ~v9;
    ++v4;
  }
  while ( v4 != 4 );
  *((_DWORD *)this + 16) = v1;
  v10 = 0;
  v11 = *((_DWORD *)this + 17);
  do
  {
    Data = 0;
    cbData = 4;
    AcquireSRWLockShared(v2);
    v12 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\DWM",
            (LPCWSTR)v19[2 * v10 - 1],
            0x20000010u,
            0,
            &Data,
            &cbData);
    if ( v12 )
    {
      v13 = (const WCHAR *)v19[2 * v10 - 1];
      v14 = (HKEY)*((_QWORD *)this + 2);
      cbData = 4;
      v12 = RegQueryValueExW(v14, v13, 0, 0, (LPBYTE)&Data, &cbData);
    }
    ReleaseSRWLockShared(v2);
    v15 = v12 < 0;
    if ( v12 > 0 )
      v15 = 1;
    if ( v15 )
      v16 = HIDWORD(v19[2 * v10]);
    else
      v16 = Data;
    v17 = v19[2 * v10];
    if ( v16 )
      v11 |= v17;
    else
      v11 &= ~v17;
    ++v10;
  }
  while ( v10 != 3 );
  *((_DWORD *)this + 17) = v11;
}

```

## disassembly

```asm
0x140002988  mov     [rsp-8+arg_10], rbx
0x14000298d  mov     [rsp-8+arg_18], rsi
0x140002992  push    rbp
0x140002993  push    rdi
0x140002994  push    r12
0x140002996  push    r14
0x140002998  push    r15
0x14000299a  lea     rbp, [rsp-37h]
0x14000299f  sub     rsp, 0B0h
0x1400029a6  mov     edi, [rcx+40h]
0x1400029a9  lea     rax, aUsedpiscaling; "UseDPIScaling"
0x1400029b0  mov     [rbp+57h+lpValueName], rax
0x1400029b4  lea     r12, [rcx+30h]
0x1400029b8  lea     rax, aAnimationsshif; "AnimationsShiftKey"
0x1400029bf  mov     [rbp+57h+var_58], 1
0x1400029c6  mov     [rbp+57h+var_50], rax
0x1400029ca  mov     r15, rcx
0x1400029cd  lea     rax, aDisablelocking; "DisableLockingMemory"
0x1400029d4  mov     [rbp+57h+var_54], 1
0x1400029db  mov     [rbp+57h+var_40], rax
0x1400029df  xor     esi, esi
0x1400029e1  lea     rax, aModechangecurt; "ModeChangeCurtainUseDebugColor"
0x1400029e8  mov     [rbp+57h+var_48], 2
0x1400029f0  mov     [rbp+57h+var_30], rax
0x1400029f4  lea     rax, aDisallowanimat; "DisallowAnimations"
0x1400029fb  mov     [rbp+57h+lpValue], rax
0x1400029ff  lea     rax, aDisallowcolori; "DisallowColorizationColorChanges"
0x140002a06  mov     [rbp+57h+var_80], rax
0x140002a0a  lea     rax, aDefaultcoloriz; "DefaultColorizationColorState"
0x140002a11  mov     [rbp+57h+var_70], rax
0x140002a15  mov     [rbp+57h+var_38], 40h ; '@'
0x140002a1d  mov     [rbp+57h+var_28], 80h
0x140002a25  mov     [rbp+57h+var_88], 1
0x140002a2d  mov     [rbp+57h+var_78], 2
0x140002a35  mov     [rbp+57h+var_68], 4
0x140002a3d  mov     r14, rsi
0x140002a40  mov     [rbp+57h+Data], 0
0x140002a47  mov     rcx, r12; SRWLock
0x140002a4a  mov     [rbp+57h+cbData], 4
0x140002a51  add     r14, r14
0x140002a54  call    cs:__imp_AcquireSRWLockShared
0x140002a5a  mov     rdx, [rbp+r14*8+57h+lpValueName]; lpValueName
0x140002a5f  lea     rax, [rbp+57h+cbData]
0x140002a63  mov     rcx, [r15+8]; hKey
0x140002a67  xor     r9d, r9d; lpType
0x140002a6a  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x140002a6f  xor     r8d, r8d; lpReserved
0x140002a72  lea     rax, [rbp+57h+Data]
0x140002a76  mov     [rsp+0D0h+lpData], rax; lpData
0x140002a7b  call    cs:__imp_RegQueryValueExW
0x140002a81  mov     ebx, eax
0x140002a83  test    eax, eax
0x140002a85  jz      short loc_140002ACA
0x140002a87  mov     r8, [rbp+r14*8+57h+lpValueName]; lpValue
0x140002a8c  lea     rax, [rbp+57h+cbData]
0x140002a90  mov     [rsp+0D0h+pcbData], rax; pcbData
0x140002a95  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\DWM"
0x140002a9c  lea     rax, [rbp+57h+Data]
0x140002aa0  mov     [rbp+57h+cbData], 4
0x140002aa7  mov     [rsp+0D0h+lpcbData], rax; pvData
0x140002aac  mov     r9d, 20000010h; dwFlags
0x140002ab2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002ab9  mov     [rsp+0D0h+lpData], 0; pdwType
0x140002ac2  call    cs:__imp_RegGetValueW
0x140002ac8  mov     ebx, eax
0x140002aca  mov     rcx, r12; SRWLock
0x140002acd  call    cs:__imp_ReleaseSRWLockShared
0x140002ad3  test    ebx, ebx
0x140002ad5  jle     short loc_140002AE2
0x140002ad7  movzx   ebx, bx
0x140002ada  or      ebx, 80070000h
0x140002ae0  test    ebx, ebx
0x140002ae2  jns     loc_140002C06
0x140002ae8  mov     ecx, [rbp+r14*8+57h+var_54]
0x140002aed  mov     eax, [rbp+r14*8+57h+var_58]
0x140002af2  test    ecx, ecx
0x140002af4  jnz     loc_140002BFB
0x140002afa  not     eax
0x140002afc  and     edi, eax
0x140002afe  inc     rsi
0x140002b01  cmp     rsi, 4
0x140002b05  jnz     loc_140002A3D
0x140002b0b  mov     [r15+40h], edi
0x140002b0f  xor     esi, esi
0x140002b11  mov     edi, [r15+44h]
0x140002b15  mov     r14, rsi
0x140002b18  mov     [rbp+57h+Data], 0
0x140002b1f  mov     rcx, r12; SRWLock
0x140002b22  mov     [rbp+57h+cbData], 4
0x140002b29  add     r14, r14
0x140002b2c  call    cs:__imp_AcquireSRWLockShared
0x140002b32  mov     r8, [rbp+r14*8+57h+lpValue]; lpValue
0x140002b37  lea     rax, [rbp+57h+cbData]
0x140002b3b  mov     [rsp+0D0h+pcbData], rax; pcbData
0x140002b40  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x140002b47  lea     rax, [rbp+57h+Data]
0x140002b4b  mov     r9d, 20000010h; dwFlags
0x140002b51  mov     [rsp+0D0h+lpcbData], rax; pvData
0x140002b56  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002b5d  mov     [rsp+0D0h+lpData], 0; pdwType
0x140002b66  call    cs:__imp_RegGetValueW
0x140002b6c  mov     ebx, eax
0x140002b6e  test    eax, eax
0x140002b70  jz      short loc_140002BA2
0x140002b72  mov     rdx, [rbp+r14*8+57h+lpValue]; lpValueName
0x140002b77  lea     rax, [rbp+57h+cbData]
0x140002b7b  mov     rcx, [r15+10h]; hKey
0x140002b7f  xor     r9d, r9d; lpType
0x140002b82  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x140002b87  xor     r8d, r8d; lpReserved
0x140002b8a  lea     rax, [rbp+57h+Data]
0x140002b8e  mov     [rbp+57h+cbData], 4
0x140002b95  mov     [rsp+0D0h+lpData], rax; lpData
0x140002b9a  call    cs:__imp_RegQueryValueExW
0x140002ba0  mov     ebx, eax
0x140002ba2  mov     rcx, r12; SRWLock
0x140002ba5  call    cs:__imp_ReleaseSRWLockShared
0x140002bab  test    ebx, ebx
0x140002bad  jle     short loc_140002BBA
0x140002baf  movzx   ebx, bx
0x140002bb2  or      ebx, 80070000h
0x140002bb8  test    ebx, ebx
0x140002bba  jns     short loc_140002C0E
0x140002bbc  mov     ecx, dword ptr [rbp+r14*8+57h+var_88+4]
0x140002bc1  mov     eax, dword ptr [rbp+r14*8+57h+var_88]
0x140002bc6  test    ecx, ecx
0x140002bc8  jnz     short loc_140002C02
0x140002bca  not     eax
0x140002bcc  and     edi, eax
0x140002bce  inc     rsi
0x140002bd1  cmp     rsi, 3
0x140002bd5  jnz     loc_140002B15
0x140002bdb  lea     r11, [rsp+0D0h+var_20]
0x140002be3  mov     [r15+44h], edi
0x140002be7  mov     rbx, [r11+40h]
0x140002beb  mov     rsi, [r11+48h]
0x140002bef  mov     rsp, r11
0x140002bf2  pop     r15
0x140002bf4  pop     r14
0x140002bf6  pop     r12
0x140002bf8  pop     rdi
0x140002bf9  pop     rbp
0x140002bfa  retn
0x140002bfb  or      edi, eax
0x140002bfd  jmp     loc_140002AFE
0x140002c02  or      edi, eax
0x140002c04  jmp     short loc_140002BCE
0x140002c06  mov     ecx, [rbp+57h+Data]
0x140002c09  jmp     loc_140002AED
0x140002c0e  mov     ecx, [rbp+57h+Data]
0x140002c11  jmp     short loc_140002BC1
```
