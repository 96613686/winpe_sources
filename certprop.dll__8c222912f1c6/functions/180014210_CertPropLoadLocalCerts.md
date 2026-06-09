# CertPropLoadLocalCerts

- ea: `0x180014210`
- end: `0x1800144c7`
- name: `CertPropLoadLocalCerts`
- size: `695`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fe80`

## callees

- `0x180004600`
- `0x18000d7a0`
- `0x180014210`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014445`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014445`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014271`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014290`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001434b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001434b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014470`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014470`
- `CRYPT32!CertCloseStore` at `0x180014455`
- `CRYPT32!CertCloseStore` at `0x180014465`
- `CRYPT32!CertCloseStore` at `0x180014455`
- `CRYPT32!CertCloseStore` at `0x180014465`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800143f0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800143f0`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180014398`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180014398`
- `CRYPT32!CertOpenStore` at `0x1800142be`
- `CRYPT32!CertOpenStore` at `0x18001433d`
- `CRYPT32!CertOpenStore` at `0x1800142be`
- `CRYPT32!CertOpenStore` at `0x18001433d`

## pseudocode

```c
__int64 __fastcall CertPropLoadLocalCerts(__int64 a1)
{
  int v1; // r14d
  HCERTSTORE v2; // rdi
  HCERTSTORE v3; // rbp
  unsigned int v4; // ebx
  int v5; // r9d
  __int64 SessionNode; // rax
  __int64 v7; // rcx
  DWORD LastError; // ebx
  __int64 v9; // rcx
  STRSAFE_LPSTR v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  const CERT_CONTEXT *i; // rdx
  char v14; // si
  __int64 v15; // rcx
  const CERT_CONTEXT *v16; // rax
  const CERT_CONTEXT *v17; // rbx
  __int64 v18; // rcx

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v4 = a1;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      v5,
      v4);
  }
  EnterCriticalSection(&g_csSessionList);
  SessionNode = CertPropGetSessionNode(v4);
  if ( !SessionNode )
  {
    LastError = 0;
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
    }
    goto LABEL_31;
  }
  if ( !SetThreadToken(0, *(HANDLE *)(SessionNode + 416)) )
  {
LABEL_26:
    LastError = 0;
    goto LABEL_31;
  }
  v1 = 1;
  v2 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x14000u, L"Local NonRemovable Certificates");
  if ( !v2 )
  {
    LastError = GetLastError();
    WppTraceIndent(v9, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v11 = 57;
LABEL_12:
      WPP_SF_sD(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
        WPP_pszIndent,
        LastError);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
  if ( v3 )
  {
    for ( i = 0; ; i = v17 )
    {
      v16 = CertEnumCertificatesInStore(v2, i);
      v17 = v16;
      if ( !v16 )
        break;
      if ( !CertAddCertificateContextToStore(v3, v16, 3u, 0) )
      {
        v14 = GetLastError();
        WppTraceIndent(v15, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
            WPP_pszIndent,
            v14);
        }
      }
    }
    goto LABEL_26;
  }
  LastError = GetLastError();
  WppTraceIndent(v12, 2);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v11 = 58;
    goto LABEL_12;
  }
LABEL_31:
  LeaveCriticalSection(&g_csSessionList);
  if ( v2 )
    CertCloseStore(v2, 0);
  if ( v3 )
    CertCloseStore(v3, 0);
  if ( v1 )
    RevertToSelf();
  WppTraceIndent(v18, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180014210  push    rbx
0x180014212  push    rbp
0x180014213  push    rsi
0x180014214  push    rdi
0x180014215  push    r13
0x180014217  push    r14
0x180014219  push    r15
0x18001421b  sub     rsp, 30h
0x18001421f  xor     r14d, r14d
0x180014222  xor     edi, edi
0x180014224  xor     ebp, ebp
0x180014226  mov     ebx, ecx
0x180014228  lea     r15d, [r14+2]
0x18001422c  mov     edx, r15d
0x18001422f  call    WppTraceIndent
0x180014234  mov     rcx, cs:WPP_GLOBAL_Control
0x18001423b  lea     r13, WPP_GLOBAL_Control
0x180014242  cmp     rcx, r13
0x180014245  jz      short loc_18001426A
0x180014247  test    byte ptr [rcx+1Ch], 1
0x18001424b  jz      short loc_18001426A
0x18001424d  cmp     byte ptr [rcx+19h], 5
0x180014251  jb      short loc_18001426A
0x180014253  mov     rcx, [rcx+10h]
0x180014257  lea     edx, [rdi+38h]
0x18001425a  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014261  mov     dword ptr [rsp+68h+pvPara], ebx
0x180014265  call    WPP_SF_sd
0x18001426a  lea     rcx, g_csSessionList; lpCriticalSection
0x180014271  call    cs:__imp_EnterCriticalSection
0x180014277  mov     ecx, ebx
0x180014279  call    CertPropGetSessionNode
0x18001427e  test    rax, rax
0x180014281  jz      loc_180014402
0x180014287  mov     rdx, [rax+1A0h]; Token
0x18001428e  xor     ecx, ecx; Thread
0x180014290  call    cs:__imp_SetThreadToken
0x180014296  test    eax, eax
0x180014298  jz      loc_1800143FE
0x18001429e  xor     edx, edx; dwEncodingType
0x1800142a0  lea     rax, aLocalNonremova; "Local NonRemovable Certificates"
0x1800142a7  mov     r9d, 14000h; dwFlags
0x1800142ad  mov     [rsp+68h+pvPara], rax; pvPara
0x1800142b2  xor     r8d, r8d; hCryptProv
0x1800142b5  mov     r14d, 1
0x1800142bb  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x1800142be  call    cs:__imp_CertOpenStore
0x1800142c4  mov     rdi, rax
0x1800142c7  test    rax, rax
0x1800142ca  jnz     short loc_180014323
0x1800142cc  call    cs:__imp_GetLastError
0x1800142d2  mov     edx, r15d
0x1800142d5  mov     ebx, eax
0x1800142d7  call    WppTraceIndent
0x1800142dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142e3  cmp     rcx, r13
0x1800142e6  jz      loc_18001443E
0x1800142ec  test    [rcx+1Ch], r14b
0x1800142f0  jz      loc_18001443E
0x1800142f6  cmp     [rcx+19h], r15b
0x1800142fa  jb      loc_18001443E
0x180014300  lea     edx, [rdi+39h]
0x180014303  mov     r9, cs:WPP_pszIndent
0x18001430a  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014311  mov     rcx, [rcx+10h]
0x180014315  mov     dword ptr [rsp+68h+pvPara], ebx
0x180014319  call    WPP_SF_sD
0x18001431e  jmp     loc_18001443E
0x180014323  xor     edx, edx; dwEncodingType
0x180014325  lea     rax, aMy; "MY"
0x18001432c  mov     r9d, 10000h; dwFlags
0x180014332  mov     [rsp+68h+pvPara], rax; pvPara
0x180014337  xor     r8d, r8d; hCryptProv
0x18001433a  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18001433d  call    cs:__imp_CertOpenStore
0x180014343  mov     rbp, rax
0x180014346  test    rax, rax
0x180014349  jnz     short loc_180014387
0x18001434b  call    cs:__imp_GetLastError
0x180014351  mov     edx, r15d
0x180014354  mov     ebx, eax
0x180014356  call    WppTraceIndent
0x18001435b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014362  cmp     rcx, r13
0x180014365  jz      loc_18001443E
0x18001436b  test    [rcx+1Ch], r14b
0x18001436f  jz      loc_18001443E
0x180014375  cmp     [rcx+19h], r15b
0x180014379  jb      loc_18001443E
0x18001437f  lea     edx, [rbp+3Ah]
0x180014382  jmp     loc_180014303
0x180014387  xor     edx, edx
0x180014389  jmp     short loc_1800143ED
0x18001438b  xor     r9d, r9d; ppStoreContext
0x18001438e  mov     rdx, rbx; pCertContext
0x180014391  mov     rcx, rbp; hCertStore
0x180014394  lea     r8d, [r9+3]; dwAddDisposition
0x180014398  call    cs:__imp_CertAddCertificateContextToStore
0x18001439e  test    eax, eax
0x1800143a0  jnz     short loc_1800143EA
0x1800143a2  call    cs:__imp_GetLastError
0x1800143a8  mov     edx, r15d
0x1800143ab  mov     esi, eax
0x1800143ad  call    WppTraceIndent
0x1800143b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143b9  cmp     rcx, r13
0x1800143bc  jz      short loc_1800143EA
0x1800143be  test    [rcx+1Ch], r14b
0x1800143c2  jz      short loc_1800143EA
0x1800143c4  cmp     byte ptr [rcx+19h], 3
0x1800143c8  jb      short loc_1800143EA
0x1800143ca  mov     r9, cs:WPP_pszIndent
0x1800143d1  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800143d8  mov     rcx, [rcx+10h]
0x1800143dc  mov     edx, 3Bh ; ';'
0x1800143e1  mov     dword ptr [rsp+68h+pvPara], esi
0x1800143e5  call    WPP_SF_sD
0x1800143ea  mov     rdx, rbx; pPrevCertContext
0x1800143ed  mov     rcx, rdi; hCertStore
0x1800143f0  call    cs:__imp_CertEnumCertificatesInStore
0x1800143f6  mov     rbx, rax
0x1800143f9  test    rax, rax
0x1800143fc  jnz     short loc_18001438B
0x1800143fe  xor     ebx, ebx
0x180014400  jmp     short loc_18001443E
0x180014402  xor     ebx, ebx
0x180014404  mov     edx, r15d
0x180014407  call    WppTraceIndent
0x18001440c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014413  cmp     rcx, r13
0x180014416  jz      short loc_18001443E
0x180014418  test    byte ptr [rcx+1Ch], 1
0x18001441c  jz      short loc_18001443E
0x18001441e  cmp     byte ptr [rcx+19h], 4
0x180014422  jb      short loc_18001443E
0x180014424  mov     r9, cs:WPP_pszIndent
0x18001442b  lea     edx, [rbx+3Ch]
0x18001442e  mov     rcx, [rcx+10h]
0x180014432  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014439  call    WPP_SF_s
0x18001443e  lea     rcx, g_csSessionList; lpCriticalSection
0x180014445  call    cs:__imp_LeaveCriticalSection
0x18001444b  test    rdi, rdi
0x18001444e  jz      short loc_18001445B
0x180014450  xor     edx, edx; dwFlags
0x180014452  mov     rcx, rdi; hCertStore
0x180014455  call    cs:__imp_CertCloseStore
0x18001445b  test    rbp, rbp
0x18001445e  jz      short loc_18001446B
0x180014460  xor     edx, edx; dwFlags
0x180014462  mov     rcx, rbp; hCertStore
0x180014465  call    cs:__imp_CertCloseStore
0x18001446b  test    r14d, r14d
0x18001446e  jz      short loc_180014476
0x180014470  call    cs:__imp_RevertToSelf
0x180014476  mov     edx, r15d
0x180014479  call    WppTraceIndent
0x18001447e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014485  cmp     rcx, r13
0x180014488  jz      short loc_1800144B6
0x18001448a  test    byte ptr [rcx+1Ch], 1
0x18001448e  jz      short loc_1800144B6
0x180014490  cmp     byte ptr [rcx+19h], 5
0x180014494  jb      short loc_1800144B6
0x180014496  mov     r9, cs:WPP_pszIndent
0x18001449d  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800144a4  mov     rcx, [rcx+10h]
0x1800144a8  mov     edx, 3Dh ; '='
0x1800144ad  mov     dword ptr [rsp+68h+pvPara], ebx
0x1800144b1  call    WPP_SF_sD
0x1800144b6  mov     eax, ebx
0x1800144b8  add     rsp, 30h
0x1800144bc  pop     r15
0x1800144be  pop     r14
0x1800144c0  pop     r13
0x1800144c2  pop     rdi
0x1800144c3  pop     rsi
0x1800144c4  pop     rbp
0x1800144c5  pop     rbx
0x1800144c6  retn
```
