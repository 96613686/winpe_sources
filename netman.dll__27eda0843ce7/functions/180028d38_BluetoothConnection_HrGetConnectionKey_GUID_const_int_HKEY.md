# BluetoothConnection::HrGetConnectionKey(_GUID const *,int,HKEY__ * *)

- ea: `0x180028d38`
- end: `0x180028df6`
- name: `?HrGetConnectionKey@BluetoothConnection@@AEAAJPEBU_GUID@@HPEAPEAUHKEY__@@@Z`
- size: `190`
- prototype: `int(BluetoothConnection *__hidden this, const struct _GUID *, int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029128`

## callees

- `0x180001710`
- `0x180003d5c`
- `0x180028d38`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180028dc2`
- `ADVAPI32!RegCreateKeyExW` at `0x180028dc2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028d64`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028d64`

## pseudocode

```c
LSTATUS __fastcall BluetoothConnection::HrGetConnectionKey(
        BluetoothConnection *this,
        const struct _GUID *a2,
        __int64 a3,
        HKEY *a4)
{
  LSTATUS result; // eax
  OLECHAR sz[40]; // [rsp+50h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-228h] BYREF

  StringFromGUID2(a2, sz, 39);
  StringCchPrintfW(SubKey, 0x105u, c_szConnectionKeyFmt, sz);
  SubKey[260] = 0;
  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, a4, 0);
  if ( result )
  {
    *a4 = 0;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180028d38  push    rbx
0x180028d3a  sub     rsp, 2C0h
0x180028d41  mov     rax, cs:__security_cookie
0x180028d48  xor     rax, rsp
0x180028d4b  mov     [rsp+2C8h+var_18], rax
0x180028d53  mov     rcx, rdx; rguid
0x180028d56  mov     r8d, 27h ; '''; cchMax
0x180028d5c  lea     rdx, [rsp+2C8h+sz]; lpsz
0x180028d61  mov     rbx, r9
0x180028d64  call    cs:__imp_StringFromGUID2
0x180028d6a  lea     r9, [rsp+2C8h+sz]
0x180028d6f  mov     edx, 105h; unsigned __int64
0x180028d74  lea     r8, ?c_szConnectionKeyFmt@@3PAGA; "System\\CurrentControlSet\\Control\\Net"...
0x180028d7b  lea     rcx, [rsp+2C8h+SubKey]; unsigned __int16 *
0x180028d83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028d88  xor     eax, eax
0x180028d8a  lea     rdx, [rsp+2C8h+SubKey]; lpSubKey
0x180028d92  mov     [rsp+2C8h+lpdwDisposition], rax; lpdwDisposition
0x180028d97  xor     r9d, r9d; lpClass
0x180028d9a  mov     [rsp+2C8h+phkResult], rbx; phkResult
0x180028d9f  xor     r8d, r8d; Reserved
0x180028da2  mov     [rsp+2C8h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180028da7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028dae  mov     [rsp+2C8h+samDesired], 2001Fh; samDesired
0x180028db6  mov     [rsp+2C8h+dwOptions], eax; dwOptions
0x180028dba  mov     [rsp+2C8h+var_20], ax
0x180028dc2  call    cs:__imp_RegCreateKeyExW
0x180028dc8  test    eax, eax
0x180028dca  jz      short loc_180028DDD
0x180028dcc  mov     qword ptr [rbx], 0
0x180028dd3  jle     short loc_180028DDD
0x180028dd5  movzx   eax, ax
0x180028dd8  or      eax, 80070000h
0x180028ddd  mov     rcx, [rsp+2C8h+var_18]
0x180028de5  xor     rcx, rsp; StackCookie
0x180028de8  call    __security_check_cookie
0x180028ded  add     rsp, 2C0h
0x180028df4  pop     rbx
0x180028df5  retn
```
