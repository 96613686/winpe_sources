# XMLParser::Run(long)

- ea: `0x1800343d0`
- end: `0x180034af9`
- name: `?Run@XMLParser@@UEAAJJ@Z`
- size: `1833`
- prototype: `__int64 __fastcall(XMLParser *__hidden this, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x180033a24`
- `0x180033e44`
- `0x1800341fc`
- `0x1800343d0`
- `0x180034c54`
- `0x180034ea4`
- `0x180034f70`
- `0x180034fc8`
- `0x180035008`
- `0x18003510c`
- `0x18003522c`
- `0x180035c14`
- `0x180039310`
- `0x180039418`
- `0x180045020`

## pseudocode

```c
__int64 __fastcall XMLParser::Run(XMLParser *this, int a2)
{
  void *v2; // rbx
  __int64 v5; // rcx
  unsigned int v6; // r12d
  int NextToken; // esi
  char v9; // r14
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r9
  XMLStream *v14; // rcx
  char v15; // dl
  unsigned int v16; // ecx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r14
  __int64 v21; // r9
  XMLParser *v22; // rcx
  __int64 v23; // rax
  char v24; // r14
  int v25; // edx
  char v26; // r13
  char v27; // r15
  __int64 v28; // r8
  unsigned int v29[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v30[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v31; // [rsp+50h] [rbp-10h]
  char v32; // [rsp+A0h] [rbp+40h]
  unsigned int *v33; // [rsp+B0h] [rbp+50h] BYREF

  v2 = (void *)*((_QWORD *)this + 25);
  ClrEnterCriticalSection(v2);
  *(_OWORD *)v29 = 0;
  v33 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  if ( *((_BYTE *)this + 49) )
    *((_BYTE *)this + 49) = 0;
  v5 = *((_QWORD *)this + 24);
  if ( !v5 )
  {
    v6 = -2147467259;
LABEL_18:
    ClrLeaveCriticalSection(v2);
    return v6;
  }
  if ( *((_BYTE *)this + 50) )
  {
    v6 = -1072896687;
    goto LABEL_18;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v6 = *((_DWORD *)this + 8);
    if ( v6 )
      goto LABEL_18;
LABEL_17:
    v6 = 0;
    goto LABEL_18;
  }
  if ( *((_BYTE *)this + 64) || !a2 )
  {
    ClrLeaveCriticalSection(v2);
    return 2147483658LL;
  }
  *((_BYTE *)this + 64) = 1;
  v6 = *((_DWORD *)this + 8);
  if ( v6 )
  {
    XMLParser::StackCleanupImpl(this);
    *((_BYTE *)this + 64) = 0;
    goto LABEL_18;
  }
  NextToken = 0;
  if ( !*((_BYTE *)this + 51) )
  {
    *((_BYTE *)this + 51) = 1;
    NextToken = (*(__int64 (__fastcall **)(__int64, XMLParser *, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, this, 0);
    if ( *((_BYTE *)this + 50) )
    {
      *((_BYTE *)this + 64) = 0;
      goto LABEL_17;
    }
  }
  v9 = 0;
  v32 = 0;
  *((_BYTE *)this + 48) = 0;
  if ( *((_BYTE *)this + 68) )
  {
    v10 = *((_QWORD *)this + 24);
    v11 = *((_QWORD *)this + 19);
    *((_BYTE *)this + 68) = 0;
    NextToken = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64))(*(_QWORD *)v10 + 32LL))(v10, this, v11);
  }
  if ( *((_BYTE *)this + 69) )
  {
    v12 = *((_QWORD *)this + 24);
    v13 = *((_QWORD *)this + 19);
    *((_BYTE *)this + 69) = 0;
    NextToken = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64, __int64))(*(_QWORD *)v12 + 40LL))(
                  v12,
                  this,
                  1,
                  v13);
    if ( NextToken >= 0 )
      NextToken = XMLParser::pop(this);
  }
  *(_QWORD *)v29 = 48;
  v29[2] = 0;
  v31 = 0;
  v33 = v29;
  v30[0] = 0;
  v30[1] = 0;
  while ( 2 )
  {
    ++*((_DWORD *)this + 15);
    while ( !NextToken && !*((_BYTE *)this + 49) )
    {
      v14 = (XMLStream *)*((_QWORD *)this + 2);
      v29[2] = 0;
      NextToken = XMLStream::GetNextToken(
                    v14,
                    &v29[1],
                    (const unsigned __int16 **)v30,
                    (int *)&v30[1],
                    (int *)&v30[1] + 1);
      if ( NextToken == -2147483638 )
      {
        *((_BYTE *)this + 48) = 1;
        break;
      }
      v15 = *((_BYTE *)this + 67);
      v16 = v29[1];
      if ( !v15 )
      {
        if ( !v29[1] || v29[1] == 18 || v29[1] == 4 )
        {
          v15 = 0;
        }
        else
        {
          *((_BYTE *)this + 67) = 1;
          v15 = 1;
        }
      }
      if ( v16 > 0x1D )
      {
        switch ( v16 )
        {
          case 0x1Eu:
LABEL_104:
            if ( *((_BYTE *)this + 57) || *((_DWORD *)this + 22) != 1 )
            {
              if ( v16 != 30 || *((int *)this + 22) <= 1 )
                goto LABEL_56;
              NextToken = -1072896646;
            }
            else
            {
              NextToken = -1072896663;
            }
            break;
          case 0x3Au:
          case 0x3Bu:
          case 0x3Cu:
            v29[2] = v16;
            v29[1] = 13;
            if ( *((_WORD *)this + 80) )
            {
              v29[3] = 1;
              NextToken = XMLParser::pushAttributeValue(this, (struct _XML_NODE_INFO *)v29);
              if ( NextToken >= 0 )
              {
                v18 = XMLParser::CopyText(v22, *((struct XMLParser::_MY_XML_NODE_INFO **)this + 19));
                goto LABEL_114;
              }
            }
            else
            {
LABEL_99:
              v29[3] = 1;
              if ( *((_WORD *)this + 80) )
              {
                v18 = XMLParser::pushAttributeValue(this, (struct _XML_NODE_INFO *)v29);
                goto LABEL_114;
              }
              NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, unsigned int **))(**((_QWORD **)this + 24) + 56LL))(
                            *((_QWORD *)this + 24),
                            this,
                            *((_QWORD *)this + 23),
                            1,
                            &v33);
              *(_QWORD *)&v31 = 0;
            }
            break;
          case 0x3Du:
            v21 = *((unsigned __int16 *)this + 80);
            if ( (_WORD)v21 )
              XMLParser::popAttributes(this);
            LOWORD(v21) = v21 + 1;
            NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, __int64))(**((_QWORD **)this + 24)
                                                                                                 + 56LL))(
                          *((_QWORD *)this + 24),
                          this,
                          *((_QWORD *)this + 23),
                          v21,
                          *((_QWORD *)this + 21) + 8LL * *((int *)this + 36));
            *((_QWORD *)this + 23) = *(_QWORD *)(*((_QWORD *)this + 19) + 32LL);
            if ( NextToken >= 0 )
            {
              v18 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *))(**((_QWORD **)this + 24) + 32LL))(
                      *((_QWORD *)this + 24),
                      this);
              goto LABEL_114;
            }
            *((_BYTE *)this + 68) = 1;
            break;
          case 0x3Eu:
LABEL_83:
            v19 = *((unsigned __int16 *)this + 80);
            if ( (_WORD)v19 )
              XMLParser::popAttributes(this);
            LOWORD(v19) = v19 + 1;
            NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, __int64))(**((_QWORD **)this + 24)
                                                                                                 + 56LL))(
                          *((_QWORD *)this + 24),
                          this,
                          *((_QWORD *)this + 23),
                          v19,
                          *((_QWORD *)this + 21) + 8LL * *((int *)this + 36));
            if ( NextToken >= 0 )
            {
              NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, _QWORD))(**((_QWORD **)this + 24)
                                                                                          + 40LL))(
                            *((_QWORD *)this + 24),
                            this,
                            1,
                            *((_QWORD *)this + 19));
              if ( !NextToken )
              {
                v18 = XMLParser::pop(this);
                goto LABEL_114;
              }
            }
            else
            {
              *((_BYTE *)this + 69) = 1;
            }
            break;
          case 0x3Fu:
            if ( *((_DWORD *)this + 32) )
            {
              v20 = *((_QWORD *)this + 19);
              NextToken = XMLParser::pop(this, v30[0], (unsigned int)v30[1]);
              if ( !NextToken )
                NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64))(**((_QWORD **)this + 24)
                                                                                            + 40LL))(
                              *((_QWORD *)this + 24),
                              this,
                              0,
                              v20);
              v9 = v32;
            }
            else
            {
              NextToken = -1072896686;
            }
            break;
          case 0x41u:
            *((_BYTE *)this + 57) = 0;
            goto LABEL_83;
          case 0x46u:
            if ( *((_BYTE *)this + 66) )
            {
              v17 = *((_QWORD *)this + 13);
              if ( !*(_BYTE *)(v17 + 18) && !*(_BYTE *)(v17 + 17) )
              {
                v18 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 24) + 24LL))(
                        *((_QWORD *)this + 24),
                        this,
                        5);
                goto LABEL_114;
              }
            }
            break;
          default:
            goto LABEL_77;
        }
      }
      else
      {
        if ( v16 == 29 )
          goto LABEL_104;
        if ( v16 > 0xE )
        {
          if ( v16 == 16 )
            goto LABEL_99;
          if ( v16 != 17 )
          {
            if ( v16 == 18 )
              goto LABEL_99;
            if ( v16 != 28 )
              goto LABEL_77;
            *((_BYTE *)this + 57) = 1;
LABEL_56:
            v29[2] = v16;
            v16 = 2;
            v29[1] = 2;
LABEL_57:
            v9 = 1;
            v32 = 1;
            goto LABEL_58;
          }
          if ( *((_BYTE *)this + 66) )
            goto LABEL_112;
LABEL_66:
          if ( !*((_BYTE *)this + 66) )
            goto LABEL_99;
LABEL_112:
          NextToken = -1072896682;
        }
        else
        {
          if ( v16 == 14 )
            goto LABEL_66;
          if ( v16 )
          {
            switch ( v16 )
            {
              case 1u:
LABEL_58:
                if ( *((_BYTE *)this + 66) )
                {
                  if ( v16 != 1 )
                  {
                    if ( v16 - 3 > 2 )
                      goto LABEL_112;
                    goto LABEL_62;
                  }
                  if ( !*((_BYTE *)this + 65) )
                  {
                    *((_BYTE *)this + 65) = 1;
                    goto LABEL_62;
                  }
                  NextToken = -1072896683;
                }
                else
                {
LABEL_62:
                  v29[3] = 0;
                  if ( v9 )
                  {
                    NextToken = XMLParser::pushAttribute(this, (struct _XML_NODE_INFO *)v29);
                    if ( !NextToken )
                    {
                      v9 = 0;
                      v32 = 0;
                    }
                  }
                  else
                  {
                    v18 = XMLParser::push(this, (struct _XML_NODE_INFO *)v29);
LABEL_114:
                    NextToken = v18;
                  }
                }
                break;
              case 2u:
                goto LABEL_57;
              case 4u:
                if ( !v15 )
                  goto LABEL_58;
                NextToken = -1072896681;
                break;
              case 0xDu:
                goto LABEL_66;
              default:
LABEL_77:
                NextToken = -2147467259;
                break;
            }
          }
          else if ( NextToken == -1072896657 && *((_BYTE *)this + 232) )
          {
            NextToken = 0;
          }
        }
      }
    }
    --*((_DWORD *)this + 15);
    if ( NextToken != -1072896768 )
    {
LABEL_130:
      if ( !NextToken )
        goto LABEL_138;
      goto LABEL_131;
    }
    v23 = *((_QWORD *)this + 13);
    v24 = *(_BYTE *)(v23 + 18);
    if ( v24 )
    {
      v25 = *(_DWORD *)(v23 + 24);
      if ( v25 != *((_DWORD *)this + 32) )
      {
LABEL_129:
        NextToken = XMLParser::ReportUnclosedTags(this, v25);
        goto LABEL_130;
      }
    }
    v26 = *(_BYTE *)(v23 + 17);
    NextToken = 0;
    v27 = *(_BYTE *)(v23 + 19);
    if ( (unsigned int)XMLParser::PopDownload(this) )
    {
      if ( *((int *)this + 32) <= 0 )
      {
        if ( !*((_BYTE *)this + 65) )
        {
          NextToken = -1072896680;
          goto LABEL_132;
        }
LABEL_138:
        *((_DWORD *)this + 8) = NextToken;
        goto LABEL_139;
      }
      v25 = 0;
      goto LABEL_129;
    }
    if ( !v27 )
    {
      if ( v24 )
      {
        v28 = 7;
        goto LABEL_125;
      }
      if ( v26 )
      {
        v28 = 2;
LABEL_125:
        NextToken = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 24) + 24LL))(
                      *((_QWORD *)this + 24),
                      this,
                      v28);
        if ( NextToken < 0 )
        {
LABEL_131:
          if ( NextToken != -2147483638 )
          {
LABEL_132:
            *((_DWORD *)this + 8) = NextToken;
            XMLParser::StackCleanupImpl(this);
LABEL_139:
            *((_BYTE *)this + 64) = 0;
            ClrLeaveCriticalSection(v2);
            return (unsigned int)NextToken;
          }
          goto LABEL_138;
        }
      }
    }
    if ( *((int *)this + 15) <= 0 && !*((_BYTE *)this + 50) )
    {
      v9 = v32;
      continue;
    }
    break;
  }
  *((_BYTE *)this + 64) = 0;
  ClrLeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x1800343d0  mov     [rsp-38h+arg_8], rbx
0x1800343d5  push    rbp
0x1800343d6  push    rsi
0x1800343d7  push    rdi
0x1800343d8  push    r12
0x1800343da  push    r13
0x1800343dc  push    r14
0x1800343de  push    r15
0x1800343e0  mov     rbp, rsp
0x1800343e3  sub     rsp, 60h
0x1800343e7  mov     rbx, [rcx+0C8h]
0x1800343ee  mov     rdi, rcx
0x1800343f1  mov     rcx, rbx; void *
0x1800343f4  mov     esi, edx
0x1800343f6  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x1800343fb  xorps   xmm0, xmm0
0x1800343fe  xor     r15d, r15d
0x180034401  movups  xmmword ptr [rbp+var_30], xmm0
0x180034405  mov     [rbp+arg_10], r15
0x180034409  movups  xmmword ptr [rbp+var_20], xmm0
0x18003440d  movups  [rbp+var_10], xmm0
0x180034411  cmp     [rdi+31h], r15b
0x180034415  jz      short loc_18003441B
0x180034417  mov     [rdi+31h], r15b
0x18003441b  mov     rcx, [rdi+0C0h]
0x180034422  test    rcx, rcx
0x180034425  jnz     short loc_180034432
0x180034427  mov     r12d, 80004005h
0x18003442d  jmp     loc_1800344B2
0x180034432  cmp     [rdi+32h], r15b
0x180034436  jz      short loc_180034440
0x180034438  mov     r12d, 0C00CE551h
0x18003443e  jmp     short loc_1800344B2
0x180034440  cmp     [rdi+10h], r15
0x180034444  jnz     short loc_180034451
0x180034446  mov     r12d, [rdi+20h]
0x18003444a  test    r12d, r12d
0x18003444d  jnz     short loc_1800344B2
0x18003444f  jmp     short loc_1800344AF
0x180034451  cmp     [rdi+40h], r15b
0x180034455  jnz     loc_180034AD4
0x18003445b  test    esi, esi
0x18003445d  jz      loc_180034AD4
0x180034463  mov     r13d, 1
0x180034469  mov     [rdi+40h], r13b
0x18003446d  mov     r12d, [rdi+20h]
0x180034471  test    r12d, r12d
0x180034474  jz      short loc_180034484
0x180034476  mov     rcx, rdi; this
0x180034479  call    ?StackCleanupImpl@XMLParser@@AEAAXXZ; XMLParser::StackCleanupImpl(void)
0x18003447e  mov     [rdi+40h], r15b
0x180034482  jmp     short loc_1800344B2
0x180034484  mov     esi, r15d
0x180034487  cmp     [rdi+33h], r15b
0x18003448b  jnz     short loc_1800344C2
0x18003448d  mov     [rdi+33h], r13b
0x180034491  xor     r8d, r8d
0x180034494  mov     rax, [rcx]
0x180034497  mov     rdx, rdi
0x18003449a  mov     rax, [rax+18h]
0x18003449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a3  mov     esi, eax
0x1800344a5  cmp     [rdi+32h], r15b
0x1800344a9  jz      short loc_1800344C2
0x1800344ab  mov     [rdi+40h], r15b
0x1800344af  mov     r12d, r15d
0x1800344b2  mov     rcx, rbx; void *
0x1800344b5  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x1800344ba  mov     eax, r12d
0x1800344bd  jmp     loc_180034AE1
0x1800344c2  mov     r14b, r15b
0x1800344c5  mov     [rbp+arg_0], r15b
0x1800344c9  mov     [rdi+30h], r15b
0x1800344cd  cmp     [rdi+44h], r15b
0x1800344d1  jz      short loc_1800344F6
0x1800344d3  mov     rcx, [rdi+0C0h]
0x1800344da  mov     rdx, rdi
0x1800344dd  mov     r8, [rdi+98h]
0x1800344e4  mov     [rdi+44h], r15b
0x1800344e8  mov     rax, [rcx]
0x1800344eb  mov     rax, [rax+20h]
0x1800344ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344f4  mov     esi, eax
0x1800344f6  cmp     [rdi+45h], r15b
0x1800344fa  jz      short loc_180034530
0x1800344fc  mov     rcx, [rdi+0C0h]
0x180034503  mov     r8d, r13d
0x180034506  mov     r9, [rdi+98h]
0x18003450d  mov     rdx, rdi
0x180034510  mov     [rdi+45h], r15b
0x180034514  mov     rax, [rcx]
0x180034517  mov     rax, [rax+28h]
0x18003451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034520  mov     esi, eax
0x180034522  test    eax, eax
0x180034524  js      short loc_180034530
0x180034526  mov     rcx, rdi; this
0x180034529  call    ?pop@XMLParser@@AEAAJXZ; XMLParser::pop(void)
0x18003452e  mov     esi, eax
0x180034530  xorps   xmm0, xmm0
0x180034533  mov     qword ptr [rbp+var_30], 30h ; '0'
0x18003453b  lea     rax, [rbp+var_30]
0x18003453f  mov     [rbp+var_30+8], r15d
0x180034543  movdqu  [rbp+var_10], xmm0
0x180034548  mov     [rbp+arg_10], rax
0x18003454c  mov     r12d, 80004005h
0x180034552  mov     [rbp+var_20], r15
0x180034556  mov     [rbp+var_20+8], r15
0x18003455a  add     [rdi+3Ch], r13d
0x18003455e  jmp     short loc_180034564
0x180034560  mov     r14b, [rbp+arg_0]
0x180034564  test    esi, esi
0x180034566  jnz     loc_1800349CF
0x18003456c  cmp     [rdi+31h], r15b
0x180034570  jnz     loc_1800349CF
0x180034576  mov     rcx, [rdi+10h]; this
0x18003457a  lea     rax, [rbp+var_20+0Ch]
0x18003457e  lea     r9, [rbp+var_20+8]; int *
0x180034582  mov     [rsp+60h+var_40], rax; int *
0x180034587  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18003458b  mov     [rbp+var_30+8], r15d
0x18003458f  lea     rdx, [rbp+var_30+4]; unsigned int *
0x180034593  call    ?GetNextToken@XMLStream@@QEAAJPEAKPEAPEBGPEAJ2@Z; XMLStream::GetNextToken(ulong *,ushort const * *,long *,long *)
0x180034598  mov     esi, eax
0x18003459a  cmp     eax, 8000000Ah
0x18003459f  jz      loc_1800349CB
0x1800345a5  mov     dl, [rdi+43h]
0x1800345a8  mov     ecx, [rbp+var_30+4]
0x1800345ab  test    dl, dl
0x1800345ad  jnz     short loc_1800345C9
0x1800345af  test    ecx, ecx
0x1800345b1  jz      short loc_1800345C6
0x1800345b3  cmp     ecx, 12h
0x1800345b6  jz      short loc_1800345C6
0x1800345b8  cmp     ecx, 4
0x1800345bb  jz      short loc_1800345C6
0x1800345bd  mov     [rdi+43h], r13b
0x1800345c1  mov     dl, r13b
0x1800345c4  jmp     short loc_1800345C9
0x1800345c6  mov     dl, r15b
0x1800345c9  cmp     ecx, 1Dh
0x1800345cc  ja      loc_1800346D2
0x1800345d2  jz      loc_18003496C
0x1800345d8  cmp     ecx, 0Eh
0x1800345db  ja      short loc_180034635
0x1800345dd  jz      loc_1800346C3
0x1800345e3  mov     eax, ecx
0x1800345e5  test    ecx, ecx
0x1800345e7  jz      short loc_180034614
0x1800345e9  sub     eax, 1
0x1800345ec  jz      short loc_18003466D
0x1800345ee  sub     eax, 1
0x1800345f1  jz      short loc_180034666
0x1800345f3  sub     eax, 2
0x1800345f6  jz      short loc_180034606
0x1800345f8  cmp     eax, 9
0x1800345fb  jz      loc_1800346C3
0x180034601  jmp     loc_180034719
0x180034606  test    dl, dl
0x180034608  jz      short loc_18003466D
0x18003460a  mov     esi, 0C00CE557h
0x18003460f  jmp     loc_180034564
0x180034614  cmp     esi, 0C00CE56Fh
0x18003461a  jnz     loc_180034564
0x180034620  cmp     [rdi+0E8h], r15b
0x180034627  jz      loc_180034564
0x18003462d  mov     esi, r15d
0x180034630  jmp     loc_180034564
0x180034635  mov     eax, ecx
0x180034637  sub     eax, 10h
0x18003463a  jz      loc_1800348F1
0x180034640  sub     eax, 1
0x180034643  jz      short loc_1800346B9
0x180034645  sub     eax, 1
0x180034648  jz      loc_1800348F1
0x18003464e  cmp     eax, 0Ah
0x180034651  jnz     loc_180034719
0x180034657  mov     [rdi+39h], r13b
0x18003465b  mov     [rbp+var_30+8], ecx
0x18003465e  mov     ecx, 2
0x180034663  mov     [rbp+var_30+4], ecx
0x180034666  mov     r14b, r13b
0x180034669  mov     [rbp+arg_0], r13b
0x18003466d  cmp     [rdi+42h], r15b
0x180034671  jz      short loc_18003468A
0x180034673  cmp     ecx, r13d
0x180034676  jnz     loc_1800349A9
0x18003467c  cmp     [rdi+41h], r15b
0x180034680  jnz     loc_18003499F
0x180034686  mov     [rdi+41h], r13b
0x18003468a  mov     [rbp+var_30+0Ch], r15d
0x18003468e  lea     rdx, [rbp+var_30]; struct _XML_NODE_INFO *
0x180034692  mov     rcx, rdi; this
0x180034695  test    r14b, r14b
0x180034698  jz      loc_1800349BF
0x18003469e  call    ?pushAttribute@XMLParser@@AEAAJAEAU_XML_NODE_INFO@@@Z; XMLParser::pushAttribute(_XML_NODE_INFO &)
0x1800346a3  mov     esi, eax
0x1800346a5  test    eax, eax
0x1800346a7  jnz     loc_180034564
0x1800346ad  mov     r14b, r15b
0x1800346b0  mov     [rbp+arg_0], r15b
0x1800346b4  jmp     loc_180034564
0x1800346b9  cmp     [rdi+42h], r15b
0x1800346bd  jnz     loc_1800349B5
0x1800346c3  cmp     [rdi+42h], r15b
0x1800346c7  jz      loc_1800348F1
0x1800346cd  jmp     loc_1800349B5
0x1800346d2  mov     eax, ecx
0x1800346d4  sub     eax, 1Eh
0x1800346d7  jz      loc_18003496C
0x1800346dd  sub     eax, 1Ch
0x1800346e0  jz      loc_1800348DD
0x1800346e6  sub     eax, 1
0x1800346e9  jz      loc_1800348DD
0x1800346ef  sub     eax, 1
0x1800346f2  jz      loc_1800348DD
0x1800346f8  sub     eax, 1
0x1800346fb  jz      loc_180034853
0x180034701  sub     eax, 1
0x180034704  jz      short loc_180034768
0x180034706  sub     eax, 1
0x180034709  jz      loc_1800347C5
0x18003470f  sub     eax, 2
0x180034712  jz      short loc_180034764
0x180034714  cmp     eax, 5
0x180034717  jz      short loc_180034721
0x180034719  mov     esi, r12d
0x18003471c  jmp     loc_180034564
0x180034721  cmp     [rdi+42h], r15b
0x180034725  jz      loc_180034564
0x18003472b  mov     rax, [rdi+68h]
0x18003472f  cmp     [rax+12h], r15b
0x180034733  jnz     loc_180034564
0x180034739  cmp     [rax+11h], r15b
0x18003473d  jnz     loc_180034564
0x180034743  mov     rcx, [rdi+0C0h]
0x18003474a  mov     r8d, 5
0x180034750  mov     rdx, rdi
0x180034753  mov     rax, [rcx]
0x180034756  mov     rax, [rax+18h]
0x18003475a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003475f  jmp     loc_1800349C4
0x180034764  mov     [rdi+39h], r15b
0x180034768  movzx   r9d, word ptr [rdi+0A0h]
0x180034770  test    r9w, r9w
0x180034774  jz      short loc_18003477E
0x180034776  mov     rcx, rdi; this
0x180034779  call    ?popAttributes@XMLParser@@AEAAJXZ; XMLParser::popAttributes(void)
0x18003477e  movsxd  rdx, dword ptr [rdi+90h]
0x180034785  add     r9w, r13w
0x180034789  mov     rax, [rdi+0A8h]
0x180034790  mov     rcx, [rdi+0C0h]
0x180034797  lea     r8, [rax+rdx*8]
0x18003479b  mov     rdx, rdi
0x18003479e  mov     r10, [rcx]
0x1800347a1  mov     [rsp+60h+var_40], r8
0x1800347a6  mov     r8, [rdi+0B8h]
0x1800347ad  mov     rax, [r10+38h]
0x1800347b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347b6  mov     esi, eax
0x1800347b8  test    eax, eax
0x1800347ba  jns     short loc_18003481C
0x1800347bc  mov     [rdi+45h], r13b
0x1800347c0  jmp     loc_180034564
0x1800347c5  cmp     [rdi+80h], r15d
0x1800347cc  jnz     short loc_1800347D8
0x1800347ce  mov     esi, 0C00CE552h
0x1800347d3  jmp     loc_180034564
0x1800347d8  mov     r8d, dword ptr [rbp+var_20+8]; unsigned int
0x1800347dc  mov     rcx, rdi; this
0x1800347df  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x1800347e3  mov     r14, [rdi+98h]
0x1800347ea  call    ?pop@XMLParser@@AEAAJPEBGK@Z; XMLParser::pop(ushort const *,ulong)
0x1800347ef  mov     esi, eax
0x1800347f1  test    eax, eax
0x1800347f3  jnz     loc_180034560
0x1800347f9  mov     rcx, [rdi+0C0h]
0x180034800  mov     r9, r14
0x180034803  xor     r8d, r8d
0x180034806  mov     rdx, rdi
0x180034809  mov     rax, [rcx]
0x18003480c  mov     rax, [rax+28h]
0x180034810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034815  mov     esi, eax
0x180034817  jmp     loc_180034560
0x18003481c  mov     rcx, [rdi+0C0h]
0x180034823  mov     r8d, r13d
0x180034826  mov     r9, [rdi+98h]
0x18003482d  mov     rdx, rdi
0x180034830  mov     rax, [rcx]
0x180034833  mov     rax, [rax+28h]
0x180034837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003483c  mov     esi, eax
0x18003483e  test    eax, eax
0x180034840  jnz     loc_180034564
0x180034846  mov     rcx, rdi; this
0x180034849  call    ?pop@XMLParser@@AEAAJXZ; XMLParser::pop(void)
0x18003484e  jmp     loc_1800349C4
0x180034853  movzx   r9d, word ptr [rdi+0A0h]
0x18003485b  test    r9w, r9w
  ... truncated ...
```
