# LsaDbpDsCreateAndSetObject(_UNICODE_STRING *,ulong,ulong,ulong *,_ATTRVAL *)

- ea: `0x180010f28`
- end: `0x180011150`
- name: `?LsaDbpDsCreateAndSetObject@@YAJPEAU_UNICODE_STRING@@KKPEAKPEAU_ATTRVAL@@@Z`
- size: `552`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int *@<r9>, struct _ATTRVAL *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001f43c`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x1800107e0`
- `0x180010d48`
- `0x180010f28`
- `0x180011580`
- `0x18001182c`
- `0x180011d6c`
- `0x180012fa4`
- `0x18001f3b4`

## import_xrefs

- `NTDSA!THClearErrors` at `0x18001107e`
- `NTDSA!THClearErrors` at `0x18001107e`
- `NTDSA!SampSetDsa` at `0x18001105e`
- `NTDSA!SampSetDsa` at `0x18001109f`
- `NTDSA!SampSetDsa` at `0x18001105e`
- `NTDSA!SampSetDsa` at `0x18001109f`
- `NTDSA!DirAddEntry` at `0x18001106e`
- `NTDSA!DirAddEntry` at `0x18001106e`

## pseudocode

```c
__int64 __fastcall LsaDbpDsCreateAndSetObject(
        struct _UNICODE_STRING *a1,
        __int16 a2,
        unsigned int a3,
        unsigned int *a4,
        struct _ATTRVAL *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  _DWORD *v11; // rax
  struct _DSNAME *v12; // r14
  _DWORD *v13; // rdx
  unsigned int v14; // r9d
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // esi
  unsigned int v19; // eax
  __int64 v20; // rcx
  struct _DSNAME *v22; // [rsp+30h] [rbp-D0h] BYREF
  struct _COMMRES *v23; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h]
  struct _DSNAME *v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+5Ch] [rbp-A4h]
  _DWORD *v28; // [rsp+60h] [rbp-A0h]
  char v29[224]; // [rsp+70h] [rbp-90h] BYREF

  v22 = 0;
  memset_0(&v25, 0, 0x100u);
  v23 = 0;
  v24 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids);
  memset_0(&v25, 0, 0x100u);
  v9 = LsaDbpAllocAndInitializeDsNameFromUnicode(a1, &v22);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids,
      (_DWORD)a1,
      v9);
  }
  else
  {
    v11 = LsaDbpDsAlloc(24 * a3);
    v12 = v22;
    v13 = v11;
    if ( v11 )
    {
      v14 = 0;
      if ( a3 )
      {
        v15 = 0;
        do
        {
          v16 = 3 * v15;
          v13[2 * v16] = a4[v15];
          ++v14;
          v13[2 * v16 + 2] = 1;
          v17 = 16 * v15++;
          *(_QWORD *)&v13[2 * v16 + 4] = (char *)a5 + v17;
        }
        while ( v14 < a3 );
      }
      v28 = v13;
      v25 = v12;
      v26 = a3;
      v27 = DWORD1(v24);
      LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v29, 0);
      v18 = a2 & 0x2000;
      if ( !v18 )
        SampSetDsa(0);
      v19 = DirAddEntry(&v25, &v23);
      if ( v23 )
      {
        v10 = LsaDbpDsMapDsReturnToStatusEx(v19, v23);
      }
      else
      {
        THClearErrors();
        v10 = -1073741801;
      }
      LsaDbpDsContinueTransaction();
      if ( !v18 )
      {
        LOBYTE(v20) = 1;
        SampSetDsa(v20);
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids,
          (_DWORD)a1,
          v10);
    }
    else
    {
      v10 = -1073741801;
    }
    LsaDbpDsFree(v12);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180010f28  mov     [rsp-8+arg_8], rbx
0x180010f2d  mov     [rsp-8+arg_18], rsi
0x180010f32  push    rbp
0x180010f33  push    rdi
0x180010f34  push    r12
0x180010f36  push    r14
0x180010f38  push    r15
0x180010f3a  lea     rbp, [rsp-60h]
0x180010f3f  sub     rsp, 160h
0x180010f46  mov     rax, cs:__security_cookie
0x180010f4d  xor     rax, rsp
0x180010f50  mov     [rbp+80h+var_30], rax
0x180010f54  mov     edi, r8d
0x180010f57  mov     [rsp+180h+var_150], 0
0x180010f60  mov     esi, edx
0x180010f62  mov     r15, rcx
0x180010f65  mov     ebx, 100h
0x180010f6a  lea     rcx, [rsp+180h+var_130]; void *
0x180010f6f  mov     r8d, ebx; Size
0x180010f72  xor     edx, edx; Val
0x180010f74  mov     r12, r9
0x180010f77  call    memset_0
0x180010f7c  xorps   xmm0, xmm0
0x180010f7f  mov     [rsp+180h+var_148], 0
0x180010f88  movups  [rsp+180h+var_140], xmm0
0x180010f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f94  test    byte ptr [rcx+1Ch], 1
0x180010f98  jz      short loc_180010FAF
0x180010f9a  mov     rcx, [rcx+10h]
0x180010f9e  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180010fa5  mov     edx, 0Ch
0x180010faa  call    WPP_SF_
0x180010faf  mov     r8, rbx; Size
0x180010fb2  lea     rcx, [rsp+180h+var_130]; void *
0x180010fb7  xor     edx, edx; Val
0x180010fb9  call    memset_0
0x180010fbe  lea     rdx, [rsp+180h+var_150]; struct _DSNAME **
0x180010fc3  mov     rcx, r15; struct _UNICODE_STRING *
0x180010fc6  call    ?LsaDbpAllocAndInitializeDsNameFromUnicode@@YAJPEAU_UNICODE_STRING@@PEAPEAU_DSNAME@@@Z; LsaDbpAllocAndInitializeDsNameFromUnicode(_UNICODE_STRING *,_DSNAME * *)
0x180010fcb  mov     ebx, eax
0x180010fcd  test    eax, eax
0x180010fcf  js      loc_1800110D8
0x180010fd5  lea     ecx, [rdi+rdi*2]
0x180010fd8  shl     ecx, 3; unsigned int
0x180010fdb  call    ?LsaDbpDsAlloc@@YAPEAXK@Z; LsaDbpDsAlloc(ulong)
0x180010fe0  mov     r14, [rsp+180h+var_150]
0x180010fe5  mov     rdx, rax
0x180010fe8  test    rax, rax
0x180010feb  jnz     short loc_180010FF7
0x180010fed  mov     ebx, 0C0000017h
0x180010ff2  jmp     loc_1800110CE
0x180010ff7  xor     r9d, r9d
0x180010ffa  test    edi, edi
0x180010ffc  jz      short loc_180011032
0x180010ffe  xor     r8d, r8d
0x180011001  mov     eax, [r12+r8*4]
0x180011005  lea     rcx, [r8+r8*2]
0x180011009  mov     [rdx+rcx*8], eax
0x18001100c  inc     r9d
0x18001100f  mov     rax, r8
0x180011012  mov     dword ptr [rdx+rcx*8+8], 1
0x18001101a  shl     rax, 4
0x18001101e  inc     r8
0x180011021  add     rax, [rbp+80h+arg_20]
0x180011028  mov     [rdx+rcx*8+10h], rax
0x18001102d  cmp     r9d, edi
0x180011030  jb      short loc_180011001
0x180011032  mov     eax, dword ptr [rsp+180h+var_140+4]
0x180011036  lea     rcx, [rsp+180h+var_110]; struct _COMMARG *
0x18001103b  mov     [rsp+180h+var_120], rdx
0x180011040  xor     edx, edx; unsigned int
0x180011042  mov     [rsp+180h+var_130], r14
0x180011047  mov     [rsp+180h+var_128], edi
0x18001104b  mov     [rsp+180h+var_124], eax
0x18001104f  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x180011054  and     esi, 2000h
0x18001105a  jnz     short loc_180011064
0x18001105c  xor     ecx, ecx
0x18001105e  call    cs:__imp_SampSetDsa
0x180011064  lea     rdx, [rsp+180h+var_148]
0x180011069  lea     rcx, [rsp+180h+var_130]
0x18001106e  call    cs:__imp_DirAddEntry
0x180011074  mov     rdx, [rsp+180h+var_148]; struct _COMMRES *
0x180011079  test    rdx, rdx
0x18001107c  jnz     short loc_18001108B
0x18001107e  call    cs:__imp_THClearErrors
0x180011084  mov     ebx, 0C0000017h
0x180011089  jmp     short loc_180011094
0x18001108b  mov     ecx, eax; unsigned int
0x18001108d  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x180011092  mov     ebx, eax
0x180011094  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x180011099  test    esi, esi
0x18001109b  jnz     short loc_1800110A5
0x18001109d  mov     cl, 1
0x18001109f  call    cs:__imp_SampSetDsa
0x1800110a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110ac  test    byte ptr [rcx+1Ch], 1
0x1800110b0  jz      short loc_1800110CE
0x1800110b2  mov     rcx, [rcx+10h]
0x1800110b6  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x1800110bd  mov     edx, 0Dh
0x1800110c2  mov     [rsp+180h+var_160], ebx
0x1800110c6  mov     r9, r15
0x1800110c9  call    WPP_SF_ZD
0x1800110ce  mov     rcx, r14; void *
0x1800110d1  call    ?LsaDbpDsFree@@YAXPEAX@Z; LsaDbpDsFree(void *)
0x1800110d6  jmp     short loc_180011101
0x1800110d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110df  test    byte ptr [rcx+1Ch], 1
0x1800110e3  jz      short loc_180011126
0x1800110e5  mov     rcx, [rcx+10h]
0x1800110e9  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x1800110f0  mov     edx, 0Eh
0x1800110f5  mov     [rsp+180h+var_160], eax
0x1800110f9  mov     r9, r15
0x1800110fc  call    WPP_SF_ZD
0x180011101  mov     rcx, cs:WPP_GLOBAL_Control
0x180011108  test    byte ptr [rcx+1Ch], 1
0x18001110c  jz      short loc_180011126
0x18001110e  mov     rcx, [rcx+10h]
0x180011112  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180011119  mov     edx, 0Fh
0x18001111e  mov     r9d, ebx
0x180011121  call    WPP_SF_d
0x180011126  mov     eax, ebx
0x180011128  mov     rcx, [rbp+80h+var_30]
0x18001112c  xor     rcx, rsp; StackCookie
0x18001112f  call    __security_check_cookie
0x180011134  lea     r11, [rsp+180h+var_20]
0x18001113c  mov     rbx, [r11+38h]
0x180011140  mov     rsi, [r11+48h]
0x180011144  mov     rsp, r11
0x180011147  pop     r15
0x180011149  pop     r14
0x18001114b  pop     r12
0x18001114d  pop     rdi
0x18001114e  pop     rbp
0x18001114f  retn
```
