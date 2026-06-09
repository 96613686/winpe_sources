# CNonClusterTmInstance::CreateRegistryKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800527b0`
- end: `0x1800528ca`
- name: `?CreateRegistryKey@CNonClusterTmInstance@@UEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `282`
- prototype: `int(CNonClusterTmInstance *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800527b0`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800528af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800528af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005286e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005286e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005281b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005282b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005283b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005281b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005282b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005283b`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::CreateRegistryKey(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        DWORD a3,
        REGSAM a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes)
{
  int v9; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  HKEY v12; // [rsp+50h] [rbp-38h] BYREF
  HKEY v13; // [rsp+58h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+10h] BYREF

  v12 = 0;
  hKey = 0;
  v13 = 0;
  if ( !a2 )
    return 2147942487LL;
  v9 = RegConnectHostnameW(this[5], HKEY_LOCAL_MACHINE, &v12);
  v10 = v9;
  v11 = v9 <= 0;
  if ( !v9 )
  {
    v9 = RegOpenKeyExW(v12, L"Software\\Microsoft\\MSDTC", 0, 0x104u, &hKey);
    v10 = v9;
    v11 = v9 <= 0;
    if ( !v9 )
    {
      v9 = RegCreateKeyExW(hKey, a2, 0, 0, a3, a4, lpSecurityAttributes, &v13, 0);
      if ( !v9 )
        goto LABEL_6;
      if ( v9 <= 0 )
      {
        v10 = v9;
        goto LABEL_6;
      }
      goto LABEL_5;
    }
  }
  if ( !v11 )
LABEL_5:
    v10 = (unsigned __int16)v9 | 0x80070000;
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 )
    RegCloseKey(v13);
  if ( v12 )
    RegCloseKey(v12);
  return v10;
}

```

## disassembly

```asm
0x1800527b0  mov     rax, rsp
0x1800527b3  push    rbx
0x1800527b4  push    rbp
0x1800527b5  push    rsi
0x1800527b6  push    rdi
0x1800527b7  sub     rsp, 68h
0x1800527bb  mov     qword ptr [rax-38h], 0
0x1800527c3  mov     esi, r9d
0x1800527c6  mov     qword ptr [rax+10h], 0
0x1800527ce  mov     ebp, r8d
0x1800527d1  mov     qword ptr [rax-30h], 0
0x1800527d9  mov     rdi, rdx
0x1800527dc  test    rdx, rdx
0x1800527df  jnz     short loc_1800527E8
0x1800527e1  mov     eax, 80070057h
0x1800527e6  jmp     short loc_180052843
0x1800527e8  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1800527ec  lea     r8, [rsp+88h+var_38]; HKEY *
0x1800527f1  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800527f8  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x1800527fd  mov     ebx, eax
0x1800527ff  test    eax, eax
0x180052801  jz      short loc_18005284C
0x180052803  jle     short loc_18005280E
0x180052805  movzx   ebx, ax
0x180052808  or      ebx, 80070000h
0x18005280e  mov     rcx, [rsp+88h+hKey]; hKey
0x180052816  test    rcx, rcx
0x180052819  jz      short loc_180052821
0x18005281b  call    cs:__imp_RegCloseKey
0x180052821  mov     rcx, [rsp+88h+var_30]; hKey
0x180052826  test    rcx, rcx
0x180052829  jz      short loc_180052831
0x18005282b  call    cs:__imp_RegCloseKey
0x180052831  mov     rcx, [rsp+88h+var_38]; hKey
0x180052836  test    rcx, rcx
0x180052839  jz      short loc_180052841
0x18005283b  call    cs:__imp_RegCloseKey
0x180052841  mov     eax, ebx
0x180052843  add     rsp, 68h
0x180052847  pop     rdi
0x180052848  pop     rsi
0x180052849  pop     rbp
0x18005284a  pop     rbx
0x18005284b  retn
0x18005284c  mov     rcx, [rsp+88h+var_38]; hKey
0x180052851  lea     rax, [rsp+88h+hKey]
0x180052859  mov     r9d, 104h; samDesired
0x18005285f  mov     [rsp+88h+phkResult], rax; phkResult
0x180052864  xor     r8d, r8d; ulOptions
0x180052867  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x18005286e  call    cs:__imp_RegOpenKeyExW
0x180052874  mov     ebx, eax
0x180052876  test    eax, eax
0x180052878  jnz     short loc_180052803
0x18005287a  mov     rcx, [rsp+88h+hKey]; hKey
0x180052882  lea     rax, [rsp+88h+var_30]
0x180052887  mov     [rsp+88h+lpdwDisposition], rbx; lpdwDisposition
0x18005288c  xor     r9d, r9d; lpClass
0x18005288f  mov     [rsp+88h+var_50], rax; phkResult
0x180052894  xor     r8d, r8d; Reserved
0x180052897  mov     rax, [rsp+88h+arg_20]
0x18005289f  mov     rdx, rdi; lpSubKey
0x1800528a2  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800528a7  mov     [rsp+88h+samDesired], esi; samDesired
0x1800528ab  mov     dword ptr [rsp+88h+phkResult], ebp; dwOptions
0x1800528af  call    cs:__imp_RegCreateKeyExW
0x1800528b5  test    eax, eax
0x1800528b7  jz      loc_18005280E
0x1800528bd  jg      loc_180052805
0x1800528c3  mov     ebx, eax
0x1800528c5  jmp     loc_18005280E
```
