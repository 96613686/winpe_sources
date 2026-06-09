# WPP_SF__sid_

- ea: `0x1800b15a8`
- end: `0x1800b1630`
- name: `WPP_SF__sid_`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001249c`
- `0x18001a6fc`
- `0x180089d4c`
- `0x1800f5088`

## callees

- `0x1800b15a8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800b161f`
- `ntdll!EtwTraceMessage` at `0x1800b161f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b15c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b15eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b15c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b15eb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b15d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b15d4`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_(__int64 a1, unsigned __int16 a2, __int64 a3, char *a4)
{
  unsigned int v4; // ebp
  char *v5; // rbx
  DWORD LengthSid; // edi

  v4 = a2;
  v5 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_6:
      v5 = "NULL";
      return EtwTraceMessage(a1, 43, a3, v4, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, a3, v4, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x1800b15a8  push    rbx
0x1800b15aa  push    rbp
0x1800b15ab  push    rsi
0x1800b15ac  push    rdi
0x1800b15ad  push    r14
0x1800b15af  sub     rsp, 40h
0x1800b15b3  movzx   ebp, dx
0x1800b15b6  mov     rbx, r9
0x1800b15b9  mov     rsi, r8
0x1800b15bc  mov     r14, rcx
0x1800b15bf  test    r9, r9
0x1800b15c2  jz      short loc_1800B15DE
0x1800b15c4  mov     rcx, rbx; pSid
0x1800b15c7  call    cs:__imp_IsValidSid
0x1800b15cd  test    eax, eax
0x1800b15cf  jz      short loc_1800B15DE
0x1800b15d1  mov     rcx, rbx; pSid
0x1800b15d4  call    cs:__imp_GetLengthSid
0x1800b15da  mov     edi, eax
0x1800b15dc  jmp     short loc_1800B15E8
0x1800b15de  mov     edi, 5
0x1800b15e3  test    rbx, rbx
0x1800b15e6  jz      short loc_1800B15F5
0x1800b15e8  mov     rcx, rbx; pSid
0x1800b15eb  call    cs:__imp_IsValidSid
0x1800b15f1  test    eax, eax
0x1800b15f3  jnz     short loc_1800B15FC
0x1800b15f5  lea     rbx, aNull; "NULL"
0x1800b15fc  mov     eax, edi
0x1800b15fe  mov     r9d, ebp
0x1800b1601  mov     [rsp+68h+var_38], 0
0x1800b160a  mov     r8, rsi
0x1800b160d  mov     [rsp+68h+var_40], rax
0x1800b1612  mov     edx, 2Bh ; '+'
0x1800b1617  mov     rcx, r14
0x1800b161a  mov     [rsp+68h+var_48], rbx
0x1800b161f  call    cs:__imp_EtwTraceMessage
0x1800b1625  add     rsp, 40h
0x1800b1629  pop     r14
0x1800b162b  pop     rdi
0x1800b162c  pop     rsi
0x1800b162d  pop     rbp
0x1800b162e  pop     rbx
0x1800b162f  retn
```
