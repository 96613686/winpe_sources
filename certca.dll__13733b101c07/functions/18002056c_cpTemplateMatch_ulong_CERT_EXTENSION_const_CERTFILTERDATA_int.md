# cpTemplateMatch(ulong,_CERT_EXTENSION const *,_CERTFILTERDATA *,int *)

- ea: `0x18002056c`
- end: `0x1800207a8`
- name: `?cpTemplateMatch@@YAJKPEBU_CERT_EXTENSION@@PEAU_CERTFILTERDATA@@PEAH@Z`
- size: `572`
- prototype: `__int64 __fastcall(DWORD cExtensions, CERT_EXTENSION *__attribute__((__org_arrdim(0,0))) rgExtensions, struct _CERTFILTERDATA *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001fb04`

## callees

- `0x180008400`
- `0x180008610`
- `0x180012450`
- `0x18001aea4`
- `0x18001dfa0`
- `0x18001e080`
- `0x18001eba8`
- `0x180020378`
- `0x18002056c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020782`
- `CRYPT32!CertFindExtension` at `0x1800205c0`
- `CRYPT32!CertFindExtension` at `0x180020621`
- `CRYPT32!CertFindExtension` at `0x1800205c0`
- `CRYPT32!CertFindExtension` at `0x180020621`

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
  __int64 cbData; // r9
  BYTE *pbData; // r8
  __int64 v17; // r8
  unsigned __int8 *v18; // rcx
  int v19; // edx
  int v20; // eax
  unsigned __int8 *v21; // rcx
  int v22; // edx
  int v23; // eax
  const unsigned __int16 *v24; // rdx
  int v25; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL v28; // [rsp+48h] [rbp-18h]
  unsigned __int16 *v29; // [rsp+50h] [rbp-10h] BYREF
  int v30; // [rsp+B0h] [rbp+50h] BYREF
  int *v31; // [rsp+B8h] [rbp+58h]

  v31 = a4;
  v4 = 0;
  v5 = (struct _CERTFILTERDATA *)((char *)a3 + 40);
  v6 = 0;
  v30 = 0;
  v7 = 0;
  hMem = 0;
  v29 = 0;
  v28 = 0;
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
    if ( !(unsigned int)myDecodeObjectEx(1, 64, pbData, cbData, 0) )
    {
      v13 = myHLastError();
      CSPrintErrorLineFile(0x4B4019Bu, v13);
      goto LABEL_31;
    }
    v18 = (unsigned __int8 *)*((_QWORD *)a3 + 7);
    if ( v18 )
    {
      v17 = *(_QWORD *)v28 - (_QWORD)v18;
      do
      {
        v19 = v18[v17];
        v20 = *v18 - v19;
        if ( v20 )
          break;
        ++v18;
      }
      while ( v19 );
      if ( !v20 )
        goto LABEL_6;
    }
    v21 = (unsigned __int8 *)*((_QWORD *)a3 + 8);
    if ( v21 )
    {
      v17 = *(_QWORD *)v28 - (_QWORD)v21;
      do
      {
        v22 = v21[v17];
        v23 = *v21 - v22;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v22 );
      if ( !v23 )
        goto LABEL_6;
    }
    if ( !(unsigned int)myConvertSzToWsz(&v29, *(const char **)v28, v17) )
    {
      v13 = -2147024882;
      CSPrintErrorLineFile(0x4C2019Bu, -2147024882);
      v7 = v29;
      goto LABEL_31;
    }
    v7 = v29;
    if ( CERTFILTERSTRING::Match(v5, v29) )
    {
LABEL_6:
      v4 = 1;
    }
    else
    {
LABEL_24:
      if ( v6 || v7 )
      {
        v24 = v6;
        if ( v7 )
          v24 = v7;
        v25 = cpTemplateMatch2(v7 != 0, v24, a3, &v30);
        v13 = v25;
        if ( v25 )
        {
          CSPrintErrorLineFileData2(0, 0x4D5019Bu, v25, v25);
          v4 = v30;
          goto LABEL_31;
        }
        v4 = v30;
      }
    }
  }
  v13 = 0;
LABEL_31:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  if ( v28 )
    LocalFree(v28);
  *v31 = v4;
  return v13;
}

