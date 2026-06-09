# SpDecryptToken

- ea: `0x1800035b4`
- end: `0x1800039db`
- name: `SpDecryptToken`
- size: `1063`
- prototype: `__int64 __fastcall(PCtxtHandle phContext, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001b50`
- `0x180002560`

## callees

- `0x1800035b4`
- `0x180003dd9`
- `0x180003de5`
- `0x180003df1`
- `0x180003e20`

## import_xrefs

- `SspiCli!DecryptMessage` at `0x18000372d`
- `SspiCli!DecryptMessage` at `0x180003959`
- `SspiCli!DecryptMessage` at `0x18000372d`
- `SspiCli!DecryptMessage` at `0x180003959`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003690`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000399e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000399e`
- `NTASN1!__imp_ASN1DER_DecTagLength` at `0x1800037f4`
- `NTASN1!__imp_ASN1DER_DecTagLength` at `0x1800037f4`

## pseudocode

```c
__int64 __fastcall SpDecryptToken(PCtxtHandle phContext, __int64 a2, int a3)
{
  unsigned int v6; // r15d
  int v7; // r14d
  char *v8; // rsi
  bool v9; // cf
  unsigned int *v10; // rdx
  size_t v11; // r12
  _QWORD *v12; // r8
  int dwLower_high; // r9d
  unsigned int v14; // ebx
  SIZE_T v15; // rbx
  char *v16; // rax
  const void *dwLower; // rdx
  SECURITY_STATUS v18; // eax
  unsigned int *v19; // rdx
  const void **v20; // r14
  __int64 v21; // rcx
  __int64 v22; // rax
  void *v23; // rcx
  int v24; // r14d
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  int v27; // eax
  struct _SecBufferDesc pMessage; // [rsp+28h] [rbp-91h] BYREF
  int v30; // [rsp+38h] [rbp-81h] BYREF
  int v31; // [rsp+3Ch] [rbp-7Dh]
  _DWORD *v32; // [rsp+40h] [rbp-79h]
  __int64 v33; // [rsp+48h] [rbp-71h] BYREF
  char *v34; // [rsp+50h] [rbp-69h] BYREF
  __int64 dwUpper_low; // [rsp+58h] [rbp-61h]
  char *v36; // [rsp+60h] [rbp-59h]
  char *v37; // [rsp+68h] [rbp-51h]
  __int64 v38; // [rsp+70h] [rbp-49h]
  __int64 v39; // [rsp+78h] [rbp-41h]
  __int128 v40; // [rsp+80h] [rbp-39h]
  unsigned int v41; // [rsp+90h] [rbp-29h] BYREF
  int v42; // [rsp+94h] [rbp-25h]
  char *v43; // [rsp+98h] [rbp-21h]
  unsigned int Size; // [rsp+A0h] [rbp-19h]
  int Size_4; // [rsp+A4h] [rbp-15h]
  void *Src; // [rsp+A8h] [rbp-11h]
  int v47; // [rsp+B4h] [rbp-5h]
  int v48; // [rsp+C4h] [rbp+Bh]

  v31 = a3;
  memset_0(&v41, 0, 0x40u);
  pMessage = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(&v34, 0, 0x40u);
  v9 = *(_DWORD *)(a2 + 4) == 0;
  v30 = 0;
  v33 = 0;
  if ( v9 )
    goto LABEL_7;
  v10 = *(unsigned int **)(a2 + 8);
  if ( !v10 )
    goto LABEL_7;
  v11 = *v10;
  if ( !(_DWORD)v11 )
    goto LABEL_7;
  v12 = (_QWORD *)*((_QWORD *)v10 + 1);
  if ( !v12 )
    goto LABEL_7;
  dwLower_high = HIDWORD(phContext[2].dwLower);
  if ( ((a3 != 0 ? 0x8000 : 0x10000) & dwLower_high) != 0 )
  {
    if ( *(_DWORD *)(a2 + 4) >= 2u )
    {
      v7 = *v10;
      v6 = v11 - HIDWORD(phContext[7].dwUpper);
      if ( HIDWORD(phContext[7].dwUpper) < (unsigned int)v11 )
      {
        v15 = *v10;
        v16 = (char *)LocalAlloc(0x40u, v15);
        v8 = v16;
        if ( v16 )
        {
          memcpy_0(v16, *(const void **)(*(_QWORD *)(a2 + 8) + 8LL), v11);
          if ( LODWORD(phContext[7].dwUpper) )
          {
            dwLower = (const void *)phContext[7].dwLower;
            if ( dwLower )
              memcpy_0(v8, dwLower, LODWORD(phContext[7].dwUpper));
          }
          while ( 1 )
          {
            v41 = v6;
            v42 = 1;
            Size_4 = 0;
            v43 = &v8[v15 - v6];
            v47 = 0;
            v48 = 0;
            pMessage.cBuffers = 4;
            pMessage.ulVersion = 0;
            pMessage.pBuffers = (PSecBuffer)&v41;
            v18 = DecryptMessage(phContext, &pMessage, 0, 0);
            v14 = v18;
            if ( v18 )
            {
              if ( v18 != 590625 )
                break;
            }
            v19 = 0;
            v20 = 0;
            v21 = 0;
            v22 = 0;
            do
            {
              if ( *(int *)((char *)&v42 + v22) == 1 )
              {
                v19 = (unsigned int *)((char *)&v41 + v22);
              }
              else if ( *(int *)((char *)&v42 + v22) == 5 )
              {
                v20 = (const void **)((char *)&v41 + v22);
              }
              ++v21;
              v22 += 16;
            }
            while ( v21 != 4 );
            v32 = v19;
            if ( !v19 )
              goto LABEL_44;
            if ( v14 == 590625 )
            {
              if ( !v31 )
                break;
              if ( !v20 || (v25 = *(_QWORD *)(a2 + 8), *(_DWORD *)v20 > *(_DWORD *)v25) )
              {
LABEL_44:
                v14 = -2146893052;
                break;
              }
              memcpy_0(*(void **)(v25 + 8), v20[1], *(unsigned int *)v20);
              **(_DWORD **)(a2 + 8) = *(_DWORD *)v20;
              break;
            }
            memmove_0(&v8[LODWORD(phContext[7].dwUpper)], *((const void **)v19 + 1), *v19);
            LODWORD(phContext[7].dwUpper) += *v32;
            if ( v20 )
              v6 = *(_DWORD *)v20;
            else
              v6 = 0;
            dwUpper_low = LODWORD(phContext[7].dwUpper);
            v34 = v8;
            v37 = &v8[dwUpper_low];
            v36 = v8;
            v40 = 0;
            v38 = 0;
            v39 = 0;
            if ( (unsigned int)ASN1DER_DecTagLength(&v34, &v30, &v33) )
            {
              v14 = -2146893048;
              break;
            }
            if ( v37 >= &v36[v33] )
            {
              v14 = 0;
LABEL_32:
              if ( v37 >= &v36[v33] )
              {
                memcpy_0(*(void **)(*(_QWORD *)(a2 + 8) + 8LL), v8, LODWORD(phContext[7].dwUpper));
                **(_DWORD **)(a2 + 8) = phContext[7].dwUpper;
                if ( v20 )
                {
                  *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) = *(_DWORD *)v20;
                  *(_DWORD *)(*(_QWORD *)(a2 + 8) + 20LL) = *((_DWORD *)v20 + 1);
                }
              }
              else
              {
                v14 = -2146893032;
              }
              break;
            }
            if ( !v20 )
              goto LABEL_32;
            v15 = v11;
          }
          v7 = v11;
        }
        else
        {
          v14 = -2146893056;
        }
        goto LABEL_35;
      }
    }
LABEL_7:
    v14 = -2146892963;
    goto LABEL_35;
  }
  if ( (dwLower_high & 0x800) == 0 || (unsigned int)v11 < 8 )
    goto LABEL_49;
  if ( *v12 > 0xFFFFFFFF )
  {
    v14 = -1073741675;
    goto LABEL_35;
  }
  v26 = *(unsigned int *)v12;
  if ( v26 > v11 - 8 )
  {
LABEL_49:
    v14 = -2146893048;
    goto LABEL_35;
  }
  v41 = *(_DWORD *)v12;
  v43 = (char *)(v12 + 1);
  v42 = 2;
  Src = (char *)v12 + v26 + 8;
  v27 = *v10;
  Size_4 = 1;
  pMessage.cBuffers = 2;
  Size = v27 - v26 - 8;
  pMessage.ulVersion = 0;
  pMessage.pBuffers = (PSecBuffer)&v41;
  v14 = DecryptMessage(phContext, &pMessage, 0, 0);
  if ( !v14 )
  {
    **(_DWORD **)(a2 + 8) = Size;
    memmove_0(*(void **)(*(_QWORD *)(a2 + 8) + 8LL), Src, Size);
  }
LABEL_35:
  v23 = (void *)phContext[7].dwLower;
  if ( v23 )
  {
    LocalFree(v23);
    phContext[7].dwLower = 0;
  }
  if ( v14 == -2146893032 )
  {
    phContext[7].dwLower = (ULONG_PTR)v8;
    v24 = v7 - v6;
  }
  else
  {
    if ( v8 )
      LocalFree(v8);
    LODWORD(phContext[7].dwUpper) = 0;
    v24 = 0;
  }
  HIDWORD(phContext[7].dwUpper) = v24;
  return v14;
}

```

