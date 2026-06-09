# LoadIconFromXMLData

- ea: `0x1800074d4`
- end: `0x180007910`
- name: `LoadIconFromXMLData`
- size: `1084`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180007114`

## callees

- `0x180002c40`
- `0x180007258`
- `0x180007420`
- `0x1800074d4`
- `0x180007cb8`
- `0x180007da0`
- `0x18000a5b0`

## import_xrefs

- `USER32!DestroyIcon` at `0x180007886`
- `USER32!DestroyIcon` at `0x180007898`
- `USER32!DestroyIcon` at `0x1800078aa`
- `USER32!DestroyIcon` at `0x180007886`
- `USER32!DestroyIcon` at `0x180007898`
- `USER32!DestroyIcon` at `0x1800078aa`
- `KERNEL32!WideCharToMultiByte` at `0x180007630`
- `KERNEL32!WideCharToMultiByte` at `0x180007679`
- `KERNEL32!WideCharToMultiByte` at `0x1800076c7`
- `KERNEL32!WideCharToMultiByte` at `0x180007630`
- `KERNEL32!WideCharToMultiByte` at `0x180007679`
- `KERNEL32!WideCharToMultiByte` at `0x1800076c7`
- `KERNEL32!GlobalFree` at `0x1800078c2`
- `KERNEL32!GlobalFree` at `0x1800078d0`
- `KERNEL32!GlobalFree` at `0x1800078de`
- `KERNEL32!GlobalFree` at `0x1800078c2`
- `KERNEL32!GlobalFree` at `0x1800078d0`
- `KERNEL32!GlobalFree` at `0x1800078de`

## pseudocode

```c
__int64 __fastcall LoadIconFromXMLData(unsigned __int8 *a1, unsigned __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  HGLOBAL v4; // r14
  char v5; // al
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rsp
  unsigned __int64 v9; // r12
  void *v10; // rsp
  unsigned __int64 v11; // r15
  HICON v12; // r13
  HICON v13; // rsi
  int IconData; // eax
  HGLOBAL v15; // r12
  int v16; // ebx
  int v17; // eax
  HICON v18; // r15
  __int64 v19; // rbx
  int v20; // eax
  HGLOBAL v21; // rdi
  CSmartIcon *v22; // rcx
  __int64 v24; // [rsp-20h] [rbp-E0h] BYREF
  CHAR v25[32]; // [rsp+20h] [rbp-A0h] BYREF
  LPCCH v26; // [rsp+50h] [rbp-70h] BYREF
  CHAR v27[16]; // [rsp+60h] [rbp-60h] BYREF
  CHAR MultiByteStr[48]; // [rsp+90h] [rbp-30h] BYREF
  HGLOBAL v29; // [rsp+C0h] [rbp+0h] BYREF
  HICON v30; // [rsp+C8h] [rbp+8h] BYREF
  HICON v31; // [rsp+D0h] [rbp+10h] BYREF
  HGLOBAL v32; // [rsp+D8h] [rbp+18h] BYREF
  unsigned __int64 v33; // [rsp+E0h] [rbp+20h]
  HGLOBAL hMem; // [rsp+E8h] [rbp+28h] BYREF
  HICON hIcon; // [rsp+F0h] [rbp+30h] BYREF
  __int64 v36; // [rsp+F8h] [rbp+38h]
  unsigned __int8 *v37; // [rsp+150h] [rbp+90h] BYREF
  unsigned __int64 v38; // [rsp+158h] [rbp+98h] BYREF

  v38 = a2;
  v37 = a1;
  v3 = 1;
  v36 = a3;
  v4 = 0;
  if ( a2 < 2 )
    goto LABEL_18;
  v5 = a1[1];
  if ( v5 == -1 && *a1 == 0xFE )
  {
    a1 += 3;
    v37 = a1;
    if ( a2 <= 2 )
      v6 = 0;
    else
      v6 = a2 - 3;
    goto LABEL_7;
  }
  if ( *a1 != 0xFF )
  {
    if ( *a1 != 0xEF || v5 != -69 || a1[2] != 0xBF )
      goto LABEL_18;
    a1 += 3;
    v37 = a1;
    if ( a2 <= 2 )
      a2 = 0;
    else
      a2 -= 3LL;
    goto LABEL_17;
  }
  if ( v5 == -2 )
  {
    a1 += 2;
    v37 = a1;
    v6 = a2 - 2;
LABEL_7:
    a2 = v6 >> 1;
    v3 = 2;
LABEL_17:
    v38 = a2;
  }
LABEL_18:
  if ( !a2 )
    return 2147500037LL;
  do
  {
    if ( *a1 > 0x20u )
      break;
    v7 = 0x100002600LL;
    if ( !_bittest64(&v7, (char)*a1) )
      break;
    a1 += v3;
    v37 = a1;
    if ( a2 <= v3 )
    {
      a2 = 0;
      v38 = 0;
      break;
    }
    a2 -= v3;
    v38 = a2;
  }
  while ( a2 );
  if ( !a2 || *a1 != 60 )
    return 2147500037LL;
  v8 = alloca(48);
  if ( &v26 == (LPCCH *)-64LL )
  {
    LODWORD(v9) = 0;
  }
  else
  {
    MultiByteStr[0] = 0;
    v9 = (unsigned __int64)MultiByteStr
       & -(__int64)(WideCharToMultiByte(0, 0, L"CONSOLE_FILE_ICON_LARGE", -1, MultiByteStr, 48, 0, 0) != 0);
  }
  v10 = alloca(48);
  if ( v25 == (CHAR *)-64LL )
  {
    LODWORD(v11) = 0;
  }
  else
  {
    v27[0] = 0;
    v11 = (unsigned __int64)v27
        & -(__int64)(WideCharToMultiByte(0, 0, L"CONSOLE_FILE_ICON_SMALL", -1, v27, 48, 0, 0) != 0);
  }
  if ( &v24 == (__int64 *)-64LL )
  {
    v33 = 0;
  }
  else
  {
    v25[0] = 0;
    v33 = (unsigned __int64)v25
        & -(__int64)(WideCharToMultiByte(
                       0,
                       0,
                       (LPCWCH)"C\x00O\x00N\x00S\x00O\x00L\x00E\x00_\x00F\x00I\x00L\x00E\x00_\x00I\x00C\x00O\x00N\x00_\x00L\x00A\x00R\x00G\x00E\x004\x008\x00x",
                       -1,
                       v25,
                       54,
                       0,
                       0) != 0);
  }
  hIcon = 0;
  v31 = 0;
  v30 = 0;
  hMem = 0;
  v12 = 0;
  v32 = 0;
  v13 = 0;
  v29 = 0;
  IconData = FindAndReadIconData((unsigned int)&v37, v3, (unsigned int)&v38, v9, (__int64)&hMem);
  v15 = hMem;
  v16 = IconData;
  if ( IconData >= 0 )
  {
    v16 = FindAndReadIconData((unsigned int)&v37, v3, (unsigned int)&v38, v11, (__int64)&v32);
    if ( v16 >= 0 )
    {
      v17 = LoadIconFromHGlobal(v15, &hIcon);
      v18 = hIcon;
      v16 = v17;
      v4 = v32;
      if ( v17 >= 0 )
      {
        v16 = LoadIconFromHGlobal(v32, &v31);
        if ( v16 >= 0 )
        {
          v19 = v36;
          CSmartIcon::Attach((CSmartIcon *)(v36 + 48), v18);
          v12 = v31;
          CSmartIcon::Attach((CSmartIcon *)(v19 + 40), v31);
          v20 = FindAndReadIconData((unsigned int)&v37, v3, (unsigned int)&v38, v33, (__int64)&v29);
          if ( v20 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_425635d597cf3634a5269b3442d551b5_Traceguids,
                (unsigned int)v20);
            v21 = v29;
          }
          else
          {
            v21 = v29;
            v16 = LoadIconFromHGlobal(v29, &v30);
            v22 = (CSmartIcon *)(v36 + 56);
            if ( v16 < 0 )
            {
              CSmartIcon::Empty(v22);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  WPP_425635d597cf3634a5269b3442d551b5_Traceguids,
                  (unsigned int)v16);
              v13 = v30;
              goto LABEL_54;
            }
            v13 = v30;
            CSmartIcon::Attach(v22, v30);
          }
          v16 = 0;
LABEL_54:
          if ( v18 && v16 < 0 )
            DestroyIcon(v18);
          if ( v12 && v16 < 0 )
            DestroyIcon(v12);
          if ( v13 && v16 < 0 )
            DestroyIcon(v13);
          goto LABEL_65;
        }
        v12 = v31;
      }
      v21 = v29;
      goto LABEL_54;
    }
    v4 = v32;
  }
  v21 = v29;
