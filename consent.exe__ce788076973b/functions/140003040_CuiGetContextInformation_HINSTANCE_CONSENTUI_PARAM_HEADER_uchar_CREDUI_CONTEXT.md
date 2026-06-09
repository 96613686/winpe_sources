# CuiGetContextInformation(HINSTANCE__ *,_CONSENTUI_PARAM_HEADER *,uchar *,_CREDUI_CONTEXT *)

- ea: `0x140003040`
- end: `0x140003650`
- name: `?CuiGetContextInformation@@YAKPEAUHINSTANCE__@@PEAU_CONSENTUI_PARAM_HEADER@@PEAEPEAU_CREDUI_CONTEXT@@@Z`
- size: `1552`
- prototype: `__int64 __fastcall(HINSTANCE, struct _CONSENTUI_PARAM_HEADER *, unsigned __int8 *, struct _CREDUI_CONTEXT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140003040`
- `0x140003c90`
- `0x140003e40`
- `0x1400042e0`
- `0x14000eee4`
- `0x14000f200`
- `0x14000f4b8`
- `0x140010ad3`
- `0x140013a8c`
- `0x140013b04`
- `0x140018ce8`
- `0x140018d60`
- `0x140019534`
- `0x1400195d4`
- `0x1400197d8`
- `0x1400198cc`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x140003555`
- `USER32!GetSystemMetrics` at `0x140003555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400034d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400034d6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003433`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003433`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400034b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400034b1`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003573`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003573`
- `SHLWAPI!PathFindFileNameW` at `0x14000357e`
- `SHLWAPI!PathFindFileNameW` at `0x14000357e`
- `SHLWAPI!SHStrDupW` at `0x140003411`
- `SHLWAPI!SHStrDupW` at `0x14000353a`
- `SHLWAPI!SHStrDupW` at `0x14000358b`
- `SHLWAPI!SHStrDupW` at `0x140003411`
- `SHLWAPI!SHStrDupW` at `0x14000353a`
- `SHLWAPI!SHStrDupW` at `0x14000358b`
- `SHLWAPI!PathUnquoteSpacesW` at `0x140003429`
- `SHLWAPI!PathUnquoteSpacesW` at `0x140003429`
- `SHLWAPI!PathRemoveBlanksW` at `0x140003544`
- `SHLWAPI!PathRemoveBlanksW` at `0x140003544`

## pseudocode

```c
__int64 __fastcall CuiGetContextInformation(
        HINSTANCE a1,
        struct _CONSENTUI_PARAM_HEADER *a2,
        unsigned __int8 *a3,
        struct _CREDUI_CONTEXT *a4)
{
  unsigned int v4; // r14d
  __int64 v9; // rdi
  int v10; // eax
  const wchar_t *v11; // r13
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rdi
  __int64 v16; // rbp
  const WCHAR *v17; // rcx
  int BinarySignature; // edi
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // ecx
  signed int LastError; // eax
  const wchar_t *v23; // rax
  const WCHAR *v24; // rbp
  unsigned __int16 SystemMetrics; // ax
  const WCHAR *FileNameW; // rax
  int BinaryLocation; // eax
  __int64 v28; // r9
  int v30; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v31[180]; // [rsp+64h] [rbp-B4h] BYREF
  LPWSTR ppwsz; // [rsp+128h] [rbp+10h] BYREF

