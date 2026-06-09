# CSharePageProgress::_s_IsSleepEnabled(void)

- ea: `0x18006e5b0`
- end: `0x18006e6eb`
- name: `?_s_IsSleepEnabled@CSharePageProgress@@CAHXZ`
- size: `315`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18006e6f4`

## callees

- `0x1800254e0`
- `0x180026394`
- `0x18006e5b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e6c2`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18006e5e3`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18006e5e3`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18006e659`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18006e6ae`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18006e659`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18006e6ae`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18006e604`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18006e604`

## pseudocode

```c
__int64 CSharePageProgress::_s_IsSleepEnabled(void)
{
  unsigned int v0; // ebx
  BYTE Buffer[4]; // [rsp+40h] [rbp-19h] BYREF
  DWORD BufferSize; // [rsp+44h] [rbp-15h] BYREF
  GUID *ActivePolicyGuid; // [rsp+48h] [rbp-11h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+50h] [rbp-9h] BYREF

  ActivePolicyGuid = 0;
  v0 = 0;
  if ( !PowerGetActiveScheme(0, &ActivePolicyGuid) )
  {
    memset_0(&spc, 0, sizeof(spc));
    if ( GetPwrCapabilities(&spc) )
    {
      if ( (spc.SystemS1 || spc.SystemS2 || spc.SystemS3)
        && (*(_DWORD *)Buffer = 0,
            BufferSize = 4,
            !PowerReadACValue(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_STANDBY_TIMEOUT, 0, Buffer, &BufferSize))
        && *(_DWORD *)Buffer )
      {
        v0 = 1;
      }
      else if ( spc.SystemS4 )
      {
        if ( spc.HiberFilePresent )
        {
          *(_DWORD *)Buffer = 0;
          BufferSize = 4;
          if ( !PowerReadACValue(
                  0,
                  ActivePolicyGuid,
                  &GUID_SLEEP_SUBGROUP,
                  &GUID_HIBERNATE_TIMEOUT,
                  0,
                  Buffer,
                  &BufferSize) )
            LOBYTE(v0) = *(_DWORD *)Buffer != 0;
        }
      }
    }
    LocalFree(ActivePolicyGuid);
  }
  return v0;
}

```

## disassembly

```asm
0x18006e5b0  mov     [rsp-8+arg_0], rbx
0x18006e5b5  mov     [rsp-8+arg_8], rdi
0x18006e5ba  push    rbp
0x18006e5bb  lea     rbp, [rsp-57h]
0x18006e5c0  sub     rsp, 0B0h
0x18006e5c7  mov     rax, cs:__security_cookie
0x18006e5ce  xor     rax, rsp
0x18006e5d1  mov     [rbp+57h+var_10], rax
0x18006e5d5  xor     edi, edi
0x18006e5d7  lea     rdx, [rbp+57h+ActivePolicyGuid]; ActivePolicyGuid
0x18006e5db  xor     ecx, ecx; UserRootPowerKey
0x18006e5dd  mov     [rbp+57h+ActivePolicyGuid], rdi
0x18006e5e1  mov     ebx, edi
0x18006e5e3  call    cs:__imp_PowerGetActiveScheme
0x18006e5e9  test    eax, eax
0x18006e5eb  jnz     loc_18006E6C8
0x18006e5f1  xor     edx, edx; Val
0x18006e5f3  lea     r8d, [rdi+4Ch]; Size
0x18006e5f7  lea     rcx, [rbp+57h+spc]; void *
0x18006e5fb  call    memset_0
0x18006e600  lea     rcx, [rbp+57h+spc]; lpspc
0x18006e604  call    cs:__imp_GetPwrCapabilities
0x18006e60a  test    al, al
0x18006e60c  jz      loc_18006E6BE
0x18006e612  cmp     [rbp+57h+spc.SystemS1], dil
0x18006e616  jnz     short loc_18006E624
0x18006e618  cmp     [rbp+57h+spc.SystemS2], dil
0x18006e61c  jnz     short loc_18006E624
0x18006e61e  cmp     [rbp+57h+spc.SystemS3], dil
0x18006e622  jz      short loc_18006E66D
0x18006e624  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18006e628  lea     rax, [rbp+57h+var_6C]
0x18006e62c  mov     [rsp+0B0h+BufferSize], rax; BufferSize
0x18006e631  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x18006e638  lea     rax, [rbp+57h+var_70]
0x18006e63c  mov     dword ptr [rbp+57h+var_70], edi
0x18006e63f  mov     [rsp+0B0h+Buffer], rax; Buffer
0x18006e644  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18006e64b  xor     ecx, ecx; RootPowerKey
0x18006e64d  mov     [rsp+0B0h+Type], rdi; Type
0x18006e652  mov     [rbp+57h+var_6C], 4
0x18006e659  call    cs:__imp_PowerReadACValue
0x18006e65f  test    eax, eax
0x18006e661  jnz     short loc_18006E66D
0x18006e663  cmp     dword ptr [rbp+57h+var_70], edi
0x18006e666  jz      short loc_18006E66D
0x18006e668  lea     ebx, [rax+1]
0x18006e66b  jmp     short loc_18006E6BE
0x18006e66d  cmp     [rbp+57h+spc.SystemS4], dil
0x18006e671  jz      short loc_18006E6BE
0x18006e673  cmp     [rbp+57h+spc.HiberFilePresent], dil
0x18006e677  jz      short loc_18006E6BE
0x18006e679  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18006e67d  lea     rax, [rbp+57h+var_6C]
0x18006e681  mov     [rsp+0B0h+BufferSize], rax; BufferSize
0x18006e686  lea     r9, GUID_HIBERNATE_TIMEOUT; PowerSettingGuid
0x18006e68d  lea     rax, [rbp+57h+var_70]
0x18006e691  mov     dword ptr [rbp+57h+var_70], edi
0x18006e694  mov     [rsp+0B0h+Buffer], rax; Buffer
0x18006e699  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18006e6a0  xor     ecx, ecx; RootPowerKey
0x18006e6a2  mov     [rsp+0B0h+Type], rdi; Type
0x18006e6a7  mov     [rbp+57h+var_6C], 4
0x18006e6ae  call    cs:__imp_PowerReadACValue
0x18006e6b4  test    eax, eax
0x18006e6b6  jnz     short loc_18006E6BE
0x18006e6b8  cmp     dword ptr [rbp+57h+var_70], edi
0x18006e6bb  setnz   bl
0x18006e6be  mov     rcx, [rbp+57h+ActivePolicyGuid]; hMem
0x18006e6c2  call    cs:__imp_LocalFree
0x18006e6c8  mov     eax, ebx
0x18006e6ca  mov     rcx, [rbp+57h+var_10]
0x18006e6ce  xor     rcx, rsp; StackCookie
0x18006e6d1  call    __security_check_cookie
0x18006e6d6  lea     r11, [rsp+0B0h+var_s0]
0x18006e6de  mov     rbx, [r11+10h]
0x18006e6e2  mov     rdi, [r11+18h]
0x18006e6e6  mov     rsp, r11
0x18006e6e9  pop     rbp
0x18006e6ea  retn
```
