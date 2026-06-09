# PsmpReadQuotaValues

- ea: `0x180020f3c`
- end: `0x18002192e`
- name: `PsmpReadQuotaValues`
- size: `2546`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800209f4`

## callees

- `0x18001752c`
- `0x180017650`
- `0x180020f3c`
- `0x1800225ec`
- `0x18002268c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180021396`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180021396`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021641`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021641`

## pseudocode

```c
__int64 __fastcall PsmpReadQuotaValues(int *a1, int a2)
{
  unsigned int v4; // ebx
  int v5; // edi
  int v6; // ebx
  int v7; // edi
  int v8; // ebx
  int v9; // edi
  int v10; // ebx
  int v11; // edi
  int v12; // ebx
  int v13; // edi
  int v14; // ebx
  int v15; // edi
  int v16; // ebx
  int v17; // edi
  int v18; // esi
  int v19; // edi
  int v20; // ebx
  int v21; // edi
  int v22; // ebx
  int v23; // edi
  int v24; // ebx
  unsigned int v25; // edx
  unsigned int v26; // edx
  _QWORD *v27; // r8
  unsigned int v28; // ebx
  __int64 v29; // rdi
  unsigned int i; // esi

  v4 = (((int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"EnableQuota") >> 31) & 0xFFFFFC00) + 1024;
  v5 = v4 | 1;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"BackgroundQuotaGeneral") < 0 )
    v5 = v4;
  v6 = v5 | 2;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"BackgroundQuotaRtc") < 0 )
    v6 = v5;
  v7 = v6 | 4;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaGeneral") < 0 )
    v7 = v6;
  v8 = v7 | 8;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaRtc") < 0 )
    v8 = v7;
  if ( a2 == 1 )
  {
    v9 = v8 | 0x800;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaGeneralWifi") < 0 )
      v9 = v8;
    v10 = v9 | 0x1000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaRtcWifi") < 0 )
      v10 = v9;
    v11 = v10 | 0x2000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaGeneralMbb") < 0 )
      v11 = v10;
    v12 = v11 | 0x4000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaRtcMbb") < 0 )
      v12 = v11;
    v13 = v12 | 0x8000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaGeneralEth") < 0 )
      v13 = v12;
    v14 = v13 | 0x10000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"CriticalQuotaRtcEth") < 0 )
      v14 = v13;
    v15 = v14 | 0x20000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaGeneralWifi") < 0 )
      v15 = v14;
    v16 = v15 | 0x40000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaRtcWifi") < 0 )
      v16 = v15;
    v17 = v16 | 0x80000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaGeneralMbb") < 0 )
      v17 = v16;
    v18 = v17 | 0x100000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaRtcMbb") < 0 )
      v18 = v17;
    v8 = v18 | 0x200000;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaGeneralEth") < 0 )
      v8 = v18;
    if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"VoipQuotaRtcEth") >= 0 )
      v8 |= 0x400000u;
  }
  v19 = v8 | 0x200;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"EnableGlobalPool") < 0 )
    v19 = v8;
  v20 = v19 | 0x10;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"DisableQuotaOnAC") < 0 )
    v20 = v19;
  v21 = v20 | 0x20;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"GeneralGlobalPoolMax") < 0 )
    v21 = v20;
  v22 = v21 | 0x40;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"GeneralGlobalPoolInit") < 0 )
    v22 = v21;
  v23 = v22 | 0x80;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"RtcGlobalPoolMax") < 0 )
    v23 = v22;
  v24 = v23 | 0x100;
  if ( (int)PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], L"RtcGlobalPoolInit") < 0 )
    v24 = v23;
  if ( v24 )
  {
    RtlAcquireSRWLockExclusive(&PsmpPolicyLock);
    if ( (v24 & 1) != 0 )
    {
      v25 = 0;
      if ( a1[39] )
        v25 = a1[39];
      *((_QWORD *)a1 + 18) = v25 * (unsigned __int64)(unsigned int)a1[1];
    }
    if ( (v24 & 2) != 0 )
    {
      v26 = 0;
      if ( a1[38] )
        v26 = a1[38];
      *((_QWORD *)a1 + 17) = v26 * (unsigned __int64)(unsigned int)a1[1];
    }
    if ( (v24 & 4) != 0 && !a2 )
      *((_QWORD *)a1 + 2) = 0;
    if ( (v24 & 8) != 0 && !a2 )
      *((_QWORD *)a1 + 1) = 0;
    if ( (v24 & 0x800) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 6) = 0;
    if ( (v24 & 0x1000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 2) = 0;
    if ( (v24 & 0x2000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 7) = 0;
    if ( (v24 & 0x4000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 3) = 0;
    if ( (v24 & 0x8000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 8) = 0;
    if ( (v24 & 0x10000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 4) = 0;
    if ( (v24 & 0x20000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 14) = 0;
    if ( (v24 & 0x40000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 10) = 0;
    if ( (v24 & 0x80000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 15) = 0;
    if ( (v24 & 0x100000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 11) = 0;
    if ( (v24 & 0x200000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 16) = 0;
    if ( (v24 & 0x400000) != 0 && a2 == 1 )
      *((_QWORD *)a1 + 12) = 0;
    if ( (v24 & 0x20) != 0 )
    {
      *((_QWORD *)a1 + 23) = 0;
      if ( *((__int64 *)a1 + 27) > 0 )
        *((_QWORD *)a1 + 27) = 0;
    }
    if ( (v24 & 0x40) != 0 )
    {
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 27) = 0;
    }
    if ( (v24 & 0x80u) != 0 )
    {
      *((_QWORD *)a1 + 22) = 0;
      if ( *((__int64 *)a1 + 26) > 0 )
        *((_QWORD *)a1 + 26) = 0;
    }
    if ( (v24 & 0x100) != 0 )
    {
      *((_QWORD *)a1 + 24) = 0;
      *((_QWORD *)a1 + 26) = 0;
    }
    if ( (v24 & 0x200) != 0 )
      *((_BYTE *)a1 + 273) = 0;
    if ( (v24 & 0x10) != 0 )
      *((_BYTE *)a1 + 272) = 0;
    if ( (v24 & 0x400) != 0 )
      *((_BYTE *)a1 + 274) = 0;
    RtlReleaseSRWLockExclusive(&PsmpPolicyLock);
    v27 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_LD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        WPP_GLOBAL_Control,
        (unsigned int)*a1,
        *((unsigned __int8 *)a1 + 274));
      v27 = WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)a1 + 273) )
    {
      if ( (*((_BYTE *)v27 + 28) & 1) != 0 )
      {
        if ( *((_BYTE *)v27 + 25) >= 4u )
        {
          WPP_SF_LD(v27[2], 100, v27, (unsigned int)*a1, *((unsigned __int8 *)a1 + 273));
          v27 = WPP_GLOBAL_Control;
        }
        if ( (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
        {
          WPP_SF_LD(v27[2], 101, v27, (unsigned int)*a1, *((unsigned __int8 *)a1 + 272));
          v27 = WPP_GLOBAL_Control;
        }
      }
      v28 = 0;
      v29 = 0;
      do
      {
        if ( a2 )
        {
          if ( a2 == 1 )
          {
            if ( (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
            {
              WPP_SF_LD(v27[2], 105, v27, v28, *(_QWORD *)&a1[2 * v29 + 34] / (unsigned __int64)(unsigned int)a1[1]);
              v27 = WPP_GLOBAL_Control;
            }
            for ( i = 0; i < 4; ++i )
            {
              if ( (*((_BYTE *)v27 + 28) & 1) != 0 )
              {
                if ( *((_BYTE *)v27 + 25) >= 4u )
                {
                  WPP_SF_LLD(
                    v27[2],
                    106,
                    v27,
                    v28,
                    i,
                    *(_QWORD *)&a1[8 * v28 + 2 + 2 * i] / (unsigned __int64)(unsigned int)a1[1]);
                  v27 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
                {
                  WPP_SF_LLD(
                    v27[2],
                    107,
                    v27,
                    v28,
                    i,
                    *(_QWORD *)&a1[8 * v28 + 18 + 2 * i] / (unsigned __int64)(unsigned int)a1[1]);
                  v27 = WPP_GLOBAL_Control;
                }
              }
            }
          }
        }
        else
        {
          if ( (*((_BYTE *)v27 + 28) & 1) == 0 )
            goto LABEL_152;
          if ( *((_BYTE *)v27 + 25) >= 4u )
          {
            WPP_SF_LD(v27[2], 102, v27, v28, *(_QWORD *)&a1[2 * v29 + 34] / (unsigned __int64)(unsigned int)a1[1]);
            v27 = WPP_GLOBAL_Control;
          }
          if ( (*((_BYTE *)v27 + 28) & 1) == 0 )
            goto LABEL_152;
          if ( *((_BYTE *)v27 + 25) >= 4u )
          {
            WPP_SF_LD(v27[2], 103, v27, v28, *(_QWORD *)&a1[2 * v29 + 2] / (unsigned __int64)(unsigned int)a1[1]);
            v27 = WPP_GLOBAL_Control;
          }
          if ( (*((_BYTE *)v27 + 28) & 1) == 0 )
            goto LABEL_152;
          if ( *((_BYTE *)v27 + 25) >= 4u )
          {
            WPP_SF_LD(v27[2], 104, v27, v28, *(_QWORD *)&a1[2 * v29 + 6] / (unsigned __int64)(unsigned int)a1[1]);
            v27 = WPP_GLOBAL_Control;
          }
        }
        if ( (*((_BYTE *)v27 + 28) & 1) != 0 )
        {
          if ( *((_BYTE *)v27 + 25) >= 4u )
          {
            WPP_SF_LD(v27[2], 108, v27, v28, *(_QWORD *)&a1[2 * v29 + 44] / (unsigned __int64)(unsigned int)a1[1]);
            v27 = WPP_GLOBAL_Control;
          }
          if ( (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
          {
            WPP_SF_LD(v27[2], 109, v27, v28, *(_QWORD *)&a1[2 * v29 + 48] / (unsigned __int64)(unsigned int)a1[1]);
            v27 = WPP_GLOBAL_Control;
          }
        }
LABEL_152:
        ++v28;
        ++v29;
      }
      while ( v28 < 2 );
    }
  }
  return PsmpReadRefillRates(a1);
}

```

