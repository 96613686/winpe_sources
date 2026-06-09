# CertPropHandleNonRemovableCerts

- ea: `0x18000d588`
- end: `0x18000d78e`
- name: `CertPropHandleNonRemovableCerts`
- size: `518`
- prototype: `__int64 __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fe80`

## callees

- `0x180004600`
- `0x18000d588`
- `0x18000d7a0`
- `0x18000d7c0`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d76a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d76a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5a5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d5c7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d716`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d716`
- `CRYPT32!CertCloseStore` at `0x18000d77a`
- `CRYPT32!CertCloseStore` at `0x18000d77a`
- `CRYPT32!CertOpenStore` at `0x18000d60d`
- `CRYPT32!CertOpenStore` at `0x18000d670`
- `CRYPT32!CertOpenStore` at `0x18000d60d`
- `CRYPT32!CertOpenStore` at `0x18000d670`

## pseudocode

```c
__int64 __fastcall CertPropHandleNonRemovableCerts(unsigned int a1, int a2)
{
  unsigned int v4; // esi
  HCERTSTORE v5; // r14
  __int64 SessionNode; // rax
  __int64 v7; // rcx
  __int64 v8; // rbx
  DWORD LastError; // eax
  __int64 v10; // rcx
  char v11; // bl
  __int64 v12; // rcx
  __int64 v13; // rbx
  char v14; // al
  __int64 v15; // rcx

  v4 = 0;
  v5 = 0;
  EnterCriticalSection(&g_csSessionList);
  SessionNode = CertPropGetSessionNode(a1);
  v8 = SessionNode;
  if ( SessionNode )
  {
    if ( SetThreadToken(0, *(HANDLE *)(SessionNode + 416)) )
    {
      if ( a2 && !*(_DWORD *)(v8 + 616) )
      {
        CertOpenStore((LPCSTR)0xD, 0, 0, 0x10010u, L"Local NonRemovable Certificates");
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError )
        {
          WppTraceIndent(v10, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
              WPP_pszIndent,
              v11);
          }
        }
        v5 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x10000u, L"Local NonRemovable Certificates");
        if ( !v5 )
        {
          WppTraceIndent(v12, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
          {
            v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v14 = GetLastError();
            WPP_SF_sD(v13, 53, (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent, v14);
          }
        }
      }
      v4 = DeleteNonRemovableCertificatesFromUserStore(v5);
      if ( v4 )
      {
        WppTraceIndent(v15, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
            WPP_pszIndent,
            v4);
        }
      }
      RevertToSelf();
    }
  }
  else
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
    }
  }
  LeaveCriticalSection(&g_csSessionList);
  if ( v5 )
    CertCloseStore(v5, 0);
  return v4;
}

```

## disassembly

