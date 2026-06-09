# FwRegDeleteKey

- ea: `0x180013a20`
- end: `0x180013ab4`
- name: `FwRegDeleteKey`
- size: `148`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x1800130bc`
- `0x180013a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180013a6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180013a6c`

## string_xrefs

- `0x180013a79`: `RegDeleteTreeW`
- `0x180013a80`: `FwRegDeleteKey`
- `0x180013a94`: `FwRegDeleteKey`

## pseudocode

```c
__int64 __fastcall FwRegDeleteKey(HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids, lpSubKey);
  v5 = RegDeleteTreeW(hKey, lpSubKey);
  if ( v5 )
  {
    v6 = FwReportErrorAsWinError("FwRegDeleteKey", "RegDeleteTreeW", v5);
    v4 = v6;
    if ( v6 < 0 )
      return (unsigned int)FwReportReturnError("FwRegDeleteKey", (unsigned int)v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180013a20  mov     [rsp+arg_0], rbx
0x180013a25  mov     [rsp+arg_8], rsi
0x180013a2a  push    rdi
0x180013a2b  sub     rsp, 20h
0x180013a2f  mov     rdi, rdx
0x180013a32  mov     rsi, rcx
0x180013a35  xor     ebx, ebx
0x180013a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a3e  lea     rax, WPP_GLOBAL_Control
0x180013a45  cmp     rcx, rax
0x180013a48  jz      short loc_180013A66
0x180013a4a  test    byte ptr [rcx+1Ch], 8
0x180013a4e  jz      short loc_180013A66
0x180013a50  mov     rcx, [rcx+10h]
0x180013a54  lea     edx, [rbx+0Dh]
0x180013a57  mov     r9, rdi
0x180013a5a  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x180013a61  call    WPP_SF_S
0x180013a66  mov     rdx, rdi; lpSubKey
0x180013a69  mov     rcx, rsi; hKey
0x180013a6c  call    cs:__imp_RegDeleteTreeW
0x180013a72  test    eax, eax
0x180013a74  jz      short loc_180013AA2
0x180013a76  mov     r8d, eax
0x180013a79  lea     rdx, aRegdeletetreew; "RegDeleteTreeW"
0x180013a80  lea     rcx, aFwregdeletekey_0; "FwRegDeleteKey"
0x180013a87  call    FwReportErrorAsWinError
0x180013a8c  mov     ebx, eax
0x180013a8e  test    eax, eax
0x180013a90  jns     short loc_180013AA2
0x180013a92  mov     edx, eax
0x180013a94  lea     rcx, aFwregdeletekey_0; "FwRegDeleteKey"
0x180013a9b  call    FwReportReturnError
0x180013aa0  mov     ebx, eax
0x180013aa2  mov     rsi, [rsp+28h+arg_8]
0x180013aa7  mov     eax, ebx
0x180013aa9  mov     rbx, [rsp+28h+arg_0]
0x180013aae  add     rsp, 20h
0x180013ab2  pop     rdi
0x180013ab3  retn
```
