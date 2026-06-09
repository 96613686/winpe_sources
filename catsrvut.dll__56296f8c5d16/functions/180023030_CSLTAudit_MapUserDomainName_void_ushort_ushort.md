# CSLTAudit::MapUserDomainName(void *,ushort * *,ushort * *)

- ea: `0x180023030`
- end: `0x180023183`
- name: `?MapUserDomainName@CSLTAudit@@EEAAJPEAXPEAPEAG1@Z`
- size: `339`
- prototype: `int(CSLTAudit *__hidden this, void *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180023030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800230c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800230f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800230c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800230f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002313a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002313a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002307e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180023130`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002307e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180023130`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::MapUserDomainName(
        CSLTAudit *this,
        void *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  signed int v7; // ebx
  signed int LastError; // eax
  WCHAR *v9; // rsi
  WCHAR *v10; // rdi
  signed int v11; // eax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-48h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-44h] BYREF
  enum _SID_NAME_USE peUse[16]; // [rsp+38h] [rbp-40h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  v7 = 0;
  if ( LookupAccountSidLocalW(a2, 0, &cchName, 0, &cchReferencedDomainName, peUse) || GetLastError() == 122 )
    goto LABEL_6;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_6:
    v9 = (WCHAR *)CoTaskMemAlloc(saturated_mul(cchName, 2u));
    if ( v9 )
    {
      v10 = (WCHAR *)CoTaskMemAlloc(saturated_mul(cchReferencedDomainName, 2u));
      if ( v10 )
      {
        if ( !LookupAccountSidLocalW(a2, v9, &cchName, v10, &cchReferencedDomainName, peUse) )
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
        }
        if ( v7 >= 0 )
        {
          *a3 = v9;
          *a4 = v10;
          return (unsigned int)v7;
        }
      }
      else
      {
        v7 = -2147024882;
      }
      CoTaskMemFree(v9);
      if ( v10 )
        CoTaskMemFree(v10);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023030  mov     r11, rsp
0x180023033  push    rbx
0x180023034  push    rbp
0x180023035  push    rsi
0x180023036  push    rdi
0x180023037  push    r14
0x180023039  push    r15
0x18002303b  sub     rsp, 48h
0x18002303f  mov     r14, r9
0x180023042  mov     r15, r8
0x180023045  mov     rbp, rdx
0x180023048  mov     [rsp+78h+cchName], 0
0x180023050  mov     [rsp+78h+var_48], 0
0x180023058  mov     [rsp+78h+var_40], 0
0x180023060  xor     ebx, ebx
0x180023062  lea     rax, [r11-40h]
0x180023066  mov     [r11-50h], rax
0x18002306a  lea     rax, [r11-48h]
0x18002306e  mov     [r11-58h], rax
0x180023072  xor     r9d, r9d; ReferencedDomainName
0x180023075  lea     r8, [r11-44h]; cchName
0x180023079  xor     edx, edx; Name
0x18002307b  mov     rcx, rbp; Sid
0x18002307e  call    cs:__imp_LookupAccountSidLocalW
0x180023084  test    eax, eax
0x180023086  jnz     short loc_1800230B0
0x180023088  call    cs:__imp_GetLastError
0x18002308e  cmp     eax, 7Ah ; 'z'
0x180023091  jz      short loc_1800230B0
0x180023093  call    cs:__imp_GetLastError
0x180023099  mov     ebx, eax
0x18002309b  test    eax, eax
0x18002309d  jle     short loc_1800230A8
0x18002309f  movzx   ebx, ax
0x1800230a2  or      ebx, 80070000h
0x1800230a8  test    ebx, ebx
0x1800230aa  js      loc_180023174
0x1800230b0  mov     ecx, [rsp+78h+cchName]
0x1800230b4  mov     edi, 2
0x1800230b9  mov     eax, edi
0x1800230bb  mul     rcx
0x1800230be  lea     rcx, [rdi-3]
0x1800230c2  cmovb   rax, rcx
0x1800230c6  mov     rcx, rax; cb
0x1800230c9  call    cs:__imp_CoTaskMemAlloc
0x1800230cf  mov     rsi, rax
0x1800230d2  test    rax, rax
0x1800230d5  jnz     short loc_1800230E1
0x1800230d7  mov     ebx, 8007000Eh
0x1800230dc  jmp     loc_180023174
0x1800230e1  mov     ecx, [rsp+78h+var_48]
0x1800230e5  mov     rax, rdi
0x1800230e8  mul     rcx
0x1800230eb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800230f2  cmovb   rax, rcx
0x1800230f6  mov     rcx, rax; cb
0x1800230f9  call    cs:__imp_CoTaskMemAlloc
0x1800230ff  mov     rdi, rax
0x180023102  test    rax, rax
0x180023105  jnz     short loc_18002310E
0x180023107  mov     ebx, 8007000Eh
0x18002310c  jmp     short loc_180023153
0x18002310e  lea     rax, [rsp+78h+var_40]
0x180023113  mov     [rsp+78h+peUse], rax; peUse
0x180023118  lea     rax, [rsp+78h+var_48]
0x18002311d  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023122  mov     r9, rdi; ReferencedDomainName
0x180023125  lea     r8, [rsp+78h+cchName]; cchName
0x18002312a  mov     rdx, rsi; Name
0x18002312d  mov     rcx, rbp; Sid
0x180023130  call    cs:__imp_LookupAccountSidLocalW
0x180023136  test    eax, eax
0x180023138  jnz     short loc_18002314F
0x18002313a  call    cs:__imp_GetLastError
0x180023140  mov     ebx, eax
0x180023142  test    eax, eax
0x180023144  jle     short loc_18002314F
0x180023146  movzx   ebx, ax
0x180023149  or      ebx, 80070000h
0x18002314f  test    ebx, ebx
0x180023151  jns     short loc_18002316E
0x180023153  mov     rcx, rsi; pv
0x180023156  call    cs:__imp_CoTaskMemFree
0x18002315c  nop
0x18002315d  test    rdi, rdi
0x180023160  jz      short loc_180023174
0x180023162  mov     rcx, rdi; pv
0x180023165  call    cs:__imp_CoTaskMemFree
0x18002316b  nop
0x18002316c  jmp     short loc_180023174
0x18002316e  mov     [r15], rsi
0x180023171  mov     [r14], rdi
0x180023174  mov     eax, ebx
0x180023176  add     rsp, 48h
0x18002317a  pop     r15
0x18002317c  pop     r14
0x18002317e  pop     rdi
0x18002317f  pop     rsi
0x180023180  pop     rbp
0x180023181  pop     rbx
0x180023182  retn
```
