# Smb2BatchedWriteExecute

- ea: `0x1400513a0`
- end: `0x140051657`
- name: `Smb2BatchedWriteExecute`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140050b90`

## callees

- `0x140014650`
- `0x140014a00`
- `0x14002fb78`
- `0x1400513a0`
- `0x140056ee0`

## import_xrefs

- `mrxsmb!SmbCeInitiateExchange` at `0x140051639`
- `mrxsmb!SmbCeInitiateExchange` at `0x140051639`
- `mrxsmb!SmbCeInitializeExchange` at `0x140051524`
- `mrxsmb!SmbCeInitializeExchange` at `0x140051524`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051614`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051614`

## pseudocode

```c
__int64 __fastcall Smb2BatchedWriteExecute(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        char a8)
{
  __int64 v8; // r10
  __int64 v9; // r14
  unsigned int v10; // esi
  int v11; // r12d
  unsigned int v12; // edx
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 result; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // [rsp+40h] [rbp-18h]
  __int64 v32; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+50h]
  unsigned int v34; // [rsp+B0h] [rbp+58h]
  __int64 v35; // [rsp+B8h] [rbp+60h]

  v35 = a4;
  v34 = a3;
  v33 = a2;
  v8 = *(_QWORD *)(a1 + 72);
  v9 = a1 + 56;
  v10 = 0;
  v32 = 0;
  v11 = 0;
  v12 = 0;
  v14 = *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL);
  v15 = *(_QWORD *)(a1 + 56);
  v16 = *(_QWORD *)(v15 + 120);
  v31 = *(_QWORD *)(v15 + 136);
  if ( a6 )
  {
    do
    {
      v17 = 2LL * v12++;
      v18 = *(_DWORD *)(a4 + 8 * v17 + 12);
      v11 += v18;
      v10 += ((unsigned int)(v18 - 1) >> 16) + 2;
    }
    while ( v12 < a6 );
    v19 = a1 + 56;
  }
  else
  {
    v19 = a1 + 56;
  }
  *(_BYTE *)(*(_QWORD *)(v8 + 48) + 320LL) = 1;
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v9 + 136LL) + 81LL) )
    Smb2InvalidateFileInfoCacheEntry(a1, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v14 + 424) + 376LL));
  v20 = *(_QWORD *)v19;
  v21 = *(_QWORD *)(*(_QWORD *)v19 + 288LL);
  if ( v21 )
  {
    v22 = *(_QWORD *)(v21 + 136);
    if ( !v22 || (LODWORD(v22) = *(_DWORD *)(v22 + 88), *(_DWORD *)(*(_QWORD *)(v20 + 136) + 84LL) != (_DWORD)v22) )
    {
      Smb2InvalidateSingleFileInDirInfoCache(
        (_QWORD *)a1,
        (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v14 + 424) + 1112LL));
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*(_QWORD *)v9 + 136LL) + 84LL), v22);
    }
  }
  v23 = *(_QWORD *)(v14 + 416);
  if ( (*(_DWORD *)(v23 + 4) & 8) == 0 )
  {
    v24 = *(_QWORD *)(v23 + 384);
    if ( *(_QWORD *)(v24 + 576) )
    {
      if ( (*(_DWORD *)(v24 + 4) & 1) != 0 && (*(_BYTE *)(v23 + 4) & 3) == 0 )
        Smb2TryToEstablishMultipleChannelsImpl((PVOID)v23);
    }
  }
  if ( *(_BYTE *)(v16 + 77) == 1 && v10 > 1 )
    return 3221225485LL;
  result = SmbCeInitializeExchange(&v32, a1, 0, 0, 0, v14, 8 * v10 + 2528, &WriteDispatch);
  if ( !(_DWORD)result )
  {
    v26 = *(_QWORD *)(a1 + 856);
    if ( v26 )
      *(_DWORD *)(v26 + 408) = v11;
    v27 = v32;
    v28 = a5;
    *(_QWORD *)(v32 + 2488) = v33;
    *(_QWORD *)(v27 + 2496) = v35;
    v29 = 16LL * v34 + 8;
    *(_QWORD *)(v27 + 2512) = v28;
    *(_QWORD *)(v27 + 2504) = v28 + v29;
    *(_DWORD *)(v27 + 2520) = a6;
    *(_BYTE *)(v27 + 2524) = a7;
    *(_BYTE *)(v27 + 2525) = a8;
    *(_DWORD *)(v32 + 64) = 0;
    if ( v10 > 1 )
      _InterlockedOr((volatile signed __int32 *)(v32 + 68), 0x1000u);
    if ( (*(_BYTE *)(a1 + 522) & 8) != 0 )
      _InterlockedOr((volatile signed __int32 *)(v32 + 68), 0x40000u);
    *(_DWORD *)(v32 + 1052) = v10;
    *(_BYTE *)(v32 + 1048) = *(_BYTE *)(v16 + 77);
    InitializeWriteExchangeBlockState(v32);
    if ( *(_BYTE *)(v16 + 77) == 1 )
      _InterlockedOr((volatile signed __int32 *)(v32 + 68), 0x40u);
    v30 = *(_QWORD *)(v31 + 96);
    *(_QWORD *)(v32 + 504) = v30;
    if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(v30) + 509) )
      _InterlockedOr((volatile signed __int32 *)(v32 + 68), 0x2000u);
    return SmbCeInitiateExchange(v32);
  }
  return result;
}

