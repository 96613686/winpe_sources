# I_GetDescriptorFromAndCombiner

- ea: `0x18001d7b8`
- end: `0x18001dc06`
- name: `I_GetDescriptorFromAndCombiner`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005a18`

## callees

- `0x180005f90`
- `0x1800090e0`
- `0x18000e120`
- `0x180019de4`
- `0x18001d7b8`
- `0x18001f175`
- `0x18001f1b0`

## import_xrefs

- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001d8cb`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001d9fe`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001da4e`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001d8cb`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001d9fe`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18001da4e`

## string_xrefs

- `0x18001db37`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18001dbb7`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall I_GetDescriptorFromAndCombiner(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  bool v12; // cc
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int RecipientIdString; // eax
  HLOCAL *v20; // r14
  _DWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdi
  HLOCAL v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rcx
  HLOCAL v28; // rcx
  HLOCAL v29; // rcx
  HLOCAL v30; // rcx
  HLOCAL v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33[2]; // [rsp+48h] [rbp-B8h] BYREF
  __m256i *v34; // [rsp+50h] [rbp-B0h]
  __m256i v35; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem[8]; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v37[8]; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v38[8]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v39[32]; // [rsp+140h] [rbp+40h] BYREF

  memset(&v35, 0, 28);
  v33[1] = 0;
  memset_0(v39, 0, sizeof(v39));
  v32 = 0;
  memset_0(hMem, 0, sizeof(hMem));
  memset_0(v37, 0, sizeof(v37));
  memset_0(v38, 0, sizeof(v38));
  *a3 = 0;
  if ( *(_DWORD *)a1 != 5 || *(_DWORD *)(a1 + 8) != 12 )
    goto LABEL_54;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(_QWORD *)v5 + 0x7DFEFBFEF9D4F5FALL;
  if ( *(_QWORD *)v5 == 0x82010401062B0A06uLL )
    v6 = *(unsigned int *)(v5 + 8) - 67193399LL;
  if ( v6 )
  {
LABEL_54:
    v8 = -2146893783;
    v9 = 1291;
    v10 = 2148073513LL;
    goto LABEL_55;
  }
  v7 = RtlAsn1DecodeAndAllocate(
         ASN1_NCRYPT_MODULE_HANDLE,
         29,
         1,
         *(_QWORD *)(a1 + 32),
         *(unsigned int *)(a1 + 24),
         0,
         &NCryptDefaultAllocPara,
         &v32);
  v8 = v7;
  if ( v7 )
  {
    v9 = 1307;
    v10 = v7;
LABEL_55:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c", v9);
    goto LABEL_56;
  }
  v11 = v32;
  v34 = &v35;
  v35.m256i_i64[1] = (__int64)v39;
  v35.m256i_i32[0] = 0;
  v35.m256i_i64[3] = 0;
  v35.m256i_i32[4] = 0;
  v12 = *((_DWORD *)v32 + 1) <= 8u;
  v33[0] = 1;
  if ( !v12 )
  {
    v8 = -2146893819;
    v9 = 1324;
    v10 = 2148073477LL;
    goto LABEL_55;
  }
  v13 = 0;
  while ( (unsigned int)v13 < *((_DWORD *)v11 + 1) )
  {
    v14 = v11[1];
    v15 = 160 * v13;
    if ( *(_DWORD *)(160 * v13 + v14) == 1 || *(_DWORD *)(160 * v13 + v14) == 2 )
    {
      if ( *(_DWORD *)(v15 + v14) == 1 )
      {
        v25 = v15 + v14 + 16;
      }
      else
      {
        if ( *(_DWORD *)(v15 + v14 + 144) != 1 )
        {
          v26 = 1350;
LABEL_41:
          v8 = -2146893783;
          v27 = 2148073513LL;
LABEL_42:
          DebugTraceError(
            v27,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
            v26);
          goto LABEL_52;
        }
        v25 = *(_QWORD *)(v15 + v14 + 152);
      }
      RecipientIdString = I_GetRecipientIdString(v25, v14, (wchar_t **)&v38[v13]);
      v8 = RecipientIdString;
      if ( RecipientIdString )
      {
        v26 = 1364;
        goto LABEL_35;
      }
      v23 = 4LL * (unsigned int)v13;
      v39[v23] = L"CERTIFICATE";
      v24 = v38[v13];
    }
    else
    {
      if ( *(_DWORD *)(160 * v13 + v14) != 3 )
      {
        v26 = 1438;
        goto LABEL_41;
      }
      v16 = *(_QWORD *)(v15 + v14 + 40);
      if ( !v16 || *(_DWORD *)v16 != 11 )
        goto LABEL_37;
      v17 = *(_QWORD *)(v16 + 8);
      v18 = *(_QWORD *)v17 + 0x7DFEFBFEF9D4F6FALL;
      if ( *(_QWORD *)v17 == 0x82010401062B0906uLL )
      {
        v18 = *(unsigned __int16 *)(v17 + 8) - 18999LL;
        if ( *(_WORD *)(v17 + 8) == 18999 )
          v18 = *(unsigned __int8 *)(v17 + 10) - 1LL;
      }
      if ( v18 )
      {
LABEL_37:
        v26 = 1382;
        goto LABEL_41;
      }
      RecipientIdString = RtlAsn1DecodeAndAllocate(
                            ASN1_NCRYPT_MODULE_HANDLE,
                            1,
                            2097153,
                            *(_QWORD *)(v16 + 24),
                            *(unsigned int *)(v16 + 16),
                            0,
                            &NCryptDefaultAllocPara,
                            &hMem[v13]);
      v8 = RecipientIdString;
      if ( RecipientIdString )
      {
        v26 = 1402;
        goto LABEL_35;
      }
      v20 = &v37[v13];
      RecipientIdString = RtlAsn1DecodeAndAllocate(
                            ASN1_NCRYPT_MODULE_HANDLE,
                            28,
                            1,
                            *((_QWORD *)hMem[v13] + 3),
                            *((unsigned int *)hMem[v13] + 4),
                            0,
                            &NCryptDefaultAllocPara,
                            v20);
      v8 = RecipientIdString;
      if ( RecipientIdString )
      {
        v26 = 1418;
        goto LABEL_35;
      }
      v21 = *v20;
      if ( *(_DWORD *)*v20 != 1 || (v22 = *((_QWORD *)v21 + 1), *(_DWORD *)v22 != 1) )
      {
        v26 = 1426;
        goto LABEL_41;
      }
      v23 = 4LL * (unsigned int)v13;
      v39[v23] = **(_QWORD **)(v22 + 8);
      v24 = *(HLOCAL *)(*(_QWORD *)(*((_QWORD *)v21 + 1) + 8LL) + 8LL);
    }
    v39[v23 + 1] = v24;
    v13 = (unsigned int)(v13 + 1);
    v11 = v32;
  }
  v35.m256i_i32[0] = v13;
  RecipientIdString = CNG_DuplicateDescriptor(v33, a3, 0);
  v8 = RecipientIdString;
  if ( RecipientIdString )
  {
    v26 = 1454;
LABEL_35:
    v27 = RecipientIdString;
    goto LABEL_42;
  }
  v8 = 0;
LABEL_52:
  while ( (_DWORD)v13 )
  {
    v13 = (unsigned int)(v13 - 1);
    v28 = hMem[v13];
    if ( v28 )
      I_DefaultExtrenalFree(v28);
    v29 = v37[v13];
    if ( v29 )
      I_DefaultExtrenalFree(v29);
    v30 = v38[v13];
    if ( v30 )
      I_DefaultExtrenalFree(v30);
  }
LABEL_56:
  if ( v32 )
    I_DefaultExtrenalFree(v32);
  return v8;
}

