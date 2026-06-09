# CertPropRemoveRootCertificatesPerReaderList

- ea: `0x180014a30`
- end: `0x180014c97`
- name: `CertPropRemoveRootCertificatesPerReaderList`
- size: `615`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800010c4`
- `0x1800103f0`

## callees

- `0x180004600`
- `0x18000e28c`
- `0x180014a30`
- `0x180017a9c`
- `0x180018b58`
- `0x180018bb4`
- `0x1800214a8`
- `0x180021848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014bda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014bda`
- `CRYPT32!CertCloseStore` at `0x180014c3b`
- `CRYPT32!CertCloseStore` at `0x180014c3b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180014acb`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180014bff`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180014acb`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180014bff`
- `CRYPT32!CertFreeCertificateContext` at `0x180014c19`
- `CRYPT32!CertFreeCertificateContext` at `0x180014c19`

## pseudocode

```c
__int64 __fastcall CertPropRemoveRootCertificatesPerReaderList(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  STRSAFE_LPSTR v5; // rcx
  __int64 v6; // rdx
  const CERT_CONTEXT *v7; // rbx
  int v8; // r15d
  BYTE *v9; // rsi
  int v10; // r11d
  unsigned __int128 v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // r10
  __int64 v14; // rcx
  LPVOID lpMem[7]; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+80h] [rbp+18h] BYREF
  HCERTSTORE hCertStore; // [rsp+88h] [rbp+20h] BYREF

  v2 = 0;
  hCertStore = 0;
  lpMem[0] = 0;
  v17 = 0;
  WppTraceIndent(a1, 2);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  if ( g_RootsCleanupOption )
  {
    v2 = RootInfoOpenVirtualStore(*(_DWORD *)(a1 + 576), &hCertStore);
    if ( !v2 )
    {
      v7 = CertEnumCertificatesInStore(hCertStore, 0);
      if ( v7 )
      {
        while ( 1 )
        {
          v2 = RootInfoGet((__int64)v5, v6, v7, lpMem, (unsigned int *)&v17);
          if ( v2 )
            break;
          v8 = v17;
          v9 = (BYTE *)lpMem[0];
          v10 = 0;
          v11 = (unsigned int)v17 * (unsigned __int128)0xAAAAAAAAAAAAAAABuLL;
          v12 = 0;
          v13 = (unsigned int)v17 / 0x18uLL;
          if ( v13 )
          {
            do
            {
              *(_QWORD *)&v11 = a2;
              if ( !a2 )
                goto LABEL_17;
              *((_QWORD *)&v11 + 1) = 24 * v12;
              do
              {
                v14 = *(_QWORD *)(v11 + 24) - *(_QWORD *)&v9[*((_QWORD *)&v11 + 1)];
                if ( !v14 )
                  v14 = *(_QWORD *)(v11 + 32) - *(_QWORD *)&v9[*((_QWORD *)&v11 + 1) + 8];
                if ( !v14 )
                  break;
                *(_QWORD *)&v11 = *(_QWORD *)(v11 + 240);
              }
              while ( (_QWORD)v11 );
              if ( !(_QWORD)v11 )
              {
LABEL_17:
                v14 = 3 * v12;
                if ( *(_QWORD *)&v9[24 * v12 + 16] == *(_QWORD *)(a1 + 592) )
                {
                  *(_OWORD *)&v9[24 * v12] = 0;
                  *(_QWORD *)&v9[24 * v12 + 16] = 0;
                  ++v10;
                }
              }
              v12 = (unsigned int)(v12 + 1);
            }
            while ( (unsigned int)v12 < v13 );
            if ( v10 )
            {
              if ( v10 == v13 )
              {
                v2 = CertPropDeleteRootCertFromStore(v7, *(HANDLE *)(a1 + 416));
                if ( v2 )
                  goto LABEL_26;
                v7 = 0;
              }
              else
              {
                RootInfoSet(v14, *((__int64 *)&v11 + 1), v7, v9, v8);
              }
            }
          }
          HeapFree(g_hHeap, 0, v9);
          lpMem[0] = 0;
          v17 = 0;
          v7 = CertEnumCertificatesInStore(hCertStore, v7);
          if ( !v7 )
          {
LABEL_26:
            if ( !v7 )
              goto LABEL_28;
            break;
          }
        }
        CertFreeCertificateContext(v7);
      }
    }
LABEL_28:
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
  }
  WppTraceIndent(v5, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180014a30  mov     rax, rsp
0x180014a33  mov     [rax+8], rbx
0x180014a37  push    rsi
0x180014a38  push    rdi
0x180014a39  push    r12
0x180014a3b  push    r14
0x180014a3d  push    r15
0x180014a3f  sub     rsp, 40h
0x180014a43  xor     edi, edi
0x180014a45  mov     r12, rdx
0x180014a48  mov     r14, rcx
0x180014a4b  mov     [rax+20h], rdi
0x180014a4f  mov     [rax-38h], rdi
0x180014a53  mov     [rax+18h], edi
0x180014a56  lea     edx, [rdi+2]
0x180014a59  call    WppTraceIndent
0x180014a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a65  lea     rbx, WPP_GLOBAL_Control
0x180014a6c  cmp     rcx, rbx
0x180014a6f  jz      short loc_180014A97
0x180014a71  test    byte ptr [rcx+1Ch], 1
0x180014a75  jz      short loc_180014A97
0x180014a77  cmp     byte ptr [rcx+19h], 4
0x180014a7b  jb      short loc_180014A97
0x180014a7d  mov     r9, cs:WPP_pszIndent
0x180014a84  lea     edx, [rdi+0Ch]
0x180014a87  mov     rcx, [rcx+10h]
0x180014a8b  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014a92  call    WPP_SF_s
0x180014a97  cmp     cs:g_RootsCleanupOption, edi
0x180014a9d  jz      loc_180014C41
0x180014aa3  mov     ecx, [r14+240h]
0x180014aaa  lea     rdx, [rsp+68h+hCertStore]
0x180014ab2  call    RootInfoOpenVirtualStore
0x180014ab7  mov     edi, eax
0x180014ab9  test    eax, eax
0x180014abb  jnz     loc_180014C26
0x180014ac1  mov     rcx, [rsp+68h+hCertStore]; hCertStore
0x180014ac9  xor     edx, edx; pPrevCertContext
0x180014acb  call    cs:__imp_CertEnumCertificatesInStore
0x180014ad1  mov     rbx, rax
0x180014ad4  test    rax, rax
0x180014ad7  jz      loc_180014C1F
0x180014add  lea     rax, [rsp+68h+arg_10]
0x180014ae5  mov     r8, rbx
0x180014ae8  lea     r9, [rsp+68h+lpMem]
0x180014aed  mov     [rsp+68h+var_48], rax
0x180014af2  call    RootInfoGet
0x180014af7  mov     edi, eax
0x180014af9  test    eax, eax
0x180014afb  jnz     loc_180014C16
0x180014b01  mov     r15d, [rsp+68h+arg_10]
0x180014b09  mov     rax, 0AAAAAAAAAAAAAAABh
0x180014b13  mov     rsi, [rsp+68h+lpMem]
0x180014b18  xor     r11d, r11d
0x180014b1b  mul     r15
0x180014b1e  xor     r9d, r9d
0x180014b21  mov     r10, rdx
0x180014b24  shr     r10, 4
0x180014b28  test    r10, r10
0x180014b2b  jz      loc_180014BCE
0x180014b31  mov     rax, r12
0x180014b34  test    r12, r12
0x180014b37  jz      short loc_180014B6A
0x180014b39  lea     rdx, [r9+r9*2]
0x180014b3d  shl     rdx, 3
0x180014b41  mov     rcx, [rax+18h]
0x180014b45  sub     rcx, [rdx+rsi]
0x180014b49  jnz     short loc_180014B54
0x180014b4b  mov     rcx, [rax+20h]
0x180014b4f  sub     rcx, [rdx+rsi+8]
0x180014b54  test    rcx, rcx
0x180014b57  jz      short loc_180014B65
0x180014b59  mov     rax, [rax+0F0h]
0x180014b60  test    rax, rax
0x180014b63  jnz     short loc_180014B41
0x180014b65  test    rax, rax
0x180014b68  jnz     short loc_180014B8D
0x180014b6a  lea     rcx, [r9+r9*2]
0x180014b6e  mov     rax, [rsi+rcx*8+10h]
0x180014b73  cmp     rax, [r14+250h]
0x180014b7a  jnz     short loc_180014B8D
0x180014b7c  xor     eax, eax
0x180014b7e  xorps   xmm0, xmm0
0x180014b81  movups  xmmword ptr [rsi+rcx*8], xmm0
0x180014b85  mov     [rsi+rcx*8+10h], rax
0x180014b8a  inc     r11d
0x180014b8d  inc     r9d
0x180014b90  mov     eax, r9d
0x180014b93  cmp     rax, r10
0x180014b96  jb      short loc_180014B31
0x180014b98  test    r11d, r11d
0x180014b9b  jz      short loc_180014BCE
0x180014b9d  mov     eax, r11d
0x180014ba0  cmp     rax, r10
0x180014ba3  jnz     short loc_180014BBE
0x180014ba5  mov     rdx, [r14+1A0h]; Token
0x180014bac  mov     rcx, rbx; pCertContext
0x180014baf  call    CertPropDeleteRootCertFromStore
0x180014bb4  mov     edi, eax
0x180014bb6  test    eax, eax
0x180014bb8  jnz     short loc_180014C11
0x180014bba  xor     ebx, ebx
0x180014bbc  jmp     short loc_180014BCE
0x180014bbe  mov     r9, rsi
0x180014bc1  mov     dword ptr [rsp+68h+var_48], r15d
0x180014bc6  mov     r8, rbx
0x180014bc9  call    RootInfoSet
0x180014bce  mov     rcx, cs:g_hHeap; hHeap
0x180014bd5  mov     r8, rsi; lpMem
0x180014bd8  xor     edx, edx; dwFlags
0x180014bda  call    cs:__imp_HeapFree
0x180014be0  mov     rcx, [rsp+68h+hCertStore]; hCertStore
0x180014be8  mov     rdx, rbx; pPrevCertContext
0x180014beb  mov     [rsp+68h+lpMem], 0
0x180014bf4  mov     [rsp+68h+arg_10], 0
0x180014bff  call    cs:__imp_CertEnumCertificatesInStore
0x180014c05  mov     rbx, rax
0x180014c08  test    rax, rax
0x180014c0b  jnz     loc_180014ADD
0x180014c11  test    rbx, rbx
0x180014c14  jz      short loc_180014C1F
0x180014c16  mov     rcx, rbx; pCertContext
0x180014c19  call    cs:__imp_CertFreeCertificateContext
0x180014c1f  lea     rbx, WPP_GLOBAL_Control
0x180014c26  cmp     [rsp+68h+hCertStore], 0
0x180014c2f  jz      short loc_180014C41
0x180014c31  mov     rcx, [rsp+68h+hCertStore]; hCertStore
0x180014c39  xor     edx, edx; dwFlags
0x180014c3b  call    cs:__imp_CertCloseStore
0x180014c41  mov     edx, 2
0x180014c46  call    WppTraceIndent
0x180014c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c52  cmp     rcx, rbx
0x180014c55  jz      short loc_180014C83
0x180014c57  test    byte ptr [rcx+1Ch], 1
0x180014c5b  jz      short loc_180014C83
0x180014c5d  cmp     byte ptr [rcx+19h], 4
0x180014c61  jb      short loc_180014C83
0x180014c63  mov     r9, cs:WPP_pszIndent
0x180014c6a  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014c71  mov     rcx, [rcx+10h]
0x180014c75  mov     edx, 0Dh
0x180014c7a  mov     dword ptr [rsp+68h+var_48], edi
0x180014c7e  call    WPP_SF_sD
0x180014c83  mov     rbx, [rsp+68h+arg_0]
0x180014c88  mov     eax, edi
0x180014c8a  add     rsp, 40h
0x180014c8e  pop     r15
0x180014c90  pop     r14
0x180014c92  pop     r12
0x180014c94  pop     rdi
0x180014c95  pop     rsi
0x180014c96  retn
```
