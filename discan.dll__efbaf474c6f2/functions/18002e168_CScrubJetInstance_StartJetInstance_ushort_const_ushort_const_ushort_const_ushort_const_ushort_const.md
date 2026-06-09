# CScrubJetInstance::StartJetInstance(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002e168`
- end: `0x18002e553`
- name: `?StartJetInstance@CScrubJetInstance@@QEAAJPEBG0000@Z`
- size: `1003`
- prototype: `__int64 __fastcall(CScrubJetInstance *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001e49c`
- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002d8f4`
- `0x18002d918`
- `0x18002d944`
- `0x18002dcf8`
- `0x18002e168`

## import_xrefs

- `KERNEL32!Sleep` at `0x18002e3c8`
- `KERNEL32!Sleep` at `0x18002e3c8`
- `ESENT!JetCreateInstance2W` at `0x18002e247`
- `ESENT!JetCreateInstance2W` at `0x18002e247`
- `ESENT!JetInit3W` at `0x18002e351`
- `ESENT!JetInit3W` at `0x18002e351`
- `ESENT!JetBeginSessionW` at `0x18002e485`
- `ESENT!JetBeginSessionW` at `0x18002e485`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScrubJetInstance::StartJetInstance(
        CScrubJetInstance *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  __int64 v9; // r11
  USHORT v10; // dx
  USHORT Length; // cx
  USHORT v12; // ax
  unsigned int v13; // eax
  int v14; // edi
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r12d
  unsigned int v19; // eax
  int v20; // edi
  unsigned int v21; // ecx
  int v22; // eax
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  JET_ERR v26; // edi
  int v27; // eax
  JET_SESID v28; // rax
  JET_INSTANCE pinstance; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v31[2]; // [rsp+38h] [rbp-38h] BYREF
  JET_INSTANCE *p_pinstance; // [rsp+48h] [rbp-28h] BYREF
  JET_SESID psesid; // [rsp+50h] [rbp-20h] BYREF
  int v34; // [rsp+58h] [rbp-18h]
  char v35; // [rsp+5Ch] [rbp-14h]
  const char *v36; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v37; // [rsp+68h] [rbp-8h]

  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v9 + 16) = "CScrubJetInstance::StartJetInstance";
  v36 = "CScrubJetInstance::StartJetInstance";
  v10 = ++*(_WORD *)(v9 + 8);
  Length = GlobalIndentString.Length;
  v12 = GlobalIndentString.Length;
  if ( v10 < GlobalIndentString.Length )
    v12 = *(_WORD *)(v9 + 8);
  LOWORD(v31[0]) = v12;
  if ( v10 < GlobalIndentString.Length )
    Length = v10;
  WORD1(v31[0]) = Length;
  HIDWORD(v31[0]) = 0;
  v31[1] = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubJetInstance::StartJetInstance");
  }
  pinstance = 0;
  v13 = JetCreateInstance2W(&pinstance, a2, 0, 0);
  v14 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, v13);
    }
    if ( v14 == -1011 )
    {
      v15 = -2147024882;
    }
    else
    {
      v16 = -v14;
      if ( v14 > 0 )
        LOWORD(v16) = v14;
      v15 = v14 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
    }
    v37 = v15;
    goto LABEL_68;
  }
  p_pinstance = &pinstance;
  v31[0] = &p_pinstance;
  v17 = CScrubJetInstance::SetupInstanceParameters(&pinstance, a3, a4, a5, a6);
  v15 = v17;
  v37 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids,
        (unsigned int)v17);
    }
LABEL_25:
    CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___::_CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___(v31);
    goto LABEL_68;
  }
  v18 = 0;
  v15 = -2147024882;
  do
  {
    v19 = JetInit3W(&pinstance, 0, 4u);
    v20 = v19;
    if ( v19 != -1216 && v19 != -1085 && v19 != -545 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, v19);
    }
    v21 = 0;
    if ( v20 )
    {
      if ( v20 == -1011 )
      {
        v21 = -2147024882;
      }
      else
      {
        v22 = -v20;
        if ( v20 > 0 )
          LOWORD(v22) = v20;
        v21 = v20 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
      }
    }
    v37 = v21;
    Sleep(0x1F4u);
    ++v18;
  }
  while ( v18 < 5 );
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids,
        (unsigned int)v20);
    }
    v23 = (unsigned int)(v20 + 533);
    if ( (unsigned int)v23 <= 0x20 )
    {
      v24 = 0x100000021LL;
      if ( _bittest64(&v24, v23) )
        DeleteJetDatabase(a4, a5, a6);
    }
    if ( v20 != -1011 )
    {
      v25 = -v20;
      if ( v20 > 0 )
        LOWORD(v25) = v20;
      v15 = v20 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
    }
    v37 = v15;
    goto LABEL_25;
  }
  psesid = 0;
  v34 = 0;
  v35 = 0;
  v26 = JetBeginSessionW(pinstance, &psesid, 0, 0);
  if ( v26 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids,
        (unsigned int)v26);
    }
    if ( v26 != -1011 )
    {
      v27 = -v26;
      if ( v26 > 0 )
        LOWORD(v27) = v26;
      v15 = v26 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
    }
    v37 = v15;
    CHandleT<unsigned __int64,JetSesIdTrait>::~CHandleT<unsigned __int64,JetSesIdTrait>(&psesid);
    goto LABEL_25;
  }
  if ( !v35 || (v28 = 0, !v34) )
  {
    v28 = psesid;
    psesid = 0;
  }
  *((_QWORD *)this + 1) = v28;
  v31[0] = 0;
  *(_QWORD *)this = pinstance;
  v37 = 0;
  CHandleT<unsigned __int64,JetSesIdTrait>::~CHandleT<unsigned __int64,JetSesIdTrait>(&psesid);
  CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___::_CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___(v31);
  v15 = 0;
LABEL_68:
  CHResultImp::~CHResultImp((CHResultImp *)&v36);
  return v15;
}

```

