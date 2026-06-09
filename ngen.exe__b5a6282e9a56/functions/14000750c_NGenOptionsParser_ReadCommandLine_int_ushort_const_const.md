# NGenOptionsParser::ReadCommandLine(int,ushort const * * const)

- ea: `0x14000750c`
- end: `0x14000793b`
- name: `?ReadCommandLine@NGenOptionsParser@@QEAAJHQEAPEBG@Z`
- size: `1071`
- prototype: `__int64 __fastcall(NGenOptionsParser *__hidden this, int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140009104`

## callees

- `0x140006e3c`
- `0x140006fb8`
- `0x140007388`
- `0x14000750c`
- `0x14000a05c`
- `0x14000a10c`
- `0x140013f04`

## import_xrefs

- `ucrtbase_clr0400!_wcsnicmp` at `0x1400076b3`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1400076f4`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140007715`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140007739`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1400076b3`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1400076f4`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140007715`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140007739`
- `ucrtbase_clr0400!tolower` at `0x1400075e2`
- `ucrtbase_clr0400!tolower` at `0x1400075e2`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007638`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007659`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007676`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007693`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007783`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400077a0`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400077e3`
- `ucrtbase_clr0400!_wcsicmp` at `0x14000781e`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007838`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007852`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400078a1`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007638`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007659`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007676`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007693`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007783`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400077a0`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400077e3`
- `ucrtbase_clr0400!_wcsicmp` at `0x14000781e`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007838`
- `ucrtbase_clr0400!_wcsicmp` at `0x140007852`
- `ucrtbase_clr0400!_wcsicmp` at `0x1400078a1`

## string_xrefs

- `0x140007848`: `delete`
- `0x140007802`: `WARNING: Use "ngen install /Tuning" instead of "ngen /instrument"\n`
- `0x140007887`: `\nError: You must specify an assembly to install.\n`
- `0x1400078e0`: `\nError: You must specify an assembly to uninstall.\n`

## pseudocode

```c
__int64 __fastcall NGenOptionsParser::ReadCommandLine(
        NGenOptionsParser *this,
        int a2,
        const unsigned __int16 **const a3)
{
  int v4; // r14d
  unsigned int v6; // ebp
  _WORD *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  void *v11; // rax
  void *v12; // rsi
  const wchar_t *v13; // rdi
  int v14; // eax
  _WORD *v15; // rdi
  bool i; // zf
  const wchar_t *v17; // rdi
  const char *v19; // rdi
  const wchar_t *v20; // rdx
  char v21; // cl

  v4 = a2;
  v6 = 0;
  if ( !a2 )
    return 1;
  if ( a2 <= 0 )
  {
LABEL_61:
    v19 = 0;
    if ( !*((_QWORD *)this + 1) )
    {
      if ( !*((_BYTE *)this + 24) )
      {
        if ( !*((_BYTE *)this + 32) )
        {
          v19 = "\nError: You must specify an assembly to install.\n";
LABEL_72:
          v6 = -2147467259;
          goto LABEL_73;
        }
LABEL_71:
        v19 = "\nError: You must specify an assembly to uninstall.\n";
        goto LABEL_72;
      }
      if ( *((_BYTE *)this + 32) )
        goto LABEL_71;
    }
LABEL_73:
    v21 = *((_BYTE *)this + 26);
    if ( v21 && *((_BYTE *)this + 27) )
    {
      v19 = "\nError: Cannot specify both /debug and /debugopt.\n";
      v6 = -2147467259;
    }
    if ( *((_BYTE *)this + 28) && v21 )
    {
      v19 = "\nWarning: /debug will be ignored if /prof is specified.\n";
    }
    else if ( !v19 )
    {
      return v6;
    }
    if ( *((_BYTE *)this + 25) )
    {
      if ( !*((_BYTE *)this + 30) )
      {
        PrintLogoHelper();
        *((_BYTE *)this + 25) = 0;
      }
    }
    Output(v19);
    return v6;
  }
  while ( 1 )
  {
    v7 = *a3;
    --v4;
    ++a3;
    if ( ((*v7 - 45) & 0xFFFD) != 0 )
    {
      v8 = *((_QWORD *)this + 1);
      v9 = *((_QWORD *)this + 2);
      if ( v8 == v9 )
      {
        i = v8 == 0;
        v10 = 5;
        if ( !i )
          v10 = 2 * v9;
        *((_QWORD *)this + 2) = v10;
        v11 = operator new(saturated_mul(v10, 8u));
        v12 = v11;
        if ( !v11 )
          return 2147942414LL;
        memcpy_0(v11, *(const void **)this, 8LL * *((_QWORD *)this + 1));
        operator delete(*(void **)this);
        v8 = *((_QWORD *)this + 1);
        *(_QWORD *)this = v12;
      }
      *(_QWORD *)(*(_QWORD *)this + 8 * v8) = v7;
      ++*((_QWORD *)this + 1);
      goto LABEL_60;
    }
    v13 = v7 + 1;
    v14 = tolower(*v13);
    if ( v14 == 63 )
      break;
    switch ( v14 )
    {
      case 'd':
        if ( _wcsicmp(v13, L"debug") )
        {
          if ( _wcsicmp(v13, L"debugopt") )
          {
            if ( _wcsicmp(v13, L"delete") )
              goto LABEL_45;
            *((_BYTE *)this + 32) = 1;
          }
          else
          {
            *((_BYTE *)this + 27) = 1;
          }
        }
        else
        {
          *((_BYTE *)this + 26) = 1;
        }
        break;
      case 'h':
        v20 = L"help";
        goto LABEL_67;
      case 'i':
        if ( _wcsicmp(v13, L"instrument") )
          goto LABEL_45;
        if ( *((_BYTE *)this + 25) && !*((_BYTE *)this + 30) )
        {
          PrintLogoHelper();
          *((_BYTE *)this + 25) = 0;
        }
        Output("WARNING: Use \"ngen install /Tuning\" instead of \"ngen /instrument\"\n");
        *((_BYTE *)this + 29) = 1;
        break;
      case 'n':
        if ( _wcsicmp(v13, L"nologo") )
          goto LABEL_45;
        goto LABEL_41;
      case 'p':
        if ( _wcsicmp(v13, L"prof") )
          goto LABEL_45;
        *((_BYTE *)this + 28) = 1;
        break;
      case 's':
        if ( _wcsicmp(v13, L"show") )
        {
          if ( _wcsicmp(v13, L"silent") )
          {
            if ( _wcsicmp(v13, L"showversion") )
            {
              if ( _wcsnicmp(v13, L"stats", 5u) )
                goto LABEL_45;
              v15 = v13 + 5;
              *((_DWORD *)this + 9) = 1;
              if ( *v15 )
              {
                for ( i = *v15 == 58; i; i = *v15 == 44 )
                {
                  v17 = v15 + 1;
                  if ( _wcsnicmp(v17, L"fixups", 6u) )
                  {
                    if ( _wcsnicmp(v17, L"calls", 5u) )
                    {
                      if ( _wcsnicmp(v17, L"attributed", 0xAu) )
                        goto LABEL_45;
                      v15 = v17 + 10;
                      *((_DWORD *)this + 9) |= 8u;
                    }
                    else
                    {
                      v15 = v17 + 5;
                      *((_DWORD *)this + 9) |= 4u;
                    }
                  }
                  else
                  {
                    v15 = v17 + 6;
                    *((_DWORD *)this + 9) |= 2u;
                  }
                  if ( !*v15 )
                    goto LABEL_38;
                }
                goto LABEL_45;
              }
LABEL_38:
              if ( *((_BYTE *)this + 25) && !*((_BYTE *)this + 30) )
              {
                PrintLogoHelper();
LABEL_41:
                *((_BYTE *)this + 25) = 0;
              }
            }
            else
            {
              *((_BYTE *)this + 31) = 1;
            }
          }
          else
          {
            *((_BYTE *)this + 30) = 1;
          }
        }
        else
        {
          *((_BYTE *)this + 24) = 1;
        }
        break;
      default:
        if ( v14 != 118 || _wcsicmp(v13, L"verbose") )
          goto LABEL_45;
        *((_BYTE *)this + 33) = 1;
        break;
    }
LABEL_60:
    if ( v4 <= 0 )
      goto LABEL_61;
  }
  v20 = L"?";
LABEL_67:
  if ( !_wcsicmp(v13, v20) )
    return 1;
LABEL_45:
  if ( *((_BYTE *)this + 25) && !*((_BYTE *)this + 30) )
  {
    PrintLogoHelper();
    *((_BYTE *)this + 25) = 0;
  }
  Outputf(L"\nError: Unrecognized option %s\n", *(a3 - 1));
  return 2147500037LL;
}

