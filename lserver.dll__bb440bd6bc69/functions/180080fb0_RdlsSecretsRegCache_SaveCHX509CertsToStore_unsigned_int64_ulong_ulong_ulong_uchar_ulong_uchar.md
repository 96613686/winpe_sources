# RdlsSecretsRegCache::SaveCHX509CertsToStore(unsigned __int64,ulong,ulong,ulong,uchar *,ulong,uchar *)

- ea: `0x180080fb0`
- end: `0x180081281`
- name: `?SaveCHX509CertsToStore@RdlsSecretsRegCache@@UEAAK_KKKKPEAEK1@Z`
- size: `721`
- prototype: `unsigned int __usercall@<eax>(RdlsSecretsRegCache *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, DWORD, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18007cdfc`
- `0x180080fb0`
- `0x180081288`
- `0x18008143c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18008105d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800810e7`
- `ADVAPI32!RegCreateKeyExW` at `0x18008105d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800810e7`
- `ADVAPI32!RegCloseKey` at `0x180081090`
- `ADVAPI32!RegCloseKey` at `0x18008111a`
- `ADVAPI32!RegCloseKey` at `0x180081090`
- `ADVAPI32!RegCloseKey` at `0x18008111a`
- `KERNEL32!LocalFree` at `0x180081207`
- `KERNEL32!LocalFree` at `0x180081221`
- `KERNEL32!LocalFree` at `0x180081244`
- `KERNEL32!LocalFree` at `0x180081258`
- `KERNEL32!LocalFree` at `0x180081207`
- `KERNEL32!LocalFree` at `0x180081221`
- `KERNEL32!LocalFree` at `0x180081244`
- `KERNEL32!LocalFree` at `0x180081258`

## pseudocode