  v4 = 0;
  *(_OWORD *)((char *)a4 + 4) = 0;
  *(_OWORD *)((char *)a4 + 20) = 0;
  *(_OWORD *)((char *)a4 + 36) = 0;
  *(_OWORD *)((char *)a4 + 52) = 0;
  *(_OWORD *)((char *)a4 + 68) = 0;
  *(_OWORD *)((char *)a4 + 84) = 0;
  *((_DWORD *)a4 + 25) = 0;
  *(_DWORD *)a4 = 1;
  *((_WORD *)a4 + 28) = *((_WORD *)a2 + 2);
  *((_QWORD *)a4 + 6) = *((_QWORD *)a2 + 3);
  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_dD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a2, a3, *((unsigned int *)a2 + 1), *((_DWORD *)a2 + 12));
    v9 = WPP_GLOBAL_Control;
  }
  v10 = *((_DWORD *)a2 + 1);
  v11 = L"TRUE";
  if ( v10 )
  {
    switch ( v10 )
    {
      case 1:
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
          WPP_SF_S(*(_QWORD *)(v9 + 16), 13, WPP_bed9811735e730a365d52877ff824444_Traceguids, *((_QWORD *)a2 + 26));
        GetContextFromSignature(a2, *((const unsigned __int16 **)a2 + 26), 0, a3, a4);
        GetCOMContext(a2, a4);
        goto LABEL_72;
      case 2:
        memset_0(&v30, 0, 0x68u);
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
        {
          WPP_SF_Sd(
            *(_QWORD *)(v9 + 16),
            14,
            (unsigned int)WPP_bed9811735e730a365d52877ff824444_Traceguids,
            *((_QWORD *)a2 + 30),
            *((_DWORD *)a2 + 50));
          v9 = WPP_GLOBAL_Control;
        }
        v12 = *((_DWORD *)a2 + 50);
        if ( !v12 )
          goto LABEL_19;
        v13 = v12 - 1;
        if ( !v13 )
        {
          GetContextFromSignature(a2, *((const unsigned __int16 **)a2 + 30), 0, a3, a4);
          GetMSIContext(a1, a2, a4);
          goto LABEL_72;
        }
        v14 = v13 - 1;
        if ( v14 && (unsigned int)(v14 - 1) >= 2 )
        {
          v4 = 87;
          goto LABEL_73;
        }
LABEL_19:
        GetContextFromSignature(a2, *((const unsigned __int16 **)a2 + 30), 0, a3, a4);
        if ( (unsigned int)(*(_DWORD *)a4 - 2) > 1 )
          goto LABEL_28;
        memset_0(v31, 0, 0x64u);
        v15 = 0;
        v30 = 1;
        break;
      case 3:
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
          WPP_SF_S(*(_QWORD *)(v9 + 16), 16, WPP_bed9811735e730a365d52877ff824444_Traceguids, *((_QWORD *)a2 + 25));
        GetContextFromSignature(a2, *((const unsigned __int16 **)a2 + 25), 0, a3, a4);
        *a3 = 1;
        GetAxISContext(a2, a4);
        goto LABEL_72;
      case 4:
      case 6:
        goto LABEL_73;
      case 5:
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
          WPP_SF_SSS(
            *(_QWORD *)(v9 + 16),
            (unsigned int)&_ImageBase,
            (unsigned int)L"FALSE",
            *((_QWORD *)a2 + 26),
            *((_QWORD *)a2 + 27),
            *((_QWORD *)a2 + 28));
        GetPackagedAppContext(a2, a3, a4);
        goto LABEL_72;
      default:
        v4 = 87;
        goto LABEL_73;
    }
    while ( (unsigned int)v15 < *((_DWORD *)a2 + 64) )
    {
      GetContextFromSignature(
        a2,
        *(const unsigned __int16 **)(8 * v15 + *((_QWORD *)a2 + 33)),
        0,
        a3,
        (struct _CREDUI_CONTEXT *)&v30);
      if ( (unsigned int)(v30 - 2) > 1 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            15,
            (unsigned int)WPP_bed9811735e730a365d52877ff824444_Traceguids,
            *(_QWORD *)(8 * v15 + *((_QWORD *)a2 + 33)),
            v30);
        CuiFreeContextInformation(a4);
        *(_DWORD *)a4 = v30;
        CuiFreeContextInformation((struct _CREDUI_CONTEXT *)&v30);
        break;
      }
      CuiFreeContextInformation((struct _CREDUI_CONTEXT *)&v30);
      v15 = (unsigned int)(v15 + 1);
    }
