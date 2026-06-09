# ZtInitClientCerts

- ea: `0x1800576b4`
- end: `0x180057864`
- name: `ZtInitClientCerts`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180055ac4`

## callees

- `0x180008870`
- `0x180046ec0`
- `0x1800576b4`
- `0x180066b8c`
- `0x18006a7ac`
- `0x18006a924`
- `0x180086b1c`
- `0x180086eb4`
- `0x18008841c`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180057810`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180057810`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005774e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005774e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577d9`
- `CRYPT32!CertFreeCertificateContext` at `0x18005781e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005781e`

## pseudocode

```c
__int64 __fastcall ZtInitClientCerts(unsigned int a1, __int64 a2)
{
  const CERT_CONTEXT *v2; // rsi
  char v5; // al
  void *v6; // rdi
  _DWORD *v7; // rax
  unsigned int v8; // ebx
  unsigned int ClientCertContextRef; // eax
  __int64 v10; // rcx
  unsigned int updated; // eax
  const CERT_CONTEXT *v13; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  v13 = 0;
  v5 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_dq(1035, 10, (unsigned int)WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids, a1, a2);
    v5 = BYTE1(xmmword_1800AB5A0);
  }
  if ( a1 > 1 )
  {
    v6 = 0;
    v8 = 87;
    if ( (v5 & 8) != 0 )
      WPP_SF_d(1035, 11, WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids, 87);
  }
  else
  {
    if ( a2 )
    {
      v6 = *(void **)(a2 + 56);
      *(_QWORD *)(a2 + 56) = 0;
    }
    else
    {
      v7 = (_DWORD *)Dns_Allocate(48);
      v6 = v7;
      if ( !v7 )
      {
        v8 = 14;
        goto LABEL_19;
      }
      *v7 = 1;
    }
    AcquireSRWLockExclusive(&g_rwZtSettingsLock);
    ClientCertContextRef = ZtGetClientCertContextRef(v6, &v13, 0);
    v2 = v13;
    v8 = ClientCertContextRef;
    if ( !ClientCertContextRef || ClientCertContextRef == 1168 )
    {
      updated = ZtUpdateClientCertConfigGlobal(a1, (__int64)v6, v13, 0, 0);
      v8 = updated;
      if ( updated && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 13, WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids, updated);
    }
    else if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_Dd(v10, 12, WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids, ClientCertContextRef, ClientCertContextRef);
    }
    ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
  }
LABEL_19:
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeClientCertConfig(v6);
  else
    DnsFreeZtClientCertConfig(v6);
  if ( v2 )
    CertFreeCertificateContext(v2);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 14, WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800576b4  mov     r11, rsp
0x1800576b7  mov     [r11+18h], rbx
0x1800576bb  mov     [r11+20h], rbp
0x1800576bf  push    rsi
0x1800576c0  push    rdi
0x1800576c1  push    r12
0x1800576c3  sub     rsp, 40h
0x1800576c7  mov     rax, cs:__security_cookie
0x1800576ce  xor     rax, rsp
0x1800576d1  mov     [rsp+58h+var_20], rax
0x1800576d6  xor     esi, esi
0x1800576d8  mov     rbx, rdx
0x1800576db  mov     [r11-28h], rsi
0x1800576df  mov     ebp, ecx
0x1800576e1  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x1800576e7  lea     r12, WPP_5fb69ae629ca32aed11c463b5577d91f_Traceguids
0x1800576ee  test    al, 8
0x1800576f0  jz      short loc_18005770F
0x1800576f2  lea     edx, [rsi+0Ah]
0x1800576f5  mov     [r11-38h], rbx
0x1800576f9  mov     ecx, 40Bh
0x1800576fe  mov     r9d, ebp
0x180057701  mov     r8, r12
0x180057704  call    WPP_SF_dq
0x180057709  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18005770f  cmp     ebp, 1
0x180057712  ja      loc_1800577E1
0x180057718  test    rbx, rbx
0x18005771b  jz      short loc_180057727
0x18005771d  mov     rdi, [rbx+38h]
0x180057721  mov     [rbx+38h], rsi
0x180057725  jmp     short loc_180057747
0x180057727  mov     ecx, 30h ; '0'
0x18005772c  call    Dns_Allocate
0x180057731  mov     rdi, rax
0x180057734  test    rax, rax
0x180057737  jnz     short loc_180057741
0x180057739  lea     ebx, [rax+0Eh]
0x18005773c  jmp     loc_1800577FD
0x180057741  mov     dword ptr [rax], 1
0x180057747  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18005774e  call    cs:__imp_AcquireSRWLockExclusive
0x180057754  xor     r8d, r8d
0x180057757  lea     rdx, [rsp+58h+var_28]
0x18005775c  mov     rcx, rdi
0x18005775f  call    ZtGetClientCertContextRef
0x180057764  mov     rsi, [rsp+58h+var_28]
0x180057769  mov     ebx, eax
0x18005776b  test    eax, eax
0x18005776d  jz      short loc_180057795
0x18005776f  cmp     eax, 490h
0x180057774  jz      short loc_180057795
0x180057776  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005777d  jz      short loc_1800577D2
0x18005777f  mov     edx, 0Ch
0x180057784  mov     dword ptr [rsp+58h+var_38], eax
0x180057788  mov     r9d, eax
0x18005778b  mov     r8, r12
0x18005778e  call    WPP_SF_Dd
0x180057793  jmp     short loc_1800577D2
0x180057795  xor     r9d, r9d
0x180057798  mov     [rsp+58h+var_38], 0
0x1800577a1  mov     r8, rsi
0x1800577a4  mov     rdx, rdi
0x1800577a7  mov     ecx, ebp
0x1800577a9  call    ZtUpdateClientCertConfigGlobal
0x1800577ae  mov     ebx, eax
0x1800577b0  test    eax, eax
0x1800577b2  jz      short loc_1800577D2
0x1800577b4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800577bb  jz      short loc_1800577D2
0x1800577bd  mov     edx, 0Dh
0x1800577c2  mov     ecx, 40Bh
0x1800577c7  mov     r9d, eax
0x1800577ca  mov     r8, r12
0x1800577cd  call    WPP_SF_d
0x1800577d2  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800577d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800577df  jmp     short loc_1800577FD
0x1800577e1  xor     edi, edi
0x1800577e3  lea     ebx, [rdi+57h]
0x1800577e6  test    al, 8
0x1800577e8  jz      short loc_1800577FD
0x1800577ea  lea     edx, [rdi+0Bh]
0x1800577ed  mov     ecx, 40Bh
0x1800577f2  mov     r9d, ebx
0x1800577f5  mov     r8, r12
0x1800577f8  call    WPP_SF_d
0x1800577fd  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180057804  mov     rcx, rdi; void *
0x180057807  jz      short loc_180057810
0x180057809  call    ZtFreeClientCertConfig
0x18005780e  jmp     short loc_180057816
0x180057810  call    cs:__imp_DnsFreeZtClientCertConfig
0x180057816  test    rsi, rsi
0x180057819  jz      short loc_180057824
0x18005781b  mov     rcx, rsi; pCertContext
0x18005781e  call    cs:__imp_CertFreeCertificateContext
0x180057824  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005782b  jz      short loc_180057842
0x18005782d  mov     edx, 0Eh
0x180057832  mov     ecx, 40Bh
0x180057837  mov     r9d, ebx
0x18005783a  mov     r8, r12
0x18005783d  call    WPP_SF_d
0x180057842  mov     eax, ebx
0x180057844  mov     rcx, [rsp+58h+var_20]
0x180057849  xor     rcx, rsp; StackCookie
0x18005784c  call    __security_check_cookie
0x180057851  mov     rbx, [rsp+58h+arg_10]
0x180057856  mov     rbp, [rsp+58h+arg_18]
0x18005785b  add     rsp, 40h
0x18005785f  pop     r12
0x180057861  pop     rdi
0x180057862  pop     rsi
0x180057863  retn
```
