# CIssuanceLicense::GenerateEncryptedRightsXML(ushort *,uint,uint *,ushort * *)

- ea: `0x18000af3c`
- end: `0x18000b446`
- name: `?GenerateEncryptedRightsXML@CIssuanceLicense@@AEAAJPEAGIPEAIPEAPEAG@Z`
- size: `1290`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned __int16 *, unsigned int, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000eb04`

## callees

- `0x180001284`
- `0x180001290`
- `0x180003416`
- `0x18000af3c`
- `0x180015438`
- `0x180017358`
- `0x18001f020`
- `0x18001ffd8`
- `0x18004f91c`
- `0x18005bd72`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b404`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CIssuanceLicense::GenerateEncryptedRightsXML(
        CIssuanceLicense *this,
        unsigned __int16 *a2,
        unsigned int a3,
        DRMWB *a4,
        unsigned __int16 **a5)
{
  CDRMCBase *WBCapiSymKey; // r15
  void *v8; // r13
  unsigned __int8 *v9; // r12
  void *v10; // r14
  DRMWB *v11; // rcx
  int v12; // edi
  unsigned __int64 v13; // rdi
  void *v14; // rax
  unsigned int v15; // ebx
  unsigned __int8 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int Size; // [rsp+40h] [rbp-158h] BYREF
  unsigned int Size_4; // [rsp+44h] [rbp-154h]
  unsigned int v24; // [rsp+48h] [rbp-150h] BYREF
  unsigned int v25; // [rsp+4Ch] [rbp-14Ch]
  void *v26; // [rsp+50h] [rbp-148h]
  unsigned __int16 **v27; // [rsp+58h] [rbp-140h]
  DRMWB *v28; // [rsp+60h] [rbp-138h]
  void *Block; // [rsp+68h] [rbp-130h] BYREF
  void *Src; // [rsp+70h] [rbp-128h]
  CDRMCBase *v31; // [rsp+78h] [rbp-120h]
  void *v32; // [rsp+80h] [rbp-118h]
  unsigned __int8 *v33; // [rsp+88h] [rbp-110h]
  unsigned __int64 v34; // [rsp+90h] [rbp-108h]
  DRMWB *v35; // [rsp+98h] [rbp-100h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-F8h]
  __int64 v37; // [rsp+A8h] [rbp-F0h]
  char *v38; // [rsp+B0h] [rbp-E8h]
  unsigned __int16 v39[8]; // [rsp+C0h] [rbp-D8h] BYREF
  __int128 v40; // [rsp+D0h] [rbp-C8h]
  __int128 v41; // [rsp+E0h] [rbp-B8h]
  __int128 v42; // [rsp+F0h] [rbp-A8h]
  __int128 v43; // [rsp+100h] [rbp-98h]
  __int128 v44; // [rsp+110h] [rbp-88h]
  __int128 v45; // [rsp+120h] [rbp-78h]
  _OWORD v46[2]; // [rsp+130h] [rbp-68h]

  v37 = -2;
  v28 = a4;
  Size_4 = a3;
  Src = a2;
  v35 = a4;
  v27 = a5;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 88);
  v38 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  WBCapiSymKey = 0;
  v31 = 0;
  v8 = 0;
  v32 = 0;
  Size = 0;
  v9 = 0;
  v33 = 0;
  *(_OWORD *)v39 = *(_OWORD *)L"<AUTHENTICATEDDATA id=\"Encrypted-Rights-Data\">%s</AUTHENTICATEDDATA>";
  v40 = *(_OWORD *)L"ICATEDDATA id=\"Encrypted-Rights-Data\">%s</AUTHENTICATEDDATA>";
  v41 = *(_OWORD *)L"TA id=\"Encrypted-Rights-Data\">%s</AUTHENTICATEDDATA>";
  v42 = *(_OWORD *)L"ncrypted-Rights-Data\">%s</AUTHENTICATEDDATA>";
  v43 = *(_OWORD *)L"-Rights-Data\">%s</AUTHENTICATEDDATA>";
  v44 = *(_OWORD *)L"Data\">%s</AUTHENTICATEDDATA>";
  v45 = *(_OWORD *)L"</AUTHENTICATEDDATA>";
  v46[0] = *(_OWORD *)L"TICATEDDATA>";
  *(_OWORD *)((char *)v46 + 10) = *(_OWORD *)L"EDDATA>";
  Block = 0;
  v10 = 0;
  v26 = 0;
  v24 = 0;
  v11 = v28;
  if ( !v28 || !a2 )
  {
    v12 = -2147024809;
    goto LABEL_33;
  }
  v12 = 0;
  *(_DWORD *)v28 = 0;
  v25 = 67;
  if ( (*((_BYTE *)this + 728) & 2) == 0 )
  {
    WBCapiSymKey = DRMWB::CreateWBCapiSymKey(v11);
    v31 = WBCapiSymKey;
    if ( !WBCapiSymKey )
    {
      v12 = -2147024882;
      goto LABEL_33;
    }
    v13 = -*((_DWORD *)this + 178) & (*((_DWORD *)this + 178) + 2 * Size_4 - 1);
    v34 = v13;
    v14 = operator new[](v13);
    v8 = v14;
    v32 = v14;
    if ( !v14 )
    {
      v12 = -2147024882;
      goto LABEL_33;
    }
    memset_0(v14, 0, v13);
    memcpy_0(v8, Src, 2 * Size_4);
    v12 = (*(__int64 (__fastcall **)(CDRMCBase *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)WBCapiSymKey + 8LL))(
            WBCapiSymKey,
            0,
            0,
            0);
    if ( v12 < 0 )
      goto LABEL_33;
    v12 = (*(__int64 (__fastcall **)(CDRMCBase *, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)WBCapiSymKey + 80LL))(
            WBCapiSymKey,
            *((_QWORD *)this + 88),
            *((unsigned int *)this + 178),
            *((unsigned int *)this + 178),
            4098);
    if ( v12 < 0 )
      goto LABEL_33;
    v15 = v34;
    v12 = (*(__int64 (__fastcall **)(CDRMCBase *, void *, _QWORD, _QWORD, unsigned int *, _DWORD, _DWORD))(*(_QWORD *)WBCapiSymKey + 40LL))(
            WBCapiSymKey,
            v8,
            (unsigned int)v34,
            0,
            &Size,
            0,
            0);
    if ( v12 < 0 )
      goto LABEL_33;
    v16 = (unsigned __int8 *)operator new[](Size);
    v9 = v16;
    v33 = v16;
    if ( !v16 )
    {
      v12 = -2147024882;
      goto LABEL_33;
    }
    memset_0(v16, 0, Size);
    v12 = (*(__int64 (__fastcall **)(CDRMCBase *, void *, _QWORD, unsigned __int8 *, unsigned int *, _DWORD, _DWORD))(*(_QWORD *)WBCapiSymKey + 40LL))(
            WBCapiSymKey,
            v8,
            v15,
            v9,
            &Size,
            0,
            0);
    if ( v12 < 0 )
      goto LABEL_33;
    v12 = CDRMCBase::Base64EncodeData(Size, v9, &v24, 0);
    if ( v12 < 0 )
      goto LABEL_33;
    v18 = v24 + 67;
    if ( v24 >= 0xFFFFFFBD )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
    v25 = v24 + 67;
    if ( !v27 )
      goto LABEL_30;
    v12 = CDRMCBase::Base64EncodeData(Size, v9, &v24, (unsigned __int16 **)&Block);
    if ( v12 < 0 )
      goto LABEL_33;
    v10 = operator new[](saturated_mul((unsigned int)v18, 2u));
    v26 = v10;
    if ( !v10 )
    {
      v12 = -2147024882;
      goto LABEL_33;
    }
    v19 = 2 * v18;
    if ( (unsigned __int64)(2 * v18) > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v19);
    memset_0(v10, 0, (unsigned int)v19);
    v12 = StringCchPrintfW((unsigned __int16 *)v10, (unsigned int)v18, v39, Block);
    if ( v12 < 0 )
      goto LABEL_33;
LABEL_29:
    *v27 = (unsigned __int16 *)v10;
LABEL_30:
    v11 = v28;
    v26 = 0;
    v10 = 0;
LABEL_31:
    *(_DWORD *)v11 = v18;
    goto LABEL_33;
  }
  v18 = Size_4 + 67;
  if ( Size_4 >= 0xFFFFFFBD )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
  v25 = Size_4 + 67;
  if ( !v27 )
    goto LABEL_31;
  v10 = operator new[](saturated_mul((unsigned int)v18, 2u));
  v26 = v10;
  if ( !v10 )
  {
    v12 = -2147024882;
    goto LABEL_33;
  }
  v20 = 2 * v18;
  if ( (unsigned __int64)(2 * v18) > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20);
  memset_0(v10, 0, (unsigned int)v20);
  v12 = StringCchPrintfW((unsigned __int16 *)v10, (unsigned int)v18, v39, Src);
  if ( v12 >= 0 )
    goto LABEL_29;
