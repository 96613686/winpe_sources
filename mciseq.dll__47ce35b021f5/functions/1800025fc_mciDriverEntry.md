# mciDriverEntry

- ea: `0x1800025fc`
- end: `0x180002a7f`
- name: `mciDriverEntry`
- size: `1155`
- prototype: `__int64 __fastcall(MCIDEVICEID wDeviceID, unsigned int, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000160c`
- `0x180001a44`
- `0x1800022c0`

## callees

- `0x1800014f8`
- `0x18000160c`
- `0x180001810`
- `0x180001a44`
- `0x180001bfc`
- `0x180001eec`
- `0x18000240c`
- `0x1800025fc`
- `0x1800033d8`
- `0x180003520`
- `0x1800036e0`
- `0x180005270`
- `0x180005ff0`

## import_xrefs

- `WINMM!mciGetDriverData` at `0x18000262c`
- `WINMM!mciGetDriverData` at `0x18000262c`
- `WINMM!mciDriverNotify` at `0x180002a18`
- `WINMM!mciDriverNotify` at `0x180002a18`
- `WINMM!midiOutGetNumDevs` at `0x18000291b`
- `WINMM!midiOutGetNumDevs` at `0x18000291b`

## pseudocode

```c
__int64 __fastcall mciDriverEntry(MCIDEVICEID wDeviceID, unsigned int a2, unsigned int a3, __int64 a4)
{
  int v8; // r15d
  DWORD_PTR DriverData; // rdi
  unsigned int v11; // esi
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // r15d
  unsigned int v17; // eax
  bool v18; // zf
  bool v19; // zf
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  DWORD_PTR v24; // [rsp+20h] [rbp-50h] BYREF
  __int128 v25; // [rsp+28h] [rbp-48h] BYREF
  __int128 v26; // [rsp+38h] [rbp-38h]
  __int128 v27; // [rsp+48h] [rbp-28h]
  __int64 v28; // [rsp+58h] [rbp-18h]

  v8 = 0;
  DriverData = mciGetDriverData(wDeviceID);
  v24 = DriverData;
  if ( !DriverData )
  {
    if ( a2 != 2049 )
    {
      if ( a2 != 2059 )
      {
        if ( a2 != 2058 )
        {
          if ( a2 != 2050 )
            return 274;
          goto LABEL_25;
        }
        goto LABEL_27;
      }
      goto LABEL_28;
    }
LABEL_10:
    switch ( a2 )
    {
      case 0x80Au:
LABEL_27:
        v12 = msInfo((_WORD *)DriverData, 2059, a3, a4);
        break;
      case 0x801u:
        v14 = msOpen(&v24, wDeviceID, a3, a4);
        DriverData = v24;
        v11 = v14;
        goto LABEL_49;
      case 0x802u:
        if ( DriverData )
        {
          midiSeqMessage(*(_QWORD *)(DriverData + 256), 9u, 0, 0);
          midiSeqMessage(*(_QWORD *)(DriverData + 256), 0xDu, 0, 0);
          v13 = 2;
          if ( a3 != 1 )
            v13 = 4;
          Notify(DriverData, v13);
          EndFileStream(DriverData);
        }
LABEL_25:
        v11 = 0;
        DriverData = 0;
        goto LABEL_49;
      case 0x806u:
        v12 = msPlay(DriverData, wDeviceID, a3, a4);
        break;
      case 0x807u:
        *(_DWORD *)(DriverData + 348) = 0;
        v12 = msSeek(DriverData, wDeviceID, a3, a4);
        break;
      default:
        if ( a2 - 2056 > 1 )
          return 261;
        *(_DWORD *)(DriverData + 348) = a2 == 2057;
        v11 = midiSeqMessage(*(_QWORD *)(DriverData + 256), 9u, 0, 0);
        if ( !v11 )
          midiSeqMessage(*(_QWORD *)(DriverData + 256), 0xDu, 1, 0);
LABEL_49:
        if ( (_WORD)v11 )
          return v11;
        v28 = 0;
        v25 = 0;
        v26 = 0;
        v27 = 0;
        if ( a2 == 2054 )
        {
          midiSeqMessage(*(_QWORD *)(DriverData + 256), 0xBu, (__int64)&v25, 0);
          if ( (a3 & 8) == 0
            || (v16 = *(_DWORD *)(a4 + 12), v16 == (unsigned int)CnvtTimeFromSeq(DriverData, DWORD1(v25), &v25)) )
          {
            v8 = DWORD1(v25);
          }
          else
          {
            v8 = CnvtTimeToSeq(DriverData, v16, &v25);
          }
        }
        if ( !DriverData )
        {
          if ( (a3 & 1) != 0 )
            mciDriverNotify(*(HANDLE *)a4, wDeviceID, 1u);
          return v11;
        }
        if ( !*(_QWORD *)(DriverData + 320) )
          goto LABEL_70;
        if ( *(_DWORD *)(DriverData + 328) == 2054 )
        {
          if ( a2 != 2050 )
          {
            if ( a2 != 2054 )
            {
              if ( a2 == 2055 )
                goto LABEL_69;
              v17 = a2 - 2056;
              if ( a2 == 2056 )
                goto LABEL_69;
LABEL_68:
              if ( v17 == 1 )
                goto LABEL_69;
LABEL_77:
              if ( (a3 & 1) == 0 )
                return v11;
              Notify(DriverData, 2);
LABEL_71:
              *(_QWORD *)(DriverData + 320) = *(_QWORD *)a4;
              *(_DWORD *)(DriverData + 328) = a2;
              *(_DWORD *)(DriverData + 332) = v8;
              if ( a2 != 2054 )
              {
                if ( a2 == 2055 )
                  return v11;
                goto LABEL_80;
              }
              if ( DWORD1(v26) == v8 )
LABEL_80:
                Notify(DriverData, 1);
              return v11;
            }
            if ( (a3 & 4) == 0 )
            {
              v18 = v8 == *(_DWORD *)(DriverData + 332);
LABEL_76:
              if ( v18 )
                goto LABEL_77;
            }
          }
        }
        else
        {
          if ( *(_DWORD *)(DriverData + 328) != 2055 )
            goto LABEL_77;
          if ( a2 != 2050 )
          {
            v17 = a2 - 2054;
            if ( a2 == 2054 )
            {
              v18 = (a3 & 4) == 0;
              goto LABEL_76;
            }
            goto LABEL_68;
          }
        }
LABEL_69:
        Notify(DriverData, 4);
LABEL_70:
        if ( (a3 & 1) == 0 )
          return v11;
        goto LABEL_71;
    }
LABEL_20:
    v11 = v12;
    goto LABEL_49;
  }
  if ( a2 > 0x830 )
  {
    if ( a2 > 0x850 )
    {
      v20 = a2 - 2129;
      v19 = v20 == 0;
    }
    else
    {
      if ( a2 == 2128 )
        return 274;
      v20 = a2 - 2112;
      v19 = v20 == 0;
    }
    if ( v19 )
      return 274;
    v21 = v20 - 1;
    if ( !v21 )
      return 274;
    v22 = v21 - 1;
    if ( !v22 )
      return 274;
    v23 = v22 - 1;
    if ( !v23 || v23 - 1 < 2 )
      return 274;
    return 261;
  }
  if ( a2 == 2096 )
    return 274;
  if ( a2 <= 0x80A )
    goto LABEL_10;
LABEL_28:
  switch ( a2 )
  {
    case 0x80Bu:
      if ( (a3 & 0x100) == 0 )
      {
LABEL_37:
        v11 = 273;
        goto LABEL_49;
      }
      if ( *(_DWORD *)(a4 + 12) == 1 )
        goto LABEL_47;
      if ( *(_DWORD *)(a4 + 12) != 2 )
      {
        switch ( *(_DWORD *)(a4 + 12) )
        {
          case 3:
            goto LABEL_47;
          case 4:
            v15 = 34275851;
            goto LABEL_48;
          case 5:
          case 6:
            goto LABEL_55;
          case 7:
LABEL_47:
            v15 = 34799616;
LABEL_48:
            *(_DWORD *)(a4 + 8) = v15;
            v11 = 0x10000;
            goto LABEL_49;
        }
        if ( *(_DWORD *)(a4 + 12) != 8 )
        {
          if ( *(_DWORD *)(a4 + 12) != 9 )
            goto LABEL_37;
          goto LABEL_47;
        }
      }
LABEL_55:
      v15 = midiOutGetNumDevs() != 0 ? 34865153 : 34799616;
      goto LABEL_48;
    case 0x80Du:
      v12 = msSet(DriverData, 2059, a3, a4);
      goto LABEL_20;
    case 0x80Eu:
    case 0x80Fu:
    case 0x813u:
      return 274;
    case 0x814u:
      v12 = msStatus(DriverData, 2059, a3, a4);
      goto LABEL_20;
  }
  return 261;
}

```

