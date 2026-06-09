# PoWdiLogTelemetryData

- ea: `0x1800032c0`
- end: `0x1800039a7`
- name: `PoWdiLogTelemetryData`
- size: `1767`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180004710`

## callees

- `0x18000113c`
- `0x180001c40`
- `0x180001d10`
- `0x1800022dc`
- `0x180002e50`
- `0x1800032c0`
- `0x180004902`
- `0x180004930`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180003424`
- `msvcrt!swprintf_s` at `0x180003424`
- `ntdll!RtlGetNativeSystemInformation` at `0x18000354f`
- `ntdll!RtlGetNativeSystemInformation` at `0x18000354f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000393f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000395a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003975`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000393f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000395a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000394b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000394b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003966`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800033c4`
- `wdi!WdiGetLoggerSnapshotPath` at `0x1800033c4`
- `wdi!WdiSetFeedback` at `0x18000351f`
- `wdi!WdiSetFeedback` at `0x18000351f`

## pseudocode

```c
__int64 __fastcall PoWdiLogTelemetryData(__int64 a1, struct _EVENT_RECORD *a2)
{
  int LoggerSnapshotPath; // ebx
  int v5; // edi
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // esi
  __int64 v12; // r9
  __int64 v13; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+5Ch] [rbp-A4h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  int v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+6Ch] [rbp-94h] BYREF
  int v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+84h] [rbp-7Ch]
  BOOL v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+8Ch] [rbp-74h]
  int v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+94h] [rbp-6Ch]
  int v40; // [rsp+98h] [rbp-68h]
  unsigned int v41; // [rsp+9Ch] [rbp-64h]
  int v42; // [rsp+A0h] [rbp-60h]
  int v43; // [rsp+A4h] [rbp-5Ch]
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  int v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B4h] [rbp-4Ch]
  int v48; // [rsp+B8h] [rbp-48h]
  unsigned int v49; // [rsp+BCh] [rbp-44h]
  unsigned int v50; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem; // [rsp+D0h] [rbp-30h]
  LPVOID v52; // [rsp+E0h] [rbp-20h]
  LPVOID v53; // [rsp+F0h] [rbp-10h]
  BYTE v54[8]; // [rsp+100h] [rbp+0h] BYREF
  int v55; // [rsp+108h] [rbp+8h]
  int v56; // [rsp+10Ch] [rbp+Ch]
  int v57; // [rsp+110h] [rbp+10h]
  unsigned int v58; // [rsp+114h] [rbp+14h]
  unsigned int v59; // [rsp+118h] [rbp+18h]
  unsigned int v60; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v61; // [rsp+120h] [rbp+20h]
  unsigned int v62; // [rsp+124h] [rbp+24h]
  unsigned int v63; // [rsp+128h] [rbp+28h]
  unsigned int v64; // [rsp+12Ch] [rbp+2Ch]
  unsigned int v65; // [rsp+130h] [rbp+30h]
  unsigned int v66; // [rsp+134h] [rbp+34h]
  unsigned int v67; // [rsp+138h] [rbp+38h]
  int v68; // [rsp+13Ch] [rbp+3Ch]
  int v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+150h] [rbp+50h] BYREF
  __int64 v71; // [rsp+158h] [rbp+58h] BYREF
  __int64 v72; // [rsp+160h] [rbp+60h] BYREF
  __int64 v73; // [rsp+168h] [rbp+68h] BYREF
  __int64 v74; // [rsp+170h] [rbp+70h] BYREF
  __int64 v75; // [rsp+178h] [rbp+78h] BYREF
  __int64 v76; // [rsp+180h] [rbp+80h] BYREF
  __int64 v77; // [rsp+188h] [rbp+88h] BYREF
  __int64 v78; // [rsp+190h] [rbp+90h] BYREF
  __int64 v79; // [rsp+198h] [rbp+98h] BYREF
  __int64 v80; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v81; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v82; // [rsp+1B0h] [rbp+B0h] BYREF
  char v83[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v84; // [rsp+1C8h] [rbp+C8h]
  char v85[32]; // [rsp+200h] [rbp+100h] BYREF
  int *v86; // [rsp+220h] [rbp+120h]
  __int64 v87; // [rsp+228h] [rbp+128h]
  int *v88; // [rsp+230h] [rbp+130h]
  __int64 v89; // [rsp+238h] [rbp+138h]
  __int64 *v90; // [rsp+240h] [rbp+140h]
  __int64 v91; // [rsp+248h] [rbp+148h]
  int *v92; // [rsp+250h] [rbp+150h]
  __int64 v93; // [rsp+258h] [rbp+158h]
  int *v94; // [rsp+260h] [rbp+160h]
  __int64 v95; // [rsp+268h] [rbp+168h]
  int *v96; // [rsp+270h] [rbp+170h]
  __int64 v97; // [rsp+278h] [rbp+178h]
  int *v98; // [rsp+280h] [rbp+180h]
  __int64 v99; // [rsp+288h] [rbp+188h]
  int *v100; // [rsp+290h] [rbp+190h]
  __int64 v101; // [rsp+298h] [rbp+198h]
  int *v102; // [rsp+2A0h] [rbp+1A0h]
  __int64 v103; // [rsp+2A8h] [rbp+1A8h]
  int *v104; // [rsp+2B0h] [rbp+1B0h]
  __int64 v105; // [rsp+2B8h] [rbp+1B8h]
  int *v106; // [rsp+2C0h] [rbp+1C0h]
  __int64 v107; // [rsp+2C8h] [rbp+1C8h]
  int *v108; // [rsp+2D0h] [rbp+1D0h]
  __int64 v109; // [rsp+2D8h] [rbp+1D8h]
  __int64 *v110; // [rsp+2E0h] [rbp+1E0h]
  __int64 v111; // [rsp+2E8h] [rbp+1E8h]
  __int64 *v112; // [rsp+2F0h] [rbp+1F0h]
  __int64 v113; // [rsp+2F8h] [rbp+1F8h]
  __int64 *v114; // [rsp+300h] [rbp+200h]
  __int64 v115; // [rsp+308h] [rbp+208h]
  __int64 *v116; // [rsp+310h] [rbp+210h]
  __int64 v117; // [rsp+318h] [rbp+218h]
  __int64 *v118; // [rsp+320h] [rbp+220h]
  __int64 v119; // [rsp+328h] [rbp+228h]
  __int64 *v120; // [rsp+330h] [rbp+230h]
  __int64 v121; // [rsp+338h] [rbp+238h]
  __int64 *v122; // [rsp+340h] [rbp+240h]
  __int64 v123; // [rsp+348h] [rbp+248h]
  __int64 *v124; // [rsp+350h] [rbp+250h]
  __int64 v125; // [rsp+358h] [rbp+258h]
  __int64 *v126; // [rsp+360h] [rbp+260h]
  __int64 v127; // [rsp+368h] [rbp+268h]
  __int64 *v128; // [rsp+370h] [rbp+270h]
  __int64 v129; // [rsp+378h] [rbp+278h]
  __int64 *v130; // [rsp+380h] [rbp+280h]
  __int64 v131; // [rsp+388h] [rbp+288h]
  __int64 *v132; // [rsp+390h] [rbp+290h]
  __int64 v133; // [rsp+398h] [rbp+298h]
  __int64 *v134; // [rsp+3A0h] [rbp+2A0h]
  __int64 v135; // [rsp+3A8h] [rbp+2A8h]
  int *v136; // [rsp+3B0h] [rbp+2B0h]
  __int64 v137; // [rsp+3B8h] [rbp+2B8h]
  int *v138; // [rsp+3C0h] [rbp+2C0h]
  __int64 v139; // [rsp+3C8h] [rbp+2C8h]
  int *v140; // [rsp+3D0h] [rbp+2D0h]
  __int64 v141; // [rsp+3D8h] [rbp+2D8h]
  int *v142; // [rsp+3E0h] [rbp+2E0h]
  __int64 v143; // [rsp+3E8h] [rbp+2E8h]
  char v144[32]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 *v145; // [rsp+410h] [rbp+310h]
  __int64 v146; // [rsp+418h] [rbp+318h]
  int *v147; // [rsp+420h] [rbp+320h]
  __int64 v148; // [rsp+428h] [rbp+328h]
  int *v149; // [rsp+430h] [rbp+330h]
  __int64 v150; // [rsp+438h] [rbp+338h]
  wchar_t *v151; // [rsp+440h] [rbp+340h]
  int v152; // [rsp+448h] [rbp+348h]
  int v153; // [rsp+44Ch] [rbp+34Ch]
  wchar_t Buffer[16]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v155[528]; // [rsp+470h] [rbp+370h] BYREF

  memset_0(v83, 0, 0x40u);
  v18 = 0;
  memset_0(&v34, 0, 0xC8u);
  LoggerSnapshotPath = 0;
  v5 = 0;
  if ( !PoWdiGetProperty(a2, (ULONGLONG)L"Status", v6, (BYTE *)&v34, 4u, (ULONG *)&v18)
    && (_DWORD)v18 == 4
    && !PoWdiGetProperty(a2, (ULONGLONG)L"Time", v7, v54, 8u, (ULONG *)&v18)
    && (_DWORD)v18 == 8 )
  {
    v18 = 0x10400000008LL;
    v36 = v34 >= 0;
    LoggerSnapshotPath = WdiGetLoggerSnapshotPath(a1, 0, v155, (char *)&v18 + 4);
    if ( LoggerSnapshotPath < 0 || HIDWORD(v18) > 0x104 )
    {
      LoggerSnapshotPath = 0;
    }
    else
    {
      v5 = 8;
      if ( (unsigned int)PoWdiCollectData(v155, a2, &v34) )
      {
        PoWdiCollectWakeSourceInfo(&v34);
        v35 |= 0x4000u;
        swprintf_s(Buffer, 9u, L"%08X", (unsigned int)v34);
        if ( (unsigned int)dword_1800091A8 > 5
          && (qword_1800091B8 & 0x400000000000LL) != 0
          && (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
        {
          LODWORD(v18) = v36;
          v145 = &v18;
          v19 = v37;
          v147 = &v19;
          v20 = v35;
          v149 = &v20;
          v10 = -1;
          v146 = 4;
          v148 = 4;
          v150 = 4;
          do
            ++v10;
          while ( Buffer[v10] );
          v153 = 0;
          v152 = 2 * v10 + 2;
          v151 = Buffer;
          tlgWriteTransfer_EtwEventWriteTransfer((__int64)Buffer, byte_180006E35, v8, v9, 6, (__int64)v144);
        }
        if ( v34 >= 0 )
        {
          v5 = 31;
          PoWdiLogResumeEvent(&v34);
          v11 = 0;
          if ( (int)RtlGetNativeSystemInformation(0, v83, 64, 0) >= 0 )
            v11 = v44 * (v84 >> 10);
          if ( v38 == 5 )
            v5 = 63;
          v13 = v60 + v61 + v62;
          if ( (unsigned int)dword_1800091A8 > 5
            && (qword_1800091B8 & 0x400000000000LL) != 0
            && (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
          {
            v20 = v39;
            v86 = &v20;
            v19 = v40;
            v88 = &v19;
            LODWORD(v18) = v43;
            v90 = &v18;
            v21 = v42;
            v92 = &v21;
            v94 = &v22;
            v23 = v45;
            v96 = &v23;
            v98 = (int *)&v24;
            v25 = v37;
            v100 = &v25;
            v26 = v35;
            v102 = &v26;
            v27 = v41 + v46;
            v104 = &v27;
            v106 = &v28;
            v29 = v48;
            v108 = &v29;
            v82 = v49;
            v110 = &v82;
            v70 = v50;
            v112 = &v70;
            v71 = v58;
            v114 = &v71;
            v72 = v59;
            v116 = &v72;
            v73 = v64;
            v87 = 4;
            v89 = 4;
            v91 = 4;
            v93 = 4;
            v22 = v46;
            v95 = 4;
            v97 = 4;
            v24 = v41;
            v99 = 4;
            v101 = 4;
            v103 = 4;
            v105 = 4;
            v28 = v11;
            v107 = 4;
            v109 = 4;
            v111 = 8;
            v113 = 8;
            v115 = 8;
            v117 = 8;
            v119 = 8;
            v118 = &v73;
            v74 = (unsigned int)v13;
            v120 = &v74;
            v75 = v60;
            v122 = &v75;
            v76 = v61;
            v124 = &v76;
            v77 = v62;
            v126 = &v77;
            v78 = v65;
            v128 = &v78;
            v79 = v63;
            v130 = &v79;
            v80 = v66;
            v132 = &v80;
            v81 = v67;
            v134 = &v81;
            v30 = v38;
            v136 = &v30;
            v31 = v68;
            v138 = &v31;
            v32 = v69;
            v140 = &v32;
            v33 = v47;
            v142 = &v33;
            v121 = 8;
            v123 = 8;
            v125 = 8;
            v127 = 8;
            v129 = 8;
            v131 = 8;
            v133 = 8;
            v135 = 8;
            v137 = 4;
            v139 = 4;
            v141 = 4;
            v143 = 4;
            tlgWriteTransfer_EtwEventWriteTransfer(v41, byte_180006F51, v13, v12, 31, (__int64)v85);
          }
        }
        else
        {
          v5 = 15;
          WdiSetFeedback(a1, 1);
        }
      }
    }
  }
  if ( v56 && (~v55 & v5) != 0 )
    LoggerSnapshotPath = 1168;
  if ( v57 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v52 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v52);
  }
  if ( v53 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v53);
  }
  return (unsigned int)LoggerSnapshotPath;
}

```

