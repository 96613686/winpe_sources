# CUstUser::_GetUserDomain(void *,ushort * *)

- ea: `0x18001cc24`
- end: `0x18001cda9`
- name: `?_GetUserDomain@CUstUser@@KAJPEAXPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001cdb0`

## callees

- `0x18000a8f0`
- `0x18000baec`
- `0x18001afc8`
- `0x18001cc24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd4e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001cc6e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ccf4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001cc6e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ccf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUstUser::_GetUserDomain(PSID Sid, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // rax
  unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  WCHAR *v9; // rsi
  signed int v10; // eax
  signed int LastError; // eax
  enum _SID_NAME_USE peUse[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+20h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  if ( LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse) || GetLastError() != 122 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v4);
    }
  }
  else
  {
    v4 = 0;
    v5 = 2LL * cchReferencedDomainName;
    if ( !is_mul_ok(cchReferencedDomainName, 2u) )
      v5 = -1;
    v6 = (unsigned __int16 *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
    v7 = cchName;
    *a2 = v6;
    v8 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    if ( !LookupAccountSidLocalW(Sid, v9, &cchName, *a2, &cchReferencedDomainName, peUse) )
    {
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v4);
      }
    }
    operator delete(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x18001cc24  mov     r11, rsp
0x18001cc27  mov     [r11+8], rbx
0x18001cc2b  mov     [r11+10h], rbp
0x18001cc2f  push    rsi
0x18001cc30  push    rdi
0x18001cc31  push    r14
0x18001cc33  sub     rsp, 40h
0x18001cc37  lea     rax, [r11-28h]
0x18001cc3b  mov     [rsp+58h+cchName], 0
0x18001cc43  mov     [r11-30h], rax
0x18001cc47  lea     r8, [r11+20h]; cchName
0x18001cc4b  lea     rax, [r11+18h]
0x18001cc4f  mov     [rsp+58h+arg_10], 0
0x18001cc57  mov     r14, rdx
0x18001cc5a  mov     [r11-38h], rax
0x18001cc5e  xor     r9d, r9d; ReferencedDomainName
0x18001cc61  mov     [rsp+58h+var_28], 0
0x18001cc69  xor     edx, edx; Name
0x18001cc6b  mov     rdi, rcx
0x18001cc6e  call    cs:__imp_LookupAccountSidLocalW
0x18001cc74  test    eax, eax
0x18001cc76  jnz     loc_18001CD4E
0x18001cc7c  call    cs:__imp_GetLastError
0x18001cc82  cmp     eax, 7Ah ; 'z'
0x18001cc85  jnz     loc_18001CD4E
0x18001cc8b  mov     ecx, [rsp+58h+arg_10]
0x18001cc8f  lea     esi, [rax-78h]
0x18001cc92  xor     ebx, ebx
0x18001cc94  mov     eax, esi
0x18001cc96  mul     rcx
0x18001cc99  lea     rbp, [rbx-1]
0x18001cc9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cca4  cmovb   rax, rbp
0x18001cca8  mov     rcx, rax; unsigned __int64
0x18001ccab  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ccb0  mov     ecx, [rsp+58h+cchName]
0x18001ccb4  mov     [r14], rax
0x18001ccb7  mov     eax, esi
0x18001ccb9  mul     rcx
0x18001ccbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ccc3  cmovb   rax, rbp
0x18001ccc7  mov     rcx, rax; unsigned __int64
0x18001ccca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001cccf  mov     r9, [r14]; ReferencedDomainName
0x18001ccd2  lea     r8, [rsp+58h+cchName]; cchName
0x18001ccd7  mov     rsi, rax
0x18001ccda  mov     rcx, rdi; Sid
0x18001ccdd  lea     rax, [rsp+58h+var_28]
0x18001cce2  mov     rdx, rsi; Name
0x18001cce5  mov     [rsp+58h+peUse], rax; peUse
0x18001ccea  lea     rax, [rsp+58h+arg_10]
0x18001ccef  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001ccf4  call    cs:__imp_LookupAccountSidLocalW
0x18001ccfa  test    eax, eax
0x18001ccfc  jnz     short loc_18001CD44
0x18001ccfe  call    cs:__imp_GetLastError
0x18001cd04  mov     ebx, eax
0x18001cd06  test    eax, eax
0x18001cd08  jle     short loc_18001CD13
0x18001cd0a  movzx   ebx, ax
0x18001cd0d  or      ebx, 80070000h
0x18001cd13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd1a  lea     rax, WPP_GLOBAL_Control
0x18001cd21  cmp     rcx, rax
0x18001cd24  jz      short loc_18001CD44
0x18001cd26  test    byte ptr [rcx+1Ch], 1
0x18001cd2a  jz      short loc_18001CD44
0x18001cd2c  mov     rcx, [rcx+10h]
0x18001cd30  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cd37  mov     edx, 0Ah
0x18001cd3c  mov     r9d, ebx
0x18001cd3f  call    WPP_SF_d
0x18001cd44  mov     rcx, rsi; void *
0x18001cd47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cd4c  jmp     short loc_18001CD94
0x18001cd4e  call    cs:__imp_GetLastError
0x18001cd54  mov     ebx, eax
0x18001cd56  test    eax, eax
0x18001cd58  jle     short loc_18001CD63
0x18001cd5a  movzx   ebx, ax
0x18001cd5d  or      ebx, 80070000h
0x18001cd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd6a  lea     rax, WPP_GLOBAL_Control
0x18001cd71  cmp     rcx, rax
0x18001cd74  jz      short loc_18001CD94
0x18001cd76  test    byte ptr [rcx+1Ch], 1
0x18001cd7a  jz      short loc_18001CD94
0x18001cd7c  mov     rcx, [rcx+10h]
0x18001cd80  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cd87  mov     edx, 0Bh
0x18001cd8c  mov     r9d, ebx
0x18001cd8f  call    WPP_SF_d
0x18001cd94  mov     rbp, [rsp+58h+arg_8]
0x18001cd99  mov     eax, ebx
0x18001cd9b  mov     rbx, [rsp+58h+arg_0]
0x18001cda0  add     rsp, 40h
0x18001cda4  pop     r14
0x18001cda6  pop     rdi
0x18001cda7  pop     rsi
0x18001cda8  retn
```
