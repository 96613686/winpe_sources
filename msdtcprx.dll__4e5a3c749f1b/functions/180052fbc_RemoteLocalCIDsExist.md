# RemoteLocalCIDsExist

- ea: `0x180052fbc`
- end: `0x1800530a5`
- name: `RemoteLocalCIDsExist`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800537f0`

## callees

- `0x1800125fc`
- `0x180052fbc`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005307c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005307c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053048`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053092`

## pseudocode

```c
__int64 __fastcall RemoteLocalCIDsExist(__int64 a1, _DWORD *a2)
{
  int RegistryHostName; // ebx
  signed int LastError; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+20h] BYREF

  *a2 = 0;
  hKey = 0;
  phkResult = 0;
  pv = 0;
  RegistryHostName = GetRegistryHostName(a1, (unsigned __int16 **)&pv);
  if ( RegistryHostName >= 0 )
  {
    if ( !(unsigned int)RegConnectHostnameW((const unsigned __int16 *)pv, HKEY_CLASSES_ROOT, &hKey) )
    {
      v6 = RegOpenKeyExW(hKey, L"CID.Local", 0, 0x20119u, &phkResult);
      if ( !v6 )
      {
        *a2 = 1;
        goto LABEL_13;
      }
      if ( (unsigned int)(v6 - 2) <= 1 )
      {
        *a2 = 0;
        goto LABEL_13;
      }
      if ( v6 <= 0 )
      {
        RegistryHostName = v6;
        goto LABEL_13;
      }
      v5 = (unsigned __int16)v6;
      goto LABEL_5;
    }
    LastError = GetLastError();
    RegistryHostName = LastError;
    if ( LastError > 0 )
    {
      v5 = (unsigned __int16)LastError;
LABEL_5:
      RegistryHostName = v5 | 0x80070000;
    }
  }
LABEL_13:
  CoTaskMemFree(pv);
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  return (unsigned int)RegistryHostName;
}

```

## disassembly

```asm
0x180052fbc  mov     rax, rsp
0x180052fbf  mov     [rax+8], rbx
0x180052fc3  push    rdi
0x180052fc4  sub     rsp, 30h
0x180052fc8  mov     rdi, rdx
0x180052fcb  mov     dword ptr [rdx], 0
0x180052fd1  lea     rdx, [rax+10h]
0x180052fd5  mov     qword ptr [rax+18h], 0
0x180052fdd  mov     qword ptr [rax+20h], 0
0x180052fe5  mov     qword ptr [rax+10h], 0
0x180052fed  call    GetRegistryHostName
0x180052ff2  mov     ebx, eax
0x180052ff4  test    eax, eax
0x180052ff6  js      short loc_180053077
0x180052ff8  mov     rcx, [rsp+38h+pv]; unsigned __int16 *
0x180052ffd  lea     r8, [rsp+38h+hKey]; HKEY *
0x180053002  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x180053009  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x18005300e  test    eax, eax
0x180053010  jz      short loc_180053029
0x180053012  call    cs:__imp_GetLastError
0x180053018  mov     ebx, eax
0x18005301a  test    eax, eax
0x18005301c  jle     short loc_180053077
0x18005301e  movzx   ebx, ax
0x180053021  or      ebx, 80070000h
0x180053027  jmp     short loc_180053077
0x180053029  mov     rcx, [rsp+38h+hKey]; hKey
0x18005302e  lea     rax, [rsp+38h+arg_18]
0x180053033  mov     r9d, 20119h; samDesired
0x180053039  mov     [rsp+38h+phkResult], rax; phkResult
0x18005303e  xor     r8d, r8d; ulOptions
0x180053041  lea     rdx, aCidLocal; "CID.Local"
0x180053048  call    cs:__imp_RegOpenKeyExW
0x18005304e  mov     ecx, eax
0x180053050  test    eax, eax
0x180053052  jnz     short loc_18005305C
0x180053054  mov     dword ptr [rdi], 1
0x18005305a  jmp     short loc_180053077
0x18005305c  add     eax, 0FFFFFFFEh
0x18005305f  cmp     eax, 1
0x180053062  jbe     short loc_180053071
0x180053064  test    ecx, ecx
0x180053066  jg      short loc_18005306C
0x180053068  mov     ebx, ecx
0x18005306a  jmp     short loc_180053077
0x18005306c  movzx   ebx, cx
0x18005306f  jmp     short loc_180053021
0x180053071  mov     dword ptr [rdi], 0
0x180053077  mov     rcx, [rsp+38h+pv]; pv
0x18005307c  call    cs:__imp_CoTaskMemFree
0x180053082  mov     rcx, [rsp+38h+arg_18]; hKey
0x180053087  call    cs:__imp_RegCloseKey
0x18005308d  mov     rcx, [rsp+38h+hKey]; hKey
0x180053092  call    cs:__imp_RegCloseKey
0x180053098  mov     eax, ebx
0x18005309a  mov     rbx, [rsp+38h+arg_0]
0x18005309f  add     rsp, 30h
0x1800530a3  pop     rdi
0x1800530a4  retn
```
