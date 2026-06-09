# CUtils::CreateLPACCapabilitySid(void * *)

- ea: `0x1800473dc`
- end: `0x18004745f`
- name: `?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019dc8`
- `0x18002d804`

## callees

- `0x1800074c0`
- `0x1800473dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047423`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180047419`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180047419`

## string_xrefs

- `0x1800473e7`: `CUtils::CreateLPACCapabilitySid`
- `0x18004743c`: `CUtils::CreateLPACCapabilitySid`
- `0x1800473f3`: `ppLPACCapabilitySid`
- `0x180047446`: `ConvertStringSidToSidW failed: 0x%x in %s`

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
0x1800473dc  push    rbx
0x1800473de  sub     rsp, 20h
0x1800473e2  test    rcx, rcx
0x1800473e5  jnz     short loc_18004740D
0x1800473e7  lea     r9, aCutilsCreatelp_0; "CUtils::CreateLPACCapabilitySid"
0x1800473ee  mov     ecx, 8; int
0x1800473f3  lea     r8, aPplpaccapabili; "ppLPACCapabilitySid"
0x1800473fa  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180047401  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180047406  mov     ebx, 80070057h
0x18004740b  jmp     short loc_180047457
0x18004740d  mov     rdx, rcx; Sid
0x180047410  xor     ebx, ebx
0x180047412  lea     rcx, StringSid; "S-1-15-3-1024-1864111754-776273317-3666"...
0x180047419  call    cs:__imp_ConvertStringSidToSidW
0x18004741f  test    eax, eax
0x180047421  jnz     short loc_180047457
0x180047423  call    cs:__imp_GetLastError
0x180047429  mov     ebx, eax
0x18004742b  test    eax, eax
0x18004742d  jle     short loc_180047438
0x18004742f  movzx   ebx, ax
0x180047432  or      ebx, 80070000h
0x180047438  test    ebx, ebx
0x18004743a  jns     short loc_180047457
0x18004743c  lea     r9, aCutilsCreatelp_0; "CUtils::CreateLPACCapabilitySid"
0x180047443  mov     r8d, ebx
0x180047446  lea     rdx, aConvertstrings_1; "ConvertStringSidToSidW failed: 0x%x in "...
0x18004744d  mov     ecx, 8; int
0x180047452  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180047457  mov     eax, ebx
0x180047459  add     rsp, 20h
0x18004745d  pop     rbx
0x18004745e  retn
```