```

## disassembly

```asm
0x1400513a0  mov     [rsp-40h+arg_18], r9
0x1400513a5  mov     [rsp-40h+arg_10], r8d
0x1400513aa  mov     [rsp-40h+arg_8], rdx
0x1400513af  push    rbp
0x1400513b0  push    rbx
0x1400513b1  push    rsi
0x1400513b2  push    rdi
0x1400513b3  push    r12
0x1400513b5  push    r13
0x1400513b7  push    r14
0x1400513b9  push    r15
0x1400513bb  mov     rbp, rsp
0x1400513be  sub     rsp, 58h
0x1400513c2  mov     r10, [rcx+48h]
0x1400513c6  lea     r14, [rcx+38h]
0x1400513ca  mov     r8d, [rbp+arg_28]
0x1400513ce  xor     esi, esi
0x1400513d0  mov     [rbp+arg_0], 0
0x1400513d8  xor     r12d, r12d
0x1400513db  xor     edx, edx
0x1400513dd  mov     rbx, rcx
0x1400513e0  mov     rax, [r10+28h]
0x1400513e4  mov     r15, [rax+28h]
0x1400513e8  mov     rax, [r14]
0x1400513eb  mov     r13, [rax+78h]
0x1400513ef  mov     rax, [rax+88h]
0x1400513f6  mov     [rbp+var_18], rax
0x1400513fa  test    r8d, r8d
0x1400513fd  jz      short loc_140051423
0x1400513ff  mov     eax, edx
0x140051401  add     esi, 2
0x140051404  add     rax, rax
0x140051407  inc     edx
0x140051409  mov     ecx, [r9+rax*8+0Ch]
0x14005140e  add     r12d, ecx
0x140051411  dec     ecx
0x140051413  shr     ecx, 10h
0x140051416  add     esi, ecx
0x140051418  cmp     edx, r8d
0x14005141b  jb      short loc_1400513FF
0x14005141d  lea     rdi, [rbx+38h]
0x140051421  jmp     short loc_140051426
0x140051423  mov     rdi, r14
0x140051426  mov     rax, [r10+30h]
0x14005142a  mov     byte ptr [rax+140h], 1
0x140051431  mov     rax, [r14]
0x140051434  mov     rcx, [rax+88h]
0x14005143b  nop
0x14005143c  mov     al, [rcx+51h]
0x14005143f  nop
0x140051440  test    al, al
0x140051442  jz      short loc_14005145A
0x140051444  mov     rdx, [r15+1A8h]
0x14005144b  mov     rcx, rbx
0x14005144e  add     rdx, 178h
0x140051455  call    Smb2InvalidateFileInfoCacheEntry
0x14005145a  mov     rcx, [rdi]
0x14005145d  mov     rax, [rcx+120h]
0x140051464  test    rax, rax
0x140051467  jz      short loc_1400514AD
0x140051469  mov     rdi, [rax+88h]
0x140051470  mov     rdx, [r15+1A8h]
0x140051477  test    rdi, rdi
0x14005147a  jz      short loc_140051491
0x14005147c  mov     rax, [rcx+88h]
0x140051483  nop
0x140051484  mov     edi, [rdi+58h]
0x140051487  nop
0x140051488  nop
0x140051489  mov     eax, [rax+54h]
0x14005148c  nop
0x14005148d  cmp     eax, edi
0x14005148f  jz      short loc_1400514AD
0x140051491  add     rdx, 458h
0x140051498  mov     rcx, rbx
0x14005149b  call    Smb2InvalidateSingleFileInDirInfoCache
0x1400514a0  mov     rax, [r14]
0x1400514a3  mov     rcx, [rax+88h]
0x1400514aa  xchg    edi, [rcx+54h]
0x1400514ad  mov     rcx, [r15+1A0h]; pContext
0x1400514b4  mov     eax, [rcx+4]
0x1400514b7  test    al, 8
0x1400514b9  jnz     short loc_1400514DE
0x1400514bb  mov     rax, [rcx+180h]
0x1400514c2  cmp     qword ptr [rax+240h], 0
0x1400514ca  jz      short loc_1400514DE
0x1400514cc  mov     eax, [rax+4]
0x1400514cf  test    al, 1
0x1400514d1  jz      short loc_1400514DE
0x1400514d3  test    byte ptr [rcx+4], 3
0x1400514d7  jnz     short loc_1400514DE
0x1400514d9  call    Smb2TryToEstablishMultipleChannelsImpl
0x1400514de  cmp     byte ptr [r13+4Dh], 1
0x1400514e3  jnz     short loc_1400514F4
0x1400514e5  cmp     esi, 1
0x1400514e8  jbe     short loc_1400514F4
0x1400514ea  mov     eax, 0C000000Dh
0x1400514ef  jmp     loc_140051645
0x1400514f4  lea     rcx, WriteDispatch
0x1400514fb  xor     edi, edi
0x1400514fd  mov     [rsp+58h+var_20], rcx
0x140051502  lea     eax, ds:9E0h[rsi*8]
0x140051509  mov     [rsp+58h+var_28], eax
0x14005150d  lea     rcx, [rbp+arg_0]
0x140051511  mov     [rsp+58h+var_30], r15
0x140051516  xor     r9d, r9d
0x140051519  xor     r8d, r8d
0x14005151c  mov     [rsp+58h+var_38], rdi
0x140051521  mov     rdx, rbx
0x140051524  call    cs:__imp_SmbCeInitializeExchange
0x14005152b  nop     dword ptr [rax+rax+00h]
0x140051530  test    eax, eax
0x140051532  jnz     loc_140051645
0x140051538  mov     rax, [rbx+358h]
0x14005153f  test    rax, rax
0x140051542  jz      short loc_14005154B
0x140051544  mov     [rax+198h], r12d
0x14005154b  mov     rdx, [rbp+arg_0]
0x14005154f  mov     rax, [rbp+arg_8]
0x140051553  mov     rcx, [rbp+arg_20]
0x140051557  mov     [rdx+9B8h], rax
0x14005155e  mov     rax, [rbp+arg_18]
0x140051562  mov     [rdx+9C0h], rax
0x140051569  mov     eax, [rbp+arg_10]
0x14005156c  shl     rax, 4
0x140051570  add     rax, 8
0x140051574  mov     [rdx+9D0h], rcx
0x14005157b  add     rax, rcx
0x14005157e  mov     [rdx+9C8h], rax
0x140051585  mov     eax, [rbp+arg_28]
0x140051588  mov     [rdx+9D8h], eax
0x14005158e  mov     al, [rbp+arg_30]
0x140051591  mov     [rdx+9DCh], al
0x140051597  mov     al, [rbp+arg_38]
0x14005159d  mov     [rdx+9DDh], al
0x1400515a3  mov     rax, [rbp+arg_0]
0x1400515a7  mov     [rax+40h], edi
0x1400515aa  cmp     esi, 1
0x1400515ad  jbe     short loc_1400515BB
0x1400515af  mov     rax, [rbp+arg_0]
0x1400515b3  lock or dword ptr [rax+44h], 1000h
0x1400515bb  test    byte ptr [rbx+20Ah], 8
0x1400515c2  jz      short loc_1400515D0
0x1400515c4  mov     rax, [rbp+arg_0]
0x1400515c8  lock or dword ptr [rax+44h], 40000h
0x1400515d0  mov     rax, [rbp+arg_0]
0x1400515d4  mov     [rax+41Ch], esi
0x1400515da  mov     cl, [r13+4Dh]
0x1400515de  mov     rax, [rbp+arg_0]
0x1400515e2  mov     [rax+418h], cl
0x1400515e8  mov     rcx, [rbp+arg_0]
0x1400515ec  call    InitializeWriteExchangeBlockState
0x1400515f1  cmp     byte ptr [r13+4Dh], 1
0x1400515f6  jnz     short loc_140051601
0x1400515f8  mov     rax, [rbp+arg_0]
0x1400515fc  lock or dword ptr [rax+44h], 40h
0x140051601  mov     rcx, [rbp+var_18]
0x140051605  mov     rcx, [rcx+60h]
0x140051609  mov     rax, [rbp+arg_0]
0x14005160d  mov     [rax+1F8h], rcx
0x140051614  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14005161b  nop     dword ptr [rax+rax+00h]
0x140051620  cmp     [rax+1FDh], dil
0x140051627  jnz     short loc_140051635
0x140051629  mov     rax, [rbp+arg_0]
0x14005162d  lock or dword ptr [rax+44h], 2000h
0x140051635  mov     rcx, [rbp+arg_0]
0x140051639  call    cs:__imp_SmbCeInitiateExchange
0x140051640  nop     dword ptr [rax+rax+00h]
0x140051645  add     rsp, 58h
0x140051649  pop     r15
0x14005164b  pop     r14
0x14005164d  pop     r13
0x14005164f  pop     r12
0x140051651  pop     rdi
0x140051652  pop     rsi
0x140051653  pop     rbx
0x140051654  pop     rbp
0x140051655  retn
```