## disassembly

```asm
0x18002e168  mov     [rsp-38h+arg_8], rbx
0x18002e16d  mov     [rsp-38h+lpString1], r9
0x18002e172  mov     [rsp-38h+arg_0], rcx
0x18002e177  push    rbp
0x18002e178  push    rsi
0x18002e179  push    rdi
0x18002e17a  push    r12
0x18002e17c  push    r13
0x18002e17e  push    r14
0x18002e180  push    r15
0x18002e182  mov     rbp, rsp
0x18002e185  sub     rsp, 70h
0x18002e189  mov     r14, r9
0x18002e18c  mov     rsi, r8
0x18002e18f  mov     rbx, rdx
0x18002e192  mov     r10d, cs:_tls_index
0x18002e199  mov     rax, gs:58h
0x18002e1a2  mov     r11, [rax+r10*8]
0x18002e1a6  mov     eax, 10h
0x18002e1ab  lea     r8, aCscrubjetinsta; "CScrubJetInstance::StartJetInstance"
0x18002e1b2  mov     [rax+r11], r8
0x18002e1b6  mov     [rbp+var_10], r8
0x18002e1ba  mov     edx, 8
0x18002e1bf  mov     r15d, 1
0x18002e1c5  add     [rdx+r11], r15w
0x18002e1ca  movzx   edx, word ptr [rdx+r11]
0x18002e1cf  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002e1d6  movzx   eax, cx
0x18002e1d9  cmp     dx, cx
0x18002e1dc  cmovb   ax, dx
0x18002e1e0  mov     word ptr [rbp+var_38], ax
0x18002e1e4  cmovb   cx, dx
0x18002e1e8  mov     word ptr [rbp+var_38+2], cx
0x18002e1ec  xor     eax, eax
0x18002e1ee  mov     dword ptr [rbp+var_38+4], eax
0x18002e1f1  mov     rax, cs:off_180047060; "                                       "...
0x18002e1f8  mov     [rbp+var_30], rax
0x18002e1fc  lea     r12, WPP_GLOBAL_Control
0x18002e203  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e20a  cmp     rcx, r12
0x18002e20d  jz      short loc_18002E232
0x18002e20f  test    [rcx+1Ch], r15b
0x18002e213  jz      short loc_18002E232
0x18002e215  cmp     byte ptr [rcx+19h], 5
0x18002e219  jb      short loc_18002E232
0x18002e21b  lea     edx, [r15+0Ch]
0x18002e21f  mov     [rsp+70h+var_50], r8; __int64
0x18002e224  lea     r9, [rbp+var_38]
0x18002e228  mov     rcx, [rcx+10h]; LoggerHandle
0x18002e22c  call    WPP_SF_aZs
0x18002e231  nop
0x18002e232  mov     [rbp+pinstance], 0
0x18002e23a  xor     r9d, r9d; grbit
0x18002e23d  xor     r8d, r8d; szDisplayName
0x18002e240  mov     rdx, rbx; szInstanceName
0x18002e243  lea     rcx, [rbp+pinstance]; pinstance
0x18002e247  call    cs:__imp_JetCreateInstance2W
0x18002e24d  mov     edi, eax
0x18002e24f  test    eax, eax
0x18002e251  jz      short loc_18002E2B3
0x18002e253  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e25a  cmp     rcx, r12
0x18002e25d  jz      short loc_18002E283
0x18002e25f  test    [rcx+1Ch], r15b
0x18002e263  jz      short loc_18002E283
0x18002e265  cmp     byte ptr [rcx+19h], 2
0x18002e269  jb      short loc_18002E283
0x18002e26b  mov     edx, 12h
0x18002e270  mov     r9d, eax
0x18002e273  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002e27a  mov     rcx, [rcx+10h]
0x18002e27e  call    WPP_SF_d
0x18002e283  mov     esi, 0FFFFFC0Dh
0x18002e288  cmp     edi, esi
0x18002e28a  jnz     short loc_18002E293
0x18002e28c  mov     ebx, 8007000Eh
0x18002e291  jmp     short loc_18002E2AB
0x18002e293  mov     eax, edi
0x18002e295  neg     eax
0x18002e297  cmovs   eax, edi
0x18002e29a  movzx   ebx, ax
0x18002e29d  and     edi, 8E5E0000h
0x18002e2a3  or      ebx, edi
0x18002e2a5  or      ebx, 0E5E0000h
0x18002e2ab  mov     [rbp+var_8], ebx
0x18002e2ae  jmp     loc_18002E530
0x18002e2b3  lea     rax, [rbp+pinstance]
0x18002e2b7  mov     [rbp+var_28], rax
0x18002e2bb  lea     rax, [rbp+var_28]
0x18002e2bf  mov     [rbp+var_38], rax
0x18002e2c3  mov     rax, [rbp+arg_28]
0x18002e2c7  mov     [rsp+70h+var_50], rax; JET_PCWSTR
0x18002e2cc  mov     r9, [rbp+arg_20]; JET_PCWSTR
0x18002e2d0  mov     r8, r14; JET_PCWSTR
0x18002e2d3  mov     rdx, rsi; szParam
0x18002e2d6  lea     rcx, [rbp+pinstance]; pinstance
0x18002e2da  call    ?SetupInstanceParameters@CScrubJetInstance@@CAJPEA_KPEBG111@Z; CScrubJetInstance::SetupInstanceParameters(unsigned __int64 *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002e2df  mov     ebx, eax
0x18002e2e1  mov     [rbp+var_8], eax
0x18002e2e4  test    eax, eax
0x18002e2e6  jns     short loc_18002E327
0x18002e2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2ef  cmp     rcx, r12
0x18002e2f2  jz      short loc_18002E319
0x18002e2f4  test    [rcx+1Ch], r15b
0x18002e2f8  jz      short loc_18002E319
0x18002e2fa  cmp     byte ptr [rcx+19h], 2
0x18002e2fe  jb      short loc_18002E319
0x18002e300  mov     edx, 13h
0x18002e305  mov     r9d, eax
0x18002e308  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002e30f  mov     rcx, [rcx+10h]
0x18002e313  call    WPP_SF_d
0x18002e318  nop
0x18002e319  lea     rcx, [rbp+var_38]
0x18002e31d  call    CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c______CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___
0x18002e322  jmp     loc_18002E530
0x18002e327  xor     r12d, r12d
0x18002e32a  mov     esi, 0FFFFFC0Dh
0x18002e32f  mov     ebx, 8007000Eh
0x18002e334  mov     r14d, 8E5E0000h
0x18002e33a  mov     r15d, 0E5E0000h
0x18002e340  lea     r13, WPP_GLOBAL_Control
0x18002e347  xor     edx, edx; prstInfo
0x18002e349  lea     r8d, [rdx+4]; grbit
0x18002e34d  lea     rcx, [rbp+pinstance]; pinstance
0x18002e351  call    cs:__imp_JetInit3W
0x18002e357  mov     edi, eax
0x18002e359  cmp     eax, 0FFFFFB40h
0x18002e35e  jz      short loc_18002E36E
0x18002e360  cmp     eax, 0FFFFFBC3h
0x18002e365  jz      short loc_18002E36E
0x18002e367  cmp     eax, 0FFFFFDDFh
0x18002e36c  jnz     short loc_18002E3DB
0x18002e36e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e375  cmp     rcx, r13
0x18002e378  jz      short loc_18002E39E
0x18002e37a  test    byte ptr [rcx+1Ch], 1
0x18002e37e  jz      short loc_18002E39E
0x18002e380  cmp     byte ptr [rcx+19h], 2
0x18002e384  jb      short loc_18002E39E
0x18002e386  mov     edx, 14h
0x18002e38b  mov     r9d, edi
0x18002e38e  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002e395  mov     rcx, [rcx+10h]
0x18002e399  call    WPP_SF_d
0x18002e39e  xor     ecx, ecx
0x18002e3a0  test    edi, edi
0x18002e3a2  jz      short loc_18002E3C0
0x18002e3a4  cmp     edi, esi
0x18002e3a6  jnz     short loc_18002E3AC
0x18002e3a8  mov     ecx, ebx
0x18002e3aa  jmp     short loc_18002E3C0
0x18002e3ac  mov     eax, edi
0x18002e3ae  neg     eax
0x18002e3b0  cmovs   eax, edi
0x18002e3b3  movzx   ecx, ax
0x18002e3b6  mov     eax, edi
0x18002e3b8  and     eax, r14d
0x18002e3bb  or      ecx, eax
0x18002e3bd  or      ecx, r15d
0x18002e3c0  mov     [rbp+var_8], ecx
0x18002e3c3  mov     ecx, 1F4h; dwMilliseconds
0x18002e3c8  call    cs:__imp_Sleep
0x18002e3ce  inc     r12d
0x18002e3d1  cmp     r12d, 5
0x18002e3d5  jb      loc_18002E347
0x18002e3db  xor     r12d, r12d
0x18002e3de  test    edi, edi
0x18002e3e0  mov     r13, [rbp+arg_0]
0x18002e3e4  jz      loc_18002E46B
0x18002e3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3f1  lea     rax, WPP_GLOBAL_Control
0x18002e3f8  cmp     rcx, rax
0x18002e3fb  jz      short loc_18002E421
0x18002e3fd  test    byte ptr [rcx+1Ch], 1
0x18002e401  jz      short loc_18002E421
0x18002e403  cmp     byte ptr [rcx+19h], 2
0x18002e407  jb      short loc_18002E421
0x18002e409  lea     edx, [r12+15h]
0x18002e40e  mov     r9d, edi
0x18002e411  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002e418  mov     rcx, [rcx+10h]
0x18002e41c  call    WPP_SF_d
0x18002e421  lea     eax, [rdi+215h]
0x18002e427  cmp     eax, 20h ; ' '
0x18002e42a  ja      short loc_18002E44D
0x18002e42c  mov     rcx, 100000021h
0x18002e436  bt      rcx, rax
0x18002e43a  jnb     short loc_18002E44D
0x18002e43c  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x18002e440  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x18002e444  mov     rcx, [rbp+lpString1]; lpString1
0x18002e448  call    ?DeleteJetDatabase@@YAXPEBG00@Z; DeleteJetDatabase(ushort const *,ushort const *,ushort const *)
0x18002e44d  cmp     edi, esi
0x18002e44f  jz      short loc_18002E463
0x18002e451  mov     eax, edi
0x18002e453  neg     eax
0x18002e455  cmovs   eax, edi
0x18002e458  movzx   ebx, ax
0x18002e45b  and     edi, r14d
0x18002e45e  or      ebx, edi
0x18002e460  or      ebx, r15d
0x18002e463  mov     [rbp+var_8], ebx
0x18002e466  jmp     loc_18002E319
0x18002e46b  mov     [rbp+psesid], r12
0x18002e46f  mov     [rbp+var_18], r12d
0x18002e473  mov     [rbp+var_14], r12b
0x18002e477  xor     r9d, r9d; szPassword
0x18002e47a  xor     r8d, r8d; szUserName
0x18002e47d  lea     rdx, [rbp+psesid]; psesid
0x18002e481  mov     rcx, [rbp+pinstance]; instance
0x18002e485  call    cs:__imp_JetBeginSessionW
0x18002e48b  mov     edi, eax
0x18002e48d  test    eax, eax
0x18002e48f  jz      short loc_18002E4EF
0x18002e491  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e498  lea     rax, WPP_GLOBAL_Control
0x18002e49f  cmp     rcx, rax
0x18002e4a2  jz      short loc_18002E4C8
0x18002e4a4  test    byte ptr [rcx+1Ch], 1
0x18002e4a8  jz      short loc_18002E4C8
0x18002e4aa  cmp     byte ptr [rcx+19h], 2
0x18002e4ae  jb      short loc_18002E4C8
0x18002e4b0  mov     edx, 16h
0x18002e4b5  mov     r9d, edi
0x18002e4b8  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002e4bf  mov     rcx, [rcx+10h]
0x18002e4c3  call    WPP_SF_d
0x18002e4c8  cmp     edi, esi
0x18002e4ca  jz      short loc_18002E4DE
0x18002e4cc  mov     eax, edi
0x18002e4ce  neg     eax
0x18002e4d0  cmovs   eax, edi
0x18002e4d3  movzx   ebx, ax
0x18002e4d6  and     edi, r14d
0x18002e4d9  or      ebx, edi
0x18002e4db  or      ebx, r15d
0x18002e4de  mov     [rbp+var_8], ebx
0x18002e4e1  lea     rcx, [rbp+psesid]
0x18002e4e5  call    ??1?$CHandleT@_KUJetSesIdTrait@@@@QEAA@XZ; CHandleT<unsigned __int64,JetSesIdTrait>::~CHandleT<unsigned __int64,JetSesIdTrait>(void)
0x18002e4ea  jmp     loc_18002E319
0x18002e4ef  cmp     [rbp+var_14], r12b
0x18002e4f3  jz      short loc_18002E4FE
0x18002e4f5  mov     rax, r12
0x18002e4f8  cmp     [rbp+var_18], r12d
0x18002e4fc  jnz     short loc_18002E506
0x18002e4fe  mov     rax, [rbp+psesid]
0x18002e502  mov     [rbp+psesid], r12
0x18002e506  mov     [r13+8], rax
0x18002e50a  mov     [rbp+var_38], r12
0x18002e50e  mov     rax, [rbp+pinstance]
0x18002e512  mov     [r13+0], rax
0x18002e516  mov     [rbp+var_8], r12d
0x18002e51a  lea     rcx, [rbp+psesid]
0x18002e51e  call    ??1?$CHandleT@_KUJetSesIdTrait@@@@QEAA@XZ; CHandleT<unsigned __int64,JetSesIdTrait>::~CHandleT<unsigned __int64,JetSesIdTrait>(void)
0x18002e523  nop
0x18002e524  lea     rcx, [rbp+var_38]
0x18002e528  call    CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c______CAutoTearDown__lambda_7a3fd7436352e3d62268b784e6ca570c___
0x18002e52d  mov     ebx, r12d
0x18002e530  lea     rcx, [rbp+var_10]; this
0x18002e534  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002e539  mov     eax, ebx
0x18002e53b  mov     rbx, [rsp+70h+arg_8]
0x18002e543  add     rsp, 70h
0x18002e547  pop     r15
0x18002e549  pop     r14
0x18002e54b  pop     r13
0x18002e54d  pop     r12
0x18002e54f  pop     rdi
0x18002e550  pop     rsi
0x18002e551  pop     rbp
0x18002e552  retn
```
