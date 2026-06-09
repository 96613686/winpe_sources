# cpTemplateMatch(ulong,_CERT_EXTENSION const *,_CERTFILTERDATA *,int *)

- ea: `0x180017818`
- end: `0x180017a56`
- name: `?cpTemplateMatch@@YAJKPEBU_CERT_EXTENSION@@PEAU_CERTFILTERDATA@@PEAH@Z`
- size: `574`
- prototype: `__int64 __fastcall(DWORD cExtensions, CERT_EXTENSION *__attribute__((__org_arrdim(0,0))) rgExtensions, struct _CERTFILTERDATA *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180016dac`

## callees

- `0x180015dc8`
- `0x180017620`
- `0x180017818`
- `0x18001a440`
- `0x180020638`
- `0x180020834`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a30`
- `CRYPT32!CertFindExtension` at `0x18001786c`
- `CRYPT32!CertFindExtension` at `0x1800178ce`
- `CRYPT32!CertFindExtension` at `0x18001786c`
- `CRYPT32!CertFindExtension` at `0x1800178ce`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017891`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001791a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800179a5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017891`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001791a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800179a5`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x1800179fb`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x1800179fb`

## pseudocode

```c
__int64 __fastcall cpTemplateMatch(
        DWORD cExtensions,
        CERT_EXTENSION rgExtensions[],
        struct _CERTFILTERDATA *a3,
        int *a4)
{
  int v4; // esi
  CERTFILTERSTRING *v5; // rbx
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rdi
  PCERT_EXTENSION Extension; // rax
  int v12; // eax
  unsigned int v13; // ebx
  PCERT_EXTENSION v14; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned __int8 *v17; // rcx
  __int64 v18; // r8
  int v19; // edx
  int v20; // eax
  unsigned __int8 *v21; // rcx
  __int64 v22; // r8
  int v23; // edx
  int v24; // eax
  const unsigned __int16 *v25; // rdx
  int v26; // eax
  __int64 v28; // [rsp+28h] [rbp-38h]
  HLOCAL hMem; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL v30; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-10h] BYREF
  int v32; // [rsp+B0h] [rbp+50h] BYREF
  int *v33; // [rsp+B8h] [rbp+58h]

  v33 = a4;
  v4 = 0;
  v5 = (struct _CERTFILTERDATA *)((char *)a3 + 40);
  v6 = 0;
  v32 = 0;
  v7 = 0;
  hMem = 0;
  v31 = 0;
  v30 = 0;
  if ( *((_QWORD *)a3 + 5) )
  {
    Extension = CertFindExtension("1.3.6.1.4.1.311.20.2", cExtensions, rgExtensions);
    if ( Extension )
    {
      v12 = myDecodeUnicodeName(&Extension->Value, (unsigned __int16 **)&hMem);
      v13 = v12;
      if ( v12 )
      {
        CSPrintErrorLineFile(0x495019Bu, v12);
        v6 = (unsigned __int16 *)hMem;
        goto LABEL_31;
      }
      v6 = (unsigned __int16 *)hMem;
      v5 = (struct _CERTFILTERDATA *)((char *)a3 + 40);
      if ( CERTFILTERSTRING::Match((struct _CERTFILTERDATA *)((char *)a3 + 40), (const unsigned __int16 *)hMem) )
        goto LABEL_6;
    }
    v14 = CertFindExtension("1.3.6.1.4.1.311.21.7", cExtensions, rgExtensions);
    if ( !v14 )
      goto LABEL_24;
    cbData = v14->Value.cbData;
    pbData = v14->Value.pbData;
    LODWORD(hMem) = 0;
    if ( !myDecodeObjectEx((__int64)&v30, (const CHAR *)0x40, pbData, cbData, 0, v28, &v30, (DWORD *)&hMem) )
    {
      v13 = myHLastError();
      CSPrintErrorLineFile(0x4B4019Bu, v13);
      goto LABEL_31;
    }
    v17 = (unsigned __int8 *)*((_QWORD *)a3 + 7);
    if ( v17 )
    {
      v18 = *(_QWORD *)v30 - (_QWORD)v17;
      do
      {
        v19 = v17[v18];
        v20 = *v17 - v19;
        if ( v20 )
          break;
        ++v17;
      }
      while ( v19 );
      if ( !v20 )
        goto LABEL_6;
    }
    v21 = (unsigned __int8 *)*((_QWORD *)a3 + 8);
    if ( v21 )
    {
      v22 = *(_QWORD *)v30 - (_QWORD)v21;
      do
      {
        v23 = v21[v22];
        v24 = *v21 - v23;
        if ( v24 )
          break;
        ++v21;
      }
      while ( v23 );
      if ( !v24 )
        goto LABEL_6;
    }
    if ( !(unsigned int)myConvertSzToWsz(&v31, *(const char **)v30, -1) )
    {
      v13 = -2147024882;
      CSPrintErrorLineFile(0x4C2019Bu, -2147024882);
      v7 = v31;
      goto LABEL_31;
    }
    v7 = v31;
    if ( CERTFILTERSTRING::Match(v5, v31) )
    {
LABEL_6:
      v4 = 1;
    }
    else
    {
LABEL_24:
      if ( v6 || v7 )
      {
        v25 = v6;
        if ( v7 )
          v25 = v7;
        v26 = cpTemplateMatch2(v7 != 0, v25, a3, &v32);
        v13 = v26;
        if ( v26 )
        {
          CSPrintErrorLineFile2(0x4D5019Bu, v26, v26);
          v4 = v32;
          goto LABEL_31;
        }
        v4 = v32;
      }
    }
  }
  v13 = 0;
LABEL_31:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  if ( v30 )
    LocalFree(v30);
  *v33 = v4;
  return v13;
}

```

