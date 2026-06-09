# CFaxConfigUI::InitializePages(void)

- ea: `0x18000fd8c`
- end: `0x180010191`
- name: `?InitializePages@CFaxConfigUI@@AEAAKXZ`
- size: `1029`
- prototype: `unsigned int __fastcall(CFaxConfigUI *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800101a0`

## callees

- `0x180001f9c`
- `0x180001fc4`
- `0x180005eac`
- `0x180005ed4`
- `0x18000fc3c`
- `0x18000fd8c`
- `0x180010970`
- `0x180013b44`
- `0x1800145b4`
- `0x1800155f8`
- `0x180015cbe`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010141`
- `KERNEL32!GetLastError` at `0x180010141`

## pseudocode

```c
__int64 __fastcall CFaxConfigUI::InitializePages(CFaxConfigUI *this)
{
  void *v2; // rax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  struct ISecurityInformationVtbl **v7; // rsi
  _QWORD *v8; // rbx
  CConfigGeneralPage *v9; // rcx
  unsigned int v10; // eax
  _DWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // rax
  _QWORD *v15; // rdx
  __int64 v16; // rbx
  unsigned int TrackingOptions; // eax
  _QWORD *v18; // rax
  _QWORD *v19; // rdx
  CConfigAdvancedPage *v20; // rcx
  HPROPSHEETPAGE FaxSecurityPage; // rax
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids);
  }
  *((_DWORD *)this + 12) = 3;
  v2 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 4) = v2;
  if ( !v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v4 = 11;
LABEL_10:
    WPP_SF_(v3[2], v4, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids);
LABEL_11:
    v5 = 8;
LABEL_67:
    CFaxConfigUI::CleanUp(this);
    return v5;
  }
  *(_DWORD *)(*((_QWORD *)this + 3) + 136LL) = 4;
  v6 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (struct ISecurityInformationVtbl **)((char *)this + 8);
  v8 = v6;
  if ( v6 )
  {
    v6[1] = *v7;
    *((_DWORD *)v6 + 4) = 4600;
    *((_DWORD *)v6 + 6) = 4651;
    *v6 = &CConfigGeneralPage::`vftable';
    v6[4] = 0;
    *((_DWORD *)v6 + 10) = 0;
    memset_0(v6 + 6, 0, 0x48u);
    v8[15] = 0;
    *((_DWORD *)v8 + 32) = 0;
  }
  else
  {
    v8 = 0;
  }
  **((_QWORD **)this + 4) = v8;
  v9 = (CConfigGeneralPage *)**((_QWORD **)this + 4);
  if ( !v9 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v4 = 12;
    goto LABEL_10;
  }
  v10 = CConfigGeneralPage::Init(v9, *((void **)this + 7));
  v5 = v10;
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v12 = 13;
    goto LABEL_25;
  }
  v14 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    v14[1] = *v7;
    *((_DWORD *)v14 + 4) = 4603;
    *((_DWORD *)v14 + 6) = 4652;
    *v14 = &CConfigTrackingPage::`vftable';
  }
  else
  {
    v15 = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = v15;
  v16 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL);
  if ( !v16 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v4 = 14;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  TrackingOptions = LoadTrackingOptions((LPBYTE)(v16 + 32));
  v5 = TrackingOptions;
  if ( TrackingOptions )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_67;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids,
        TrackingOptions);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 == (_DWORD *)&WPP_GLOBAL_Control || (v11[7] & 0x100) == 0 || *((_BYTE *)v11 + 25) < 2u )
      goto LABEL_67;
    v12 = 15;
    v13 = v5;
    goto LABEL_26;
  }
  v18 = operator new(0x248u, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v18;
  if ( v18 )
  {
    v18[1] = *v7;
    *((_DWORD *)v18 + 4) = 4601;
    *((_DWORD *)v18 + 6) = 4653;
    *v18 = &CConfigAdvancedPage::`vftable';
    v18[4] = 0;
    *((_DWORD *)v18 + 140) = 0;
    v18[71] = 0;
    *((_DWORD *)v18 + 144) = 0;
  }
  else
  {
    v19 = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = v19;
  v20 = *(CConfigAdvancedPage **)(*((_QWORD *)this + 4) + 16LL);
  if ( !v20 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v4 = 16;
    goto LABEL_10;
  }
  v10 = CConfigAdvancedPage::Init(v20, *((void **)this + 7));
  v5 = v10;
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v12 = 17;
LABEL_25:
    v13 = v10;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids, v13);
    goto LABEL_67;
  }
  FaxSecurityPage = CreateFaxSecurityPage(*((struct ISecurityInformationVtbl **)this + 7), *v7);
  *((_QWORD *)this + 5) = FaxSecurityPage;
  if ( !FaxSecurityPage )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids, LastError);
    }
    if ( v5 )
      goto LABEL_67;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fd8c  push    rbx
0x18000fd8e  push    rsi
0x18000fd8f  push    rdi
0x18000fd90  push    r12
0x18000fd92  push    r14
0x18000fd94  push    r15
0x18000fd96  sub     rsp, 28h
0x18000fd9a  mov     rdi, rcx
0x18000fd9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fda4  lea     r15, WPP_GLOBAL_Control
0x18000fdab  lea     r12, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids
0x18000fdb2  mov     r14d, 100h
0x18000fdb8  cmp     rcx, r15
0x18000fdbb  jz      short loc_18000FDDA
0x18000fdbd  test    [rcx+1Ch], r14d
0x18000fdc1  jz      short loc_18000FDDA
0x18000fdc3  cmp     byte ptr [rcx+19h], 5
0x18000fdc7  jb      short loc_18000FDDA
0x18000fdc9  mov     rcx, [rcx+10h]
0x18000fdcd  mov     edx, 0Ah
0x18000fdd2  mov     r8, r12
0x18000fdd5  call    WPP_SF_
0x18000fdda  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fde1  mov     dword ptr [rdi+30h], 3
0x18000fde8  mov     ecx, 18h; unsigned __int64
0x18000fded  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fdf2  mov     [rdi+20h], rax
0x18000fdf6  test    rax, rax
0x18000fdf9  jnz     short loc_18000FE2C
0x18000fdfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe02  cmp     rcx, r15
0x18000fe05  jz      short loc_18000FE22
0x18000fe07  test    [rcx+1Ch], r14d
0x18000fe0b  jz      short loc_18000FE22
0x18000fe0d  cmp     byte ptr [rcx+19h], 2
0x18000fe11  jb      short loc_18000FE22
0x18000fe13  lea     edx, [rax+0Bh]
0x18000fe16  mov     rcx, [rcx+10h]
0x18000fe1a  mov     r8, r12
0x18000fe1d  call    WPP_SF_
0x18000fe22  mov     ebx, 8
0x18000fe27  jmp     loc_180010179
0x18000fe2c  mov     rax, [rdi+18h]
0x18000fe30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fe37  mov     ecx, 88h; unsigned __int64
0x18000fe3c  mov     dword ptr [rax+88h], 4
0x18000fe46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fe4b  lea     rsi, [rdi+8]
0x18000fe4f  mov     rbx, rax
0x18000fe52  test    rax, rax
0x18000fe55  jz      short loc_18000FEA8
0x18000fe57  mov     rcx, [rsi]
0x18000fe5a  xor     edx, edx; Val
0x18000fe5c  mov     [rax+8], rcx
0x18000fe60  lea     rcx, [rbx+30h]; void *
0x18000fe64  mov     dword ptr [rax+10h], 11F8h
0x18000fe6b  mov     dword ptr [rax+18h], 122Bh
0x18000fe72  lea     rax, ??_7CConfigGeneralPage@@6B@; const CConfigGeneralPage::`vftable'
0x18000fe79  lea     r8d, [rdx+48h]; Size
0x18000fe7d  mov     [rbx], rax
0x18000fe80  mov     qword ptr [rbx+20h], 0
0x18000fe88  mov     dword ptr [rbx+28h], 0
0x18000fe8f  call    memset_0
0x18000fe94  mov     qword ptr [rbx+78h], 0
0x18000fe9c  mov     dword ptr [rbx+80h], 0
0x18000fea6  jmp     short loc_18000FEAA
0x18000fea8  xor     ebx, ebx
0x18000feaa  mov     rax, [rdi+20h]
0x18000feae  mov     [rax], rbx
0x18000feb1  mov     rax, [rdi+20h]
0x18000feb5  mov     rcx, [rax]; this
0x18000feb8  test    rcx, rcx
0x18000febb  jnz     short loc_18000FEEB
0x18000febd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fec4  cmp     rcx, r15
0x18000fec7  jz      loc_18000FE22
0x18000fecd  test    [rcx+1Ch], r14d
0x18000fed1  jz      loc_18000FE22
0x18000fed7  cmp     byte ptr [rcx+19h], 2
0x18000fedb  jb      loc_18000FE22
0x18000fee1  mov     edx, 0Ch
0x18000fee6  jmp     loc_18000FE16
0x18000feeb  mov     rdx, [rdi+38h]; void *
0x18000feef  call    ?Init@CConfigGeneralPage@@QEAAKPEAX@Z; CConfigGeneralPage::Init(void *)
0x18000fef4  mov     ebx, eax
0x18000fef6  test    eax, eax
0x18000fef8  jz      short loc_18000FF37
0x18000fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff01  cmp     rcx, r15
0x18000ff04  jz      loc_180010179
0x18000ff0a  test    [rcx+1Ch], r14d
0x18000ff0e  jz      loc_180010179
0x18000ff14  cmp     byte ptr [rcx+19h], 2
0x18000ff18  jb      loc_180010179
0x18000ff1e  mov     edx, 0Dh
0x18000ff23  mov     r9d, eax
0x18000ff26  mov     rcx, [rcx+10h]
0x18000ff2a  mov     r8, r12
0x18000ff2d  call    WPP_SF_d
0x18000ff32  jmp     loc_180010179
0x18000ff37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ff3e  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000ff43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ff48  mov     rdx, rax
0x18000ff4b  test    rax, rax
0x18000ff4e  jz      short loc_18000FF71
0x18000ff50  mov     rcx, [rsi]
0x18000ff53  mov     [rax+8], rcx
0x18000ff57  mov     dword ptr [rax+10h], 11FBh
0x18000ff5e  mov     dword ptr [rax+18h], 122Ch
0x18000ff65  lea     rax, ??_7CConfigTrackingPage@@6B@; const CConfigTrackingPage::`vftable'
0x18000ff6c  mov     [rdx], rax
0x18000ff6f  jmp     short loc_18000FF73
0x18000ff71  xor     edx, edx
0x18000ff73  mov     rax, [rdi+20h]
0x18000ff77  mov     [rax+8], rdx
0x18000ff7b  mov     rax, [rdi+20h]
0x18000ff7f  mov     rbx, [rax+8]
0x18000ff83  test    rbx, rbx
0x18000ff86  jnz     short loc_18000FFB4
0x18000ff88  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff8f  cmp     rcx, r15
0x18000ff92  jz      loc_18000FE22
0x18000ff98  test    [rcx+1Ch], r14d
0x18000ff9c  jz      loc_18000FE22
0x18000ffa2  cmp     byte ptr [rcx+19h], 2
0x18000ffa6  jb      loc_18000FE22
0x18000ffac  lea     edx, [rbx+0Eh]
0x18000ffaf  jmp     loc_18000FE16
0x18000ffb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffbb  cmp     rcx, r15
0x18000ffbe  jz      short loc_18000FFE1
0x18000ffc0  test    [rcx+1Ch], r14d
0x18000ffc4  jz      short loc_18000FFE1
0x18000ffc6  cmp     byte ptr [rcx+19h], 5
0x18000ffca  jb      short loc_18000FFE1
0x18000ffcc  mov     rcx, [rcx+10h]
0x18000ffd0  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x18000ffd7  mov     edx, 0Ah
0x18000ffdc  call    WPP_SF_
0x18000ffe1  lea     rcx, [rbx+20h]; lpData
0x18000ffe5  call    LoadTrackingOptions
0x18000ffea  mov     ebx, eax
0x18000ffec  test    eax, eax
0x18000ffee  jz      short loc_180010055
0x18000fff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fff7  cmp     rcx, r15
0x18000fffa  jz      loc_180010179
0x180010000  test    [rcx+1Ch], r14d
0x180010004  jz      short loc_18001002B
0x180010006  cmp     byte ptr [rcx+19h], 2
0x18001000a  jb      short loc_18001002B
0x18001000c  mov     rcx, [rcx+10h]
0x180010010  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180010017  mov     edx, 0Bh
0x18001001c  mov     r9d, eax
0x18001001f  call    WPP_SF_d
0x180010024  mov     rcx, cs:WPP_GLOBAL_Control
0x18001002b  cmp     rcx, r15
0x18001002e  jz      loc_180010179
0x180010034  test    [rcx+1Ch], r14d
0x180010038  jz      loc_180010179
0x18001003e  cmp     byte ptr [rcx+19h], 2
0x180010042  jb      loc_180010179
0x180010048  mov     edx, 0Fh
0x18001004d  mov     r9d, ebx
0x180010050  jmp     loc_18000FF26
0x180010055  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001005c  mov     ecx, 248h; unsigned __int64
0x180010061  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010066  mov     rdx, rax
0x180010069  test    rax, rax
0x18001006c  jz      short loc_1800100B6
0x18001006e  mov     rcx, [rsi]
0x180010071  mov     [rax+8], rcx
0x180010075  mov     dword ptr [rax+10h], 11F9h
0x18001007c  mov     dword ptr [rax+18h], 122Dh
0x180010083  lea     rax, ??_7CConfigAdvancedPage@@6B@; const CConfigAdvancedPage::`vftable'
0x18001008a  mov     [rdx], rax
0x18001008d  mov     qword ptr [rdx+20h], 0
0x180010095  mov     dword ptr [rdx+230h], 0
0x18001009f  mov     qword ptr [rdx+238h], 0
0x1800100aa  mov     dword ptr [rdx+240h], 0
0x1800100b4  jmp     short loc_1800100B8
0x1800100b6  xor     edx, edx
0x1800100b8  mov     rax, [rdi+20h]
0x1800100bc  mov     [rax+10h], rdx
0x1800100c0  mov     rax, [rdi+20h]
0x1800100c4  mov     rcx, [rax+10h]; this
0x1800100c8  test    rcx, rcx
0x1800100cb  jnz     short loc_1800100FB
0x1800100cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100d4  cmp     rcx, r15
0x1800100d7  jz      loc_18000FE22
0x1800100dd  test    [rcx+1Ch], r14d
0x1800100e1  jz      loc_18000FE22
0x1800100e7  cmp     byte ptr [rcx+19h], 2
0x1800100eb  jb      loc_18000FE22
0x1800100f1  mov     edx, 10h
0x1800100f6  jmp     loc_18000FE16
0x1800100fb  mov     rdx, [rdi+38h]; void *
0x1800100ff  call    ?Init@CConfigAdvancedPage@@QEAAKPEAX@Z; CConfigAdvancedPage::Init(void *)
0x180010104  mov     ebx, eax
0x180010106  test    eax, eax
0x180010108  jz      short loc_18001012C
0x18001010a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010111  cmp     rcx, r15
0x180010114  jz      short loc_180010179
0x180010116  test    [rcx+1Ch], r14d
0x18001011a  jz      short loc_180010179
0x18001011c  cmp     byte ptr [rcx+19h], 2
0x180010120  jb      short loc_180010179
0x180010122  mov     edx, 11h
0x180010127  jmp     loc_18000FF23
0x18001012c  mov     rdx, [rsi]; HINSTANCE
0x18001012f  mov     rcx, [rdi+38h]; void *
0x180010133  call    ?CreateFaxSecurityPage@@YAPEAU_PSP@@PEAXPEAUHINSTANCE__@@@Z; CreateFaxSecurityPage(void *,HINSTANCE__ *)
0x180010138  mov     [rdi+28h], rax
0x18001013c  test    rax, rax
0x18001013f  jnz     short loc_180010181
0x180010141  call    cs:__imp_GetLastError
0x180010147  mov     ebx, eax
0x180010149  mov     rcx, cs:WPP_GLOBAL_Control
0x180010150  cmp     rcx, r15
0x180010153  jz      short loc_180010175
0x180010155  test    [rcx+1Ch], r14d
0x180010159  jz      short loc_180010175
0x18001015b  cmp     byte ptr [rcx+19h], 2
0x18001015f  jb      short loc_180010175
0x180010161  mov     rcx, [rcx+10h]
0x180010165  mov     edx, 12h
0x18001016a  mov     r9d, eax
0x18001016d  mov     r8, r12
0x180010170  call    WPP_SF_d
0x180010175  test    ebx, ebx
0x180010177  jz      short loc_180010181
0x180010179  mov     rcx, rdi; this
0x18001017c  call    ?CleanUp@CFaxConfigUI@@AEAAXXZ; CFaxConfigUI::CleanUp(void)
0x180010181  mov     eax, ebx
0x180010183  add     rsp, 28h
0x180010187  pop     r15
0x180010189  pop     r14
0x18001018b  pop     r12
0x18001018d  pop     rdi
0x18001018e  pop     rsi
0x18001018f  pop     rbx
0x180010190  retn
```