```asm
0x18000d588  push    rbx
0x18000d58a  push    rbp
0x18000d58b  push    rsi
0x18000d58c  push    r14
0x18000d58e  push    r15
0x18000d590  sub     rsp, 30h
0x18000d594  mov     ebx, ecx
0x18000d596  mov     r15d, edx
0x18000d599  lea     rcx, g_csSessionList; lpCriticalSection
0x18000d5a0  xor     esi, esi
0x18000d5a2  xor     r14d, r14d
0x18000d5a5  call    cs:__imp_EnterCriticalSection
0x18000d5ab  mov     ecx, ebx
0x18000d5ad  call    CertPropGetSessionNode
0x18000d5b2  mov     rbx, rax
0x18000d5b5  test    rax, rax
0x18000d5b8  jz      loc_18000D71E
0x18000d5be  mov     rdx, [rax+1A0h]; Token
0x18000d5c5  xor     ecx, ecx; Thread
0x18000d5c7  call    cs:__imp_SetThreadToken
0x18000d5cd  test    eax, eax
0x18000d5cf  jz      loc_18000D763
0x18000d5d5  lea     rbp, WPP_GLOBAL_Control
0x18000d5dc  test    r15d, r15d
0x18000d5df  jz      loc_18000D6C6
0x18000d5e5  cmp     [rbx+268h], esi
0x18000d5eb  jnz     loc_18000D6C6
0x18000d5f1  xor     edx, edx; dwEncodingType
0x18000d5f3  lea     r14, aLocalNonremova; "Local NonRemovable Certificates"
0x18000d5fa  mov     r9d, 10010h; dwFlags
0x18000d600  mov     [rsp+58h+pvPara], r14; pvPara
0x18000d605  xor     r8d, r8d; hCryptProv
0x18000d608  lea     esi, [rdx+0Dh]
0x18000d60b  mov     ecx, esi; lpszStoreProvider
0x18000d60d  call    cs:__imp_CertOpenStore
0x18000d613  call    cs:__imp_GetLastError
0x18000d619  mov     ebx, eax
0x18000d61b  test    eax, eax
0x18000d61d  jz      short loc_18000D65D
0x18000d61f  lea     edx, [rsi-0Bh]
0x18000d622  call    WppTraceIndent
0x18000d627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d62e  cmp     rcx, rbp
0x18000d631  jz      short loc_18000D65D
0x18000d633  test    byte ptr [rcx+1Ch], 1
0x18000d637  jz      short loc_18000D65D
0x18000d639  cmp     byte ptr [rcx+19h], 3
0x18000d63d  jb      short loc_18000D65D
0x18000d63f  mov     r9, cs:WPP_pszIndent
0x18000d646  lea     edx, [rsi+27h]
0x18000d649  mov     rcx, [rcx+10h]
0x18000d64d  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000d654  mov     dword ptr [rsp+58h+pvPara], ebx
0x18000d658  call    WPP_SF_sD
0x18000d65d  mov     r9d, 10000h; dwFlags
0x18000d663  mov     [rsp+58h+pvPara], r14; pvPara
0x18000d668  xor     r8d, r8d; hCryptProv
0x18000d66b  xor     edx, edx; dwEncodingType
0x18000d66d  mov     rcx, rsi; lpszStoreProvider
0x18000d670  call    cs:__imp_CertOpenStore
0x18000d676  mov     r14, rax
0x18000d679  test    rax, rax
0x18000d67c  jnz     short loc_18000D6C6
0x18000d67e  lea     edx, [rax+2]
0x18000d681  call    WppTraceIndent
0x18000d686  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d68d  cmp     rbx, rbp
0x18000d690  jz      short loc_18000D6C6
0x18000d692  test    byte ptr [rbx+1Ch], 1
0x18000d696  jz      short loc_18000D6C6
0x18000d698  cmp     byte ptr [rbx+19h], 3
0x18000d69c  jb      short loc_18000D6C6
0x18000d69e  mov     rbx, [rbx+10h]
0x18000d6a2  call    cs:__imp_GetLastError
0x18000d6a8  mov     r9, cs:WPP_pszIndent
0x18000d6af  lea     edx, [r14+35h]
0x18000d6b3  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000d6ba  mov     dword ptr [rsp+58h+pvPara], eax
0x18000d6be  mov     rcx, rbx
0x18000d6c1  call    WPP_SF_sD
0x18000d6c6  mov     rcx, r14; hCertStore
0x18000d6c9  call    DeleteNonRemovableCertificatesFromUserStore
0x18000d6ce  mov     esi, eax
0x18000d6d0  test    eax, eax
0x18000d6d2  jz      short loc_18000D716
0x18000d6d4  mov     edx, 2
0x18000d6d9  call    WppTraceIndent
0x18000d6de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6e5  cmp     rcx, rbp
0x18000d6e8  jz      short loc_18000D716
0x18000d6ea  test    byte ptr [rcx+1Ch], 1
0x18000d6ee  jz      short loc_18000D716
0x18000d6f0  cmp     byte ptr [rcx+19h], 2
0x18000d6f4  jb      short loc_18000D716
0x18000d6f6  mov     r9, cs:WPP_pszIndent
0x18000d6fd  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000d704  mov     rcx, [rcx+10h]
0x18000d708  mov     edx, 36h ; '6'
0x18000d70d  mov     dword ptr [rsp+58h+pvPara], esi
0x18000d711  call    WPP_SF_sD
0x18000d716  call    cs:__imp_RevertToSelf
0x18000d71c  jmp     short loc_18000D763
0x18000d71e  mov     edx, 2
0x18000d723  call    WppTraceIndent
0x18000d728  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d72f  lea     rbp, WPP_GLOBAL_Control
0x18000d736  cmp     rcx, rbp
0x18000d739  jz      short loc_18000D763
0x18000d73b  test    byte ptr [rcx+1Ch], 1
0x18000d73f  jz      short loc_18000D763
0x18000d741  cmp     byte ptr [rcx+19h], 4
0x18000d745  jb      short loc_18000D763
0x18000d747  mov     r9, cs:WPP_pszIndent
0x18000d74e  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000d755  mov     rcx, [rcx+10h]
0x18000d759  mov     edx, 37h ; '7'
0x18000d75e  call    WPP_SF_s
0x18000d763  lea     rcx, g_csSessionList; lpCriticalSection
0x18000d76a  call    cs:__imp_LeaveCriticalSection
0x18000d770  test    r14, r14
0x18000d773  jz      short loc_18000D780
0x18000d775  xor     edx, edx; dwFlags
0x18000d777  mov     rcx, r14; hCertStore
0x18000d77a  call    cs:__imp_CertCloseStore
0x18000d780  mov     eax, esi
0x18000d782  add     rsp, 30h
0x18000d786  pop     r15
0x18000d788  pop     r14
0x18000d78a  pop     rsi
0x18000d78b  pop     rbp
0x18000d78c  pop     rbx
0x18000d78d  retn
```
