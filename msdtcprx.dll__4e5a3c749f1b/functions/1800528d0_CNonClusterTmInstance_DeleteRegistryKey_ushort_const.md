# CNonClusterTmInstance::DeleteRegistryKey(ushort const *)

- ea: `0x1800528d0`
- end: `0x180052991`
- name: `?DeleteRegistryKey@CNonClusterTmInstance@@UEAAJPEBG@Z`
- size: `193`
- prototype: `int(CNonClusterTmInstance *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800528d0`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005296d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005296d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005292b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005293b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005292b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005293b`
- `ADVAPI32!RegDeleteKeyW` at `0x180052981`
- `ADVAPI32!RegDeleteKeyW` at `0x180052981`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::DeleteRegistryKey(const unsigned __int16 **this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  hKey = 0;
  if ( !a2 )
    return 2147942487LL;
  v4 = RegConnectHostnameW(this[5], HKEY_LOCAL_MACHINE, &v8);
  v5 = v4;
  v6 = v4 <= 0;
  if ( !v4 )
  {
    v4 = RegOpenKeyExW(v8, L"Software\\Microsoft\\MSDTC", 0, 0x10100u, &hKey);
    v5 = v4;
    v6 = v4 <= 0;
    if ( !v4 )
    {
      v4 = RegDeleteKeyW(hKey, a2);
      if ( !v4 )
        goto LABEL_6;
      if ( v4 <= 0 )
      {
        v5 = v4;
        goto LABEL_6;
      }
      goto LABEL_5;
    }
  }
  if ( !v6 )
LABEL_5:
    v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    RegCloseKey(v8);
  return v5;
}

```

## disassembly

```asm
0x1800528d0  mov     [rsp+arg_0], rbx
0x1800528d5  push    rdi
0x1800528d6  sub     rsp, 30h
0x1800528da  mov     [rsp+38h+arg_10], 0
0x1800528e3  mov     rdi, rdx
0x1800528e6  mov     [rsp+38h+hKey], 0
0x1800528ef  test    rdx, rdx
0x1800528f2  jnz     short loc_1800528FB
0x1800528f4  mov     eax, 80070057h
0x1800528f9  jmp     short loc_180052943
0x1800528fb  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1800528ff  lea     r8, [rsp+38h+arg_10]; HKEY *
0x180052904  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18005290b  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x180052910  mov     ebx, eax
0x180052912  test    eax, eax
0x180052914  jz      short loc_18005294E
0x180052916  jle     short loc_180052921
0x180052918  movzx   ebx, ax
0x18005291b  or      ebx, 80070000h
0x180052921  mov     rcx, [rsp+38h+hKey]; hKey
0x180052926  test    rcx, rcx
0x180052929  jz      short loc_180052931
0x18005292b  call    cs:__imp_RegCloseKey
0x180052931  mov     rcx, [rsp+38h+arg_10]; hKey
0x180052936  test    rcx, rcx
0x180052939  jz      short loc_180052941
0x18005293b  call    cs:__imp_RegCloseKey
0x180052941  mov     eax, ebx
0x180052943  mov     rbx, [rsp+38h+arg_0]
0x180052948  add     rsp, 30h
0x18005294c  pop     rdi
0x18005294d  retn
0x18005294e  mov     rcx, [rsp+38h+arg_10]; hKey
0x180052953  lea     rax, [rsp+38h+hKey]
0x180052958  mov     r9d, 10100h; samDesired
0x18005295e  mov     [rsp+38h+phkResult], rax; phkResult
0x180052963  xor     r8d, r8d; ulOptions
0x180052966  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x18005296d  call    cs:__imp_RegOpenKeyExW
0x180052973  mov     ebx, eax
0x180052975  test    eax, eax
0x180052977  jnz     short loc_180052916
0x180052979  mov     rcx, [rsp+38h+hKey]; hKey
0x18005297e  mov     rdx, rdi; lpSubKey
0x180052981  call    cs:__imp_RegDeleteKeyW
0x180052987  test    eax, eax
0x180052989  jz      short loc_180052921
0x18005298b  jg      short loc_180052918
0x18005298d  mov     ebx, eax
0x18005298f  jmp     short loc_180052921
```
