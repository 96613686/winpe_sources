# CCLCPubData::ParseDataAndCacheChain(ushort *)

- ea: `0x18001315c`
- end: `0x180013484`
- name: `?ParseDataAndCacheChain@CCLCPubData@@QEAAJPEAG@Z`
- size: `808`
- prototype: `__int64 __fastcall(CCLCPubData *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180005fc0`
- `0x18001f1a8`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x18000d110`
- `0x180012d20`
- `0x18001315c`
- `0x180015438`
- `0x18001fbdc`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800133ef`
- `msvcrt!wcsstr` at `0x180013415`
- `msvcrt!wcsstr` at `0x180013431`
- `msvcrt!wcsstr` at `0x1800133ef`
- `msvcrt!wcsstr` at `0x180013415`
- `msvcrt!wcsstr` at `0x180013431`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall CCLCPubData::ParseDataAndCacheChain(unsigned __int16 **this, unsigned __int16 *a2)
{
  signed int LicenseFromChain; // ebx
  __int64 v5; // r8
  unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rcx
  signed __int64 v8; // rbx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rsi
  unsigned __int16 *v13; // rax
  const wchar_t **v14; // r14
  unsigned __int16 *v16; // rax
  __int64 v17; // r8
  unsigned __int64 v18; // rcx
  signed __int64 v19; // rbx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  unsigned __int16 *v29; // rax
  __int64 v30; // [rsp+20h] [rbp-28h]
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  v30 = -2;
  Block = 0;
  if ( !a2 )
  {
    LicenseFromChain = -2147024809;
    goto LABEL_18;
  }
  LicenseFromChain = CDRMCBase::GetLicenseFromChain((CDRMCBase *)this, a2, (unsigned __int16 **)&Block);
  if ( (int)(LicenseFromChain + 0x80000000) < 0 || LicenseFromChain == -2147168418 )
  {
    if ( Block )
    {
      this[29] = (unsigned __int16 *)Block;
      Block = 0;
      v5 = 0x7FFFFFFF;
      v6 = a2;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      LicenseFromChain = v5 == 0 ? 0x80070057 : 0;
      v7 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
      if ( !v5 )
        goto LABEL_18;
      v8 = v7 + 1;
      if ( v7 + 1 < v7 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v7);
      v9 = HIDWORD(v8);
      if ( v8 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
      v10 = 2LL * (unsigned int)v8;
      v11 = v9 << 33;
      if ( v11 + v10 < v10 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
      v12 = -1;
      if ( v11 + v10 )
      {
        v13 = (unsigned __int16 *)operator new[](saturated_mul(v8, 2u));
        this[31] = v13;
        if ( !v13 )
        {
          LicenseFromChain = -2147024882;
          goto LABEL_18;
        }
        LicenseFromChain = StringCchCopyW(v13, v8, a2);
        if ( LicenseFromChain < 0 )
          goto LABEL_18;
      }
      v14 = (const wchar_t **)(this + 31);
    }
    else
    {
      v17 = 0x7FFFFFFF;
      v16 = a2;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v17;
      }
      while ( v17 );
      LicenseFromChain = v17 == 0 ? 0x80070057 : 0;
      v18 = (0x7FFFFFFF - v17) & -(__int64)(v17 != 0);
      if ( !v17 )
        goto LABEL_18;
      v19 = v18 + 1;
      if ( v18 + 1 < v18 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v18);
      v20 = HIDWORD(v19);
      if ( v19 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20);
      v21 = 2LL * (unsigned int)v19;
      v22 = v20 << 33;
      if ( v22 + v21 < v21 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22);
      if ( v22 + v21 )
      {
        v12 = -1;
        v23 = (unsigned __int16 *)operator new[](saturated_mul(v19, 2u));
        this[29] = v23;
        if ( !v23 )
        {
          LicenseFromChain = -2147024882;
          goto LABEL_18;
        }
        LicenseFromChain = StringCchCopyW(v23, v19, a2);
        if ( LicenseFromChain < 0 )
          goto LABEL_18;
      }
      else
      {
        v12 = -1;
      }
      v14 = (const wchar_t **)(this + 31);
      LicenseFromChain = CIssuanceLicense::GetChain(this[29], this + 31);
      if ( LicenseFromChain < 0 )
        goto LABEL_18;
    }
    v24 = this[29];
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    *((_DWORD *)this + 60) = v25;
    LicenseFromChain = CCLCPubData::ParseData((CCLCPubData *)this, v24);
    if ( LicenseFromChain >= 0 )
    {
      v26 = wcsstr(this[29], L"<XrML");
      this[32] = v26;
      if ( v26
        && (v27 = wcsstr(v26, L"</XrML>"), (this[33] = v27) != 0)
        && (v28 = wcsstr(*v14, L"<CERTIFICATECHAIN>"), (this[34] = v28) != 0) )
      {
        v29 = v28 + 18;
        this[34] = v29;
        do
          ++v12;
        while ( v29[v12] );
        *((_DWORD *)this + 70) = v12;
      }
      else
      {
        LicenseFromChain = -2147168512;
      }
    }
  }
LABEL_18:
  operator delete(Block);
  return (unsigned int)LicenseFromChain;
}

```

## disassembly

```asm
0x18001315c  mov     rax, rsp
0x18001315f  push    rdi
0x180013160  push    r14
0x180013162  push    r15
0x180013164  sub     rsp, 30h
0x180013168  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180013170  mov     [rax+8], rbx
0x180013174  mov     [rax+20h], rsi
0x180013178  mov     r14, rdx
0x18001317b  mov     rdi, rcx
0x18001317e  xor     r15d, r15d
0x180013181  mov     [rax+18h], r15
0x180013185  test    rdx, rdx
0x180013188  jnz     short loc_180013194
0x18001318a  mov     ebx, 80070057h
0x18001318f  jmp     loc_1800132A7
0x180013194  lea     r8, [rsp+48h+Block]; unsigned __int16 **
0x180013199  call    ?GetLicenseFromChain@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::GetLicenseFromChain(ushort *,ushort * *)
0x18001319e  mov     ebx, eax
0x1800131a0  mov     eax, 80000000h
0x1800131a5  lea     ecx, [rbx+rax]
0x1800131a8  test    eax, ecx
0x1800131aa  jnz     short loc_1800131B8
0x1800131ac  cmp     ebx, 8004CF5Eh
0x1800131b2  jnz     loc_1800132A7
0x1800131b8  mov     rax, [rsp+48h+Block]
0x1800131bd  test    rax, rax
0x1800131c0  jz      loc_1800132C7
0x1800131c6  mov     [rdi+0E8h], rax
0x1800131cd  mov     [rsp+48h+Block], r15
0x1800131d2  mov     edx, 7FFFFFFFh
0x1800131d7  mov     r8d, edx
0x1800131da  mov     rax, r14
0x1800131dd  cmp     [rax], r15w
0x1800131e1  jz      short loc_1800131ED
0x1800131e3  add     rax, 2
0x1800131e7  sub     r8, 1
0x1800131eb  jnz     short loc_1800131DD
0x1800131ed  mov     rax, r8
0x1800131f0  neg     rax
0x1800131f3  sbb     ecx, ecx
0x1800131f5  not     ecx
0x1800131f7  mov     ebx, 80070057h
0x1800131fc  and     ebx, ecx
0x1800131fe  mov     rax, r8
0x180013201  sub     rdx, r8
0x180013204  neg     rax
0x180013207  sbb     rcx, rcx
0x18001320a  and     rcx, rdx
0x18001320d  test    r8, r8
0x180013210  jnz     short loc_180013217
0x180013212  jmp     loc_1800132A7
0x180013217  lea     rbx, [rcx+1]
0x18001321b  cmp     rbx, rcx
0x18001321e  jb      loc_180013463
0x180013224  mov     rcx, rbx
0x180013227  shr     rcx, 20h
0x18001322b  mov     rax, rcx
0x18001322e  shr     rax, 1Fh
0x180013232  test    eax, eax
0x180013234  jnz     loc_180013468
0x18001323a  mov     eax, ebx
0x18001323c  add     rax, rax
0x18001323f  shl     rcx, 21h
0x180013243  lea     rdx, [rcx+rax]
0x180013247  cmp     rdx, rax
0x18001324a  jb      loc_18001346D
0x180013250  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180013257  test    rdx, rdx
0x18001325a  jz      short loc_180013297
0x18001325c  lea     eax, [rsi+3]
0x18001325f  mul     rbx
0x180013262  cmovb   rax, rsi
0x180013266  mov     rcx, rax; unsigned __int64
0x180013269  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001326e  mov     [rdi+0F8h], rax
0x180013275  test    rax, rax
0x180013278  jnz     short loc_180013281
0x18001327a  mov     ebx, 8007000Eh
0x18001327f  jmp     short loc_1800132A7
0x180013281  mov     r8, r14; unsigned __int16 *
0x180013284  mov     rdx, rbx; unsigned __int64
0x180013287  mov     rcx, rax; unsigned __int16 *
0x18001328a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001328f  mov     ebx, eax
0x180013291  test    eax, eax
0x180013293  jns     short loc_180013297
0x180013295  jmp     short loc_1800132A7
0x180013297  lea     r14, [rdi+0F8h]
0x18001329e  jmp     loc_1800133B5
0x1800132a3  mov     ebx, [rsp+48h+arg_8]
0x1800132a7  mov     rcx, [rsp+48h+Block]; Block
0x1800132ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800132b1  mov     eax, ebx
0x1800132b3  mov     rbx, [rsp+48h+arg_0]
0x1800132b8  mov     rsi, [rsp+48h+arg_18]
0x1800132bd  add     rsp, 30h
0x1800132c1  pop     r15
0x1800132c3  pop     r14
0x1800132c5  pop     rdi
0x1800132c6  retn
0x1800132c7  mov     edx, 7FFFFFFFh
0x1800132cc  mov     r8d, edx
0x1800132cf  mov     rax, r14
0x1800132d2  cmp     [rax], r15w
0x1800132d6  jz      short loc_1800132E2
0x1800132d8  add     rax, 2
0x1800132dc  sub     r8, 1
0x1800132e0  jnz     short loc_1800132D2
0x1800132e2  mov     rax, r8
0x1800132e5  neg     rax
0x1800132e8  sbb     ecx, ecx
0x1800132ea  not     ecx
0x1800132ec  mov     ebx, 80070057h
0x1800132f1  and     ebx, ecx
0x1800132f3  mov     rax, r8
0x1800132f6  sub     rdx, r8
0x1800132f9  neg     rax
0x1800132fc  sbb     rcx, rcx
0x1800132ff  and     rcx, rdx
0x180013302  test    r8, r8
0x180013305  jnz     short loc_180013309
0x180013307  jmp     short loc_1800132A7
0x180013309  lea     rbx, [rcx+1]
0x18001330d  cmp     rbx, rcx
0x180013310  jb      loc_180013473
0x180013316  mov     rcx, rbx
0x180013319  shr     rcx, 20h
0x18001331d  mov     rax, rcx
0x180013320  shr     rax, 1Fh
0x180013324  test    eax, eax
0x180013326  jnz     loc_180013478
0x18001332c  mov     eax, ebx
0x18001332e  add     rax, rax
0x180013331  shl     rcx, 21h
0x180013335  lea     rdx, [rcx+rax]
0x180013339  cmp     rdx, rax
0x18001333c  jb      loc_18001347D
0x180013342  test    rdx, rdx
0x180013345  jz      short loc_180013391
0x180013347  mov     eax, 2
0x18001334c  mul     rbx
0x18001334f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180013356  cmovb   rax, rsi
0x18001335a  mov     rcx, rax; unsigned __int64
0x18001335d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013362  mov     [rdi+0E8h], rax
0x180013369  test    rax, rax
0x18001336c  jnz     short loc_180013378
0x18001336e  mov     ebx, 8007000Eh
0x180013373  jmp     loc_1800132A7
0x180013378  mov     r8, r14; unsigned __int16 *
0x18001337b  mov     rdx, rbx; unsigned __int64
0x18001337e  mov     rcx, rax; unsigned __int16 *
0x180013381  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013386  mov     ebx, eax
0x180013388  test    eax, eax
0x18001338a  jns     short loc_180013395
0x18001338c  jmp     loc_1800132A7
0x180013391  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013395  lea     r14, [rdi+0F8h]
0x18001339c  mov     rdx, r14; unsigned __int16 **
0x18001339f  mov     rcx, [rdi+0E8h]; unsigned __int16 *
0x1800133a6  call    ?GetChain@CIssuanceLicense@@SAJPEAGPEAPEAG@Z; CIssuanceLicense::GetChain(ushort *,ushort * *)
0x1800133ab  mov     ebx, eax
0x1800133ad  test    eax, eax
0x1800133af  js      loc_1800132A7
0x1800133b5  mov     rdx, [rdi+0E8h]; unsigned __int16 *
0x1800133bc  mov     rax, rsi
0x1800133bf  inc     rax
0x1800133c2  cmp     [rdx+rax*2], r15w
0x1800133c7  jnz     short loc_1800133BF
0x1800133c9  mov     [rdi+0F0h], eax
0x1800133cf  mov     rcx, rdi; this
0x1800133d2  call    ?ParseData@CCLCPubData@@QEAAJPEAG@Z; CCLCPubData::ParseData(ushort *)
0x1800133d7  mov     ebx, eax
0x1800133d9  test    eax, eax
0x1800133db  js      loc_1800132A7
0x1800133e1  lea     rdx, aXrml_0; "<XrML"
0x1800133e8  mov     rcx, [rdi+0E8h]; Str
0x1800133ef  call    cs:__imp_wcsstr
0x1800133f5  mov     [rdi+100h], rax
0x1800133fc  test    rax, rax
0x1800133ff  jnz     short loc_18001340B
0x180013401  mov     ebx, 8004CF00h
0x180013406  jmp     loc_1800132A7
0x18001340b  lea     rdx, aXrml; "</XrML>"
0x180013412  mov     rcx, rax; Str
0x180013415  call    cs:__imp_wcsstr
0x18001341b  mov     [rdi+108h], rax
0x180013422  test    rax, rax
0x180013425  jz      short loc_180013401
0x180013427  lea     rdx, ?g_wszCertificateChainOpenNode@@3QBGB; "<CERTIFICATECHAIN>"
0x18001342e  mov     rcx, [r14]; Str
0x180013431  call    cs:__imp_wcsstr
0x180013437  mov     [rdi+110h], rax
0x18001343e  test    rax, rax
0x180013441  jz      short loc_180013401
0x180013443  add     rax, 24h ; '$'
0x180013447  mov     [rdi+110h], rax
0x18001344e  inc     rsi
0x180013451  cmp     [rax+rsi*2], r15w
0x180013456  jnz     short loc_18001344E
0x180013458  mov     [rdi+118h], esi
0x18001345e  jmp     loc_1800132A7
0x180013463  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180013468  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001346d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180013473  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180013478  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001347d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