## disassembly

```asm
0x180020f3c  push    rbp
0x180020f3e  push    rbx
0x180020f3f  push    rsi
0x180020f40  push    rdi
0x180020f41  push    r12
0x180020f43  push    r13
0x180020f45  push    r14
0x180020f47  push    r15
0x180020f49  lea     rbp, [rsp-1Fh]
0x180020f4e  sub     rsp, 88h
0x180020f55  xor     r13d, r13d
0x180020f58  lea     rsi, PsmpQuotaName
0x180020f5f  mov     r15d, edx
0x180020f62  mov     [rbp+57h+arg_8], r13d
0x180020f66  movsxd  rdx, dword ptr [rcx]
0x180020f69  lea     r9, [rbp+57h+var_48]
0x180020f6d  mov     r14, rcx
0x180020f70  mov     [rbp+57h+arg_0], r13d
0x180020f74  mov     rcx, cs:KeyHandle; KeyHandle
0x180020f7b  lea     r8, aEnablequota; "EnableQuota"
0x180020f82  mov     [rbp+57h+arg_10], r13d
0x180020f86  mov     rdx, [rsi+rdx*8]; pszSrc
0x180020f8a  mov     [rbp+57h+arg_18], r13d
0x180020f8e  mov     [rbp+57h+var_90], r13d
0x180020f92  mov     [rbp+57h+var_8C], r13d
0x180020f96  mov     [rbp+57h+var_88], r13d
0x180020f9a  mov     [rbp+57h+var_84], r13d
0x180020f9e  mov     [rbp+57h+var_80], r13d
0x180020fa2  mov     [rbp+57h+var_7C], r13d
0x180020fa6  mov     [rbp+57h+var_4C], r13d
0x180020faa  mov     [rbp+57h+var_60], r13d
0x180020fae  mov     [rbp+57h+var_5C], r13d
0x180020fb2  mov     [rbp+57h+var_58], r13d
0x180020fb6  mov     [rbp+57h+var_54], r13d
0x180020fba  mov     [rbp+57h+var_50], r13d
0x180020fbe  mov     [rbp+57h+var_48], r13d
0x180020fc2  mov     [rbp+57h+var_78], r13d
0x180020fc6  mov     [rbp+57h+var_74], r13d
0x180020fca  mov     [rbp+57h+var_70], r13d
0x180020fce  mov     [rbp+57h+var_6C], r13d
0x180020fd2  mov     [rbp+57h+var_68], r13d
0x180020fd6  mov     [rbp+57h+var_64], r13d
0x180020fda  call    PsmpReadRegUlongWithPrefix
0x180020fdf  movsxd  rdx, dword ptr [r14]
0x180020fe2  lea     r9, [rbp+57h+arg_8]
0x180020fe6  mov     rcx, cs:KeyHandle; KeyHandle
0x180020fed  lea     r8, aBackgroundquot_1; "BackgroundQuotaGeneral"
0x180020ff4  sar     eax, 1Fh
0x180020ff7  and     eax, 0FFFFFC00h
0x180020ffc  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021000  lea     ebx, [rax+400h]
0x180021006  call    PsmpReadRegUlongWithPrefix
0x18002100b  movsxd  rdx, dword ptr [r14]
0x18002100e  lea     r12d, [r13+1]
0x180021012  mov     rcx, cs:KeyHandle; KeyHandle
0x180021019  lea     r9, [rbp+57h+arg_0]
0x18002101d  mov     edi, ebx
0x18002101f  lea     r8, aBackgroundquot; "BackgroundQuotaRtc"
0x180021026  or      edi, r12d
0x180021029  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002102d  test    eax, eax
0x18002102f  cmovs   edi, ebx
0x180021032  call    PsmpReadRegUlongWithPrefix
0x180021037  movsxd  rdx, dword ptr [r14]
0x18002103a  lea     r9, [rbp+57h+arg_10]
0x18002103e  mov     rcx, cs:KeyHandle; KeyHandle
0x180021045  lea     r8, aCriticalquotag_2; "CriticalQuotaGeneral"
0x18002104c  mov     ebx, edi
0x18002104e  or      ebx, 2
0x180021051  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021055  test    eax, eax
0x180021057  cmovs   ebx, edi
0x18002105a  call    PsmpReadRegUlongWithPrefix
0x18002105f  movsxd  rdx, dword ptr [r14]
0x180021062  lea     r9, [rbp+57h+arg_18]
0x180021066  mov     rcx, cs:KeyHandle; KeyHandle
0x18002106d  lea     r8, aCriticalquotar_1; "CriticalQuotaRtc"
0x180021074  mov     edi, ebx
0x180021076  or      edi, 4
0x180021079  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002107d  test    eax, eax
0x18002107f  cmovs   edi, ebx
0x180021082  call    PsmpReadRegUlongWithPrefix
0x180021087  mov     ebx, edi
0x180021089  or      ebx, 8
0x18002108c  test    eax, eax
0x18002108e  cmovs   ebx, edi
0x180021091  cmp     r15d, r12d
0x180021094  jnz     loc_180021291
0x18002109a  movsxd  rdx, dword ptr [r14]
0x18002109d  lea     r9, [rbp+57h+var_90]
0x1800210a1  mov     rcx, cs:KeyHandle; KeyHandle
0x1800210a8  lea     r8, aCriticalquotag; "CriticalQuotaGeneralWifi"
0x1800210af  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800210b3  call    PsmpReadRegUlongWithPrefix
0x1800210b8  movsxd  rdx, dword ptr [r14]
0x1800210bb  lea     r9, [rbp+57h+var_8C]
0x1800210bf  mov     rcx, cs:KeyHandle; KeyHandle
0x1800210c6  lea     r8, aCriticalquotar_2; "CriticalQuotaRtcWifi"
0x1800210cd  mov     edi, ebx
0x1800210cf  bts     edi, 0Bh
0x1800210d3  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800210d7  test    eax, eax
0x1800210d9  cmovs   edi, ebx
0x1800210dc  call    PsmpReadRegUlongWithPrefix
0x1800210e1  movsxd  rdx, dword ptr [r14]
0x1800210e4  lea     r9, [rbp+57h+var_88]
0x1800210e8  mov     rcx, cs:KeyHandle; KeyHandle
0x1800210ef  lea     r8, aCriticalquotag_1; "CriticalQuotaGeneralMbb"
0x1800210f6  mov     ebx, edi
0x1800210f8  bts     ebx, 0Ch
0x1800210fc  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021100  test    eax, eax
0x180021102  cmovs   ebx, edi
0x180021105  call    PsmpReadRegUlongWithPrefix
0x18002110a  movsxd  rdx, dword ptr [r14]
0x18002110d  lea     r9, [rbp+57h+var_84]
0x180021111  mov     rcx, cs:KeyHandle; KeyHandle
0x180021118  lea     r8, aCriticalquotar; "CriticalQuotaRtcMbb"
0x18002111f  mov     edi, ebx
0x180021121  bts     edi, 0Dh
0x180021125  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021129  test    eax, eax
0x18002112b  cmovs   edi, ebx
0x18002112e  call    PsmpReadRegUlongWithPrefix
0x180021133  movsxd  rdx, dword ptr [r14]
0x180021136  lea     r9, [rbp+57h+var_80]
0x18002113a  mov     rcx, cs:KeyHandle; KeyHandle
0x180021141  lea     r8, aCriticalquotag_0; "CriticalQuotaGeneralEth"
0x180021148  mov     ebx, edi
0x18002114a  bts     ebx, 0Eh
0x18002114e  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021152  test    eax, eax
0x180021154  cmovs   ebx, edi
0x180021157  call    PsmpReadRegUlongWithPrefix
0x18002115c  movsxd  rdx, dword ptr [r14]
0x18002115f  lea     r9, [rbp+57h+var_7C]
0x180021163  mov     rcx, cs:KeyHandle; KeyHandle
0x18002116a  lea     r8, aCriticalquotar_0; "CriticalQuotaRtcEth"
0x180021171  mov     edi, ebx
0x180021173  bts     edi, 0Fh
0x180021177  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002117b  test    eax, eax
0x18002117d  cmovs   edi, ebx
0x180021180  call    PsmpReadRegUlongWithPrefix
0x180021185  movsxd  rdx, dword ptr [r14]
0x180021188  lea     r9, [rbp+57h+var_78]
0x18002118c  mov     rcx, cs:KeyHandle; KeyHandle
0x180021193  lea     r8, aVoipquotagener; "VoipQuotaGeneralWifi"
0x18002119a  mov     ebx, edi
0x18002119c  bts     ebx, 10h
0x1800211a0  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800211a4  test    eax, eax
0x1800211a6  cmovs   ebx, edi
0x1800211a9  call    PsmpReadRegUlongWithPrefix
0x1800211ae  movsxd  rdx, dword ptr [r14]
0x1800211b1  lea     r9, [rbp+57h+var_74]
0x1800211b5  mov     rcx, cs:KeyHandle; KeyHandle
0x1800211bc  lea     r8, aVoipquotartcwi; "VoipQuotaRtcWifi"
0x1800211c3  mov     edi, ebx
0x1800211c5  bts     edi, 11h
0x1800211c9  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800211cd  test    eax, eax
0x1800211cf  cmovs   edi, ebx
0x1800211d2  call    PsmpReadRegUlongWithPrefix
0x1800211d7  movsxd  rdx, dword ptr [r14]
0x1800211da  mov     ebx, edi
0x1800211dc  bts     ebx, 12h
0x1800211e0  test    eax, eax
0x1800211e2  cmovs   ebx, edi
0x1800211e5  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800211e9  lea     r9, [rbp+57h+var_70]
0x1800211ed  mov     rcx, cs:KeyHandle; KeyHandle
0x1800211f4  lea     r8, aVoipquotagener_0; "VoipQuotaGeneralMbb"
0x1800211fb  call    PsmpReadRegUlongWithPrefix
0x180021200  movsxd  rdx, dword ptr [r14]
0x180021203  lea     r9, [rbp+57h+var_6C]
0x180021207  mov     rcx, cs:KeyHandle; KeyHandle
0x18002120e  lea     r8, aVoipquotartcmb; "VoipQuotaRtcMbb"
0x180021215  mov     edi, ebx
0x180021217  bts     edi, 13h
0x18002121b  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002121f  test    eax, eax
0x180021221  cmovs   edi, ebx
0x180021224  call    PsmpReadRegUlongWithPrefix
0x180021229  movsxd  rdx, dword ptr [r14]
0x18002122c  lea     r9, [rbp+57h+var_68]
0x180021230  mov     rcx, cs:KeyHandle; KeyHandle
0x180021237  lea     r8, aVoipquotagener_1; "VoipQuotaGeneralEth"
0x18002123e  mov     esi, edi
0x180021240  bts     esi, 14h
0x180021244  test    eax, eax
0x180021246  lea     rax, PsmpQuotaName
0x18002124d  mov     rdx, [rax+rdx*8]; pszSrc
0x180021251  cmovs   esi, edi
0x180021254  call    PsmpReadRegUlongWithPrefix
0x180021259  movsxd  rdx, dword ptr [r14]
0x18002125c  lea     r9, [rbp+57h+var_64]
0x180021260  mov     rcx, cs:KeyHandle; KeyHandle
0x180021267  lea     r8, aVoipquotartcet; "VoipQuotaRtcEth"
0x18002126e  mov     ebx, esi
0x180021270  bts     ebx, 15h
0x180021274  test    eax, eax
0x180021276  cmovs   ebx, esi
0x180021279  lea     rsi, PsmpQuotaName
0x180021280  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021284  call    PsmpReadRegUlongWithPrefix
0x180021289  test    eax, eax
0x18002128b  js      short loc_180021291
0x18002128d  bts     ebx, 16h
0x180021291  movsxd  rdx, dword ptr [r14]
0x180021294  lea     r9, [rbp+57h+var_50]
0x180021298  mov     rcx, cs:KeyHandle; KeyHandle
0x18002129f  lea     r8, aEnableglobalpo; "EnableGlobalPool"
0x1800212a6  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800212aa  call    PsmpReadRegUlongWithPrefix
0x1800212af  movsxd  rdx, dword ptr [r14]
0x1800212b2  lea     r9, [rbp+57h+var_4C]
0x1800212b6  mov     rcx, cs:KeyHandle; KeyHandle
0x1800212bd  lea     r8, aDisablequotaon; "DisableQuotaOnAC"
0x1800212c4  mov     edi, ebx
0x1800212c6  bts     edi, 9
0x1800212ca  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800212ce  test    eax, eax
0x1800212d0  cmovs   edi, ebx
0x1800212d3  call    PsmpReadRegUlongWithPrefix
0x1800212d8  movsxd  rdx, dword ptr [r14]
0x1800212db  lea     r9, [rbp+57h+var_60]
0x1800212df  mov     rcx, cs:KeyHandle; KeyHandle
0x1800212e6  lea     r8, aGeneralglobalp; "GeneralGlobalPoolMax"
0x1800212ed  mov     ebx, edi
0x1800212ef  or      ebx, 10h
0x1800212f2  mov     rdx, [rsi+rdx*8]; pszSrc
0x1800212f6  test    eax, eax
0x1800212f8  cmovs   ebx, edi
0x1800212fb  call    PsmpReadRegUlongWithPrefix
0x180021300  movsxd  rdx, dword ptr [r14]
0x180021303  lea     r9, [rbp+57h+var_5C]
0x180021307  mov     rcx, cs:KeyHandle; KeyHandle
0x18002130e  lea     r8, aGeneralglobalp_0; "GeneralGlobalPoolInit"
0x180021315  mov     edi, ebx
0x180021317  or      edi, 20h
0x18002131a  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002131e  test    eax, eax
0x180021320  cmovs   edi, ebx
0x180021323  call    PsmpReadRegUlongWithPrefix
0x180021328  movsxd  rdx, dword ptr [r14]
0x18002132b  lea     r9, [rbp+57h+var_58]
0x18002132f  mov     rcx, cs:KeyHandle; KeyHandle
0x180021336  lea     r8, aRtcglobalpoolm; "RtcGlobalPoolMax"
0x18002133d  mov     ebx, edi
0x18002133f  or      ebx, 40h
0x180021342  mov     rdx, [rsi+rdx*8]; pszSrc
0x180021346  test    eax, eax
0x180021348  cmovs   ebx, edi
0x18002134b  call    PsmpReadRegUlongWithPrefix
0x180021350  movsxd  rdx, dword ptr [r14]
0x180021353  lea     r9, [rbp+57h+var_54]
0x180021357  mov     rcx, cs:KeyHandle; KeyHandle
0x18002135e  lea     r8, aRtcglobalpooli; "RtcGlobalPoolInit"
0x180021365  mov     edi, ebx
0x180021367  bts     edi, 7
0x18002136b  mov     rdx, [rsi+rdx*8]; pszSrc
0x18002136f  test    eax, eax
0x180021371  cmovs   edi, ebx
0x180021374  call    PsmpReadRegUlongWithPrefix
0x180021379  mov     ebx, edi
0x18002137b  mov     esi, 100h
0x180021380  or      ebx, esi
0x180021382  test    eax, eax
0x180021384  cmovs   ebx, edi
0x180021387  test    ebx, ebx
0x180021389  jz      loc_180021913
0x18002138f  lea     rcx, PsmpPolicyLock
0x180021396  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002139c  test    r12b, bl
0x18002139f  jz      short loc_1800213C1
0x1800213a1  mov     eax, [r14+9Ch]
0x1800213a8  mov     edx, [rbp+57h+arg_8]
0x1800213ab  cmp     edx, eax
0x1800213ad  mov     ecx, [r14+4]
0x1800213b1  cmovb   edx, eax
0x1800213b4  mov     eax, edx
0x1800213b6  imul    rcx, rax
0x1800213ba  mov     [r14+90h], rcx
0x1800213c1  test    bl, 2
0x1800213c4  jz      short loc_1800213E6
0x1800213c6  mov     eax, [r14+98h]
0x1800213cd  mov     edx, [rbp+57h+arg_0]
0x1800213d0  cmp     edx, eax
0x1800213d2  mov     ecx, [r14+4]
0x1800213d6  cmovb   edx, eax
0x1800213d9  mov     eax, edx
0x1800213db  imul    rcx, rax
0x1800213df  mov     [r14+88h], rcx
0x1800213e6  test    bl, 4
0x1800213e9  jz      short loc_1800213FF
0x1800213eb  test    r15d, r15d
0x1800213ee  jnz     short loc_1800213FF
0x1800213f0  mov     ecx, [r14+4]
  ... truncated ...
```
