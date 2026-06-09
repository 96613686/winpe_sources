# myGetCertNameList(_CERT_CONTEXT const *,ulong,ulong,ulong *,ushort * * *)

- ea: `0x180017fac`
- end: `0x180018308`
- name: `?myGetCertNameList@@YAJPEBU_CERT_CONTEXT@@KKPEAKPEAPEAPEAG@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800174f8`

## callees

- `0x180016fa0`
- `0x1800172f0`
- `0x180017fac`
- `0x18001a158`
- `0x18001df64`
- `0x1800204d8`
- `0x180020638`
- `0x180020834`
- `0x180020a6c`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001812e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001812e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182e0`
- `CRYPT32!CertFindExtension` at `0x180018004`
- `CRYPT32!CertFindExtension` at `0x180018004`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018051`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018051`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x1800180d5`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180018108`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x1800180d5`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180018108`

## pseudocode

```c
__int64 __fastcall myGetCertNameList(
        PCCERT_CONTEXT pCertContext,
        int a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  unsigned int v5; // r12d
  unsigned __int16 *v9; // r14
  PCERT_INFO pCertInfo; // rdx
  unsigned __int16 **v11; // rdi
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // ecx
  int v18; // edx
  __int64 v19; // r8
  unsigned int v20; // r15d
  unsigned int v21; // edx
  DWORD v22; // edx
  unsigned int NameString; // eax
  unsigned __int16 **v24; // rax
  __int64 v25; // rsi
  _QWORD *v26; // rcx
  __int64 v27; // r10
  int v28; // ecx
  unsigned __int16 *v29; // rdx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  __int64 v36; // rax
  __int64 v38; // [rsp+28h] [rbp-28h]
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v40; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 *v41; // [rsp+90h] [rbp+40h] BYREF
  unsigned int *v42; // [rsp+A8h] [rbp+58h]

  v42 = a4;
  v5 = 0;
  hMem = 0;
  v9 = 0;
  v40 = 0;
  pCertInfo = pCertContext->pCertInfo;
  v11 = 0;
  *a5 = 0;
  *a4 = 0;
  Extension = CertFindExtension("2.5.29.17", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( !Extension )
    goto LABEL_19;
  cbData = Extension->Value.cbData;
  pbData = Extension->Value.pbData;
  LODWORD(v41) = 0;
  if ( !myDecodeObjectEx((__int64)&hMem, (const CHAR *)0xC, pbData, cbData, a3, v38, &hMem, (DWORD *)&v41) )
  {
    v15 = myHLastError();
    v16 = v15;
    v17 = 251068827;
LABEL_4:
    v18 = v15;
    goto LABEL_5;
  }
  if ( !*(_DWORD *)hMem )
    goto LABEL_19;
  v19 = *((_QWORD *)hMem + 1);
  v20 = 0;
  v21 = 0;
  do
  {
    if ( (!a2 || *(_DWORD *)(v19 + 24LL * v21) == a2)
      && (*(_DWORD *)(v19 + 24LL * v21) == 1
       || *(_DWORD *)(v19 + 24LL * v21) == 2
       || *(_DWORD *)(v19 + 24LL * v21) == 3
       || *(_DWORD *)(v19 + 24LL * v21) == 5
       || *(_DWORD *)(v19 + 24LL * v21) == 7
       || (unsigned int)(*(_DWORD *)(v19 + 24LL * v21) - 8) <= 1) )
    {
      ++v20;
    }
    ++v21;
  }
  while ( v21 < *(_DWORD *)hMem );
  if ( !v20 )
  {
LABEL_19:
    if ( a2 == 2 )
    {
      v22 = 1;
    }
    else
    {
      if ( a2 != 3 )
      {
        v16 = -2146885628;
        CSPrintErrorLineFile2(0xF22019Bu, -2146885628, -2146885628);
        goto LABEL_59;
      }
      v22 = 6;
    }
    NameString = myCertGetNameString(pCertContext, v22, &v40);
    v16 = NameString;
    if ( NameString )
    {
      CSPrintErrorLineFile2(0xF25019Bu, NameString, NameString);
      v9 = v40;
      goto LABEL_59;
    }
    v9 = v40;
    v20 = 1;
  }
  v24 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * (v20 + 1));
  v11 = v24;
  if ( !v24 )
  {
    v18 = -2147024882;
    v17 = 254738843;
    v16 = -2147024882;
LABEL_5:
    CSPrintErrorLineFile(v17, v18);
    goto LABEL_59;
  }
  *v24 = 0;
  if ( !v9 )
  {
    v26 = hMem;
    LODWORD(v25) = 0;
    while ( 1 )
    {
      if ( v5 >= *(_DWORD *)v26 )
        goto LABEL_58;
      v27 = v26[1];
      if ( !a2 || *(_DWORD *)(v27 + 24LL * v5) == a2 )
        break;
LABEL_56:
      ++v5;
    }
    v28 = *(_DWORD *)(v27 + 24LL * v5);
    v29 = 0;
    v41 = 0;
    v30 = v28 - 1;
    if ( !v30 )
    {
      v15 = cpOtherNameToWsz(*(const struct _CERT_OTHER_NAME **)(v27 + 24LL * v5 + 8), &v41);
      v16 = v15;
      if ( v15 > 1 )
      {
        v17 = 259195291;
        goto LABEL_4;
      }
      goto LABEL_51;
    }
    v31 = v30 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 2;
        if ( !v33 )
        {
          v15 = myCertNameToStr(0, (const struct _CRYPTOAPI_BLOB *)(v27 + 8 * (3LL * v5 + 1)), 0x2000003u, &v41);
          v16 = v15;
          if ( v15 )
          {
            v17 = 257229211;
            goto LABEL_4;
          }
          goto LABEL_51;
        }
        v34 = v33 - 2;
        if ( v34 )
        {
          v35 = v34 - 1;
          if ( v35 )
          {
            if ( v35 != 1 )
            {
LABEL_55:
              LocalFree(v29);
              v26 = hMem;
              goto LABEL_56;
            }
            if ( !(unsigned int)myConvertSzToWsz(&v41, *(const char **)(v27 + 24LL * v5 + 8), -1) )
            {
              v18 = -2147024882;
              v17 = 258539931;
              v16 = -2147024882;
              goto LABEL_5;
            }
          }
          else
          {
            v15 = cpIPAddressToWsz(
                    *(const unsigned __int8 **)(v27 + 24LL * v5 + 16),
                    *(_DWORD *)(v27 + 24LL * v5 + 8),
                    &v41);
            v16 = v15;
            if ( v15 )
            {
              v17 = 257819035;
              goto LABEL_4;
            }
          }
LABEL_51:
          v29 = v41;
          if ( v41 && *v41 && (unsigned int)v25 < v20 )
          {
            v36 = (unsigned int)v25;
            v25 = (unsigned int)(v25 + 1);
            v11[v36] = v41;
            v29 = 0;
            v11[v25] = 0;
          }
          goto LABEL_55;
        }
      }
    }
    v15 = myDupString(*(const unsigned __int16 **)(v27 + 24LL * v5 + 8), &v41);
    v16 = v15;
    if ( v15 )
    {
      v17 = 256573851;
      goto LABEL_4;
    }
    goto LABEL_51;
  }
  *v24 = v9;
  LODWORD(v25) = 1;
  v9 = 0;
  v24[1] = 0;
