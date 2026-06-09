# I_ReaderListBuildCredFromCertContext

- ea: `0x180002aa0`
- end: `0x180002de4`
- name: `I_ReaderListBuildCredFromCertContext`
- size: `836`
- prototype: `__int64 __fastcall(__int64, const CERT_CONTEXT *, _WORD *, int, _QWORD *)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000b09c`
- `0x18001f548`
- `0x18001f9ec`
- `0x1800205c4`

## callees

- `0x180001570`
- `0x1800019d8`
- `0x180001c98`
- `0x180001e90`
- `0x180002aa0`
- `0x180004600`
- `0x180008bc0`
- `0x18000cce0`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002bc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002bc0`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180002dca`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180002dca`

## pseudocode

```c
__int64 __fastcall I_ReaderListBuildCredFromCertContext(
        __int64 a1,
        const CERT_CONTEXT *a2,
        _WORD *a3,
        int a4,
        _QWORD *a5)
{
  unsigned int UpnFromCert; // esi
  _DWORD *v10; // rax
  __int64 v11; // rcx
  _DWORD *v12; // r14
  STRSAFE_LPSTR v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // r8
  _WORD *v17; // rax
  __int64 v18; // rcx
  _WORD *v19; // rdx
  unsigned __int64 v20; // rbx
  __int64 v22; // rcx
  _WORD *v23; // rax
  __int64 v24; // rcx
  STRSAFE_LPSTR v25; // rcx
  int v26; // edx
  __int64 v27; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  UpnFromCert = 8;
  v10 = HeapAlloc(hHeap, 8u, 0x70u);
  v12 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x70u);
    v14 = -1;
    v15 = -1;
    while ( a3[++v15] != 0 )
      ;
    v17 = HeapAlloc(hHeap, 8u, 2 * v15 + 2);
    *(_QWORD *)v12 = v17;
    v19 = v17;
    if ( !v17 )
    {
      WppTraceIndent(v18, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_22;
    }
    do
      ++v14;
    while ( a3[v14] );
    v20 = v14 + 1;
    if ( v20 )
    {
      if ( v20 <= 0x7FFFFFFF )
      {
        v22 = 2147483646;
        do
        {
          if ( !v22 )
            break;
          if ( !*a3 )
            break;
          *v19++ = *a3++;
          --v22;
          --v20;
        }
        while ( v20 );
        v23 = v19 - 1;
        if ( v20 )
          v23 = v19;
        *v23 = 0;
        if ( v20 )
        {
          v12[2] = a4;
          UpnFromCert = I_GetUpnFromCert(a2, v12 + 6, *(unsigned int *)(a1 + 12));
          if ( UpnFromCert )
          {
            WppTraceIndent(v24, 2);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              || (WPP_GLOBAL_Control[28] & 1) == 0
              || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
            {
              goto LABEL_22;
            }
            v26 = 66;
          }
          else
          {
            UpnFromCert = I_GetCommonNameFromCert(a2);
            if ( !UpnFromCert )
            {
              I_GetTemplateInfoFromCert(a2, v12 + 8, v12 + 10);
              I_GetPinInfoFromCertContext(a2);
              I_GetCertificate_UPN_DN_Hash(a2, v12);
              *((_QWORD *)v12 + 6) = CertDuplicateCertificateContext(a2);
              *a5 = v12;
              goto LABEL_23;
            }
            WppTraceIndent(v27, 2);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              || (WPP_GLOBAL_Control[28] & 1) == 0
              || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
            {
              goto LABEL_22;
            }
            v26 = 67;
          }
          WPP_SF_sD(
            *((_QWORD *)v25 + 2),
            v26,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            UpnFromCert);
LABEL_22:
          I_FreeCredListItem(v12);
          goto LABEL_23;
        }
      }
      else
      {
        *v17 = 0;
      }
    }
    UpnFromCert = 122;
    goto LABEL_22;
  }
  WppTraceIndent(v11, 2);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
LABEL_23:
  WppTraceIndent(v13, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      UpnFromCert);
  }
  return UpnFromCert;
}

