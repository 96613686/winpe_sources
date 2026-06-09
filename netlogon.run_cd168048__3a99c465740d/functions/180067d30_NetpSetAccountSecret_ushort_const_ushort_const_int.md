# NetpSetAccountSecret(ushort const *,ushort const *,int)

- ea: `0x180067d30`
- end: `0x180067fa3`
- name: `?NetpSetAccountSecret@@YAJPEBG0H@Z`
- size: `627`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180065520`

## callees

- `0x18000e910`
- `0x180065bec`
- `0x180066480`
- `0x180067d30`

## import_xrefs

- `LSASRV!LsarClose` at `0x180067f51`
- `LSASRV!LsarClose` at `0x180067f51`
- `LSASRV!LsarCreateSecret` at `0x180067e30`
- `LSASRV!LsarCreateSecret` at `0x180067e30`
- `LSASRV!LsarSetSecret` at `0x180067f04`
- `LSASRV!LsarSetSecret` at `0x180067f04`
- `LSASRV!LsarDeleteObject` at `0x180067f3f`
- `LSASRV!LsarDeleteObject` at `0x180067f3f`
- `LSASRV!LsarOpenSecret` at `0x180067dff`
- `LSASRV!LsarOpenSecret` at `0x180067dff`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180067f6b`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180067f6b`
- `LSASRV!LsarQuerySecret` at `0x180067e9c`
- `LSASRV!LsarQuerySecret` at `0x180067e9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180067e4a`
- `ntdll!RtlLeaveCriticalSection` at `0x180067e4a`
- `ntdll!RtlEnterCriticalSection` at `0x180067dd7`
- `ntdll!RtlEnterCriticalSection` at `0x180067dd7`
- `ntdll!RtlInitUnicodeString` at `0x180067dc4`
- `ntdll!RtlInitUnicodeString` at `0x180067dc4`
- `netutils!NetApiBufferFree` at `0x180067f21`
- `netutils!NetApiBufferFree` at `0x180067f21`

## pseudocode

```c
__int64 __fastcall NetpSetAccountSecret(PCWSTR SourceString, const unsigned __int16 *a2, int a3)
{
  int v4; // edi
  int v5; // r15d
  int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int128 *v11; // r8
  __int64 v13; // [rsp+30h] [rbp-39h] BYREF
  __int128 *v14; // [rsp+38h] [rbp-31h] BYREF
  PCWSTR SourceStringa; // [rsp+40h] [rbp-29h] BYREF
  __int128 v16; // [rsp+48h] [rbp-21h] BYREF
  __int128 v17; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 v19[16]; // [rsp+78h] [rbp+Fh] BYREF

  v14 = 0;
  v13 = 0;
  SourceStringa = 0;
  v4 = 0;
  v5 = 0;
  v16 = 0;
  v17 = 0;
  DestinationString = 0;
  v8 = NetpConcatenate(
         0,
         (unsigned __int16 **)&SourceStringa,
         3u,
         L"_SC_{262E99C9-6160-4871-ACEC-4E61736B6F21}_",
         SourceString,
         L"$");
  if ( v8 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceStringa);
    RtlEnterCriticalSection(&NlGlobalDomainCritSect);
    v8 = LsarOpenSecret(*((_QWORD *)NlGlobalDomainInfo + 49), &DestinationString, 3, &v13);
    if ( v8 == -1073741772 )
    {
      v8 = LsarCreateSecret(*((_QWORD *)NlGlobalDomainInfo + 49), &DestinationString, 983043, &v13);
      v4 = 1;
    }
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    if ( v8 >= 0 )
    {
      v9 = -1;
      *((_QWORD *)&v16 + 1) = a2;
      v10 = -1;
      do
        ++v10;
      while ( a2[v10] );
      LODWORD(v16) = 2 * v10;
      DWORD1(v16) = 2 * v10;
      if ( a3 )
      {
        if ( !v4 )
        {
          v8 = -1073741725;
          goto LABEL_19;
        }
        NetpGenerateDefaultPassword(SourceString, v19);
        *((_QWORD *)&v17 + 1) = v19;
        do
          ++v9;
        while ( v19[v9] );
        DWORD1(v17) = 2 * v9;
        v11 = &v17;
        LODWORD(v17) = 2 * v9;
      }
      else
      {
        if ( !v4 )
        {
          v8 = LsarQuerySecret(v13, &v14, 0, 0, 0);
          if ( v8 < 0 )
            goto LABEL_19;
          v11 = v14;
          v5 = 1;
          goto LABEL_18;
        }
        v11 = &v16;
      }
      v14 = v11;
LABEL_18:
      v8 = LsarSetSecret(v13, &v16, v11);
    }
  }
