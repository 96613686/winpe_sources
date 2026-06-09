# ExtractAllLuts

- ea: `0x1800053d0`
- end: `0x18000582f`
- name: `ExtractAllLuts`
- size: `1119`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800029a4`

## callees

- `0x1800053d0`
- `0x180005838`
- `0x18000614c`
- `0x18001bb30`
- `0x180020828`
- `0x18003d040`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180005800`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180005800`

## pseudocode

```c
__int64 __fastcall ExtractAllLuts(_DWORD *a1, __int64 a2)
{
  char v3; // dl
  TAGTYPE v5; // ebx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // eax
  unsigned int All_MFT_Luts; // esi
  TAGTYPE v11; // r8d
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  TAGTYPE v14; // r12d
  unsigned int v15; // eax
  unsigned int All_TRC_Luts; // eax
  int v17; // r15d
  unsigned int Gray_Luts; // eax
  unsigned int v19; // eax
  TAGTYPE v20; // r8d
  signed int i; // edx
  __int64 v22; // rcx
  char *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  signed int v26; // r8d
  __int64 v27; // rcx
  char *v28; // rax
  _DWORD v30[2]; // [rsp+20h] [rbp-59h] BYREF
  int v31; // [rsp+28h] [rbp-51h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-49h] BYREF
  int *v33; // [rsp+40h] [rbp-39h]
  __int64 v34; // [rsp+48h] [rbp-31h]
  _WORD *v35; // [rsp+50h] [rbp-29h]
  int v36; // [rsp+58h] [rbp-21h]
  int v37; // [rsp+5Ch] [rbp-1Dh]
  __int64 v38; // [rsp+60h] [rbp-19h]
  __int64 v39; // [rsp+68h] [rbp-11h]
  _WORD v40[8]; // [rsp+70h] [rbp-9h] BYREF
  _WORD v41[8]; // [rsp+80h] [rbp+7h] BYREF

  *(_DWORD *)(a2 + 32) = 1;
  v3 = *(_BYTE *)(a2 + 53);
  v31 = 1;
  if ( v3 )
  {
    v5 = 1734438260;
    v31 = 0;
    goto LABEL_19;
  }
  v6 = *(_DWORD *)(a2 + 28);
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
LABEL_8:
      if ( *(_BYTE *)(a2 + 55) )
        v5 = 1886545201;
      else
        v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589745 : 1093812785;
      goto LABEL_19;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
        v5 = 0;
        goto LABEL_19;
      }
      goto LABEL_8;
    }
    if ( *(_BYTE *)(a2 + 55) )
      v5 = 1886545202;
    else
      v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589746 : 1093812786;
  }
  else if ( *(_BYTE *)(a2 + 55) )
  {
    v5 = 1886545200;
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589744 : 1093812784;
  }
  if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
    *(_DWORD *)(a2 + 32) = 2;
