# CopyIniDriverToDriverInfo

- ea: `0x1800391d4`
- end: `0x18003980f`
- name: `CopyIniDriverToDriverInfo`
- size: `1595`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180068db4`
- `0x180069738`
- `0x18006ab60`
- `0x180071bd4`
- `0x18009cdac`
- `0x1800c27d8`

## callees

- `0x18000ba20`
- `0x18000c424`
- `0x180011f00`
- `0x180014930`
- `0x180020420`
- `0x1800390e8`
- `0x1800391d4`
- `0x18003ea2c`
- `0x180046650`
- `0x18006b4bc`
- `0x1800bed34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039284`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039284`
- `SPOOLSS!DllFreeSplStr` at `0x1800397a1`
- `SPOOLSS!DllFreeSplStr` at `0x1800397ac`
- `SPOOLSS!DllFreeSplStr` at `0x1800397b7`
- `SPOOLSS!DllFreeSplStr` at `0x1800397c2`
- `SPOOLSS!DllFreeSplStr` at `0x1800397a1`
- `SPOOLSS!DllFreeSplStr` at `0x1800397ac`
- `SPOOLSS!DllFreeSplStr` at `0x1800397b7`
- `SPOOLSS!DllFreeSplStr` at `0x1800397c2`
- `SPOOLSS!DllFreeSplMem` at `0x1800397cb`
- `SPOOLSS!DllFreeSplMem` at `0x1800397cb`
- `SPOOLSS!DllAllocSplMem` at `0x180039309`
- `SPOOLSS!DllAllocSplMem` at `0x180039309`
- `SPOOLSS!AllocSplStr` at `0x18003943d`
- `SPOOLSS!AllocSplStr` at `0x180039482`
- `SPOOLSS!AllocSplStr` at `0x1800394ba`
- `SPOOLSS!AllocSplStr` at `0x180039511`
- `SPOOLSS!AllocSplStr` at `0x18003943d`
- `SPOOLSS!AllocSplStr` at `0x180039482`
- `SPOOLSS!AllocSplStr` at `0x1800394ba`
- `SPOOLSS!AllocSplStr` at `0x180039511`
- `SPOOLSS!PackStrings` at `0x1800395db`
- `SPOOLSS!PackStrings` at `0x180039793`
- `SPOOLSS!PackStrings` at `0x1800395db`
- `SPOOLSS!PackStrings` at `0x180039793`

## string_xrefs

- `0x18003923e`: `CopyIniDriverToDriverInfo`
- `0x180039454`: `CopyIniDriverToDriverInfo`
- `0x1800395f2`: `CopyIniDriverToDriverInfo`
- `0x1800397da`: `CopyIniDriverToDriverInfo`

## pseudocode

