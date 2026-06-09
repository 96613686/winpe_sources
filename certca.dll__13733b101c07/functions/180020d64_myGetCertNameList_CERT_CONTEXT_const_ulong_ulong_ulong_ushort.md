# myGetCertNameList(_CERT_CONTEXT const *,ulong,ulong,ulong *,ushort * * *)

- ea: `0x180020d64`
- end: `0x1800210bd`
- name: `?myGetCertNameList@@YAJPEBU_CERT_CONTEXT@@KKPEAKPEAPEAPEAG@Z`
- size: `857`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, int, int, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180015c10`
- `0x18002024c`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000dce0`
- `0x180012450`
- `0x180017f00`
- `0x18001ac74`
- `0x18001dd10`
- `0x18001dfa0`
- `0x18001e080`
- `0x18001fcf4`
- `0x180020040`
- `0x180020d64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020eeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002108b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021095`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002108b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021095`
- `CRYPT32!CertFindExtension` at `0x180020dbc`
- `CRYPT32!CertFindExtension` at `0x180020dbc`

## pseudocode

```c
__int64 __fastcall myGetCertNameList(
        PCCERT_CONTEXT pCertContext,
        int a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  unsigned int v5; // r15d
  unsigned __int16 *v9; // r12
  unsigned __int16 **v10; // rsi
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  int v17; // edx
  __int64 v18; // r8
  unsigned int v19; // r14d
  unsigned int v20; // edx
  DWORD v21; // edx
  int NameString; // eax
  unsigned __int16 **v23; // rax
  int v24; // r8d
  __int64 v25; // rdi
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
  v10 = 0;
  *a5 = 0;
  *a4 = 0;
  Extension = CertFindExtension("2.5.29.17", pCertContext->pCertInfo->cExtension, pCertContext->pCertInfo->rgExtension);
  if ( !Extension )
    goto LABEL_19;
  cbData = Extension->Value.cbData;
  pbData = Extension->Value.pbData;
  LODWORD(v41) = 0;
  if ( !myDecodeObjectEx(1u, (const CHAR *)0xC, pbData, cbData, a3, v38, &hMem, (DWORD *)&v41) )
  {
    v14 = myHLastError();
    v15 = v14;
    v16 = 251068827;
LABEL_4:
    v17 = v14;
    goto LABEL_5;
  }
  if ( !*(_DWORD *)hMem )
    goto LABEL_19;
  v18 = *((_QWORD *)hMem + 1);
  v19 = 0;
  v20 = 0;
  do
  {
    if ( (!a2 || *(_DWORD *)(v18 + 24LL * v20) == a2)
      && (*(_DWORD *)(v18 + 24LL * v20) == 1
       || *(_DWORD *)(v18 + 24LL * v20) == 2
       || *(_DWORD *)(v18 + 24LL * v20) == 3
       || *(_DWORD *)(v18 + 24LL * v20) == 5
       || *(_DWORD *)(v18 + 24LL * v20) == 7
       || (unsigned int)(*(_DWORD *)(v18 + 24LL * v20) - 8) <= 1) )
    {
      ++v19;
    }
    ++v20;
  }
  while ( v20 < *(_DWORD *)hMem );
  if ( !v19 )
  {
LABEL_19:
    if ( a2 == 2 )
    {
      v21 = 1;
    }
    else
    {
      if ( a2 != 3 )
      {
        v15 = -2146885628;
        CSPrintErrorLineFileData2(0, 0xF22019Bu, -2146885628, -2146885628);
        goto LABEL_59;
      }
      v21 = 6;
    }
    NameString = myCertGetNameString(pCertContext, v21, &v40);
    v15 = NameString;
    if ( NameString )
    {
      CSPrintErrorLineFileData2(0, 0xF25019Bu, NameString, NameString);
      v9 = v40;
      goto LABEL_59;
    }
    v9 = v40;
    v19 = 1;
  }
  v23 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * (v19 + 1));
  v10 = v23;
  if ( !v23 )
  {
    v17 = -2147024882;
    v16 = 254738843;
    v15 = -2147024882;
LABEL_5:
    CSPrintErrorLineFile(v16, v17);
    goto LABEL_59;
  }
  *v23 = 0;
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
      v14 = cpOtherNameToWsz(*(const struct _CERT_OTHER_NAME **)(v27 + 24LL * v5 + 8), &v41);
      v15 = v14;
      if ( v14 > 1 )
      {
        v16 = 259195291;
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
          v14 = myCertNameToStr(0, (const struct _CRYPTOAPI_BLOB *)(v27 + 8 * (3LL * v5 + 1)), 0x2000003u, &v41);
          v15 = v14;
          if ( v14 )
          {
            v16 = 257229211;
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
            if ( !(unsigned int)myConvertSzToWsz(&v41, *(const char **)(v27 + 24LL * v5 + 8), v24) )
            {
              v17 = -2147024882;
              v16 = 258539931;
              v15 = -2147024882;
              goto LABEL_5;
            }
          }
          else
          {
            v14 = cpIPAddressToWsz(
                    *(const unsigned __int8 **)(v27 + 24LL * v5 + 16),
                    *(_DWORD *)(v27 + 24LL * v5 + 8),
                    &v41);
            v15 = v14;
            if ( v14 )
            {
              v16 = 257819035;
              goto LABEL_4;
            }
          }
LABEL_51:
          v29 = v41;
          if ( v41 && *v41 && (unsigned int)v25 < v19 )
          {
            v36 = (unsigned int)v25;
            v25 = (unsigned int)(v25 + 1);
            v10[v36] = v41;
            v29 = 0;
            v10[v25] = 0;
          }
          goto LABEL_55;
        }
      }
    }
    v14 = myDupString(*(const unsigned __int16 **)(v27 + 24LL * v5 + 8), &v41);
    v15 = v14;
    if ( v14 )
    {
      v16 = 256573851;
      goto LABEL_4;
    }
    goto LABEL_51;
  }
  *v23 = v9;
  LODWORD(v25) = 1;
  v9 = 0;
  v23[1] = 0;
