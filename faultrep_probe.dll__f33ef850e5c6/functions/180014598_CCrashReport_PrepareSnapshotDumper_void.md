# CCrashReport::PrepareSnapshotDumper(void)

- ea: `0x180014598`
- end: `0x1800149aa`
- name: `?PrepareSnapshotDumper@CCrashReport@@AEAAJXZ`
- size: `1042`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013b74`
- `0x180013e58`
- `0x18001611c`

## callees

- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000e524`
- `0x18000fb44`
- `0x180014598`
- `0x18003b3a8`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014786`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800147cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800148bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014786`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800147cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800148bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014897`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014897`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180014704`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180014704`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x18001487d`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x18001487d`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x180014756`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x180014756`
- `wer!WerpUnmapProcessViews` at `0x1800147f6`
- `wer!WerpUnmapProcessViews` at `0x1800147f6`
- `wer!WerpInitializeImageCache` at `0x180014694`
- `wer!WerpInitializeImageCache` at `0x180014694`
- `wer!WerpAuxmdFree` at `0x18001488a`
- `wer!WerpAuxmdFree` at `0x18001488a`

## pseudocode

```c
__int64 __fastcall CCrashReport::PrepareSnapshotDumper(CCrashReport *this)
{
  __int64 result; // rax
  int IsNamedEventSet; // eax
  unsigned int v4; // edx
  int v5; // eax
  signed int v6; // esi
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  void *v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  bool *v25; // [rsp+20h] [rbp-69h]
  bool v26; // [rsp+28h] [rbp-61h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-59h] BYREF
  LARGE_INTEGER v28; // [rsp+38h] [rbp-51h] BYREF
  _OWORD v29[9]; // [rsp+40h] [rbp-49h] BYREF
  void *v30; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v31; // [rsp+F8h] [rbp+6Fh] BYREF

  result = *((unsigned int *)this + 1238);
  v30 = 0;
  v31 = 0;
  if ( (int)result < 1 )
    return result;
  if ( !*((_QWORD *)this + 617) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !UtilRegGetDWORD(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
          L"FailSnapshotDumper",
          0,
          v25,
          v26) )
  {
    if ( !*((_DWORD *)this + 2536) )
    {
      if ( (unsigned int)UtilIsNamedEventSet(L"BD") != 1
        || (unsigned int)UtilIsNamedEventSet(L"DF") != 1
        || (IsNamedEventSet = UtilIsNamedEventSet(L"JL"), v4 = 0x8000000, IsNamedEventSet != 1) )
      {
        v4 = 0x2000000;
      }
      v5 = WerpInitializeImageCache((CCrashReport *)((char *)this + 9336), v4);
      v6 = v5;
      *((_DWORD *)this + 2536) = v5 >= 0;
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            141,
            &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
            (unsigned int)v5);
LABEL_18:
        *((_DWORD *)this + 1238) = v6;
        return (unsigned int)v6;
      }
    }
    v7 = *((_QWORD *)this + 617);
    v30 = 0;
    v6 = PssQuerySnapshot(v7, 1, &v30, 8);
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 142;
LABEL_23:
        WPP_SF_d(v8[2], v9, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)v6);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    v6 = PssWalkMarkerCreate(0, &v31);
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 143;
        goto LABEL_23;
      }
LABEL_24:
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_18;
    }
    QueryPerformanceCounter(&PerformanceCount);
    v6 = CCrashReport::DumpProcessDataSegsRegisteredBlocks(this, v30);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_44;
      v11 = 144;
LABEL_43:
      WPP_SF_d(v10[2], v11, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)v6);
LABEL_44:
      v14 = v31;
      *((_DWORD *)this + 1238) = v6;
      PssWalkMarkerFree(v14);
      WerpAuxmdFree((char *)this + 5144);
      DeleteFileW((LPCWSTR)this + 4804);
      return (unsigned int)v6;
    }
    QueryPerformanceCounter(&v28);
    v12 = v30;
    *((_QWORD *)this + 1266) = v28.QuadPart - PerformanceCount.QuadPart;
    v6 = WerpUnmapProcessViews((char *)this + 5112, v12, 3);
    if ( v6 >= 0 )
    {
      v13 = *((unsigned int *)this + 1285);
      if ( !(_DWORD)v13 )
      {
        QueryPerformanceCounter(&PerformanceCount);
        *((_QWORD *)this + 1267) = PerformanceCount.QuadPart - v28.QuadPart;
        memset_0(v29, 0, sizeof(v29));
        v15 = *((_QWORD *)this + 639);
        v16 = v29[0];
        *((_DWORD *)this + 1238) = 0;
        v17 = v29[1];
        *((_OWORD *)this + 310) = v16;
        v18 = v29[2];
        *((_OWORD *)this + 311) = v17;
        v19 = v29[3];
        *((_OWORD *)this + 312) = v18;
        v20 = v29[4];
        *((_OWORD *)this + 313) = v19;
        v21 = v29[5];
        *((_OWORD *)this + 314) = v20;
        v22 = v29[6];
        *((_OWORD *)this + 315) = v21;
        v23 = v29[7];
        *((_OWORD *)this + 316) = v22;
        v24 = v29[8];
        *((_OWORD *)this + 317) = v23;
        *((_OWORD *)this + 318) = v24;
        *((_QWORD *)this + 621) = v15;
        *((_DWORD *)this + 1244) = *((_DWORD *)this + 1280);
        *((_QWORD *)this + 623) = (char *)this + 5144;
        *((_QWORD *)this + 625) = (char *)this + 9336;
        *((_QWORD *)this + 626) = *((_QWORD *)this + 617);
        *((_QWORD *)this + 627) = v31;
        result = 0;
        *((_DWORD *)this + 1240) = 3;
        return result;
      }
      v6 = -2147023672;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        145,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        v13,
        -2147023672);
    }
    v10 = WPP_GLOBAL_Control;
LABEL_40:
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 2) == 0 )
      goto LABEL_44;
    v11 = 146;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
  result = 2147943525LL;
  *((_DWORD *)this + 1238) = -2147023771;
  return result;
}

```