```

## disassembly

```asm
0x180002aa0  push    rsi
0x180002aa2  sub     rsp, 50h
0x180002aa6  mov     [rsp+58h+arg_8], rbp
0x180002aab  mov     rbp, rdx
0x180002aae  mov     [rsp+58h+arg_10], rdi
0x180002ab3  xor     edx, edx
0x180002ab5  mov     [rsp+58h+var_10], r12
0x180002aba  mov     rdi, r8
0x180002abd  mov     [rsp+58h+var_18], r13
0x180002ac2  mov     r13, rcx
0x180002ac5  mov     [rsp+58h+var_20], r14
0x180002aca  mov     [rsp+58h+var_28], r15
0x180002acf  mov     r15d, r9d
0x180002ad2  call    WppTraceIndent
0x180002ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ade  lea     r12, WPP_GLOBAL_Control
0x180002ae5  cmp     rcx, r12
0x180002ae8  jz      short loc_180002B12
0x180002aea  test    byte ptr [rcx+1Ch], 2
0x180002aee  jz      short loc_180002B12
0x180002af0  cmp     byte ptr [rcx+19h], 5
0x180002af4  jb      short loc_180002B12
0x180002af6  mov     r9, cs:WPP_pszIndent
0x180002afd  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180002b04  mov     rcx, [rcx+10h]
0x180002b08  mov     edx, 3Fh ; '?'
0x180002b0d  call    WPP_SF_s
0x180002b12  mov     rcx, cs:hHeap; hHeap
0x180002b19  mov     esi, 8
0x180002b1e  mov     edx, esi; dwFlags
0x180002b20  mov     r8d, 70h ; 'p'; dwBytes
0x180002b26  call    cs:__imp_HeapAlloc
0x180002b2c  mov     r14, rax
0x180002b2f  test    rax, rax
0x180002b32  jnz     short loc_180002B83
0x180002b34  mov     edx, 2
0x180002b39  call    WppTraceIndent
0x180002b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b45  cmp     rcx, r12
0x180002b48  jz      loc_180002C41
0x180002b4e  test    byte ptr [rcx+1Ch], 1
0x180002b52  jz      loc_180002C41
0x180002b58  cmp     byte ptr [rcx+19h], 2
0x180002b5c  jb      loc_180002C41
0x180002b62  mov     r9, cs:WPP_pszIndent
0x180002b69  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180002b70  mov     rcx, [rcx+10h]
0x180002b74  mov     edx, 40h ; '@'
0x180002b79  call    WPP_SF_s
0x180002b7e  jmp     loc_180002C41
0x180002b83  xor     edx, edx; Val
0x180002b85  mov     [rsp+58h+arg_0], rbx
0x180002b8a  mov     r8d, 70h ; 'p'; Size
0x180002b90  mov     rcx, r14; void *
0x180002b93  call    memset_0
0x180002b98  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002b9f  mov     r8, rbx
0x180002ba2  cmp     word ptr [rdi+r8*2+2], 0
0x180002ba9  lea     r8, [r8+1]
0x180002bad  jnz     short loc_180002BA2
0x180002baf  mov     rcx, cs:hHeap; hHeap
0x180002bb6  lea     r8, ds:2[r8*2]; dwBytes
0x180002bbe  mov     edx, esi; dwFlags
0x180002bc0  call    cs:__imp_HeapAlloc
0x180002bc6  mov     [r14], rax
0x180002bc9  mov     rdx, rax
0x180002bcc  test    rax, rax
0x180002bcf  jnz     short loc_180002C11
0x180002bd1  mov     edx, 2
0x180002bd6  call    WppTraceIndent
0x180002bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002be2  cmp     rcx, r12
0x180002be5  jz      short loc_180002C34
0x180002be7  test    byte ptr [rcx+1Ch], 1
0x180002beb  jz      short loc_180002C34
0x180002bed  cmp     byte ptr [rcx+19h], 2
0x180002bf1  jb      short loc_180002C34
0x180002bf3  mov     r9, cs:WPP_pszIndent
0x180002bfa  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180002c01  mov     rcx, [rcx+10h]
0x180002c05  mov     edx, 41h ; 'A'
0x180002c0a  call    WPP_SF_s
0x180002c0f  jmp     short loc_180002C34
0x180002c11  inc     rbx
0x180002c14  cmp     word ptr [rdi+rbx*2], 0
0x180002c19  jnz     short loc_180002C11
0x180002c1b  add     rbx, 1
0x180002c1f  jz      short loc_180002C2F
0x180002c21  cmp     rbx, 7FFFFFFFh
0x180002c28  jbe     short loc_180002CA9
0x180002c2a  xor     ecx, ecx
0x180002c2c  mov     [rax], cx
0x180002c2f  mov     esi, 7Ah ; 'z'
0x180002c34  mov     rcx, r14; lpMem
0x180002c37  call    I_FreeCredListItem
0x180002c3c  mov     rbx, [rsp+58h+arg_0]
0x180002c41  mov     edx, 1
0x180002c46  call    WppTraceIndent
0x180002c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c52  mov     r15, [rsp+58h+var_28]
0x180002c57  cmp     rcx, r12
0x180002c5a  mov     r12, [rsp+58h+var_10]
0x180002c5f  mov     r14, [rsp+58h+var_20]
0x180002c64  mov     r13, [rsp+58h+var_18]
0x180002c69  mov     rdi, [rsp+58h+arg_10]
0x180002c6e  mov     rbp, [rsp+58h+arg_8]
0x180002c73  jz      short loc_180002CA1
0x180002c75  test    byte ptr [rcx+1Ch], 2
0x180002c79  jz      short loc_180002CA1
0x180002c7b  cmp     byte ptr [rcx+19h], 5
0x180002c7f  jb      short loc_180002CA1
0x180002c81  mov     r9, cs:WPP_pszIndent
0x180002c88  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180002c8f  mov     rcx, [rcx+10h]
0x180002c93  mov     edx, 44h ; 'D'
0x180002c98  mov     [rsp+58h+var_38], esi
0x180002c9c  call    WPP_SF_sD
0x180002ca1  mov     eax, esi
0x180002ca3  add     rsp, 50h
0x180002ca7  pop     rsi
0x180002ca8  retn
0x180002ca9  mov     ecx, 7FFFFFFEh
0x180002cae  test    rcx, rcx
0x180002cb1  jz      short loc_180002CCF
0x180002cb3  movzx   eax, word ptr [rdi]
0x180002cb6  test    ax, ax
0x180002cb9  jz      short loc_180002CCF
0x180002cbb  mov     [rdx], ax
0x180002cbe  add     rdi, 2
0x180002cc2  add     rdx, 2
0x180002cc6  dec     rcx
0x180002cc9  sub     rbx, 1
0x180002ccd  jnz     short loc_180002CAE
0x180002ccf  test    rbx, rbx
0x180002cd2  lea     rax, [rdx-2]
0x180002cd6  cmovnz  rax, rdx
0x180002cda  xor     ecx, ecx
0x180002cdc  mov     [rax], cx
0x180002cdf  test    rbx, rbx
0x180002ce2  jz      loc_180002C2F
0x180002ce8  mov     [r14+8], r15d
0x180002cec  lea     rdx, [r14+18h]
0x180002cf0  mov     r8d, [r13+0Ch]
0x180002cf4  mov     rcx, rbp
0x180002cf7  call    I_GetUpnFromCert
0x180002cfc  mov     esi, eax
0x180002cfe  test    eax, eax
0x180002d00  jz      short loc_180002D55
0x180002d02  mov     edx, 2
0x180002d07  call    WppTraceIndent
0x180002d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d13  cmp     rcx, r12
0x180002d16  jz      loc_180002C34
0x180002d1c  test    byte ptr [rcx+1Ch], 1
0x180002d20  jz      loc_180002C34
0x180002d26  cmp     byte ptr [rcx+19h], 2
0x180002d2a  jb      loc_180002C34
0x180002d30  mov     edx, 42h ; 'B'
0x180002d35  mov     r9, cs:WPP_pszIndent
0x180002d3c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180002d43  mov     rcx, [rcx+10h]
0x180002d47  mov     [rsp+58h+var_38], esi
0x180002d4b  call    WPP_SF_sD
0x180002d50  jmp     loc_180002C34
0x180002d55  lea     rdx, [r14+10h]
0x180002d59  mov     rcx, rbp; pCertContext
0x180002d5c  call    I_GetCommonNameFromCert
0x180002d61  mov     esi, eax
0x180002d63  test    eax, eax
0x180002d65  jz      short loc_180002D9C
0x180002d67  mov     edx, 2
0x180002d6c  call    WppTraceIndent
0x180002d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d78  cmp     rcx, r12
0x180002d7b  jz      loc_180002C34
0x180002d81  test    byte ptr [rcx+1Ch], 1
0x180002d85  jz      loc_180002C34
0x180002d8b  cmp     byte ptr [rcx+19h], 2
0x180002d8f  jb      loc_180002C34
0x180002d95  mov     edx, 43h ; 'C'
0x180002d9a  jmp     short loc_180002D35
0x180002d9c  lea     r8, [r14+28h]
0x180002da0  mov     rcx, rbp
0x180002da3  lea     rdx, [r14+20h]
0x180002da7  call    I_GetTemplateInfoFromCert
0x180002dac  lea     r8, [r14+40h]
0x180002db0  mov     rcx, rbp; pCertContext
0x180002db3  lea     rdx, [r14+38h]
0x180002db7  call    I_GetPinInfoFromCertContext
0x180002dbc  mov     rdx, r14
0x180002dbf  mov     rcx, rbp
0x180002dc2  call    I_GetCertificate_UPN_DN_Hash
0x180002dc7  mov     rcx, rbp; pCertContext
0x180002dca  call    cs:__imp_CertDuplicateCertificateContext
0x180002dd0  mov     [r14+30h], rax
0x180002dd4  mov     rax, [rsp+58h+arg_20]
0x180002ddc  mov     [rax], r14
0x180002ddf  jmp     loc_180002C3C
```