LABEL_58:
  v15 = 0;
  *v42 = v25;
  *a5 = v10;
  v10 = 0;
LABEL_59:
  LocalFree(v9);
  LocalFree(hMem);
  myFreeStringArray(v10);
  return v15;
}

```

## disassembly

```asm
0x180020d64  mov     [rsp-38h+arg_8], rbx
0x180020d69  mov     [rsp-38h+arg_18], r9
0x180020d6e  push    rbp
0x180020d6f  push    rsi
0x180020d70  push    rdi
0x180020d71  push    r12
0x180020d73  push    r13
0x180020d75  push    r14
0x180020d77  push    r15
0x180020d79  mov     rbp, rsp
0x180020d7c  sub     rsp, 50h
0x180020d80  xor     r15d, r15d
0x180020d83  mov     rdi, rcx
0x180020d86  mov     rcx, [rbp+arg_20]
0x180020d8a  mov     r13d, edx
0x180020d8d  mov     [rbp+hMem], r15
0x180020d91  mov     ebx, r8d
0x180020d94  mov     r12d, r15d
0x180020d97  mov     [rbp+var_8], r15
0x180020d9b  mov     esi, r15d
0x180020d9e  mov     [rcx], r15
0x180020da1  lea     rcx, a252917; "2.5.29.17"
0x180020da8  mov     [r9], r15d
0x180020dab  mov     rdx, [rdi+18h]
0x180020daf  mov     r8, [rdx+0C8h]; rgExtensions
0x180020db6  mov     edx, [rdx+0C0h]; cExtensions
0x180020dbc  call    cs:__imp_CertFindExtension
0x180020dc2  test    rax, rax
0x180020dc5  jz      loc_180020E72
0x180020dcb  mov     r9d, [rax+10h]
0x180020dcf  lea     rcx, [rbp+arg_0]
0x180020dd3  mov     r8, [rax+18h]
0x180020dd7  lea     edx, [r15+0Ch]
0x180020ddb  mov     [rsp+50h+var_18], rcx
0x180020de0  lea     rcx, [rbp+hMem]
0x180020de4  mov     [rsp+50h+var_20], rcx
0x180020de9  lea     ecx, [rdx-0Bh]
0x180020dec  mov     dword ptr [rbp+arg_0], r15d
0x180020df0  mov     [rsp+50h+var_30], ebx
0x180020df4  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180020df9  test    eax, eax
0x180020dfb  jnz     short loc_180020E15
0x180020dfd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020e02  mov     ebx, eax
0x180020e04  mov     ecx, 0EF7019Bh; unsigned int
0x180020e09  mov     edx, eax; int
0x180020e0b  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180020e10  jmp     loc_180021088
0x180020e15  mov     rax, [rbp+hMem]
0x180020e19  mov     r9d, [rax]
0x180020e1c  test    r9d, r9d
0x180020e1f  jz      short loc_180020E72
0x180020e21  mov     r8, [rax+8]
0x180020e25  mov     r14d, r15d
0x180020e28  mov     edx, r15d
0x180020e2b  mov     eax, edx
0x180020e2d  lea     rcx, [rax+rax*2]
0x180020e31  test    r13d, r13d
0x180020e34  jz      short loc_180020E3C
0x180020e36  cmp     [r8+rcx*8], r13d
0x180020e3a  jnz     short loc_180020E66
0x180020e3c  mov     ecx, [r8+rcx*8]
0x180020e40  sub     ecx, 1
0x180020e43  jz      short loc_180020E63
0x180020e45  sub     ecx, 1
0x180020e48  jz      short loc_180020E63
0x180020e4a  sub     ecx, 1
0x180020e4d  jz      short loc_180020E63
0x180020e4f  sub     ecx, 2
0x180020e52  jz      short loc_180020E63
0x180020e54  sub     ecx, 2
0x180020e57  jz      short loc_180020E63
0x180020e59  sub     ecx, 1
0x180020e5c  jz      short loc_180020E63
0x180020e5e  cmp     ecx, 1
0x180020e61  jnz     short loc_180020E66
0x180020e63  inc     r14d
0x180020e66  inc     edx
0x180020e68  cmp     edx, r9d
0x180020e6b  jb      short loc_180020E2B
0x180020e6d  test    r14d, r14d
0x180020e70  jnz     short loc_180020EDE
0x180020e72  mov     eax, r13d
0x180020e75  sub     eax, 2
0x180020e78  jz      short loc_180020EA2
0x180020e7a  cmp     eax, 1
0x180020e7d  jz      short loc_180020E9B
0x180020e7f  mov     ebx, 80092004h
0x180020e84  mov     edx, 0F22019Bh; unsigned int
0x180020e89  mov     r9d, ebx; int
0x180020e8c  mov     r8d, ebx; int
0x180020e8f  xor     ecx, ecx; unsigned __int16 *
0x180020e91  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180020e96  jmp     loc_180021088
0x180020e9b  mov     edx, 6
0x180020ea0  jmp     short loc_180020EA7
0x180020ea2  mov     edx, 1; dwType
0x180020ea7  lea     r8, [rbp+var_8]; unsigned __int16 **
0x180020eab  mov     rcx, rdi; pCertContext
0x180020eae  call    ?myCertGetNameString@@YAJPEBU_CERT_CONTEXT@@KPEAPEAG@Z; myCertGetNameString(_CERT_CONTEXT const *,ulong,ushort * *)
0x180020eb3  mov     ebx, eax
0x180020eb5  test    eax, eax
0x180020eb7  jz      short loc_180020ED4
0x180020eb9  mov     r9d, eax; int
0x180020ebc  mov     r8d, eax; int
0x180020ebf  mov     edx, 0F25019Bh; unsigned int
0x180020ec4  xor     ecx, ecx; unsigned __int16 *
0x180020ec6  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180020ecb  mov     r12, [rbp+var_8]
0x180020ecf  jmp     loc_180021088
0x180020ed4  mov     r12, [rbp+var_8]
0x180020ed8  mov     r14d, 1
0x180020ede  lea     edx, [r14+1]
0x180020ee2  mov     ecx, 40h ; '@'; uFlags
0x180020ee7  shl     rdx, 3; uBytes
0x180020eeb  call    cs:__imp_LocalAlloc
0x180020ef1  mov     rsi, rax
0x180020ef4  test    rax, rax
0x180020ef7  jnz     short loc_180020F0A
0x180020ef9  mov     edx, 8007000Eh
0x180020efe  mov     ecx, 0F2F019Bh
0x180020f03  mov     ebx, edx
0x180020f05  jmp     loc_180020E0B
0x180020f0a  mov     [rax], r15
0x180020f0d  test    r12, r12
0x180020f10  jz      short loc_180020F26
0x180020f12  mov     [rax], r12
0x180020f15  mov     edi, 1
0x180020f1a  mov     r12, r15
0x180020f1d  mov     [rax+8], r15
0x180020f21  jmp     loc_180021075
0x180020f26  mov     rcx, [rbp+hMem]
0x180020f2a  mov     edi, r15d
0x180020f2d  cmp     r15d, [rcx]
0x180020f30  jnb     loc_180021072
0x180020f36  mov     r10, [rcx+8]
0x180020f3a  mov     eax, r15d
0x180020f3d  lea     r9, [rax+rax*2]
0x180020f41  test    r13d, r13d
0x180020f44  jz      short loc_180020F50
0x180020f46  cmp     [r10+r9*8], r13d
0x180020f4a  jnz     loc_180021060
0x180020f50  mov     ecx, [r10+r9*8]
0x180020f54  xor     edx, edx
0x180020f56  mov     [rbp+arg_0], rdx
0x180020f5a  sub     ecx, 1
0x180020f5d  jz      loc_18002101B
0x180020f63  sub     ecx, 1
0x180020f66  jz      loc_180020FFD
0x180020f6c  sub     ecx, 1
0x180020f6f  jz      loc_180020FFD
0x180020f75  sub     ecx, 2; unsigned int
0x180020f78  jz      short loc_180020FD7
0x180020f7a  sub     ecx, 2
0x180020f7d  jz      short loc_180020FFD
0x180020f7f  sub     ecx, 1
0x180020f82  jz      short loc_180020FB4
0x180020f84  cmp     ecx, 1
0x180020f87  jnz     loc_180021053
0x180020f8d  mov     rdx, [r10+r9*8+8]; char *
0x180020f92  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x180020f96  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x180020f9b  test    eax, eax
0x180020f9d  jnz     loc_180021030
0x180020fa3  mov     edx, 8007000Eh
0x180020fa8  mov     ecx, 0F69019Bh
0x180020fad  mov     ebx, edx
0x180020faf  jmp     loc_180020E0B
0x180020fb4  mov     edx, [r10+r9*8+8]; unsigned int
0x180020fb9  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180020fbd  mov     rcx, [r10+r9*8+10h]; unsigned __int8 *
0x180020fc2  call    ?cpIPAddressToWsz@@YAJPEBEKPEAPEAG@Z; cpIPAddressToWsz(uchar const *,ulong,ushort * *)
0x180020fc7  mov     ebx, eax
0x180020fc9  test    eax, eax
0x180020fcb  jz      short loc_180021030
0x180020fcd  mov     ecx, 0F5E019Bh
0x180020fd2  jmp     loc_180020E09
0x180020fd7  inc     r9
0x180020fda  mov     r8d, 2000003h; unsigned int
0x180020fe0  lea     rdx, [r10+r9*8]; struct _CRYPTOAPI_BLOB *
0x180020fe4  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x180020fe8  call    ?myCertNameToStr@@YAJKPEBU_CRYPTOAPI_BLOB@@KPEAPEAG@Z; myCertNameToStr(ulong,_CRYPTOAPI_BLOB const *,ulong,ushort * *)
0x180020fed  mov     ebx, eax
0x180020fef  test    eax, eax
0x180020ff1  jz      short loc_180021030
0x180020ff3  mov     ecx, 0F55019Bh
0x180020ff8  jmp     loc_180020E09
0x180020ffd  mov     rcx, [r10+r9*8+8]; Src
0x180021002  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x180021006  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18002100b  mov     ebx, eax
0x18002100d  test    eax, eax
0x18002100f  jz      short loc_180021030
0x180021011  mov     ecx, 0F4B019Bh
0x180021016  jmp     loc_180020E09
0x18002101b  mov     rcx, [r10+r9*8+8]; struct _CERT_OTHER_NAME *
0x180021020  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x180021024  call    ?cpOtherNameToWsz@@YAJPEBU_CERT_OTHER_NAME@@PEAPEAG@Z; cpOtherNameToWsz(_CERT_OTHER_NAME const *,ushort * *)
0x180021029  mov     ebx, eax
0x18002102b  cmp     eax, 1
0x18002102e  ja      short loc_180021068
0x180021030  mov     rdx, [rbp+arg_0]
0x180021034  test    rdx, rdx
0x180021037  jz      short loc_180021053
0x180021039  xor     eax, eax
0x18002103b  cmp     ax, [rdx]
0x18002103e  jz      short loc_180021053
0x180021040  cmp     edi, r14d
0x180021043  jnb     short loc_180021053
0x180021045  mov     eax, edi
0x180021047  inc     edi
0x180021049  mov     [rsi+rax*8], rdx
0x18002104d  xor     edx, edx
0x18002104f  mov     [rsi+rdi*8], rdx
0x180021053  mov     rcx, rdx; hMem
0x180021056  call    cs:__imp_LocalFree
0x18002105c  mov     rcx, [rbp+hMem]
0x180021060  inc     r15d
0x180021063  jmp     loc_180020F2D
0x180021068  mov     ecx, 0F73019Bh
0x18002106d  jmp     loc_180020E09
0x180021072  xor     r15d, r15d
0x180021075  mov     rax, [rbp+arg_18]
0x180021079  mov     ebx, r15d
0x18002107c  mov     [rax], edi
0x18002107e  mov     rax, [rbp+arg_20]
0x180021082  mov     [rax], rsi
0x180021085  mov     rsi, r15
0x180021088  mov     rcx, r12; hMem
0x18002108b  call    cs:__imp_LocalFree
0x180021091  mov     rcx, [rbp+hMem]; hMem
0x180021095  call    cs:__imp_LocalFree
0x18002109b  mov     rcx, rsi; hMem
0x18002109e  call    ?myFreeStringArray@@YAXPEAPEAG@Z; myFreeStringArray(ushort * *)
0x1800210a3  mov     eax, ebx
0x1800210a5  mov     rbx, [rsp+50h+arg_8]
0x1800210ad  add     rsp, 50h
0x1800210b1  pop     r15
0x1800210b3  pop     r14
0x1800210b5  pop     r13
0x1800210b7  pop     r12
0x1800210b9  pop     rdi
0x1800210ba  pop     rsi
0x1800210bb  pop     rbp
0x1800210bc  retn
```