## disassembly

```asm
0x180014598  mov     [rsp-8+arg_10], rbx
0x18001459d  mov     [rsp-8+arg_18], rsi
0x1800145a2  push    rbp
0x1800145a3  push    rdi
0x1800145a4  push    r14
0x1800145a6  lea     rbp, [rsp-47h]
0x1800145ab  sub     rsp, 0D0h
0x1800145b2  mov     eax, [rcx+1358h]
0x1800145b8  mov     edi, 1
0x1800145bd  mov     [rbp+57h+arg_0], 0
0x1800145c5  mov     rbx, rcx
0x1800145c8  mov     [rbp+57h+arg_8], 0
0x1800145d0  cmp     eax, edi
0x1800145d2  jl      loc_18001489F
0x1800145d8  cmp     qword ptr [rcx+1348h], 0
0x1800145e0  jnz     short loc_1800145E7
0x1800145e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800145e7  xor     r9d, r9d; unsigned int
0x1800145ea  lea     r8, aFailsnapshotdu; "FailSnapshotDumper"
0x1800145f1  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800145f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800145ff  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180014604  test    eax, eax
0x180014606  jz      short loc_180014646
0x180014608  mov     rcx, cs:WPP_GLOBAL_Control
0x18001460f  lea     rdi, WPP_GLOBAL_Control
0x180014616  cmp     rcx, rdi
0x180014619  jz      short loc_180014636
0x18001461b  test    byte ptr [rcx+1Ch], 4
0x18001461f  jz      short loc_180014636
0x180014621  mov     rcx, [rcx+10h]
0x180014625  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001462c  mov     edx, 8Ch
0x180014631  call    WPP_SF_
0x180014636  mov     eax, 80070465h
0x18001463b  mov     [rbx+1358h], eax
0x180014641  jmp     loc_18001489F
0x180014646  cmp     dword ptr [rbx+27A0h], 0
0x18001464d  jnz     loc_1800146E9
0x180014653  lea     rcx, aBd_0; "BD"
0x18001465a  call    UtilIsNamedEventSet
0x18001465f  cmp     eax, edi
0x180014661  jnz     short loc_180014688
0x180014663  lea     rcx, aDf_0; "DF"
0x18001466a  call    UtilIsNamedEventSet
0x18001466f  cmp     eax, edi
0x180014671  jnz     short loc_180014688
0x180014673  lea     rcx, aJl; "JL"
0x18001467a  call    UtilIsNamedEventSet
0x18001467f  mov     edx, 8000000h
0x180014684  cmp     eax, edi
0x180014686  jz      short loc_18001468D
0x180014688  mov     edx, 2000000h
0x18001468d  lea     rcx, [rbx+2478h]
0x180014694  call    cs:__imp_?WerpInitializeImageCache@@YAJPEAUWERP_IMAGE_CACHE@@K@Z; WerpInitializeImageCache(WERP_IMAGE_CACHE *,ulong)
0x18001469a  mov     ecx, eax
0x18001469c  mov     esi, eax
0x18001469e  not     ecx
0x1800146a0  shr     ecx, 1Fh
0x1800146a3  mov     [rbx+27A0h], ecx
0x1800146a9  test    eax, eax
0x1800146ab  jns     short loc_1800146E9
0x1800146ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146b4  lea     rdi, WPP_GLOBAL_Control
0x1800146bb  cmp     rcx, rdi
0x1800146be  jz      short loc_1800146DE
0x1800146c0  test    byte ptr [rcx+1Ch], 2
0x1800146c4  jz      short loc_1800146DE
0x1800146c6  mov     rcx, [rcx+10h]
0x1800146ca  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x1800146d1  mov     edx, 8Dh
0x1800146d6  mov     r9d, eax
0x1800146d9  call    WPP_SF_d
0x1800146de  mov     [rbx+1358h], esi
0x1800146e4  jmp     loc_18001489D
0x1800146e9  mov     rcx, [rbx+1348h]
0x1800146f0  lea     r8, [rbp+57h+arg_0]
0x1800146f4  mov     r9d, 8
0x1800146fa  mov     [rbp+57h+arg_0], 0
0x180014702  mov     edx, edi
0x180014704  call    cs:__imp_PssQuerySnapshot
0x18001470a  mov     esi, eax
0x18001470c  test    eax, eax
0x18001470e  jz      short loc_180014750
0x180014710  mov     rcx, cs:WPP_GLOBAL_Control
0x180014717  lea     rdi, WPP_GLOBAL_Control
0x18001471e  cmp     rcx, rdi
0x180014721  jz      short loc_180014741
0x180014723  test    byte ptr [rcx+1Ch], 2
0x180014727  jz      short loc_180014741
0x180014729  mov     edx, 8Eh
0x18001472e  mov     rcx, [rcx+10h]
0x180014732  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014739  mov     r9d, esi
0x18001473c  call    WPP_SF_d
0x180014741  test    esi, esi
0x180014743  jle     short loc_1800146DE
0x180014745  movzx   esi, si
0x180014748  or      esi, 80070000h
0x18001474e  jmp     short loc_1800146DE
0x180014750  lea     rdx, [rbp+57h+arg_8]
0x180014754  xor     ecx, ecx
0x180014756  call    cs:__imp_PssWalkMarkerCreate
0x18001475c  mov     esi, eax
0x18001475e  test    eax, eax
0x180014760  jz      short loc_180014782
0x180014762  mov     rcx, cs:WPP_GLOBAL_Control
0x180014769  lea     rdi, WPP_GLOBAL_Control
0x180014770  cmp     rcx, rdi
0x180014773  jz      short loc_180014741
0x180014775  test    byte ptr [rcx+1Ch], 2
0x180014779  jz      short loc_180014741
0x18001477b  mov     edx, 8Fh
0x180014780  jmp     short loc_18001472E
0x180014782  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180014786  call    cs:__imp_QueryPerformanceCounter
0x18001478c  mov     rdx, [rbp+57h+arg_0]; void *
0x180014790  mov     rcx, rbx; this
0x180014793  call    ?DumpProcessDataSegsRegisteredBlocks@CCrashReport@@AEAAJPEAX@Z; CCrashReport::DumpProcessDataSegsRegisteredBlocks(void *)
0x180014798  mov     esi, eax
0x18001479a  test    eax, eax
0x18001479c  jns     short loc_1800147C9
0x18001479e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a5  lea     rdi, WPP_GLOBAL_Control
0x1800147ac  cmp     rcx, rdi
0x1800147af  jz      loc_180014873
0x1800147b5  test    byte ptr [rcx+1Ch], 2
0x1800147b9  jz      loc_180014873
0x1800147bf  mov     edx, 90h
0x1800147c4  jmp     loc_180014860
0x1800147c9  lea     rcx, [rbp+57h+var_A8]; lpPerformanceCount
0x1800147cd  call    cs:__imp_QueryPerformanceCounter
0x1800147d3  mov     rax, qword ptr [rbp+57h+var_A8]
0x1800147d7  lea     r14, [rbx+13F8h]
0x1800147de  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800147e2  mov     r8d, 3
0x1800147e8  mov     rdx, [rbp+57h+arg_0]
0x1800147ec  mov     rcx, r14
0x1800147ef  mov     [rbx+2790h], rax
0x1800147f6  call    cs:__imp_WerpUnmapProcessViews
0x1800147fc  lea     rdi, WPP_GLOBAL_Control
0x180014803  mov     esi, eax
0x180014805  test    eax, eax
0x180014807  js      short loc_180014849
0x180014809  mov     r9d, [rbx+1414h]
0x180014810  test    r9d, r9d
0x180014813  jz      loc_1800148B7
0x180014819  mov     esi, 800704C8h
0x18001481e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014825  cmp     rcx, rdi
0x180014828  jz      short loc_180014873
0x18001482a  test    byte ptr [rcx+1Ch], 2
0x18001482e  jz      short loc_180014850
0x180014830  mov     rcx, [rcx+10h]
0x180014834  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001483b  mov     edx, 91h
0x180014840  mov     dword ptr [rsp+0E0h+var_C0], esi
0x180014844  call    WPP_SF_Dd
0x180014849  mov     rcx, cs:WPP_GLOBAL_Control
0x180014850  cmp     rcx, rdi
0x180014853  jz      short loc_180014873
0x180014855  test    byte ptr [rcx+1Ch], 2
0x180014859  jz      short loc_180014873
0x18001485b  mov     edx, 92h
0x180014860  mov     rcx, [rcx+10h]
0x180014864  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001486b  mov     r9d, esi
0x18001486e  call    WPP_SF_d
0x180014873  mov     rcx, [rbp+57h+arg_8]
0x180014877  mov     [rbx+1358h], esi
0x18001487d  call    cs:__imp_PssWalkMarkerFree
0x180014883  lea     rcx, [rbx+1418h]
0x18001488a  call    cs:__imp_WerpAuxmdFree
0x180014890  lea     rcx, [rbx+2588h]; lpFileName
0x180014897  call    cs:__imp_DeleteFileW
0x18001489d  mov     eax, esi
0x18001489f  lea     r11, [rsp+0E0h+var_10]
0x1800148a7  mov     rbx, [r11+30h]
0x1800148ab  mov     rsi, [r11+38h]
0x1800148af  mov     rsp, r11
0x1800148b2  pop     r14
0x1800148b4  pop     rdi
0x1800148b5  pop     rbp
0x1800148b6  retn
0x1800148b7  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800148bb  call    cs:__imp_QueryPerformanceCounter
0x1800148c1  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800148c5  lea     rcx, [rbp+57h+var_A0]; void *
0x1800148c9  sub     rax, qword ptr [rbp+57h+var_A8]
0x1800148cd  xor     edx, edx; Val
0x1800148cf  mov     r8d, 90h; Size
0x1800148d5  mov     [rbx+2798h], rax
0x1800148dc  call    memset_0
0x1800148e1  mov     rax, [r14]
0x1800148e4  movups  xmm0, [rbp+57h+var_A0]
0x1800148e8  mov     dword ptr [rbx+1358h], 0
0x1800148f2  movups  xmm1, [rbp+57h+var_90]
0x1800148f6  movups  xmmword ptr [rbx+1360h], xmm0
0x1800148fd  movups  xmm0, [rbp+57h+var_80]
0x180014901  movups  xmmword ptr [rbx+1370h], xmm1
0x180014908  movups  xmm1, [rbp+57h+var_70]
0x18001490c  movups  xmmword ptr [rbx+1380h], xmm0
0x180014913  movups  xmm0, [rbp+57h+var_60]
0x180014917  movups  xmmword ptr [rbx+1390h], xmm1
0x18001491e  movups  xmm1, [rbp+57h+var_50]
0x180014922  movups  xmmword ptr [rbx+13A0h], xmm0
0x180014929  movups  xmm0, [rbp+57h+var_40]
0x18001492d  movups  xmmword ptr [rbx+13B0h], xmm1
0x180014934  movups  xmm1, [rbp+57h+var_30]
0x180014938  movups  xmmword ptr [rbx+13C0h], xmm0
0x18001493f  movups  xmm0, [rbp+57h+var_20]
0x180014943  movups  xmmword ptr [rbx+13D0h], xmm1
0x18001494a  movups  xmmword ptr [rbx+13E0h], xmm0
0x180014951  mov     [rbx+1368h], rax
0x180014958  mov     eax, [rbx+1400h]
0x18001495e  mov     [rbx+1370h], eax
0x180014964  lea     rax, [rbx+1418h]
0x18001496b  mov     [rbx+1378h], rax
0x180014972  lea     rax, [rbx+2478h]
0x180014979  mov     [rbx+1388h], rax
0x180014980  mov     rax, [rbx+1348h]
0x180014987  mov     [rbx+1390h], rax
0x18001498e  mov     rax, [rbp+57h+arg_8]
0x180014992  mov     [rbx+1398h], rax
0x180014999  xor     eax, eax
0x18001499b  mov     dword ptr [rbx+1360h], 3
0x1800149a5  jmp     loc_18001489F
```