## disassembly

```asm
0x1800035b4  mov     [rsp-8+arg_10], rbx
0x1800035b9  push    rbp
0x1800035ba  push    rsi
0x1800035bb  push    rdi
0x1800035bc  push    r12
0x1800035be  push    r13
0x1800035c0  push    r14
0x1800035c2  push    r15
0x1800035c4  lea     rbp, [rsp-27h]
0x1800035c9  sub     rsp, 0E0h
0x1800035d0  mov     rax, cs:__security_cookie
0x1800035d7  xor     rax, rsp
0x1800035da  mov     [rbp+57h+var_40], rax
0x1800035de  mov     ebx, r8d
0x1800035e1  mov     r13, rdx
0x1800035e4  mov     rdi, rcx
0x1800035e7  mov     [rbp+57h+var_D4], ebx
0x1800035ea  mov     r12d, 40h ; '@'
0x1800035f0  lea     rcx, [rbp+57h+var_80]; void *
0x1800035f4  mov     r8d, r12d; Size
0x1800035f7  xor     edx, edx; Val
0x1800035f9  call    memset_0
0x1800035fe  xorps   xmm0, xmm0
0x180003601  lea     rcx, [rbp+57h+var_C0]; void *
0x180003605  mov     r8d, r12d; Size
0x180003608  xor     edx, edx; Val
0x18000360a  movups  xmmword ptr [rsp+110h+pMessage.ulVersion], xmm0
0x18000360f  xor     r15d, r15d
0x180003612  xor     r14d, r14d
0x180003615  xor     esi, esi
0x180003617  call    memset_0
0x18000361c  cmp     dword ptr [r13+4], 1
0x180003621  mov     [rsp+110h+var_D8], esi
0x180003625  mov     [rbp+57h+var_C8], rsi
0x180003629  jb      short loc_18000366B
0x18000362b  mov     rdx, [r13+8]
0x18000362f  test    rdx, rdx
0x180003632  jz      short loc_18000366B
0x180003634  mov     r12d, [rdx]
0x180003637  test    r12d, r12d
0x18000363a  jz      short loc_18000366B
0x18000363c  mov     r8, [rdx+8]
0x180003640  test    r8, r8
0x180003643  jz      short loc_18000366B
0x180003645  mov     r9d, [rdi+24h]
0x180003649  mov     eax, ebx
0x18000364b  neg     eax
0x18000364d  sbb     ecx, ecx
0x18000364f  and     ecx, 0FFFF8000h
0x180003655  add     ecx, 10000h
0x18000365b  test    r9d, ecx
0x18000365e  jz      loc_1800038DA
0x180003664  cmp     dword ptr [r13+4], 2
0x180003669  jnb     short loc_180003675
0x18000366b  mov     ebx, 8009035Dh
0x180003670  jmp     loc_18000382D
0x180003675  mov     r15d, r12d
0x180003678  mov     r14d, r12d
0x18000367b  sub     r15d, [rdi+7Ch]
0x18000367f  cmp     [rdi+7Ch], r12d
0x180003683  jnb     short loc_18000366B
0x180003685  mov     rdx, r12; uBytes
0x180003688  mov     ecx, 40h ; '@'; uFlags
0x18000368d  mov     rbx, r12
0x180003690  call    cs:__imp_LocalAlloc
0x180003696  mov     rsi, rax
0x180003699  test    rax, rax
0x18000369c  jnz     short loc_1800036A8
0x18000369e  mov     ebx, 80090300h
0x1800036a3  jmp     loc_18000382D
0x1800036a8  mov     rdx, [r13+8]
0x1800036ac  mov     r8, rbx; Size
0x1800036af  mov     rcx, rsi; void *
0x1800036b2  mov     rdx, [rdx+8]; Src
0x1800036b6  call    memcpy_0
0x1800036bb  cmp     dword ptr [rdi+78h], 0
0x1800036bf  jbe     short loc_1800036D6
0x1800036c1  mov     rdx, [rdi+70h]; Src
0x1800036c5  test    rdx, rdx
0x1800036c8  jz      short loc_1800036D6
0x1800036ca  mov     r8d, [rdi+78h]; Size
0x1800036ce  mov     rcx, rsi; void *
0x1800036d1  call    memcpy_0
0x1800036d6  mov     eax, r15d
0x1800036d9  lea     rdx, [rsp+110h+pMessage]; pMessage
0x1800036de  mov     rcx, rbx
0x1800036e1  mov     [rbp+57h+var_80], r15d
0x1800036e5  sub     rcx, rax
0x1800036e8  mov     [rbp+57h+var_7C], 1
0x1800036ef  add     rcx, rsi
0x1800036f2  mov     dword ptr [rbp+57h+Size+4], 0
0x1800036f9  mov     [rbp+57h+var_78], rcx
0x1800036fd  lea     rax, [rbp+57h+var_80]
0x180003701  mov     rcx, rdi; phContext
0x180003704  mov     [rbp+57h+var_5C], 0
0x18000370b  xor     r9d, r9d; pfQOP
0x18000370e  mov     [rbp+57h+var_4C], 0
0x180003715  xor     r8d, r8d; MessageSeqNo
0x180003718  mov     [rsp+110h+pMessage.cBuffers], 4
0x180003720  mov     [rsp+110h+pMessage.ulVersion], 0
0x180003728  mov     [rsp+110h+pMessage.pBuffers], rax
0x18000372d  call    cs:__imp_DecryptMessage
0x180003733  mov     ebx, eax
0x180003735  test    eax, eax
0x180003737  jz      short loc_180003744
0x180003739  cmp     eax, 90321h
0x18000373e  jnz     loc_18000382A
0x180003744  xor     edx, edx
0x180003746  xor     r14d, r14d
0x180003749  xor     ecx, ecx
0x18000374b  xor     eax, eax
0x18000374d  cmp     [rbp+rax+57h+var_7C], 1
0x180003752  jnz     short loc_18000375D
0x180003754  lea     rdx, [rbp+57h+var_80]
0x180003758  add     rdx, rax
0x18000375b  jmp     short loc_18000376B
0x18000375d  cmp     [rbp+rax+57h+var_7C], 5
0x180003762  jnz     short loc_18000376B
0x180003764  lea     r14, [rbp+57h+var_80]
0x180003768  add     r14, rax
0x18000376b  inc     rcx
0x18000376e  add     rax, 10h
0x180003772  cmp     rcx, 4
0x180003776  jnz     short loc_18000374D
0x180003778  mov     [rbp+57h+var_D0], rdx
0x18000377c  test    rdx, rdx
0x18000377f  jz      loc_1800038A7
0x180003785  cmp     ebx, 90321h
0x18000378b  jz      loc_18000389C
0x180003791  mov     ecx, [rdi+78h]
0x180003794  mov     r8d, [rdx]; Size
0x180003797  add     rcx, rsi; void *
0x18000379a  mov     rdx, [rdx+8]; Src
0x18000379e  call    memmove_0
0x1800037a3  mov     rcx, [rbp+57h+var_D0]
0x1800037a7  mov     eax, [rcx]
0x1800037a9  add     [rdi+78h], eax
0x1800037ac  test    r14, r14
0x1800037af  jz      short loc_1800037B6
0x1800037b1  mov     r15d, [r14]
0x1800037b4  jmp     short loc_1800037B9
0x1800037b6  xor     r15d, r15d
0x1800037b9  mov     eax, [rdi+78h]
0x1800037bc  lea     r8, [rbp+57h+var_C8]
0x1800037c0  mov     [rbp+57h+var_B8], rax
0x1800037c4  lea     rdx, [rsp+110h+var_D8]
0x1800037c9  add     rax, rsi
0x1800037cc  mov     [rbp+57h+var_C0], rsi
0x1800037d0  xorps   xmm0, xmm0
0x1800037d3  mov     [rbp+57h+var_A8], rax
0x1800037d7  lea     rcx, [rbp+57h+var_C0]
0x1800037db  mov     [rbp+57h+var_B0], rsi
0x1800037df  movdqa  [rbp+57h+var_90], xmm0
0x1800037e4  mov     [rbp+57h+var_A0], 0
0x1800037ec  mov     [rbp+57h+var_98], 0
0x1800037f4  call    cs:__imp_ASN1DER_DecTagLength
0x1800037fa  test    eax, eax
0x1800037fc  jnz     loc_180003895
0x180003802  mov     rdx, [rbp+57h+var_B0]
0x180003806  add     rdx, [rbp+57h+var_C8]
0x18000380a  cmp     [rbp+57h+var_A8], rdx
0x18000380e  jnb     short loc_18000381D
0x180003810  test    r14, r14
0x180003813  jz      short loc_18000381F
0x180003815  mov     rbx, r12
0x180003818  jmp     loc_1800036D6
0x18000381d  xor     ebx, ebx
0x18000381f  cmp     [rbp+57h+var_A8], rdx
0x180003823  jnb     short loc_18000385C
0x180003825  mov     ebx, 80090318h
0x18000382a  mov     r14d, r12d
0x18000382d  mov     rcx, [rdi+70h]; hMem
0x180003831  test    rcx, rcx
0x180003834  jz      short loc_180003844
0x180003836  call    cs:__imp_LocalFree
0x18000383c  mov     qword ptr [rdi+70h], 0
0x180003844  cmp     ebx, 80090318h
0x18000384a  jnz     loc_180003996
0x180003850  mov     [rdi+70h], rsi
0x180003854  sub     r14d, r15d
0x180003857  jmp     loc_1800039AE
0x18000385c  mov     rcx, [r13+8]
0x180003860  mov     rdx, rsi; Src
0x180003863  mov     r8d, [rdi+78h]; Size
0x180003867  mov     rcx, [rcx+8]; void *
0x18000386b  call    memcpy_0
0x180003870  mov     rcx, [r13+8]
0x180003874  mov     eax, [rdi+78h]
0x180003877  mov     [rcx], eax
0x180003879  test    r14, r14
0x18000387c  jz      short loc_18000382A
0x18000387e  mov     rcx, [r13+8]
0x180003882  mov     eax, [r14]
0x180003885  mov     [rcx+10h], eax
0x180003888  mov     rcx, [r13+8]
0x18000388c  mov     eax, [r14+4]
0x180003890  mov     [rcx+14h], eax
0x180003893  jmp     short loc_18000382A
0x180003895  mov     ebx, 80090308h
0x18000389a  jmp     short loc_18000382A
0x18000389c  cmp     [rbp+57h+var_D4], 0
0x1800038a0  jz      short loc_18000382A
0x1800038a2  test    r14, r14
0x1800038a5  jnz     short loc_1800038B1
0x1800038a7  mov     ebx, 80090304h
0x1800038ac  jmp     loc_18000382A
0x1800038b1  mov     rcx, [r13+8]
0x1800038b5  mov     eax, [r14]
0x1800038b8  cmp     eax, [rcx]
0x1800038ba  ja      short loc_1800038A7
0x1800038bc  mov     rdx, [r14+8]; Src
0x1800038c0  mov     r8d, eax; Size
0x1800038c3  mov     rcx, [rcx+8]; void *
0x1800038c7  call    memcpy_0
0x1800038cc  mov     rcx, [r13+8]
0x1800038d0  mov     eax, [r14]
0x1800038d3  mov     [rcx], eax
0x1800038d5  jmp     loc_18000382A
0x1800038da  bt      r9d, 0Bh
0x1800038df  jnb     short loc_1800038E7
0x1800038e1  cmp     r12d, 8
0x1800038e5  jnb     short loc_1800038F1
0x1800038e7  mov     ebx, 80090308h
0x1800038ec  jmp     loc_18000382D
0x1800038f1  mov     eax, 0FFFFFFFFh
0x1800038f6  cmp     [r8], rax
0x1800038f9  ja      loc_18000398C
0x1800038ff  mov     ecx, [r8]
0x180003902  lea     rax, [r12-8]
0x180003907  cmp     rcx, rax
0x18000390a  ja      short loc_1800038E7
0x18000390c  lea     rax, [r8+8]
0x180003910  mov     [rbp+57h+var_80], ecx
0x180003913  mov     [rbp+57h+var_78], rax
0x180003917  xor     r9d, r9d; pfQOP
0x18000391a  add     rax, rcx
0x18000391d  mov     [rbp+57h+var_7C], 2
0x180003924  mov     [rbp+57h+Src], rax
0x180003928  xor     r8d, r8d; MessageSeqNo
0x18000392b  mov     eax, [rdx]
0x18000392d  lea     rdx, [rsp+110h+pMessage]; pMessage
0x180003932  sub     eax, ecx
0x180003934  mov     dword ptr [rbp+57h+Size+4], 1
0x18000393b  sub     eax, 8
0x18000393e  mov     [rsp+110h+pMessage.cBuffers], 2
0x180003946  mov     dword ptr [rbp+57h+Size], eax
0x180003949  mov     rcx, rdi; phContext
0x18000394c  lea     rax, [rbp+57h+var_80]
0x180003950  mov     [rsp+110h+pMessage.ulVersion], esi
0x180003954  mov     [rsp+110h+pMessage.pBuffers], rax
0x180003959  call    cs:__imp_DecryptMessage
0x18000395f  mov     ebx, eax
0x180003961  test    eax, eax
0x180003963  jnz     loc_18000382D
0x180003969  mov     rcx, [r13+8]
0x18000396d  mov     eax, dword ptr [rbp+57h+Size]
0x180003970  mov     [rcx], eax
0x180003972  mov     rcx, [r13+8]
0x180003976  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000397a  mov     rdx, [rbp+57h+Src]; Src
0x18000397e  mov     rcx, [rcx+8]; void *
0x180003982  call    memmove_0
0x180003987  jmp     loc_18000382D
0x18000398c  mov     ebx, 0C0000095h
0x180003991  jmp     loc_18000382D
0x180003996  test    rsi, rsi
0x180003999  jz      short loc_1800039A4
0x18000399b  mov     rcx, rsi; hMem
0x18000399e  call    cs:__imp_LocalFree
0x1800039a4  mov     dword ptr [rdi+78h], 0
0x1800039ab  xor     r14d, r14d
0x1800039ae  mov     [rdi+7Ch], r14d
0x1800039b2  mov     eax, ebx
0x1800039b4  mov     rcx, [rbp+57h+var_40]
0x1800039b8  xor     rcx, rsp; StackCookie
0x1800039bb  call    __security_check_cookie
0x1800039c0  mov     rbx, [rsp+110h+arg_10]
0x1800039c8  add     rsp, 0E0h
0x1800039cf  pop     r15
0x1800039d1  pop     r14
0x1800039d3  pop     r13
0x1800039d5  pop     r12
0x1800039d7  pop     rdi
0x1800039d8  pop     rsi
0x1800039d9  pop     rbp
0x1800039da  retn
```