LABEL_65:
  if ( v15 )
    GlobalFree(v15);
  if ( v4 )
    GlobalFree(v4);
  if ( v21 )
    GlobalFree(v21);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800074d4  mov     [rsp-8+arg_8], rdx
0x1800074d9  mov     [rsp-8+arg_0], rcx
0x1800074de  push    rbp
0x1800074df  push    rsi
0x1800074e0  push    rdi
0x1800074e1  push    r12
0x1800074e3  push    r13
0x1800074e5  push    r14
0x1800074e7  push    r15
0x1800074e9  sub     rsp, 90h
0x1800074f0  lea     rbp, [rsp+40h]
0x1800074f5  mov     [rbp+80h+arg_10], rbx
0x1800074fc  mov     rax, cs:__security_cookie
0x180007503  xor     rax, rbp
0x180007506  mov     [rbp+80h+var_40], rax
0x18000750a  mov     edi, 1
0x18000750f  mov     [rbp+80h+var_48], r8
0x180007513  xor     r14d, r14d
0x180007516  lea     r8d, [rdi+1]
0x18000751a  cmp     rdx, r8
0x18000751d  jb      short loc_180007594
0x18000751f  mov     al, [rcx+1]
0x180007522  cmp     al, 0FFh
0x180007524  jnz     short loc_18000754C
0x180007526  cmp     byte ptr [rcx], 0FEh
0x180007529  jnz     short loc_18000754C
0x18000752b  add     rcx, 3
0x18000752f  mov     [rbp+80h+arg_0], rcx
0x180007536  cmp     rdx, r8
0x180007539  jbe     short loc_180007541
0x18000753b  add     rdx, 0FFFFFFFFFFFFFFFDh
0x18000753f  jmp     short loc_180007544
0x180007541  mov     rdx, r14
0x180007544  shr     rdx, 1
0x180007547  mov     edi, r8d
0x18000754a  jmp     short loc_18000758D
0x18000754c  cmp     byte ptr [rcx], 0FFh
0x18000754f  jnz     short loc_180007565
0x180007551  cmp     al, 0FEh
0x180007553  jnz     short loc_180007594
0x180007555  add     rcx, r8
0x180007558  mov     [rbp+80h+arg_0], rcx
0x18000755f  add     rdx, 0FFFFFFFFFFFFFFFEh
0x180007563  jmp     short loc_180007544
0x180007565  cmp     byte ptr [rcx], 0EFh
0x180007568  jnz     short loc_180007594
0x18000756a  cmp     al, 0BBh
0x18000756c  jnz     short loc_180007594
0x18000756e  cmp     byte ptr [rcx+2], 0BFh
0x180007572  jnz     short loc_180007594
0x180007574  add     rcx, 3
0x180007578  mov     [rbp+80h+arg_0], rcx
0x18000757f  cmp     rdx, r8
0x180007582  jbe     short loc_18000758A
0x180007584  add     rdx, 0FFFFFFFFFFFFFFFDh
0x180007588  jmp     short loc_18000758D
0x18000758a  mov     rdx, r14
0x18000758d  mov     [rbp+80h+arg_8], rdx
0x180007594  test    rdx, rdx
0x180007597  jz      loc_1800078E8
0x18000759d  cmp     byte ptr [rcx], 20h ; ' '
0x1800075a0  ja      short loc_1800075DF
0x1800075a2  movsx   rax, byte ptr [rcx]
0x1800075a6  mov     r8, 100002600h
0x1800075b0  bt      r8, rax
0x1800075b4  jnb     short loc_1800075DF
0x1800075b6  mov     eax, edi
0x1800075b8  add     rcx, rax
0x1800075bb  mov     [rbp+80h+arg_0], rcx
0x1800075c2  cmp     rdx, rax
0x1800075c5  jbe     short loc_1800075D5
0x1800075c7  sub     rdx, rax
0x1800075ca  mov     [rbp+80h+arg_8], rdx
0x1800075d1  jnz     short loc_18000759D
0x1800075d3  jmp     short loc_1800075DF
0x1800075d5  mov     rdx, r14
0x1800075d8  mov     [rbp+80h+arg_8], rdx
0x1800075df  test    rdx, rdx
0x1800075e2  jz      loc_1800078E8
0x1800075e8  cmp     byte ptr [rcx], 3Ch ; '<'
0x1800075eb  jnz     loc_1800078E8
0x1800075f1  mov     eax, dword ptr [rsp+0C0h+lpDefaultChar]
0x1800075f4  mov     esi, 30h ; '0'
0x1800075f9  sub     rsp, rsi
0x1800075fc  lea     rbx, [rsp+0F0h+MultiByteStr]
0x180007601  mov     eax, [rbx]
0x180007603  or      r13d, 0FFFFFFFFh
0x180007607  test    rbx, rbx
0x18000760a  jz      short loc_180007640
0x18000760c  mov     [rsp+0F0h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180007611  lea     r8, WideCharStr; "CONSOLE_FILE_ICON_LARGE"
0x180007618  mov     [rsp+0F0h+lpDefaultChar], r14; lpDefaultChar
0x18000761d  mov     r9d, r13d; cchWideChar
0x180007620  mov     [rsp+0F0h+cbMultiByte], esi; cbMultiByte
0x180007624  xor     edx, edx; dwFlags
0x180007626  xor     ecx, ecx; CodePage
0x180007628  mov     [rsp+0F0h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000762d  mov     [rbx], r14b
0x180007630  call    cs:__imp_WideCharToMultiByte
0x180007636  neg     eax
0x180007638  sbb     r12, r12
0x18000763b  and     r12, rbx
0x18000763e  jmp     short loc_180007643
0x180007640  mov     r12, r14
0x180007643  mov     eax, dword ptr [rsp+0F0h+var_F0]
0x180007646  sub     rsp, rsi
0x180007649  lea     rbx, [rsp+120h+var_E0]
0x18000764e  mov     eax, [rbx]
0x180007650  test    rbx, rbx
0x180007653  jz      short loc_180007689
0x180007655  mov     [rsp+120h+var_E8], r14; lpUsedDefaultChar
0x18000765a  lea     r8, aConsoleFileIco; "CONSOLE_FILE_ICON_SMALL"
0x180007661  mov     [rsp+120h+var_F0], r14; lpDefaultChar
0x180007666  mov     r9d, r13d; cchWideChar
0x180007669  mov     [rsp+120h+var_F8], esi; cbMultiByte
0x18000766d  xor     edx, edx; dwFlags
0x18000766f  xor     ecx, ecx; CodePage
0x180007671  mov     [rsp+120h+var_100], rbx; lpMultiByteStr
0x180007676  mov     [rbx], r14b
0x180007679  call    cs:__imp_WideCharToMultiByte
0x18000767f  neg     eax
0x180007681  sbb     r15, r15
0x180007684  and     r15, rbx
0x180007687  jmp     short loc_18000768C
0x180007689  mov     r15, r14
0x18000768c  mov     eax, dword ptr [rsp+120h+var_120]
0x18000768f  sub     rsp, 40h
0x180007693  lea     rbx, [rsp+160h+var_120]
0x180007698  mov     eax, [rbx]
0x18000769a  test    rbx, rbx
0x18000769d  jz      short loc_1800076DB
0x18000769f  mov     [rsp+160h+var_128], r14; lpUsedDefaultChar
0x1800076a4  lea     r8, ?_six2pr64@base64_table@@1PAEA+40h; lpWideCharStr
0x1800076ab  mov     [rsp+160h+var_130], r14; lpDefaultChar
0x1800076b0  mov     r9d, r13d; cchWideChar
0x1800076b3  mov     [rsp+160h+var_138], 36h ; '6'; cbMultiByte
0x1800076bb  xor     edx, edx; dwFlags
0x1800076bd  xor     ecx, ecx; CodePage
0x1800076bf  mov     [rsp+160h+var_140], rbx; lpMultiByteStr
0x1800076c4  mov     [rbx], r14b
0x1800076c7  call    cs:__imp_WideCharToMultiByte
0x1800076cd  neg     eax
0x1800076cf  sbb     rax, rax
0x1800076d2  and     rax, rbx
0x1800076d5  mov     [rbp+80h+var_60], rax
0x1800076d9  jmp     short loc_1800076DF
0x1800076db  mov     [rbp+80h+var_60], r14
0x1800076df  lea     rax, [rbp+80h+hMem]
0x1800076e3  mov     [rbp+80h+hIcon], r14
0x1800076e7  mov     r9, r12
0x1800076ea  mov     [rsp+160h+var_140], rax
0x1800076ef  lea     r8, [rbp+80h+arg_8]
0x1800076f6  mov     [rbp+80h+var_70], r14
0x1800076fa  mov     edx, edi
0x1800076fc  mov     [rbp+80h+var_78], r14
0x180007700  lea     rcx, [rbp+80h+arg_0]
0x180007707  mov     [rbp+80h+hMem], r14
0x18000770b  mov     r13, r14
0x18000770e  mov     [rbp+80h+var_68], r14
0x180007712  mov     rsi, r14
0x180007715  mov     [rbp+80h+var_80], r14
0x180007719  call    FindAndReadIconData
0x18000771e  mov     r12, [rbp+80h+hMem]
0x180007722  mov     ebx, eax
0x180007724  test    eax, eax
0x180007726  js      loc_1800078B6
0x18000772c  lea     rax, [rbp+80h+var_68]
0x180007730  mov     r9, r15
0x180007733  lea     r8, [rbp+80h+arg_8]
0x18000773a  mov     [rsp+160h+var_140], rax
0x18000773f  mov     edx, edi
0x180007741  lea     rcx, [rbp+80h+arg_0]
0x180007748  call    FindAndReadIconData
0x18000774d  mov     ebx, eax
0x18000774f  test    eax, eax
0x180007751  js      loc_1800078B2
0x180007757  lea     rdx, [rbp+80h+hIcon]
0x18000775b  mov     rcx, r12
0x18000775e  call    LoadIconFromHGlobal
0x180007763  mov     r15, [rbp+80h+hIcon]
0x180007767  mov     ebx, eax
0x180007769  mov     r14, [rbp+80h+var_68]
0x18000776d  test    eax, eax
0x18000776f  js      loc_180007876
0x180007775  lea     rdx, [rbp+80h+var_70]
0x180007779  mov     rcx, r14
0x18000777c  call    LoadIconFromHGlobal
0x180007781  mov     ebx, eax
0x180007783  test    eax, eax
0x180007785  js      loc_180007872
0x18000778b  mov     rbx, [rbp+80h+var_48]
0x18000778f  mov     rdx, r15; HICON
0x180007792  lea     rcx, [rbx+30h]; this
0x180007796  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x18000779b  mov     r13, [rbp+80h+var_70]
0x18000779f  lea     rcx, [rbx+28h]; this
0x1800077a3  mov     rdx, r13; HICON
0x1800077a6  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x1800077ab  mov     r9, [rbp+80h+var_60]
0x1800077af  lea     rax, [rbp+80h+var_80]
0x1800077b3  lea     r8, [rbp+80h+arg_8]
0x1800077ba  mov     [rsp+160h+var_140], rax
0x1800077bf  mov     edx, edi
0x1800077c1  lea     rcx, [rbp+80h+arg_0]
0x1800077c8  call    FindAndReadIconData
0x1800077cd  mov     r9d, eax
0x1800077d0  test    eax, eax
0x1800077d2  js      short loc_18000783C
0x1800077d4  mov     rdi, [rbp+80h+var_80]
0x1800077d8  lea     rdx, [rbp+80h+var_78]
0x1800077dc  mov     rcx, rdi
0x1800077df  call    LoadIconFromHGlobal
0x1800077e4  mov     rcx, [rbp+80h+var_48]
0x1800077e8  mov     ebx, eax
0x1800077ea  add     rcx, 38h ; '8'; this
0x1800077ee  test    eax, eax
0x1800077f0  js      short loc_180007800
0x1800077f2  mov     rsi, [rbp+80h+var_78]
0x1800077f6  mov     rdx, rsi; HICON
0x1800077f9  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x1800077fe  jmp     short loc_18000786E
0x180007800  call    ?Empty@CSmartIcon@@QEAAXXZ; CSmartIcon::Empty(void)
0x180007805  mov     rcx, cs:WPP_GLOBAL_Control
0x18000780c  lea     rax, WPP_GLOBAL_Control
0x180007813  cmp     rcx, rax
0x180007816  jz      short loc_180007836
0x180007818  cmp     byte ptr [rcx+19h], 4
0x18000781c  jb      short loc_180007836
0x18000781e  mov     rcx, [rcx+10h]
0x180007822  lea     r8, WPP_425635d597cf3634a5269b3442d551b5_Traceguids
0x180007829  mov     edx, 0Ah
0x18000782e  mov     r9d, ebx
0x180007831  call    WPP_SF_d
0x180007836  mov     rsi, [rbp+80h+var_78]
0x18000783a  jmp     short loc_18000787A
0x18000783c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007843  lea     rax, WPP_GLOBAL_Control
0x18000784a  cmp     rcx, rax
0x18000784d  jz      short loc_18000786A
0x18000784f  cmp     byte ptr [rcx+19h], 4
0x180007853  jb      short loc_18000786A
0x180007855  mov     rcx, [rcx+10h]
0x180007859  lea     r8, WPP_425635d597cf3634a5269b3442d551b5_Traceguids
0x180007860  mov     edx, 0Bh
0x180007865  call    WPP_SF_d
0x18000786a  mov     rdi, [rbp+80h+var_80]
0x18000786e  xor     ebx, ebx
0x180007870  jmp     short loc_18000787A
0x180007872  mov     r13, [rbp+80h+var_70]
0x180007876  mov     rdi, [rbp+80h+var_80]
0x18000787a  test    r15, r15
0x18000787d  jz      short loc_18000788C
0x18000787f  test    ebx, ebx
0x180007881  jns     short loc_18000788C
0x180007883  mov     rcx, r15; hIcon
0x180007886  call    cs:__imp_DestroyIcon
0x18000788c  test    r13, r13
0x18000788f  jz      short loc_18000789E
0x180007891  test    ebx, ebx
0x180007893  jns     short loc_18000789E
0x180007895  mov     rcx, r13; hIcon
0x180007898  call    cs:__imp_DestroyIcon
0x18000789e  test    rsi, rsi
0x1800078a1  jz      short loc_1800078BA
0x1800078a3  test    ebx, ebx
0x1800078a5  jns     short loc_1800078BA
0x1800078a7  mov     rcx, rsi; hIcon
0x1800078aa  call    cs:__imp_DestroyIcon
0x1800078b0  jmp     short loc_1800078BA
0x1800078b2  mov     r14, [rbp+80h+var_68]
0x1800078b6  mov     rdi, [rbp+80h+var_80]
0x1800078ba  test    r12, r12
0x1800078bd  jz      short loc_1800078C8
0x1800078bf  mov     rcx, r12; hMem
0x1800078c2  call    cs:__imp_GlobalFree
0x1800078c8  test    r14, r14
0x1800078cb  jz      short loc_1800078D6
0x1800078cd  mov     rcx, r14; hMem
0x1800078d0  call    cs:__imp_GlobalFree
0x1800078d6  test    rdi, rdi
0x1800078d9  jz      short loc_1800078E4
0x1800078db  mov     rcx, rdi; hMem
0x1800078de  call    cs:__imp_GlobalFree
0x1800078e4  mov     eax, ebx
0x1800078e6  jmp     short loc_1800078ED
0x1800078e8  mov     eax, 80004005h
0x1800078ed  mov     rcx, [rbp+80h+var_40]
0x1800078f1  xor     rcx, rbp; StackCookie
0x1800078f4  call    __security_check_cookie
0x1800078f9  mov     rbx, [rbp+80h+arg_10]
0x180007900  lea     rsp, [rbp+50h]
0x180007904  pop     r15
0x180007906  pop     r14
0x180007908  pop     r13
0x18000790a  pop     r12
0x18000790c  pop     rdi
0x18000790d  pop     rsi
0x18000790e  pop     rbp
0x18000790f  retn
```
