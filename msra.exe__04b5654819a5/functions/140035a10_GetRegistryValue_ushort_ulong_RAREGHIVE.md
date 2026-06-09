# GetRegistryValue(ushort *,ulong *,_RAREGHIVE)

- ea: `0x140035a10`
- end: `0x140035b18`
- name: `?GetRegistryValue@@YAJPEAGPEAKW4_RAREGHIVE@@@Z`
- size: `264`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ea24`
- `0x14001c458`
- `0x140021e00`
- `0x140022c68`
- `0x140024100`

## callees

- `0x140035a10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140035afc`
- `ADVAPI32!RegCloseKey` at `0x140035afc`
- `ADVAPI32!RegOpenKeyExW` at `0x140035a96`
- `ADVAPI32!RegOpenKeyExW` at `0x140035a96`
- `ADVAPI32!RegQueryValueExW` at `0x140035adc`
- `ADVAPI32!RegQueryValueExW` at `0x140035adc`

## string_xrefs

- `0x140035a6d`: `Software\policies\Microsoft\Windows NT\Terminal Services`
- `0x140035a64`: `SYSTEM\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(const WCHAR *a1, _DWORD *a2, int a3)
{
  int v5; // r8d
  int v6; // r8d
  __int64 v7; // rcx
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  v5 = a3 - 2;
  if ( !v5 )
  {
    v8 = L"System\\CurrentControlSet\\Control\\Remote Assistance";
    goto LABEL_8;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v8 = L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services";
    goto LABEL_8;
  }
  if ( v6 == 3 )
  {
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\W32Time\\Parameters";
LABEL_8:
    v7 = -2147483646;
    goto LABEL_9;
  }
  v7 = -2147483647;
  v8 = L"Software\\Microsoft\\Remote Assistance";
LABEL_9:
  v9 = RegOpenKeyExW((HKEY)v7, v8, 0, 1u, &hKey);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9
    || (cbData = 4, v9 = RegQueryValueExW(hKey, a1, 0, &Type, (LPBYTE)&Data, &cbData), v10 = v9, v11 = v9 <= 0, v9) )
  {
    if ( !v11 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    *a2 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x140035a10  mov     [rsp-18h+arg_0], rbx
0x140035a15  push    rbp
0x140035a16  push    rsi
0x140035a17  push    rdi
0x140035a18  mov     rbp, rsp
0x140035a1b  sub     rsp, 40h
0x140035a1f  mov     [rbp+hKey], 0
0x140035a27  mov     rdi, rdx
0x140035a2a  mov     [rbp+cbData], 0
0x140035a31  mov     rsi, rcx
0x140035a34  mov     [rbp+Data], 0
0x140035a3b  mov     [rbp+Type], 4
0x140035a42  sub     r8d, 2
0x140035a46  jz      short loc_140035A76
0x140035a48  sub     r8d, 1
0x140035a4c  jz      short loc_140035A6D
0x140035a4e  cmp     r8d, 3
0x140035a52  jz      short loc_140035A64
0x140035a54  mov     rcx, 0FFFFFFFF80000001h
0x140035a5b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x140035a62  jmp     short loc_140035A84
0x140035a64  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\W3"...
0x140035a6b  jmp     short loc_140035A7D
0x140035a6d  lea     rdx, aSoftwarePolici; "Software\\policies\\Microsoft\\Windows "...
0x140035a74  jmp     short loc_140035A7D
0x140035a76  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Rem"...
0x140035a7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140035a84  lea     rax, [rbp+hKey]
0x140035a88  mov     r9d, 1; samDesired
0x140035a8e  xor     r8d, r8d; ulOptions
0x140035a91  mov     [rsp+40h+phkResult], rax; phkResult
0x140035a96  call    cs:__imp_RegOpenKeyExW
0x140035a9d  nop     dword ptr [rax+rax+00h]
0x140035aa2  mov     ebx, eax
0x140035aa4  test    eax, eax
0x140035aa6  jz      short loc_140035AB5
0x140035aa8  jle     short loc_140035AF3
0x140035aaa  movzx   ebx, ax
0x140035aad  or      ebx, 80070000h
0x140035ab3  jmp     short loc_140035AF3
0x140035ab5  mov     rcx, [rbp+hKey]; hKey
0x140035ab9  lea     rax, [rbp+cbData]
0x140035abd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140035ac2  lea     r9, [rbp+Type]; lpType
0x140035ac6  lea     rax, [rbp+Data]
0x140035aca  mov     [rbp+cbData], 4
0x140035ad1  xor     r8d, r8d; lpReserved
0x140035ad4  mov     [rsp+40h+phkResult], rax; lpData
0x140035ad9  mov     rdx, rsi; lpValueName
0x140035adc  call    cs:__imp_RegQueryValueExW
0x140035ae3  nop     dword ptr [rax+rax+00h]
0x140035ae8  mov     ebx, eax
0x140035aea  test    eax, eax
0x140035aec  jnz     short loc_140035AA8
0x140035aee  mov     ecx, [rbp+Data]
0x140035af1  mov     [rdi], ecx
0x140035af3  mov     rcx, [rbp+hKey]; hKey
0x140035af7  test    rcx, rcx
0x140035afa  jz      short loc_140035B08
0x140035afc  call    cs:__imp_RegCloseKey
0x140035b03  nop     dword ptr [rax+rax+00h]
0x140035b08  mov     eax, ebx
0x140035b0a  mov     rbx, [rsp+40h+arg_0]
0x140035b0f  add     rsp, 40h
0x140035b13  pop     rdi
0x140035b14  pop     rsi
0x140035b15  pop     rbp
0x140035b16  retn
```
