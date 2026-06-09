# ZtUpdateClientCertConfigGlobal

- ea: `0x18006a924`
- end: `0x18006aace`
- name: `ZtUpdateClientCertConfigGlobal`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800576b4`
- `0x18006aad4`

## callees

- `0x180046ec0`
- `0x180066b8c`
- `0x18006a560`
- `0x18006a924`
- `0x1800852c4`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18006aa66`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18006aa71`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18006aa66`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18006aa71`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006a9fb`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006a9fb`
- `CRYPT32!CertFreeCertificateContext` at `0x18006aa88`
- `CRYPT32!CertFreeCertificateContext` at `0x18006aa88`

## pseudocode

```c
__int64 __fastcall ZtUpdateClientCertConfigGlobal(
        int a1,
        __int64 a2,
        const CERT_CONTEXT *a3,
        _QWORD *a4,
        const CERT_CONTEXT **a5)
{
  void *v5; // r14
  const CERT_CONTEXT *v6; // rbp
  __int64 v7; // r15
  unsigned int v11; // ebx
  unsigned int v12; // eax
  void *v13; // rdx
  void *v15; // [rsp+40h] [rbp-48h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = a1;
  v15 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_dqqqq(a1, a2, (_DWORD)a3, a1, a2, (__int64)a3, (__int64)a4, (__int64)a5);
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a2 && (unsigned int)v7 <= 1 )
  {
    v12 = ZtCopyClientCertConfig(a2, &v15);
    v11 = v12;
    if ( v12 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 14, WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v12);
    }
    else
    {
      v13 = v15;
      v5 = (void *)g_rgpZtClientCerts[v7];
      v15 = 0;
      v6 = (const CERT_CONTEXT *)g_rgpZtClientCertContext[v7];
      g_rgpZtClientCerts[v7] = (__int64)v13;
      g_rgpZtClientCertContext[v7] = 0;
      if ( a3 )
        g_rgpZtClientCertContext[v7] = (__int64)CertDuplicateCertificateContext(a3);
      if ( a4 )
      {
        *a4 = v5;
        v5 = 0;
      }
      if ( a5 )
      {
        *a5 = v6;
        v6 = 0;
      }
    }
  }
  else
  {
    v11 = 87;
  }
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeClientCertConfig(v5);
    ZtFreeClientCertConfig(v15);
  }
  else
  {
    DnsFreeZtClientCertConfig(v5);
    DnsFreeZtClientCertConfig(v15);
  }
  v15 = 0;
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 15, WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18006a924  mov     r11, rsp
0x18006a927  push    rbx
0x18006a928  push    rbp
0x18006a929  push    rsi
0x18006a92a  push    rdi
0x18006a92b  push    r12
0x18006a92d  push    r14
0x18006a92f  push    r15
0x18006a931  sub     rsp, 50h
0x18006a935  mov     rax, cs:__security_cookie
0x18006a93c  xor     rax, rsp
0x18006a93f  mov     [rsp+88h+var_40], rax
0x18006a944  mov     rdi, [rsp+88h+arg_20]
0x18006a94c  xor     r14d, r14d
0x18006a94f  xor     ebp, ebp
0x18006a951  movsxd  r15, ecx
0x18006a954  mov     rsi, r9
0x18006a957  mov     qword ptr [r11-48h], 0
0x18006a95f  mov     r12, r8
0x18006a962  mov     rbx, rdx
0x18006a965  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18006a96c  jz      short loc_18006A986
0x18006a96e  mov     [r11-50h], rdi
0x18006a972  mov     [r11-58h], r9
0x18006a976  mov     r9d, r15d
0x18006a979  mov     [r11-60h], r8
0x18006a97d  mov     [r11-68h], rdx
0x18006a981  call    WPP_SF_dqqqq
0x18006a986  test    rsi, rsi
0x18006a989  jz      short loc_18006A98E
0x18006a98b  mov     [rsi], rbp
0x18006a98e  test    rdi, rdi
0x18006a991  jz      short loc_18006A996
0x18006a993  mov     [rdi], rbp
0x18006a996  test    rbx, rbx
0x18006a999  jnz     short loc_18006A9A5
0x18006a99b  mov     ebx, 57h ; 'W'
0x18006a9a0  jmp     loc_18006AA49
0x18006a9a5  cmp     r15d, 1
0x18006a9a9  ja      short loc_18006A99B
0x18006a9ab  lea     rdx, [rsp+88h+var_48]
0x18006a9b0  mov     rcx, rbx
0x18006a9b3  call    ZtCopyClientCertConfig
0x18006a9b8  mov     ebx, eax
0x18006a9ba  test    eax, eax
0x18006a9bc  jnz     short loc_18006AA27
0x18006a9be  mov     rdx, [rsp+88h+var_48]
0x18006a9c3  lea     rax, __ImageBase
0x18006a9ca  mov     r14, rva g_rgpZtClientCerts[rax+r15*8]
0x18006a9d2  mov     [rsp+88h+var_48], rbp
0x18006a9d7  mov     rbp, rva g_rgpZtClientCertContext[rax+r15*8]
0x18006a9df  mov     rva g_rgpZtClientCerts[rax+r15*8], rdx
0x18006a9e7  mov     rva g_rgpZtClientCertContext[rax+r15*8], 0
0x18006a9f3  test    r12, r12
0x18006a9f6  jz      short loc_18006AA10
0x18006a9f8  mov     rcx, r12; pCertContext
0x18006a9fb  call    cs:__imp_CertDuplicateCertificateContext
0x18006aa01  lea     rcx, __ImageBase
0x18006aa08  mov     rva g_rgpZtClientCertContext[rcx+r15*8], rax
0x18006aa10  test    rsi, rsi
0x18006aa13  jz      short loc_18006AA1B
0x18006aa15  mov     [rsi], r14
0x18006aa18  xor     r14d, r14d
0x18006aa1b  test    rdi, rdi
0x18006aa1e  jz      short loc_18006AA49
0x18006aa20  mov     [rdi], rbp
0x18006aa23  xor     ebp, ebp
0x18006aa25  jmp     short loc_18006AA49
0x18006aa27  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18006aa2e  jz      short loc_18006AA49
0x18006aa30  mov     edx, 0Eh
0x18006aa35  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x18006aa3c  mov     ecx, 40Bh
0x18006aa41  mov     r9d, eax
0x18006aa44  call    WPP_SF_d
0x18006aa49  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x18006aa50  mov     rcx, r14; void *
0x18006aa53  jz      short loc_18006AA66
0x18006aa55  call    ZtFreeClientCertConfig
0x18006aa5a  mov     rcx, [rsp+88h+var_48]; void *
0x18006aa5f  call    ZtFreeClientCertConfig
0x18006aa64  jmp     short loc_18006AA77
0x18006aa66  call    cs:__imp_DnsFreeZtClientCertConfig
0x18006aa6c  mov     rcx, [rsp+88h+var_48]
0x18006aa71  call    cs:__imp_DnsFreeZtClientCertConfig
0x18006aa77  mov     [rsp+88h+var_48], 0
0x18006aa80  test    rbp, rbp
0x18006aa83  jz      short loc_18006AA8E
0x18006aa85  mov     rcx, rbp; pCertContext
0x18006aa88  call    cs:__imp_CertFreeCertificateContext
0x18006aa8e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18006aa95  jz      short loc_18006AAB0
0x18006aa97  mov     edx, 0Fh
0x18006aa9c  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x18006aaa3  mov     ecx, 40Bh
0x18006aaa8  mov     r9d, ebx
0x18006aaab  call    WPP_SF_d
0x18006aab0  mov     eax, ebx
0x18006aab2  mov     rcx, [rsp+88h+var_40]
0x18006aab7  xor     rcx, rsp; StackCookie
0x18006aaba  call    __security_check_cookie
0x18006aabf  add     rsp, 50h
0x18006aac3  pop     r15
0x18006aac5  pop     r14
0x18006aac7  pop     r12
0x18006aac9  pop     rdi
0x18006aaca  pop     rsi
0x18006aacb  pop     rbp
0x18006aacc  pop     rbx
0x18006aacd  retn
```
