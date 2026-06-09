# QueryDataIntegrityScanConfiguration(_DISCAN_TASK_CONFIGURATION *)

- ea: `0x180007f18`
- end: `0x18000854e`
- name: `?QueryDataIntegrityScanConfiguration@@YAXPEAU_DISCAN_TASK_CONFIGURATION@@@Z`
- size: `1590`
- prototype: `void __fastcall(struct _DISCAN_TASK_CONFIGURATION *, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005d20`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800071c8`
- `0x1800075a4`
- `0x180007ec8`
- `0x180007f18`
- `0x180008554`
- `0x1800085c0`

## string_xrefs

- `0x180007f37`: `QueryDataIntegrityScanConfiguration`
- `0x1800081bb`: `ScrubThreadPerVolumeMaximum`
- `0x18000821f`: `ScrubThreadMaximumIosPerScrub`
- `0x180008443`: `ScrubProgressUpdatePeriodInHours`

## pseudocode

```c
void __fastcall QueryDataIntegrityScanConfiguration(
        struct _DISCAN_TASK_CONFIGURATION *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v7; // rdx
  USHORT v8; // dx
  USHORT v9; // ax
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  PVOID *v13; // r10
  __int64 v14; // rdx
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  const char *v25; // [rsp+50h] [rbp-30h] BYREF
  signed int v26; // [rsp+58h] [rbp-28h]
  __int64 v27; // [rsp+60h] [rbp-20h] BYREF
  char *v28; // [rsp+68h] [rbp-18h]
  __int64 v29; // [rsp+70h] [rbp-10h]
  unsigned int v30; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+D0h] [rbp+50h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v25 = "QueryDataIntegrityScanConfiguration";
  Length = GlobalIndentString.Length;
  v26 = 0;
  v7 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v7 + 16) = "QueryDataIntegrityScanConfiguration";
  v8 = ++*(_WORD *)(v7 + 8);
  v9 = Length;
  if ( v8 < Length )
  {
    v9 = v8;
    Length = v8;
  }
  LOWORD(v27) = v9;
  HIDWORD(v27) = 0;
  v28 = off_180047060;
  WORD1(v27) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"QueryDataIntegrityScanConfiguration");
  }
  *(_DWORD *)a1 = 1;
  *((_DWORD *)a1 + 2) = 0;
  *(_QWORD *)((char *)a1 + 12) = 50;
  *((_DWORD *)a1 + 5) = 0;
  *((_WORD *)a1 + 2) = 256;
  *((_DWORD *)a1 + 6) = 30;
  *((_DWORD *)a1 + 8) = 96;
  *((_DWORD *)a1 + 7) = 7;
  *((_DWORD *)a1 + 9) = 6;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v10 = ATL::CRegKey::Open(
          (ATL::CRegKey *)&v27,
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\FileSystem",
          a4);
  if ( v10 )
  {
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v26 = v10;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 10;
LABEL_14:
        WPP_SF_d(v13[2], v14, &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids, (unsigned int)v10);
LABEL_110:
        v13 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_111;
      }
      goto LABEL_111;
    }
  }
  else
  {
    v31 = 0;
    v15 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubMode", &v31);
    if ( v15 )
    {
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v26 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v15);
      }
    }
    else if ( v31 == 3 )
    {
      *(_DWORD *)a1 = 3;
    }
    v30 = 0;
    v16 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubConcurrencyMaximum", &v30);
    if ( v16 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v26 = v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v16);
      }
    }
    else
    {
      *((_DWORD *)a1 + 2) = v30;
    }
    v17 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubConcurrencyRate", &v30);
    if ( v17 )
    {
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v26 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v17);
      }
    }
    else
    {
      *((_DWORD *)a1 + 3) = v30;
    }
    v18 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubThreadPerVolumeMaximum", &v30);
    if ( v18 )
    {
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v26 = v18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v18);
      }
    }
    else
    {
      *((_DWORD *)a1 + 4) = v30;
    }
    v19 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubThreadMaximumIosPerScrub", &v30);
    if ( v19 )
    {
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v26 = v19;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v19);
      }
    }
    else
    {
      *((_DWORD *)a1 + 5) = v30;
    }
    v32 = 0;
    v20 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"RefsScrubUseNormalPriority", &v32);
    if ( v20 )
    {
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v26 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v20);
      }
    }
    else if ( v32 == 1 )
    {
      *((_BYTE *)a1 + 4) = 1;
    }
    v21 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubFileInParallel", &v30);
    if ( v21 )
    {
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v26 = v21;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v21);
      }
    }
    else if ( !v30 )
    {
      *((_BYTE *)a1 + 5) = 0;
    }
    v22 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubPeriodInDays", &v30);
    if ( v22 )
    {
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      v26 = v22;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v22);
      }
    }
    else if ( v30 <= 0x16D )
    {
      *((_DWORD *)a1 + 6) = v30;
    }
    v23 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubMaximumDelayAllowedInDays", &v30);
    if ( v23 )
    {
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      v26 = v23;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v23);
      }
    }
    else if ( v30 <= 0x1F )
    {
      *((_DWORD *)a1 + 7) = v30;
    }
    v24 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubAllowToStartInDaysOfWeekMask", &v30);
    if ( v24 )
    {
      if ( v24 > 0 )
        v24 = (unsigned __int16)v24 | 0x80070000;
      v26 = v24;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids,
          (unsigned int)v24);
      }
    }
    else if ( v30 - 1 <= 0x7E )
    {
      *((_DWORD *)a1 + 8) = v30;
    }
    v10 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v27, L"ScrubProgressUpdatePeriodInHours", &v30);
    if ( !v10 )
    {
      if ( v30 - 1 <= 0x17 )
        *((_DWORD *)a1 + 9) = v30;
      goto LABEL_110;
    }
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v26 = v10;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 21;
        goto LABEL_14;
      }