## disassembly

```asm
0x1800025fc  mov     [rsp-38h+arg_8], rbx
0x180002601  push    rbp
0x180002602  push    rsi
0x180002603  push    rdi
0x180002604  push    r12
0x180002606  push    r13
0x180002608  push    r14
0x18000260a  push    r15
0x18000260c  mov     rbp, rsp
0x18000260f  sub     rsp, 70h
0x180002613  mov     rax, cs:__security_cookie
0x18000261a  xor     rax, rsp
0x18000261d  mov     [rbp+var_10], rax
0x180002621  mov     r12, r9
0x180002624  mov     r14, r8
0x180002627  mov     ebx, edx
0x180002629  mov     r13d, ecx
0x18000262c  call    cs:__imp_mciGetDriverData
0x180002632  mov     edx, 80Bh
0x180002637  xor     r15d, r15d
0x18000263a  mov     rdi, rax
0x18000263d  mov     [rbp+var_50], rax
0x180002641  mov     esi, 4
0x180002646  lea     eax, [rdx-1]
0x180002649  lea     r8d, [rdx-0Ah]
0x18000264d  test    rdi, rdi
0x180002650  jnz     short loc_18000269C
0x180002652  cmp     ebx, r8d
0x180002655  jz      short loc_1800026B3
0x180002657  cmp     ebx, edx
0x180002659  jz      loc_1800027EE
0x18000265f  cmp     ebx, eax
0x180002661  jz      loc_1800027DB
0x180002667  cmp     ebx, 802h
0x18000266d  jz      loc_1800027B3
0x180002673  mov     eax, 112h
0x180002678  mov     rcx, [rbp+var_10]
0x18000267c  xor     rcx, rsp; StackCookie
0x18000267f  call    __security_check_cookie
0x180002684  mov     rbx, [rsp+70h+arg_8]
0x18000268c  add     rsp, 70h
0x180002690  pop     r15
0x180002692  pop     r14
0x180002694  pop     r13
0x180002696  pop     r12
0x180002698  pop     rdi
0x180002699  pop     rsi
0x18000269a  pop     rbp
0x18000269b  retn
0x18000269c  mov     ecx, 830h
0x1800026a1  cmp     ebx, ecx
0x1800026a3  ja      loc_180002A25
0x1800026a9  jz      short loc_180002673
0x1800026ab  cmp     ebx, eax
0x1800026ad  ja      loc_1800027EE
0x1800026b3  cmp     ebx, eax
0x1800026b5  jz      loc_1800027DB
0x1800026bb  mov     eax, ebx
0x1800026bd  sub     eax, r8d
0x1800026c0  jz      loc_1800027BE
0x1800026c6  sub     eax, 1
0x1800026c9  jz      loc_180002766
0x1800026cf  sub     eax, esi
0x1800026d1  jz      short loc_18000274E
0x1800026d3  sub     eax, 1
0x1800026d6  jz      short loc_180002734
0x1800026d8  sub     eax, 1
0x1800026db  jz      short loc_1800026E6
0x1800026dd  cmp     eax, 1
0x1800026e0  jnz     loc_180002A75
0x1800026e6  mov     eax, r15d
0x1800026e9  cmp     ebx, 809h
0x1800026ef  setz    al
0x1800026f2  xor     r9d, r9d
0x1800026f5  mov     [rdi+15Ch], eax
0x1800026fb  xor     r8d, r8d
0x1800026fe  mov     rcx, [rdi+100h]; dwUser
0x180002705  lea     edx, [r9+9]
0x180002709  call    midiSeqMessage
0x18000270e  mov     rsi, rax
0x180002711  test    eax, eax
0x180002713  jnz     loc_1800028A5
0x180002719  mov     rcx, [rdi+100h]; dwUser
0x180002720  lea     edx, [rax+0Dh]
0x180002723  xor     r9d, r9d
0x180002726  lea     r8d, [rax+1]
0x18000272a  call    midiSeqMessage
0x18000272f  jmp     loc_1800028A5
0x180002734  mov     r8d, r14d
0x180002737  mov     [rdi+15Ch], r15d
0x18000273e  mov     r9, r12
0x180002741  mov     edx, r13d
0x180002744  mov     rcx, rdi
0x180002747  call    msSeek
0x18000274c  jmp     short loc_18000275F
0x18000274e  mov     r8d, r14d
0x180002751  mov     r9, r12
0x180002754  mov     edx, r13d
0x180002757  mov     rcx, rdi
0x18000275a  call    msPlay
0x18000275f  mov     esi, eax
0x180002761  jmp     loc_1800028A5
0x180002766  test    rdi, rdi
0x180002769  jz      short loc_1800027B3
0x18000276b  mov     rcx, [rdi+100h]; dwUser
0x180002772  xor     r9d, r9d
0x180002775  xor     r8d, r8d
0x180002778  lea     edx, [r9+9]
0x18000277c  call    midiSeqMessage
0x180002781  mov     rcx, [rdi+100h]; dwUser
0x180002788  xor     r9d, r9d
0x18000278b  xor     r8d, r8d
0x18000278e  lea     edx, [r9+0Dh]
0x180002792  call    midiSeqMessage
0x180002797  mov     edx, 2
0x18000279c  cmp     r14d, 1
0x1800027a0  mov     rcx, rdi
0x1800027a3  cmovnz  edx, esi
0x1800027a6  call    Notify
0x1800027ab  mov     rcx, rdi
0x1800027ae  call    EndFileStream
0x1800027b3  mov     esi, r15d
0x1800027b6  mov     rdi, r15
0x1800027b9  jmp     loc_1800028A5
0x1800027be  mov     r8d, r14d
0x1800027c1  lea     rcx, [rbp+var_50]
0x1800027c5  mov     r9, r12
0x1800027c8  mov     edx, r13d
0x1800027cb  call    msOpen
0x1800027d0  mov     rdi, [rbp+var_50]
0x1800027d4  mov     esi, eax
0x1800027d6  jmp     loc_1800028A5
0x1800027db  mov     r8d, r14d
0x1800027de  mov     r9, r12
0x1800027e1  mov     rcx, rdi
0x1800027e4  call    msInfo
0x1800027e9  jmp     loc_18000275F
0x1800027ee  mov     eax, ebx
0x1800027f0  sub     eax, edx
0x1800027f2  jz      short loc_180002842
0x1800027f4  sub     eax, 2
0x1800027f7  jz      short loc_18000282F
0x1800027f9  sub     eax, 1
0x1800027fc  jz      loc_180002673
0x180002802  sub     eax, 1
0x180002805  jz      loc_180002673
0x18000280b  sub     eax, esi
0x18000280d  jz      loc_180002673
0x180002813  cmp     eax, 1
0x180002816  jnz     loc_180002A75
0x18000281c  mov     r8d, r14d
0x18000281f  mov     r9, r12
0x180002822  mov     rcx, rdi
0x180002825  call    msStatus
0x18000282a  jmp     loc_18000275F
0x18000282f  mov     r8d, r14d
0x180002832  mov     r9, r12
0x180002835  mov     rcx, rdi
0x180002838  call    msSet
0x18000283d  jmp     loc_18000275F
0x180002842  bt      r14d, 8
0x180002847  jb      short loc_180002850
0x180002849  mov     esi, 111h
0x18000284e  jmp     short loc_1800028A5
0x180002850  mov     ecx, [r12+0Ch]
0x180002855  sub     ecx, 1
0x180002858  jz      short loc_180002896
0x18000285a  sub     ecx, 1
0x18000285d  jz      loc_18000291B
0x180002863  sub     ecx, 1
0x180002866  jz      short loc_180002896
0x180002868  sub     ecx, 1
0x18000286b  jz      loc_180002914
0x180002871  sub     ecx, 1
0x180002874  jz      loc_18000291B
0x18000287a  sub     ecx, 1
0x18000287d  jz      loc_18000291B
0x180002883  sub     ecx, 1
0x180002886  jz      short loc_180002896
0x180002888  sub     ecx, 1
0x18000288b  jz      loc_18000291B
0x180002891  cmp     ecx, 1
0x180002894  jnz     short loc_180002849
0x180002896  mov     eax, 2130000h
0x18000289b  mov     [r12+8], eax
0x1800028a0  mov     esi, 10000h
0x1800028a5  test    si, si
0x1800028a8  jnz     loc_180002A1E
0x1800028ae  xorps   xmm0, xmm0
0x1800028b1  xor     eax, eax
0x1800028b3  mov     [rbp+var_18], rax
0x1800028b7  movups  [rbp+var_48], xmm0
0x1800028bb  movups  [rbp+var_38], xmm0
0x1800028bf  movups  [rbp+var_28], xmm0
0x1800028c3  cmp     ebx, 806h
0x1800028c9  jnz     short loc_180002938
0x1800028cb  mov     rcx, [rdi+100h]; dwUser
0x1800028d2  lea     r8, [rbp+var_48]
0x1800028d6  xor     r9d, r9d
0x1800028d9  lea     edx, [rax+0Bh]
0x1800028dc  call    midiSeqMessage
0x1800028e1  test    r14b, 8
0x1800028e5  jz      short loc_180002934
0x1800028e7  mov     edx, dword ptr [rbp+var_48+4]
0x1800028ea  lea     r8, [rbp+var_48]
0x1800028ee  mov     r15d, [r12+0Ch]
0x1800028f3  mov     rcx, rdi
0x1800028f6  call    CnvtTimeFromSeq
0x1800028fb  cmp     r15d, eax
0x1800028fe  jz      short loc_180002934
0x180002900  lea     r8, [rbp+var_48]
0x180002904  mov     edx, r15d
0x180002907  mov     rcx, rdi
0x18000290a  call    CnvtTimeToSeq
0x18000290f  mov     r15d, eax
0x180002912  jmp     short loc_180002938
0x180002914  mov     eax, 20B020Bh
0x180002919  jmp     short loc_18000289B
0x18000291b  call    cs:__imp_midiOutGetNumDevs
0x180002921  neg     eax
0x180002923  sbb     eax, eax
0x180002925  and     eax, 10001h
0x18000292a  add     eax, 2130000h
0x18000292f  jmp     loc_18000289B
0x180002934  mov     r15d, dword ptr [rbp+var_48+4]
0x180002938  test    rdi, rdi
0x18000293b  jz      loc_180002A05
0x180002941  cmp     qword ptr [rdi+140h], 0
0x180002949  jz      short loc_18000299C
0x18000294b  mov     ecx, [rdi+148h]
0x180002951  sub     ecx, 806h
0x180002957  jz      short loc_180002972
0x180002959  cmp     ecx, 1
0x18000295c  jnz     short loc_1800029DB
0x18000295e  mov     eax, ebx
0x180002960  sub     eax, 802h
0x180002965  jz      short loc_18000298F
0x180002967  sub     eax, 4
0x18000296a  jnz     short loc_18000298A
0x18000296c  test    r14b, 4
0x180002970  jmp     short loc_1800029D9
0x180002972  mov     eax, ebx
0x180002974  sub     eax, 802h
0x180002979  jz      short loc_18000298F
0x18000297b  sub     eax, 4
0x18000297e  jz      short loc_1800029CC
0x180002980  sub     eax, 1
0x180002983  jz      short loc_18000298F
0x180002985  sub     eax, 1
0x180002988  jz      short loc_18000298F
0x18000298a  cmp     eax, 1
0x18000298d  jnz     short loc_1800029DB
0x18000298f  mov     edx, 4
0x180002994  mov     rcx, rdi
0x180002997  call    Notify
0x18000299c  test    r14b, 1
0x1800029a0  jz      short loc_180002A1E
0x1800029a2  mov     rax, [r12]
0x1800029a6  mov     [rdi+140h], rax
0x1800029ad  mov     [rdi+148h], ebx
0x1800029b3  mov     [rdi+14Ch], r15d
0x1800029ba  cmp     ebx, 806h
0x1800029c0  jz      short loc_1800029F0
0x1800029c2  cmp     ebx, 807h
0x1800029c8  jnz     short loc_1800029F6
0x1800029ca  jmp     short loc_180002A1E
0x1800029cc  test    r14b, 4
0x1800029d0  jnz     short loc_18000298F
0x1800029d2  cmp     r15d, [rdi+14Ch]
0x1800029d9  jnz     short loc_18000298F
0x1800029db  test    r14b, 1
0x1800029df  jz      short loc_180002A1E
0x1800029e1  mov     edx, 2
0x1800029e6  mov     rcx, rdi
0x1800029e9  call    Notify
0x1800029ee  jmp     short loc_1800029A2
0x1800029f0  cmp     dword ptr [rbp+var_38+4], r15d
0x1800029f4  jnz     short loc_180002A1E
0x1800029f6  mov     edx, 1
0x1800029fb  mov     rcx, rdi
0x1800029fe  call    Notify
0x180002a03  jmp     short loc_180002A1E
0x180002a05  test    r14b, 1
0x180002a09  jz      short loc_180002A1E
0x180002a0b  mov     rcx, [r12]; hwndCallback
0x180002a0f  mov     r8d, 1; uStatus
0x180002a15  mov     edx, r13d; wDeviceID
0x180002a18  call    cs:__imp_mciDriverNotify
0x180002a1e  mov     eax, esi
0x180002a20  jmp     loc_180002678
0x180002a25  mov     eax, 850h
0x180002a2a  cmp     ebx, eax
0x180002a2c  ja      short loc_180002A3C
0x180002a2e  jz      loc_180002673
0x180002a34  sub     ebx, 840h
0x180002a3a  jmp     short loc_180002A42
0x180002a3c  sub     ebx, 851h
0x180002a42  jz      loc_180002673
0x180002a48  sub     ebx, 1
0x180002a4b  jz      loc_180002673
  ... truncated ...
```