LABEL_58:
  v16 = 0;
  *v42 = v25;
  *a5 = v11;
  v11 = 0;
LABEL_59:
  LocalFree(v9);
  LocalFree(hMem);
  myFreeStringArray(v11);
  return v16;
}

```

## disassembly

```asm
0x180017fac  mov     [rsp-38h+arg_8], rbx
0x180017fb1  mov     [rsp-38h+arg_18], r9
0x180017fb6  push    rbp
0x180017fb7  push    rsi
0x180017fb8  push    rdi
0x180017fb9  push    r12
0x180017fbb  push    r13
0x180017fbd  push    r14
0x180017fbf  push    r15
0x180017fc1  mov     rbp, rsp
0x180017fc4  sub     rsp, 50h
0x180017fc8  xor     r12d, r12d
0x180017fcb  mov     rsi, rcx
0x180017fce  mov     rcx, [rbp+arg_20]
0x180017fd2  mov     r13d, edx
0x180017fd5  mov     [rbp+hMem], r12
0x180017fd9  mov     ebx, r8d
0x180017fdc  mov     r14d, r12d
0x180017fdf  mov     [rbp+var_8], r12
0x180017fe3  mov     rdx, [rsi+18h]
0x180017fe7  mov     edi, r12d
0x180017fea  mov     [rcx], r12
0x180017fed  lea     rcx, a252917; "2.5.29.17"
0x180017ff4  mov     [r9], r12d
0x180017ff7  mov     r8, [rdx+0C8h]; rgExtensions
0x180017ffe  mov     edx, [rdx+0C0h]; cExtensions
0x180018004  call    cs:__imp_CertFindExtension
0x18001800a  test    rax, rax
0x18001800d  jz      loc_1800180B9
0x180018013  mov     r9d, [rax+10h]
0x180018017  lea     rcx, [rbp+arg_0]
0x18001801b  mov     r8, [rax+18h]
0x18001801f  lea     edx, [r12+0Ch]
0x180018024  mov     [rsp+50h+var_18], rcx
0x180018029  lea     rcx, [rbp+hMem]
0x18001802d  mov     [rsp+50h+var_20], rcx
0x180018032  mov     [rsp+50h+var_30], ebx
0x180018036  mov     dword ptr [rbp+arg_0], r12d
0x18001803a  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18001803f  test    eax, eax
0x180018041  jnz     short loc_18001805C
0x180018043  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018048  mov     ebx, eax
0x18001804a  mov     ecx, 0EF7019Bh
0x18001804f  mov     edx, eax
0x180018051  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180018057  jmp     loc_1800182D3
0x18001805c  mov     rax, [rbp+hMem]
0x180018060  mov     r9d, [rax]
0x180018063  test    r9d, r9d
0x180018066  jz      short loc_1800180B9
0x180018068  mov     r8, [rax+8]
0x18001806c  mov     r15d, r12d
0x18001806f  mov     edx, r12d
0x180018072  mov     eax, edx
0x180018074  lea     rcx, [rax+rax*2]
0x180018078  test    r13d, r13d
0x18001807b  jz      short loc_180018083
0x18001807d  cmp     [r8+rcx*8], r13d
0x180018081  jnz     short loc_1800180AD
0x180018083  mov     ecx, [r8+rcx*8]
0x180018087  sub     ecx, 1
0x18001808a  jz      short loc_1800180AA
0x18001808c  sub     ecx, 1
0x18001808f  jz      short loc_1800180AA
0x180018091  sub     ecx, 1
0x180018094  jz      short loc_1800180AA
0x180018096  sub     ecx, 2
0x180018099  jz      short loc_1800180AA
0x18001809b  sub     ecx, 2
0x18001809e  jz      short loc_1800180AA
0x1800180a0  sub     ecx, 1
0x1800180a3  jz      short loc_1800180AA
0x1800180a5  cmp     ecx, 1
0x1800180a8  jnz     short loc_1800180AD
0x1800180aa  inc     r15d
0x1800180ad  inc     edx
0x1800180af  cmp     edx, r9d
0x1800180b2  jb      short loc_180018072
0x1800180b4  test    r15d, r15d
0x1800180b7  jnz     short loc_180018121
0x1800180b9  mov     eax, r13d
0x1800180bc  sub     eax, 2
0x1800180bf  jz      short loc_1800180E7
0x1800180c1  cmp     eax, 1
0x1800180c4  jz      short loc_1800180E0
0x1800180c6  mov     ebx, 80092004h
0x1800180cb  mov     ecx, 0F22019Bh
0x1800180d0  mov     r8d, ebx
0x1800180d3  mov     edx, ebx
0x1800180d5  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x1800180db  jmp     loc_1800182D3
0x1800180e0  mov     edx, 6
0x1800180e5  jmp     short loc_1800180EC
0x1800180e7  mov     edx, 1; dwType
0x1800180ec  lea     r8, [rbp+var_8]; unsigned __int16 **
0x1800180f0  mov     rcx, rsi; pCertContext
0x1800180f3  call    ?myCertGetNameString@@YAJPEBU_CERT_CONTEXT@@KPEAPEAG@Z; myCertGetNameString(_CERT_CONTEXT const *,ulong,ushort * *)
0x1800180f8  mov     ebx, eax
0x1800180fa  test    eax, eax
0x1800180fc  jz      short loc_180018117
0x1800180fe  mov     r8d, eax
0x180018101  mov     edx, eax
0x180018103  mov     ecx, 0F25019Bh
0x180018108  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18001810e  mov     r14, [rbp+var_8]
0x180018112  jmp     loc_1800182D3
0x180018117  mov     r14, [rbp+var_8]
0x18001811b  mov     r15d, 1
0x180018121  lea     edx, [r15+1]
0x180018125  mov     ecx, 40h ; '@'; uFlags
0x18001812a  shl     rdx, 3; uBytes
0x18001812e  call    cs:__imp_LocalAlloc
0x180018134  mov     rdi, rax
0x180018137  test    rax, rax
0x18001813a  jnz     short loc_18001814D
0x18001813c  mov     edx, 8007000Eh
0x180018141  mov     ecx, 0F2F019Bh
0x180018146  mov     ebx, edx
0x180018148  jmp     loc_180018051
0x18001814d  mov     [rax], r12
0x180018150  test    r14, r14
0x180018153  jz      short loc_180018169
0x180018155  mov     [rax], r14
0x180018158  mov     esi, 1
0x18001815d  mov     r14, r12
0x180018160  mov     [rax+8], r12
0x180018164  jmp     loc_1800182C0
0x180018169  mov     rcx, [rbp+hMem]
0x18001816d  mov     esi, r12d
0x180018170  cmp     r12d, [rcx]
0x180018173  jnb     loc_1800182BD
0x180018179  mov     r10, [rcx+8]
0x18001817d  mov     eax, r12d
0x180018180  lea     r9, [rax+rax*2]
0x180018184  test    r13d, r13d
0x180018187  jz      short loc_180018193
0x180018189  cmp     [r10+r9*8], r13d
0x18001818d  jnz     loc_1800182AB
0x180018193  mov     ecx, [r10+r9*8]
0x180018197  xor     edx, edx
0x180018199  mov     [rbp+arg_0], rdx
0x18001819d  sub     ecx, 1
0x1800181a0  jz      loc_180018266
0x1800181a6  sub     ecx, 1
0x1800181a9  jz      loc_180018248
0x1800181af  sub     ecx, 1
0x1800181b2  jz      loc_180018248
0x1800181b8  sub     ecx, 2; unsigned int
0x1800181bb  jz      short loc_180018222
0x1800181bd  sub     ecx, 2
0x1800181c0  jz      loc_180018248
0x1800181c6  sub     ecx, 1
0x1800181c9  jz      short loc_1800181FF
0x1800181cb  cmp     ecx, 1
0x1800181ce  jnz     loc_18001829E
0x1800181d4  mov     rdx, [r10+r9*8+8]; char *
0x1800181d9  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x1800181dd  or      r8d, 0FFFFFFFFh; int
0x1800181e1  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x1800181e6  test    eax, eax
0x1800181e8  jnz     loc_18001827B
0x1800181ee  mov     edx, 8007000Eh
0x1800181f3  mov     ecx, 0F69019Bh
0x1800181f8  mov     ebx, edx
0x1800181fa  jmp     loc_180018051
0x1800181ff  mov     edx, [r10+r9*8+8]; unsigned int
0x180018204  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180018208  mov     rcx, [r10+r9*8+10h]; unsigned __int8 *
0x18001820d  call    ?cpIPAddressToWsz@@YAJPEBEKPEAPEAG@Z; cpIPAddressToWsz(uchar const *,ulong,ushort * *)
0x180018212  mov     ebx, eax
0x180018214  test    eax, eax
0x180018216  jz      short loc_18001827B
0x180018218  mov     ecx, 0F5E019Bh
0x18001821d  jmp     loc_18001804F
0x180018222  inc     r9
0x180018225  mov     r8d, 2000003h; unsigned int
0x18001822b  lea     rdx, [r10+r9*8]; struct _CRYPTOAPI_BLOB *
0x18001822f  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x180018233  call    ?myCertNameToStr@@YAJKPEBU_CRYPTOAPI_BLOB@@KPEAPEAG@Z; myCertNameToStr(ulong,_CRYPTOAPI_BLOB const *,ulong,ushort * *)
0x180018238  mov     ebx, eax
0x18001823a  test    eax, eax
0x18001823c  jz      short loc_18001827B
0x18001823e  mov     ecx, 0F55019Bh
0x180018243  jmp     loc_18001804F
0x180018248  mov     rcx, [r10+r9*8+8]; Src
0x18001824d  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x180018251  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180018256  mov     ebx, eax
0x180018258  test    eax, eax
0x18001825a  jz      short loc_18001827B
0x18001825c  mov     ecx, 0F4B019Bh
0x180018261  jmp     loc_18001804F
0x180018266  mov     rcx, [r10+r9*8+8]; struct _CERT_OTHER_NAME *
0x18001826b  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18001826f  call    ?cpOtherNameToWsz@@YAJPEBU_CERT_OTHER_NAME@@PEAPEAG@Z; cpOtherNameToWsz(_CERT_OTHER_NAME const *,ushort * *)
0x180018274  mov     ebx, eax
0x180018276  cmp     eax, 1
0x180018279  ja      short loc_1800182B3
0x18001827b  mov     rdx, [rbp+arg_0]
0x18001827f  test    rdx, rdx
0x180018282  jz      short loc_18001829E
0x180018284  xor     eax, eax
0x180018286  cmp     ax, [rdx]
0x180018289  jz      short loc_18001829E
0x18001828b  cmp     esi, r15d
0x18001828e  jnb     short loc_18001829E
0x180018290  mov     eax, esi
0x180018292  inc     esi
0x180018294  mov     [rdi+rax*8], rdx
0x180018298  xor     edx, edx
0x18001829a  mov     [rdi+rsi*8], rdx
0x18001829e  mov     rcx, rdx; hMem
0x1800182a1  call    cs:__imp_LocalFree
0x1800182a7  mov     rcx, [rbp+hMem]
0x1800182ab  inc     r12d
0x1800182ae  jmp     loc_180018170
0x1800182b3  mov     ecx, 0F73019Bh
0x1800182b8  jmp     loc_18001804F
0x1800182bd  xor     r12d, r12d
0x1800182c0  mov     rax, [rbp+arg_18]
0x1800182c4  mov     ebx, r12d
0x1800182c7  mov     [rax], esi
0x1800182c9  mov     rax, [rbp+arg_20]
0x1800182cd  mov     [rax], rdi
0x1800182d0  mov     rdi, r12
0x1800182d3  mov     rcx, r14; hMem
0x1800182d6  call    cs:__imp_LocalFree
0x1800182dc  mov     rcx, [rbp+hMem]; hMem
0x1800182e0  call    cs:__imp_LocalFree
0x1800182e6  mov     rcx, rdi; hMem
0x1800182e9  call    ?myFreeStringArray@@YAXPEAPEAG@Z; myFreeStringArray(ushort * *)
0x1800182ee  mov     eax, ebx
0x1800182f0  mov     rbx, [rsp+50h+arg_8]
0x1800182f8  add     rsp, 50h
0x1800182fc  pop     r15
0x1800182fe  pop     r14
0x180018300  pop     r13
0x180018302  pop     r12
0x180018304  pop     rdi
0x180018305  pop     rsi
0x180018306  pop     rbp
0x180018307  retn
```
