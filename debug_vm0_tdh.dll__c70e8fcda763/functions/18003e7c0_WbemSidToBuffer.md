# WbemSidToBuffer

- ea: `0x18003e7c0`
- end: `0x18003e8ef`
- name: `WbemSidToBuffer`
- size: `303`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000dcb0`

## callees

- `0x18000e7c0`
- `0x18000ed38`
- `0x1800207c0`
- `0x18003e7c0`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003e82a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003e82a`

## pseudocode

```c
__int64 __fastcall WbemSidToBuffer(void *Src, unsigned __int16 a2, EmdStringBuffer *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // ecx
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchName; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t ReferencedDomainName[256]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Name[256]; // [rsp+240h] [rbp+140h] BYREF

  cchName = 256;
  cchReferencedDomainName = 256;
  peUse = 0;
  if ( !LookupAccountSidLocalW(Src, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    return SidToBuffer(Src, a2, (__int64)a3);
  EmdStringBuffer::AppendWide(a3, L"\\\\", 2u);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( ReferencedDomainName[v7] );
  EmdStringBuffer::AppendWide(a3, ReferencedDomainName, v7);
  v8 = *((unsigned int *)a3 + 3);
  *((_DWORD *)a3 + 3) = v8 + 1;
  if ( (unsigned int)(v8 + 1) <= *((_DWORD *)a3 + 2) )
    *(_WORD *)(*(_QWORD *)a3 + 2 * v8) = 92;
  do
    ++v6;
  while ( Name[v6] );
  EmdStringBuffer::AppendWide(a3, Name, v6);
  v9 = *((_DWORD *)a3 + 3);
  *((_DWORD *)a3 + 3) = v9 + 1;
  if ( v9 + 1 <= *((_DWORD *)a3 + 2) )
    *(_WORD *)(*(_QWORD *)a3 + 2LL * v9) = 0;
  return 0;
}

```

## disassembly

```asm
0x18003e7c0  push    rbp
0x18003e7c2  push    rbx
0x18003e7c3  push    rsi
0x18003e7c4  push    rdi
0x18003e7c5  push    r14
0x18003e7c7  lea     rbp, [rsp-350h]
0x18003e7cf  sub     rsp, 450h
0x18003e7d6  mov     rax, cs:__security_cookie
0x18003e7dd  xor     rax, rsp
0x18003e7e0  mov     [rbp+370h+var_30], rax
0x18003e7e7  mov     eax, 100h
0x18003e7ec  lea     r9, [rsp+470h+ReferencedDomainName]; ReferencedDomainName
0x18003e7f1  mov     [rsp+470h+cchName], eax
0x18003e7f5  mov     rbx, r8
0x18003e7f8  mov     [rsp+470h+var_43C], eax
0x18003e7fc  lea     r8, [rsp+470h+cchName]; cchName
0x18003e801  lea     rax, [rsp+470h+var_440]
0x18003e806  movzx   esi, dx
0x18003e809  mov     [rsp+470h+peUse], rax; peUse
0x18003e80e  lea     rdx, [rbp+370h+Name]; Name
0x18003e815  lea     rax, [rsp+470h+var_43C]
0x18003e81a  xor     r14d, r14d
0x18003e81d  mov     [rsp+470h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003e822  mov     rdi, rcx
0x18003e825  mov     [rsp+470h+var_440], r14d
0x18003e82a  call    cs:__imp_LookupAccountSidLocalW
0x18003e830  test    eax, eax
0x18003e832  jz      loc_18003E8C4
0x18003e838  lea     r8d, [r14+2]; unsigned int
0x18003e83c  mov     rcx, rbx; this
0x18003e83f  lea     rdx, asc_18005B764; "\\\\"
0x18003e846  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18003e84b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e84f  lea     rax, [rsp+470h+ReferencedDomainName]
0x18003e854  mov     r8, rdi
0x18003e857  inc     r8; unsigned int
0x18003e85a  cmp     [rax+r8*2], r14w
0x18003e85f  jnz     short loc_18003E857
0x18003e861  lea     rdx, [rsp+470h+ReferencedDomainName]; wchar_t *
0x18003e866  mov     rcx, rbx; this
0x18003e869  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18003e86e  mov     ecx, [rbx+0Ch]
0x18003e871  lea     eax, [rcx+1]
0x18003e874  mov     [rbx+0Ch], eax
0x18003e877  cmp     eax, [rbx+8]
0x18003e87a  ja      short loc_18003E885
0x18003e87c  mov     rax, [rbx]
0x18003e87f  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18003e885  lea     rax, [rbp+370h+Name]
0x18003e88c  inc     rdi
0x18003e88f  cmp     [rax+rdi*2], r14w
0x18003e894  jnz     short loc_18003E88C
0x18003e896  mov     r8d, edi; unsigned int
0x18003e899  lea     rdx, [rbp+370h+Name]; wchar_t *
0x18003e8a0  mov     rcx, rbx; this
0x18003e8a3  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18003e8a8  mov     ecx, [rbx+0Ch]
0x18003e8ab  lea     eax, [rcx+1]
0x18003e8ae  mov     [rbx+0Ch], eax
0x18003e8b1  cmp     eax, [rbx+8]
0x18003e8b4  ja      short loc_18003E8C0
0x18003e8b6  mov     edx, ecx
0x18003e8b8  mov     rcx, [rbx]
0x18003e8bb  mov     [rcx+rdx*2], r14w
0x18003e8c0  xor     eax, eax
0x18003e8c2  jmp     short loc_18003E8D2
0x18003e8c4  mov     r8, rbx
0x18003e8c7  movzx   edx, si
0x18003e8ca  mov     rcx, rdi; Src
0x18003e8cd  call    SidToBuffer
0x18003e8d2  mov     rcx, [rbp+370h+var_30]
0x18003e8d9  xor     rcx, rsp; StackCookie
0x18003e8dc  call    __security_check_cookie
0x18003e8e1  add     rsp, 450h
0x18003e8e8  pop     r14
0x18003e8ea  pop     rdi
0x18003e8eb  pop     rsi
0x18003e8ec  pop     rbx
0x18003e8ed  pop     rbp
0x18003e8ee  retn
```
