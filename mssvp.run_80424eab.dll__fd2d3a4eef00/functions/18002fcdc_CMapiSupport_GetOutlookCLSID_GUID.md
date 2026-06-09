# CMapiSupport::GetOutlookCLSID(_GUID *)

- ea: `0x18002fcdc`
- end: `0x18002fd37`
- name: `?GetOutlookCLSID@CMapiSupport@@SAJPEAU_GUID@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(LPCLSID lpclsid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019a20`
- `0x18001b4d0`

## callees

- `0x18002fcdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fcef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd03`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd2b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fcef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd03`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002fd2b`

## pseudocode

```c
int __fastcall CMapiSupport::GetOutlookCLSID(LPCLSID lpclsid)
{
  int result; // eax

  result = CLSIDFromProgID(L"Outlook.Application", lpclsid);
  if ( result < 0 )
  {
    result = CLSIDFromProgID(L"Outlook.Application.12", lpclsid);
    if ( result < 0 )
    {
      result = CLSIDFromProgID(L"Outlook.Application.11", lpclsid);
      if ( result < 0 )
        return CLSIDFromProgID(L"Outlook.Application.10", lpclsid);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002fcdc  push    rbx
0x18002fcde  sub     rsp, 20h
0x18002fce2  mov     rbx, rcx
0x18002fce5  mov     rdx, rcx; lpclsid
0x18002fce8  lea     rcx, aOutlookApplica_3; "Outlook.Application"
0x18002fcef  call    cs:__imp_CLSIDFromProgID
0x18002fcf5  test    eax, eax
0x18002fcf7  jns     short loc_18002FD31
0x18002fcf9  mov     rdx, rbx; lpclsid
0x18002fcfc  lea     rcx, aOutlookApplica_1; "Outlook.Application.12"
0x18002fd03  call    cs:__imp_CLSIDFromProgID
0x18002fd09  test    eax, eax
0x18002fd0b  jns     short loc_18002FD31
0x18002fd0d  mov     rdx, rbx; lpclsid
0x18002fd10  lea     rcx, aOutlookApplica_0; "Outlook.Application.11"
0x18002fd17  call    cs:__imp_CLSIDFromProgID
0x18002fd1d  test    eax, eax
0x18002fd1f  jns     short loc_18002FD31
0x18002fd21  mov     rdx, rbx; lpclsid
0x18002fd24  lea     rcx, aOutlookApplica_2; "Outlook.Application.10"
0x18002fd2b  call    cs:__imp_CLSIDFromProgID
0x18002fd31  add     rsp, 20h
0x18002fd35  pop     rbx
0x18002fd36  retn
```
