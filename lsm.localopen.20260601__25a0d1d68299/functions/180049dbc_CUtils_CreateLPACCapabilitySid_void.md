# CUtils::CreateLPACCapabilitySid(void * *)

- ea: `0x180049dbc`
- end: `0x180049e4c`
- name: `?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ab80`
- `0x18002f7c0`

## callees

- `0x1800077a0`
- `0x180049dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180049df9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180049df9`

## string_xrefs

- `0x180049dd3`: `ppLPACCapabilitySid`
- `0x180049dc7`: `CUtils::CreateLPACCapabilitySid`
- `0x180049e28`: `CUtils::CreateLPACCapabilitySid`
- `0x180049e32`: `ConvertStringSidToSidW failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateLPACCapabilitySid(PSID *Sid)
{
  signed int v1; // ebx
  signed int LastError; // eax

  if ( Sid )
  {
    v1 = 0;
    if ( !ConvertStringSidToSidW(
            L"S-1-15-3-1024-1864111754-776273317-3666925027-2523908081-3792458206-3582472437-4114419977-1582884857",
            Sid) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
        _DbgPrintMessage(8, "ConvertStringSidToSidW failed: 0x%x in %s", v1, "CUtils::CreateLPACCapabilitySid");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "ppLPACCapabilitySid", "CUtils::CreateLPACCapabilitySid");
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180049dbc  push    rbx
0x180049dbe  sub     rsp, 20h
0x180049dc2  test    rcx, rcx
0x180049dc5  jnz     short loc_180049DED
0x180049dc7  lea     r9, aCutilsCreatelp_0; "CUtils::CreateLPACCapabilitySid"
0x180049dce  mov     ecx, 8; int
0x180049dd3  lea     r8, aPplpaccapabili; "ppLPACCapabilitySid"
0x180049dda  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180049de1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180049de6  mov     ebx, 80070057h
0x180049deb  jmp     short loc_180049E43
0x180049ded  mov     rdx, rcx; Sid
0x180049df0  xor     ebx, ebx
0x180049df2  lea     rcx, StringSid; "S-1-15-3-1024-1864111754-776273317-3666"...
0x180049df9  call    cs:__imp_ConvertStringSidToSidW
0x180049e00  nop     dword ptr [rax+rax+00h]
0x180049e05  test    eax, eax
0x180049e07  jnz     short loc_180049E43
0x180049e09  call    cs:__imp_GetLastError
0x180049e10  nop     dword ptr [rax+rax+00h]
0x180049e15  mov     ebx, eax
0x180049e17  test    eax, eax
0x180049e19  jle     short loc_180049E24
0x180049e1b  movzx   ebx, ax
0x180049e1e  or      ebx, 80070000h
0x180049e24  test    ebx, ebx
0x180049e26  jns     short loc_180049E43
0x180049e28  lea     r9, aCutilsCreatelp_0; "CUtils::CreateLPACCapabilitySid"
0x180049e2f  mov     r8d, ebx
0x180049e32  lea     rdx, aConvertstrings_1; "ConvertStringSidToSidW failed: 0x%x in "...
0x180049e39  mov     ecx, 8; int
0x180049e3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180049e43  mov     eax, ebx
0x180049e45  add     rsp, 20h
0x180049e49  pop     rbx
0x180049e4a  retn
```