## disassembly

```asm
0x180017818  mov     [rsp-38h+arg_0], rbx
0x18001781d  mov     [rsp-38h+arg_18], r9
0x180017822  push    rbp
0x180017823  push    rsi
0x180017824  push    rdi
0x180017825  push    r12
0x180017827  push    r13
0x180017829  push    r14
0x18001782b  push    r15
0x18001782d  mov     rbp, rsp
0x180017830  sub     rsp, 60h
0x180017834  xor     esi, esi
0x180017836  lea     rbx, [r8+28h]
0x18001783a  xor     r14d, r14d
0x18001783d  mov     [rbp+arg_10], esi
0x180017840  xor     edi, edi
0x180017842  mov     [rbp+hMem], r14
0x180017846  mov     r13, r8
0x180017849  mov     r15, rdx
0x18001784c  mov     r12d, ecx
0x18001784f  mov     [rbp+var_10], rdi
0x180017853  mov     [rbp+var_18], rsi
0x180017857  cmp     [rbx], rsi
0x18001785a  jz      loc_180017A09
0x180017860  mov     r8, rdx; rgExtensions
0x180017863  mov     edx, ecx; cExtensions
0x180017865  lea     rcx, pszObjId; "1.3.6.1.4.1.311.20.2"
0x18001786c  call    cs:__imp_CertFindExtension
0x180017872  test    rax, rax
0x180017875  jz      short loc_1800178C1
0x180017877  lea     rcx, [rax+10h]; struct _CRYPTOAPI_BLOB *
0x18001787b  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18001787f  call    ?myDecodeUnicodeName@@YAJPEBU_CRYPTOAPI_BLOB@@PEAPEAG@Z; myDecodeUnicodeName(_CRYPTOAPI_BLOB const *,ushort * *)
0x180017884  mov     ebx, eax
0x180017886  test    eax, eax
0x180017888  jz      short loc_1800178A0
0x18001788a  mov     edx, eax
0x18001788c  mov     ecx, 495019Bh
0x180017891  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017897  mov     r14, [rbp+hMem]
0x18001789b  jmp     loc_180017A0B
0x1800178a0  mov     r14, [rbp+hMem]
0x1800178a4  lea     rbx, [r13+28h]
0x1800178a8  mov     rdx, r14; unsigned __int16 *
0x1800178ab  mov     rcx, rbx; this
0x1800178ae  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x1800178b3  test    al, al
0x1800178b5  jz      short loc_1800178C1
0x1800178b7  mov     esi, 1
0x1800178bc  jmp     loc_180017A09
0x1800178c1  mov     r8, r15; rgExtensions
0x1800178c4  lea     rcx, a136141311217; "1.3.6.1.4.1.311.21.7"
0x1800178cb  mov     edx, r12d; cExtensions
0x1800178ce  call    cs:__imp_CertFindExtension
0x1800178d4  test    rax, rax
0x1800178d7  jz      loc_1800179C8
0x1800178dd  mov     r9d, [rax+10h]
0x1800178e1  lea     rcx, [rbp+hMem]
0x1800178e5  mov     r8, [rax+18h]
0x1800178e9  mov     edx, 40h ; '@'
0x1800178ee  mov     [rsp+60h+var_28], rcx
0x1800178f3  lea     rcx, [rbp+var_18]
0x1800178f7  mov     [rsp+60h+var_30], rcx
0x1800178fc  mov     [rsp+60h+var_40], esi
0x180017900  mov     dword ptr [rbp+hMem], esi
0x180017903  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180017908  test    eax, eax
0x18001790a  jnz     short loc_180017925
0x18001790c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017911  mov     edx, eax
0x180017913  mov     ecx, 4B4019Bh
0x180017918  mov     ebx, eax
0x18001791a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017920  jmp     loc_180017A0B
0x180017925  mov     rcx, [r13+38h]
0x180017929  test    rcx, rcx
0x18001792c  jz      short loc_180017953
0x18001792e  mov     rax, [rbp+var_18]
0x180017932  mov     r8, [rax]
0x180017935  sub     r8, rcx
0x180017938  movzx   eax, byte ptr [rcx]
0x18001793b  movzx   edx, byte ptr [rcx+r8]
0x180017940  sub     eax, edx
0x180017942  jnz     short loc_18001794B
0x180017944  inc     rcx
0x180017947  test    edx, edx
0x180017949  jnz     short loc_180017938
0x18001794b  test    eax, eax
0x18001794d  jz      loc_1800178B7
0x180017953  mov     rcx, [r13+40h]
0x180017957  test    rcx, rcx
0x18001795a  jz      short loc_180017981
0x18001795c  mov     rax, [rbp+var_18]
0x180017960  mov     r8, [rax]
0x180017963  sub     r8, rcx
0x180017966  movzx   eax, byte ptr [rcx]
0x180017969  movzx   edx, byte ptr [rcx+r8]
0x18001796e  sub     eax, edx
0x180017970  jnz     short loc_180017979
0x180017972  inc     rcx
0x180017975  test    edx, edx
0x180017977  jnz     short loc_180017966
0x180017979  test    eax, eax
0x18001797b  jz      loc_1800178B7
0x180017981  mov     rdx, [rbp+var_18]
0x180017985  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180017989  or      r8d, 0FFFFFFFFh; int
0x18001798d  mov     rdx, [rdx]; char *
0x180017990  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x180017995  test    eax, eax
0x180017997  jnz     short loc_1800179B1
0x180017999  mov     ebx, 8007000Eh
0x18001799e  mov     ecx, 4C2019Bh
0x1800179a3  mov     edx, ebx
0x1800179a5  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800179ab  mov     rdi, [rbp+var_10]
0x1800179af  jmp     short loc_180017A0B
0x1800179b1  mov     rdi, [rbp+var_10]
0x1800179b5  mov     rcx, rbx; this
0x1800179b8  mov     rdx, rdi; unsigned __int16 *
0x1800179bb  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x1800179c0  test    al, al
0x1800179c2  jnz     loc_1800178B7
0x1800179c8  test    r14, r14
0x1800179cb  jnz     short loc_1800179D2
0x1800179cd  test    rdi, rdi
0x1800179d0  jz      short loc_180017A09
0x1800179d2  test    rdi, rdi
0x1800179d5  lea     r9, [rbp+arg_10]; int *
0x1800179d9  mov     rdx, r14
0x1800179dc  mov     r8, r13; struct _CERTFILTERDATA *
0x1800179df  cmovnz  rdx, rdi; unsigned __int16 *
0x1800179e3  setnz   cl; bool
0x1800179e6  call    ?cpTemplateMatch2@@YAJ_NPEBGPEAU_CERTFILTERDATA@@PEAH@Z; cpTemplateMatch2(bool,ushort const *,_CERTFILTERDATA *,int *)
0x1800179eb  mov     ebx, eax
0x1800179ed  test    eax, eax
0x1800179ef  jz      short loc_180017A06
0x1800179f1  mov     r8d, eax
0x1800179f4  mov     edx, eax
0x1800179f6  mov     ecx, 4D5019Bh
0x1800179fb  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x180017a01  mov     esi, [rbp+arg_10]
0x180017a04  jmp     short loc_180017A0B
0x180017a06  mov     esi, [rbp+arg_10]
0x180017a09  xor     ebx, ebx
0x180017a0b  test    r14, r14
0x180017a0e  jz      short loc_180017A19
0x180017a10  mov     rcx, r14; hMem
0x180017a13  call    cs:__imp_LocalFree
0x180017a19  test    rdi, rdi
0x180017a1c  jz      short loc_180017A27
0x180017a1e  mov     rcx, rdi; hMem
0x180017a21  call    cs:__imp_LocalFree
0x180017a27  mov     rcx, [rbp+var_18]; hMem
0x180017a2b  test    rcx, rcx
0x180017a2e  jz      short loc_180017A36
0x180017a30  call    cs:__imp_LocalFree
0x180017a36  mov     rax, [rbp+arg_18]
0x180017a3a  mov     [rax], esi
0x180017a3c  mov     eax, ebx
0x180017a3e  mov     rbx, [rsp+60h+arg_0]
0x180017a46  add     rsp, 60h
0x180017a4a  pop     r15
0x180017a4c  pop     r14
0x180017a4e  pop     r13
0x180017a50  pop     r12
0x180017a52  pop     rdi
0x180017a53  pop     rsi
0x180017a54  pop     rbp
0x180017a55  retn
```
