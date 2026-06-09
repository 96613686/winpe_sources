# DsrCmdCertHelper::TryPrivateKeyAquire(KeyProvInfo const &)

- ea: `0x1800b26e4`
- end: `0x1800b284c`
- name: `?TryPrivateKeyAquire@DsrCmdCertHelper@@SAJAEBVKeyProvInfo@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(const struct KeyProvInfo *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800a81f0`
- `0x1800b2528`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x180046ae8`
- `0x180046b3c`
- `0x180076b8c`
- `0x180076bd8`
- `0x1800b26e4`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800b27a2`
- `ncrypt!NCryptOpenKey` at `0x1800b27a2`
- `ncrypt!NCryptFreeObject` at `0x1800b282c`
- `ncrypt!NCryptFreeObject` at `0x1800b283c`
- `ncrypt!NCryptFreeObject` at `0x1800b282c`
- `ncrypt!NCryptFreeObject` at `0x1800b283c`

## string_xrefs

- `0x1800b2729`: `%s: NCryptOpenStorageProvider failed 0x%08x.\n`
- `0x1800b27b3`: `%s: NCryptOpenKey failed 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall DsrCmdCertHelper::TryPrivateKeyAquire(LPCWSTR **a1)
{
  LPCWSTR *v2; // rcx
  int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  SECURITY_STATUS v6; // ebx
  _BYTE **CurrentRef; // rax
  const wchar_t *v8; // rsi
  int IsTpmProvider; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  int v20; // [rsp+50h] [rbp+8h] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+58h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp+18h] BYREF

  hProvider = 0;
  v2 = *a1;
  phKey = 0;
  v20 = 0;
  v3 = *((_DWORD *)v2 + 5);
  v6 = RegistrationKeyHelper::OpenNCryptStorageProvider(v2[1], &hProvider, 0);
  if ( v6 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v5, v4);
    v8 = L"%s: NCryptOpenStorageProvider failed 0x%08x.\n";
    goto LABEL_7;
  }
  IsTpmProvider = RegistrationKeyHelper::IsTpmProvider((*a1)[1], &v20);
  v6 = IsTpmProvider;
  if ( IsTpmProvider < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrCmdCertHelper::TryPrivateKeyAquire",
      L"RegistrationKeyHelper::IsTpmProvider",
      (unsigned int)IsTpmProvider);
    goto LABEL_12;
  }
  v6 = NCryptOpenKey(hProvider, &phKey, **a1, 0, (v20 != 0 ? 0x10000000 : 0) | ((v3 & 0x20) != 0 ? 96 : 64));
  if ( v6 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v11, v10);
    v8 = L"%s: NCryptOpenKey failed 0x%08x.\n";
LABEL_7:
    if ( **CurrentRef )
    {
      wprintf(v8, L"DsrCmdCertHelper::TryPrivateKeyAquire", (unsigned int)v6);
      v14 = (_QWORD *)CmdOptions::GetCurrentRef(v13, v12);
      if ( *(_BYTE *)(*v14 + 12LL) )
      {
        v16 = (_QWORD *)CmdOptions::GetCurrentRef(*v14, v15);
        if ( *(_QWORD *)(*v16 + 184LL) )
        {
          v18 = CmdOptions::GetCurrentRef(*v16, v17);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v18 + 184LL),
            v8,
            L"DsrCmdCertHelper::TryPrivateKeyAquire",
            (unsigned int)v6);
        }
      }
    }
    Logger::TraceError(v8, L"DsrCmdCertHelper::TryPrivateKeyAquire", (unsigned int)v6);
  }
LABEL_12:
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( hProvider )
    NCryptFreeObject(hProvider);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b26e4  mov     rax, rsp
0x1800b26e7  push    rbx
0x1800b26e8  push    rsi
0x1800b26e9  push    rdi
0x1800b26ea  sub     rsp, 30h
0x1800b26ee  mov     rdi, rcx
0x1800b26f1  mov     qword ptr [rax+10h], 0
0x1800b26f9  mov     rcx, [rcx]
0x1800b26fc  lea     rdx, [rax+10h]; phProvider
0x1800b2700  mov     qword ptr [rax+18h], 0
0x1800b2708  xor     r8d, r8d; int
0x1800b270b  mov     dword ptr [rax+8], 0
0x1800b2712  mov     esi, [rcx+14h]
0x1800b2715  mov     rcx, [rcx+8]; unsigned __int16 *
0x1800b2719  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x1800b271e  mov     ebx, eax
0x1800b2720  test    eax, eax
0x1800b2722  jns     short loc_1800B2735
0x1800b2724  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800b2729  lea     rsi, aSNcryptopensto_0; "%s: NCryptOpenStorageProvider failed 0x"...
0x1800b2730  jmp     loc_1800B27BA
0x1800b2735  mov     rcx, [rdi]
0x1800b2738  lea     rdx, [rsp+48h+arg_0]; int *
0x1800b273d  mov     rcx, [rcx+8]; unsigned __int16 *
0x1800b2741  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x1800b2746  mov     ebx, eax
0x1800b2748  test    eax, eax
0x1800b274a  jns     short loc_1800B276E
0x1800b274c  mov     r9d, eax
0x1800b274f  lea     r8, aRegistrationke_3; "RegistrationKeyHelper::IsTpmProvider"
0x1800b2756  lea     rdx, aDsrcmdcerthelp; "DsrCmdCertHelper::TryPrivateKeyAquire"
0x1800b275d  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b2764  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b2769  jmp     loc_1800B2822
0x1800b276e  mov     eax, [rsp+48h+arg_0]
0x1800b2772  and     esi, 20h
0x1800b2775  mov     r8, [rdi]
0x1800b2778  neg     eax
0x1800b277a  mov     rcx, [rsp+48h+hProvider]; hProvider
0x1800b277f  sbb     edx, edx
0x1800b2781  and     edx, 10000000h
0x1800b2787  mov     r8, [r8]; pszKeyName
0x1800b278a  neg     esi
0x1800b278c  sbb     eax, eax
0x1800b278e  xor     r9d, r9d; dwLegacyKeySpec
0x1800b2791  and     eax, 20h
0x1800b2794  add     eax, 40h ; '@'
0x1800b2797  or      eax, edx
0x1800b2799  lea     rdx, [rsp+48h+phKey]; phKey
0x1800b279e  mov     [rsp+48h+dwFlags], eax; dwFlags
0x1800b27a2  call    cs:__imp_NCryptOpenKey
0x1800b27a8  mov     ebx, eax
0x1800b27aa  test    eax, eax
0x1800b27ac  jns     short loc_1800B2822
0x1800b27ae  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800b27b3  lea     rsi, aSNcryptopenkey; "%s: NCryptOpenKey failed 0x%08x.\n"
0x1800b27ba  mov     rcx, [rax]
0x1800b27bd  lea     rdi, aDsrcmdcerthelp; "DsrCmdCertHelper::TryPrivateKeyAquire"
0x1800b27c4  cmp     byte ptr [rcx], 0
0x1800b27c7  jz      short loc_1800B2814
0x1800b27c9  mov     r8d, ebx
0x1800b27cc  mov     rdx, rdi
0x1800b27cf  mov     rcx, rsi; Format
0x1800b27d2  call    wprintf
0x1800b27d7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800b27dc  mov     rcx, [rax]
0x1800b27df  cmp     byte ptr [rcx+0Ch], 0
0x1800b27e3  jz      short loc_1800B2814
0x1800b27e5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800b27ea  mov     rcx, [rax]
0x1800b27ed  cmp     qword ptr [rcx+0B8h], 0
0x1800b27f5  jz      short loc_1800B2814
0x1800b27f7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800b27fc  mov     r9d, ebx
0x1800b27ff  mov     r8, rdi
0x1800b2802  mov     rdx, rsi; Format
0x1800b2805  mov     rcx, [rax]
0x1800b2808  mov     rcx, [rcx+0B8h]; Stream
0x1800b280f  call    fwprintf_s
0x1800b2814  mov     r8d, ebx
0x1800b2817  mov     rdx, rdi
0x1800b281a  mov     rcx, rsi; unsigned __int16 *
0x1800b281d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b2822  mov     rcx, [rsp+48h+phKey]; hObject
0x1800b2827  test    rcx, rcx
0x1800b282a  jz      short loc_1800B2832
0x1800b282c  call    cs:__imp_NCryptFreeObject
0x1800b2832  mov     rcx, [rsp+48h+hProvider]; hObject
0x1800b2837  test    rcx, rcx
0x1800b283a  jz      short loc_1800B2842
0x1800b283c  call    cs:__imp_NCryptFreeObject
0x1800b2842  mov     eax, ebx
0x1800b2844  add     rsp, 30h
0x1800b2848  pop     rdi
0x1800b2849  pop     rsi
0x1800b284a  pop     rbx
0x1800b284b  retn
```