## disassembly

```asm
0x1800032c0  mov     [rsp-8+arg_10], rbx
0x1800032c5  push    rbp
0x1800032c6  push    rsi
0x1800032c7  push    rdi
0x1800032c8  push    r12
0x1800032ca  push    r13
0x1800032cc  push    r14
0x1800032ce  push    r15
0x1800032d0  lea     rbp, [rsp-590h]
0x1800032d8  sub     rsp, 690h
0x1800032df  mov     rax, cs:__security_cookie
0x1800032e6  xor     rax, rsp
0x1800032e9  mov     [rbp+5C0h+var_40], rax
0x1800032f0  mov     rsi, rdx
0x1800032f3  mov     r14, rcx
0x1800032f6  xor     edx, edx; Val
0x1800032f8  lea     rcx, [rbp+5C0h+var_500]; void *
0x1800032ff  lea     r8d, [rdx+40h]; Size
0x180003303  call    memset_0
0x180003308  xor     r15d, r15d
0x18000330b  lea     rcx, [rbp+5C0h+var_640]; void *
0x18000330f  xor     edx, edx; Val
0x180003311  mov     dword ptr [rsp+6C0h+var_690+4], r15d
0x180003316  mov     r8d, 0C8h; Size
0x18000331c  mov     dword ptr [rsp+6C0h+var_690], r15d
0x180003321  call    memset_0
0x180003326  lea     rax, [rsp+6C0h+var_690]
0x18000332b  mov     rcx, rsi; pEvent
0x18000332e  mov     [rsp+6C0h+var_698], rax; __int64
0x180003333  lea     r12d, [r15+4]
0x180003337  lea     r9, [rbp+5C0h+var_640]
0x18000333b  mov     [rsp+6C0h+var_6A0], r12d; int
0x180003340  lea     rdx, aStatus; "Status"
0x180003347  mov     ebx, r15d
0x18000334a  mov     edi, r15d
0x18000334d  call    PoWdiGetProperty
0x180003352  test    eax, eax
0x180003354  jnz     loc_180003915
0x18000335a  cmp     dword ptr [rsp+6C0h+var_690], r12d
0x18000335f  jnz     loc_180003915
0x180003365  lea     rax, [rsp+6C0h+var_690]
0x18000336a  mov     rcx, rsi; pEvent
0x18000336d  mov     [rsp+6C0h+var_698], rax; __int64
0x180003372  lea     r13d, [r15+8]
0x180003376  lea     r9, [rbp+5C0h+var_5C0]
0x18000337a  mov     [rsp+6C0h+var_6A0], r13d; int
0x18000337f  lea     rdx, aTime; "Time"
0x180003386  call    PoWdiGetProperty
0x18000338b  test    eax, eax
0x18000338d  jnz     loc_180003915
0x180003393  cmp     dword ptr [rsp+6C0h+var_690], r13d
0x180003398  jnz     loc_180003915
0x18000339e  cmp     [rbp+5C0h+var_640], r15d
0x1800033a2  lea     r9, [rsp+6C0h+var_690+4]
0x1800033a7  mov     eax, r15d
0x1800033aa  mov     dword ptr [rsp+6C0h+var_690+4], 104h
0x1800033b2  setnl   al
0x1800033b5  lea     r8, [rbp+5C0h+var_250]
0x1800033bc  xor     edx, edx
0x1800033be  mov     [rbp+5C0h+var_638], eax
0x1800033c1  mov     rcx, r14
0x1800033c4  call    cs:__imp_WdiGetLoggerSnapshotPath
0x1800033ca  mov     ebx, eax
0x1800033cc  test    eax, eax
0x1800033ce  js      loc_180003912
0x1800033d4  cmp     dword ptr [rsp+6C0h+var_690+4], 104h
0x1800033dc  ja      loc_180003912
0x1800033e2  lea     r8, [rbp+5C0h+var_640]
0x1800033e6  mov     rdx, rsi
0x1800033e9  lea     rcx, [rbp+5C0h+var_250]
0x1800033f0  mov     edi, r13d
0x1800033f3  call    PoWdiCollectData
0x1800033f8  test    eax, eax
0x1800033fa  jz      loc_180003915
0x180003400  lea     rcx, [rbp+5C0h+var_640]
0x180003404  call    PoWdiCollectWakeSourceInfo
0x180003409  mov     r9d, [rbp+5C0h+var_640]
0x18000340d  lea     r8, a08x; "%08X"
0x180003414  bts     [rbp+5C0h+var_63C], 0Eh
0x180003419  lea     edx, [r15+9]; BufferCount
0x18000341d  lea     rcx, [rbp+5C0h+Buffer]; Buffer
0x180003424  call    cs:__imp_swprintf_s
0x18000342a  mov     eax, cs:dword_1800091A8
0x180003430  mov     r13, 400000000000h
0x18000343a  cmp     eax, 5
0x18000343d  jbe     loc_18000350E
0x180003443  mov     rcx, cs:qword_1800091C0
0x18000344a  mov     rax, cs:qword_1800091B8
0x180003451  test    r13, rax
0x180003454  jz      loc_18000350E
0x18000345a  mov     rax, rcx
0x18000345d  and     rax, r13
0x180003460  cmp     rax, rcx
0x180003463  jnz     loc_18000350E
0x180003469  mov     eax, [rbp+5C0h+var_638]
0x18000346c  lea     rcx, [rbp+5C0h+Buffer]
0x180003473  mov     dword ptr [rsp+6C0h+var_690], eax
0x180003477  lea     rax, [rsp+6C0h+var_690]
0x18000347c  mov     [rbp+5C0h+var_2B0], rax
0x180003483  mov     eax, [rbp+5C0h+var_634]
0x180003486  mov     [rsp+6C0h+var_688], eax
0x18000348a  lea     rax, [rsp+6C0h+var_688]
0x18000348f  mov     [rbp+5C0h+var_2A0], rax
0x180003496  mov     eax, [rbp+5C0h+var_63C]
0x180003499  mov     [rsp+6C0h+var_684], eax
0x18000349d  lea     rax, [rsp+6C0h+var_684]
0x1800034a2  mov     [rbp+5C0h+var_290], rax
0x1800034a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034ad  mov     [rbp+5C0h+var_2A8], r12
0x1800034b4  mov     [rbp+5C0h+var_298], r12
0x1800034bb  mov     [rbp+5C0h+var_288], r12
0x1800034c2  inc     rax
0x1800034c5  cmp     [rcx+rax*2], r15w
0x1800034ca  jnz     short loc_1800034C2
0x1800034cc  lea     eax, ds:2[rax*2]
0x1800034d3  mov     [rbp+5C0h+var_274], r15d
0x1800034da  mov     [rbp+5C0h+var_278], eax
0x1800034e0  lea     rcx, [rbp+5C0h+Buffer]
0x1800034e7  lea     rax, [rbp+5C0h+var_2D0]
0x1800034ee  mov     [rbp+5C0h+var_280], rcx
0x1800034f5  mov     [rsp+6C0h+var_698], rax
0x1800034fa  lea     rdx, byte_180006E35
0x180003501  mov     [rsp+6C0h+var_6A0], 6
0x180003509  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000350e  cmp     [rbp+5C0h+var_640], r15d
0x180003512  jge     short loc_18000352A
0x180003514  mov     edi, 0Fh
0x180003519  mov     rcx, r14
0x18000351c  lea     edx, [rdi-0Eh]
0x18000351f  call    cs:__imp_WdiSetFeedback
0x180003525  jmp     loc_180003915
0x18000352a  mov     r14d, 1Fh
0x180003530  lea     rcx, [rbp+5C0h+var_640]
0x180003534  mov     edi, r14d
0x180003537  call    PoWdiLogResumeEvent
0x18000353c  xor     r9d, r9d
0x18000353f  lea     r8d, [r14+21h]
0x180003543  lea     rdx, [rbp+5C0h+var_500]
0x18000354a  xor     ecx, ecx
0x18000354c  mov     esi, r15d
0x18000354f  call    cs:__imp_RtlGetNativeSystemInformation
0x180003555  test    eax, eax
0x180003557  js      short loc_180003566
0x180003559  mov     esi, [rbp+5C0h+var_4F8]
0x18000355f  shr     esi, 0Ah
0x180003562  imul    esi, [rbp+5C0h+var_618]
0x180003566  cmp     [rbp+5C0h+var_630], 5
0x18000356a  mov     eax, 3Fh ; '?'
0x18000356f  mov     r8d, [rbp+5C0h+var_59C]
0x180003573  cmovz   edi, eax
0x180003576  add     r8d, [rbp+5C0h+var_5A0]
0x18000357a  add     r8d, [rbp+5C0h+var_5A4]
0x18000357e  mov     eax, cs:dword_1800091A8
0x180003584  cmp     eax, 5
0x180003587  jbe     loc_180003915
0x18000358d  mov     rcx, cs:qword_1800091C0
0x180003594  mov     rax, cs:qword_1800091B8
0x18000359b  test    r13, rax
0x18000359e  jz      loc_180003915
0x1800035a4  mov     rax, rcx
0x1800035a7  and     rax, r13
0x1800035aa  cmp     rax, rcx
0x1800035ad  jnz     loc_180003915
0x1800035b3  mov     eax, [rbp+5C0h+var_62C]
0x1800035b6  mov     edx, [rbp+5C0h+var_610]
0x1800035b9  mov     ecx, [rbp+5C0h+var_624]
0x1800035bc  mov     [rsp+6C0h+var_684], eax
0x1800035c0  lea     rax, [rsp+6C0h+var_684]
0x1800035c5  mov     [rbp+5C0h+var_4A0], rax
0x1800035cc  mov     eax, [rbp+5C0h+var_628]
0x1800035cf  mov     [rsp+6C0h+var_688], eax
0x1800035d3  lea     rax, [rsp+6C0h+var_688]
0x1800035d8  mov     [rbp+5C0h+var_490], rax
0x1800035df  mov     eax, [rbp+5C0h+var_61C]
0x1800035e2  mov     dword ptr [rsp+6C0h+var_690], eax
0x1800035e6  lea     rax, [rsp+6C0h+var_690]
0x1800035eb  mov     [rbp+5C0h+var_480], rax
0x1800035f2  mov     eax, [rbp+5C0h+var_620]
0x1800035f5  mov     [rsp+6C0h+var_680], eax
0x1800035f9  lea     rax, [rsp+6C0h+var_680]
0x1800035fe  mov     [rbp+5C0h+var_470], rax
0x180003605  lea     rax, [rsp+6C0h+var_67C]
0x18000360a  mov     [rbp+5C0h+var_460], rax
0x180003611  mov     eax, [rbp+5C0h+var_614]
0x180003614  mov     [rsp+6C0h+var_678], eax
0x180003618  lea     rax, [rsp+6C0h+var_678]
0x18000361d  mov     [rbp+5C0h+var_450], rax
0x180003624  lea     rax, [rsp+6C0h+var_674]
0x180003629  mov     [rbp+5C0h+var_440], rax
0x180003630  mov     eax, [rbp+5C0h+var_634]
0x180003633  mov     [rsp+6C0h+var_670], eax
0x180003637  lea     rax, [rsp+6C0h+var_670]
0x18000363c  mov     [rbp+5C0h+var_430], rax
0x180003643  mov     eax, [rbp+5C0h+var_63C]
0x180003646  mov     [rsp+6C0h+var_66C], eax
0x18000364a  lea     rax, [rsp+6C0h+var_66C]
0x18000364f  mov     [rbp+5C0h+var_420], rax
0x180003656  lea     eax, [rcx+rdx]
0x180003659  mov     [rsp+6C0h+var_668], eax
0x18000365d  lea     rax, [rsp+6C0h+var_668]
0x180003662  mov     [rbp+5C0h+var_410], rax
0x180003669  lea     rax, [rsp+6C0h+var_664]
0x18000366e  mov     [rbp+5C0h+var_400], rax
0x180003675  mov     eax, [rbp+5C0h+var_608]
0x180003678  mov     [rsp+6C0h+var_660], eax
0x18000367c  lea     rax, [rsp+6C0h+var_660]
0x180003681  mov     [rbp+5C0h+var_3F0], rax
0x180003688  mov     eax, [rbp+5C0h+var_604]
0x18000368b  mov     [rbp+5C0h+var_510], rax
0x180003692  lea     rax, [rbp+5C0h+var_510]
0x180003699  mov     [rbp+5C0h+var_3E0], rax
0x1800036a0  mov     eax, [rbp+5C0h+var_600]
0x1800036a3  mov     [rbp+5C0h+var_570], rax
0x1800036a7  lea     rax, [rbp+5C0h+var_570]
0x1800036ab  mov     [rbp+5C0h+var_3D0], rax
0x1800036b2  mov     eax, [rbp+5C0h+var_5AC]
0x1800036b5  mov     [rbp+5C0h+var_568], rax
0x1800036b9  lea     rax, [rbp+5C0h+var_568]
0x1800036bd  mov     [rbp+5C0h+var_3C0], rax
0x1800036c4  mov     eax, [rbp+5C0h+var_5A8]
0x1800036c7  mov     [rbp+5C0h+var_560], rax
0x1800036cb  lea     rax, [rbp+5C0h+var_560]
0x1800036cf  mov     [rbp+5C0h+var_3B0], rax
0x1800036d6  mov     eax, [rbp+5C0h+var_594]
0x1800036d9  mov     [rbp+5C0h+var_558], rax
0x1800036dd  mov     [rbp+5C0h+var_498], r12
0x1800036e4  mov     [rbp+5C0h+var_488], r12
0x1800036eb  mov     [rbp+5C0h+var_478], r12
0x1800036f2  mov     [rbp+5C0h+var_468], r12
0x1800036f9  mov     [rsp+6C0h+var_67C], edx
0x1800036fd  mov     [rbp+5C0h+var_458], r12
0x180003704  mov     [rbp+5C0h+var_448], r12
0x18000370b  mov     [rsp+6C0h+var_674], ecx
0x18000370f  mov     [rbp+5C0h+var_438], r12
0x180003716  mov     [rbp+5C0h+var_428], r12
0x18000371d  mov     [rbp+5C0h+var_418], r12
0x180003724  mov     [rbp+5C0h+var_408], r12
0x18000372b  mov     [rsp+6C0h+var_664], esi
0x18000372f  mov     [rbp+5C0h+var_3F8], r12
0x180003736  mov     [rbp+5C0h+var_3E8], r12
0x18000373d  mov     [rbp+5C0h+var_3D8], 8
0x180003748  mov     [rbp+5C0h+var_3C8], 8
0x180003753  mov     [rbp+5C0h+var_3B8], 8
0x18000375e  mov     [rbp+5C0h+var_3A8], 8
0x180003769  lea     rax, [rbp+5C0h+var_558]
0x18000376d  mov     [rbp+5C0h+var_398], 8
0x180003778  mov     [rbp+5C0h+var_3A0], rax
0x18000377f  lea     rdx, byte_180006F51
0x180003786  mov     eax, r8d
0x180003789  mov     [rbp+5C0h+var_550], rax
0x18000378d  lea     rax, [rbp+5C0h+var_550]
0x180003791  mov     [rbp+5C0h+var_390], rax
0x180003798  mov     eax, [rbp+5C0h+var_5A4]
0x18000379b  mov     [rbp+5C0h+var_548], rax
0x18000379f  lea     rax, [rbp+5C0h+var_548]
0x1800037a3  mov     [rbp+5C0h+var_380], rax
0x1800037aa  mov     eax, [rbp+5C0h+var_5A0]
0x1800037ad  mov     [rbp+5C0h+var_540], rax
0x1800037b4  lea     rax, [rbp+5C0h+var_540]
0x1800037bb  mov     [rbp+5C0h+var_370], rax
0x1800037c2  mov     eax, [rbp+5C0h+var_59C]
0x1800037c5  mov     [rbp+5C0h+var_538], rax
0x1800037cc  lea     rax, [rbp+5C0h+var_538]
0x1800037d3  mov     [rbp+5C0h+var_360], rax
0x1800037da  mov     eax, [rbp+5C0h+var_590]
0x1800037dd  mov     [rbp+5C0h+var_530], rax
0x1800037e4  lea     rax, [rbp+5C0h+var_530]
0x1800037eb  mov     [rbp+5C0h+var_350], rax
0x1800037f2  mov     eax, [rbp+5C0h+var_598]
0x1800037f5  mov     [rbp+5C0h+var_528], rax
0x1800037fc  lea     rax, [rbp+5C0h+var_528]
0x180003803  mov     [rbp+5C0h+var_340], rax
0x18000380a  mov     eax, [rbp+5C0h+var_58C]
0x18000380d  mov     [rbp+5C0h+var_520], rax
0x180003814  lea     rax, [rbp+5C0h+var_520]
0x18000381b  mov     [rbp+5C0h+var_330], rax
0x180003822  mov     eax, [rbp+5C0h+var_588]
0x180003825  mov     [rbp+5C0h+var_518], rax
0x18000382c  lea     rax, [rbp+5C0h+var_518]
0x180003833  mov     [rbp+5C0h+var_320], rax
0x18000383a  mov     eax, [rbp+5C0h+var_630]
0x18000383d  mov     [rsp+6C0h+var_65C], eax
0x180003841  lea     rax, [rsp+6C0h+var_65C]
0x180003846  mov     [rbp+5C0h+var_310], rax
0x18000384d  mov     eax, [rbp+5C0h+var_584]
0x180003850  mov     [rsp+6C0h+var_658], eax
0x180003854  lea     rax, [rsp+6C0h+var_658]
0x180003859  mov     [rbp+5C0h+var_300], rax
0x180003860  mov     eax, [rbp+5C0h+var_580]
0x180003863  mov     [rsp+6C0h+var_654], eax
0x180003867  lea     rax, [rsp+6C0h+var_654]
0x18000386c  mov     [rbp+5C0h+var_2F0], rax
0x180003873  mov     eax, [rbp+5C0h+var_60C]
0x180003876  mov     [rsp+6C0h+var_650], eax
0x18000387a  lea     rax, [rsp+6C0h+var_650]
0x18000387f  mov     [rbp+5C0h+var_2E0], rax
0x180003886  lea     rax, [rbp+5C0h+var_4C0]
0x18000388d  mov     [rsp+6C0h+var_698], rax
0x180003892  mov     [rsp+6C0h+var_6A0], r14d
0x180003897  mov     [rbp+5C0h+var_388], 8
  ... truncated ...
```