LABEL_19:
  v9 = *(_DWORD *)(a2 + 12);
  if ( v9 != 1835955314 )
  {
    if ( v9 == 1818848875 )
    {
      v5 = 1093812784;
      v20 = 1093812784;
      goto LABEL_63;
    }
    if ( v9 == 1633842036 )
    {
      v5 = 1093812784;
      v11 = 1093812784;
LABEL_66:
      All_MFT_Luts = ExtractAll_MFT_Luts(a1, a2, v11);
      if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
        *(_DWORD *)(a2 + 32) = 2;
      goto LABEL_68;
    }
    if ( v9 != 1886549106 )
    {
      if ( v9 != 1935896178 )
      {
        if ( v9 != 1936744803 )
          return 2011;
        v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589744 : 1093812784;
        v11 = v5;
        goto LABEL_66;
      }
      v12 = a2;
      v13 = a1;
      if ( *(_DWORD *)(a2 + 16) != 1196573017 )
      {
        All_MFT_Luts = ExtractAll_MFT_Luts(a1, a2, v5);
        if ( All_MFT_Luts )
        {
          v14 = v5;
          if ( !*(_DWORD *)(a2 + 28) )
            goto LABEL_34;
          v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589744 : 1093812784;
          v15 = ExtractAll_MFT_Luts(a1, a2, v5);
          All_MFT_Luts = v15;
          if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
            *(_DWORD *)(a2 + 32) = 2;
          if ( v15 )
          {
LABEL_34:
            if ( *(_DWORD *)(a2 + 16) != 1380401696 || *(_DWORD *)(a2 + 20) != 1482250784 )
              goto LABEL_38;
            v5 = 1918128707;
            All_TRC_Luts = ExtractAll_TRC_Luts(a1, a2);
            All_MFT_Luts = All_TRC_Luts;
            if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
              *(_DWORD *)(a2 + 32) = 1;
            if ( All_TRC_Luts )
            {
LABEL_38:
              if ( !*(_BYTE *)(a2 + 54) )
                goto LABEL_68;
              qmemcpy(v30, "1A2B2A2B", sizeof(v30));
              v17 = 0;
              while ( All_MFT_Luts )
              {
                v5 = v30[v17];
                if ( v5 != v14 )
                {
                  All_MFT_Luts = ExtractAll_MFT_Luts(a1, a2, v5);
                  if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
                    *(_DWORD *)(a2 + 32) = 2;
                }
                if ( (unsigned int)++v17 >= 2 )
                  goto LABEL_68;
              }
            }
          }
        }
        goto LABEL_69;
      }
      goto LABEL_46;
    }
    if ( *(_DWORD *)(a2 + 16) == 1196573017 )
    {
LABEL_49:
      v12 = a2;
      v13 = a1;
LABEL_46:
      v5 = 1800688195;
      Gray_Luts = Extract_Gray_Luts(v13, v12, 16776960, 0x4000000);
LABEL_47:
      All_MFT_Luts = Gray_Luts;
      goto LABEL_68;
    }
LABEL_62:
    v20 = v5;
LABEL_63:
    Gray_Luts = ExtractAll_MFT_Luts(a1, a2, v20);
    goto LABEL_47;
  }
  if ( *(_DWORD *)(a2 + 16) == 1196573017 )
    goto LABEL_49;
  if ( *(_DWORD *)(a2 + 16) != 1380401696 )
    goto LABEL_62;
  if ( v3 )
  {
    v5 = 1918128707;
    Gray_Luts = DoMakeGamutForMonitor(a1, a2, 16776960, 0x4000000);
    goto LABEL_47;
  }
  All_MFT_Luts = ExtractAll_MFT_Luts(a1, a2, v5);
  if ( All_MFT_Luts )
  {
    if ( !*(_DWORD *)(a2 + 28) )
      goto LABEL_81;
    v5 = *(_BYTE *)(a2 + 54) != 0 ? 1110589744 : 1093812784;
    v19 = ExtractAll_MFT_Luts(a1, a2, v5);
    All_MFT_Luts = v19;
    if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
      *(_DWORD *)(a2 + 32) = 2;
    if ( v19 )
    {
LABEL_81:
      if ( *(_DWORD *)(a2 + 20) == 1482250784 )
      {
        v5 = 1918128707;
        All_MFT_Luts = ExtractAll_TRC_Luts(a1, a2);
        if ( *(_DWORD *)(a2 + 8) >= 0x4000000u )
          *(_DWORD *)(a2 + 32) = 1;
      }
LABEL_68:
      if ( All_MFT_Luts )
        return All_MFT_Luts;
    }
  }
