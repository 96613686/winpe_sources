# UnRegisterComClass(ushort const *,_GUID)

- ea: `0x180041e80`
- end: `0x18004203a`
- name: `?UnRegisterComClass@@YAJPEBGU_GUID@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, UUID *Uuid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fbe0`

## callees

- `0x180041e80`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041fde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041fde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041f71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041fbb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041f71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041fbb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004200e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004200e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041fa7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041fa7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180041ee3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180041ee3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041f1c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041f1c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041f36`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041f52`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041f36`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041f52`
- `RPCRT4!UuidToStringW` at `0x180041f00`
- `RPCRT4!UuidToStringW` at `0x180041f00`
- `RPCRT4!RpcStringFreeW` at `0x180041ffa`
- `RPCRT4!RpcStringFreeW` at `0x180041ffa`

## string_xrefs

- `0x180041f8e`: `CLSID`

## pseudocode

```c
__int64 __fastcall UnRegisterComClass(LPCWSTR lpSubKey, UUID *Uuid)
{
  int v4; // ebx
  LSTATUS v5; // eax
  bool v6; // cc
  const WCHAR *Str; // rax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v12[256]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  StringUuid = 0;
  memset_0(v12, 0, sizeof(v12));
  STRU::STRU((STRU *)v11, v12, 0x100u);
  if ( lpSubKey )
  {
    v4 = UuidToStringW(Uuid, &StringUuid);
    if ( !v4 )
    {
      v4 = STRU::Copy((STRU *)v11, L"{");
      if ( v4 >= 0 )
      {
        v4 = STRU::Append((STRU *)v11, StringUuid);
        if ( v4 >= 0 )
        {
          v4 = STRU::Append((STRU *)v11, L"}");
          if ( v4 >= 0 )
          {
            v5 = RegDeleteKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0);
            v6 = v5 <= 0;
            if ( v5
              || (v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &hKey), v6 = v5 <= 0, v5)
              || (Str = STRU::QueryStr((STRU *)v11), v5 = RegDeleteKeyExW(hKey, Str, 0, 0), v6 = v5 <= 0, v5) )
            {
              if ( v6 )
                v4 = v5;
              else
                v4 = (unsigned __int16)v5 | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180041e80  mov     [rsp-8+arg_10], rbx
0x180041e85  mov     [rsp-8+arg_18], rdi
0x180041e8a  push    rbp
0x180041e8b  lea     rbp, [rsp-190h]
0x180041e93  sub     rsp, 290h
0x180041e9a  mov     rax, cs:__security_cookie
0x180041ea1  xor     rax, rsp
0x180041ea4  mov     [rbp+190h+var_10], rax
0x180041eab  mov     rbx, rdx
0x180041eae  mov     [rsp+290h+hKey], 0
0x180041eb7  mov     rdi, rcx
0x180041eba  mov     [rsp+290h+StringUuid], 0
0x180041ec3  xor     edx, edx; Val
0x180041ec5  lea     rcx, [rbp+190h+var_210]; void *
0x180041ec9  mov     r8d, 200h; Size
0x180041ecf  call    memset_0
0x180041ed4  mov     r8d, 100h
0x180041eda  lea     rdx, [rbp+190h+var_210]
0x180041ede  lea     rcx, [rsp+290h+var_250]
0x180041ee3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180041ee9  test    rdi, rdi
0x180041eec  jnz     short loc_180041EF8
0x180041eee  mov     ebx, 80070057h
0x180041ef3  jmp     loc_180041FD4
0x180041ef8  lea     rdx, [rsp+290h+StringUuid]; StringUuid
0x180041efd  mov     rcx, rbx; Uuid
0x180041f00  call    cs:__imp_UuidToStringW
0x180041f06  mov     ebx, eax
0x180041f08  test    eax, eax
0x180041f0a  jnz     loc_180041FD4
0x180041f10  lea     rdx, asc_180062380; "{"
0x180041f17  lea     rcx, [rsp+290h+var_250]
0x180041f1c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180041f22  mov     ebx, eax
0x180041f24  test    eax, eax
0x180041f26  js      loc_180041FD4
0x180041f2c  mov     rdx, [rsp+290h+StringUuid]
0x180041f31  lea     rcx, [rsp+290h+var_250]
0x180041f36  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041f3c  mov     ebx, eax
0x180041f3e  test    eax, eax
0x180041f40  js      loc_180041FD4
0x180041f46  lea     rdx, asc_180062384; "}"
0x180041f4d  lea     rcx, [rsp+290h+var_250]
0x180041f52  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041f58  mov     ebx, eax
0x180041f5a  test    eax, eax
0x180041f5c  js      short loc_180041FD4
0x180041f5e  mov     rdx, rdi; lpSubKey
0x180041f61  xor     r9d, r9d; Reserved
0x180041f64  mov     rdi, 0FFFFFFFF80000000h
0x180041f6b  xor     r8d, r8d; samDesired
0x180041f6e  mov     rcx, rdi; hKey
0x180041f71  call    cs:__imp_RegDeleteKeyExW
0x180041f77  test    eax, eax
0x180041f79  jnz     short loc_180041FC5
0x180041f7b  lea     rax, [rsp+290h+hKey]
0x180041f80  mov     r9d, 0F003Fh; samDesired
0x180041f86  xor     r8d, r8d; ulOptions
0x180041f89  mov     [rsp+290h+phkResult], rax; phkResult
0x180041f8e  lea     rdx, aClsid; "CLSID"
0x180041f95  mov     rcx, rdi; hKey
0x180041f98  call    cs:__imp_RegOpenKeyExW
0x180041f9e  test    eax, eax
0x180041fa0  jnz     short loc_180041FC5
0x180041fa2  lea     rcx, [rsp+290h+var_250]
0x180041fa7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180041fad  mov     rcx, [rsp+290h+hKey]; hKey
0x180041fb2  xor     r9d, r9d; Reserved
0x180041fb5  mov     rdx, rax; lpSubKey
0x180041fb8  xor     r8d, r8d; samDesired
0x180041fbb  call    cs:__imp_RegDeleteKeyExW
0x180041fc1  test    eax, eax
0x180041fc3  jz      short loc_180041FD4
0x180041fc5  jg      short loc_180041FCB
0x180041fc7  mov     ebx, eax
0x180041fc9  jmp     short loc_180041FD4
0x180041fcb  movzx   ebx, ax
0x180041fce  or      ebx, 80070000h
0x180041fd4  mov     rcx, [rsp+290h+hKey]; hKey
0x180041fd9  test    rcx, rcx
0x180041fdc  jz      short loc_180041FED
0x180041fde  call    cs:__imp_RegCloseKey
0x180041fe4  mov     [rsp+290h+hKey], 0
0x180041fed  cmp     [rsp+290h+StringUuid], 0
0x180041ff3  jz      short loc_180042009
0x180041ff5  lea     rcx, [rsp+290h+StringUuid]; String
0x180041ffa  call    cs:__imp_RpcStringFreeW
0x180042000  mov     [rsp+290h+StringUuid], 0
0x180042009  lea     rcx, [rsp+290h+var_250]
0x18004200e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180042014  mov     eax, ebx
0x180042016  mov     rcx, [rbp+190h+var_10]
0x18004201d  xor     rcx, rsp; StackCookie
0x180042020  call    __security_check_cookie
0x180042025  lea     r11, [rsp+290h+var_s0]
0x18004202d  mov     rbx, [r11+20h]
0x180042031  mov     rdi, [r11+28h]
0x180042035  mov     rsp, r11
0x180042038  pop     rbp
0x180042039  retn
```
