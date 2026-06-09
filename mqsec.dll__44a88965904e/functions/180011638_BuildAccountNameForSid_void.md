# _BuildAccountNameForSid(void *)

- ea: `0x180011638`
- end: `0x1800117b3`
- name: `?_BuildAccountNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAX@Z`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180011bd8`
- `0x180011dfc`

## callees

- `0x18000ee9c`
- `0x180011638`
- `0x1800129c0`
- `0x18001722c`

## import_xrefs

- `msvcrt!free` at `0x18001178f`
- `msvcrt!free` at `0x180011799`
- `msvcrt!free` at `0x18001178f`
- `msvcrt!free` at `0x180011799`
- `ADVAPI32!LookupAccountSidW` at `0x1800116ac`
- `ADVAPI32!LookupAccountSidW` at `0x18001173c`
- `ADVAPI32!LookupAccountSidW` at `0x1800116ac`
- `ADVAPI32!LookupAccountSidW` at `0x18001173c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _BuildAccountNameForSid(__int64 a1, void *a2)
{
  WCHAR *v4; // rbx
  WCHAR *ReferencedDomainName; // rdi
  __int64 v6; // r14
  __int64 v7; // r8
  enum _SID_NAME_USE peUse[2]; // [rsp+40h] [rbp-20h] BYREF
  DWORD v10; // [rsp+48h] [rbp-18h] BYREF
  DWORD v11; // [rsp+4Ch] [rbp-14h] BYREF
  WCHAR *v12; // [rsp+50h] [rbp-10h]
  WCHAR *v13; // [rsp+58h] [rbp-8h]
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+58h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  v4 = 0;
  v12 = 0;
  ReferencedDomainName = 0;
  v13 = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_QWORD *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 8) = 0;
  peUse[1] = SidTypeUser;
  v6 = -1;
  if ( LookupAccountSidW(0, a2, 0, &cchName, 0, &cchReferencedDomainName, peUse)
    || cchName
    && cchReferencedDomainName
    && (v4 = (WCHAR *)MmAllocate(saturated_mul(cchName, 2u)),
        v12 = v4,
        ReferencedDomainName = (WCHAR *)MmAllocate(saturated_mul(cchReferencedDomainName, 2u)),
        v13 = ReferencedDomainName,
        v11 = cchName,
        v10 = cchReferencedDomainName,
        LookupAccountSidW(0, a2, v4, &v11, ReferencedDomainName, &v10, peUse)) )
  {
    v7 = -1;
    do
      ++v7;
    while ( ReferencedDomainName[v7] );
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
      a1,
      ReferencedDomainName,
      v7);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(a1, L"\\", 1);
    do
      ++v6;
    while ( v4[v6] );
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(a1, v4, v6);
  }
  free(ReferencedDomainName);
  free(v4);
  return a1;
}

