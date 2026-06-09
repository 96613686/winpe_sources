# CDefCompFrameWindow::LoadPosition(void)

- ea: `0x180048fc0`
- end: `0x1800490ee`
- name: `?LoadPosition@CDefCompFrameWindow@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(CDefCompFrameWindow *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048bd4`

## callees

- `0x180048fc0`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004906e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800490a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004906e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800490a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004901b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004901b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800490db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800490db`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180048ff2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180048ff2`

## string_xrefs

- `0x180048ffe`: `SOFTWARE\Microsoft\CTF\CUAS\DefaultCompositionWindow`

## pseudocode

```c
void __fastcall CDefCompFrameWindow::LoadPosition(CDefCompFrameWindow *this)
{
  unsigned int v2; // esi
  HKEY v3; // rdi
  unsigned int v4; // r14d
  HKEY v5; // rbx
  LSTATUS v6; // ebx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+80h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+40h] BYREF
  DWORD Type; // [rsp+90h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+50h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = 0;
  phkResult = 0;
  v4 = 0;
  v5 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x20019u, &phkResult) )
    v5 = phkResult;
  v6 = RegOpenKeyExW(v5, L"SOFTWARE\\Microsoft\\CTF\\CUAS\\DefaultCompositionWindow", 0, 0x20019u, &hKey);
  if ( !v6 )
    v3 = hKey;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( !v6 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v7 = RegQueryValueExW(v3, L"Left", 0, &Type, (LPBYTE)&Data, &cbData);
    Type = 0;
    cbData = 4;
    if ( !v7 )
      v2 = Data;
    if ( !RegQueryValueExW(v3, L"Top", 0, &Type, (LPBYTE)&Data, &cbData) )
      v4 = Data;
  }
  (*(void (__fastcall **)(CDefCompFrameWindow *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 472LL))(
    this,
    v2,
    v4,
    0,
    0);
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x180048fc0  push    rbp
0x180048fc2  push    rbx
0x180048fc3  push    rsi
0x180048fc4  push    rdi
0x180048fc5  push    r14
0x180048fc7  push    r15
0x180048fc9  mov     rbp, rsp
0x180048fcc  sub     rsp, 48h
0x180048fd0  mov     r15, rcx
0x180048fd3  lea     rdx, [rbp+phkResult]; phkResult
0x180048fd7  xor     esi, esi
0x180048fd9  mov     ecx, 20019h; samDesired
0x180048fde  mov     [rbp+hKey], rsi
0x180048fe2  xor     edi, edi
0x180048fe4  mov     [rbp+phkResult], rsi
0x180048fe8  xor     r14d, r14d
0x180048feb  mov     rbx, 0FFFFFFFF80000001h
0x180048ff2  call    cs:__imp_RegOpenCurrentUser
0x180048ff8  mov     r9d, 20019h; samDesired
0x180048ffe  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\CTF\\CUAS\\Default"...
0x180049005  test    eax, eax
0x180049007  lea     rax, [rbp+hKey]
0x18004900b  mov     [rsp+48h+var_28], rax; phkResult
0x180049010  cmovz   rbx, [rbp+phkResult]
0x180049015  xor     r8d, r8d; ulOptions
0x180049018  mov     rcx, rbx; hKey
0x18004901b  call    cs:__imp_RegOpenKeyExW
0x180049021  mov     rcx, [rbp+phkResult]; hKey
0x180049025  test    eax, eax
0x180049027  mov     ebx, eax
0x180049029  cmovz   rdi, [rbp+hKey]
0x18004902e  test    rcx, rcx
0x180049031  jz      short loc_180049039
0x180049033  call    cs:__imp_RegCloseKey
0x180049039  test    ebx, ebx
0x18004903b  jnz     short loc_1800490B1
0x18004903d  lea     rax, [rbp+cbData]
0x180049041  mov     [rbp+Data], esi
0x180049044  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180049049  lea     r9, [rbp+Type]; lpType
0x18004904d  lea     rax, [rbp+Data]
0x180049051  mov     [rbp+Type], esi
0x180049054  mov     ebx, 4
0x180049059  mov     [rsp+48h+var_28], rax; lpData
0x18004905e  xor     r8d, r8d; lpReserved
0x180049061  mov     [rbp+cbData], ebx
0x180049064  lea     rdx, aLeft; "Left"
0x18004906b  mov     rcx, rdi; hKey
0x18004906e  call    cs:__imp_RegQueryValueExW
0x180049074  lea     r9, [rbp+Type]; lpType
0x180049078  mov     [rbp+Type], r14d
0x18004907c  test    eax, eax
0x18004907e  mov     [rbp+cbData], ebx
0x180049081  lea     rax, [rbp+cbData]
0x180049085  mov     rcx, rdi; hKey
0x180049088  cmovz   esi, [rbp+Data]
0x18004908c  lea     rdx, aTop; "Top"
0x180049093  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180049098  xor     r8d, r8d; lpReserved
0x18004909b  lea     rax, [rbp+Data]
0x18004909f  mov     [rsp+48h+var_28], rax; lpData
0x1800490a4  call    cs:__imp_RegQueryValueExW
0x1800490aa  test    eax, eax
0x1800490ac  cmovz   r14d, [rbp+Data]
0x1800490b1  mov     rax, [r15]
0x1800490b4  xor     r9d, r9d
0x1800490b7  mov     r8d, r14d
0x1800490ba  mov     dword ptr [rsp+48h+var_28], 0
0x1800490c2  mov     edx, esi
0x1800490c4  mov     rcx, r15
0x1800490c7  mov     rax, [rax+1D8h]
0x1800490ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490d3  test    rdi, rdi
0x1800490d6  jz      short loc_1800490E1
0x1800490d8  mov     rcx, rdi; hKey
0x1800490db  call    cs:__imp_RegCloseKey
0x1800490e1  add     rsp, 48h
0x1800490e5  pop     r15
0x1800490e7  pop     r14
0x1800490e9  pop     rdi
0x1800490ea  pop     rsi
0x1800490eb  pop     rbx
0x1800490ec  pop     rbp
0x1800490ed  retn
```
