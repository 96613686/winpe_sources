# OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x18001df90`
- end: `0x18001e084`
- name: `?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z`
- size: `244`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005f80`

## callees

- `0x180011cc8`
- `0x18001df90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e06a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e06a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e01c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e01c`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001dfb9`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001dfb9`

## string_xrefs

- `0x18001e007`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x18001e045`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`

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
0x18001df90  mov     [rsp+arg_8], rbx
0x18001df95  mov     [rsp+phkResult], rcx
0x18001df9a  push    rdi
0x18001df9b  sub     rsp, 30h
0x18001df9f  mov     rbx, r8
0x18001dfa2  mov     [rsp+38h+phkResult], 0
0x18001dfab  lea     r8, [rsp+38h+phkResult]; phkResult
0x18001dfb0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001dfb7  xor     ecx, ecx; lpMachineName
0x18001dfb9  call    cs:__imp_RegConnectRegistryW
0x18001dfc0  nop     dword ptr [rax+rax+00h]
0x18001dfc5  mov     edi, eax
0x18001dfc7  test    eax, eax
0x18001dfc9  jz      short loc_18001E002
0x18001dfcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfd2  lea     rax, WPP_GLOBAL_Control
0x18001dfd9  cmp     rcx, rax
0x18001dfdc  jz      short loc_18001DFFE
0x18001dfde  mov     rcx, [rcx+10h]
0x18001dfe2  lea     r9, aNull_0; "NULL"
0x18001dfe9  mov     edx, 3Eh ; '>'
0x18001dfee  mov     dword ptr [rsp+38h+var_18], edi
0x18001dff2  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001dff9  call    WPP_SF_Sd
0x18001dffe  mov     eax, edi
0x18001e000  jmp     short loc_18001E078
0x18001e002  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001e007  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001e00e  mov     r9d, 20019h; samDesired
0x18001e014  mov     [rsp+38h+var_18], rbx; phkResult
0x18001e019  xor     r8d, r8d; ulOptions
0x18001e01c  call    cs:__imp_RegOpenKeyExW
0x18001e023  nop     dword ptr [rax+rax+00h]
0x18001e028  mov     ebx, eax
0x18001e02a  test    eax, eax
0x18001e02c  jz      short loc_18001E063
0x18001e02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e035  lea     rax, WPP_GLOBAL_Control
0x18001e03c  cmp     rcx, rax
0x18001e03f  jz      short loc_18001E065
0x18001e041  mov     rcx, [rcx+10h]
0x18001e045  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001e04c  mov     edx, 3Fh ; '?'
0x18001e051  mov     dword ptr [rsp+38h+var_18], ebx
0x18001e055  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001e05c  call    WPP_SF_Sd
0x18001e061  jmp     short loc_18001E065
0x18001e063  xor     ebx, ebx
0x18001e065  mov     rcx, [rsp+38h+phkResult]; hKey
0x18001e06a  call    cs:__imp_RegCloseKey
0x18001e071  nop     dword ptr [rax+rax+00h]
0x18001e076  mov     eax, ebx
0x18001e078  mov     rbx, [rsp+38h+arg_8]
0x18001e07d  add     rsp, 30h
0x18001e081  pop     rdi
0x18001e082  retn
```