```

## disassembly

```asm
0x180011638  mov     r11, rsp
0x18001163b  mov     [r11+8], rcx
0x18001163f  push    rbp
0x180011640  push    rbx
0x180011641  push    rsi
0x180011642  push    rdi
0x180011643  push    r12
0x180011645  push    r14
0x180011647  push    r15
0x180011649  mov     rbp, rsp
0x18001164c  sub     rsp, 60h
0x180011650  mov     r15, rdx
0x180011653  mov     rsi, rcx
0x180011656  xor     r12d, r12d
0x180011659  mov     [rbp+var_1C], r12d
0x18001165d  mov     [rbp+cchName], r12d
0x180011661  mov     [rbp+arg_10], r12d
0x180011665  mov     [rbp+var_20], r12d
0x180011669  mov     ebx, r12d
0x18001166c  mov     [rbp+var_10], rbx
0x180011670  mov     edi, r12d
0x180011673  mov     [rbp+var_8], r12
0x180011677  mov     qword ptr [rcx+20h], 7
0x18001167f  mov     [rcx+18h], r12
0x180011683  mov     [rcx+8], r12w
0x180011688  mov     [rbp+var_1C], 1
0x18001168f  lea     rax, [rbp+var_20]
0x180011693  mov     [r11-68h], rax
0x180011697  lea     rax, [rbp+arg_10]
0x18001169b  mov     [r11-70h], rax
0x18001169f  mov     [r11-78h], r12
0x1800116a3  lea     r9, [rbp+cchName]; cchName
0x1800116a7  xor     r8d, r8d; Name
0x1800116aa  xor     ecx, ecx; lpSystemName
0x1800116ac  call    cs:__imp_LookupAccountSidW
0x1800116b2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800116b6  test    eax, eax
0x1800116b8  jnz     loc_180011746
0x1800116be  mov     eax, [rbp+cchName]
0x1800116c1  test    eax, eax
0x1800116c3  jz      loc_18001178C
0x1800116c9  cmp     [rbp+arg_10], r12d
0x1800116cd  jz      loc_18001178C
0x1800116d3  mov     ecx, eax
0x1800116d5  lea     edi, [r12+2]
0x1800116da  mov     eax, edi
0x1800116dc  mul     rcx
0x1800116df  cmovb   rax, r14
0x1800116e3  mov     rcx, rax; unsigned __int64
0x1800116e6  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800116eb  mov     rbx, rax
0x1800116ee  mov     [rbp+var_10], rax
0x1800116f2  mov     ecx, [rbp+arg_10]
0x1800116f5  mov     eax, edi
0x1800116f7  mul     rcx
0x1800116fa  cmovb   rax, r14
0x1800116fe  mov     rcx, rax; unsigned __int64
0x180011701  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011706  mov     rdi, rax
0x180011709  mov     [rbp+var_8], rax
0x18001170d  mov     ecx, [rbp+cchName]
0x180011710  mov     [rbp+var_14], ecx
0x180011713  mov     ecx, [rbp+arg_10]
0x180011716  mov     [rbp+var_18], ecx
0x180011719  lea     rax, [rbp+var_20]
0x18001171d  mov     [rsp+60h+peUse], rax; peUse
0x180011722  lea     rax, [rbp+var_18]
0x180011726  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001172b  mov     [rsp+60h+ReferencedDomainName], rdi; ReferencedDomainName
0x180011730  lea     r9, [rbp+var_14]; cchName
0x180011734  mov     r8, rbx; Name
0x180011737  mov     rdx, r15; Sid
0x18001173a  xor     ecx, ecx; lpSystemName
0x18001173c  call    cs:__imp_LookupAccountSidW
0x180011742  test    eax, eax
0x180011744  jz      short loc_18001178C
0x180011746  mov     r8, r14
0x180011749  inc     r8
0x18001174c  cmp     [rdi+r8*2], r12w
0x180011751  jnz     short loc_180011749
0x180011753  mov     rdx, rdi
0x180011756  mov     rcx, rsi
0x180011759  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(wchar_t const *,unsigned __int64)
0x18001175e  mov     r8d, 1
0x180011764  lea     rdx, asc_180034060; "\\"
0x18001176b  mov     rcx, rsi
0x18001176e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(wchar_t const *,unsigned __int64)
0x180011773  inc     r14
0x180011776  cmp     [rbx+r14*2], r12w
0x18001177b  jnz     short loc_180011773
0x18001177d  mov     r8, r14
0x180011780  mov     rdx, rbx
0x180011783  mov     rcx, rsi
0x180011786  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(wchar_t const *,unsigned __int64)
0x18001178b  nop
0x18001178c  mov     rcx, rdi; Block
0x18001178f  call    cs:__imp_free
0x180011795  nop
0x180011796  mov     rcx, rbx; Block
0x180011799  call    cs:__imp_free
0x18001179f  nop
0x1800117a0  mov     rax, rsi
0x1800117a3  add     rsp, 60h
0x1800117a7  pop     r15
0x1800117a9  pop     r14
0x1800117ab  pop     r12
0x1800117ad  pop     rdi
0x1800117ae  pop     rsi
0x1800117af  pop     rbx
0x1800117b0  pop     rbp
0x1800117b1  retn
```