```c
LSTATUS __fastcall RdlsSecretsRegCache::SaveCHX509CertsToStore(
        RdlsSecretsRegCache *this,
        unsigned __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8)
{
  unsigned int v8; // edi
  LSTATUS result; // eax
  const WCHAR *v13; // rdx
  const WCHAR *v14; // rbx
  RdlsSecretsRegCache *v15; // rcx
  RdlsSecretsRegCache *v16; // rcx
  DWORD v17; // r12d
  unsigned __int8 *v18; // rsi
  unsigned __int8 *v19; // rbx
  unsigned int IsCertificateLicenseServerCertificate; // eax
  unsigned int v21; // eax
  void *v22; // rcx
  void *v23; // rcx
  unsigned int v24; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 *v27; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+30h] BYREF

  hKey = 0;
  v8 = 0;
  switch ( a3 )
  {
    case 1:
      v13 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Signature\\CA";
      v14 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Exchange\\CA";
      break;
    case 2:
      v13 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Signature\\RA";
      v14 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Exchange\\RA";
      break;
    case 3:
      v13 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Signature\\CH";
      v14 = L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Exchange\\CH";
      break;
    default:
      return -1073676256;
  }
  if ( !a5 )
    goto LABEL_37;
  dwDisposition = 0;
  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( result )
    return result;
  v8 = RdlsSecretsRegCache::SaveCertificatesToReg(v15, a2, hKey, a5, a6);
  RegCloseKey(hKey);
  if ( !v8 )
  {
LABEL_37:
    if ( !a7 )
      goto LABEL_14;
    dwDisposition = 0;
    result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( result )
      return result;
    v8 = RdlsSecretsRegCache::SaveCertificatesToReg(v16, a2, hKey, a7, a8);
    RegCloseKey(hKey);
    if ( !v8 )
    {
LABEL_14:
      if ( a3 == 1 )
      {
        v17 = 0;
        v18 = 0;
        v24 = 0;
        v19 = 0;
        dwDisposition = 0;
        hMem = 0;
        v27 = 0;
        if ( a5 )
        {
          IsCertificateLicenseServerCertificate = RdlsSecretsCache::IsCertificateLicenseServerCertificate(
                                                    this,
                                                    g_RdlsCryptProv,
                                                    2u,
                                                    a5,
                                                    a6,
                                                    &dwDisposition,
                                                    (unsigned __int8 **)&hMem);
          v18 = (unsigned __int8 *)hMem;
          v8 = IsCertificateLicenseServerCertificate;
          if ( IsCertificateLicenseServerCertificate )
            goto LABEL_23;
          v17 = dwDisposition;
        }
        if ( a7 )
        {
          v21 = RdlsSecretsCache::IsCertificateLicenseServerCertificate(this, g_RdlsCryptProv, 1u, a7, a8, &v24, &v27);
          v19 = v27;
          v8 = v21;
          if ( !v21 && (v24 || v27) )
            v8 = RdlsSecretsRegCache::StoreCHEndorsedRdlsCertificates(this, v17, v18, v24, v27);
        }
LABEL_23:
        if ( v18 )
        {
          if ( !v19 )
          {
LABEL_32:
            if ( v18 )
              LocalFree(v18);
            return v8;
          }
          v22 = (void *)*((_QWORD *)this + 4);
          if ( v22 )
            LocalFree(v22);
          *((_QWORD *)this + 4) = 0;
          v23 = (void *)*((_QWORD *)this + 6);
          if ( v23 )
            LocalFree(v23);
          *((_QWORD *)this + 6) = 0;
          *((_DWORD *)this + 6) = 0;
          *((_DWORD *)this + 10) = 0;
        }
        if ( v19 )
          LocalFree(v19);
        goto LABEL_32;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180080fb0  mov     [rsp-18h+arg_0], rbx
0x180080fb5  mov     [rsp-18h+arg_8], rsi
0x180080fba  mov     [rsp-18h+arg_18], rdi
0x180080fbf  push    rbp
0x180080fc0  push    r12
0x180080fc2  push    r14
0x180080fc4  mov     rbp, rsp
0x180080fc7  sub     rsp, 70h
0x180080fcb  and     [rbp+hKey], 0
0x180080fd0  xor     edi, edi
0x180080fd2  mov     eax, r8d
0x180080fd5  mov     esi, r8d
0x180080fd8  mov     r12, rdx
0x180080fdb  mov     r14, rcx
0x180080fde  sub     eax, 1
0x180080fe1  jz      short loc_180081017
0x180080fe3  sub     eax, 1
0x180080fe6  jz      short loc_180081007
0x180080fe8  cmp     eax, 1
0x180080feb  jz      short loc_180080FF7
0x180080fed  mov     eax, 0C0010020h
0x180080ff2  jmp     loc_180081266
0x180080ff7  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180080ffe  lea     rbx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180081005  jmp     short loc_180081025
0x180081007  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x18008100e  lea     rbx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180081015  jmp     short loc_180081025
0x180081017  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x18008101e  lea     rbx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180081025  cmp     [rbp+arg_20], edi
0x180081028  jz      short loc_1800810A4
0x18008102a  and     [rbp+dwDisposition], edi
0x18008102d  lea     rax, [rbp+dwDisposition]
0x180081031  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180081036  xor     r9d, r9d; lpClass
0x180081039  lea     rax, [rbp+hKey]
0x18008103d  xor     r8d, r8d; Reserved
0x180081040  mov     [rsp+70h+phkResult], rax; phkResult
0x180081045  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008104c  and     [rsp+70h+var_40], rdi
0x180081051  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180081059  and     [rsp+70h+dwOptions], edi
0x18008105d  call    cs:__imp_RegCreateKeyExW
0x180081064  nop     dword ptr [rax+rax+00h]
0x180081069  test    eax, eax
0x18008106b  jnz     loc_180081266
0x180081071  mov     rax, [rbp+arg_28]
0x180081075  mov     rdx, r12; unsigned __int64
0x180081078  mov     r9d, [rbp+arg_20]; unsigned int
0x18008107c  mov     r8, [rbp+hKey]; HKEY
0x180081080  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int8 *
0x180081085  call    ?SaveCertificatesToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z; RdlsSecretsRegCache::SaveCertificatesToReg(unsigned __int64,HKEY__ *,ulong,uchar *)
0x18008108a  mov     rcx, [rbp+hKey]; hKey
0x18008108e  mov     edi, eax
0x180081090  call    cs:__imp_RegCloseKey
0x180081097  nop     dword ptr [rax+rax+00h]
0x18008109c  test    edi, edi
0x18008109e  jnz     loc_180081264
0x1800810a4  cmp     [rbp+arg_30], 0
0x1800810a8  jz      loc_18008112E
0x1800810ae  and     [rbp+dwDisposition], 0
0x1800810b2  lea     rax, [rbp+dwDisposition]
0x1800810b6  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800810bb  xor     r9d, r9d; lpClass
0x1800810be  lea     rax, [rbp+hKey]
0x1800810c2  xor     r8d, r8d; Reserved
0x1800810c5  mov     [rsp+70h+phkResult], rax; phkResult
0x1800810ca  mov     rdx, rbx; lpSubKey
0x1800810cd  and     [rsp+70h+var_40], 0
0x1800810d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800810da  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x1800810e2  and     [rsp+70h+dwOptions], 0
0x1800810e7  call    cs:__imp_RegCreateKeyExW
0x1800810ee  nop     dword ptr [rax+rax+00h]
0x1800810f3  test    eax, eax
0x1800810f5  jnz     loc_180081266
0x1800810fb  mov     rax, [rbp+arg_38]
0x1800810ff  mov     rdx, r12; unsigned __int64
0x180081102  mov     r9d, [rbp+arg_30]; unsigned int
0x180081106  mov     r8, [rbp+hKey]; HKEY
0x18008110a  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int8 *
0x18008110f  call    ?SaveCertificatesToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z; RdlsSecretsRegCache::SaveCertificatesToReg(unsigned __int64,HKEY__ *,ulong,uchar *)
0x180081114  mov     rcx, [rbp+hKey]; hKey
0x180081118  mov     edi, eax
0x18008111a  call    cs:__imp_RegCloseKey
0x180081121  nop     dword ptr [rax+rax+00h]
0x180081126  test    edi, edi
0x180081128  jnz     loc_180081264
0x18008112e  cmp     esi, 1
0x180081131  jnz     loc_180081264
0x180081137  xor     r12d, r12d
0x18008113a  xor     esi, esi
0x18008113c  and     [rbp+var_20], r12d
0x180081140  xor     ebx, ebx
0x180081142  mov     [rbp+dwDisposition], r12d
0x180081146  mov     [rbp+hMem], rsi
0x18008114a  mov     [rbp+var_8], rbx
0x18008114e  cmp     [rbp+arg_20], ebx
0x180081151  jz      short loc_180081191
0x180081153  mov     r9d, [rbp+arg_20]; unsigned int
0x180081157  lea     rax, [rbp+hMem]
0x18008115b  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; unsigned __int64
0x180081162  lea     r8d, [r12+2]; unsigned int
0x180081167  mov     [rsp+70h+var_40], rax; unsigned __int8 **
0x18008116c  lea     rax, [rbp+dwDisposition]
0x180081170  mov     qword ptr [rsp+70h+samDesired], rax; unsigned int *
0x180081175  mov     rax, [rbp+arg_28]
0x180081179  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int8 *
0x18008117e  call    ?IsCertificateLicenseServerCertificate@RdlsSecretsCache@@IEAAK_KKKPEAEPEAKPEAPEAE@Z; RdlsSecretsCache::IsCertificateLicenseServerCertificate(unsigned __int64,ulong,ulong,uchar *,ulong *,uchar * *)
0x180081183  mov     rsi, [rbp+hMem]
0x180081187  mov     edi, eax
0x180081189  test    eax, eax
0x18008118b  jnz     short loc_1800811F4
0x18008118d  mov     r12d, [rbp+dwDisposition]
0x180081191  cmp     [rbp+arg_30], ebx
0x180081194  jz      short loc_1800811F4
0x180081196  mov     r9d, [rbp+arg_30]; unsigned int
0x18008119a  lea     rax, [rbp+var_8]
0x18008119e  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; unsigned __int64
0x1800811a5  mov     r8d, 1; unsigned int
0x1800811ab  mov     [rsp+70h+var_40], rax; unsigned __int8 **
0x1800811b0  lea     rax, [rbp+var_20]
0x1800811b4  mov     qword ptr [rsp+70h+samDesired], rax; unsigned int *
0x1800811b9  mov     rax, [rbp+arg_38]
0x1800811bd  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int8 *
0x1800811c2  call    ?IsCertificateLicenseServerCertificate@RdlsSecretsCache@@IEAAK_KKKPEAEPEAKPEAPEAE@Z; RdlsSecretsCache::IsCertificateLicenseServerCertificate(unsigned __int64,ulong,ulong,uchar *,ulong *,uchar * *)
0x1800811c7  mov     rbx, [rbp+var_8]
0x1800811cb  mov     edi, eax
0x1800811cd  test    eax, eax
0x1800811cf  jnz     short loc_1800811F4
0x1800811d1  mov     r9d, [rbp+var_20]; unsigned int
0x1800811d5  test    r9d, r9d
0x1800811d8  jnz     short loc_1800811DF
0x1800811da  test    rbx, rbx
0x1800811dd  jz      short loc_1800811F4
0x1800811df  mov     r8, rsi; unsigned __int8 *
0x1800811e2  mov     qword ptr [rsp+70h+dwOptions], rbx; unsigned __int8 *
0x1800811e7  mov     edx, r12d; unsigned int
0x1800811ea  mov     rcx, r14; this
0x1800811ed  call    ?StoreCHEndorsedRdlsCertificates@RdlsSecretsRegCache@@AEAAKKPEAEK0@Z; RdlsSecretsRegCache::StoreCHEndorsedRdlsCertificates(ulong,uchar *,ulong,uchar *)
0x1800811f2  mov     edi, eax
0x1800811f4  test    rsi, rsi
0x1800811f7  jz      short loc_18008123C
0x1800811f9  test    rbx, rbx
0x1800811fc  jz      short loc_180081250
0x1800811fe  mov     rcx, [r14+20h]; hMem
0x180081202  test    rcx, rcx
0x180081205  jz      short loc_180081213
0x180081207  call    cs:__imp_LocalFree
0x18008120e  nop     dword ptr [rax+rax+00h]
0x180081213  and     qword ptr [r14+20h], 0
0x180081218  mov     rcx, [r14+30h]; hMem
0x18008121c  test    rcx, rcx
0x18008121f  jz      short loc_18008122D
0x180081221  call    cs:__imp_LocalFree
0x180081228  nop     dword ptr [rax+rax+00h]
0x18008122d  and     qword ptr [r14+30h], 0
0x180081232  and     dword ptr [r14+18h], 0
0x180081237  and     dword ptr [r14+28h], 0
0x18008123c  test    rbx, rbx
0x18008123f  jz      short loc_180081250
0x180081241  mov     rcx, rbx; hMem
0x180081244  call    cs:__imp_LocalFree
0x18008124b  nop     dword ptr [rax+rax+00h]
0x180081250  test    rsi, rsi
0x180081253  jz      short loc_180081264
0x180081255  mov     rcx, rsi; hMem
0x180081258  call    cs:__imp_LocalFree
0x18008125f  nop     dword ptr [rax+rax+00h]
0x180081264  mov     eax, edi
0x180081266  lea     r11, [rsp+70h+var_s0]
0x18008126b  mov     rbx, [r11+20h]
0x18008126f  mov     rsi, [r11+28h]
0x180081273  mov     rdi, [r11+38h]
0x180081277  mov     rsp, r11
0x18008127a  pop     r14
0x18008127c  pop     r12
0x18008127e  pop     rbp
0x18008127f  retn
```
