# CMachine::InitializeDeviceIdFromRegistry(void)

- ea: `0x18003faf8`
- end: `0x18003fc7d`
- name: `?InitializeDeviceIdFromRegistry@CMachine@@AEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(CMachine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003ed44`

## callees

- `0x180006210`
- `0x18000624c`
- `0x180016440`
- `0x18003faf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fb36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fb36`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fb7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fbfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fb7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fbfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc67`

## string_xrefs

- `0x18003fb71`: `ComputerHardwareId`
- `0x18003fbf1`: `ComputerHardwareId`

## pseudocode

```c
__int64 __fastcall CMachine::InitializeDeviceIdFromRegistry(CMachine *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  unsigned __int64 v5; // rax
  BYTE *v6; // rsi
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE *v10; // [rsp+38h] [rbp-20h]
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+78h] [rbp+20h]

  hKey = 0;
  cbData = 0;
  Type = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SystemInformation", 0, 0x20019u, &hKey);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2
    || (cbData = 0, v2 = RegQueryValueExW(hKey, L"ComputerHardwareId", 0, &Type, 0, &cbData), v3 = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else if ( cbData >= 2 )
  {
    v5 = 2 * ((unsigned __int64)cbData >> 1);
    if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
      v5 = -1;
    v6 = (BYTE *)operator new[](v5, (const struct std::nothrow_t *)std::nothrow);
    v10 = v6;
    if ( v6 )
    {
      v7 = RegQueryValueExW(hKey, L"ComputerHardwareId", 0, &Type, v6, &cbData);
      v3 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      else if ( Type == 1 || (cbData & 0xFFFFFFFE) >= 2 )
      {
        try
        {
          *(_WORD *)&v6[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
          std::wstring::append(this, v6);
          v3 = 0;
        }
        catch ( std::bad_alloc )
        {
          v13 = -2147024888;
          v3 = -2147024888;
          v6 = v10;
        }
      }
      else
      {
        v3 = -2147024883;
      }
      operator delete(v6);
    }
    else
    {
      v3 = -2147024888;
    }
  }
  else
  {
    v3 = -2147024883;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18003faf8  mov     rax, rsp
0x18003fafb  mov     [rax+8], rbx
0x18003faff  push    rsi
0x18003fb00  push    rdi
0x18003fb01  push    r14
0x18003fb03  sub     rsp, 40h
0x18003fb07  mov     r14, rcx
0x18003fb0a  xor     edi, edi
0x18003fb0c  mov     [rax-28h], rdi
0x18003fb10  mov     [rax+10h], edi
0x18003fb13  mov     [rax+18h], edi
0x18003fb16  lea     rax, [rax-28h]
0x18003fb1a  mov     [rsp+58h+phkResult], rax; phkResult
0x18003fb1f  mov     r9d, 20019h; samDesired
0x18003fb25  xor     r8d, r8d; ulOptions
0x18003fb28  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Sys"...
0x18003fb2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fb36  call    cs:__imp_RegOpenKeyExW
0x18003fb3c  mov     ebx, eax
0x18003fb3e  test    eax, eax
0x18003fb40  jz      short loc_18003FB56
0x18003fb42  jle     loc_18003FC5D
0x18003fb48  movzx   ebx, ax
0x18003fb4b  or      ebx, 80070000h
0x18003fb51  jmp     loc_18003FC5D
0x18003fb56  mov     [rsp+58h+cbData], edi
0x18003fb5a  lea     rax, [rsp+58h+cbData]
0x18003fb5f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003fb64  mov     [rsp+58h+phkResult], rdi; lpData
0x18003fb69  lea     r9, [rsp+58h+Type]; lpType
0x18003fb6e  xor     r8d, r8d; lpReserved
0x18003fb71  lea     rdx, ValueName; "ComputerHardwareId"
0x18003fb78  mov     rcx, [rsp+58h+hKey]; hKey
0x18003fb7d  call    cs:__imp_RegQueryValueExW
0x18003fb83  mov     ebx, eax
0x18003fb85  test    eax, eax
0x18003fb87  jnz     short loc_18003FB42
0x18003fb89  cmp     [rsp+58h+cbData], 2
0x18003fb8e  jnb     short loc_18003FB9A
0x18003fb90  mov     ebx, 8007000Dh
0x18003fb95  jmp     loc_18003FC5D
0x18003fb9a  mov     ecx, [rsp+58h+cbData]
0x18003fb9e  shr     rcx, 1
0x18003fba1  mov     eax, 2
0x18003fba6  mul     rcx
0x18003fba9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003fbb0  cmovb   rax, rcx
0x18003fbb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003fbbb  mov     rcx, rax; unsigned __int64
0x18003fbbe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003fbc3  mov     rsi, rax
0x18003fbc6  mov     [rsp+58h+var_20], rax
0x18003fbcb  test    rax, rax
0x18003fbce  jnz     short loc_18003FBDA
0x18003fbd0  mov     ebx, 80070008h
0x18003fbd5  jmp     loc_18003FC5D
0x18003fbda  lea     rax, [rsp+58h+cbData]
0x18003fbdf  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003fbe4  mov     [rsp+58h+phkResult], rsi; lpData
0x18003fbe9  lea     r9, [rsp+58h+Type]; lpType
0x18003fbee  xor     r8d, r8d; lpReserved
0x18003fbf1  lea     rdx, ValueName; "ComputerHardwareId"
0x18003fbf8  mov     rcx, [rsp+58h+hKey]; hKey
0x18003fbfd  call    cs:__imp_RegQueryValueExW
0x18003fc03  mov     ebx, eax
0x18003fc05  test    eax, eax
0x18003fc07  jz      short loc_18003FC16
0x18003fc09  jle     short loc_18003FC55
0x18003fc0b  movzx   ebx, ax
0x18003fc0e  or      ebx, 80070000h
0x18003fc14  jmp     short loc_18003FC55
0x18003fc16  mov     ecx, [rsp+58h+cbData]
0x18003fc1a  cmp     [rsp+58h+Type], 1
0x18003fc1f  jz      short loc_18003FC32
0x18003fc21  mov     eax, ecx
0x18003fc23  and     eax, 0FFFFFFFEh
0x18003fc26  cmp     eax, 2
0x18003fc29  jnb     short loc_18003FC32
0x18003fc2b  mov     ebx, 8007000Dh
0x18003fc30  jmp     short loc_18003FC55
0x18003fc32  mov     eax, ecx
0x18003fc34  shr     rax, 1
0x18003fc37  mov     [rsi+rax*2-2], di
0x18003fc3c  mov     rdx, rsi; void *
0x18003fc3f  mov     rcx, r14; Src
0x18003fc42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003fc47  nop
0x18003fc48  mov     ebx, edi
0x18003fc4a  jmp     short loc_18003FC55
0x18003fc4c  mov     ebx, [rsp+58h+arg_18]
0x18003fc50  mov     rsi, [rsp+58h+var_20]
0x18003fc55  mov     rcx, rsi; Block
0x18003fc58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003fc5d  mov     rcx, [rsp+58h+hKey]; hKey
0x18003fc62  test    rcx, rcx
0x18003fc65  jz      short loc_18003FC6D
0x18003fc67  call    cs:__imp_RegCloseKey
0x18003fc6d  mov     eax, ebx
0x18003fc6f  mov     rbx, [rsp+58h+arg_0]
0x18003fc74  add     rsp, 40h
0x18003fc78  pop     r14
0x18003fc7a  pop     rdi
0x18003fc7b  pop     rsi
0x18003fc7c  retn
```
