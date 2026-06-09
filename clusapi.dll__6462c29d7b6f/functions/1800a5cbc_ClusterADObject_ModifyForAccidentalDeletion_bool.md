# ClusterADObject::ModifyForAccidentalDeletion(bool)

- ea: `0x1800a5cbc`
- end: `0x1800a5ddb`
- name: `?ModifyForAccidentalDeletion@ClusterADObject@@QEAAJ_N@Z`
- size: `287`
- prototype: `__int64 __fastcall(ClusterADObject *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180074b2c`

## callees

- `0x180002f50`
- `0x18001cc2c`
- `0x180029578`
- `0x180038494`
- `0x1800a3a0c`
- `0x1800a5cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d32`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5cf3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5cf3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5d28`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall ClusterADObject::ModifyForAccidentalDeletion(ClusterADObject *this)
{
  int v1; // ebx
  signed int result; // eax
  signed int LastError; // eax
  signed int v4; // ebx
  LPWSTR v5; // rcx
  __int64 v6; // rax
  int v7; // r8d
  LPWSTR v8; // rcx
  LPWSTR StringSid; // [rsp+40h] [rbp-39h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v11[32]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE pSid[80]; // [rsp+70h] [rbp-9h] BYREF

  v1 = (int)this;
  cbSid = 68;
  if ( CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(pSid, &StringSid) )
    {
      v6 = std::wstring::wstring(v11, StringSid);
      v4 = ClusterADObject::AddAccessForSid(v1, 1, v7, 65600, v6, 0, 0, 0);
      std::wstring::_Tidy_deallocate(v11);
      v8 = StringSid;
      StringSid = 0;
      CTSmartPtr_PolicyLocalMem::DestroyMem(v8);
      if ( v4 >= 0 )
        return 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = StringSid;
      StringSid = 0;
      CTSmartPtr_PolicyLocalMem::DestroyMem(v5);
    }
    return v4;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800a5cbc  mov     [rsp-8+arg_8], rbx
0x1800a5cc1  push    rbp
0x1800a5cc2  lea     rbp, [rsp-57h]
0x1800a5cc7  sub     rsp, 0D0h
0x1800a5cce  mov     rax, cs:__security_cookie
0x1800a5cd5  xor     rax, rsp
0x1800a5cd8  mov     [rbp+57h+var_10], rax
0x1800a5cdc  mov     rbx, rcx
0x1800a5cdf  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800a5ce6  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800a5cea  lea     r8, [rbp+57h+pSid]; pSid
0x1800a5cee  xor     edx, edx; DomainSid
0x1800a5cf0  lea     ecx, [rdx+1]; WellKnownSidType
0x1800a5cf3  call    cs:__imp_CreateWellKnownSid
0x1800a5cf9  test    eax, eax
0x1800a5cfb  jnz     short loc_1800A5D18
0x1800a5cfd  call    cs:__imp_GetLastError
0x1800a5d03  test    eax, eax
0x1800a5d05  jle     loc_1800A5DBE
0x1800a5d0b  movzx   eax, ax
0x1800a5d0e  or      eax, 80070000h
0x1800a5d13  jmp     loc_1800A5DBE
0x1800a5d18  mov     [rbp+57h+StringSid], 0
0x1800a5d20  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800a5d24  lea     rcx, [rbp+57h+pSid]; Sid
0x1800a5d28  call    cs:__imp_ConvertSidToStringSidW
0x1800a5d2e  test    eax, eax
0x1800a5d30  jnz     short loc_1800A5D5C
0x1800a5d32  call    cs:__imp_GetLastError
0x1800a5d38  mov     ebx, eax
0x1800a5d3a  test    eax, eax
0x1800a5d3c  jle     short loc_1800A5D47
0x1800a5d3e  movzx   ebx, ax
0x1800a5d41  or      ebx, 80070000h
0x1800a5d47  mov     rcx, [rbp+57h+StringSid]; void *
0x1800a5d4b  mov     [rbp+57h+StringSid], 0
0x1800a5d53  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a5d58  mov     eax, ebx
0x1800a5d5a  jmp     short loc_1800A5DBE
0x1800a5d5c  mov     rdx, [rbp+57h+StringSid]
0x1800a5d60  lea     rcx, [rbp+57h+var_80]
0x1800a5d64  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a5d69  nop
0x1800a5d6a  mov     [rsp+0D0h+var_98], 0
0x1800a5d72  mov     [rsp+0D0h+var_A0], 0
0x1800a5d7b  mov     [rsp+0D0h+var_A8], 0
0x1800a5d83  mov     [rsp+0D0h+var_B0], rax
0x1800a5d88  mov     edx, 1
0x1800a5d8d  mov     r9d, 10040h
0x1800a5d93  mov     rcx, rbx
0x1800a5d96  call    ?AddAccessForSid@ClusterADObject@@AEAAJJJJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@JPEBQEB_WK@Z; ClusterADObject::AddAccessForSid(long,long,long,std::wstring const &,long,wchar_t const * const *,ulong)
0x1800a5d9b  mov     ebx, eax
0x1800a5d9d  lea     rcx, [rbp+57h+var_80]
0x1800a5da1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5da6  nop
0x1800a5da7  mov     rcx, [rbp+57h+StringSid]; void *
0x1800a5dab  mov     [rbp+57h+StringSid], 0
0x1800a5db3  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a5db8  test    ebx, ebx
0x1800a5dba  js      short loc_1800A5D58
0x1800a5dbc  xor     eax, eax
0x1800a5dbe  mov     rcx, [rbp+57h+var_10]
0x1800a5dc2  xor     rcx, rsp; StackCookie
0x1800a5dc5  call    __security_check_cookie
0x1800a5dca  mov     rbx, [rsp+0D0h+arg_8]
0x1800a5dd2  add     rsp, 0D0h
0x1800a5dd9  pop     rbp
0x1800a5dda  retn
```
