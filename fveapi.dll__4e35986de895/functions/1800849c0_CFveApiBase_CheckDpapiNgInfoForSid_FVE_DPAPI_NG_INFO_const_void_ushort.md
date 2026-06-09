# CFveApiBase::CheckDpapiNgInfoForSid(_FVE_DPAPI_NG_INFO const *,void *,ushort * *)

- ea: `0x1800849c0`
- end: `0x180084ce7`
- name: `?CheckDpapiNgInfoForSid@CFveApiBase@@MEBAJPEBU_FVE_DPAPI_NG_INFO@@PEAXPEAPEAG@Z`
- size: `807`
- prototype: `__int64 __fastcall(CFveApiBase *this, const struct _FVE_DPAPI_NG_INFO *, void *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005410`
- `0x180009d00`
- `0x18000ba30`
- `0x180037f50`
- `0x18008354c`
- `0x1800849c0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084c6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124191`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084c6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124191`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084c5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012417d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084c5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012417d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b88`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084bab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084bdc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b88`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084bab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084bdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801241a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801241a7`
- `ncrypt!NCryptUnprotectSecret` at `0x180084a65`
- `ncrypt!NCryptUnprotectSecret` at `0x180084a65`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180084c9a`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1801241bd`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180084c9a`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1801241bd`
- `ext-ms-win-feclient-encryptedfile-l1-1-3!DpQueryUserProtectorDescriptorInfo` at `0x180084b51`
- `ext-ms-win-feclient-encryptedfile-l1-1-3!DpQueryUserProtectorDescriptorInfo` at `0x180084b51`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084a95`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084a95`

## pseudocode

