# SetRequestOptions(void *)

- ea: `0x140052524`
- end: `0x140052682`
- name: `?SetRequestOptions@@YAJPEAX@Z`
- size: `350`
- prototype: `__int64 __fastcall(HINTERNET hInternet)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400506ac`

## callees

- `0x140052524`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14005256d`
- `ADVAPI32!RegOpenKeyExW` at `0x14005256d`
- `ADVAPI32!RegQueryValueExW` at `0x1400525b8`
- `ADVAPI32!RegQueryValueExW` at `0x1400525b8`
- `ADVAPI32!RegCloseKey` at `0x140052665`
- `ADVAPI32!RegCloseKey` at `0x140052665`
- `KERNEL32!GetLastError` at `0x1400525fc`
- `KERNEL32!GetLastError` at `0x140052644`
- `KERNEL32!GetLastError` at `0x1400525fc`
- `KERNEL32!GetLastError` at `0x140052644`
- `WINHTTP!WinHttpSetOption` at `0x1400525ec`
- `WINHTTP!WinHttpSetOption` at `0x140052630`
- `WINHTTP!WinHttpSetOption` at `0x1400525ec`
- `WINHTTP!WinHttpSetOption` at `0x140052630`

## pseudocode

```c
__int64 __fastcall SetRequestOptions(HINTERNET hInternet)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // sf
  signed int LastError; // eax
  signed int v7; // eax
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Data = 0;
  hKey = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDE\\Support\\", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( !v2 )
    goto LABEL_5;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_5:
    v4 = RegQueryValueExW(hKey, L"AutoLogonPolicy", 0, 0, (LPBYTE)&Data, &cbData);
    v5 = v4 < 0;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = 1;
      if ( v5 )
        Data = 2;
    }
    if ( WinHttpSetOption(hInternet, 0x4Du, &Data, 4u) )
      goto LABEL_14;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_14:
      Data = 0;
      if ( WinHttpSetOption(hInternet, 0x58u, &Data, 4u) )
      {
        v3 = 0;
      }
      else
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140052524  mov     [rsp-18h+arg_0], rbx
0x140052529  push    rbp
0x14005252a  push    rdi
0x14005252b  push    r14
0x14005252d  mov     rbp, rsp
0x140052530  sub     rsp, 30h
0x140052534  mov     rdi, rcx
0x140052537  mov     [rbp+Data], 0
0x14005253e  lea     rax, [rbp+hKey]
0x140052542  mov     [rbp+hKey], 0
0x14005254a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140052551  mov     [rsp+30h+phkResult], rax; phkResult
0x140052556  mov     r9d, 20019h; samDesired
0x14005255c  mov     [rbp+cbData], 4
0x140052563  xor     r8d, r8d; ulOptions
0x140052566  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MSDE\\Support\\"
0x14005256d  call    cs:__imp_RegOpenKeyExW
0x140052574  nop     dword ptr [rax+rax+00h]
0x140052579  mov     ebx, eax
0x14005257b  mov     r14d, 80070000h
0x140052581  test    eax, eax
0x140052583  jz      short loc_140052595
0x140052585  jle     short loc_14005258D
0x140052587  movzx   ebx, ax
0x14005258a  or      ebx, r14d
0x14005258d  test    ebx, ebx
0x14005258f  js      loc_14005265C
0x140052595  mov     rcx, [rbp+hKey]; hKey
0x140052599  lea     rax, [rbp+cbData]
0x14005259d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1400525a2  lea     rdx, aAutologonpolic; "AutoLogonPolicy"
0x1400525a9  lea     rax, [rbp+Data]
0x1400525ad  xor     r9d, r9d; lpType
0x1400525b0  xor     r8d, r8d; lpReserved
0x1400525b3  mov     [rsp+30h+phkResult], rax; lpData
0x1400525b8  call    cs:__imp_RegQueryValueExW
0x1400525bf  nop     dword ptr [rax+rax+00h]
0x1400525c4  test    eax, eax
0x1400525c6  jz      short loc_1400525DB
0x1400525c8  jle     short loc_1400525D2
0x1400525ca  movzx   eax, ax
0x1400525cd  or      eax, r14d
0x1400525d0  test    eax, eax
0x1400525d2  jns     short loc_1400525DB
0x1400525d4  mov     [rbp+Data], 2
0x1400525db  mov     r9d, 4; dwBufferLength
0x1400525e1  lea     r8, [rbp+Data]; lpBuffer
0x1400525e5  mov     rcx, rdi; hInternet
0x1400525e8  lea     edx, [r9+49h]; dwOption
0x1400525ec  call    cs:__imp_WinHttpSetOption
0x1400525f3  nop     dword ptr [rax+rax+00h]
0x1400525f8  test    eax, eax
0x1400525fa  jnz     short loc_140052618
0x1400525fc  call    cs:__imp_GetLastError
0x140052603  nop     dword ptr [rax+rax+00h]
0x140052608  mov     ebx, eax
0x14005260a  test    eax, eax
0x14005260c  jle     short loc_140052614
0x14005260e  movzx   ebx, ax
0x140052611  or      ebx, r14d
0x140052614  test    ebx, ebx
0x140052616  js      short loc_14005265C
0x140052618  mov     r9d, 4; dwBufferLength
0x14005261e  mov     [rbp+Data], 0
0x140052625  lea     r8, [rbp+Data]; lpBuffer
0x140052629  mov     rcx, rdi; hInternet
0x14005262c  lea     edx, [r9+54h]; dwOption
0x140052630  call    cs:__imp_WinHttpSetOption
0x140052637  nop     dword ptr [rax+rax+00h]
0x14005263c  test    eax, eax
0x14005263e  jz      short loc_140052644
0x140052640  xor     ebx, ebx
0x140052642  jmp     short loc_14005265C
0x140052644  call    cs:__imp_GetLastError
0x14005264b  nop     dword ptr [rax+rax+00h]
0x140052650  mov     ebx, eax
0x140052652  test    eax, eax
0x140052654  jle     short loc_14005265C
0x140052656  movzx   ebx, ax
0x140052659  or      ebx, r14d
0x14005265c  mov     rcx, [rbp+hKey]; hKey
0x140052660  test    rcx, rcx
0x140052663  jz      short loc_140052671
0x140052665  call    cs:__imp_RegCloseKey
0x14005266c  nop     dword ptr [rax+rax+00h]
0x140052671  mov     eax, ebx
0x140052673  mov     rbx, [rsp+30h+arg_0]
0x140052678  add     rsp, 30h
0x14005267c  pop     r14
0x14005267e  pop     rdi
0x14005267f  pop     rbp
0x140052680  retn
```
