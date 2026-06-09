# _anonymous_namespace_::SrumDataCache::BuildKeyData

- ea: `0x180025278`
- end: `0x1800253d7`
- name: `_anonymous_namespace_::SrumDataCache::BuildKeyData`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800087e8`

## callees

- `0x180025278`
- `0x1800253e0`
- `0x18003bce0`
- `0x18004ca90`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002537d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002537d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002531d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002531d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180025351`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180025351`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall anonymous_namespace_::SrumDataCache::BuildKeyData(__int64 a1, _QWORD *a2, PSID *a3)
{
  __int64 v5; // r8
  WCHAR *v6; // rdx
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h]
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName[3]; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD *v13; // [rsp+60h] [rbp-A0h]
  LPWSTR *p_StringSid; // [rsp+70h] [rbp-90h]
  char v15; // [rsp+78h] [rbp-88h]
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+290h] [rbp+190h] BYREF

  v13 = a2;
  cchReferencedDomainName = 260;
  std::wstring::wstring(a2);
  std::wstring::wstring(a2 + 4);
  v9 = 1;
  peUse = 0;
  cchName[0] = 260;
  StringSid = 0;
  if ( LookupAccountSidW(0, *a3, Name, cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v5 = -1;
    do
      ++v5;
    while ( Name[v5] );
    v6 = Name;
  }
  else
  {
    v5 = 7;
    v6 = (WCHAR *)L"Unknown";
  }
  std::wstring::_Assign<unsigned short>(a2, v6, v5);
  if ( ConvertSidToStringSidW(*a3, &StringSid) )
  {
    p_StringSid = &StringSid;
    v15 = 1;
    std::wstring::assign(a2 + 4, StringSid);
    LocalFree(StringSid);
  }
  else
  {
    std::wstring::_Assign<unsigned short>(a2 + 4, L"Unknown", 7);
  }
  return a2;
}

```

## disassembly

```asm
0x180025278  mov     [rsp-8+arg_0], rbx
0x18002527d  mov     [rsp-8+arg_18], rsi
0x180025282  push    rbp
0x180025283  push    rdi
0x180025284  push    r15
0x180025286  lea     rbp, [rsp-3B0h]
0x18002528e  sub     rsp, 4B0h
0x180025295  mov     rax, cs:__security_cookie
0x18002529c  xor     rax, rsp
0x18002529f  mov     [rbp+3C0h+var_20], rax
0x1800252a6  mov     rsi, r8
0x1800252a9  mov     rbx, rdx
0x1800252ac  mov     [rsp+4C0h+var_460], rdx
0x1800252b1  xor     r15d, r15d
0x1800252b4  mov     [rsp+4C0h+var_478], r15d
0x1800252b9  mov     [rsp+4C0h+var_470], 104h
0x1800252c1  mov     rcx, rdx; void *
0x1800252c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800252c9  lea     rdi, [rbx+20h]
0x1800252cd  mov     rcx, rdi; void *
0x1800252d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800252d5  mov     [rsp+4C0h+var_478], 1
0x1800252dd  mov     [rsp+4C0h+var_474], r15d
0x1800252e2  mov     [rsp+4C0h+cchName], 104h
0x1800252ea  mov     [rsp+4C0h+StringSid], r15
0x1800252ef  lea     rax, [rsp+4C0h+var_474]
0x1800252f4  mov     [rsp+4C0h+peUse], rax; peUse
0x1800252f9  lea     rax, [rsp+4C0h+var_470]
0x1800252fe  mov     [rsp+4C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180025303  lea     rax, [rbp+3C0h+var_230]
0x18002530a  mov     [rsp+4C0h+ReferencedDomainName], rax; ReferencedDomainName
0x18002530f  lea     r9, [rsp+4C0h+cchName]; cchName
0x180025314  lea     r8, [rbp+3C0h+Name]; Name
0x180025318  mov     rdx, [rsi]; Sid
0x18002531b  xor     ecx, ecx; lpSystemName
0x18002531d  call    cs:__imp_LookupAccountSidW
0x180025323  test    eax, eax
0x180025325  jz      loc_1800253C4
0x18002532b  lea     rax, [rbp+3C0h+Name]
0x18002532f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180025333  inc     r8
0x180025336  cmp     [rax+r8*2], r15w
0x18002533b  jnz     short loc_180025333
0x18002533d  lea     rdx, [rbp+3C0h+Name]
0x180025341  mov     rcx, rbx
0x180025344  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180025349  lea     rdx, [rsp+4C0h+StringSid]; StringSid
0x18002534e  mov     rcx, [rsi]; Sid
0x180025351  call    cs:__imp_ConvertSidToStringSidW
0x180025357  test    eax, eax
0x180025359  jz      short loc_1800253AD
0x18002535b  lea     rax, [rsp+4C0h+StringSid]
0x180025360  mov     [rsp+4C0h+var_450], rax
0x180025365  mov     [rsp+4C0h+var_448], 1
0x18002536a  mov     rdx, [rsp+4C0h+StringSid]
0x18002536f  mov     rcx, rdi
0x180025372  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180025377  nop
0x180025378  mov     rcx, [rsp+4C0h+StringSid]; hMem
0x18002537d  call    cs:__imp_LocalFree
0x180025383  mov     rax, rbx
0x180025386  mov     rcx, [rbp+3C0h+var_20]
0x18002538d  xor     rcx, rsp; StackCookie
0x180025390  call    __security_check_cookie
0x180025395  lea     r11, [rsp+4C0h+var_10]
0x18002539d  mov     rbx, [r11+20h]
0x1800253a1  mov     rsi, [r11+38h]
0x1800253a5  mov     rsp, r11
0x1800253a8  pop     r15
0x1800253aa  pop     rdi
0x1800253ab  pop     rbp
0x1800253ac  retn
0x1800253ad  mov     r8d, 7
0x1800253b3  lea     rdx, aUnknown_1; "Unknown"
0x1800253ba  mov     rcx, rdi
0x1800253bd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800253c2  jmp     short loc_180025383
0x1800253c4  mov     r8d, 7
0x1800253ca  lea     rdx, aUnknown_1; "Unknown"
0x1800253d1  jmp     loc_180025341
```