LABEL_33:
  operator delete(Block);
  operator delete(v10);
  operator delete(v9);
  operator delete(v8);
  if ( WBCapiSymKey )
    CDRMCBase::Release(WBCapiSymKey);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000af3c  push    rbx
0x18000af3e  push    rsi
0x18000af3f  push    rdi
0x18000af40  push    r12
0x18000af42  push    r13
0x18000af44  push    r14
0x18000af46  push    r15
0x18000af48  sub     rsp, 160h
0x18000af4f  mov     [rsp+198h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18000af5b  mov     rax, cs:__security_cookie
0x18000af62  xor     rax, rsp
0x18000af65  mov     [rsp+198h+var_40], rax
0x18000af6d  mov     [rsp+198h+var_138], r9
0x18000af72  mov     dword ptr [rsp+198h+Size+4], r8d
0x18000af77  mov     rdi, rdx
0x18000af7a  mov     [rsp+198h+Src], rdx
0x18000af7f  mov     rbx, rcx
0x18000af82  mov     [rsp+198h+var_100], r9
0x18000af8a  mov     rax, [rsp+198h+arg_20]
0x18000af92  mov     [rsp+198h+var_140], rax
0x18000af97  lea     rax, [rcx+58h]
0x18000af9b  mov     [rsp+198h+lpCriticalSection], rax
0x18000afa3  mov     [rsp+198h+var_E8], rax
0x18000afab  mov     rcx, rax; lpCriticalSection
0x18000afae  call    cs:__imp_EnterCriticalSection
0x18000afb4  nop
0x18000afb5  xor     esi, esi
0x18000afb7  mov     r15d, esi
0x18000afba  mov     [rsp+198h+var_120], rsi
0x18000afbf  mov     r13d, esi
0x18000afc2  mov     [rsp+198h+var_118], rsi
0x18000afca  mov     dword ptr [rsp+198h+Size], esi
0x18000afce  mov     r12d, esi
0x18000afd1  mov     [rsp+198h+var_110], rsi
0x18000afd9  movaps  xmm0, xmmword ptr cs:aAuthenticatedd_0; "<AUTHENTICATEDDATA id=\"Encrypted-Right"...
0x18000afe0  movups  xmmword ptr [rsp+198h+var_D8], xmm0
0x18000afe8  movaps  xmm1, xmmword ptr cs:aAuthenticatedd_0+10h; "ICATEDDATA id=\"Encrypted-Rights-Data\""...
0x18000afef  movups  [rsp+198h+var_C8], xmm1
0x18000aff7  movaps  xmm0, xmmword ptr cs:aAuthenticatedd_0+20h; "TA id=\"Encrypted-Rights-Data\">%s</AUT"...
0x18000affe  movups  [rsp+198h+var_B8], xmm0
0x18000b006  movaps  xmm1, xmmword ptr cs:aAuthenticatedd_0+30h; "ncrypted-Rights-Data\">%s</AUTHENTICATE"...
0x18000b00d  movups  [rsp+198h+var_A8], xmm1
0x18000b015  movaps  xmm0, xmmword ptr cs:aAuthenticatedd_0+40h; "-Rights-Data\">%s</AUTHENTICATEDDATA>"
0x18000b01c  movups  [rsp+198h+var_98], xmm0
0x18000b024  movaps  xmm1, xmmword ptr cs:aAuthenticatedd_0+50h; "Data\">%s</AUTHENTICATEDDATA>"
0x18000b02b  movups  [rsp+198h+var_88], xmm1
0x18000b033  movaps  xmm0, xmmword ptr cs:aAuthenticatedd_0+60h; "</AUTHENTICATEDDATA>"
0x18000b03a  movups  [rsp+198h+var_78], xmm0
0x18000b042  movaps  xmm1, xmmword ptr cs:aAuthenticatedd_0+70h; "TICATEDDATA>"
0x18000b049  movups  xmmword ptr [rsp+198h+var_68], xmm1
0x18000b051  movups  xmm0, xmmword ptr cs:aAuthenticatedd_0+7Ah; "EDDATA>"
0x18000b058  movups  xmmword ptr [rsp+198h+var_68+0Ah], xmm0
0x18000b060  mov     [rsp+198h+Block], rsi
0x18000b065  mov     r14d, esi
0x18000b068  mov     [rsp+198h+var_148], rsi
0x18000b06d  mov     [rsp+198h+var_150], esi
0x18000b071  mov     rcx, [rsp+198h+var_138]; this
0x18000b076  test    rcx, rcx
0x18000b079  jz      loc_18000B3C7
0x18000b07f  test    rdi, rdi
0x18000b082  jz      loc_18000B3C7
0x18000b088  mov     edi, esi
0x18000b08a  mov     [rcx], esi
0x18000b08c  mov     [rsp+198h+var_14C], 43h ; 'C'
0x18000b094  test    byte ptr [rbx+2D8h], 2
0x18000b09b  jnz     loc_18000B2F0
0x18000b0a1  call    ?CreateWBCapiSymKey@DRMWB@@YAPEAVWBCapiSymKey@1@XZ; DRMWB::CreateWBCapiSymKey(void)
0x18000b0a6  mov     r15, rax
0x18000b0a9  mov     [rsp+198h+var_120], rax
0x18000b0ae  test    rax, rax
0x18000b0b1  jnz     short loc_18000B0BD
0x18000b0b3  mov     edi, 8007000Eh
0x18000b0b8  jmp     loc_18000B3CC
0x18000b0bd  mov     eax, dword ptr [rsp+198h+Size+4]
0x18000b0c1  add     eax, eax
0x18000b0c3  mov     ecx, [rbx+2C8h]
0x18000b0c9  dec     eax
0x18000b0cb  add     eax, ecx
0x18000b0cd  neg     ecx
0x18000b0cf  and     eax, ecx
0x18000b0d1  mov     edi, eax
0x18000b0d3  mov     [rsp+198h+var_108], rdi
0x18000b0db  mov     ecx, eax; unsigned __int64
0x18000b0dd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b0e2  mov     r13, rax
0x18000b0e5  mov     [rsp+198h+var_118], rax
0x18000b0ed  test    rax, rax
0x18000b0f0  jnz     short loc_18000B0FC
0x18000b0f2  mov     edi, 8007000Eh
0x18000b0f7  jmp     loc_18000B3CC
0x18000b0fc  mov     r8, rdi; Size
0x18000b0ff  xor     edx, edx; Val
0x18000b101  mov     rcx, r13; void *
0x18000b104  call    memset_0
0x18000b109  mov     ecx, dword ptr [rsp+198h+Size+4]
0x18000b10d  lea     r8d, [rcx+rcx]; Size
0x18000b111  mov     rdx, [rsp+198h+Src]; Src
0x18000b116  mov     rcx, r13; void *
0x18000b119  call    memcpy_0
0x18000b11e  mov     rax, [r15]
0x18000b121  xor     r9d, r9d
0x18000b124  xor     r8d, r8d
0x18000b127  xor     edx, edx
0x18000b129  mov     rcx, r15
0x18000b12c  mov     rax, [rax+8]
0x18000b130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b135  mov     edi, eax
0x18000b137  test    eax, eax
0x18000b139  jns     short loc_18000B140
0x18000b13b  jmp     loc_18000B3CC
0x18000b140  mov     r8d, [rbx+2C8h]
0x18000b147  mov     rax, [r15]
0x18000b14a  mov     dword ptr [rsp+198h+var_178], 1002h
0x18000b152  mov     r9d, r8d
0x18000b155  mov     rdx, [rbx+2C0h]
0x18000b15c  mov     rcx, r15
0x18000b15f  mov     rax, [rax+50h]
0x18000b163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b168  mov     edi, eax
0x18000b16a  test    eax, eax
0x18000b16c  jns     short loc_18000B173
0x18000b16e  jmp     loc_18000B3CC
0x18000b173  mov     rax, [r15]
0x18000b176  mov     [rsp+198h+var_168], esi
0x18000b17a  mov     [rsp+198h+var_170], esi
0x18000b17e  lea     rcx, [rsp+198h+Size]
0x18000b183  mov     [rsp+198h+var_178], rcx
0x18000b188  xor     r9d, r9d
0x18000b18b  mov     rbx, [rsp+198h+var_108]
0x18000b193  mov     r8d, ebx
0x18000b196  mov     rdx, r13
0x18000b199  mov     rcx, r15
0x18000b19c  mov     rax, [rax+28h]
0x18000b1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1a5  mov     edi, eax
0x18000b1a7  test    eax, eax
0x18000b1a9  jns     short loc_18000B1B0
0x18000b1ab  jmp     loc_18000B3CC
0x18000b1b0  mov     ecx, dword ptr [rsp+198h+Size]; unsigned __int64
0x18000b1b4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b1b9  mov     r12, rax
0x18000b1bc  mov     [rsp+198h+var_110], rax
0x18000b1c4  test    rax, rax
0x18000b1c7  jnz     short loc_18000B1D3
0x18000b1c9  mov     edi, 8007000Eh
0x18000b1ce  jmp     loc_18000B3CC
0x18000b1d3  mov     r8d, dword ptr [rsp+198h+Size]; Size
0x18000b1d8  xor     edx, edx; Val
0x18000b1da  mov     rcx, r12; void *
0x18000b1dd  call    memset_0
0x18000b1e2  mov     rax, [r15]
0x18000b1e5  mov     [rsp+198h+var_168], esi
0x18000b1e9  mov     [rsp+198h+var_170], esi
0x18000b1ed  lea     rcx, [rsp+198h+Size]
0x18000b1f2  mov     [rsp+198h+var_178], rcx
0x18000b1f7  mov     r9, r12
0x18000b1fa  mov     r8d, ebx
0x18000b1fd  mov     rdx, r13
0x18000b200  mov     rcx, r15
0x18000b203  mov     rax, [rax+28h]
0x18000b207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b20c  mov     edi, eax
0x18000b20e  test    eax, eax
0x18000b210  jns     short loc_18000B217
0x18000b212  jmp     loc_18000B3CC
0x18000b217  xor     r9d, r9d; unsigned __int16 **
0x18000b21a  lea     r8, [rsp+198h+var_150]; unsigned int *
0x18000b21f  mov     rdx, r12; unsigned __int8 *
0x18000b222  mov     ecx, dword ptr [rsp+198h+Size]; unsigned int
0x18000b226  call    ?Base64EncodeData@CDRMCBase@@SAJIPEAEPEAIPEAPEAG@Z; CDRMCBase::Base64EncodeData(uint,uchar *,uint *,ushort * *)
0x18000b22b  mov     edi, eax
0x18000b22d  test    eax, eax
0x18000b22f  jns     short loc_18000B236
0x18000b231  jmp     loc_18000B3CC
0x18000b236  mov     ebx, [rsp+198h+var_150]
0x18000b23a  add     ebx, 43h ; 'C'
0x18000b23d  cmp     ebx, 43h ; 'C'
0x18000b240  jb      loc_18000B42F
0x18000b246  mov     [rsp+198h+var_14C], ebx
0x18000b24a  cmp     [rsp+198h+var_140], rsi
0x18000b24f  jz      loc_18000B38A
0x18000b255  lea     r9, [rsp+198h+Block]; unsigned __int16 **
0x18000b25a  lea     r8, [rsp+198h+var_150]; unsigned int *
0x18000b25f  mov     rdx, r12; unsigned __int8 *
0x18000b262  mov     ecx, dword ptr [rsp+198h+Size]; unsigned int
0x18000b266  call    ?Base64EncodeData@CDRMCBase@@SAJIPEAEPEAIPEAPEAG@Z; CDRMCBase::Base64EncodeData(uint,uchar *,uint *,ushort * *)
0x18000b26b  mov     edi, eax
0x18000b26d  test    eax, eax
0x18000b26f  jns     short loc_18000B276
0x18000b271  jmp     loc_18000B3CC
0x18000b276  mov     edi, ebx
0x18000b278  mov     eax, 2
0x18000b27d  mul     rdi
0x18000b280  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b287  cmovb   rax, rcx
0x18000b28b  mov     rcx, rax; unsigned __int64
0x18000b28e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b293  mov     r14, rax
0x18000b296  mov     [rsp+198h+var_148], rax
0x18000b29b  test    rax, rax
0x18000b29e  jnz     short loc_18000B2AA
0x18000b2a0  mov     edi, 8007000Eh
0x18000b2a5  jmp     loc_18000B3CC
0x18000b2aa  lea     rcx, [rbx+rbx]
0x18000b2ae  mov     eax, 0FFFFFFFFh
0x18000b2b3  cmp     rcx, rax
0x18000b2b6  ja      loc_18000B435
0x18000b2bc  mov     r8d, ecx; Size
0x18000b2bf  xor     edx, edx; Val
0x18000b2c1  mov     rcx, r14; void *
0x18000b2c4  call    memset_0
0x18000b2c9  mov     r9, [rsp+198h+Block]
0x18000b2ce  lea     r8, [rsp+198h+var_D8]; unsigned __int16 *
0x18000b2d6  mov     rdx, rdi; unsigned __int64
0x18000b2d9  mov     rcx, r14; unsigned __int16 *
0x18000b2dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b2e1  mov     edi, eax
0x18000b2e3  test    eax, eax
0x18000b2e5  jns     loc_18000B382
0x18000b2eb  jmp     loc_18000B3CC
0x18000b2f0  mov     ebx, dword ptr [rsp+198h+Size+4]
0x18000b2f4  add     ebx, 43h ; 'C'
0x18000b2f7  cmp     ebx, 43h ; 'C'
0x18000b2fa  jb      loc_18000B43A
0x18000b300  mov     [rsp+198h+var_14C], ebx
0x18000b304  cmp     [rsp+198h+var_140], rsi
0x18000b309  jz      loc_18000B397
0x18000b30f  mov     edi, ebx
0x18000b311  mov     eax, 2
0x18000b316  mul     rdi
0x18000b319  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b320  cmovb   rax, rcx
0x18000b324  mov     rcx, rax; unsigned __int64
0x18000b327  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b32c  mov     r14, rax
0x18000b32f  mov     [rsp+198h+var_148], rax
0x18000b334  test    rax, rax
0x18000b337  jnz     short loc_18000B343
0x18000b339  mov     edi, 8007000Eh
0x18000b33e  jmp     loc_18000B3CC
0x18000b343  lea     rcx, [rbx+rbx]
0x18000b347  mov     eax, 0FFFFFFFFh
0x18000b34c  cmp     rcx, rax
0x18000b34f  ja      loc_18000B43F
0x18000b355  mov     r8d, ecx; Size
0x18000b358  xor     edx, edx; Val
0x18000b35a  mov     rcx, r14; void *
0x18000b35d  call    memset_0
0x18000b362  mov     r9, [rsp+198h+Src]
0x18000b367  lea     r8, [rsp+198h+var_D8]; unsigned __int16 *
0x18000b36f  mov     rdx, rdi; unsigned __int64
0x18000b372  mov     rcx, r14; unsigned __int16 *
0x18000b375  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b37a  mov     edi, eax
0x18000b37c  test    eax, eax
0x18000b37e  jns     short loc_18000B382
0x18000b380  jmp     short loc_18000B3CC
0x18000b382  mov     rax, [rsp+198h+var_140]
0x18000b387  mov     [rax], r14
0x18000b38a  mov     rcx, [rsp+198h+var_138]
0x18000b38f  mov     [rsp+198h+var_148], rsi
0x18000b394  mov     r14, rsi
0x18000b397  jmp     short loc_18000B3C3
0x18000b399  mov     edi, dword ptr [rsp+198h+Size+4]
0x18000b39d  mov     r15, [rsp+198h+var_120]
0x18000b3a2  mov     r13, [rsp+198h+var_118]
0x18000b3aa  mov     r12, [rsp+198h+var_110]
0x18000b3b2  mov     ebx, [rsp+198h+var_14C]
0x18000b3b6  mov     r14, [rsp+198h+var_148]
0x18000b3bb  mov     rcx, [rsp+198h+var_100]
0x18000b3c3  mov     [rcx], ebx
0x18000b3c5  jmp     short loc_18000B3CC
0x18000b3c7  mov     edi, 80070057h
0x18000b3cc  mov     rcx, [rsp+198h+Block]; Block
0x18000b3d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3d6  mov     rcx, r14; Block
0x18000b3d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3de  mov     rcx, r12; Block
0x18000b3e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3e6  mov     rcx, r13; Block
0x18000b3e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3ee  test    r15, r15
0x18000b3f1  jz      short loc_18000B3FC
0x18000b3f3  mov     rcx, r15; this
0x18000b3f6  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000b3fb  nop
0x18000b3fc  mov     rcx, [rsp+198h+lpCriticalSection]; lpCriticalSection
0x18000b404  call    cs:__imp_LeaveCriticalSection
0x18000b40a  mov     eax, edi
0x18000b40c  mov     rcx, [rsp+198h+var_40]
0x18000b414  xor     rcx, rsp; StackCookie
0x18000b417  call    __security_check_cookie
0x18000b41c  add     rsp, 160h
0x18000b423  pop     r15
0x18000b425  pop     r14
0x18000b427  pop     r13
0x18000b429  pop     r12
0x18000b42b  pop     rdi
0x18000b42c  pop     rsi
0x18000b42d  pop     rbx
  ... truncated ...
```