```c
unsigned __int8 *__fastcall CopyIniDriverToDriverInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned __int16 *a7,
        struct _INISPOOLER *a8)
{
  unsigned __int8 *v9; // rbx
  unsigned int v13; // eax
  const unsigned int near *const *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 v17; // rax
  int DriverVersionDirectory; // eax
  __int64 v19; // rcx
  unsigned __int16 *v20; // r13
  unsigned __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  const unsigned __int16 *v27; // r8
  __int64 v28; // r8
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned __int8 *v33; // rcx
  int v34; // eax
  unsigned __int8 *v35; // rax
  unsigned __int8 *v36; // rax
  unsigned __int16 *v37; // [rsp+20h] [rbp-4C8h]
  unsigned int v38; // [rsp+28h] [rbp-4C0h]
  __int64 v39; // [rsp+40h] [rbp-4A8h]
  __int64 v40; // [rsp+48h] [rbp-4A0h]
  unsigned int v41; // [rsp+50h] [rbp-498h]
  __int64 v44; // [rsp+70h] [rbp-478h]
  __int64 v45; // [rsp+78h] [rbp-470h]
  unsigned __int16 v46[520]; // [rsp+80h] [rbp-468h] BYREF

  v9 = a6;
  if ( a6 <= a5 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError("CopyIniDriverToDriverInfo", L"Failing because pEnd <= pDriverInfo!");
    return 0;
  }
  switch ( a4 )
  {
    case 1u:
      v13 = (unsigned int)DriverInfo1Strings;
      v14 = &DriverInfo1Strings;
LABEL_19:
      LODWORD(v15) = 0;
      if ( v13 != -1 )
      {
        do
          v15 = (unsigned int)(v15 + 1);
        while ( *((_DWORD *)v14 + v15) != -1 );
      }
      v16 = DllAllocSplMem((unsigned int)(8 * v15));
      if ( !v16 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "CopyIniDriverToDriverInfo",
          L"Failed to allocate driver source strings.");
        return 0;
      }
      v44 = 0;
      v40 = 0;
      v45 = 0;
      v39 = 0;
      if ( a4 == 1 )
      {
        *(_QWORD *)v16 = *(_QWORD *)(a3 + 24);
        v9 = (unsigned __int8 *)PackStrings(v16, a5, v14, a6);
        goto LABEL_84;
      }
      if ( a4 != 2 && a4 != 3 && a4 != 4 && a4 != 5 && a4 != 6 && a4 != 8 )
      {
LABEL_76:
        if ( a4 == 8 && !IsDriverShareable((struct _INIDRIVER *)a3) )
          *((_DWORD *)a5 + 42) |= 0x20u;
        goto LABEL_84;
      }
      if ( *(_DWORD *)(a2 + 32) >= 4u )
      {
        v9 = CopyV4IniDriverToDriverInfo(
               (struct _INIDRIVER *)a3,
               (struct _INIENVIRONMENT *)a1,
               a4,
               a5,
               a6,
               (unsigned __int16 **)v16,
               (const unsigned int *)v14,
               a7);
        if ( v9 )
          goto LABEL_76;
LABEL_84:
        DllFreeSplStr(v44);
        DllFreeSplStr(v40);
        DllFreeSplStr(v45);
        DllFreeSplStr(v39);
        DllFreeSplMem(v16);
        return v9;
      }
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(*(_QWORD *)(a3 + 32) + 2 * v17) );
      DriverVersionDirectory = GetDriverVersionDirectory(
                                 (unsigned int)v46,
                                 516 - (int)v17,
                                 (_DWORD)a8,
                                 a1,
                                 a2,
                                 a3,
                                 (__int64)a7);
      if ( (unsigned int)(DriverVersionDirectory - 1) > 0x203 )
      {
LABEL_37:
        v9 = 0;
        goto LABEL_84;
      }
      v46[DriverVersionDirectory] = 92;
      v19 = (unsigned int)(DriverVersionDirectory + 1);
      *(_QWORD *)v16 = *(_QWORD *)(a3 + 24);
      *(_QWORD *)(v16 + 8) = *(_QWORD *)(a1 + 24);
      v20 = &v46[v19];
      v21 = 517LL - (unsigned int)v19;
      v41 = DriverVersionDirectory + 1;
      StringCchCopyW(v20, v21, *(const unsigned __int16 **)(a3 + 32));
      v22 = AllocSplStr(v46);
      v44 = v22;
      if ( v22 )
      {
        *(_QWORD *)(v16 + 16) = v22;
        StringCchCopyW(v20, v21, *(const unsigned __int16 **)(a3 + 48));
        v23 = AllocSplStr(v46);
        v45 = v23;
        if ( v23 )
        {
          *(_QWORD *)(v16 + 24) = v23;
          v24 = *(const unsigned __int16 **)(a3 + 40);
          if ( v24 && *v24 )
          {
            StringCchCopyW(v20, v21, v24);
            v25 = AllocSplStr(v46);
            v40 = v25;
            if ( !v25 )
              goto LABEL_36;
          }
          else
          {
            v25 = 0;
          }
          *(_QWORD *)(v16 + 32) = v25;
          v26 = 344;
          if ( _bittest(&v26, a4) )
          {
            v27 = *(const unsigned __int16 **)(a3 + 56);
            if ( v27 && *v27 )
            {
              StringCchCopyW(v20, v21, v27);
              v39 = AllocSplStr(v46);
              v28 = v39;
              if ( !v39 )
                goto LABEL_36;
            }
            else
            {
              v28 = 0;
            }
            *(_QWORD *)(v16 + 40) = v28;
            *(_QWORD *)(v16 + 48) = *(_QWORD *)(a3 + 80);
            *(_QWORD *)(v16 + 56) = *(_QWORD *)(a3 + 88);
            v39 = v28;
            if ( ((a4 - 6) & 0xFFFFFFFD) == 0 )
            {
              v29 = 0;
              *((_QWORD *)a5 + 11) = *(_QWORD *)(a3 + 112);
              v30 = (_QWORD *)(v16 + 64);
              *((_QWORD *)a5 + 12) = *(_QWORD *)(a3 + 120);
              do
              {
                v31 = *(_QWORD *)(a3 + 8 * v29++ + 128);
                *v30++ = v31;
              }
              while ( v29 != 4 );
              if ( a4 == 8 )
              {
                *v30 = *(_QWORD *)(a3 + 160);
                v30[1] = *(_QWORD *)(a3 + 168);
                v30[2] = *(_QWORD *)(a3 + 192);
                *((_DWORD *)a5 + 42) = *(_DWORD *)(a3 + 200);
                *((_QWORD *)a5 + 23) = *(_QWORD *)(a3 + 216);
                *((_QWORD *)a5 + 24) = *(_QWORD *)(a3 + 224);
              }
            }
          }
          v32 = PackStrings(v16, a5, v14, a6);
          v33 = 0;
          v9 = (unsigned __int8 *)v32;
          if ( v32 )
          {
            v34 = 344;
            if ( !_bittest(&v34, a4) )
            {
              *(_DWORD *)a5 = *(_DWORD *)(a3 + 236);
              if ( a4 != 2 )
              {
                if ( !*(_DWORD *)(a3 + 232) )
                  CheckDriverAttributes(
                    a8,
                    (struct _INIENVIRONMENT *)a1,
                    (struct _INIVERSION *)a2,
                    (struct _INIDRIVER *)a3,
                    v37,
                    v38);
                *((_DWORD *)a5 + 12) = *(_DWORD *)(a3 + 232);
                *((_DWORD *)a5 + 13) = GetDriverFileVersion(a2, *(_QWORD *)(a3 + 40));
                *((_DWORD *)a5 + 14) = GetDriverFileVersion(a2, *(_QWORD *)(a3 + 32));
              }
              goto LABEL_84;
            }
            if ( *(_DWORD *)(a3 + 64) <= 2u || v9 <= a5 )
            {
              v35 = 0;
            }
            else
            {
              v35 = CopyMultiSzFieldToDriverInfo(*(unsigned __int16 **)(a3 + 72), v9, v46, v41);
              v9 = v35;
              v33 = 0;
            }
            *((_QWORD *)a5 + 7) = v35;
            if ( ((a4 - 4) & 0xFFFFFFF9) == 0 )
            {
              if ( *(_DWORD *)(a3 + 96) > 2u && v9 > a5 )
              {
                v9 = CopyMultiSzFieldToDriverInfo(*(unsigned __int16 **)(a3 + 104), v9, 0, 0);
                v33 = v9;
              }
              *((_QWORD *)a5 + 10) = v33;
              if ( a4 == 8 )
              {
                if ( *(_DWORD *)(a3 + 176) <= 2u || v9 <= a5 )
                {
                  v36 = 0;
                }
                else
                {
                  v36 = CopyMultiSzFieldToDriverInfo(*(unsigned __int16 **)(a3 + 184), v9, 0, 0);
                  v9 = v36;
                }
                *((_QWORD *)a5 + 19) = v36;
                if ( *(_DWORD *)(a3 + 204) <= 2u || v9 <= a5 )
                {
                  *((_QWORD *)a5 + 22) = 0;
                }
                else
                {
                  v9 = CopyMultiSzFieldToDriverInfo(*(unsigned __int16 **)(a3 + 208), v9, 0, 0);
                  *((_QWORD *)a5 + 22) = v9;
                }
              }
            }
            *(_DWORD *)a5 = *(_DWORD *)(a3 + 236);
            goto LABEL_76;
          }
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "CopyIniDriverToDriverInfo",
            L"PackStrings ran out of space for driver source strings.");
          goto LABEL_84;
        }
      }
LABEL_36:
      LocalSpoolerTelemetry::WriteDbgTraceError("CopyIniDriverToDriverInfo", L"AllocSplStr failed.");
      goto LABEL_37;
    case 2u:
      goto LABEL_17;
    case 3u:
    case 4u:
      v13 = (unsigned int)DriverInfo3Strings;
      v14 = &DriverInfo3Strings;
      goto LABEL_19;
    case 5u:
LABEL_17:
      v13 = (unsigned int)DriverInfo2Strings;
      v14 = &DriverInfo2Strings;
      goto LABEL_19;
    case 6u:
      v13 = (unsigned int)DriverInfo6Strings;
      v14 = &DriverInfo6Strings;
      goto LABEL_19;
    case 8u:
      v13 = DriverInfo8Strings;
      v14 = (const unsigned int near *const *)&DriverInfo8Strings;
      goto LABEL_19;
  }
  if ( a4 != 101 )
  {
    SetLastError(0x7Cu);
    return 0;
  }
  return CopyIniDriverToDriverInfoVersion(
           (struct _INIENVIRONMENT *)a1,
           (struct _INIVERSION *)a2,
           (struct _INIDRIVER *)a3,
           a5,
           a6,
           a7,
           a8);
}

```

