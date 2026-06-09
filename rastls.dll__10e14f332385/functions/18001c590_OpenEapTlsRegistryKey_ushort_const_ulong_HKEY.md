# OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x18001c590`
- end: `0x18001c671`
- name: `?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z`
- size: `225`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005ac0`

## callees

- `0x180010cb4`
- `0x18001c590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c65e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c65e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c616`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c616`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001c5b9`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001c5b9`

## string_xrefs

- `0x18001c601`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x18001c639`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`

## pseudocode

```c
__int64 __fastcall OpenEapTlsRegistryKey(const unsigned __int16 *a1, __int64 a2, HKEY *a3)
{
  unsigned int v4; // edi
  unsigned int v6; // ebx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v4 = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
        (unsigned int)L"NULL",
        v4);
    return v4;
  }
  else
  {
    v6 = RegOpenKeyExW(phkResult, L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\13", 0, 0x20019u, a3);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
          (unsigned int)L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\13",
          v6);
    }
    else
    {
      v6 = 0;
    }
    RegCloseKey(phkResult);
    return v6;
  }
}

```

## disassembly

```asm
0x18001c590  mov     [rsp+arg_8], rbx
0x18001c595  mov     [rsp+phkResult], rcx
0x18001c59a  push    rdi
0x18001c59b  sub     rsp, 30h
0x18001c59f  mov     rbx, r8
0x18001c5a2  mov     [rsp+38h+phkResult], 0
0x18001c5ab  lea     r8, [rsp+38h+phkResult]; phkResult
0x18001c5b0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001c5b7  xor     ecx, ecx; lpMachineName
0x18001c5b9  call    cs:__imp_RegConnectRegistryW
0x18001c5bf  mov     edi, eax
0x18001c5c1  test    eax, eax
0x18001c5c3  jz      short loc_18001C5FC
0x18001c5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5cc  lea     rax, WPP_GLOBAL_Control
0x18001c5d3  cmp     rcx, rax
0x18001c5d6  jz      short loc_18001C5F8
0x18001c5d8  mov     rcx, [rcx+10h]
0x18001c5dc  lea     r9, aNull_0; "NULL"
0x18001c5e3  mov     edx, 3Eh ; '>'
0x18001c5e8  mov     dword ptr [rsp+38h+var_18], edi
0x18001c5ec  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001c5f3  call    WPP_SF_Sd
0x18001c5f8  mov     eax, edi
0x18001c5fa  jmp     short loc_18001C666
0x18001c5fc  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001c601  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001c608  mov     r9d, 20019h; samDesired
0x18001c60e  mov     [rsp+38h+var_18], rbx; phkResult
0x18001c613  xor     r8d, r8d; ulOptions
0x18001c616  call    cs:__imp_RegOpenKeyExW
0x18001c61c  mov     ebx, eax
0x18001c61e  test    eax, eax
0x18001c620  jz      short loc_18001C657
0x18001c622  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c629  lea     rax, WPP_GLOBAL_Control
0x18001c630  cmp     rcx, rax
0x18001c633  jz      short loc_18001C659
0x18001c635  mov     rcx, [rcx+10h]
0x18001c639  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001c640  mov     edx, 3Fh ; '?'
0x18001c645  mov     dword ptr [rsp+38h+var_18], ebx
0x18001c649  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001c650  call    WPP_SF_Sd
0x18001c655  jmp     short loc_18001C659
0x18001c657  xor     ebx, ebx
0x18001c659  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001c65e  call    cs:__imp_RegCloseKey
0x18001c664  mov     eax, ebx
0x18001c666  mov     rbx, [rsp+38h+arg_8]
0x18001c66b  add     rsp, 30h
0x18001c66f  pop     rdi
0x18001c670  retn
```
