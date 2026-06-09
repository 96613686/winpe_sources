# _lambda_593abc42667a9590cca80463005afefb_::operator()

- ea: `0x1800be388`
- end: `0x1800be41c`
- name: `_lambda_593abc42667a9590cca80463005afefb_::operator()`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800be368`
- `0x1800be424`

## callees

- `0x1800b8834`
- `0x1800bef90`

## import_xrefs

- `SHLWAPI!SHDeleteValueW` at `0x1800be3c5`
- `SHLWAPI!SHDeleteValueW` at `0x1800be3dc`
- `SHLWAPI!SHDeleteValueW` at `0x1800be3f3`
- `SHLWAPI!SHDeleteValueW` at `0x1800be40a`
- `SHLWAPI!SHDeleteValueW` at `0x1800be3c5`
- `SHLWAPI!SHDeleteValueW` at `0x1800be3dc`
- `SHLWAPI!SHDeleteValueW` at `0x1800be3f3`
- `SHLWAPI!SHDeleteValueW` at `0x1800be40a`

## pseudocode

```c
__int64 __fastcall lambda_593abc42667a9590cca80463005afefb_::operator()(_BYTE **a1)
{
  const wchar_t *v1; // rdx

  v1 = L"Clearing Auto-logon values due to failure.";
  if ( !**a1 )
    v1 = L"Clearing Auto-logon values per request";
  UnattendLogW(0, v1);
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoAdminLogon");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"SystemAutoLogon");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultUserName");
  SHDeleteValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
    L"IsConnectedAutoLogon");
  return SetAutologonPassword(0);
}

```

## disassembly

```asm
0x1800be388  push    rbx
0x1800be38a  sub     rsp, 20h
0x1800be38e  mov     rax, [rcx]
0x1800be391  lea     rdx, aClearingAutoLo; "Clearing Auto-logon values due to failu"...
0x1800be398  lea     rcx, aClearingAutoLo_0; "Clearing Auto-logon values per request"
0x1800be39f  cmp     byte ptr [rax], 0
0x1800be3a2  cmovz   rdx, rcx
0x1800be3a6  xor     ecx, ecx
0x1800be3a8  call    UnattendLogW
0x1800be3ad  mov     rbx, 0FFFFFFFF80000002h
0x1800be3b4  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x1800be3bb  mov     rcx, rbx; hkey
0x1800be3be  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be3c5  call    cs:__imp_SHDeleteValueW
0x1800be3cb  lea     r8, aSystemautologo; "SystemAutoLogon"
0x1800be3d2  mov     rcx, rbx; hkey
0x1800be3d5  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be3dc  call    cs:__imp_SHDeleteValueW
0x1800be3e2  lea     r8, aDefaultusernam; "DefaultUserName"
0x1800be3e9  mov     rcx, rbx; hkey
0x1800be3ec  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be3f3  call    cs:__imp_SHDeleteValueW
0x1800be3f9  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x1800be400  mov     rcx, rbx; hkey
0x1800be403  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be40a  call    cs:__imp_SHDeleteValueW
0x1800be410  xor     ecx, ecx; SourceString
0x1800be412  add     rsp, 20h
0x1800be416  pop     rbx
0x1800be417  jmp     _SetAutologonPassword
```