```

## disassembly

```asm
0x18002056c  mov     [rsp-38h+arg_0], rbx
0x180020571  mov     [rsp-38h+arg_18], r9
0x180020576  push    rbp
0x180020577  push    rsi
0x180020578  push    rdi
0x180020579  push    r12
0x18002057b  push    r13
0x18002057d  push    r14
0x18002057f  push    r15
0x180020581  mov     rbp, rsp
0x180020584  sub     rsp, 60h
0x180020588  xor     esi, esi
0x18002058a  lea     rbx, [r8+28h]
0x18002058e  xor     r14d, r14d
0x180020591  mov     [rbp+arg_10], esi
0x180020594  xor     edi, edi
0x180020596  mov     [rbp+hMem], r14
0x18002059a  mov     r13, r8
0x18002059d  mov     r15, rdx
0x1800205a0  mov     r12d, ecx
0x1800205a3  mov     [rbp+var_10], rdi
0x1800205a7  mov     [rbp+var_18], rsi
0x1800205ab  cmp     [rbx], rsi
0x1800205ae  jz      loc_18002075B
0x1800205b4  mov     r8, rdx; rgExtensions
0x1800205b7  mov     edx, ecx; cExtensions
0x1800205b9  lea     rcx, a136141311202_0; "1.3.6.1.4.1.311.20.2"
0x1800205c0  call    cs:__imp_CertFindExtension
0x1800205c6  test    rax, rax
0x1800205c9  jz      short loc_180020614
0x1800205cb  lea     rcx, [rax+10h]; struct _CRYPTOAPI_BLOB *
0x1800205cf  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x1800205d3  call    ?myDecodeUnicodeName@@YAJPEBU_CRYPTOAPI_BLOB@@PEAPEAG@Z; myDecodeUnicodeName(_CRYPTOAPI_BLOB const *,ushort * *)
0x1800205d8  mov     ebx, eax
0x1800205da  test    eax, eax
0x1800205dc  jz      short loc_1800205F3
0x1800205de  mov     edx, eax; int
0x1800205e0  mov     ecx, 495019Bh; unsigned int
0x1800205e5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800205ea  mov     r14, [rbp+hMem]
0x1800205ee  jmp     loc_18002075D
0x1800205f3  mov     r14, [rbp+hMem]
0x1800205f7  lea     rbx, [r13+28h]
0x1800205fb  mov     rdx, r14; unsigned __int16 *
0x1800205fe  mov     rcx, rbx; this
0x180020601  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x180020606  test    al, al
0x180020608  jz      short loc_180020614
0x18002060a  mov     esi, 1
0x18002060f  jmp     loc_18002075B
0x180020614  mov     r8, r15; rgExtensions
0x180020617  lea     rcx, a136141311217_0; "1.3.6.1.4.1.311.21.7"
0x18002061e  mov     edx, r12d; cExtensions
0x180020621  call    cs:__imp_CertFindExtension
0x180020627  test    rax, rax
0x18002062a  jz      loc_180020718
0x180020630  mov     r9d, [rax+10h]
0x180020634  lea     rcx, [rbp+hMem]
0x180020638  mov     r8, [rax+18h]
0x18002063c  mov     edx, 40h ; '@'
0x180020641  mov     [rsp+60h+var_28], rcx
0x180020646  lea     rcx, [rbp+var_18]
0x18002064a  mov     [rsp+60h+var_30], rcx
0x18002064f  mov     dword ptr [rbp+hMem], esi
0x180020652  lea     ecx, [rdx-3Fh]
0x180020655  mov     [rsp+60h+var_40], esi
0x180020659  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18002065e  test    eax, eax
0x180020660  jnz     short loc_18002067A
0x180020662  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020667  mov     edx, eax; int
0x180020669  mov     ecx, 4B4019Bh; unsigned int
0x18002066e  mov     ebx, eax
0x180020670  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180020675  jmp     loc_18002075D
0x18002067a  mov     rcx, [r13+38h]
0x18002067e  test    rcx, rcx
0x180020681  jz      short loc_1800206A8
0x180020683  mov     rax, [rbp+var_18]
0x180020687  mov     r8, [rax]
0x18002068a  sub     r8, rcx
0x18002068d  movzx   eax, byte ptr [rcx]
0x180020690  movzx   edx, byte ptr [rcx+r8]
0x180020695  sub     eax, edx
0x180020697  jnz     short loc_1800206A0
0x180020699  inc     rcx
0x18002069c  test    edx, edx
0x18002069e  jnz     short loc_18002068D
0x1800206a0  test    eax, eax
0x1800206a2  jz      loc_18002060A
0x1800206a8  mov     rcx, [r13+40h]
0x1800206ac  test    rcx, rcx
0x1800206af  jz      short loc_1800206D6
0x1800206b1  mov     rax, [rbp+var_18]
0x1800206b5  mov     r8, [rax]
0x1800206b8  sub     r8, rcx; int
0x1800206bb  movzx   eax, byte ptr [rcx]
0x1800206be  movzx   edx, byte ptr [rcx+r8]
0x1800206c3  sub     eax, edx
0x1800206c5  jnz     short loc_1800206CE
0x1800206c7  inc     rcx
0x1800206ca  test    edx, edx
0x1800206cc  jnz     short loc_1800206BB
0x1800206ce  test    eax, eax
0x1800206d0  jz      loc_18002060A
0x1800206d6  mov     rdx, [rbp+var_18]
0x1800206da  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800206de  mov     rdx, [rdx]; char *
0x1800206e1  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x1800206e6  test    eax, eax
0x1800206e8  jnz     short loc_180020701
0x1800206ea  mov     ebx, 8007000Eh
0x1800206ef  mov     ecx, 4C2019Bh; unsigned int
0x1800206f4  mov     edx, ebx; int
0x1800206f6  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800206fb  mov     rdi, [rbp+var_10]
0x1800206ff  jmp     short loc_18002075D
0x180020701  mov     rdi, [rbp+var_10]
0x180020705  mov     rcx, rbx; this
0x180020708  mov     rdx, rdi; unsigned __int16 *
0x18002070b  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x180020710  test    al, al
0x180020712  jnz     loc_18002060A
0x180020718  test    r14, r14
0x18002071b  jnz     short loc_180020722
0x18002071d  test    rdi, rdi
0x180020720  jz      short loc_18002075B
0x180020722  test    rdi, rdi
0x180020725  lea     r9, [rbp+arg_10]; int *
0x180020729  mov     rdx, r14
0x18002072c  mov     r8, r13; struct _CERTFILTERDATA *
0x18002072f  cmovnz  rdx, rdi; unsigned __int16 *
0x180020733  setnz   cl; bool
0x180020736  call    ?cpTemplateMatch2@@YAJ_NPEBGPEAU_CERTFILTERDATA@@PEAH@Z; cpTemplateMatch2(bool,ushort const *,_CERTFILTERDATA *,int *)
0x18002073b  mov     ebx, eax
0x18002073d  test    eax, eax
0x18002073f  jz      short loc_180020758
0x180020741  mov     r9d, eax; int
0x180020744  mov     r8d, eax; int
0x180020747  mov     edx, 4D5019Bh; unsigned int
0x18002074c  xor     ecx, ecx; unsigned __int16 *
0x18002074e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180020753  mov     esi, [rbp+arg_10]
0x180020756  jmp     short loc_18002075D
0x180020758  mov     esi, [rbp+arg_10]
0x18002075b  xor     ebx, ebx
0x18002075d  test    r14, r14
0x180020760  jz      short loc_18002076B
0x180020762  mov     rcx, r14; hMem
0x180020765  call    cs:__imp_LocalFree
0x18002076b  test    rdi, rdi
0x18002076e  jz      short loc_180020779
0x180020770  mov     rcx, rdi; hMem
0x180020773  call    cs:__imp_LocalFree
0x180020779  mov     rcx, [rbp+var_18]; hMem
0x18002077d  test    rcx, rcx
0x180020780  jz      short loc_180020788
0x180020782  call    cs:__imp_LocalFree
0x180020788  mov     rax, [rbp+arg_18]
0x18002078c  mov     [rax], esi
0x18002078e  mov     eax, ebx
0x180020790  mov     rbx, [rsp+60h+arg_0]
0x180020798  add     rsp, 60h
0x18002079c  pop     r15
0x18002079e  pop     r14
0x1800207a0  pop     r13
0x1800207a2  pop     r12
0x1800207a4  pop     rdi
0x1800207a5  pop     rsi
0x1800207a6  pop     rbp
0x1800207a7  retn
```
