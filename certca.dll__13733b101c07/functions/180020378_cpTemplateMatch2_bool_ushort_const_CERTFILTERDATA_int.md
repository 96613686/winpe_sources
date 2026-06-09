# cpTemplateMatch2(bool,ushort const *,_CERTFILTERDATA *,int *)

- ea: `0x180020378`
- end: `0x180020565`
- name: `?cpTemplateMatch2@@YAJ_NPEBGPEAU_CERTFILTERDATA@@PEAH@Z`
- size: `493`
- prototype: `__int64 __fastcall(char, const unsigned __int16 *, struct _CERTFILTERDATA *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002056c`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000d520`
- `0x18001dfa0`
- `0x18001eba8`
- `0x180020378`
- `0x18002128c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020530`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002053a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020530`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002053a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020543`

## pseudocode

```c
__int64 __fastcall cpTemplateMatch2(char a1, const unsigned __int16 *a2, struct _CERTFILTERDATA *a3, int *a4)
{
  HLOCAL v5; // r15
  int v6; // ebx
  int TemplateInfo; // eax
  char *v9; // r8
  unsigned __int8 *v10; // rax
  int v11; // edx
  int v12; // ecx
  unsigned __int8 *v13; // rax
  int v14; // edx
  int v15; // ecx
  unsigned int v16; // edi
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  HLOCAL v20; // [rsp+20h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-18h] BYREF
  HLOCAL v22; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL v23; // [rsp+38h] [rbp-8h] BYREF

  *a4 = 0;
  v5 = 0;
  hMem = 0;
  v22 = 0;
  v6 = 0;
  v20 = 0;
  v23 = 0;
  TemplateInfo = myLoadTemplateInfo(a2, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v22, (char **)&v20);
  if ( TemplateInfo )
  {
    CSPrintErrorLineFileData2(0, 0x42E019Bu, TemplateInfo, TemplateInfo);
LABEL_30:
    v16 = 0;
    goto LABEL_31;
  }
  if ( a1 )
  {
    if ( hMem )
    {
      if ( CERTFILTERSTRING::Match((struct _CERTFILTERDATA *)((char *)a3 + 40), (const unsigned __int16 *)hMem) )
        goto LABEL_19;
      v17 = (const unsigned __int16 *)*((_QWORD *)a3 + 6);
      if ( v17 && !(unsigned int)mylstrcmpNLSub((PCNZWCH)hMem, v17, -1, 1) )
      {
        v6 = 1;
        goto LABEL_30;
      }
    }
LABEL_25:
    if ( !v22 )
      goto LABEL_30;
    v18 = (const unsigned __int16 *)*((_QWORD *)a3 + 6);
    if ( !v18 || (unsigned int)mylstrcmpNLSub((PCNZWCH)v22, v18, -1, 1) )
    {
      if ( CERTFILTERSTRING::Match((struct _CERTFILTERDATA *)((char *)a3 + 40), (const unsigned __int16 *)v22) )
        v6 = 1;
      goto LABEL_30;
    }
    goto LABEL_19;
  }
  if ( !v20 )
    goto LABEL_25;
  v10 = (unsigned __int8 *)*((_QWORD *)a3 + 7);
  if ( v10 )
  {
    v9 = (char *)((_BYTE *)v20 - v10);
    do
    {
      v11 = (unsigned __int8)v9[(_QWORD)v10];
      v12 = *v10 - v11;
      if ( v12 )
        break;
      ++v10;
    }
    while ( v11 );
    if ( !v12 )
      goto LABEL_15;
  }
  v13 = (unsigned __int8 *)*((_QWORD *)a3 + 8);
  if ( v13 )
  {
    v9 = (char *)((_BYTE *)v20 - v13);
    do
    {
      v14 = (unsigned __int8)v9[(_QWORD)v13];
      v15 = *v13 - v14;
      if ( v15 )
        break;
      ++v13;
    }
    while ( v14 );
    if ( !v15 )
    {
LABEL_15:
      v6 = 1;
      goto LABEL_30;
    }
  }
  if ( (unsigned int)myConvertSzToWsz((unsigned __int16 **)&v23, (const char *)v20, (int)v9) )
  {
    v5 = v23;
    if ( CERTFILTERSTRING::Match((struct _CERTFILTERDATA *)((char *)a3 + 40), (const unsigned __int16 *)v23) )
    {
LABEL_19:
      v6 = 1;
      goto LABEL_30;
    }
    goto LABEL_25;
  }
  v16 = -2147024882;
  CSPrintErrorLineFile(0x43F019Bu, -2147024882);
  v5 = v23;
LABEL_31:
  LocalFree(hMem);
  LocalFree(v22);
  LocalFree(v20);
  LocalFree(v5);
  *a4 = v6;
  return v16;
}

