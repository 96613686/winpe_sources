# IsUserAdmin(int &)

- ea: `0x180018d24`
- end: `0x180018e4b`
- name: `?IsUserAdmin@@YAKAEAH@Z`
- size: `295`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015414`

## callees

- `0x180003cf0`
- `0x180018d24`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dcd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018d8a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018d8a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018dc3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018dc3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018e21`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018e21`

## string_xrefs

- `0x180018df3`: `com\complus\dtc\shared\util\security.cpp`
- `0x180018de1`: `Unable to check token membership.`
- `0x180018da8`: `Unable to allocate and initialize SID.`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(PBOOL IsMember)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  const wchar_t *v4; // rcx
  __int64 v5; // r9
  __int64 nSubAuthority3; // [rsp+28h] [rbp-60h]
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v9; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v9.Value[4] = 1280;
  *(_DWORD *)v9.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&v9, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v3 = 0;
    if ( CheckTokenMembership(0, SidToCheck, IsMember) )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = L"Unable to check token membership.";
    v5 = 1208;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = L"Unable to allocate and initialize SID.";
    v5 = 1199;
  }
  LODWORD(nSubAuthority3) = LastError;
  TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\security.cpp", v5, L"IsUserAdmin", nSubAuthority3, v4);
LABEL_10:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x180018d24  mov     r11, rsp
0x180018d27  mov     [r11+10h], rbx
0x180018d2b  mov     [r11+18h], rsi
0x180018d2f  push    rdi
0x180018d30  sub     rsp, 80h
0x180018d37  mov     rax, cs:__security_cookie
0x180018d3e  xor     rax, rsp
0x180018d41  mov     [rsp+88h+var_18], rax
0x180018d46  xor     esi, esi
0x180018d48  mov     [rsp+88h+var_1C], 500h
0x180018d4f  lea     rax, [r11-28h]
0x180018d53  mov     [rsp+88h+var_20], esi
0x180018d57  mov     [r11-38h], rax
0x180018d5b  mov     rdi, rcx
0x180018d5e  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x180018d62  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180018d66  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x180018d6a  lea     r8d, [rsi+20h]; nSubAuthority0
0x180018d6e  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x180018d72  mov     r9d, 220h; nSubAuthority1
0x180018d78  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x180018d7c  mov     dl, 2; nSubAuthorityCount
0x180018d7e  mov     dword ptr [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x180018d82  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x180018d86  mov     [r11-28h], rsi
0x180018d8a  call    cs:__imp_AllocateAndInitializeSid
0x180018d90  test    eax, eax
0x180018d92  jnz     short loc_180018DB7
0x180018d94  call    cs:__imp_GetLastError
0x180018d9a  mov     ebx, eax
0x180018d9c  test    eax, eax
0x180018d9e  jle     short loc_180018DA8
0x180018da0  movzx   eax, ax
0x180018da3  or      eax, 80070000h
0x180018da8  lea     rcx, aUnableToAlloca_2; "Unable to allocate and initialize SID."
0x180018daf  mov     r9d, 4AFh
0x180018db5  jmp     short loc_180018DEE
0x180018db7  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x180018dbc  mov     r8, rdi; IsMember
0x180018dbf  xor     ecx, ecx; TokenHandle
0x180018dc1  mov     ebx, esi
0x180018dc3  call    cs:__imp_CheckTokenMembership
0x180018dc9  test    eax, eax
0x180018dcb  jnz     short loc_180018E17
0x180018dcd  call    cs:__imp_GetLastError
0x180018dd3  mov     ebx, eax
0x180018dd5  test    eax, eax
0x180018dd7  jle     short loc_180018DE1
0x180018dd9  movzx   eax, ax
0x180018ddc  or      eax, 80070000h
0x180018de1  lea     rcx, aUnableToCheckT_0; "Unable to check token membership."
0x180018de8  mov     r9d, 4B8h
0x180018dee  mov     qword ptr [rsp+88h+nSubAuthority4], rcx
0x180018df3  lea     r8, aComComplusDtcS_7; "com\\complus\\dtc\\shared\\util\\securi"...
0x180018dfa  mov     dword ptr [rsp+88h+nSubAuthority3], eax
0x180018dfe  mov     edx, 1
0x180018e03  lea     rax, aIsuseradmin; "IsUserAdmin"
0x180018e0a  mov     qword ptr [rsp+88h+nSubAuthority2], rax
0x180018e0f  lea     ecx, [rdx+6]
0x180018e12  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180018e17  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x180018e1c  test    rcx, rcx
0x180018e1f  jz      short loc_180018E27
0x180018e21  call    cs:__imp_FreeSid
0x180018e27  mov     eax, ebx
0x180018e29  mov     rcx, [rsp+88h+var_18]
0x180018e2e  xor     rcx, rsp; StackCookie
0x180018e31  call    __security_check_cookie
0x180018e36  lea     r11, [rsp+88h+var_8]
0x180018e3e  mov     rbx, [r11+18h]
0x180018e42  mov     rsi, [r11+20h]
0x180018e46  mov     rsp, r11
0x180018e49  pop     rdi
0x180018e4a  retn
```