LABEL_28:
    GetMSIContext(a1, a2, a4);
  }
  else
  {
    if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
      WPP_SF_S(*(_QWORD *)(v9 + 16), 11, WPP_bed9811735e730a365d52877ff824444_Traceguids, *((_QWORD *)a2 + 26));
    v16 = *((_QWORD *)a2 + 25);
    v17 = (const WCHAR *)*((_QWORD *)a2 + 26);
    *a3 = 0;
    if ( (*((_BYTE *)a2 + 48) & 0x20) != 0 )
    {
      *(_DWORD *)a4 = 1;
      BinarySignature = 0;
    }
    else
    {
      ppwsz = 0;
      BinarySignature = SHStrDupW(v17, &ppwsz);
      if ( BinarySignature >= 0 )
      {
        PathUnquoteSpacesW(ppwsz);
        if ( ImpersonateLoggedOnUser(*((HANDLE *)a2 + 3)) )
        {
          v20 = *((unsigned int *)a2 + 12);
          if ( (v20 & 1) == 0 || (v20 & 0x400) != 0 )
            v21 = 4096;
          else
            v21 = 0;
          if ( (unsigned int)(*((_DWORD *)a2 + 1) - 1) <= 1 )
            LOBYTE(v19) = 1;
          else
            v19 = 0;
          LOBYTE(v20) = v20 & 0x40;
          BinarySignature = CuiGetBinarySignature(
                              ppwsz,
                              v16,
                              v20,
                              v19,
                              v21,
                              a4,
                              a3,
                              (char *)a4 + 24,
                              (char *)a4 + 16,
                              (char *)a4 + 64,
                              (char *)a4 + 72);
          RevertToSelf();
        }
        else
        {
          LastError = GetLastError();
          BinarySignature = LastError;
          if ( LastError > 0 )
            BinarySignature = (unsigned __int16)LastError | 0x80070000;
        }
        CoTaskMemFree(ppwsz);
      }
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      v23 = L"TRUE";
      if ( !*a3 )
        v23 = L"FALSE";
      WPP_SF_DdS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        32,
        (unsigned int)L"FALSE",
        BinarySignature,
        *(_DWORD *)a4,
        (__int64)v23);
    }
    v24 = (const WCHAR *)*((_QWORD *)a2 + 27);
    if ( !v24 )
      v24 = (const WCHAR *)*((_QWORD *)a2 + 28);
    SHStrDupW(*((LPCWSTR *)a2 + 28), (LPWSTR *)a4 + 4);
    PathRemoveBlanksW(*((LPWSTR *)a4 + 4));
    if ( *((_QWORD *)a4 + 2) )
    {
      SystemMetrics = GetSystemMetrics(11);
      SHDefExtractIconW(v24, 0, 0, (HICON *)a4 + 1, 0, SystemMetrics);
    }
    else
    {
      FileNameW = PathFindFileNameW(v24);
      SHStrDupW(FileNameW, (LPWSTR *)a4 + 2);
    }
    BinaryLocation = CuiGetBinaryLocation(v24);
    v28 = *(unsigned int *)a4;
    *((_DWORD *)a4 + 15) = BinaryLocation;
    if ( (_DWORD)v28 && (*((_DWORD *)a2 + 12) & 0x800) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_bed9811735e730a365d52877ff824444_Traceguids, v28, 4);
      *(_DWORD *)a4 = 4;
    }
  }
LABEL_72:
  v9 = WPP_GLOBAL_Control;
LABEL_73:
  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
  {
    if ( !*a3 )
      v11 = L"FALSE";
    WPP_SF_DdS(*(_QWORD *)(v9 + 16), 18, (unsigned int)L"FALSE", v4, *(_DWORD *)a4, (__int64)v11);
  }
  return v4;
}

