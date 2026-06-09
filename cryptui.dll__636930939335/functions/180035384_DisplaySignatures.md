# DisplaySignatures

- ea: `0x180035384`
- end: `0x1800356e3`
- name: `DisplaySignatures`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180036160`

## callees

- `0x180001f72`
- `0x180035104`
- `0x180035384`
- `0x1800370b8`
- `0x180039994`
- `0x180039c10`
- `0x180039d5c`
- `0x180039f48`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800355b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800355b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800355e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800355e6`
- `CRYPT32!CertOpenStore` at `0x18003544a`
- `CRYPT32!CertOpenStore` at `0x180035621`
- `CRYPT32!CertOpenStore` at `0x18003544a`
- `CRYPT32!CertOpenStore` at `0x180035621`
- `CRYPT32!CertCloseStore` at `0x180035480`
- `CRYPT32!CertCloseStore` at `0x180035480`
- `CRYPT32!CryptMsgClose` at `0x180035686`
- `CRYPT32!CryptMsgClose` at `0x1800356a4`
- `CRYPT32!CryptMsgClose` at `0x180035686`
- `CRYPT32!CryptMsgClose` at `0x1800356a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DisplaySignatures(__int64 a1, _QWORD *a2, int a3)
{
  void **v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // r14
  void *v7; // rsi
  __int64 v8; // rax
  struct SIP_DISPATCH_INFO_ *v9; // r9
  void *pvPara; // rax
  void *v11; // r15
  void *v12; // rcx
  __int64 v13; // r15
  struct SIP_DISPATCH_INFO_ *v14; // r9
  void *Signature; // rax
  void *v16; // r14
  unsigned int v17; // edx
  int SecondarySignatures; // eax
  HLOCAL v19; // rax
  HLOCAL v20; // r15
  __int64 i; // r15
  __int64 v22; // rdx
  __int64 v23; // rbx
  void *v24; // rcx
  unsigned int v26; // [rsp+30h] [rbp-99h] BYREF
  void **v27; // [rsp+38h] [rbp-91h] BYREF
  HLOCAL v28; // [rsp+40h] [rbp-89h]
  struct SIP_SUBJECTINFO_ v29; // [rsp+50h] [rbp-79h] BYREF
  struct _GUID v30; // [rsp+D0h] [rbp+7h] BYREF

  v4 = 0;
  *(_QWORD *)&v30.Data1 = 0;
  v5 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  if ( a3 )
  {
    v6 = *(_QWORD *)(*a2 + 56LL);
    v7 = (void *)a2[3];
    v8 = a2[1];
    if ( *(_DWORD *)(v8 + 8) )
    {
      do
      {
        *(_QWORD *)(*a2 + 56LL) = *(_QWORD *)(*(_QWORD *)(v8 + 16) + 8 * v5);
        v30 = 0;
        memset_0(&v29, 0, sizeof(v29));
        pvPara = I_GetSignature(*(const unsigned __int16 **)(*(_QWORD *)(a2[1] + 16LL) + 8 * v5), &v29, &v30, v9);
        v11 = pvPara;
        if ( pvPara )
        {
          a2[3] = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, pvPara);
          DisplaySignature((unsigned int)v5, v11, *(wchar_t **)(*(_QWORD *)(a2[1] + 16LL) + 8 * v5));
          v12 = (void *)a2[3];
          if ( v12 != v7 )
            CertCloseStore(v12, 0);
        }
        v5 = (unsigned int)(v5 + 1);
        v8 = a2[1];
      }
      while ( (unsigned int)v5 < *(_DWORD *)(v8 + 8) );
    }
    *(_QWORD *)(*a2 + 56LL) = v6;
    a2[3] = v7;
    return std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(&v27);
  }
  v13 = *a2;
  if ( *(_DWORD *)a2[1] )
  {
    v30 = 0;
    memset_0(&v29, 0, sizeof(v29));
    Signature = I_GetSignature(*(const unsigned __int16 **)(v13 + 56), &v29, &v30, v14);
    DisplaySignature(0, Signature, 0);
    return std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(&v27);
  }
  if ( *(_WORD *)(v13 + 32) == 1 )
  {
    v16 = I_OpenBlob(0x10001u, *(unsigned __int8 **)(v13 + 48), *(_DWORD *)(v13 + 40));
    if ( !v16 )
      return std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(&v27);
    goto LABEL_26;
  }
  v16 = 0;
  if ( *(_WORD *)(v13 + 32) == 2 )
  {
    v16 = *(void **)(v13 + 40);
    DisplaySignature(0, v16, 0);
    SecondarySignatures = I_GetSecondarySignatures(v16, v17, (void ***)&v30, &v26);
    v4 = *(void ***)&v30.Data1;
    if ( SecondarySignatures < 0 )
    {
      LODWORD(v5) = v26;
    }
    else
    {
      if ( *(_QWORD *)&v30.Data1 )
      {
        std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(&v27);
        v27 = v4;
      }
      LODWORD(v5) = v26;
      if ( I_OrderSignatures(v4, v26) < 0 )
        goto LABEL_26;
      if ( !(_DWORD)v5 )
        goto LABEL_21;
      v19 = LocalAlloc(0x40u, 8LL * (unsigned int)(v5 + *(_DWORD *)(*a2 + 88LL)));
      v20 = v19;
      if ( v19 )
      {
        v28 = v19;
        memmove_0(v19, *(const void **)(*a2 + 96LL), 8LL * *(unsigned int *)(*a2 + 88LL));
        LocalFree(*(HLOCAL *)(*a2 + 96LL));
        v28 = 0;
        *(_QWORD *)(*a2 + 96LL) = v20;
LABEL_21:
        for ( i = 0; (unsigned int)i < (unsigned int)v5; DisplaySignature((unsigned int)i, v4[*(_QWORD *)&v30.Data1], 0) )
        {
          *(_QWORD *)&v30.Data1 = (unsigned int)i;
          *(_QWORD *)(*(_QWORD *)(*a2 + 96LL) + 8LL * *(unsigned int *)(*a2 + 88LL)) = CertOpenStore(
                                                                                         (LPCSTR)1,
                                                                                         0x10001u,
                                                                                         0,
                                                                                         0,
                                                                                         v4[i]);
          v22 = *(unsigned int *)(*a2 + 88LL);
          if ( !*(_QWORD *)(*(_QWORD *)(*a2 + 96LL) + 8 * v22) )
            break;
          *(_DWORD *)(*a2 + 88LL) = v22 + 1;
          i = (unsigned int)(i + 1);
        }
      }
    }
  }
LABEL_26:
  if ( *(_WORD *)(*a2 + 32LL) == 1 )
    CryptMsgClose(v16);
  if ( (_DWORD)v5 && v4 )
  {
    v23 = 0;
    do
    {
      v24 = v4[v23];
      if ( v24 )
        CryptMsgClose(v24);
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (unsigned int)v23 < (unsigned int)v5 );
  }
  return std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(&v27);
}

```