LABEL_111:
      if ( v13 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
        {
          WPP_SF_LDDDDDD(
            v13[2],
            v11,
            v12,
            *(unsigned int *)a1,
            *((_DWORD *)a1 + 2),
            *((_DWORD *)a1 + 3),
            *((_DWORD *)a1 + 4),
            *((_DWORD *)a1 + 5),
            *((unsigned __int8 *)a1 + 4),
            *((unsigned __int8 *)a1 + 5),
            v25,
            v26);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          WPP_SF_DDDD(
            v13[2],
            v11,
            v12,
            *((unsigned int *)a1 + 6),
            *((_DWORD *)a1 + 7),
            *((_DWORD *)a1 + 8),
            *((_DWORD *)a1 + 9));
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)&v27);
  CHResultImp::~CHResultImp((CHResultImp *)&v25);
}

```

## disassembly

```asm
0x180007f18  push    rbp
0x180007f1a  push    rbx
0x180007f1b  push    rsi
0x180007f1c  push    r12
0x180007f1e  push    r13
0x180007f20  push    r14
0x180007f22  push    r15
0x180007f24  mov     rbp, rsp
0x180007f27  sub     rsp, 80h
0x180007f2e  mov     rax, gs:58h
0x180007f37  lea     r8, aQuerydatainteg; "QueryDataIntegrityScanConfiguration"
0x180007f3e  mov     edx, cs:_tls_index
0x180007f44  xor     r15d, r15d
0x180007f47  mov     rbx, rcx
0x180007f4a  mov     [rbp+var_30], r8
0x180007f4e  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180007f55  mov     [rbp+var_28], r15d
0x180007f59  mov     rdx, [rax+rdx*8]
0x180007f5d  lea     r13d, [r15+1]
0x180007f61  mov     eax, 10h
0x180007f66  mov     [rax+rdx], r8
0x180007f6a  mov     eax, 8
0x180007f6f  add     [rax+rdx], r13w
0x180007f74  movzx   edx, word ptr [rax+rdx]
0x180007f78  movzx   eax, cx
0x180007f7b  cmp     dx, cx
0x180007f7e  cmovb   ax, dx
0x180007f82  cmovb   cx, dx
0x180007f86  mov     word ptr [rbp+var_20], ax
0x180007f8a  xor     eax, eax
0x180007f8c  mov     dword ptr [rbp+var_20+4], eax
0x180007f8f  mov     rax, cs:off_180047060; "                                       "...
0x180007f96  mov     [rbp+var_18], rax
0x180007f9a  mov     word ptr [rbp+var_20+2], cx
0x180007f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fa5  lea     rax, WPP_GLOBAL_Control
0x180007fac  lea     r12d, [r15+0Dh]
0x180007fb0  cmp     rcx, rax
0x180007fb3  jz      short loc_180007FD6
0x180007fb5  test    [rcx+1Ch], r13b
0x180007fb9  jz      short loc_180007FD6
0x180007fbb  cmp     byte ptr [rcx+19h], 5
0x180007fbf  jb      short loc_180007FD6
0x180007fc1  mov     rcx, [rcx+10h]; LoggerHandle
0x180007fc5  lea     r9, [rbp+var_20]
0x180007fc9  mov     edx, r12d
0x180007fcc  mov     [rsp+80h+var_60], r8; __int64
0x180007fd1  call    WPP_SF_aZs
0x180007fd6  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Fil"...
0x180007fdd  mov     [rbx], r13d
0x180007fe0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180007fe7  mov     [rbx+8], r15d
0x180007feb  lea     rcx, [rbp+var_20]; this
0x180007fef  mov     qword ptr [rbx+0Ch], 32h ; '2'
0x180007ff7  mov     [rbx+14h], r15d
0x180007ffb  mov     word ptr [rbx+4], 100h
0x180008001  mov     dword ptr [rbx+18h], 1Eh
0x180008008  mov     dword ptr [rbx+20h], 60h ; '`'
0x18000800f  mov     dword ptr [rbx+1Ch], 7
0x180008016  mov     dword ptr [rbx+24h], 6
0x18000801d  mov     [rbp+var_20], r15
0x180008021  mov     [rbp+var_18], r15
0x180008025  mov     [rbp+var_10], r15
0x180008029  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000802e  test    eax, eax
0x180008030  jz      short loc_180008088
0x180008032  jle     short loc_18000803C
0x180008034  movzx   eax, ax
0x180008037  or      eax, 80070000h
0x18000803c  mov     [rbp+var_28], eax
0x18000803f  mov     r10, cs:WPP_GLOBAL_Control
0x180008046  lea     r12, WPP_GLOBAL_Control
0x18000804d  cmp     r10, r12
0x180008050  jz      loc_180008529
0x180008056  test    [r10+1Ch], r13b
0x18000805a  jz      loc_1800084A0
0x180008060  cmp     byte ptr [r10+19h], 2
0x180008065  jb      loc_1800084A0
0x18000806b  mov     edx, 0Ah
0x180008070  lea     r8, WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids
0x180008077  mov     rcx, [r10+10h]
0x18000807b  mov     r9d, eax
0x18000807e  call    WPP_SF_d
0x180008083  jmp     loc_180008499
0x180008088  lea     r8, [rbp+arg_8]; unsigned int *
0x18000808c  mov     [rbp+arg_8], r15d
0x180008090  lea     rdx, aScrubmode; "ScrubMode"
0x180008097  lea     rcx, [rbp+var_20]; this
0x18000809b  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800080a0  lea     r14, WPP_c131e5d6465c38bf7c084a75065d1b80_Traceguids
0x1800080a7  mov     esi, 80070000h
0x1800080ac  test    eax, eax
0x1800080ae  jz      short loc_1800080EF
0x1800080b0  jle     short loc_1800080B7
0x1800080b2  movzx   eax, ax
0x1800080b5  or      eax, esi
0x1800080b7  mov     [rbp+var_28], eax
0x1800080ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080c1  lea     rdx, WPP_GLOBAL_Control
0x1800080c8  cmp     rcx, rdx
0x1800080cb  jz      short loc_1800080FB
0x1800080cd  test    [rcx+1Ch], r13b
0x1800080d1  jz      short loc_1800080FB
0x1800080d3  cmp     byte ptr [rcx+19h], 2
0x1800080d7  jb      short loc_1800080FB
0x1800080d9  mov     rcx, [rcx+10h]
0x1800080dd  mov     edx, 0Bh
0x1800080e2  mov     r9d, eax
0x1800080e5  mov     r8, r14
0x1800080e8  call    WPP_SF_d
0x1800080ed  jmp     short loc_1800080FB
0x1800080ef  cmp     [rbp+arg_8], 3
0x1800080f3  jnz     short loc_1800080FB
0x1800080f5  mov     dword ptr [rbx], 3
0x1800080fb  lea     r8, [rbp+arg_0]; unsigned int *
0x1800080ff  mov     [rbp+arg_0], r15d
0x180008103  lea     rdx, aScrubconcurren_0; "ScrubConcurrencyMaximum"
0x18000810a  lea     rcx, [rbp+var_20]; this
0x18000810e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180008113  test    eax, eax
0x180008115  jz      short loc_180008156
0x180008117  jle     short loc_18000811E
0x180008119  movzx   eax, ax
0x18000811c  or      eax, esi
0x18000811e  mov     [rbp+var_28], eax
0x180008121  mov     rcx, cs:WPP_GLOBAL_Control
0x180008128  lea     rdx, WPP_GLOBAL_Control
0x18000812f  cmp     rcx, rdx
0x180008132  jz      short loc_18000815C
0x180008134  test    [rcx+1Ch], r13b
0x180008138  jz      short loc_18000815C
0x18000813a  cmp     byte ptr [rcx+19h], 2
0x18000813e  jb      short loc_18000815C
0x180008140  mov     rcx, [rcx+10h]
0x180008144  mov     edx, 0Ch
0x180008149  mov     r9d, eax
0x18000814c  mov     r8, r14
0x18000814f  call    WPP_SF_d
0x180008154  jmp     short loc_18000815C
0x180008156  mov     eax, [rbp+arg_0]
0x180008159  mov     [rbx+8], eax
0x18000815c  lea     r8, [rbp+arg_0]; unsigned int *
0x180008160  lea     rdx, aScrubconcurren; "ScrubConcurrencyRate"
0x180008167  lea     rcx, [rbp+var_20]; this
0x18000816b  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180008170  test    eax, eax
0x180008172  jz      short loc_1800081B1
0x180008174  jle     short loc_18000817B
0x180008176  movzx   eax, ax
0x180008179  or      eax, esi
0x18000817b  mov     [rbp+var_28], eax
0x18000817e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008185  lea     rdx, WPP_GLOBAL_Control
0x18000818c  cmp     rcx, rdx
0x18000818f  jz      short loc_1800081B7
0x180008191  test    [rcx+1Ch], r13b
0x180008195  jz      short loc_1800081B7
0x180008197  cmp     byte ptr [rcx+19h], 2
0x18000819b  jb      short loc_1800081B7
0x18000819d  mov     rcx, [rcx+10h]
0x1800081a1  mov     edx, r12d
0x1800081a4  mov     r9d, eax
0x1800081a7  mov     r8, r14
0x1800081aa  call    WPP_SF_d
0x1800081af  jmp     short loc_1800081B7
0x1800081b1  mov     eax, [rbp+arg_0]
0x1800081b4  mov     [rbx+0Ch], eax
0x1800081b7  lea     r8, [rbp+arg_0]; unsigned int *
0x1800081bb  lea     rdx, aScrubthreadper; "ScrubThreadPerVolumeMaximum"
0x1800081c2  lea     rcx, [rbp+var_20]; this
0x1800081c6  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800081cb  test    eax, eax
0x1800081cd  jz      short loc_18000820E
0x1800081cf  jle     short loc_1800081D6
0x1800081d1  movzx   eax, ax
0x1800081d4  or      eax, esi
0x1800081d6  mov     [rbp+var_28], eax
0x1800081d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081e0  lea     r12, WPP_GLOBAL_Control
0x1800081e7  cmp     rcx, r12
0x1800081ea  jz      short loc_18000821B
0x1800081ec  test    [rcx+1Ch], r13b
0x1800081f0  jz      short loc_18000821B
0x1800081f2  cmp     byte ptr [rcx+19h], 2
0x1800081f6  jb      short loc_18000821B
0x1800081f8  mov     rcx, [rcx+10h]
0x1800081fc  mov     edx, 0Eh
0x180008201  mov     r9d, eax
0x180008204  mov     r8, r14
0x180008207  call    WPP_SF_d
0x18000820c  jmp     short loc_18000821B
0x18000820e  mov     eax, [rbp+arg_0]
0x180008211  lea     r12, WPP_GLOBAL_Control
0x180008218  mov     [rbx+10h], eax
0x18000821b  lea     r8, [rbp+arg_0]; unsigned int *
0x18000821f  lea     rdx, aScrubthreadmax; "ScrubThreadMaximumIosPerScrub"
0x180008226  lea     rcx, [rbp+var_20]; this
0x18000822a  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000822f  test    eax, eax
0x180008231  jz      short loc_18000826B
0x180008233  jle     short loc_18000823A
0x180008235  movzx   eax, ax
0x180008238  or      eax, esi
0x18000823a  mov     [rbp+var_28], eax
0x18000823d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008244  cmp     rcx, r12
0x180008247  jz      short loc_180008271
0x180008249  test    [rcx+1Ch], r13b
0x18000824d  jz      short loc_180008271
0x18000824f  cmp     byte ptr [rcx+19h], 2
0x180008253  jb      short loc_180008271
0x180008255  mov     rcx, [rcx+10h]
0x180008259  mov     edx, 0Fh
0x18000825e  mov     r9d, eax
0x180008261  mov     r8, r14
0x180008264  call    WPP_SF_d
0x180008269  jmp     short loc_180008271
0x18000826b  mov     eax, [rbp+arg_0]
0x18000826e  mov     [rbx+14h], eax
0x180008271  lea     r8, [rbp+arg_10]; unsigned int *
0x180008275  mov     [rbp+arg_10], r15d
0x180008279  lea     rdx, aRefsscrubuseno; "RefsScrubUseNormalPriority"
0x180008280  lea     rcx, [rbp+var_20]; this
0x180008284  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180008289  test    eax, eax
0x18000828b  jz      short loc_1800082C5
0x18000828d  jle     short loc_180008294
0x18000828f  movzx   eax, ax
0x180008292  or      eax, esi
0x180008294  mov     [rbp+var_28], eax
0x180008297  mov     rcx, cs:WPP_GLOBAL_Control
0x18000829e  cmp     rcx, r12
0x1800082a1  jz      short loc_1800082CF
0x1800082a3  test    [rcx+1Ch], r13b
0x1800082a7  jz      short loc_1800082CF
0x1800082a9  cmp     byte ptr [rcx+19h], 2
0x1800082ad  jb      short loc_1800082CF
0x1800082af  mov     rcx, [rcx+10h]
0x1800082b3  mov     edx, 10h
0x1800082b8  mov     r9d, eax
0x1800082bb  mov     r8, r14
0x1800082be  call    WPP_SF_d
0x1800082c3  jmp     short loc_1800082CF
0x1800082c5  cmp     [rbp+arg_10], r13d
0x1800082c9  jnz     short loc_1800082CF
0x1800082cb  mov     [rbx+4], r13b
0x1800082cf  lea     r8, [rbp+arg_0]; unsigned int *
0x1800082d3  lea     rdx, aScrubfileinpar; "ScrubFileInParallel"
0x1800082da  lea     rcx, [rbp+var_20]; this
0x1800082de  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800082e3  test    eax, eax
0x1800082e5  jz      short loc_18000831F
0x1800082e7  jle     short loc_1800082EE
0x1800082e9  movzx   eax, ax
0x1800082ec  or      eax, esi
0x1800082ee  mov     [rbp+var_28], eax
0x1800082f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082f8  cmp     rcx, r12
0x1800082fb  jz      short loc_180008329
0x1800082fd  test    [rcx+1Ch], r13b
0x180008301  jz      short loc_180008329
0x180008303  cmp     byte ptr [rcx+19h], 2
0x180008307  jb      short loc_180008329
0x180008309  mov     rcx, [rcx+10h]
0x18000830d  mov     edx, 11h
0x180008312  mov     r9d, eax
0x180008315  mov     r8, r14
0x180008318  call    WPP_SF_d
0x18000831d  jmp     short loc_180008329
0x18000831f  cmp     [rbp+arg_0], r15d
0x180008323  jnz     short loc_180008329
0x180008325  mov     [rbx+5], r15b
0x180008329  lea     r8, [rbp+arg_0]; unsigned int *
0x18000832d  lea     rdx, aScrubperiodind; "ScrubPeriodInDays"
0x180008334  lea     rcx, [rbp+var_20]; this
0x180008338  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000833d  test    eax, eax
0x18000833f  jz      short loc_180008379
0x180008341  jle     short loc_180008348
0x180008343  movzx   eax, ax
0x180008346  or      eax, esi
0x180008348  mov     [rbp+var_28], eax
0x18000834b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008352  cmp     rcx, r12
0x180008355  jz      short loc_180008386
0x180008357  test    [rcx+1Ch], r13b
0x18000835b  jz      short loc_180008386
0x18000835d  cmp     byte ptr [rcx+19h], 2
0x180008361  jb      short loc_180008386
0x180008363  mov     rcx, [rcx+10h]
0x180008367  mov     edx, 12h
0x18000836c  mov     r9d, eax
0x18000836f  mov     r8, r14
0x180008372  call    WPP_SF_d
0x180008377  jmp     short loc_180008386
0x180008379  mov     eax, [rbp+arg_0]
0x18000837c  cmp     eax, 16Dh
0x180008381  ja      short loc_180008386
0x180008383  mov     [rbx+18h], eax
0x180008386  lea     r8, [rbp+arg_0]; unsigned int *
  ... truncated ...
```
