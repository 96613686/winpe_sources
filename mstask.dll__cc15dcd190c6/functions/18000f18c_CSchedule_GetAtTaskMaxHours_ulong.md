# CSchedule::GetAtTaskMaxHours(ulong *)

- ea: `0x18000f18c`
- end: `0x18000f2cf`
- name: `?GetAtTaskMaxHours@CSchedule@@AEAAJPEAK@Z`
- size: `323`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000e7f8`

## callees

- `0x18000f18c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f21c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f21c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f290`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f290`

## string_xrefs

- `0x18000f1b5`: `System\CurrentControlSet\Services\Schedule`
- `0x18000f1f5`: `AtTaskMaxHours`
- `0x18000f27b`: `AtTaskMaxHours`

## pseudocode

```c
LSTATUS __fastcall CSchedule::GetAtTaskMaxHours(CSchedule *this, unsigned int *a2)
{
  LSTATUS result; // eax
  char v4; // di
  LSTATUS v5; // eax
  LSTATUS v6; // ebx
  unsigned int v7; // eax
  int v8; // eax
  CSchedule *Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Data = this;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 0x2001Fu, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  LODWORD(Data) = 0;
  cbData = 4;
  v4 = 0;
  v5 = RegQueryValueExW(hKey, L"AtTaskMaxHours", 0, 0, (LPBYTE)&Data, &cbData);
  v6 = v5;
  if ( !v5 )
  {
    v7 = (unsigned int)Data;
LABEL_11:
    if ( v7 <= 0x3E7 )
    {
      if ( !v4 )
        goto LABEL_16;
    }
    else
    {
      LODWORD(Data) = 999;
    }
    v6 = RegSetValueExW(hKey, L"AtTaskMaxHours", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v6 )
      goto LABEL_6;
    v7 = (unsigned int)Data;
LABEL_16:
    if ( v7 )
      v8 = 3600000 * v7;
    else
      v8 = -1;
    LODWORD(Data) = v8;
    RegCloseKey(hKey);
    *a2 = (unsigned int)Data;
    return 0;
  }
  if ( v5 == 2 )
  {
    v7 = 72;
    v4 = 1;
    LODWORD(Data) = 72;
    goto LABEL_11;
  }
LABEL_6:
  RegCloseKey(hKey);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x18000f18c  mov     [rsp-18h+arg_8], rbx
0x18000f191  mov     [rsp-18h+Data], rcx
0x18000f196  push    rbp
0x18000f197  push    rsi
0x18000f198  push    rdi
0x18000f199  mov     rbp, rsp
0x18000f19c  sub     rsp, 30h
0x18000f1a0  mov     rsi, rdx
0x18000f1a3  mov     [rbp+hKey], 0
0x18000f1ab  lea     rax, [rbp+hKey]
0x18000f1af  mov     r9d, 2001Fh; samDesired
0x18000f1b5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x18000f1bc  mov     [rsp+30h+phkResult], rax; phkResult
0x18000f1c1  xor     r8d, r8d; ulOptions
0x18000f1c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f1cb  call    cs:__imp_RegOpenKeyExW
0x18000f1d1  test    eax, eax
0x18000f1d3  jz      short loc_18000F1E8
0x18000f1d5  jle     loc_18000F2C2
0x18000f1db  movzx   eax, ax
0x18000f1de  or      eax, 80070000h
0x18000f1e3  jmp     loc_18000F2C2
0x18000f1e8  mov     rcx, [rbp+hKey]; hKey
0x18000f1ec  lea     rax, [rbp+cbData]
0x18000f1f0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000f1f5  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x18000f1fc  lea     rax, [rbp+Data]
0x18000f200  mov     dword ptr [rbp+Data], 0
0x18000f207  xor     r9d, r9d; lpType
0x18000f20a  mov     [rsp+30h+phkResult], rax; lpData
0x18000f20f  xor     r8d, r8d; lpReserved
0x18000f212  mov     [rbp+cbData], 4
0x18000f219  xor     dil, dil
0x18000f21c  call    cs:__imp_RegQueryValueExW
0x18000f222  mov     ebx, eax
0x18000f224  test    eax, eax
0x18000f226  jz      short loc_18000F255
0x18000f228  cmp     eax, 2
0x18000f22b  jz      short loc_18000F248
0x18000f22d  mov     rcx, [rbp+hKey]; hKey
0x18000f231  call    cs:__imp_RegCloseKey
0x18000f237  test    ebx, ebx
0x18000f239  jle     short loc_18000F244
0x18000f23b  movzx   ebx, bx
0x18000f23e  or      ebx, 80070000h
0x18000f244  mov     eax, ebx
0x18000f246  jmp     short loc_18000F2C2
0x18000f248  mov     eax, 48h ; 'H'
0x18000f24d  mov     dil, 1
0x18000f250  mov     dword ptr [rbp+Data], eax
0x18000f253  jmp     short loc_18000F258
0x18000f255  mov     eax, dword ptr [rbp+Data]
0x18000f258  mov     ecx, 3E7h
0x18000f25d  cmp     eax, ecx
0x18000f25f  jbe     short loc_18000F266
0x18000f261  mov     dword ptr [rbp+Data], ecx
0x18000f264  jmp     short loc_18000F26B
0x18000f266  test    dil, dil
0x18000f269  jz      short loc_18000F29F
0x18000f26b  mov     rcx, [rbp+hKey]; hKey
0x18000f26f  lea     rax, [rbp+Data]
0x18000f273  mov     dword ptr [rsp+30h+lpcbData], 4; cbData
0x18000f27b  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x18000f282  mov     r9d, 4; dwType
0x18000f288  mov     [rsp+30h+phkResult], rax; lpData
0x18000f28d  xor     r8d, r8d; Reserved
0x18000f290  call    cs:__imp_RegSetValueExW
0x18000f296  mov     ebx, eax
0x18000f298  test    eax, eax
0x18000f29a  jnz     short loc_18000F22D
0x18000f29c  mov     eax, dword ptr [rbp+Data]
0x18000f29f  test    eax, eax
0x18000f2a1  jnz     short loc_18000F2A8
0x18000f2a3  or      eax, 0FFFFFFFFh
0x18000f2a6  jmp     short loc_18000F2AE
0x18000f2a8  imul    eax, 36EE80h
0x18000f2ae  mov     rcx, [rbp+hKey]; hKey
0x18000f2b2  mov     dword ptr [rbp+Data], eax
0x18000f2b5  call    cs:__imp_RegCloseKey
0x18000f2bb  mov     eax, dword ptr [rbp+Data]
0x18000f2be  mov     [rsi], eax
0x18000f2c0  xor     eax, eax
0x18000f2c2  mov     rbx, [rsp+30h+arg_8]
0x18000f2c7  add     rsp, 30h
0x18000f2cb  pop     rdi
0x18000f2cc  pop     rsi
0x18000f2cd  pop     rbp
0x18000f2ce  retn
```