```

## disassembly

```asm
0x140003040  push    rbx
0x140003042  push    rbp
0x140003043  push    rsi
0x140003044  push    rdi
0x140003045  push    r12
0x140003047  push    r13
0x140003049  push    r14
0x14000304b  push    r15
0x14000304d  sub     rsp, 0D8h
0x140003054  xorps   xmm0, xmm0
0x140003057  xor     r14d, r14d
0x14000305a  movups  xmmword ptr [r9+4], xmm0
0x14000305f  xor     eax, eax
0x140003061  mov     rbx, r9
0x140003064  movups  xmmword ptr [r9+14h], xmm0
0x140003069  mov     r12, r8
0x14000306c  mov     rsi, rdx
0x14000306f  movups  xmmword ptr [r9+24h], xmm0
0x140003074  mov     rbp, rcx
0x140003077  movups  xmmword ptr [r9+34h], xmm0
0x14000307c  movups  xmmword ptr [r9+44h], xmm0
0x140003081  movups  xmmword ptr [r9+54h], xmm0
0x140003086  mov     [r9+64h], eax
0x14000308a  mov     dword ptr [r9], 1
0x140003091  movzx   eax, word ptr [rdx+4]
0x140003095  mov     [r9+38h], ax
0x14000309a  mov     rax, [rdx+18h]
0x14000309e  mov     [r9+30h], rax
0x1400030a2  mov     rdi, cs:WPP_GLOBAL_Control
0x1400030a9  lea     r15, WPP_GLOBAL_Control
0x1400030b0  cmp     rdi, r15
0x1400030b3  jz      short loc_1400030D6
0x1400030b5  test    byte ptr [rdi+1Ch], 2
0x1400030b9  jz      short loc_1400030D6
0x1400030bb  mov     eax, [rdx+30h]
0x1400030be  mov     r9d, [rdx+4]
0x1400030c2  mov     rcx, [rdi+10h]
0x1400030c6  mov     dword ptr [rsp+118h+phiconSmall], eax
0x1400030ca  call    WPP_SF_dD
0x1400030cf  mov     rdi, cs:WPP_GLOBAL_Control
0x1400030d6  mov     eax, [rsi+4]
0x1400030d9  lea     r8, aFalse; "FALSE"
0x1400030e0  lea     r13, aTrue; "TRUE"
0x1400030e7  test    eax, eax
0x1400030e9  jz      loc_1400033AE
0x1400030ef  dec     eax; switch 6 cases
0x1400030f1  cmp     eax, 5
0x1400030f4  ja      def_14000310D; jumptable 000000014000310D default case
0x1400030fa  lea     rdx, __ImageBase
0x140003101  cdqe
0x140003103  mov     ecx, ds:(jpt_14000310D - 140000000h)[rdx+rax*4]
0x14000310a  add     rcx, rdx
0x14000310d  jmp     rcx; switch jump
0x14000310f  cmp     rdi, r15; jumptable 000000014000310D case 1
0x140003112  jz      short loc_140003136
0x140003114  test    byte ptr [rdi+1Ch], 2
0x140003118  jz      short loc_140003136
0x14000311a  mov     r9, [rsi+0D0h]
0x140003121  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140003128  mov     rcx, [rdi+10h]
0x14000312c  mov     edx, 0Dh
0x140003131  call    WPP_SF_S
0x140003136  mov     rdx, [rsi+0D0h]; unsigned __int16 *
0x14000313d  mov     r9, r12; unsigned __int8 *
0x140003140  xor     r8d, r8d; void *
0x140003143  mov     [rsp+118h+phiconSmall], rbx; struct _CREDUI_CONTEXT *
0x140003148  mov     rcx, rsi; struct _CONSENTUI_PARAM_HEADER *
0x14000314b  call    ?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z; GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)
0x140003150  mov     rdx, rbx; struct _CREDUI_CONTEXT *
0x140003153  mov     rcx, rsi; struct _CONSENTUI_PARAM_COM *
0x140003156  call    ?GetCOMContext@@YAXPEAU_CONSENTUI_PARAM_COM@@PEAU_CREDUI_CONTEXT@@@Z; GetCOMContext(_CONSENTUI_PARAM_COM *,_CREDUI_CONTEXT *)
0x14000315b  jmp     loc_1400035E2
0x140003160  xor     edx, edx; jumptable 000000014000310D case 2
0x140003162  lea     rcx, [rsp+118h+var_B8]; void *
0x140003167  mov     r8d, 68h ; 'h'; Size
0x14000316d  call    memset_0
0x140003172  cmp     rdi, r15
0x140003175  jz      short loc_1400031AA
0x140003177  test    byte ptr [rdi+1Ch], 2
0x14000317b  jz      short loc_1400031AA
0x14000317d  mov     eax, [rsi+0C8h]
0x140003183  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x14000318a  mov     r9, [rsi+0F0h]
0x140003191  mov     edx, 0Eh
0x140003196  mov     rcx, [rdi+10h]
0x14000319a  mov     dword ptr [rsp+118h+phiconSmall], eax
0x14000319e  call    WPP_SF_Sd
0x1400031a3  mov     rdi, cs:WPP_GLOBAL_Control
0x1400031aa  mov     ecx, [rsi+0C8h]
0x1400031b0  test    ecx, ecx
0x1400031b2  jz      short loc_140003200
0x1400031b4  sub     ecx, 1
0x1400031b7  jz      short loc_1400031D3
0x1400031b9  sub     ecx, 1
0x1400031bc  jz      short loc_140003200
0x1400031be  sub     ecx, 1
0x1400031c1  jz      short loc_140003200
0x1400031c3  cmp     ecx, 1
0x1400031c6  jz      short loc_140003200
0x1400031c8  mov     r14d, 57h ; 'W'
0x1400031ce  jmp     loc_1400035E9
0x1400031d3  mov     rdx, [rsi+0F0h]; unsigned __int16 *
0x1400031da  mov     r9, r12; unsigned __int8 *
0x1400031dd  xor     r8d, r8d; void *
0x1400031e0  mov     [rsp+118h+phiconSmall], rbx; struct _CREDUI_CONTEXT *
0x1400031e5  mov     rcx, rsi; struct _CONSENTUI_PARAM_HEADER *
0x1400031e8  call    ?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z; GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)
0x1400031ed  mov     r8, rbx; struct _CREDUI_CONTEXT *
0x1400031f0  mov     rdx, rsi; struct _CONSENTUI_PARAM_MSI *
0x1400031f3  mov     rcx, rbp; HINSTANCE
0x1400031f6  call    ?GetMSIContext@@YAXPEAUHINSTANCE__@@PEAU_CONSENTUI_PARAM_MSI@@PEAU_CREDUI_CONTEXT@@@Z; GetMSIContext(HINSTANCE__ *,_CONSENTUI_PARAM_MSI *,_CREDUI_CONTEXT *)
0x1400031fb  jmp     loc_1400035E2
0x140003200  mov     rdx, [rsi+0F0h]; unsigned __int16 *
0x140003207  mov     r9, r12; unsigned __int8 *
0x14000320a  xor     r8d, r8d; void *
0x14000320d  mov     [rsp+118h+phiconSmall], rbx; struct _CREDUI_CONTEXT *
0x140003212  mov     rcx, rsi; struct _CONSENTUI_PARAM_HEADER *
0x140003215  call    ?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z; GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)
0x14000321a  mov     eax, [rbx]
0x14000321c  sub     eax, 2
0x14000321f  cmp     eax, 1
0x140003222  ja      loc_1400032F4
0x140003228  xor     edx, edx; Val
0x14000322a  lea     rcx, [rsp+118h+var_B4]; void *
0x14000322f  mov     r8d, 64h ; 'd'; Size
0x140003235  call    memset_0
0x14000323a  xor     edi, edi
0x14000323c  mov     [rsp+118h+var_B8], 1
0x140003244  cmp     edi, [rsi+100h]
0x14000324a  jnb     loc_1400032ED
0x140003250  mov     rdx, [rsi+108h]
0x140003257  lea     rax, [rsp+118h+var_B8]
0x14000325c  lea     r15, ds:0[rdi*8]
0x140003264  mov     [rsp+118h+phiconSmall], rax; struct _CREDUI_CONTEXT *
0x140003269  mov     r9, r12; unsigned __int8 *
0x14000326c  xor     r8d, r8d; void *
0x14000326f  mov     rcx, rsi; struct _CONSENTUI_PARAM_HEADER *
0x140003272  mov     rdx, [r15+rdx]; unsigned __int16 *
0x140003276  call    ?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z; GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)
0x14000327b  mov     r8d, [rsp+118h+var_B8]
0x140003280  lea     eax, [r8-2]
0x140003284  cmp     eax, 1
0x140003287  ja      short loc_140003297
0x140003289  lea     rcx, [rsp+118h+var_B8]; struct _CREDUI_CONTEXT *
0x14000328e  call    ?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z; CuiFreeContextInformation(_CREDUI_CONTEXT *)
0x140003293  inc     edi
0x140003295  jmp     short loc_140003244
0x140003297  mov     rcx, cs:WPP_GLOBAL_Control
0x14000329e  lea     rax, WPP_GLOBAL_Control
0x1400032a5  cmp     rcx, rax
0x1400032a8  jz      short loc_1400032D5
0x1400032aa  test    byte ptr [rcx+1Ch], 2
0x1400032ae  jz      short loc_1400032D5
0x1400032b0  mov     r9, [rsi+108h]
0x1400032b7  mov     edx, 0Fh
0x1400032bc  mov     rcx, [rcx+10h]
0x1400032c0  mov     dword ptr [rsp+118h+phiconSmall], r8d
0x1400032c5  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x1400032cc  mov     r9, [r15+r9]
0x1400032d0  call    WPP_SF_Sd
0x1400032d5  mov     rcx, rbx; struct _CREDUI_CONTEXT *
0x1400032d8  call    ?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z; CuiFreeContextInformation(_CREDUI_CONTEXT *)
0x1400032dd  mov     eax, [rsp+118h+var_B8]
0x1400032e1  lea     rcx, [rsp+118h+var_B8]; struct _CREDUI_CONTEXT *
0x1400032e6  mov     [rbx], eax
0x1400032e8  call    ?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z; CuiFreeContextInformation(_CREDUI_CONTEXT *)
0x1400032ed  lea     r15, WPP_GLOBAL_Control
0x1400032f4  mov     r8, rbx; struct _CREDUI_CONTEXT *
0x1400032f7  mov     rdx, rsi; struct _CONSENTUI_PARAM_MSI *
0x1400032fa  mov     rcx, rbp; HINSTANCE
0x1400032fd  call    ?GetMSIContext@@YAXPEAUHINSTANCE__@@PEAU_CONSENTUI_PARAM_MSI@@PEAU_CREDUI_CONTEXT@@@Z; GetMSIContext(HINSTANCE__ *,_CONSENTUI_PARAM_MSI *,_CREDUI_CONTEXT *)
0x140003302  jmp     loc_1400035E2
0x140003307  cmp     rdi, r15; jumptable 000000014000310D case 3
0x14000330a  jz      short loc_14000332E
0x14000330c  test    byte ptr [rdi+1Ch], 2
0x140003310  jz      short loc_14000332E
0x140003312  mov     r9, [rsi+0C8h]
0x140003319  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140003320  mov     rcx, [rdi+10h]
0x140003324  mov     edx, 10h
0x140003329  call    WPP_SF_S
0x14000332e  mov     rdx, [rsi+0C8h]; unsigned __int16 *
0x140003335  mov     r9, r12; unsigned __int8 *
0x140003338  xor     r8d, r8d; void *
0x14000333b  mov     [rsp+118h+phiconSmall], rbx; struct _CREDUI_CONTEXT *
0x140003340  mov     rcx, rsi; struct _CONSENTUI_PARAM_HEADER *
0x140003343  call    ?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z; GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)
0x140003348  mov     rdx, rbx; struct _CREDUI_CONTEXT *
0x14000334b  mov     byte ptr [r12], 1
0x140003350  mov     rcx, rsi; struct _CONSENTUI_PARAM_AXIS *
0x140003353  call    ?GetAxISContext@@YAXPEAU_CONSENTUI_PARAM_AXIS@@PEAU_CREDUI_CONTEXT@@@Z; GetAxISContext(_CONSENTUI_PARAM_AXIS *,_CREDUI_CONTEXT *)
0x140003358  jmp     loc_1400035E2
0x14000335d  cmp     rdi, r15; jumptable 000000014000310D case 5
0x140003360  jz      short loc_140003390
0x140003362  test    byte ptr [rdi+1Ch], 2
0x140003366  jz      short loc_140003390
0x140003368  mov     rax, [rsi+0E0h]
0x14000336f  mov     r9, [rsi+0D0h]
0x140003376  mov     rcx, [rdi+10h]
0x14000337a  mov     qword ptr [rsp+118h+nIconSize], rax
0x14000337f  mov     rax, [rsi+0D8h]
0x140003386  mov     [rsp+118h+phiconSmall], rax
0x14000338b  call    WPP_SF_SSS
0x140003390  mov     r8, rbx; struct _CREDUI_CONTEXT *
0x140003393  mov     rdx, r12; unsigned __int8 *
0x140003396  mov     rcx, rsi; struct _CONSENTUI_PARAM_PACKAGED_APP *
0x140003399  call    ?GetPackagedAppContext@@YAXPEAU_CONSENTUI_PARAM_PACKAGED_APP@@PEAEPEAU_CREDUI_CONTEXT@@@Z; GetPackagedAppContext(_CONSENTUI_PARAM_PACKAGED_APP *,uchar *,_CREDUI_CONTEXT *)
0x14000339e  jmp     loc_1400035E2
0x1400033a3  mov     r14d, 57h ; 'W'; jumptable 000000014000310D default case
0x1400033a9  jmp     loc_1400035F0; jumptable 000000014000310D cases 4,6
0x1400033ae  cmp     rdi, r15
0x1400033b1  jz      short loc_1400033DC
0x1400033b3  test    byte ptr [rdi+1Ch], 2
0x1400033b7  jz      short loc_1400033DC
0x1400033b9  mov     r9, [rsi+0D0h]
0x1400033c0  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x1400033c7  mov     rcx, [rdi+10h]
0x1400033cb  mov     edx, 0Bh
0x1400033d0  call    WPP_SF_S
0x1400033d5  lea     r8, aFalse; "FALSE"
0x1400033dc  mov     rbp, [rsi+0C8h]
0x1400033e3  mov     rcx, [rsi+0D0h]; psz
0x1400033ea  mov     [r12], r14b
0x1400033ee  test    byte ptr [rsi+30h], 20h
0x1400033f2  jz      short loc_140003401
0x1400033f4  mov     dword ptr [rbx], 1
0x1400033fa  xor     edi, edi
0x1400033fc  jmp     loc_1400034E3
0x140003401  lea     rdx, [rsp+118h+ppwsz]; ppwsz
0x140003409  mov     [rsp+118h+ppwsz], r14
0x140003411  call    cs:__imp_SHStrDupW
0x140003417  mov     edi, eax
0x140003419  test    eax, eax
0x14000341b  js      loc_1400034DC
0x140003421  mov     rcx, [rsp+118h+ppwsz]; lpsz
0x140003429  call    cs:__imp_PathUnquoteSpacesW
0x14000342f  mov     rcx, [rsi+18h]; hToken
0x140003433  call    cs:__imp_ImpersonateLoggedOnUser
0x140003439  test    eax, eax
0x14000343b  jz      short loc_1400034B9
0x14000343d  mov     r8d, [rsi+30h]
0x140003441  lea     rdx, [rbx+48h]
0x140003445  lea     r10, [rbx+40h]
0x140003449  lea     r11, [rbx+10h]
0x14000344d  lea     rdi, [rbx+18h]
0x140003451  test    r8b, 1
0x140003455  jz      short loc_140003462
0x140003457  bt      r8d, 0Ah
0x14000345c  jb      short loc_140003462
0x14000345e  xor     ecx, ecx
0x140003460  jmp     short loc_140003467
0x140003462  mov     ecx, 1000h
0x140003467  mov     eax, [rsi+4]
0x14000346a  dec     eax
0x14000346c  cmp     eax, 1
0x14000346f  jbe     short loc_140003476
0x140003471  xor     r9d, r9d
0x140003474  jmp     short loc_140003479
0x140003476  mov     r9b, 1
0x140003479  mov     [rsp+118h+var_C8], rdx
0x14000347e  and     r8b, 40h
0x140003482  mov     [rsp+118h+var_D0], r10
0x140003487  mov     rdx, rbp
0x14000348a  mov     [rsp+118h+var_D8], r11
0x14000348f  mov     [rsp+118h+var_E0], rdi
0x140003494  mov     [rsp+118h+var_E8], r12
0x140003499  mov     qword ptr [rsp+118h+nIconSize], rbx
0x14000349e  mov     dword ptr [rsp+118h+phiconSmall], ecx
0x1400034a2  mov     rcx, [rsp+118h+ppwsz]
0x1400034aa  call    ?CuiGetBinarySignature@@YAJPEBGPEAXEEW4SIGNATURE_INFO_FLAGS@@PEAW4_CONTEXT_SIGNATURE@@PEAEPEAPEAG5PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CuiGetBinarySignature(ushort const *,void *,uchar,uchar,SIGNATURE_INFO_FLAGS,_CONTEXT_SIGNATURE *,uchar *,ushort * *,ushort * *,_CERT_CONTEXT const * *,void * *)
0x1400034af  mov     edi, eax
0x1400034b1  call    cs:__imp_RevertToSelf
0x1400034b7  jmp     short loc_1400034CE
0x1400034b9  call    cs:__imp_GetLastError
0x1400034bf  mov     edi, eax
0x1400034c1  test    eax, eax
0x1400034c3  jle     short loc_1400034CE
0x1400034c5  movzx   edi, ax
0x1400034c8  or      edi, 80070000h
0x1400034ce  mov     rcx, [rsp+118h+ppwsz]; pv
0x1400034d6  call    cs:__imp_CoTaskMemFree
0x1400034dc  lea     r8, aFalse; "FALSE"
0x1400034e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034ea  cmp     rcx, r15
0x1400034ed  jz      short loc_14000351C
0x1400034ef  test    byte ptr [rcx+1Ch], 2
0x1400034f3  jz      short loc_14000351C
0x1400034f5  cmp     [r12], r14b
0x1400034f9  mov     rax, r13
0x1400034fc  mov     rcx, [rcx+10h]
0x140003500  mov     edx, 20h ; ' '
0x140003505  cmovz   rax, r8
0x140003509  mov     r9d, edi
0x14000350c  mov     qword ptr [rsp+118h+nIconSize], rax
0x140003511  mov     eax, [rbx]
0x140003513  mov     dword ptr [rsp+118h+phiconSmall], eax
0x140003517  call    WPP_SF_DdS
0x14000351c  mov     rbp, [rsi+0D8h]
0x140003523  test    rbp, rbp
0x140003526  jnz     short loc_14000352F
  ... truncated ...
```