## disassembly

```asm
0x1800391d4  push    rbx
0x1800391d6  push    rbp
0x1800391d7  push    rsi
0x1800391d8  push    rdi
0x1800391d9  push    r12
0x1800391db  push    r13
0x1800391dd  push    r14
0x1800391df  push    r15
0x1800391e1  sub     rsp, 4A8h
0x1800391e8  mov     rax, cs:__security_cookie
0x1800391ef  xor     rax, rsp
0x1800391f2  mov     [rsp+4E8h+var_58], rax
0x1800391fa  mov     rsi, [rsp+4E8h+arg_20]
0x180039202  mov     r13, rdx
0x180039205  mov     rbx, [rsp+4E8h+arg_28]
0x18003920d  mov     ebp, r9d
0x180039210  mov     r12, [rsp+4E8h+arg_30]
0x180039218  mov     rdi, r8
0x18003921b  mov     [rsp+4E8h+var_480], rdx
0x180039220  mov     rdx, [rsp+4E8h+arg_38]
0x180039228  mov     [rsp+4E8h+var_488], rdx
0x18003922d  mov     [rsp+4E8h+var_490], rcx
0x180039232  cmp     rbx, rsi
0x180039235  ja      short loc_180039251
0x180039237  lea     rdx, aFailingBecause; "Failing because pEnd <= pDriverInfo!"
0x18003923e  lea     rcx, aCopyinidrivert; "CopyIniDriverToDriverInfo"
0x180039245  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003924a  xor     eax, eax
0x18003924c  jmp     loc_1800397EB
0x180039251  mov     eax, ebp
0x180039253  sub     eax, 1
0x180039256  jz      loc_1800392E7
0x18003925c  sub     eax, 1
0x18003925f  jz      short loc_1800392D8
0x180039261  sub     eax, 1
0x180039264  jz      short loc_1800392C9
0x180039266  sub     eax, 1
0x180039269  jz      short loc_1800392C9
0x18003926b  sub     eax, 1
0x18003926e  jz      short loc_1800392D8
0x180039270  sub     eax, 1
0x180039273  jz      short loc_1800392BA
0x180039275  sub     eax, 2
0x180039278  jz      short loc_1800392AB
0x18003927a  cmp     eax, 5Dh ; ']'
0x18003927d  jz      short loc_18003928C
0x18003927f  mov     ecx, 7Ch ; '|'; dwErrCode
0x180039284  call    cs:__imp_SetLastError
0x18003928a  jmp     short loc_18003924A
0x18003928c  mov     [rsp+4E8h+var_4B8], rdx; struct _INISPOOLER *
0x180039291  mov     r9, rsi; unsigned __int8 *
0x180039294  mov     [rsp+4E8h+var_4C0], r12; unsigned __int16 *
0x180039299  mov     rdx, r13; struct _INIVERSION *
0x18003929c  mov     [rsp+4E8h+var_4C8], rbx; unsigned __int8 *
0x1800392a1  call    ?CopyIniDriverToDriverInfoVersion@@YAPEAEPEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEAE3PEAGPEAU_INISPOOLER@@@Z; CopyIniDriverToDriverInfoVersion(_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,uchar *,uchar *,ushort *,_INISPOOLER *)
0x1800392a6  jmp     loc_1800397EB
0x1800392ab  mov     eax, cs:?DriverInfo8Strings@@3QBKB; ulong const near * const DriverInfo8Strings
0x1800392b1  lea     r14, ?DriverInfo8Strings@@3QBKB; ulong const near * const DriverInfo8Strings
0x1800392b8  jmp     short loc_1800392F5
0x1800392ba  mov     eax, cs:?DriverInfo6Strings@@3QBKB; ulong const near * const DriverInfo6Strings
0x1800392c0  lea     r14, ?DriverInfo6Strings@@3QBKB; ulong const near * const DriverInfo6Strings
0x1800392c7  jmp     short loc_1800392F5
0x1800392c9  mov     eax, cs:?DriverInfo3Strings@@3QBKB; ulong const near * const DriverInfo3Strings
0x1800392cf  lea     r14, ?DriverInfo3Strings@@3QBKB; ulong const near * const DriverInfo3Strings
0x1800392d6  jmp     short loc_1800392F5
0x1800392d8  mov     eax, cs:?DriverInfo2Strings@@3QBKB; ulong const near * const DriverInfo2Strings
0x1800392de  lea     r14, ?DriverInfo2Strings@@3QBKB; ulong const near * const DriverInfo2Strings
0x1800392e5  jmp     short loc_1800392F5
0x1800392e7  mov     rax, cs:?DriverInfo1Strings@@3QBKB; ulong const near * const DriverInfo1Strings
0x1800392ee  lea     r14, ?DriverInfo1Strings@@3QBKB; ulong const near * const DriverInfo1Strings
0x1800392f5  xor     ecx, ecx
0x1800392f7  or      edx, 0FFFFFFFFh
0x1800392fa  cmp     eax, edx
0x1800392fc  jz      short loc_180039306
0x1800392fe  inc     ecx
0x180039300  cmp     [r14+rcx*4], edx
0x180039304  jnz     short loc_1800392FE
0x180039306  shl     ecx, 3
0x180039309  call    cs:__imp_DllAllocSplMem
0x18003930f  xor     edx, edx
0x180039311  mov     r15, rax
0x180039314  test    rax, rax
0x180039317  jz      loc_1800397D3
0x18003931d  mov     eax, ebp
0x18003931f  mov     [rsp+4E8h+var_478], rdx
0x180039324  mov     [rsp+4E8h+var_4A0], rdx
0x180039329  mov     [rsp+4E8h+var_470], rdx
0x18003932e  mov     [rsp+4E8h+var_4A8], rdx
0x180039333  sub     eax, 1
0x180039336  jz      loc_180039780
0x18003933c  sub     eax, 1
0x18003933f  jz      short loc_18003935E
0x180039341  sub     eax, 1
0x180039344  jz      short loc_18003935E
0x180039346  sub     eax, 1
0x180039349  jz      short loc_18003935E
0x18003934b  sub     eax, 1
0x18003934e  jz      short loc_18003935E
0x180039350  sub     eax, 1
0x180039353  jz      short loc_18003935E
0x180039355  cmp     eax, 2
0x180039358  jnz     loc_18003970A
0x18003935e  cmp     dword ptr [r13+20h], 4
0x180039363  jb      short loc_18003939D
0x180039365  mov     rdx, [rsp+4E8h+var_490]; struct _INIENVIRONMENT *
0x18003936a  mov     r9, rsi; unsigned __int8 *
0x18003936d  mov     [rsp+4E8h+var_4B0], r12; unsigned __int16 *
0x180039372  mov     r8d, ebp; unsigned int
0x180039375  mov     [rsp+4E8h+var_4B8], r14; unsigned int *
0x18003937a  mov     rcx, rdi; struct _INIDRIVER *
0x18003937d  mov     [rsp+4E8h+var_4C0], r15; unsigned __int16 **
0x180039382  mov     [rsp+4E8h+var_4C8], rbx; unsigned __int8 *
0x180039387  call    ?CopyV4IniDriverToDriverInfo@@YAPEAEPEAU_INIDRIVER@@PEAU_INIENVIRONMENT@@KPEAE2PEAPEAGPEBKPEAG@Z; CopyV4IniDriverToDriverInfo(_INIDRIVER *,_INIENVIRONMENT *,ulong,uchar *,uchar *,ushort * *,ulong const *,ushort *)
0x18003938c  mov     rbx, rax
0x18003938f  test    rax, rax
0x180039392  jz      loc_18003979C
0x180039398  jmp     loc_18003970A
0x18003939d  mov     rcx, [rdi+20h]
0x1800393a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800393a5  inc     rax
0x1800393a8  cmp     [rcx+rax*2], dx
0x1800393ac  jnz     short loc_1800393A5
0x1800393ae  mov     r8, [rsp+4E8h+var_488]
0x1800393b3  lea     rcx, [rsp+4E8h+var_468]
0x1800393bb  mov     [rsp+4E8h+var_4B8], r12
0x1800393c0  mov     edx, 204h
0x1800393c5  mov     [rsp+4E8h+var_4C0], rdi; unsigned int
0x1800393ca  sub     edx, eax
0x1800393cc  mov     [rsp+4E8h+var_4C8], r13; unsigned __int16 *
0x1800393d1  mov     r13, [rsp+4E8h+var_490]
0x1800393d6  mov     r9, r13
0x1800393d9  call    GetDriverVersionDirectory
0x1800393de  lea     ecx, [rax-1]
0x1800393e1  cmp     ecx, 203h
0x1800393e7  ja      short loc_180039460
0x1800393e9  mov     ecx, eax
0x1800393eb  mov     edx, 5Ch ; '\'
0x1800393f0  mov     r12d, 205h
0x1800393f6  mov     [rsp+rcx*2+4E8h+var_468], dx
0x1800393fe  lea     ecx, [rax+1]
0x180039401  mov     rax, [rdi+18h]
0x180039405  mov     [r15], rax
0x180039408  mov     rax, [r13+18h]
0x18003940c  lea     r13, [rsp+4E8h+var_468]
0x180039414  mov     [r15+8], rax
0x180039418  lea     r13, [r13+rcx*2+0]
0x18003941d  mov     r8, [rdi+20h]; unsigned __int16 *
0x180039421  mov     eax, ecx
0x180039423  sub     r12, rax
0x180039426  mov     [rsp+4E8h+var_498], ecx
0x18003942a  mov     rdx, r12; unsigned __int64
0x18003942d  mov     rcx, r13; unsigned __int16 *
0x180039430  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039435  lea     rcx, [rsp+4E8h+var_468]
0x18003943d  call    cs:__imp_AllocSplStr
0x180039443  mov     [rsp+4E8h+var_478], rax
0x180039448  test    rax, rax
0x18003944b  jnz     short loc_180039467
0x18003944d  lea     rdx, aAllocsplstrFai_0; "AllocSplStr failed."
0x180039454  lea     rcx, aCopyinidrivert; "CopyIniDriverToDriverInfo"
0x18003945b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180039460  xor     ebx, ebx
0x180039462  jmp     loc_18003979C
0x180039467  mov     [r15+10h], rax
0x18003946b  mov     rdx, r12; unsigned __int64
0x18003946e  mov     r8, [rdi+30h]; unsigned __int16 *
0x180039472  mov     rcx, r13; unsigned __int16 *
0x180039475  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003947a  lea     rcx, [rsp+4E8h+var_468]
0x180039482  call    cs:__imp_AllocSplStr
0x180039488  xor     ecx, ecx
0x18003948a  mov     [rsp+4E8h+var_470], rax
0x18003948f  test    rax, rax
0x180039492  jz      short loc_18003944D
0x180039494  mov     [r15+18h], rax
0x180039498  mov     r8, [rdi+28h]; unsigned __int16 *
0x18003949c  test    r8, r8
0x18003949f  jz      short loc_1800394D1
0x1800394a1  cmp     [r8], cx
0x1800394a5  jz      short loc_1800394D1
0x1800394a7  mov     rdx, r12; unsigned __int64
0x1800394aa  mov     rcx, r13; unsigned __int16 *
0x1800394ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800394b2  lea     rcx, [rsp+4E8h+var_468]
0x1800394ba  call    cs:__imp_AllocSplStr
0x1800394c0  xor     ecx, ecx
0x1800394c2  mov     [rsp+4E8h+var_4A0], rax
0x1800394c7  test    rax, rax
0x1800394ca  jnz     short loc_1800394D4
0x1800394cc  jmp     loc_18003944D
0x1800394d1  mov     rax, rcx
0x1800394d4  mov     [r15+20h], rax
0x1800394d8  mov     eax, 158h
0x1800394dd  cmp     ebp, 8
0x1800394e0  ja      loc_1800395CF
0x1800394e6  bt      eax, ebp
0x1800394e9  jnb     loc_1800395CF
0x1800394ef  mov     r8, [rdi+38h]; unsigned __int16 *
0x1800394f3  test    r8, r8
0x1800394f6  jz      short loc_18003952B
0x1800394f8  cmp     [r8], cx
0x1800394fc  jz      short loc_18003952B
0x1800394fe  mov     rdx, r12; unsigned __int64
0x180039501  mov     rcx, r13; unsigned __int16 *
0x180039504  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039509  lea     rcx, [rsp+4E8h+var_468]
0x180039511  call    cs:__imp_AllocSplStr
0x180039517  xor     ecx, ecx
0x180039519  mov     [rsp+4E8h+var_4A8], rax
0x18003951e  mov     r8, rax
0x180039521  test    rax, rax
0x180039524  jnz     short loc_180039530
0x180039526  jmp     loc_18003944D
0x18003952b  mov     r8, [rsp+4E8h+var_4A8]
0x180039530  mov     [r15+28h], r8
0x180039534  mov     rax, [rdi+50h]
0x180039538  mov     [r15+30h], rax
0x18003953c  mov     rax, [rdi+58h]
0x180039540  mov     [r15+38h], rax
0x180039544  lea     eax, [rbp-6]
0x180039547  mov     [rsp+4E8h+var_4A8], r8
0x18003954c  test    eax, 0FFFFFFFDh
0x180039551  jnz     short loc_1800395CF
0x180039553  mov     rax, [rdi+70h]
0x180039557  mov     rdx, rcx
0x18003955a  mov     [rsi+58h], rax
0x18003955e  lea     rcx, [r15+40h]
0x180039562  mov     rax, [rdi+78h]
0x180039566  mov     [rsi+60h], rax
0x18003956a  mov     rax, [rdi+rdx*8+80h]
0x180039572  inc     rdx
0x180039575  mov     [rcx], rax
0x180039578  lea     rcx, [rcx+8]
0x18003957c  cmp     rdx, 4
0x180039580  jnz     short loc_18003956A
0x180039582  cmp     ebp, 8
0x180039585  jnz     short loc_1800395CF
0x180039587  mov     rax, [rdi+0A0h]
0x18003958e  mov     [rcx], rax
0x180039591  mov     rax, [rdi+0A8h]
0x180039598  mov     [rcx+8], rax
0x18003959c  mov     rax, [rdi+0C0h]
0x1800395a3  mov     [rcx+10h], rax
0x1800395a7  mov     eax, [rdi+0C8h]
0x1800395ad  mov     [rsi+0A8h], eax
0x1800395b3  mov     rax, [rdi+0D8h]
0x1800395ba  mov     [rsi+0B8h], rax
0x1800395c1  mov     rax, [rdi+0E0h]
0x1800395c8  mov     [rsi+0C0h], rax
0x1800395cf  mov     r9, rbx
0x1800395d2  mov     r8, r14
0x1800395d5  mov     rdx, rsi
0x1800395d8  mov     rcx, r15
0x1800395db  call    cs:__imp_PackStrings
0x1800395e1  xor     ecx, ecx
0x1800395e3  mov     rbx, rax
0x1800395e6  test    rax, rax
0x1800395e9  jnz     short loc_180039603
0x1800395eb  lea     rdx, aPackstringsRan; "PackStrings ran out of space for driver"...
0x1800395f2  lea     rcx, aCopyinidrivert; "CopyIniDriverToDriverInfo"
0x1800395f9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800395fe  jmp     loc_18003979C
0x180039603  cmp     ebp, 8
0x180039606  ja      loc_180039728
0x18003960c  mov     eax, 158h
0x180039611  bt      eax, ebp
0x180039614  jnb     loc_180039728
0x18003961a  cmp     dword ptr [rdi+40h], 2
0x18003961e  jbe     short loc_180039645
0x180039620  cmp     rbx, rsi
0x180039623  jbe     short loc_180039645
0x180039625  mov     r9d, [rsp+4E8h+var_498]; unsigned int
0x18003962a  lea     r8, [rsp+4E8h+var_468]; unsigned __int16 *
0x180039632  mov     rcx, [rdi+48h]; Src
0x180039636  mov     rdx, rbx; unsigned __int8 *
0x180039639  call    ?CopyMultiSzFieldToDriverInfo@@YAPEAEPEAGPEAE0K@Z; CopyMultiSzFieldToDriverInfo(ushort *,uchar *,ushort *,ulong)
0x18003963e  mov     rbx, rax
0x180039641  xor     ecx, ecx
0x180039643  jmp     short loc_180039648
0x180039645  mov     rax, rcx
0x180039648  mov     [rsi+38h], rax
0x18003964c  lea     eax, [rbp-4]
0x18003964f  test    eax, 0FFFFFFF9h
0x180039654  jnz     loc_180039702
0x18003965a  cmp     ebp, 0Ah
0x18003965d  jz      loc_180039702
0x180039663  cmp     dword ptr [rdi+60h], 2
0x180039667  jbe     short loc_180039686
0x180039669  cmp     rbx, rsi
0x18003966c  jbe     short loc_180039686
0x18003966e  mov     rcx, [rdi+68h]; Src
0x180039672  xor     r9d, r9d; unsigned int
0x180039675  xor     r8d, r8d; unsigned __int16 *
0x180039678  mov     rdx, rbx; unsigned __int8 *
0x18003967b  call    ?CopyMultiSzFieldToDriverInfo@@YAPEAEPEAGPEAE0K@Z; CopyMultiSzFieldToDriverInfo(ushort *,uchar *,ushort *,ulong)
0x180039680  mov     rbx, rax
0x180039683  mov     rcx, rax
0x180039686  mov     eax, 50h ; 'P'
0x18003968b  mov     rdx, rsi
0x18003968e  mov     [rax+rdx], rcx
  ... truncated ...
```