```

## disassembly

```asm
0x180020378  mov     [rsp-18h+arg_0], rbx
0x18002037d  mov     [rsp-18h+arg_8], rdi
0x180020382  mov     [rsp-18h+arg_18], r9
0x180020387  push    rbp
0x180020388  push    r14
0x18002038a  push    r15
0x18002038c  mov     rbp, rsp
0x18002038f  sub     rsp, 40h
0x180020393  mov     r14b, cl
0x180020396  mov     rax, rdx
0x180020399  xor     ecx, ecx
0x18002039b  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18002039f  mov     [r9], ecx
0x1800203a2  mov     r15d, ecx
0x1800203a5  mov     [rbp+hMem], rcx
0x1800203a9  lea     r9, [rbp+var_20]; char **
0x1800203ad  mov     [rbp+var_10], rcx
0x1800203b1  mov     ebx, ecx
0x1800203b3  mov     [rbp+var_20], rcx
0x1800203b7  mov     rdi, r8
0x1800203ba  mov     [rbp+var_8], rcx
0x1800203be  lea     r8, [rbp+var_10]; unsigned __int16 **
0x1800203c2  mov     rcx, rax; unsigned __int16 *
0x1800203c5  call    ?myLoadTemplateInfo@@YAJPEBGPEAPEAG1PEAPEAD@Z; myLoadTemplateInfo(ushort const *,ushort * *,ushort * *,char * *)
0x1800203ca  test    eax, eax
0x1800203cc  jz      short loc_1800203E5
0x1800203ce  mov     r9d, eax; int
0x1800203d1  mov     r8d, eax; int
0x1800203d4  mov     edx, 42E019Bh; unsigned int
0x1800203d9  xor     ecx, ecx; unsigned __int16 *
0x1800203db  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800203e0  jmp     loc_180020520
0x1800203e5  mov     r9d, 1
0x1800203eb  test    r14b, r14b
0x1800203ee  jnz     loc_18002049D
0x1800203f4  cmp     [rbp+var_20], rbx
0x1800203f8  jz      loc_1800204E7
0x1800203fe  mov     rax, [rdi+38h]
0x180020402  test    rax, rax
0x180020405  jz      short loc_180020425
0x180020407  mov     r8, [rbp+var_20]
0x18002040b  sub     r8, rax; int
0x18002040e  movzx   ecx, byte ptr [rax]
0x180020411  movzx   edx, byte ptr [rax+r8]
0x180020416  sub     ecx, edx
0x180020418  jnz     short loc_180020421
0x18002041a  add     rax, r9
0x18002041d  test    edx, edx
0x18002041f  jnz     short loc_18002040E
0x180020421  test    ecx, ecx
0x180020423  jz      short loc_18002044C
0x180020425  mov     rax, [rdi+40h]
0x180020429  test    rax, rax
0x18002042c  jz      short loc_180020454
0x18002042e  mov     r8, [rbp+var_20]
0x180020432  sub     r8, rax
0x180020435  movzx   ecx, byte ptr [rax]
0x180020438  movzx   edx, byte ptr [rax+r8]
0x18002043d  sub     ecx, edx
0x18002043f  jnz     short loc_180020448
0x180020441  add     rax, r9
0x180020444  test    edx, edx
0x180020446  jnz     short loc_180020435
0x180020448  test    ecx, ecx
0x18002044a  jnz     short loc_180020454
0x18002044c  mov     ebx, r9d
0x18002044f  jmp     loc_180020520
0x180020454  mov     rdx, [rbp+var_20]; char *
0x180020458  lea     rcx, [rbp+var_8]; unsigned __int16 **
0x18002045c  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x180020461  test    eax, eax
0x180020463  jnz     short loc_18002047F
0x180020465  mov     edi, 8007000Eh
0x18002046a  mov     ecx, 43F019Bh; unsigned int
0x18002046f  mov     edx, edi; int
0x180020471  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180020476  mov     r15, [rbp+var_8]
0x18002047a  jmp     loc_180020522
0x18002047f  mov     r15, [rbp+var_8]
0x180020483  lea     rcx, [rdi+28h]; this
0x180020487  mov     rdx, r15; unsigned __int16 *
0x18002048a  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x18002048f  test    al, al
0x180020491  jz      short loc_1800204E1
0x180020493  mov     ebx, 1
0x180020498  jmp     loc_180020520
0x18002049d  cmp     [rbp+hMem], rbx
0x1800204a1  jz      short loc_1800204E7
0x1800204a3  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x1800204a7  lea     rcx, [rdi+28h]; this
0x1800204ab  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x1800204b0  test    al, al
0x1800204b2  jnz     short loc_180020493
0x1800204b4  mov     rdx, [rdi+30h]; unsigned __int16 *
0x1800204b8  test    rdx, rdx
0x1800204bb  jz      short loc_1800204E1
0x1800204bd  mov     rcx, [rbp+hMem]; lpString1
0x1800204c1  mov     r14d, 1
0x1800204c7  mov     r9b, r14b; bool
0x1800204ca  or      r8d, 0FFFFFFFFh; int
0x1800204ce  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800204d3  test    eax, eax
0x1800204d5  jnz     short loc_1800204DC
0x1800204d7  mov     ebx, r14d
0x1800204da  jmp     short loc_180020520
0x1800204dc  mov     r9, r14
0x1800204df  jmp     short loc_1800204E7
0x1800204e1  mov     r9d, 1; bool
0x1800204e7  cmp     [rbp+var_10], rbx
0x1800204eb  jz      short loc_180020520
0x1800204ed  mov     rdx, [rdi+30h]; unsigned __int16 *
0x1800204f1  test    rdx, rdx
0x1800204f4  jz      short loc_180020507
0x1800204f6  mov     rcx, [rbp+var_10]; lpString1
0x1800204fa  or      r8d, 0FFFFFFFFh; int
0x1800204fe  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180020503  test    eax, eax
0x180020505  jz      short loc_180020493
0x180020507  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18002050b  lea     rcx, [rdi+28h]; this
0x18002050f  call    ?Match@CERTFILTERSTRING@@QEBA_NPEBG@Z; CERTFILTERSTRING::Match(ushort const *)
0x180020514  test    al, al
0x180020516  mov     r14d, 1
0x18002051c  cmovnz  ebx, r14d
0x180020520  xor     edi, edi
0x180020522  mov     rcx, [rbp+hMem]; hMem
0x180020526  call    cs:__imp_LocalFree
0x18002052c  mov     rcx, [rbp+var_10]; hMem
0x180020530  call    cs:__imp_LocalFree
0x180020536  mov     rcx, [rbp+var_20]; hMem
0x18002053a  call    cs:__imp_LocalFree
0x180020540  mov     rcx, r15; hMem
0x180020543  call    cs:__imp_LocalFree
0x180020549  mov     rax, [rbp+arg_18]
0x18002054d  mov     [rax], ebx
0x18002054f  mov     eax, edi
0x180020551  mov     rdi, [rsp+40h+arg_8]
0x180020556  mov     rbx, [rsp+40h+arg_0]
0x18002055b  add     rsp, 40h
0x18002055f  pop     r15
0x180020561  pop     r14
0x180020563  pop     rbp
0x180020564  retn
```
