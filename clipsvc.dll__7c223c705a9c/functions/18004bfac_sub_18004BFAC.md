# sub_18004BFAC

- ea: `0x18004bfac`
- end: `0x18004c4f5`
- name: `sub_18004BFAC`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800439d0`

## callees

- `0x180002800`
- `0x180007180`
- `0x180007768`
- `0x1800082e0`
- `0x1800095b0`
- `0x1800097a8`
- `0x18000bfdc`
- `0x18000e0c0`
- `0x18000e180`
- `0x1800141d8`
- `0x180021174`
- `0x180041058`
- `0x18004107c`
- `0x1800411f4`
- `0x180042ccc`
- `0x18004bfac`
- `0x18004c544`
- `0x18004c86c`
- `0x18004d4a4`
- `0x18004dabc`
- `0x18004db80`
- `0x18004f148`
- `0x18004f704`
- `0x18004fc48`
- `0x180050778`
- `0x180051534`
- `0x1800a6ac0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004c0a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004c0a1`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004c059`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004c059`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c493`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c493`

## string_xrefs

- `0x18004c111`: `<?xml version="1.0" encoding="utf-8"?>`
- `0x18004c130`: `<ClipDiagReport serviceVersion='%s' date='%s'>`
- `0x18004c1e0`: `<GetAllInstalledPackages hrRet='0x%08X' filterflag='%d' originfilter='%d' packagefilter='%d' packagefiltername='%s' count='%d'>`
- `0x18004c389`: `</GetAllInstalledPackages>`

## pseudocode

```c
__int64 __fastcall sub_18004BFAC(__int64 a1, unsigned int a2, int a3, int a4, wchar_t *a5, _QWORD *a6)
{
  __int64 v6; // r14
  const wchar_t *v7; // rsi
  int v11; // ebx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // ecx
  __int64 v19; // r15
  int i; // esi
  __int64 v21; // r8
  int v22; // r12d
  int v23; // r13d
  int j; // r14d
  __int64 v25; // rdi
  __int64 v26; // rdi
  __int64 v27; // rax
  int v29; // [rsp+20h] [rbp-E0h]
  int v30[2]; // [rsp+20h] [rbp-E0h]
  wchar_t *Str; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  _QWORD v39[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  _QWORD *v46; // [rsp+B8h] [rbp-48h]
  int v47[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  _OWORD v49[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v50; // [rsp+108h] [rbp+8h]
  struct _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF

  v6 = a1;
  v7 = a5;
  v45 = a1;
  v46 = a6;
  v40 = a2;
  sub_180007768(Src);
  v11 = 0;
  v43 = 0;
  SystemTime = 0;
  v42 = 0;
  v32 = 0;
  v39[0] = 0;
  v39[1] = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v35 = 0;
  v34 = 0;
  v41 = 0;
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  v36 = 0;
  v12 = RoInitialize(1);
  v13 = v12;
  if ( v12 >= 0 )
    v11 = 1;
  else
    sub_18000BFDC((unsigned int)v12);
  sub_18000E0C0(v13);
  if ( (v13 & 0x80000000) != 0 )
  {
    v14 = v13;
LABEL_6:
    sub_18000BFDC(v14);
    goto LABEL_52;
  }
  v15 = sub_180051534(v47);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  GetSystemTime(&SystemTime);
  v15 = sub_180021174(&SystemTime, &v42);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v15 = sub_18004D4A4(&v41);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v15 = sub_18004DABC(v41, v49);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v29 = HIWORD(HIDWORD(v49[0]));
  v15 = sub_1800097A8(&v43, L"%d.%d.%d.%d", HIWORD(DWORD2(v49[0])), WORD4(v49[0]));
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v15 = sub_1800141D8(Src, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>");
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v15 = sub_1800082E0(Src, L"<ClipDiagReport serviceVersion='%s' date='%s'>", v43, v42);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  if ( (int)sub_180042CCC(v16, v39) >= 0 )
  {
    sub_180007180(&v32);
    v15 = sub_180050778(v39, &v32);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
    v15 = sub_1800141D8(Src, v32);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
  }
  v17 = sub_18004C544((int)v47, a2, a3, a4, v29, a5, (__int64)&v37);
  v18 = 0;
  if ( v17 >= 0 )
    v18 = HIDWORD(v37);
  if ( !a5 )
    v7 = L"(none)";
  LODWORD(Str) = a4;
  v30[0] = a3;
  v15 = sub_1800082E0(
          Src,
          L"<GetAllInstalledPackages hrRet='0x%08X' filterflag='%d' originfilter='%d' packagefilter='%d' packagefiltername"
           "='%s' count='%d'>",
          (unsigned int)v17,
          a2,
          *(_QWORD *)v30,
          Str,
          v7,
          v18);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  v19 = v38;
  for ( i = 0; i < SHIDWORD(v37); ++i )
  {
    v21 = *(_QWORD *)(v19 + 24LL * i);
    v44 = 3LL * i;
    v15 = sub_1800082E0(Src, L"<PackageFamily name='%s'>", v21);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
    v22 = 0;
    v23 = 0;
    for ( j = 0; ; ++j )
    {
      v25 = v44;
      if ( j >= *(_DWORD *)(v19 + 8 * v44 + 12) )
        break;
      v26 = *(_QWORD *)(v19 + 8 * v44 + 16);
      sub_180007180(&v32);
      v15 = sub_18004F704(v26 + 48LL * j, &v34, &v35, &v32);
      v13 = v15;
      if ( v15 < 0 )
        goto LABEL_8;
      v15 = sub_1800141D8(Src, v32);
      v13 = v15;
      if ( v15 < 0 )
        goto LABEL_8;
      v23 |= v34;
      v22 |= v35;
    }
    if ( v22 )
    {
      if ( !v23 && HIDWORD(v39[0]) )
      {
        sub_180007180(&v32);
        v15 = sub_18004FC48(
                *(_QWORD *)(v19 + 8 * v25),
                (unsigned int)L"perUserLicenseResults",
                0,
                (unsigned int)v39,
                (__int64)&v32);
        v13 = v15;
        if ( v15 < 0 )
          goto LABEL_8;
        v15 = sub_1800141D8(Src, v32);
        v13 = v15;
        if ( v15 < 0 )
          goto LABEL_8;
        v25 = v44;
      }
      sub_180007180(&v32);
      v6 = v45;
      v15 = sub_18004C86C(v45, *(_QWORD *)(v19 + 8 * v25), &v32);
      v13 = v15;
      if ( v15 < 0 )
        goto LABEL_8;
      v15 = sub_1800141D8(Src, v32);
      v13 = v15;
      if ( v15 < 0 )
        goto LABEL_8;
    }
    else
    {
      v6 = v45;
    }
    v15 = sub_1800141D8(Src, L"</PackageFamily>");
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
  }
  v15 = sub_1800141D8(Src, L"</GetAllInstalledPackages>");
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_8;
  if ( (v40 & 0xC) == 0 )
  {
    sub_180007180(&v32);
    v15 = sub_18004F148(v6, &v37, v39, &v32);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
    v15 = sub_1800141D8(Src, v32);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_8;
  }
  sub_180007180(&v32);
  v15 = sub_18004DB80(v6, &v32);
  v13 = v15;
  if ( v15 < 0
    || (v15 = sub_1800141D8(Src, v32), v13 = v15, v15 < 0)
    || (v15 = sub_1800141D8(Src, L"</ClipDiagReport>"), v13 = v15, v15 < 0)
    || (v15 = sub_18000E180(Src[0]), v13 = v15, v15 < 0) )
  {
LABEL_8:
    v14 = (unsigned int)v15;
    goto LABEL_6;
  }
  v27 = v36;
  v36 = 0;
  *v46 = v27;
LABEL_52:
  sub_18000E0C0(v13);
  sub_1800095B0(&v36);
  sub_1800095B0(&v41);
  sub_1800411F4(v47);
  if ( v11 )
    RoUninitialize();
  sub_18004107C(&v37);
  sub_180041058(v39);
  sub_1800095B0(&v32);
  sub_1800095B0(&v42);
  sub_1800095B0(&v43);
  sub_180002800(Src);
  return v13;
}

```

## disassembly

```asm
0x18004bfac  push    rbp
0x18004bfae  push    rbx
0x18004bfaf  push    rsi
0x18004bfb0  push    rdi
0x18004bfb1  push    r12
0x18004bfb3  push    r13
0x18004bfb5  push    r14
0x18004bfb7  push    r15
0x18004bfb9  lea     rbp, [rsp-38h]
0x18004bfbe  sub     rsp, 138h
0x18004bfc5  mov     rax, cs:__security_cookie
0x18004bfcc  xor     rax, rsp
0x18004bfcf  mov     [rbp+70h+var_50], rax
0x18004bfd3  mov     rax, [rbp+70h+arg_28]
0x18004bfda  mov     r14, rcx
0x18004bfdd  mov     rsi, [rbp+70h+arg_20]
0x18004bfe4  mov     r12d, r9d
0x18004bfe7  mov     [rbp+70h+var_C0], rcx
0x18004bfeb  mov     r15d, r8d
0x18004bfee  lea     rcx, [rsp+170h+Src]
0x18004bff3  mov     [rbp+70h+var_B8], rax
0x18004bff7  mov     r13d, edx
0x18004bffa  mov     [rbp+70h+var_E8], edx
0x18004bffd  call    sub_180007768
0x18004c002  xor     ebx, ebx
0x18004c004  xorps   xmm0, xmm0
0x18004c007  xor     eax, eax
0x18004c009  mov     [rbp+70h+var_D0], rbx
0x18004c00d  movups  xmmword ptr [rbp+70h+SystemTime.wYear], xmm0
0x18004c011  mov     [rbp+70h+var_D8], rbx
0x18004c015  lea     ecx, [rbx+1]
0x18004c018  mov     [rsp+170h+var_130], rbx
0x18004c01d  mov     [rsp+170h+var_F8], rbx
0x18004c022  mov     [rbp+70h+var_F0], rbx
0x18004c026  mov     [rsp+170h+var_108], rbx
0x18004c02b  mov     [rsp+170h+var_100], rbx
0x18004c030  movdqu  xmmword ptr [rbp+70h+var_B0], xmm0
0x18004c035  mov     [rbp+70h+var_A0], rbx
0x18004c039  mov     [rsp+170h+var_114], ebx
0x18004c03d  mov     [rsp+170h+var_118], ebx
0x18004c041  mov     [rbp+70h+var_E0], rbx
0x18004c045  movups  [rbp+70h+var_98], xmm0
0x18004c049  mov     [rbp+70h+var_68], eax
0x18004c04c  movups  [rbp+70h+var_88], xmm0
0x18004c050  mov     [rsp+170h+var_110], rbx
0x18004c055  movups  [rbp+70h+var_78], xmm0
0x18004c059  call    cs:RoInitialize
0x18004c05f  mov     edi, eax
0x18004c061  test    eax, eax
0x18004c063  jns     short loc_18004C06E
0x18004c065  mov     ecx, eax
0x18004c067  call    sub_18000BFDC
0x18004c06c  jmp     short loc_18004C073
0x18004c06e  mov     ebx, 1
0x18004c073  mov     ecx, edi
0x18004c075  call    sub_18000E0C0
0x18004c07a  test    edi, edi
0x18004c07c  jns     short loc_18004C08A
0x18004c07e  mov     ecx, edi
0x18004c080  call    sub_18000BFDC
0x18004c085  jmp     loc_18004C46C
0x18004c08a  lea     rcx, [rbp+70h+var_B0]
0x18004c08e  call    sub_180051534
0x18004c093  mov     edi, eax
0x18004c095  test    eax, eax
0x18004c097  jns     short loc_18004C09D
0x18004c099  mov     ecx, eax
0x18004c09b  jmp     short loc_18004C080
0x18004c09d  lea     rcx, [rbp+70h+SystemTime]; lpSystemTime
0x18004c0a1  call    cs:GetSystemTime
0x18004c0a7  lea     rdx, [rbp+70h+var_D8]
0x18004c0ab  lea     rcx, [rbp+70h+SystemTime]
0x18004c0af  call    sub_180021174
0x18004c0b4  mov     edi, eax
0x18004c0b6  test    eax, eax
0x18004c0b8  js      short loc_18004C099
0x18004c0ba  lea     rcx, [rbp+70h+var_E0]
0x18004c0be  call    sub_18004D4A4
0x18004c0c3  mov     edi, eax
0x18004c0c5  test    eax, eax
0x18004c0c7  js      short loc_18004C099
0x18004c0c9  mov     rcx, [rbp+70h+var_E0]
0x18004c0cd  lea     rdx, [rbp+70h+var_98]
0x18004c0d1  call    sub_18004DABC
0x18004c0d6  mov     edi, eax
0x18004c0d8  test    eax, eax
0x18004c0da  js      short loc_18004C099
0x18004c0dc  mov     ecx, dword ptr [rbp+70h+var_98+0Ch]
0x18004c0df  lea     rdx, aDDDD; "%d.%d.%d.%d"
0x18004c0e6  movzx   eax, word ptr [rbp+70h+var_98+0Ch]
0x18004c0ea  mov     r8d, dword ptr [rbp+70h+var_98+8]
0x18004c0ee  movzx   r9d, word ptr [rbp+70h+var_98+8]
0x18004c0f3  shr     ecx, 10h
0x18004c0f6  mov     dword ptr [rsp+170h+Str], eax
0x18004c0fa  mov     [rsp+170h+var_150], ecx; int
0x18004c0fe  lea     rcx, [rbp+70h+var_D0]
0x18004c102  shr     r8d, 10h
0x18004c106  call    sub_1800097A8
0x18004c10b  mov     edi, eax
0x18004c10d  test    eax, eax
0x18004c10f  js      short loc_18004C099
0x18004c111  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18004c118  lea     rcx, [rsp+170h+Src]
0x18004c11d  call    sub_1800141D8
0x18004c122  mov     edi, eax
0x18004c124  test    eax, eax
0x18004c126  js      loc_18004C099
0x18004c12c  mov     r9, [rbp+70h+var_D8]
0x18004c130  lea     rdx, aClipdiagreport; "<ClipDiagReport serviceVersion='%s' dat"...
0x18004c137  mov     r8, [rbp+70h+var_D0]
0x18004c13b  lea     rcx, [rsp+170h+Src]
0x18004c140  call    sub_1800082E0
0x18004c145  mov     edi, eax
0x18004c147  test    eax, eax
0x18004c149  js      loc_18004C099
0x18004c14f  lea     rdx, [rsp+170h+var_F8]
0x18004c154  call    sub_180042CCC
0x18004c159  test    eax, eax
0x18004c15b  js      short loc_18004C199
0x18004c15d  lea     rcx, [rsp+170h+var_130]
0x18004c162  call    sub_180007180
0x18004c167  lea     rdx, [rsp+170h+var_130]
0x18004c16c  lea     rcx, [rsp+170h+var_F8]
0x18004c171  call    sub_180050778
0x18004c176  mov     edi, eax
0x18004c178  test    eax, eax
0x18004c17a  js      loc_18004C099
0x18004c180  mov     rdx, [rsp+170h+var_130]
0x18004c185  lea     rcx, [rsp+170h+Src]
0x18004c18a  call    sub_1800141D8
0x18004c18f  mov     edi, eax
0x18004c191  test    eax, eax
0x18004c193  js      loc_18004C099
0x18004c199  lea     rax, [rsp+170h+var_108]
0x18004c19e  mov     r9d, r12d; int
0x18004c1a1  mov     [rsp+170h+var_140], rax; __int64
0x18004c1a6  lea     rcx, [rbp+70h+var_B0]; int
0x18004c1aa  mov     r8d, r15d; int
0x18004c1ad  mov     [rsp+170h+Str], rsi; Str
0x18004c1b2  mov     edx, r13d; int
0x18004c1b5  call    sub_18004C544
0x18004c1ba  xor     ecx, ecx
0x18004c1bc  lea     rdx, aNone_0; "(none)"
0x18004c1c3  test    eax, eax
0x18004c1c5  mov     r9d, r13d
0x18004c1c8  mov     r8d, eax
0x18004c1cb  cmovns  ecx, dword ptr [rsp+170h+var_108+4]
0x18004c1d0  test    rsi, rsi
0x18004c1d3  mov     [rsp+170h+var_138], ecx
0x18004c1d7  lea     rcx, [rsp+170h+Src]
0x18004c1dc  cmovz   rsi, rdx
0x18004c1e0  lea     rdx, aGetallinstalle; "<GetAllInstalledPackages hrRet='0x%08X'"...
0x18004c1e7  mov     [rsp+170h+var_140], rsi
0x18004c1ec  mov     dword ptr [rsp+170h+Str], r12d
0x18004c1f1  mov     [rsp+170h+var_150], r15d
0x18004c1f6  call    sub_1800082E0
0x18004c1fb  mov     edi, eax
0x18004c1fd  test    eax, eax
0x18004c1ff  js      loc_18004C099
0x18004c205  mov     r15, [rsp+170h+var_100]
0x18004c20a  xor     esi, esi
0x18004c20c  lea     rcx, [rsp+170h+Src]
0x18004c211  cmp     esi, dword ptr [rsp+170h+var_108+4]
0x18004c215  jge     loc_18004C389
0x18004c21b  movsxd  rax, esi
0x18004c21e  lea     rdx, aPackagefamilyN; "<PackageFamily name='%s'>"
0x18004c225  lea     rax, [rax+rax*2]
0x18004c229  mov     r8, [r15+rax*8]
0x18004c22d  mov     [rbp+70h+var_C8], rax
0x18004c231  call    sub_1800082E0
0x18004c236  mov     edi, eax
0x18004c238  test    eax, eax
0x18004c23a  js      loc_18004C099
0x18004c240  xor     r12d, r12d
0x18004c243  xor     r13d, r13d
0x18004c246  xor     r14d, r14d
0x18004c249  mov     rdi, [rbp+70h+var_C8]
0x18004c24d  cmp     r14d, [r15+rdi*8+0Ch]
0x18004c252  jge     short loc_18004C2B7
0x18004c254  mov     rdi, [r15+rdi*8+10h]
0x18004c259  lea     rcx, [rsp+170h+var_130]
0x18004c25e  call    sub_180007180
0x18004c263  movsxd  rax, r14d
0x18004c266  lea     r9, [rsp+170h+var_130]
0x18004c26b  lea     r8, [rsp+170h+var_114]
0x18004c270  lea     rdx, [rsp+170h+var_118]
0x18004c275  lea     rcx, [rax+rax*2]
0x18004c279  shl     rcx, 4
0x18004c27d  add     rcx, rdi
0x18004c280  call    sub_18004F704
0x18004c285  mov     edi, eax
0x18004c287  test    eax, eax
0x18004c289  js      loc_18004C099
0x18004c28f  mov     rdx, [rsp+170h+var_130]
0x18004c294  lea     rcx, [rsp+170h+Src]
0x18004c299  call    sub_1800141D8
0x18004c29e  mov     edi, eax
0x18004c2a0  test    eax, eax
0x18004c2a2  js      loc_18004C099
0x18004c2a8  or      r13d, [rsp+170h+var_118]
0x18004c2ad  or      r12d, [rsp+170h+var_114]
0x18004c2b2  inc     r14d
0x18004c2b5  jmp     short loc_18004C249
0x18004c2b7  test    r12d, r12d
0x18004c2ba  jz      loc_18004C363
0x18004c2c0  test    r13d, r13d
0x18004c2c3  jnz     short loc_18004C31F
0x18004c2c5  cmp     dword ptr [rsp+170h+var_F8+4], r13d
0x18004c2ca  jz      short loc_18004C31F
0x18004c2cc  lea     rcx, [rsp+170h+var_130]
0x18004c2d1  call    sub_180007180
0x18004c2d6  mov     rcx, [r15+rdi*8]
0x18004c2da  lea     rax, [rsp+170h+var_130]
0x18004c2df  lea     r9, [rsp+170h+var_F8]
0x18004c2e4  mov     qword ptr [rsp+170h+var_150], rax
0x18004c2e9  xor     r8d, r8d
0x18004c2ec  lea     rdx, aPeruserlicense; "perUserLicenseResults"
0x18004c2f3  call    sub_18004FC48
0x18004c2f8  mov     edi, eax
0x18004c2fa  test    eax, eax
0x18004c2fc  js      loc_18004C099
0x18004c302  mov     rdx, [rsp+170h+var_130]
0x18004c307  lea     rcx, [rsp+170h+Src]
0x18004c30c  call    sub_1800141D8
0x18004c311  mov     edi, eax
0x18004c313  test    eax, eax
0x18004c315  js      loc_18004C099
0x18004c31b  mov     rdi, [rbp+70h+var_C8]
0x18004c31f  lea     rcx, [rsp+170h+var_130]
0x18004c324  call    sub_180007180
0x18004c329  mov     r14, [rbp+70h+var_C0]
0x18004c32d  lea     r8, [rsp+170h+var_130]
0x18004c332  mov     rdx, [r15+rdi*8]
0x18004c336  mov     rcx, r14
0x18004c339  call    sub_18004C86C
0x18004c33e  mov     edi, eax
0x18004c340  test    eax, eax
0x18004c342  js      loc_18004C099
0x18004c348  mov     rdx, [rsp+170h+var_130]
0x18004c34d  lea     rcx, [rsp+170h+Src]
0x18004c352  call    sub_1800141D8
0x18004c357  mov     edi, eax
0x18004c359  test    eax, eax
0x18004c35b  js      loc_18004C099
0x18004c361  jmp     short loc_18004C367
0x18004c363  mov     r14, [rbp+70h+var_C0]
0x18004c367  lea     rdx, aPackagefamily; "</PackageFamily>"
0x18004c36e  lea     rcx, [rsp+170h+Src]
0x18004c373  call    sub_1800141D8
0x18004c378  mov     edi, eax
0x18004c37a  test    eax, eax
0x18004c37c  js      loc_18004C099
0x18004c382  inc     esi
0x18004c384  jmp     loc_18004C20C
0x18004c389  lea     rdx, aGetallinstalle_0; "</GetAllInstalledPackages>"
0x18004c390  call    sub_1800141D8
0x18004c395  mov     edi, eax
0x18004c397  test    eax, eax
0x18004c399  js      loc_18004C099
0x18004c39f  test    byte ptr [rbp+70h+var_E8], 0Ch
0x18004c3a3  jnz     short loc_18004C3E9
0x18004c3a5  lea     rcx, [rsp+170h+var_130]
0x18004c3aa  call    sub_180007180
0x18004c3af  lea     r9, [rsp+170h+var_130]
0x18004c3b4  mov     rcx, r14
0x18004c3b7  lea     r8, [rsp+170h+var_F8]
0x18004c3bc  lea     rdx, [rsp+170h+var_108]
0x18004c3c1  call    sub_18004F148
0x18004c3c6  mov     edi, eax
0x18004c3c8  test    eax, eax
0x18004c3ca  js      loc_18004C099
0x18004c3d0  mov     rdx, [rsp+170h+var_130]
0x18004c3d5  lea     rcx, [rsp+170h+Src]
0x18004c3da  call    sub_1800141D8
0x18004c3df  mov     edi, eax
0x18004c3e1  test    eax, eax
0x18004c3e3  js      loc_18004C099
0x18004c3e9  lea     rcx, [rsp+170h+var_130]
0x18004c3ee  call    sub_180007180
0x18004c3f3  lea     rdx, [rsp+170h+var_130]
0x18004c3f8  mov     rcx, r14
0x18004c3fb  call    sub_18004DB80
0x18004c400  mov     edi, eax
0x18004c402  test    eax, eax
0x18004c404  js      loc_18004C099
0x18004c40a  mov     rdx, [rsp+170h+var_130]
0x18004c40f  lea     rcx, [rsp+170h+Src]
0x18004c414  call    sub_1800141D8
0x18004c419  mov     edi, eax
0x18004c41b  test    eax, eax
0x18004c41d  js      loc_18004C099
0x18004c423  lea     rdx, aClipdiagreport_0; "</ClipDiagReport>"
0x18004c42a  lea     rcx, [rsp+170h+Src]
0x18004c42f  call    sub_1800141D8
0x18004c434  mov     edi, eax
0x18004c436  test    eax, eax
0x18004c438  js      loc_18004C099
0x18004c43e  mov     rcx, [rsp+170h+Src]; Src
0x18004c443  lea     rdx, [rsp+170h+var_110]
0x18004c448  call    sub_18000E180
  ... truncated ...
```