```c
__int64 __fastcall CFveApiBase::CheckDpapiNgInfoForSid(
        CFveApiBase *this,
        const struct _FVE_DPAPI_NG_INFO *a2,
        void *a3,
        unsigned __int16 **a4)
{
  int LastHresultError; // ebx
  __int64 v8; // r14
  unsigned int i; // edi
  bool v10; // zf
  __int64 v11; // rax
  __int64 v12; // rsi
  const WCHAR **v13; // rsi
  const WCHAR *v14; // rcx
  const unsigned __int16 *v15; // rcx
  WCHAR *v16; // rdi
  HANDLE ProcessHeap; // rax
  void *lpMem; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-68h]
  LPCWCH lpString1; // [rsp+58h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp-50h] BYREF
  __int64 v24; // [rsp+70h] [rbp-48h] BYREF
  void *v25; // [rsp+78h] [rbp-40h]
  unsigned __int64 v26; // [rsp+80h] [rbp-38h]

  v24 = 0;
  lpMem = 0;
  v23 = 0;
  lpString1 = 0;
  StringSid = 0;
  v25 = 0;
  LODWORD(v26) = 0;
  LastHresultError = NCryptUnprotectSecret(&v24, 1, (char *)a2 + 8);
  if ( LastHresultError >= 0 )
  {
    v8 = *(_QWORD *)(v24 + 8);
    if ( !a3 || ConvertSidToStringSidW(a3, &StringSid) )
    {
      for ( i = 0; ; ++i )
      {
        v20 = i;
        v10 = i == *(_DWORD *)v8;
        if ( i >= *(_DWORD *)v8 )
          break;
        v11 = 32LL * i;
        v12 = *(_QWORD *)(v8 + 8);
        if ( *(_DWORD *)(v11 + v12) == 1 )
        {
          v13 = *(const WCHAR ***)(v11 + v12 + 8);
          v14 = *v13;
          if ( (*((_BYTE *)a2 + 6) & 2) != 0 )
          {
            if ( CompareStringOrdinal(v14, -1, L"LOCKEDCREDENTIALS", -1, 1) == 2 )
            {
              LastHresultError = CFveApiBase::ConcatAllocString(&v23, *v13, L"=", v13[1], 0);
              if ( LastHresultError < 0 )
                goto LABEL_27;
              LastHresultError = DpQueryUserProtectorDescriptorInfo(v23, 0, 0, &lpString1);
              if ( LastHresultError < 0 )
                goto LABEL_27;
              if ( !StringSid || CompareStringOrdinal(lpString1, -1, StringSid, -1, 1) == 2 )
              {
                v15 = lpString1;
LABEL_21:
                LastHresultError = CFveApiBase::CopyString(v15, (unsigned __int16 **)&lpMem);
                if ( LastHresultError < 0 )
                  goto LABEL_27;
                v10 = i == *(_DWORD *)v8;
                break;
              }
            }
          }
          else if ( CompareStringOrdinal(v14, -1, L"SID", -1, 1) == 2
                 && (!StringSid || CompareStringOrdinal(v13[1], -1, StringSid, -1, 1) == 2) )
          {
            v15 = v13[1];
            goto LABEL_21;
          }
        }
      }
      if ( v10 )
      {
        LastHresultError = -2144272333;
      }
      else if ( a4 )
      {
        *a4 = (unsigned __int16 *)lpMem;
        lpMem = 0;
      }
    }
    else
    {
      LastHresultError = GetLastHresultError();
    }
  }
LABEL_27:
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v23 )
    CFveApiBase::FastFree(v23);
  v16 = (WCHAR *)lpString1;
  if ( lpString1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( v24 )
    NCryptCloseProtectionDescriptor();
  if ( v25 )
    CFveApiBase::ZeroFree(v25, (unsigned int)v26);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x1800849c0  mov     r11, rsp
0x1800849c3  mov     [r11+8], rbx
0x1800849c7  push    rsi
0x1800849c8  push    rdi
0x1800849c9  push    r13
0x1800849cb  push    r14
0x1800849cd  push    r15
0x1800849cf  sub     rsp, 90h
0x1800849d6  mov     rax, cs:__security_cookie
0x1800849dd  xor     rax, rsp
0x1800849e0  mov     [rsp+0B8h+var_30], rax
0x1800849e8  mov     r15, r9
0x1800849eb  mov     rdi, r8
0x1800849ee  mov     r13, rdx
0x1800849f1  mov     qword ptr [r11-48h], 0
0x1800849f9  mov     qword ptr [r11-70h], 0
0x180084a01  mov     qword ptr [r11-50h], 0
0x180084a09  mov     qword ptr [r11-60h], 0
0x180084a11  mov     qword ptr [r11-58h], 0
0x180084a19  lea     r8, [rdx+8]
0x180084a1d  movzx   r9d, word ptr [rdx+4]
0x180084a22  sub     r9d, 8
0x180084a26  mov     qword ptr [r11-40h], 0
0x180084a2e  mov     dword ptr [r11-38h], 0
0x180084a36  lea     rax, [r11-38h]
0x180084a3a  mov     [r11-80h], rax
0x180084a3e  lea     rax, [r11-40h]
0x180084a42  mov     [rsp+0B8h+var_88], rax
0x180084a47  mov     [rsp+0B8h+var_90], 0
0x180084a50  lea     rax, qword_18012C7E0
0x180084a57  mov     qword ptr [rsp+0B8h+bIgnoreCase], rax
0x180084a5c  mov     edx, 1
0x180084a61  lea     rcx, [r11-48h]
0x180084a65  call    cs:__imp_NCryptUnprotectSecret
0x180084a6c  nop     dword ptr [rax+rax+00h]
0x180084a71  mov     ebx, eax
0x180084a73  mov     [rsp+0B8h+var_78], eax
0x180084a77  test    eax, eax
0x180084a79  js      loc_180084C32
0x180084a7f  mov     rdx, [rsp+0B8h+var_48]
0x180084a84  mov     r14, [rdx+8]
0x180084a88  test    rdi, rdi
0x180084a8b  jz      short loc_180084AB5
0x180084a8d  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x180084a92  mov     rcx, rdi; Sid
0x180084a95  call    cs:__imp_ConvertSidToStringSidW
0x180084a9c  nop     dword ptr [rax+rax+00h]
0x180084aa1  test    eax, eax
0x180084aa3  jnz     short loc_180084AB5
0x180084aa5  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180084aaa  mov     ebx, eax
0x180084aac  mov     [rsp+0B8h+var_78], eax
0x180084ab0  jmp     loc_180084C32
0x180084ab5  xor     edi, edi
0x180084ab7  mov     [rsp+0B8h+var_68], edi
0x180084abb  cmp     edi, [r14]
0x180084abe  jnb     loc_180084C0F
0x180084ac4  mov     eax, edi
0x180084ac6  shl     rax, 5
0x180084aca  mov     rsi, [r14+8]
0x180084ace  mov     ecx, 1
0x180084ad3  cmp     [rax+rsi], ecx
0x180084ad6  jz      short loc_180084ADD
0x180084ad8  jmp     loc_180084BED
0x180084add  mov     rsi, [rax+rsi+8]
0x180084ae2  mov     [rsp+0B8h+bIgnoreCase], ecx; bIgnoreCase
0x180084ae6  or      r9d, 0FFFFFFFFh; cchCount2
0x180084aea  or      edx, r9d; cchCount1
0x180084aed  mov     rcx, [rsi]; lpString1
0x180084af0  test    byte ptr [r13+6], 2
0x180084af5  jz      loc_180084BA4
0x180084afb  lea     r8, aLockedcredenti; "LOCKEDCREDENTIALS"
0x180084b02  call    cs:__imp_CompareStringOrdinal
0x180084b09  nop     dword ptr [rax+rax+00h]
0x180084b0e  cmp     eax, 2
0x180084b11  jnz     short loc_180084AD8
0x180084b13  mov     qword ptr [rsp+0B8h+bIgnoreCase], 0
0x180084b1c  mov     r9, [rsi+8]
0x180084b20  lea     r8, asc_18013BB34; "="
0x180084b27  mov     rdx, [rsi]
0x180084b2a  lea     rcx, [rsp+0B8h+var_50]; unsigned __int16 **
0x180084b2f  call    ?ConcatAllocString@CFveApiBase@@SAJPEAPEAGZZ; CFveApiBase::ConcatAllocString(ushort * *,...)
0x180084b34  mov     ebx, eax
0x180084b36  mov     [rsp+0B8h+var_78], eax
0x180084b3a  test    eax, eax
0x180084b3c  js      loc_180084C32
0x180084b42  lea     r9, [rsp+0B8h+lpString1]
0x180084b47  xor     r8d, r8d
0x180084b4a  xor     edx, edx
0x180084b4c  mov     rcx, [rsp+0B8h+var_50]
0x180084b51  call    cs:__imp_DpQueryUserProtectorDescriptorInfo
0x180084b58  nop     dword ptr [rax+rax+00h]
0x180084b5d  mov     ebx, eax
0x180084b5f  mov     [rsp+0B8h+var_78], eax
0x180084b63  test    eax, eax
0x180084b65  js      loc_180084C32
0x180084b6b  mov     r8, [rsp+0B8h+StringSid]; lpString2
0x180084b70  test    r8, r8
0x180084b73  jz      short loc_180084B9D
0x180084b75  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x180084b7d  or      edx, 0FFFFFFFFh; cchCount1
0x180084b80  mov     r9d, edx; cchCount2
0x180084b83  mov     rcx, [rsp+0B8h+lpString1]; lpString1
0x180084b88  call    cs:__imp_CompareStringOrdinal
0x180084b8f  nop     dword ptr [rax+rax+00h]
0x180084b94  cmp     eax, 2
0x180084b97  jnz     loc_180084AD8
0x180084b9d  mov     rcx, [rsp+0B8h+lpString1]
0x180084ba2  jmp     short loc_180084BF8
0x180084ba4  lea     r8, aSid; "SID"
0x180084bab  call    cs:__imp_CompareStringOrdinal
0x180084bb2  nop     dword ptr [rax+rax+00h]
0x180084bb7  cmp     eax, 2
0x180084bba  jnz     loc_180084AD8
0x180084bc0  mov     r8, [rsp+0B8h+StringSid]; lpString2
0x180084bc5  test    r8, r8
0x180084bc8  jz      short loc_180084BF4
0x180084bca  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x180084bd2  or      edx, 0FFFFFFFFh; cchCount1
0x180084bd5  mov     r9d, edx; cchCount2
0x180084bd8  mov     rcx, [rsi+8]; lpString1
0x180084bdc  call    cs:__imp_CompareStringOrdinal
0x180084be3  nop     dword ptr [rax+rax+00h]
0x180084be8  cmp     eax, 2
0x180084beb  jz      short loc_180084BF4
0x180084bed  inc     edi
0x180084bef  jmp     loc_180084AB7
0x180084bf4  mov     rcx, [rsi+8]; unsigned __int16 *
0x180084bf8  lea     rdx, [rsp+0B8h+lpMem]; unsigned __int16 **
0x180084bfd  call    ?CopyString@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::CopyString(ushort const *,ushort * *)
0x180084c02  test    eax, eax
0x180084c04  mov     [rsp+0B8h+var_78], eax
0x180084c08  mov     ebx, eax
0x180084c0a  js      short loc_180084C32
0x180084c0c  cmp     edi, [r14]
0x180084c0f  jnz     short loc_180084C1C
0x180084c11  mov     ebx, 80310033h
0x180084c16  mov     [rsp+0B8h+var_78], ebx
0x180084c1a  jmp     short loc_180084C32
0x180084c1c  test    r15, r15
0x180084c1f  jz      short loc_180084C32
0x180084c21  mov     rax, [rsp+0B8h+lpMem]
0x180084c26  mov     [r15], rax
0x180084c29  mov     [rsp+0B8h+lpMem], 0
0x180084c32  mov     rcx, [rsp+0B8h+lpMem]; lpMem
0x180084c37  test    rcx, rcx
0x180084c3a  jz      short loc_180084C41
0x180084c3c  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180084c41  mov     rcx, [rsp+0B8h+var_50]; lpMem
0x180084c46  test    rcx, rcx
0x180084c49  jz      short loc_180084C50
0x180084c4b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180084c50  mov     rdi, [rsp+0B8h+lpString1]
0x180084c55  test    rdi, rdi
0x180084c58  jz      short loc_180084C7A
0x180084c5a  call    cs:__imp_GetProcessHeap
0x180084c61  nop     dword ptr [rax+rax+00h]
0x180084c66  mov     r8, rdi; lpMem
0x180084c69  xor     edx, edx; dwFlags
0x180084c6b  mov     rcx, rax; hHeap
0x180084c6e  call    cs:__imp_HeapFree
0x180084c75  nop     dword ptr [rax+rax+00h]
0x180084c7a  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x180084c7f  test    rcx, rcx
0x180084c82  jz      short loc_180084C90
0x180084c84  call    cs:__imp_LocalFree
0x180084c8b  nop     dword ptr [rax+rax+00h]
0x180084c90  mov     rcx, [rsp+0B8h+var_48]
0x180084c95  test    rcx, rcx
0x180084c98  jz      short loc_180084CA6
0x180084c9a  call    cs:__imp_NCryptCloseProtectionDescriptor
0x180084ca1  nop     dword ptr [rax+rax+00h]
0x180084ca6  mov     rcx, [rsp+0B8h+var_40]; lpMem
0x180084cab  test    rcx, rcx
0x180084cae  jz      short loc_180084CBC
0x180084cb0  mov     edx, dword ptr [rsp+0B8h+var_38]; unsigned __int64
0x180084cb7  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180084cbc  mov     eax, ebx
0x180084cbe  mov     rcx, [rsp+0B8h+var_30]
0x180084cc6  xor     rcx, rsp; StackCookie
0x180084cc9  call    __security_check_cookie
0x180084cce  mov     rbx, [rsp+0B8h+arg_0]
0x180084cd6  add     rsp, 90h
0x180084cdd  pop     r15
0x180084cdf  pop     r14
0x180084ce1  pop     r13
0x180084ce3  pop     rdi
0x180084ce4  pop     rsi
0x180084ce5  retn
0x18012414c  push    rbx
0x18012414e  push    rbp
0x18012414f  sub     rsp, 48h
0x180124153  mov     rbp, rdx
0x180124156  mov     rcx, [rbp+48h]; lpMem
0x18012415a  test    rcx, rcx
0x18012415d  jz      short loc_180124165
0x18012415f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180124164  nop
0x180124165  mov     rcx, [rbp+68h]; lpMem
0x180124169  test    rcx, rcx
0x18012416c  jz      short loc_180124174
0x18012416e  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180124173  nop
0x180124174  mov     rbx, [rbp+58h]
0x180124178  test    rbx, rbx
0x18012417b  jz      short loc_18012419E
0x18012417d  call    cs:__imp_GetProcessHeap
0x180124184  nop     dword ptr [rax+rax+00h]
0x180124189  mov     r8, rbx; lpMem
0x18012418c  xor     edx, edx; dwFlags
0x18012418e  mov     rcx, rax; hHeap
0x180124191  call    cs:__imp_HeapFree
0x180124198  nop     dword ptr [rax+rax+00h]
0x18012419d  nop
0x18012419e  mov     rcx, [rbp+60h]; hMem
0x1801241a2  test    rcx, rcx
0x1801241a5  jz      short loc_1801241B4
0x1801241a7  call    cs:__imp_LocalFree
0x1801241ae  nop     dword ptr [rax+rax+00h]
0x1801241b3  nop
0x1801241b4  mov     rcx, [rbp+70h]
0x1801241b8  test    rcx, rcx
0x1801241bb  jz      short loc_1801241CA
0x1801241bd  call    cs:__imp_NCryptCloseProtectionDescriptor
0x1801241c4  nop     dword ptr [rax+rax+00h]
0x1801241c9  nop
0x1801241ca  mov     rcx, [rbp+78h]; lpMem
0x1801241ce  test    rcx, rcx
0x1801241d1  jz      short loc_1801241DF
0x1801241d3  mov     edx, [rbp+80h]; unsigned __int64
0x1801241d9  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1801241de  nop
0x1801241df  add     rsp, 48h
0x1801241e3  pop     rbp
0x1801241e4  pop     rbx
0x1801241e5  retn
```
