# OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x18001e320`
- end: `0x18001e401`
- name: `?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z`
- size: `225`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005ac0`
- `0x180059200`

## callees

- `0x180010cb4`
- `0x18001e320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3a6`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001e349`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001e349`

## string_xrefs

- `0x18001e391`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\25`
- `0x18001e3c9`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\25`

## pseudocode

```c
__int64 __fastcall OpenPeapRegistryKey(const unsigned __int16 *a1, __int64 a2, HKEY *a3)
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
        12,
        (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
        (unsigned int)L"NULL",
        v4);
    return v4;
  }
  else
  {
    v6 = RegOpenKeyExW(phkResult, L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\25", 0, 0x20019u, a3);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
          (unsigned int)L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\25",
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
0x18001e320  mov     [rsp+arg_8], rbx
0x18001e325  mov     [rsp+phkResult], rcx
0x18001e32a  push    rdi
0x18001e32b  sub     rsp, 30h
0x18001e32f  mov     rbx, r8
0x18001e332  mov     [rsp+38h+phkResult], 0
0x18001e33b  lea     r8, [rsp+38h+phkResult]; phkResult
0x18001e340  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001e347  xor     ecx, ecx; lpMachineName
0x18001e349  call    cs:__imp_RegConnectRegistryW
0x18001e34f  mov     edi, eax
0x18001e351  test    eax, eax
0x18001e353  jz      short loc_18001E38C
0x18001e355  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e35c  lea     rax, WPP_GLOBAL_Control
0x18001e363  cmp     rcx, rax
0x18001e366  jz      short loc_18001E388
0x18001e368  mov     rcx, [rcx+10h]
0x18001e36c  lea     r9, aNull_0; "NULL"
0x18001e373  mov     edx, 0Ch
0x18001e378  mov     dword ptr [rsp+38h+var_18], edi
0x18001e37c  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001e383  call    WPP_SF_Sd
0x18001e388  mov     eax, edi
0x18001e38a  jmp     short loc_18001E3F6
0x18001e38c  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001e391  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x18001e398  mov     r9d, 20019h; samDesired
0x18001e39e  mov     [rsp+38h+var_18], rbx; phkResult
0x18001e3a3  xor     r8d, r8d; ulOptions
0x18001e3a6  call    cs:__imp_RegOpenKeyExW
0x18001e3ac  mov     ebx, eax
0x18001e3ae  test    eax, eax
0x18001e3b0  jz      short loc_18001E3E7
0x18001e3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3b9  lea     rax, WPP_GLOBAL_Control
0x18001e3c0  cmp     rcx, rax
0x18001e3c3  jz      short loc_18001E3E9
0x18001e3c5  mov     rcx, [rcx+10h]
0x18001e3c9  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x18001e3d0  mov     edx, 0Dh
0x18001e3d5  mov     dword ptr [rsp+38h+var_18], ebx
0x18001e3d9  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001e3e0  call    WPP_SF_Sd
0x18001e3e5  jmp     short loc_18001E3E9
0x18001e3e7  xor     ebx, ebx
0x18001e3e9  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001e3ee  call    cs:__imp_RegCloseKey
0x18001e3f4  mov     eax, ebx
0x18001e3f6  mov     rbx, [rsp+38h+arg_8]
0x18001e3fb  add     rsp, 30h
0x18001e3ff  pop     rdi
0x18001e400  retn
```