## disassembly

```asm
0x180035384  mov     [rsp-8+arg_10], rbx
0x180035389  push    rbp
0x18003538a  push    rsi
0x18003538b  push    rdi
0x18003538c  push    r12
0x18003538e  push    r13
0x180035390  push    r14
0x180035392  push    r15
0x180035394  lea     rbp, [rsp-27h]
0x180035399  sub     rsp, 0F0h
0x1800353a0  mov     rax, cs:__security_cookie
0x1800353a7  xor     rax, rsp
0x1800353aa  mov     [rbp+57h+var_40], rax
0x1800353ae  mov     rbx, rdx
0x1800353b1  mov     r13, rcx
0x1800353b4  xor     esi, esi
0x1800353b6  mov     qword ptr [rbp+57h+var_50.Data1], rsi
0x1800353ba  xor     edi, edi
0x1800353bc  mov     [rsp+120h+var_F0], edi
0x1800353c0  mov     [rsp+120h+var_E0], rsi
0x1800353c5  mov     [rsp+120h+var_E8], rdi
0x1800353ca  test    r8d, r8d
0x1800353cd  jz      loc_1800354A6
0x1800353d3  mov     rax, [rdx]
0x1800353d6  mov     r14, [rax+38h]
0x1800353da  mov     rsi, [rdx+18h]
0x1800353de  mov     rax, [rdx+8]
0x1800353e2  cmp     [rax+8], edi
0x1800353e5  jbe     loc_180035496
0x1800353eb  lea     r12d, [rdi+1]
0x1800353ef  mov     rax, [rax+10h]
0x1800353f3  mov     rcx, [rbx]
0x1800353f6  mov     rax, [rax+rdi*8]
0x1800353fa  mov     [rcx+38h], rax
0x1800353fe  xorps   xmm0, xmm0
0x180035401  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180035405  xor     edx, edx; Val
0x180035407  mov     r8d, 80h; Size
0x18003540d  lea     rcx, [rbp+57h+var_D0]; void *
0x180035411  call    memset_0
0x180035416  mov     rax, [rbx+8]
0x18003541a  mov     rcx, [rax+10h]
0x18003541e  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x180035422  lea     rdx, [rbp+57h+var_D0]; struct SIP_SUBJECTINFO_ *
0x180035426  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x18003542a  call    ?I_GetSignature@@YAPEAXPEBGPEAUSIP_SUBJECTINFO_@@PEAU_GUID@@PEAUSIP_DISPATCH_INFO_@@@Z; I_GetSignature(ushort const *,SIP_SUBJECTINFO_ *,_GUID *,SIP_DISPATCH_INFO_ *)
0x18003542f  mov     r15, rax
0x180035432  test    rax, rax
0x180035435  jz      short loc_180035486
0x180035437  mov     [rsp+120h+pvPara], rax; pvPara
0x18003543c  xor     r9d, r9d; dwFlags
0x18003543f  xor     r8d, r8d; hCryptProv
0x180035442  mov     edx, 10001h; dwEncodingType
0x180035447  mov     rcx, r12; lpszStoreProvider
0x18003544a  call    cs:__imp_CertOpenStore
0x180035450  mov     [rbx+18h], rax
0x180035454  mov     rcx, [rbx+8]
0x180035458  mov     rdx, [rcx+10h]
0x18003545c  mov     rcx, [rdx+rdi*8]
0x180035460  mov     [rsp+120h+pvPara], rcx; Str
0x180035465  mov     r9, r13
0x180035468  mov     r8, rbx
0x18003546b  mov     rdx, r15; hCryptMsg
0x18003546e  mov     ecx, edi; wParam
0x180035470  call    DisplaySignature
0x180035475  mov     rcx, [rbx+18h]; hCertStore
0x180035479  cmp     rcx, rsi
0x18003547c  jz      short loc_180035486
0x18003547e  xor     edx, edx; dwFlags
0x180035480  call    cs:__imp_CertCloseStore
0x180035486  add     edi, r12d
0x180035489  mov     rax, [rbx+8]
0x18003548d  cmp     edi, [rax+8]
0x180035490  jb      loc_1800353EF
0x180035496  mov     rax, [rbx]
0x180035499  mov     [rax+38h], r14
0x18003549d  mov     [rbx+18h], rsi
0x1800354a1  jmp     loc_1800356B1
0x1800354a6  mov     r15, [rdx]
0x1800354a9  mov     rax, [rdx+8]
0x1800354ad  cmp     dword ptr [rax], 0
0x1800354b0  jbe     short loc_1800354F9
0x1800354b2  xorps   xmm0, xmm0
0x1800354b5  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1800354b9  xor     edx, edx; Val
0x1800354bb  mov     r8d, 80h; Size
0x1800354c1  lea     rcx, [rbp+57h+var_D0]; void *
0x1800354c5  call    memset_0
0x1800354ca  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x1800354ce  lea     rdx, [rbp+57h+var_D0]; struct SIP_SUBJECTINFO_ *
0x1800354d2  mov     rcx, [r15+38h]; unsigned __int16 *
0x1800354d6  call    ?I_GetSignature@@YAPEAXPEBGPEAUSIP_SUBJECTINFO_@@PEAU_GUID@@PEAUSIP_DISPATCH_INFO_@@@Z; I_GetSignature(ushort const *,SIP_SUBJECTINFO_ *,_GUID *,SIP_DISPATCH_INFO_ *)
0x1800354db  mov     [rsp+120h+pvPara], 0; Str
0x1800354e4  mov     r9, r13
0x1800354e7  mov     r8, rbx
0x1800354ea  mov     rdx, rax; hCryptMsg
0x1800354ed  xor     ecx, ecx; wParam
0x1800354ef  call    DisplaySignature
0x1800354f4  jmp     loc_1800356B1
0x1800354f9  mov     r12d, 1
0x1800354ff  cmp     [r15+20h], r12w
0x180035504  jnz     short loc_180035529
0x180035506  mov     r8d, [r15+28h]; unsigned int
0x18003550a  mov     rdx, [r15+30h]; unsigned __int8 *
0x18003550e  mov     ecx, 10001h; unsigned int
0x180035513  call    ?I_OpenBlob@@YAPEAXKPEAEK@Z; I_OpenBlob(ulong,uchar *,ulong)
0x180035518  mov     r14, rax
0x18003551b  test    rax, rax
0x18003551e  jz      loc_1800356B1
0x180035524  jmp     loc_180035679
0x180035529  xor     r14d, r14d
0x18003552c  cmp     word ptr [r15+20h], 2
0x180035532  jnz     loc_180035679
0x180035538  mov     r14, [r15+28h]
0x18003553c  mov     [rsp+120h+pvPara], 0; Str
0x180035545  mov     r9, r13
0x180035548  mov     r8, rbx
0x18003554b  mov     rdx, r14; hCryptMsg
0x18003554e  xor     ecx, ecx; wParam
0x180035550  call    DisplaySignature
0x180035555  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x18003555a  lea     r8, [rbp+57h+var_50]; void ***
0x18003555e  mov     rcx, r14; void *
0x180035561  call    ?I_GetSecondarySignatures@@YAJPEAXKPEAPEAPEAXPEAK@Z; I_GetSecondarySignatures(void *,ulong,void * * *,ulong *)
0x180035566  mov     rsi, qword ptr [rbp+57h+var_50.Data1]
0x18003556a  test    eax, eax
0x18003556c  js      loc_180035675
0x180035572  test    rsi, rsi
0x180035575  jz      short loc_180035586
0x180035577  lea     rcx, [rsp+120h+var_E8]
0x18003557c  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@heapfree@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(void)
0x180035581  mov     [rsp+120h+var_E8], rsi
0x180035586  mov     edi, [rsp+120h+var_F0]
0x18003558a  mov     edx, edi; unsigned int
0x18003558c  mov     rcx, rsi; void **
0x18003558f  call    ?I_OrderSignatures@@YAJPEAPEAXK@Z; I_OrderSignatures(void * *,ulong)
0x180035594  test    eax, eax
0x180035596  js      loc_180035679
0x18003559c  test    edi, edi
0x18003559e  jz      short loc_1800355FC
0x1800355a0  mov     rax, [rbx]
0x1800355a3  mov     edx, [rax+58h]
0x1800355a6  add     edx, edi
0x1800355a8  shl     rdx, 3; uBytes
0x1800355ac  mov     ecx, 40h ; '@'; uFlags
0x1800355b1  call    cs:__imp_LocalAlloc
0x1800355b7  mov     r15, rax
0x1800355ba  test    rax, rax
0x1800355bd  jz      loc_180035679
0x1800355c3  mov     [rsp+120h+var_E0], rax
0x1800355c8  mov     rdx, [rbx]
0x1800355cb  mov     r8d, [rdx+58h]
0x1800355cf  shl     r8, 3; Size
0x1800355d3  mov     rdx, [rdx+60h]; Src
0x1800355d7  mov     rcx, rax; void *
0x1800355da  call    memmove_0
0x1800355df  mov     rcx, [rbx]
0x1800355e2  mov     rcx, [rcx+60h]; hMem
0x1800355e6  call    cs:__imp_LocalFree
0x1800355ec  mov     [rsp+120h+var_E0], 0
0x1800355f5  mov     rax, [rbx]
0x1800355f8  mov     [rax+60h], r15
0x1800355fc  xor     r15d, r15d
0x1800355ff  test    edi, edi
0x180035601  jz      short loc_180035679
0x180035603  mov     eax, r15d
0x180035606  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18003560a  mov     rax, [rsi+r15*8]
0x18003560e  mov     [rsp+120h+pvPara], rax; pvPara
0x180035613  xor     r9d, r9d; dwFlags
0x180035616  xor     r8d, r8d; hCryptProv
0x180035619  mov     edx, 10001h; dwEncodingType
0x18003561e  mov     rcx, r12; lpszStoreProvider
0x180035621  call    cs:__imp_CertOpenStore
0x180035627  mov     rcx, [rbx]
0x18003562a  mov     edx, [rcx+58h]
0x18003562d  mov     rcx, [rcx+60h]
0x180035631  mov     [rcx+rdx*8], rax
0x180035635  mov     rcx, [rbx]
0x180035638  mov     edx, [rcx+58h]
0x18003563b  mov     rax, [rcx+60h]
0x18003563f  cmp     qword ptr [rax+rdx*8], 0
0x180035644  jz      short loc_180035679
0x180035646  lea     eax, [rdx+1]
0x180035649  mov     [rcx+58h], eax
0x18003564c  inc     r15d
0x18003564f  mov     [rsp+120h+pvPara], 0; Str
0x180035658  mov     r9, r13
0x18003565b  mov     r8, rbx
0x18003565e  mov     rdx, qword ptr [rbp+57h+var_50.Data1]
0x180035662  mov     rdx, [rsi+rdx*8]; hCryptMsg
0x180035666  mov     ecx, r15d; wParam
0x180035669  call    DisplaySignature
0x18003566e  cmp     r15d, edi
0x180035671  jb      short loc_180035603
0x180035673  jmp     short loc_180035679
0x180035675  mov     edi, [rsp+120h+var_F0]
0x180035679  mov     rax, [rbx]
0x18003567c  cmp     [rax+20h], r12w
0x180035681  jnz     short loc_18003568C
0x180035683  mov     rcx, r14; hCryptMsg
0x180035686  call    cs:__imp_CryptMsgClose
0x18003568c  test    edi, edi
0x18003568e  jz      short loc_1800356B1
0x180035690  test    rsi, rsi
0x180035693  jz      short loc_1800356B1
0x180035695  xor     ebx, ebx
0x180035697  test    edi, edi
0x180035699  jz      short loc_1800356B1
0x18003569b  mov     rcx, [rsi+rbx*8]; hCryptMsg
0x18003569f  test    rcx, rcx
0x1800356a2  jz      short loc_1800356AA
0x1800356a4  call    cs:__imp_CryptMsgClose
0x1800356aa  add     ebx, r12d
0x1800356ad  cmp     ebx, edi
0x1800356af  jb      short loc_18003569B
0x1800356b1  lea     rcx, [rsp+120h+var_E8]
0x1800356b6  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@heapfree@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::heapfree::tag>>::_Delete(void)
0x1800356bb  nop
0x1800356bc  mov     rcx, [rbp+57h+var_40]
0x1800356c0  xor     rcx, rsp; StackCookie
0x1800356c3  call    __security_check_cookie
0x1800356c8  mov     rbx, [rsp+120h+arg_10]
0x1800356d0  add     rsp, 0F0h
0x1800356d7  pop     r15
0x1800356d9  pop     r14
0x1800356db  pop     r13
0x1800356dd  pop     r12
0x1800356df  pop     rdi
0x1800356e0  pop     rsi
0x1800356e1  pop     rbp
0x1800356e2  retn
```