```

## disassembly

```asm
0x14000750c  mov     [rsp+arg_0], rbx
0x140007511  mov     [rsp+arg_8], rbp
0x140007516  mov     [rsp+arg_10], rsi
0x14000751b  push    rdi
0x14000751c  push    r12
0x14000751e  push    r13
0x140007520  push    r14
0x140007522  push    r15
0x140007524  sub     rsp, 20h
0x140007528  xor     r12d, r12d
0x14000752b  mov     r15, r8
0x14000752e  mov     r14d, edx
0x140007531  mov     rbx, rcx
0x140007534  mov     ebp, r12d
0x140007537  test    edx, edx
0x140007539  jz      loc_1400078AF
0x14000753f  jle     loc_14000786D
0x140007545  lea     r13d, [r12+5]
0x14000754a  mov     rdi, [r15]
0x14000754d  dec     r14d
0x140007550  mov     ecx, 0FFFDh
0x140007555  lea     r15, [r15+8]
0x140007559  movzx   eax, word ptr [rdi]
0x14000755c  sub     ax, 2Dh ; '-'
0x140007560  test    cx, ax
0x140007563  jz      short loc_1400075DB
0x140007565  mov     rcx, [rbx+8]
0x140007569  mov     rax, [rbx+10h]
0x14000756d  cmp     rcx, rax
0x140007570  jnz     short loc_1400075CB
0x140007572  test    rcx, rcx
0x140007575  mov     rcx, r13
0x140007578  jz      short loc_14000757E
0x14000757a  lea     rcx, [rax+rax]
0x14000757e  mov     [rbx+10h], rcx
0x140007582  mov     eax, 8
0x140007587  mul     rcx
0x14000758a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140007591  cmovo   rax, rcx
0x140007595  mov     rcx, rax; dwBytes
0x140007598  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000759d  mov     rsi, rax
0x1400075a0  test    rax, rax
0x1400075a3  jz      loc_140007890
0x1400075a9  mov     r8, [rbx+8]
0x1400075ad  mov     rcx, rax; void *
0x1400075b0  mov     rdx, [rbx]; Src
0x1400075b3  shl     r8, 3; Size
0x1400075b7  call    memcpy_0
0x1400075bc  mov     rcx, [rbx]; lpMem
0x1400075bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400075c4  mov     rcx, [rbx+8]
0x1400075c8  mov     [rbx], rsi
0x1400075cb  mov     rax, [rbx]
0x1400075ce  mov     [rax+rcx*8], rdi
0x1400075d2  inc     qword ptr [rbx+8]
0x1400075d6  jmp     loc_140007864
0x1400075db  add     rdi, 2
0x1400075df  movzx   ecx, word ptr [rdi]; C
0x1400075e2  call    cs:__imp_tolower
0x1400075e8  mov     edx, eax
0x1400075ea  sub     edx, 3Fh ; '?'
0x1400075ed  jz      loc_1400078D1
0x1400075f3  sub     edx, 25h ; '%'
0x1400075f6  jz      loc_140007814
0x1400075fc  sub     edx, 4
0x1400075ff  jz      loc_140007897
0x140007605  sub     edx, 1
0x140007608  jz      loc_1400077D9
0x14000760e  sub     edx, r13d
0x140007611  jz      loc_140007796
0x140007617  sub     edx, 2
0x14000761a  jz      loc_140007779
0x140007620  sub     edx, 3
0x140007623  jz      short loc_14000764F
0x140007625  cmp     edx, 3
0x140007628  jnz     loc_1400077AA
0x14000762e  lea     rdx, aVerbose_1; "verbose"
0x140007635  mov     rcx, rdi; String1
0x140007638  call    cs:__imp__wcsicmp
0x14000763e  test    eax, eax
0x140007640  jnz     loc_1400077AA
0x140007646  mov     byte ptr [rbx+21h], 1
0x14000764a  jmp     loc_140007864
0x14000764f  lea     rdx, aShow; "show"
0x140007656  mov     rcx, rdi; String1
0x140007659  call    cs:__imp__wcsicmp
0x14000765f  test    eax, eax
0x140007661  jnz     short loc_14000766C
0x140007663  mov     byte ptr [rbx+18h], 1
0x140007667  jmp     loc_140007864
0x14000766c  lea     rdx, aSilent_0; "silent"
0x140007673  mov     rcx, rdi; String1
0x140007676  call    cs:__imp__wcsicmp
0x14000767c  test    eax, eax
0x14000767e  jnz     short loc_140007689
0x140007680  mov     byte ptr [rbx+1Eh], 1
0x140007684  jmp     loc_140007864
0x140007689  lea     rdx, aShowversion; "showversion"
0x140007690  mov     rcx, rdi; String1
0x140007693  call    cs:__imp__wcsicmp
0x140007699  test    eax, eax
0x14000769b  jnz     short loc_1400076A6
0x14000769d  mov     byte ptr [rbx+1Fh], 1
0x1400076a1  jmp     loc_140007864
0x1400076a6  mov     r8, r13; MaxCount
0x1400076a9  lea     rdx, aStats_0; "stats"
0x1400076b0  mov     rcx, rdi; String1
0x1400076b3  call    cs:__imp__wcsnicmp
0x1400076b9  test    eax, eax
0x1400076bb  jnz     loc_1400077AA
0x1400076c1  add     rdi, 0Ah
0x1400076c5  mov     dword ptr [rbx+24h], 1
0x1400076cc  cmp     [rdi], r12w
0x1400076d0  jz      loc_140007757
0x1400076d6  cmp     word ptr [rdi], 3Ah ; ':'
0x1400076da  jnz     loc_1400077AA
0x1400076e0  add     rdi, 2
0x1400076e4  lea     rdx, aFixups; "fixups"
0x1400076eb  mov     rcx, rdi; String1
0x1400076ee  mov     r8d, 6; MaxCount
0x1400076f4  call    cs:__imp__wcsnicmp
0x1400076fa  test    eax, eax
0x1400076fc  jnz     short loc_140007708
0x1400076fe  add     rdi, 0Ch
0x140007702  or      dword ptr [rbx+24h], 2
0x140007706  jmp     short loc_14000774B
0x140007708  mov     r8, r13; MaxCount
0x14000770b  lea     rdx, aCalls; "calls"
0x140007712  mov     rcx, rdi; String1
0x140007715  call    cs:__imp__wcsnicmp
0x14000771b  test    eax, eax
0x14000771d  jnz     short loc_140007729
0x14000771f  add     rdi, 0Ah
0x140007723  or      dword ptr [rbx+24h], 4
0x140007727  jmp     short loc_14000774B
0x140007729  mov     r8d, 0Ah; MaxCount
0x14000772f  lea     rdx, aAttributed; "attributed"
0x140007736  mov     rcx, rdi; String1
0x140007739  call    cs:__imp__wcsnicmp
0x14000773f  test    eax, eax
0x140007741  jnz     short loc_1400077AA
0x140007743  add     rdi, 14h
0x140007747  or      dword ptr [rbx+24h], 8
0x14000774b  cmp     [rdi], r12w
0x14000774f  jz      short loc_140007757
0x140007751  cmp     word ptr [rdi], 2Ch ; ','
0x140007755  jmp     short loc_1400076DA
0x140007757  cmp     [rbx+19h], r12b
0x14000775b  jz      loc_140007864
0x140007761  cmp     [rbx+1Eh], r12b
0x140007765  jnz     loc_140007864
0x14000776b  call    ?PrintLogoHelper@@YAXXZ; PrintLogoHelper(void)
0x140007770  mov     [rbx+19h], r12b
0x140007774  jmp     loc_140007864
0x140007779  lea     rdx, aProf; "prof"
0x140007780  mov     rcx, rdi; String1
0x140007783  call    cs:__imp__wcsicmp
0x140007789  test    eax, eax
0x14000778b  jnz     short loc_1400077AA
0x14000778d  mov     byte ptr [rbx+1Ch], 1
0x140007791  jmp     loc_140007864
0x140007796  lea     rdx, aNologo_0; "nologo"
0x14000779d  mov     rcx, rdi; String1
0x1400077a0  call    cs:__imp__wcsicmp
0x1400077a6  test    eax, eax
0x1400077a8  jz      short loc_140007770
0x1400077aa  cmp     [rbx+19h], r12b
0x1400077ae  jz      short loc_1400077BF
0x1400077b0  cmp     [rbx+1Eh], r12b
0x1400077b4  jnz     short loc_1400077BF
0x1400077b6  call    ?PrintLogoHelper@@YAXXZ; PrintLogoHelper(void)
0x1400077bb  mov     [rbx+19h], r12b
0x1400077bf  mov     rdx, [r15-8]
0x1400077c3  lea     rcx, aErrorUnrecogni_0; "\nError: Unrecognized option %s\n"
0x1400077ca  call    ?Outputf@@YAXPEAGZZ; Outputf(ushort *,...)
0x1400077cf  mov     eax, 80004005h
0x1400077d4  jmp     loc_1400078B4
0x1400077d9  lea     rdx, aInstrument; "instrument"
0x1400077e0  mov     rcx, rdi; String1
0x1400077e3  call    cs:__imp__wcsicmp
0x1400077e9  test    eax, eax
0x1400077eb  jnz     short loc_1400077AA
0x1400077ed  cmp     [rbx+19h], r12b
0x1400077f1  jz      short loc_140007802
0x1400077f3  cmp     [rbx+1Eh], r12b
0x1400077f7  jnz     short loc_140007802
0x1400077f9  call    ?PrintLogoHelper@@YAXXZ; PrintLogoHelper(void)
0x1400077fe  mov     [rbx+19h], r12b
0x140007802  lea     rcx, aWarningUseNgen; "WARNING: Use \"ngen install /Tuning\" i"...
0x140007809  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x14000780e  mov     byte ptr [rbx+1Dh], 1
0x140007812  jmp     short loc_140007864
0x140007814  lea     rdx, aDebug_0; "debug"
0x14000781b  mov     rcx, rdi; String1
0x14000781e  call    cs:__imp__wcsicmp
0x140007824  test    eax, eax
0x140007826  jnz     short loc_14000782E
0x140007828  mov     byte ptr [rbx+1Ah], 1
0x14000782c  jmp     short loc_140007864
0x14000782e  lea     rdx, aDebugopt; "debugopt"
0x140007835  mov     rcx, rdi; String1
0x140007838  call    cs:__imp__wcsicmp
0x14000783e  test    eax, eax
0x140007840  jnz     short loc_140007848
0x140007842  mov     byte ptr [rbx+1Bh], 1
0x140007846  jmp     short loc_140007864
0x140007848  lea     rdx, aDelete; "delete"
0x14000784f  mov     rcx, rdi; String1
0x140007852  call    cs:__imp__wcsicmp
0x140007858  test    eax, eax
0x14000785a  jnz     loc_1400077AA
0x140007860  mov     byte ptr [rbx+20h], 1
0x140007864  test    r14d, r14d
0x140007867  jg      loc_14000754A
0x14000786d  mov     rdi, r12
0x140007870  mov     eax, 80004005h
0x140007875  cmp     [rbx+8], r12
0x140007879  jnz     short loc_1400078E9
0x14000787b  cmp     [rbx+18h], r12b
0x14000787f  jnz     short loc_1400078DA
0x140007881  cmp     [rbx+20h], r12b
0x140007885  jnz     short loc_1400078E0
0x140007887  lea     rdi, aErrorYouMustSp_1; "\nError: You must specify an assembly t"...
0x14000788e  jmp     short loc_1400078E7
0x140007890  mov     eax, 8007000Eh
0x140007895  jmp     short loc_1400078B4
0x140007897  lea     rdx, aHelp; "help"
0x14000789e  mov     rcx, rdi; String1
0x1400078a1  call    cs:__imp__wcsicmp
0x1400078a7  test    eax, eax
0x1400078a9  jnz     loc_1400077AA
0x1400078af  mov     eax, 1
0x1400078b4  mov     rbx, [rsp+48h+arg_0]
0x1400078b9  mov     rbp, [rsp+48h+arg_8]
0x1400078be  mov     rsi, [rsp+48h+arg_10]
0x1400078c3  add     rsp, 20h
0x1400078c7  pop     r15
0x1400078c9  pop     r14
0x1400078cb  pop     r13
0x1400078cd  pop     r12
0x1400078cf  pop     rdi
0x1400078d0  retn
0x1400078d1  lea     rdx, asc_140018C6C; "?"
0x1400078d8  jmp     short loc_14000789E
0x1400078da  cmp     [rbx+20h], r12b
0x1400078de  jz      short loc_1400078E9
0x1400078e0  lea     rdi, aErrorYouMustSp; "\nError: You must specify an assembly t"...
0x1400078e7  mov     ebp, eax
0x1400078e9  mov     cl, [rbx+1Ah]
0x1400078ec  test    cl, cl
0x1400078ee  jz      short loc_1400078FF
0x1400078f0  cmp     [rbx+1Bh], r12b
0x1400078f4  jz      short loc_1400078FF
0x1400078f6  lea     rdi, aErrorCannotSpe_1; "\nError: Cannot specify both /debug and"...
0x1400078fd  mov     ebp, eax
0x1400078ff  cmp     [rbx+1Ch], r12b
0x140007903  jz      short loc_140007912
0x140007905  test    cl, cl
0x140007907  jz      short loc_140007912
0x140007909  lea     rdi, aWarningDebugWi; "\nWarning: /debug will be ignored if /p"...
0x140007910  jmp     short loc_140007917
0x140007912  test    rdi, rdi
0x140007915  jz      short loc_140007934
0x140007917  cmp     [rbx+19h], r12b
0x14000791b  jz      short loc_14000792C
0x14000791d  cmp     [rbx+1Eh], r12b
0x140007921  jnz     short loc_14000792C
0x140007923  call    ?PrintLogoHelper@@YAXXZ; PrintLogoHelper(void)
0x140007928  mov     [rbx+19h], r12b
0x14000792c  mov     rcx, rdi; char *
0x14000792f  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140007934  mov     eax, ebp
0x140007936  jmp     loc_1400078B4
```