LABEL_69:
  v30[0] = v5;
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v22 = i;
    v23 = (char *)v30 - i + 3;
    v40[v22] = *v23;
  }
  v24 = -1;
  v40[4] = 0;
  v25 = -1;
  do
    ++v25;
  while ( v40[v25] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v25 + 2;
  UserData.Ptr = (ULONGLONG)v40;
  v33 = &v31;
  v26 = 0;
  v30[0] = *(_DWORD *)(a2 + 12);
  v34 = 4;
  do
  {
    v27 = v26;
    v28 = (char *)v30 - v26++ + 3;
    v41[v27] = *v28;
  }
  while ( (unsigned int)v26 < 4 );
  v41[4] = 0;
  do
    ++v24;
  while ( v41[v24] );
  v37 = 0;
  v36 = 2 * v24 + 2;
  v35 = v41;
  v38 = a2 + 28;
  v39 = 4;
  EventWrite(g_etwHandle, &SELECT_TAG, 4u, &UserData);
  return All_MFT_Luts;
}

```

## disassembly

```asm
0x1800053d0  mov     [rsp-8+arg_10], rbx
0x1800053d5  push    rbp
0x1800053d6  push    rsi
0x1800053d7  push    rdi
0x1800053d8  push    r12
0x1800053da  push    r13
0x1800053dc  push    r14
0x1800053de  push    r15
0x1800053e0  lea     rbp, [rsp-27h]
0x1800053e5  sub     rsp, 0A0h
0x1800053ec  mov     rax, cs:__security_cookie
0x1800053f3  xor     rax, rsp
0x1800053f6  mov     [rbp+57h+var_40], rax
0x1800053fa  mov     eax, 1
0x1800053ff  mov     rdi, rdx
0x180005402  mov     [rdx+20h], eax
0x180005405  xor     r13d, r13d
0x180005408  mov     dl, [rdx+35h]
0x18000540b  mov     r14, rcx
0x18000540e  mov     [rbp+57h+var_A8], eax
0x180005411  mov     r8d, 0FFFF00h
0x180005417  lea     r15d, [rax+1]
0x18000541b  mov     r9d, 4000000h
0x180005421  mov     r12d, 41324230h
0x180005427  test    dl, dl
0x180005429  jz      short loc_180005436
0x18000542b  mov     ebx, 67616D74h
0x180005430  mov     [rbp+57h+var_A8], r13d
0x180005434  jmp     short loc_1800054B0
0x180005436  mov     ecx, [rdi+1Ch]
0x180005439  test    ecx, ecx
0x18000543b  jz      short loc_18000548C
0x18000543d  sub     ecx, eax
0x18000543f  jz      short loc_18000544E
0x180005441  sub     ecx, eax
0x180005443  jz      short loc_18000545B
0x180005445  cmp     ecx, eax
0x180005447  jz      short loc_18000544E
0x180005449  mov     ebx, r13d
0x18000544c  jmp     short loc_1800054B0
0x18000544e  cmp     [rdi+37h], r13b
0x180005452  jz      short loc_18000547A
0x180005454  mov     ebx, 70726531h
0x180005459  jmp     short loc_1800054B0
0x18000545b  cmp     [rdi+37h], r13b
0x18000545f  jz      short loc_180005468
0x180005461  mov     ebx, 70726532h
0x180005466  jmp     short loc_1800054A6
0x180005468  mov     al, [rdi+36h]
0x18000546b  neg     al
0x18000546d  sbb     ebx, ebx
0x18000546f  and     ebx, r8d
0x180005472  add     ebx, 41324232h
0x180005478  jmp     short loc_1800054A6
0x18000547a  mov     al, [rdi+36h]
0x18000547d  neg     al
0x18000547f  sbb     ebx, ebx
0x180005481  and     ebx, r8d
0x180005484  add     ebx, 41324231h
0x18000548a  jmp     short loc_1800054B0
0x18000548c  cmp     [rdi+37h], r13b
0x180005490  jz      short loc_180005499
0x180005492  mov     ebx, 70726530h
0x180005497  jmp     short loc_1800054A6
0x180005499  mov     al, [rdi+36h]
0x18000549c  neg     al
0x18000549e  sbb     ebx, ebx
0x1800054a0  and     ebx, r8d
0x1800054a3  add     ebx, r12d
0x1800054a6  cmp     [rdi+8], r9d
0x1800054aa  jb      short loc_1800054B0
0x1800054ac  mov     [rdi+20h], r15d
0x1800054b0  mov     eax, [rdi+0Ch]
0x1800054b3  cmp     eax, 6D6E7472h
0x1800054b8  jz      loc_18000563E
0x1800054be  cmp     eax, 6C696E6Bh
0x1800054c3  jz      loc_180005700
0x1800054c9  cmp     eax, 61627374h
0x1800054ce  jz      loc_180005708
0x1800054d4  cmp     eax, 70727472h
0x1800054d9  jz      loc_18000561C
0x1800054df  cmp     eax, 73636E72h
0x1800054e4  jz      short loc_18000550C
0x1800054e6  cmp     eax, 73706163h
0x1800054eb  jz      short loc_1800054F7
0x1800054ed  mov     esi, 7DBh
0x1800054f2  jmp     loc_180005806
0x1800054f7  mov     al, [rdi+36h]
0x1800054fa  neg     al
0x1800054fc  sbb     ebx, ebx
0x1800054fe  and     ebx, r8d
0x180005501  add     ebx, r12d
0x180005504  mov     r8d, ebx
0x180005507  jmp     loc_18000570E
0x18000550c  cmp     dword ptr [rdi+10h], 47524159h
0x180005513  mov     rdx, rdi
0x180005516  mov     rcx, r14
0x180005519  jz      loc_18000560B
0x18000551f  mov     r8d, ebx
0x180005522  call    ExtractAll_MFT_Luts
0x180005527  mov     esi, eax
0x180005529  test    eax, eax
0x18000552b  jz      loc_180005730
0x180005531  mov     r12d, ebx
0x180005534  cmp     [rdi+1Ch], r13d
0x180005538  jz      short loc_180005572
0x18000553a  mov     al, [rdi+36h]
0x18000553d  mov     rdx, rdi
0x180005540  neg     al
0x180005542  mov     rcx, r14
0x180005545  sbb     ebx, ebx
0x180005547  and     ebx, 0FFFF00h
0x18000554d  add     ebx, 41324230h
0x180005553  mov     r8d, ebx
0x180005556  call    ExtractAll_MFT_Luts
0x18000555b  cmp     dword ptr [rdi+8], 4000000h
0x180005562  mov     esi, eax
0x180005564  jb      short loc_18000556A
0x180005566  mov     [rdi+20h], r15d
0x18000556a  test    eax, eax
0x18000556c  jz      loc_180005730
0x180005572  cmp     dword ptr [rdi+10h], 52474220h
0x180005579  jnz     short loc_1800055AE
0x18000557b  cmp     dword ptr [rdi+14h], 58595A20h
0x180005582  jnz     short loc_1800055AE
0x180005584  mov     rdx, rdi
0x180005587  mov     rcx, r14
0x18000558a  mov     ebx, 72545243h
0x18000558f  call    ExtractAll_TRC_Luts
0x180005594  cmp     dword ptr [rdi+8], 4000000h
0x18000559b  mov     esi, eax
0x18000559d  jb      short loc_1800055A6
0x18000559f  mov     dword ptr [rdi+20h], 1
0x1800055a6  test    eax, eax
0x1800055a8  jz      loc_180005730
0x1800055ae  cmp     [rdi+36h], r13b
0x1800055b2  jz      loc_180005728
0x1800055b8  mov     [rbp+57h+var_B0], 42324131h
0x1800055bf  mov     r15d, r13d
0x1800055c2  mov     [rbp+57h+var_AC], 42324132h
0x1800055c9  test    esi, esi
0x1800055cb  jz      loc_180005730
0x1800055d1  mov     eax, r15d
0x1800055d4  mov     ebx, [rbp+rax*4+57h+var_B0]
0x1800055d8  cmp     ebx, r12d
0x1800055db  jz      short loc_1800055FD
0x1800055dd  mov     r8d, ebx
0x1800055e0  mov     rdx, rdi
0x1800055e3  mov     rcx, r14
0x1800055e6  call    ExtractAll_MFT_Luts
0x1800055eb  cmp     dword ptr [rdi+8], 4000000h
0x1800055f2  mov     esi, eax
0x1800055f4  jb      short loc_1800055FD
0x1800055f6  mov     dword ptr [rdi+20h], 2
0x1800055fd  inc     r15d
0x180005600  cmp     r15d, 2
0x180005604  jb      short loc_1800055C9
0x180005606  jmp     loc_180005728
0x18000560b  mov     ebx, 6B545243h
0x180005610  call    Extract_Gray_Luts
0x180005615  mov     esi, eax
0x180005617  jmp     loc_180005728
0x18000561c  cmp     dword ptr [rdi+10h], 434D594Bh
0x180005623  jz      loc_1800056ED
0x180005629  cmp     dword ptr [rdi+10h], 47524159h
0x180005630  jnz     loc_1800056ED
0x180005636  mov     rdx, rdi
0x180005639  mov     rcx, r14
0x18000563c  jmp     short loc_18000560B
0x18000563e  cmp     dword ptr [rdi+10h], 47524159h
0x180005645  jz      short loc_180005636
0x180005647  cmp     dword ptr [rdi+10h], 434D594Bh
0x18000564e  jz      loc_1800056ED
0x180005654  cmp     dword ptr [rdi+10h], 52474220h
0x18000565b  jnz     loc_1800056ED
0x180005661  test    dl, dl
0x180005663  mov     rcx, r14
0x180005666  mov     rdx, rdi
0x180005669  jz      short loc_180005677
0x18000566b  mov     ebx, 72545243h
0x180005670  call    DoMakeGamutForMonitor
0x180005675  jmp     short loc_180005615
0x180005677  mov     r8d, ebx
0x18000567a  call    ExtractAll_MFT_Luts
0x18000567f  mov     esi, eax
0x180005681  test    eax, eax
0x180005683  jz      loc_180005730
0x180005689  cmp     [rdi+1Ch], r13d
0x18000568d  jz      short loc_1800056C0
0x18000568f  mov     al, [rdi+36h]
0x180005692  mov     rdx, rdi
0x180005695  neg     al
0x180005697  mov     rcx, r14
0x18000569a  sbb     ebx, ebx
0x18000569c  and     ebx, 0FFFF00h
0x1800056a2  add     ebx, r12d
0x1800056a5  mov     r8d, ebx
0x1800056a8  call    ExtractAll_MFT_Luts
0x1800056ad  cmp     dword ptr [rdi+8], 4000000h
0x1800056b4  mov     esi, eax
0x1800056b6  jb      short loc_1800056BC
0x1800056b8  mov     [rdi+20h], r15d
0x1800056bc  test    eax, eax
0x1800056be  jz      short loc_180005730
0x1800056c0  cmp     dword ptr [rdi+14h], 58595A20h
0x1800056c7  jnz     short loc_180005728
0x1800056c9  mov     rdx, rdi
0x1800056cc  mov     rcx, r14
0x1800056cf  mov     ebx, 72545243h
0x1800056d4  call    ExtractAll_TRC_Luts
0x1800056d9  cmp     dword ptr [rdi+8], 4000000h
0x1800056e0  mov     esi, eax
0x1800056e2  jb      short loc_180005728
0x1800056e4  mov     dword ptr [rdi+20h], 1
0x1800056eb  jmp     short loc_180005728
0x1800056ed  mov     r8d, ebx
0x1800056f0  mov     rdx, rdi
0x1800056f3  mov     rcx, r14
0x1800056f6  call    ExtractAll_MFT_Luts
0x1800056fb  jmp     loc_180005615
0x180005700  mov     ebx, r12d
0x180005703  mov     r8d, r12d
0x180005706  jmp     short loc_1800056F0
0x180005708  mov     ebx, r12d
0x18000570b  mov     r8d, r12d
0x18000570e  mov     rdx, rdi
0x180005711  mov     rcx, r14
0x180005714  call    ExtractAll_MFT_Luts
0x180005719  cmp     dword ptr [rdi+8], 4000000h
0x180005720  mov     esi, eax
0x180005722  jb      short loc_180005728
0x180005724  mov     [rdi+20h], r15d
0x180005728  test    esi, esi
0x18000572a  jnz     loc_180005806
0x180005730  mov     [rbp+57h+var_B0], ebx
0x180005733  mov     edx, r13d
0x180005736  mov     r10d, 4
0x18000573c  movsxd  rcx, edx
0x18000573f  lea     rax, [rbp+57h+var_B0+3]
0x180005743  sub     rax, rcx
0x180005746  inc     edx
0x180005748  movsx   eax, byte ptr [rax]
0x18000574b  mov     [rbp+rcx*2+57h+var_60], ax
0x180005750  cmp     edx, r10d
0x180005753  jb      short loc_18000573C
0x180005755  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005759  mov     [rbp+57h+var_58], r13w
0x18000575e  mov     rax, rdx
0x180005761  lea     rcx, [rbp+57h+var_60]
0x180005765  inc     rax
0x180005768  cmp     [rcx+rax*2], r13w
0x18000576d  jnz     short loc_180005765
0x18000576f  lea     rax, ds:2[rax*2]
0x180005777  mov     dword ptr [rbp+57h+UserData.0Ch], r13d
0x18000577b  mov     [rbp+57h+UserData.Size], eax
0x18000577e  lea     rcx, [rbp+57h+var_60]
0x180005782  lea     rax, [rbp+57h+var_A8]
0x180005786  mov     [rbp+57h+UserData.Ptr], rcx
0x18000578a  mov     [rbp+57h+var_90], rax
0x18000578e  mov     r8d, r13d
0x180005791  mov     eax, [rdi+0Ch]
0x180005794  mov     [rbp+57h+var_B0], eax
0x180005797  mov     [rbp+57h+var_88], r10
0x18000579b  movsxd  rcx, r8d
0x18000579e  lea     rax, [rbp+57h+var_B0+3]
0x1800057a2  sub     rax, rcx
0x1800057a5  inc     r8d
0x1800057a8  movsx   eax, byte ptr [rax]
0x1800057ab  mov     [rbp+rcx*2+57h+var_50], ax
0x1800057b0  cmp     r8d, r10d
0x1800057b3  jb      short loc_18000579B
0x1800057b5  mov     [rbp+57h+var_48], r13w
0x1800057ba  lea     rax, [rbp+57h+var_50]
0x1800057be  inc     rdx
0x1800057c1  cmp     [rax+rdx*2], r13w
0x1800057c6  jnz     short loc_1800057BE
0x1800057c8  lea     rax, ds:2[rdx*2]
0x1800057d0  mov     [rbp+57h+var_74], r13d
0x1800057d4  lea     rcx, [rbp+57h+var_50]
0x1800057d8  mov     [rbp+57h+var_78], eax
0x1800057db  lea     rax, [rdi+1Ch]
0x1800057df  mov     [rbp+57h+var_80], rcx
0x1800057e3  mov     rcx, cs:g_etwHandle; RegHandle
0x1800057ea  lea     r9, [rbp+57h+UserData]; UserData
0x1800057ee  mov     r8d, r10d; UserDataCount
0x1800057f1  mov     [rbp+57h+var_70], rax
0x1800057f5  lea     rdx, SELECT_TAG; EventDescriptor
0x1800057fc  mov     [rbp+57h+var_68], r10
0x180005800  call    cs:__imp_EventWrite
0x180005806  mov     eax, esi
0x180005808  mov     rcx, [rbp+57h+var_40]
0x18000580c  xor     rcx, rsp; StackCookie
0x18000580f  call    __security_check_cookie
0x180005814  mov     rbx, [rsp+0D0h+arg_10]
0x18000581c  add     rsp, 0A0h
0x180005823  pop     r15
0x180005825  pop     r14
0x180005827  pop     r13
0x180005829  pop     r12
0x18000582b  pop     rdi
  ... truncated ...
```