```

## disassembly

```asm
0x18001d7b8  mov     [rsp-8+arg_8], rbx
0x18001d7bd  mov     [rsp-8+arg_18], rsi
0x18001d7c2  push    rbp
0x18001d7c3  push    rdi
0x18001d7c4  push    r12
0x18001d7c6  push    r14
0x18001d7c8  push    r15
0x18001d7ca  lea     rbp, [rsp-150h]
0x18001d7d2  sub     rsp, 250h
0x18001d7d9  mov     rax, cs:__security_cookie
0x18001d7e0  xor     rax, rsp
0x18001d7e3  mov     [rbp+170h+var_30], rax
0x18001d7ea  xorps   xmm0, xmm0
0x18001d7ed  mov     r12, r8
0x18001d7f0  mov     rbx, rcx
0x18001d7f3  xor     eax, eax
0x18001d7f5  movups  [rsp+270h+var_218], xmm0
0x18001d7fa  xor     edx, edx; Val
0x18001d7fc  mov     [rsp+270h+var_224], eax
0x18001d800  mov     r8d, 100h; Size
0x18001d806  lea     rcx, [rbp+170h+var_130]; void *
0x18001d80a  movups  [rsp+270h+var_218+0Ch], xmm0
0x18001d80f  call    memset_0
0x18001d814  mov     edi, 40h ; '@'
0x18001d819  mov     [rsp+270h+var_230], 0
0x18001d822  mov     r8d, edi; Size
0x18001d825  lea     rcx, [rbp+170h+hMem]; void *
0x18001d829  xor     edx, edx; Val
0x18001d82b  call    memset_0
0x18001d830  mov     r8d, edi; Size
0x18001d833  lea     rcx, [rbp+170h+var_1B0]; void *
0x18001d837  xor     edx, edx; Val
0x18001d839  call    memset_0
0x18001d83e  mov     r8d, edi; Size
0x18001d841  lea     rcx, [rbp+170h+var_170]; void *
0x18001d845  xor     edx, edx; Val
0x18001d847  call    memset_0
0x18001d84c  mov     qword ptr [r12], 0
0x18001d854  cmp     dword ptr [rbx], 5
0x18001d857  jnz     loc_18001DBA7
0x18001d85d  cmp     dword ptr [rbx+8], 0Ch
0x18001d861  jnz     loc_18001DBA7
0x18001d867  mov     rax, [rbx+10h]
0x18001d86b  mov     rcx, [rax]
0x18001d86e  sub     rcx, cs:qword_180023328
0x18001d875  jnz     short loc_18001D883
0x18001d877  mov     ecx, [rax+8]
0x18001d87a  mov     eax, cs:dword_180023330
0x18001d880  sub     rcx, rax
0x18001d883  test    rcx, rcx
0x18001d886  jnz     loc_18001DBA7
0x18001d88c  mov     eax, [rbx+18h]
0x18001d88f  lea     rcx, [rsp+270h+var_230]
0x18001d894  mov     r9, [rbx+20h]
0x18001d898  mov     r14d, 1
0x18001d89e  mov     [rsp+270h+var_238], rcx
0x18001d8a3  mov     r8d, r14d
0x18001d8a6  lea     rcx, NCryptDefaultAllocPara
0x18001d8ad  mov     [rsp+270h+var_240], rcx
0x18001d8b2  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x18001d8b9  lea     edx, [r14+1Ch]
0x18001d8bd  mov     [rsp+270h+var_248], 0
0x18001d8c6  mov     [rsp+270h+var_250], rax
0x18001d8cb  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x18001d8d1  mov     ebx, eax
0x18001d8d3  test    eax, eax
0x18001d8d5  jz      short loc_18001D8E4
0x18001d8d7  mov     r9d, 51Bh
0x18001d8dd  mov     ecx, eax
0x18001d8df  jmp     loc_18001DBB7
0x18001d8e4  mov     rdx, [rsp+270h+var_230]
0x18001d8e9  lea     rax, [rsp+270h+var_218]
0x18001d8ee  mov     [rsp+270h+var_220], rax
0x18001d8f3  lea     rax, [rbp+170h+var_130]
0x18001d8f7  mov     qword ptr [rsp+270h+var_218+8], rax
0x18001d8fc  mov     dword ptr [rsp+270h+var_218], 0
0x18001d904  mov     [rsp+270h+var_200], 0
0x18001d90d  mov     [rsp+270h+var_208], 0
0x18001d915  cmp     dword ptr [rdx+4], 8
0x18001d919  mov     [rsp+270h+var_228], r14d
0x18001d91e  jbe     short loc_18001D935
0x18001d920  mov     ebx, 80090005h
0x18001d925  mov     r9d, 52Ch
0x18001d92b  mov     ecx, 80090005h
0x18001d930  jmp     loc_18001DBB7
0x18001d935  xor     esi, esi
0x18001d937  cmp     esi, [rdx+4]
0x18001d93a  jnb     loc_18001DB4C
0x18001d940  mov     rdx, [rdx+8]
0x18001d944  lea     rax, [rsi+rsi*4]
0x18001d948  shl     rax, 5
0x18001d94c  mov     edi, esi
0x18001d94e  mov     ecx, [rax+rdx]
0x18001d951  sub     ecx, 1
0x18001d954  jz      loc_18001DA95
0x18001d95a  sub     ecx, 1
0x18001d95d  jz      loc_18001DA95
0x18001d963  cmp     ecx, 1
0x18001d966  jnz     loc_18001DB17
0x18001d96c  mov     r9, [rax+rdx+28h]
0x18001d971  test    r9, r9
0x18001d974  jz      loc_18001DB0F
0x18001d97a  cmp     dword ptr [r9], 0Bh
0x18001d97e  jnz     loc_18001DB0F
0x18001d984  mov     rdx, [r9+8]
0x18001d988  mov     rax, 82010401062B0906h
0x18001d992  mov     rcx, [rdx]
0x18001d995  sub     rcx, rax
0x18001d998  jnz     short loc_18001D9B6
0x18001d99a  movzx   ecx, word ptr [rdx+8]
0x18001d99e  mov     eax, 4A37h
0x18001d9a3  movzx   eax, ax
0x18001d9a6  sub     rcx, rax
0x18001d9a9  jnz     short loc_18001D9B6
0x18001d9ab  movzx   ecx, byte ptr [rdx+0Ah]
0x18001d9af  movzx   eax, r14b
0x18001d9b3  sub     rcx, rax
0x18001d9b6  test    rcx, rcx
0x18001d9b9  jnz     loc_18001DB0F
0x18001d9bf  mov     eax, [r9+10h]
0x18001d9c3  lea     rcx, NCryptDefaultAllocPara
0x18001d9ca  mov     r9, [r9+18h]
0x18001d9ce  lea     r15, [rbp+170h+hMem]
0x18001d9d2  lea     r15, [r15+rsi*8]
0x18001d9d6  mov     r8d, 200001h
0x18001d9dc  mov     [rsp+270h+var_238], r15
0x18001d9e1  mov     edx, r14d
0x18001d9e4  mov     [rsp+270h+var_240], rcx
0x18001d9e9  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x18001d9f0  mov     [rsp+270h+var_248], 0
0x18001d9f9  mov     [rsp+270h+var_250], rax
0x18001d9fe  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x18001da04  mov     ebx, eax
0x18001da06  test    eax, eax
0x18001da08  jnz     loc_18001DB07
0x18001da0e  mov     r9, [r15]
0x18001da11  lea     rcx, NCryptDefaultAllocPara
0x18001da18  lea     r14, [rbp+170h+var_1B0]
0x18001da1c  lea     r14, [r14+rsi*8]
0x18001da20  mov     [rsp+270h+var_238], r14
0x18001da25  lea     edx, [rbx+1Ch]
0x18001da28  mov     eax, [r9+10h]
0x18001da2c  lea     r8d, [rbx+1]
0x18001da30  mov     r9, [r9+18h]
0x18001da34  mov     [rsp+270h+var_240], rcx
0x18001da39  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x18001da40  mov     [rsp+270h+var_248], 0
0x18001da49  mov     [rsp+270h+var_250], rax
0x18001da4e  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x18001da54  mov     ebx, eax
0x18001da56  test    eax, eax
0x18001da58  jnz     loc_18001DAFD
0x18001da5e  mov     rdx, [r14]
0x18001da61  lea     r14d, [rax+1]
0x18001da65  cmp     [rdx], r14d
0x18001da68  jnz     loc_18001DAF5
0x18001da6e  mov     rax, [rdx+8]
0x18001da72  cmp     [rax], r14d
0x18001da75  jnz     short loc_18001DAF5
0x18001da77  mov     rax, [rax+8]
0x18001da7b  shl     rdi, 5
0x18001da7f  mov     rcx, [rax]
0x18001da82  mov     [rbp+rdi+170h+var_130], rcx
0x18001da87  mov     rax, [rdx+8]
0x18001da8b  mov     rcx, [rax+8]
0x18001da8f  mov     rax, [rcx+8]
0x18001da93  jmp     short loc_18001DAE3
0x18001da95  cmp     [rax+rdx], r14d
0x18001da99  jnz     short loc_18001DAA4
0x18001da9b  lea     rcx, [rdx+10h]
0x18001da9f  add     rcx, rax
0x18001daa2  jmp     short loc_18001DAB6
0x18001daa4  cmp     [rax+rdx+90h], r14d
0x18001daac  jnz     short loc_18001DB27
0x18001daae  mov     rcx, [rax+rdx+98h]
0x18001dab6  lea     r14, [rbp+170h+var_170]
0x18001daba  lea     r14, [r14+rsi*8]
0x18001dabe  mov     r8, r14
0x18001dac1  call    I_GetRecipientIdString
0x18001dac6  mov     ebx, eax
0x18001dac8  test    eax, eax
0x18001daca  jnz     short loc_18001DB1F
0x18001dacc  lea     rax, aCertificate; "CERTIFICATE"
0x18001dad3  shl     rdi, 5
0x18001dad7  mov     [rbp+rdi+170h+var_130], rax
0x18001dadc  mov     rax, [r14]
0x18001dadf  lea     r14d, [rbx+1]
0x18001dae3  mov     [rbp+rdi+170h+var_128], rax
0x18001dae8  add     esi, r14d
0x18001daeb  mov     rdx, [rsp+270h+var_230]
0x18001daf0  jmp     loc_18001D937
0x18001daf5  mov     r9d, 592h
0x18001dafb  jmp     short loc_18001DB2D
0x18001dafd  mov     r9d, 58Ah
0x18001db03  mov     ecx, eax
0x18001db05  jmp     short loc_18001DB37
0x18001db07  mov     r9d, 57Ah
0x18001db0d  jmp     short loc_18001DB03
0x18001db0f  mov     r9d, 566h
0x18001db15  jmp     short loc_18001DB2D
0x18001db17  mov     r9d, 59Eh
0x18001db1d  jmp     short loc_18001DB2D
0x18001db1f  mov     r9d, 554h
0x18001db25  jmp     short loc_18001DB03
0x18001db27  mov     r9d, 546h
0x18001db2d  mov     ebx, 80090029h
0x18001db32  mov     ecx, 80090029h
0x18001db37  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001db3e  lea     rdx, aStatus; "Status"
0x18001db45  call    DebugTraceError
0x18001db4a  jmp     short loc_18001DBA1
0x18001db4c  xor     r8d, r8d
0x18001db4f  mov     dword ptr [rsp+270h+var_218], esi
0x18001db53  mov     rdx, r12
0x18001db56  lea     rcx, [rsp+270h+var_228]
0x18001db5b  call    CNG_DuplicateDescriptor
0x18001db60  mov     ebx, eax
0x18001db62  test    eax, eax
0x18001db64  jz      short loc_18001DB6E
0x18001db66  mov     r9d, 5AEh
0x18001db6c  jmp     short loc_18001DB03
0x18001db6e  xor     ebx, ebx
0x18001db70  jmp     short loc_18001DBA1
0x18001db72  dec     esi
0x18001db74  mov     rcx, [rbp+rsi*8+170h+hMem]; hMem
0x18001db79  test    rcx, rcx
0x18001db7c  jz      short loc_18001DB83
0x18001db7e  call    I_DefaultExtrenalFree
0x18001db83  mov     rcx, [rbp+rsi*8+170h+var_1B0]; hMem
0x18001db88  test    rcx, rcx
0x18001db8b  jz      short loc_18001DB92
0x18001db8d  call    I_DefaultExtrenalFree
0x18001db92  mov     rcx, [rbp+rsi*8+170h+var_170]; hMem
0x18001db97  test    rcx, rcx
0x18001db9a  jz      short loc_18001DBA1
0x18001db9c  call    I_DefaultExtrenalFree
0x18001dba1  test    esi, esi
0x18001dba3  jnz     short loc_18001DB72
0x18001dba5  jmp     short loc_18001DBCA
0x18001dba7  mov     ebx, 80090029h
0x18001dbac  mov     r9d, 50Bh
0x18001dbb2  mov     ecx, 80090029h
0x18001dbb7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001dbbe  lea     rdx, aStatus; "Status"
0x18001dbc5  call    DebugTraceError
0x18001dbca  mov     rcx, [rsp+270h+var_230]; hMem
0x18001dbcf  test    rcx, rcx
0x18001dbd2  jz      short loc_18001DBD9
0x18001dbd4  call    I_DefaultExtrenalFree
0x18001dbd9  mov     eax, ebx
0x18001dbdb  mov     rcx, [rbp+170h+var_30]
0x18001dbe2  xor     rcx, rsp; StackCookie
0x18001dbe5  call    __security_check_cookie
0x18001dbea  lea     r11, [rsp+270h+var_20]
0x18001dbf2  mov     rbx, [r11+38h]
0x18001dbf6  mov     rsi, [r11+48h]
0x18001dbfa  mov     rsp, r11
0x18001dbfd  pop     r15
0x18001dbff  pop     r14
0x18001dc01  pop     r12
0x18001dc03  pop     rdi
0x18001dc04  pop     rbp
0x18001dc05  retn
```
