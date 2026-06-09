# CSid::InitializeFromName(ushort *)

- ea: `0x180043cd4`
- end: `0x180043dff`
- name: `?InitializeFromName@CSid@@QEAAJPEAG@Z`
- size: `299`
- prototype: `__int64 __fastcall(CSid *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b83c`
- `0x18003bb7c`

## callees

- `0x180001e60`
- `0x180043c9c`
- `0x180043cd4`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d8a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180043d80`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180043d80`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180043d3b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180043d3b`

## pseudocode

```c
__int64 __fastcall CSid::InitializeFromName(CSid *this, unsigned __int16 *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  void *v6; // rax
  signed int v7; // eax
  DWORD cbSid; // [rsp+30h] [rbp-29h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-25h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-21h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE Sid[48]; // [rsp+60h] [rbp+7h] BYREF

  v2 = 0;
  peUse = 0;
  CSid::Initialize(this);
  cbSid = 44;
  cchReferencedDomainName = 16;
  if ( LookupAccountNameLocalW(a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_5;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_5:
    v6 = CoTaskMemAlloc(cbSid);
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      if ( CopySid(cbSid, v6, Sid) )
        goto LABEL_12;
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_12:
        StringCchCopyW((unsigned __int16 *)this + 6, 0x101u, a2);
        StringCchCopyW((unsigned __int16 *)this + 263, 0x10u, ReferencedDomainName);
        *((_DWORD *)this + 140) = peUse;
        return (unsigned int)v2;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
  CSid::Initialize(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180043cd4  mov     [rsp-8+arg_10], rbx
0x180043cd9  push    rbp
0x180043cda  push    rsi
0x180043cdb  push    rdi
0x180043cdc  lea     rbp, [rsp-47h]
0x180043ce1  sub     rsp, 0A0h
0x180043ce8  mov     rax, cs:__security_cookie
0x180043cef  xor     rax, rsp
0x180043cf2  mov     [rbp+57h+var_20], rax
0x180043cf6  xor     ebx, ebx
0x180043cf8  mov     rsi, rdx
0x180043cfb  mov     [rbp+57h+cbSid], ebx
0x180043cfe  mov     rdi, rcx
0x180043d01  mov     [rbp+57h+var_7C], ebx
0x180043d04  mov     [rbp+57h+var_78], ebx
0x180043d07  call    ?Initialize@CSid@@AEAAXXZ; CSid::Initialize(void)
0x180043d0c  lea     rax, [rbp+57h+var_78]
0x180043d10  mov     [rbp+57h+cbSid], 2Ch ; ','
0x180043d17  mov     [rsp+0B0h+peUse], rax; peUse
0x180043d1c  lea     r9, [rbp+57h+ReferencedDomainName]; ReferencedDomainName
0x180043d20  lea     rax, [rbp+57h+var_7C]
0x180043d24  mov     [rbp+57h+var_7C], 10h
0x180043d2b  lea     r8, [rbp+57h+cbSid]; cbSid
0x180043d2f  mov     [rsp+0B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180043d34  lea     rdx, [rbp+57h+Sid]; Sid
0x180043d38  mov     rcx, rsi; lpAccountName
0x180043d3b  call    cs:__imp_LookupAccountNameLocalW
0x180043d41  test    eax, eax
0x180043d43  jnz     short loc_180043D5E
0x180043d45  call    cs:__imp_GetLastError
0x180043d4b  mov     ebx, eax
0x180043d4d  test    eax, eax
0x180043d4f  jle     short loc_180043D5A
0x180043d51  movzx   ebx, ax
0x180043d54  or      ebx, 80070000h
0x180043d5a  test    ebx, ebx
0x180043d5c  js      short loc_180043DA3
0x180043d5e  mov     ecx, [rbp+57h+cbSid]; cb
0x180043d61  call    cs:__imp_CoTaskMemAlloc
0x180043d67  mov     [rdi], rax
0x180043d6a  test    rax, rax
0x180043d6d  jnz     short loc_180043D76
0x180043d6f  mov     ebx, 8007000Eh
0x180043d74  jmp     short loc_180043DA3
0x180043d76  mov     ecx, [rbp+57h+cbSid]; nDestinationSidLength
0x180043d79  lea     r8, [rbp+57h+Sid]; pSourceSid
0x180043d7d  mov     rdx, rax; pDestinationSid
0x180043d80  call    cs:__imp_CopySid
0x180043d86  test    eax, eax
0x180043d88  jnz     short loc_180043DAD
0x180043d8a  call    cs:__imp_GetLastError
0x180043d90  mov     ebx, eax
0x180043d92  test    eax, eax
0x180043d94  jle     short loc_180043D9F
0x180043d96  movzx   ebx, ax
0x180043d99  or      ebx, 80070000h
0x180043d9f  test    ebx, ebx
0x180043da1  jns     short loc_180043DAD
0x180043da3  mov     rcx, rdi; this
0x180043da6  call    ?Initialize@CSid@@AEAAXXZ; CSid::Initialize(void)
0x180043dab  jmp     short loc_180043DDE
0x180043dad  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x180043db1  mov     r8, rsi; unsigned __int16 *
0x180043db4  mov     edx, 101h; unsigned __int64
0x180043db9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043dbe  lea     rcx, [rdi+20Eh]; unsigned __int16 *
0x180043dc5  mov     edx, 10h; unsigned __int64
0x180043dca  lea     r8, [rbp+57h+ReferencedDomainName]; unsigned __int16 *
0x180043dce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043dd3  mov     r10d, [rbp+57h+var_78]
0x180043dd7  mov     [rdi+230h], r10d
0x180043dde  mov     eax, ebx
0x180043de0  mov     rcx, [rbp+57h+var_20]
0x180043de4  xor     rcx, rsp; StackCookie
0x180043de7  call    __security_check_cookie
0x180043dec  mov     rbx, [rsp+0B0h+arg_10]
0x180043df4  add     rsp, 0A0h
0x180043dfb  pop     rdi
0x180043dfc  pop     rsi
0x180043dfd  pop     rbp
0x180043dfe  retn
```