LABEL_19:
  if ( SourceStringa )
    NetApiBufferFree((LPVOID)SourceStringa);
  if ( v13 )
  {
    if ( v4 && v8 < 0 )
      LsarDeleteObject(&v13);
    else
      LsarClose(&v13);
  }
  if ( v14 && v5 )
    LsaIFree_LSAPR_CR_CIPHER_VALUE();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180067d30  mov     [rsp-8+arg_10], rbx
0x180067d35  mov     [rsp-8+arg_18], rdi
0x180067d3a  push    rbp
0x180067d3b  push    r12
0x180067d3d  push    r13
0x180067d3f  push    r14
0x180067d41  push    r15
0x180067d43  lea     rbp, [rsp-37h]
0x180067d48  sub     rsp, 0A0h
0x180067d4f  mov     rax, cs:__security_cookie
0x180067d56  xor     rax, rsp
0x180067d59  mov     [rbp+57h+var_28], rax
0x180067d5d  xor     eax, eax
0x180067d5f  lea     r9, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180067d66  xorps   xmm0, xmm0
0x180067d69  mov     [rbp+57h+var_88], rax
0x180067d6d  mov     r13d, r8d
0x180067d70  mov     [rbp+57h+var_90], rax
0x180067d74  mov     [rbp+57h+SourceString], rax
0x180067d78  mov     edi, eax
0x180067d7a  lea     r8d, [rax+3]; unsigned __int16
0x180067d7e  mov     r15d, eax
0x180067d81  lea     rax, asc_1800ACA94; "$"
0x180067d88  mov     r14, rdx
0x180067d8b  mov     [rsp+0C0h+var_98], rax
0x180067d90  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x180067d94  mov     [rsp+0C0h+var_A0], rcx
0x180067d99  mov     r12, rcx
0x180067d9c  xorps   xmm1, xmm1
0x180067d9f  xor     ecx, ecx; int
0x180067da1  movups  [rbp+57h+var_78], xmm0
0x180067da5  movups  [rbp+57h+var_68], xmm1
0x180067da9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180067dad  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x180067db2  mov     ebx, eax
0x180067db4  test    eax, eax
0x180067db6  js      loc_180067F14
0x180067dbc  mov     rdx, [rbp+57h+SourceString]; SourceString
0x180067dc0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180067dc4  call    cs:__imp_RtlInitUnicodeString
0x180067dcb  nop     dword ptr [rax+rax+00h]
0x180067dd0  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180067dd7  call    cs:__imp_RtlEnterCriticalSection
0x180067dde  nop     dword ptr [rax+rax+00h]
0x180067de3  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180067dea  lea     r9, [rbp+57h+var_90]
0x180067dee  mov     r8d, 3
0x180067df4  lea     rdx, [rbp+57h+DestinationString]
0x180067df8  mov     rcx, [rcx+188h]
0x180067dff  call    cs:__imp_LsarOpenSecret
0x180067e06  nop     dword ptr [rax+rax+00h]
0x180067e0b  mov     ebx, eax
0x180067e0d  cmp     eax, 0C0000034h
0x180067e12  jnz     short loc_180067E43
0x180067e14  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180067e1b  lea     r9, [rbp+57h+var_90]
0x180067e1f  mov     r8d, 0F0003h
0x180067e25  lea     rdx, [rbp+57h+DestinationString]
0x180067e29  mov     rcx, [rcx+188h]
0x180067e30  call    cs:__imp_LsarCreateSecret
0x180067e37  nop     dword ptr [rax+rax+00h]
0x180067e3c  mov     ebx, eax
0x180067e3e  mov     edi, 1
0x180067e43  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180067e4a  call    cs:__imp_RtlLeaveCriticalSection
0x180067e51  nop     dword ptr [rax+rax+00h]
0x180067e56  xor     ecx, ecx
0x180067e58  test    ebx, ebx
0x180067e5a  js      loc_180067F14
0x180067e60  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180067e64  mov     qword ptr [rbp+57h+var_78+8], r14
0x180067e68  mov     rax, rbx
0x180067e6b  inc     rax
0x180067e6e  cmp     [r14+rax*2], cx
0x180067e73  jnz     short loc_180067E6B
0x180067e75  add     eax, eax
0x180067e77  xor     r14d, r14d
0x180067e7a  mov     dword ptr [rbp+57h+var_78], eax
0x180067e7d  mov     dword ptr [rbp+57h+var_78+4], eax
0x180067e80  test    r13d, r13d
0x180067e83  jnz     short loc_180067EBE
0x180067e85  test    edi, edi
0x180067e87  jnz     short loc_180067EB8
0x180067e89  mov     rcx, [rbp+57h+var_90]
0x180067e8d  lea     rdx, [rbp+57h+var_88]
0x180067e91  xor     r9d, r9d
0x180067e94  mov     [rsp+0C0h+var_A0], r14
0x180067e99  xor     r8d, r8d
0x180067e9c  call    cs:__imp_LsarQuerySecret
0x180067ea3  nop     dword ptr [rax+rax+00h]
0x180067ea8  mov     ebx, eax
0x180067eaa  test    eax, eax
0x180067eac  js      short loc_180067F17
0x180067eae  mov     r8, [rbp+57h+var_88]
0x180067eb2  lea     r15d, [r14+1]
0x180067eb6  jmp     short loc_180067EFC
0x180067eb8  lea     r8, [rbp+57h+var_78]
0x180067ebc  jmp     short loc_180067EF8
0x180067ebe  test    edi, edi
0x180067ec0  jnz     short loc_180067EC9
0x180067ec2  mov     ebx, 0C0000063h
0x180067ec7  jmp     short loc_180067F17
0x180067ec9  lea     rdx, [rbp+57h+var_48]; unsigned __int16 *
0x180067ecd  mov     rcx, r12; SourceString
0x180067ed0  call    ?NetpGenerateDefaultPassword@@YAXPEBGPEAG@Z; NetpGenerateDefaultPassword(ushort const *,ushort *)
0x180067ed5  lea     rax, [rbp+57h+var_48]
0x180067ed9  mov     qword ptr [rbp+57h+var_68+8], rax
0x180067edd  lea     rax, [rbp+57h+var_48]
0x180067ee1  inc     rbx
0x180067ee4  cmp     [rax+rbx*2], r14w
0x180067ee9  jnz     short loc_180067EE1
0x180067eeb  lea     eax, [rbx+rbx]
0x180067eee  mov     dword ptr [rbp+57h+var_68+4], eax
0x180067ef1  lea     r8, [rbp+57h+var_68]
0x180067ef5  mov     dword ptr [rbp+57h+var_68], eax
0x180067ef8  mov     [rbp+57h+var_88], r8
0x180067efc  mov     rcx, [rbp+57h+var_90]
0x180067f00  lea     rdx, [rbp+57h+var_78]
0x180067f04  call    cs:__imp_LsarSetSecret
0x180067f0b  nop     dword ptr [rax+rax+00h]
0x180067f10  mov     ebx, eax
0x180067f12  jmp     short loc_180067F17
0x180067f14  xor     r14d, r14d
0x180067f17  cmp     [rbp+57h+SourceString], r14
0x180067f1b  jz      short loc_180067F2D
0x180067f1d  mov     rcx, [rbp+57h+SourceString]; Buffer
0x180067f21  call    cs:__imp_NetApiBufferFree
0x180067f28  nop     dword ptr [rax+rax+00h]
0x180067f2d  cmp     [rbp+57h+var_90], r14
0x180067f31  jz      short loc_180067F5D
0x180067f33  test    edi, edi
0x180067f35  jz      short loc_180067F4D
0x180067f37  test    ebx, ebx
0x180067f39  jns     short loc_180067F4D
0x180067f3b  lea     rcx, [rbp+57h+var_90]
0x180067f3f  call    cs:__imp_LsarDeleteObject
0x180067f46  nop     dword ptr [rax+rax+00h]
0x180067f4b  jmp     short loc_180067F5D
0x180067f4d  lea     rcx, [rbp+57h+var_90]
0x180067f51  call    cs:__imp_LsarClose
0x180067f58  nop     dword ptr [rax+rax+00h]
0x180067f5d  mov     rcx, [rbp+57h+var_88]
0x180067f61  test    rcx, rcx
0x180067f64  jz      short loc_180067F77
0x180067f66  test    r15d, r15d
0x180067f69  jz      short loc_180067F77
0x180067f6b  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x180067f72  nop     dword ptr [rax+rax+00h]
0x180067f77  mov     eax, ebx
0x180067f79  mov     rcx, [rbp+57h+var_28]
0x180067f7d  xor     rcx, rsp; StackCookie
0x180067f80  call    __security_check_cookie
0x180067f85  lea     r11, [rsp+0C0h+var_20]
0x180067f8d  mov     rbx, [r11+40h]
0x180067f91  mov     rdi, [r11+48h]
0x180067f95  mov     rsp, r11
0x180067f98  pop     r15
0x180067f9a  pop     r14
0x180067f9c  pop     r13
0x180067f9e  pop     r12
0x180067fa0  pop     rbp
0x180067fa1  retn
```
