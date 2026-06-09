# CddPresentBlt(CDDPDEV *,REGION_CORE *,_WORKERTHREAD_COMMAND)

- ea: `0x14002a758`
- end: `0x14002ad2a`
- name: `?CddPresentBlt@@YAJPEAUCDDPDEV@@PEAVREGION_CORE@@W4_WORKERTHREAD_COMMAND@@@Z`
- size: `1490`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011510`

## callees

- `0x140004600`
- `0x1400140c0`
- `0x14002a758`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002acb3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002acb3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002a977`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002a977`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a9a5`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a9a5`
- `watchdog!WdLogSingleEntry3` at `0x14002a89f`
- `watchdog!WdLogSingleEntry3` at `0x14002a89f`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a8b8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a8b8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002aa32`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ab17`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002aa32`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ab17`
- `watchdog!WdLogSingleEntry0` at `0x14002a98e`
- `watchdog!WdLogSingleEntry0` at `0x14002aa19`
- `watchdog!WdLogSingleEntry0` at `0x14002ab01`
- `watchdog!WdLogSingleEntry0` at `0x14002a98e`
- `watchdog!WdLogSingleEntry0` at `0x14002aa19`
- `watchdog!WdLogSingleEntry0` at `0x14002ab01`
- `WIN32K!CddEngGetRgnData` at `0x14002a804`
- `WIN32K!CddEngGetRgnData` at `0x14002a847`
- `WIN32K!CddEngGetRgnData` at `0x14002a804`
- `WIN32K!CddEngGetRgnData` at `0x14002a847`
- `WIN32K!CLIPOBJ_bEnum` at `0x14002aadd`
- `WIN32K!CLIPOBJ_bEnum` at `0x14002aadd`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14002aab9`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14002aab9`
- `WIN32K!EngAllocMem` at `0x14002a826`
- `WIN32K!EngAllocMem` at `0x14002a826`
- `WIN32K!EngFreeMem` at `0x14002a8eb`
- `WIN32K!EngFreeMem` at `0x14002a8eb`

## pseudocode

```c
__int64 __fastcall CddPresentBlt(__int64 a1, __int64 a2, int a3)
{
  int v6; // esi
  __int64 v7; // rcx
  ULONG RgnData; // eax
  ULONG v9; // r14d
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  BOOL v12; // r15d
  int v13; // eax
  _QWORD *v14; // rax
  __int64 v15; // r8
  ULONG v16; // r14d
  _DWORD *v17; // rdx
  __int64 v18; // rax
  char *v19; // rdi
  _QWORD *v20; // rax
  CLIPOBJ *v21; // r10
  BYTE iDComplexity; // al
  char *v23; // r12
  _QWORD *v24; // rax
  _DWORD *v25; // rax
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // edx
  _QWORD *v29; // rax
  unsigned int i; // r10d
  __int64 v31; // r9
  int v32; // r8d
  int v33; // edx
  int v34; // ecx
  _DWORD *v35; // r14
  int v36; // eax
  _BYTE v38[32]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v39[12]; // [rsp+50h] [rbp-39h] BYREF

  memset(v39, 0, 0x58u);
  v6 = 0;
  CDDETWPROFILER::CDDETWPROFILER((CDDETWPROFILER *)v38, (struct CDDPDEV *)a1, 0xBCBu, 0, 0);
  v7 = *(_QWORD *)(a1 + 2792);
  v39[1] = *(_QWORD *)(a1 + 2488);
  LODWORD(v39[2]) = *(_DWORD *)(a1 + 784);
  v39[3] = *(_QWORD *)(v7 + 48);
  v39[4] = *(_QWORD *)(a1 + 796);
  LODWORD(v39[5]) = *(_DWORD *)(v7 + 64);
  if ( a2
    && (RgnData = CddEngGetRgnData(a2, 0, 0), v9 = RgnData, RgnData > 0x20)
    && (v10 = EngAllocMem(0, RgnData, 0x64646344u), (v11 = v10) != 0) )
  {
    CddEngGetRgnData(a2, v9, v10);
    v12 = 1;
    LODWORD(v39[0]) = (a3 == 1) + 1;
    HIDWORD(v39[9]) = v11[2];
    v39[10] = v11 + 8;
    v13 = (*(__int64 (__fastcall **)(_QWORD *))(a1 + 408))(v39);
    v6 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry3(2, *(_QWORD *)(a1 + 2488), *(unsigned int *)(a1 + 784), v13);
      WdLogGlobalForLineNumber = 3390;
      v14 = (_QWORD *)WdLogNewEntry5_WdError();
      v14[3] = gCddImageInfo;
      v14[4] = (unsigned int)dword_14003E570;
      v14[5] = 215857758;
      WdLogGlobalForLineNumber = 3390;
    }
    EngFreeMem(v11);
  }
  else
  {
    v12 = 1;
  }
  if ( a3 == 2 && v6 >= 0 )
  {
    v15 = *(_QWORD *)(a1 + 2768);
    v16 = 3;
    v17 = *(_DWORD **)(a1 + 2776);
    LODWORD(v39[0]) = 3;
    *(_OWORD *)((char *)&v39[7] + 4) = *(_OWORD *)v15;
    LODWORD(v39[6]) = v17[1];
    LODWORD(v39[7]) = v17[1] + *(_DWORD *)(v15 + 12) - *(_DWORD *)(v15 + 4);
    HIDWORD(v39[5]) = *v17;
    v18 = *(_QWORD *)(a1 + 2760);
    HIDWORD(v39[6]) = *v17 + *(_DWORD *)(v15 + 8) - *(_DWORD *)v15;
    if ( v18 && *(_BYTE *)(v18 + 20) )
    {
      v19 = (char *)ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(a1 + 776));
      if ( !v19 )
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 3419;
        v20 = (_QWORD *)WdLogNewEntry5_WdLowResource();
        v6 = -1073741801;
        v20[3] = gCddImageInfo;
        v20[4] = (unsigned int)dword_14003E570;
        v20[5] = 215857758;
        WdLogGlobalForLineNumber = 3419;
        goto LABEL_53;
      }
      v21 = *(CLIPOBJ **)(a1 + 2760);
      iDComplexity = v21->iDComplexity;
      if ( iDComplexity == 1 )
      {
        *(_DWORD *)v19 = 1;
        v23 = v19 + 4;
        v12 = 0;
        *(_OWORD *)(v19 + 4) = *(_OWORD *)(*(_QWORD *)(a1 + 2760) + 4LL);
      }
      else
      {
        if ( iDComplexity != 3 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 3433;
          v24 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v24[3] = gCddImageInfo;
          v24[4] = (unsigned int)dword_14003E570;
          v24[5] = 215857758;
          WdLogGlobalForLineNumber = 3433;
          v12 = 1;
          v21 = *(CLIPOBJ **)(a1 + 2760);
        }
        v25 = *(_DWORD **)(a1 + 2768);
        v26 = *(_DWORD **)(a1 + 2776);
        v27 = v25[1];
        v28 = v26[1];
        if ( *v26 >= *v25 )
        {
          v16 = 0;
          if ( v28 < v27 )
            v16 = 2;
        }
        else if ( v28 >= v27 )
        {
          v16 = 1;
        }
        CLIPOBJ_cEnumStart(v21, 0, 0, v16, 0x14u);
        v23 = v19 + 4;
      }
      if ( !v12 )
        goto LABEL_27;
      do
      {
        v12 = CLIPOBJ_bEnum(*(CLIPOBJ **)(a1 + 2760), 0x144u, (ULONG *)v19);
LABEL_27:
        HIDWORD(v39[9]) = 0;
        v39[10] = v23;
        if ( *(_DWORD *)v19 > 0x14u )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 3483;
          v29 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v29[3] = gCddImageInfo;
          v29[4] = (unsigned int)dword_14003E570;
          v29[5] = 215857758;
          WdLogGlobalForLineNumber = 3483;
        }
        for ( i = 0; i < *(_DWORD *)v19; ++i )
        {
          v31 = 16LL * i;
          v32 = **(_DWORD **)(a1 + 2768);
          if ( *(_DWORD *)&v19[v31 + 4] >= v32 )
            v32 = *(_DWORD *)&v19[v31 + 4];
          else
            *(_DWORD *)&v19[v31 + 4] = v32;
          v33 = *(_DWORD *)(*(_QWORD *)(a1 + 2768) + 8LL);
          if ( *(_DWORD *)&v19[v31 + 12] <= v33 )
            v33 = *(_DWORD *)&v19[v31 + 12];
          else
            *(_DWORD *)&v19[v31 + 12] = v33;
          v34 = *(_DWORD *)(*(_QWORD *)(a1 + 2768) + 4LL);
          if ( *(_DWORD *)&v19[v31 + 8] >= v34 )
            v34 = *(_DWORD *)&v19[v31 + 8];
          else
            *(_DWORD *)&v19[v31 + 8] = v34;
          v35 = *(_DWORD **)(a1 + 2768);
          v36 = v35[3];
          if ( *(_DWORD *)&v19[v31 + 16] <= v36 )
          {
            v36 = *(_DWORD *)&v19[v31 + 16];
          }
          else
          {
            *(_DWORD *)&v19[v31 + 16] = v36;
            v35 = *(_DWORD **)(a1 + 2768);
          }
          if ( v34 < v36 && v32 < v33 )
          {
            *(_DWORD *)&v19[16 * HIDWORD(v39[9]) + 4] = v32 + **(_DWORD **)(a1 + 2776) - *v35;
            *(_DWORD *)&v19[16 * HIDWORD(v39[9]) + 12] = *(_DWORD *)&v19[v31 + 12]
                                                       + **(_DWORD **)(a1 + 2776)
                                                       - **(_DWORD **)(a1 + 2768);
            *(_DWORD *)&v19[16 * HIDWORD(v39[9]) + 8] = *(_DWORD *)&v19[v31 + 8]
                                                      + *(_DWORD *)(*(_QWORD *)(a1 + 2776) + 4LL)
                                                      - *(_DWORD *)(*(_QWORD *)(a1 + 2768) + 4LL);
            *(_DWORD *)&v19[16 * HIDWORD(v39[9]) + 16] = *(_DWORD *)&v19[v31 + 16]
                                                       + *(_DWORD *)(*(_QWORD *)(a1 + 2776) + 4LL)
                                                       - *(_DWORD *)(*(_QWORD *)(a1 + 2768) + 4LL);
            ++HIDWORD(v39[9]);
          }
        }
        if ( HIDWORD(v39[9]) )
        {
          v6 = (*(__int64 (__fastcall **)(_QWORD *))(a1 + 408))(v39);
          if ( v6 < 0 )
            break;
        }
      }
      while ( v12 );
      ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(a1 + 776), v19);
      LOBYTE(v12) = 1;
    }
    else
    {
      HIDWORD(v39[9]) = 1;
      v39[10] = (char *)&v39[5] + 4;
      v6 = (*(__int64 (__fastcall **)(_QWORD *))(a1 + 408))(v39);
    }
    if ( v6 == -1071774910 )
    {
      *(_BYTE *)(a1 + 2714) = v12;
      v6 = 0;
    }
  }
LABEL_53:
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v38);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002a758  mov     [rsp-8+arg_10], rbx
0x14002a75d  mov     [rsp-8+arg_18], rsi
0x14002a762  push    rbp
0x14002a763  push    rdi
0x14002a764  push    r12
0x14002a766  push    r14
0x14002a768  push    r15
0x14002a76a  lea     rbp, [rsp-37h]
0x14002a76f  sub     rsp, 0C0h
0x14002a776  mov     rax, cs:__security_cookie
0x14002a77d  xor     rax, rsp
0x14002a780  mov     [rbp+57h+var_30], rax
0x14002a784  mov     r15, rdx
0x14002a787  mov     r12d, r8d
0x14002a78a  xor     edx, edx; Val
0x14002a78c  mov     rbx, rcx
0x14002a78f  lea     rcx, [rbp+57h+var_90]; void *
0x14002a793  lea     r8d, [rdx+58h]; Size
0x14002a797  call    memset
0x14002a79c  xor     esi, esi
0x14002a79e  lea     rcx, [rbp+57h+var_B0]; this
0x14002a7a2  xor     r9d, r9d; struct _DXGKETW_PARAMS *
0x14002a7a5  mov     byte ptr [rsp+0E0h+cLimit], sil; bool
0x14002a7aa  mov     r8d, 0BCBh; unsigned int
0x14002a7b0  mov     rdx, rbx; struct CDDPDEV *
0x14002a7b3  call    ??0CDDETWPROFILER@@QEAA@PEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::CDDETWPROFILER(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14002a7b8  mov     rax, [rbx+9B8h]
0x14002a7bf  mov     rcx, [rbx+0AE8h]
0x14002a7c6  mov     [rbp+57h+var_88], rax
0x14002a7ca  mov     eax, [rbx+310h]
0x14002a7d0  mov     [rbp+57h+var_80], eax
0x14002a7d3  mov     rax, [rcx+30h]
0x14002a7d7  mov     [rbp+57h+var_78], rax
0x14002a7db  mov     eax, [rbx+31Ch]
0x14002a7e1  mov     [rbp+57h+var_70], eax
0x14002a7e4  mov     eax, [rbx+320h]
0x14002a7ea  mov     [rbp+57h+var_6C], eax
0x14002a7ed  mov     eax, [rcx+40h]
0x14002a7f0  mov     [rbp+57h+var_68], eax
0x14002a7f3  test    r15, r15
0x14002a7f6  jz      loc_14002A8F9
0x14002a7fc  xor     r8d, r8d
0x14002a7ff  xor     edx, edx
0x14002a801  mov     rcx, r15
0x14002a804  call    cs:__imp_CddEngGetRgnData
0x14002a80b  nop     dword ptr [rax+rax+00h]
0x14002a810  mov     r14d, eax
0x14002a813  cmp     eax, 20h ; ' '
0x14002a816  jbe     loc_14002A8F9
0x14002a81c  mov     r8d, 64646344h; ulTag
0x14002a822  mov     edx, eax; cjMemSize
0x14002a824  xor     ecx, ecx; fl
0x14002a826  call    cs:__imp_EngAllocMem
0x14002a82d  nop     dword ptr [rax+rax+00h]
0x14002a832  mov     rdi, rax
0x14002a835  test    rax, rax
0x14002a838  jz      loc_14002A8F9
0x14002a83e  mov     r8, rax
0x14002a841  mov     edx, r14d
0x14002a844  mov     rcx, r15
0x14002a847  call    cs:__imp_CddEngGetRgnData
0x14002a84e  nop     dword ptr [rax+rax+00h]
0x14002a853  xor     eax, eax
0x14002a855  lea     r15d, [rsi+1]
0x14002a859  cmp     r12d, r15d
0x14002a85c  lea     rcx, [rbp+57h+var_90]
0x14002a860  setz    al
0x14002a863  add     eax, r15d
0x14002a866  mov     [rbp+57h+var_90], eax
0x14002a869  mov     eax, [rdi+8]
0x14002a86c  mov     [rbp+57h+var_44], eax
0x14002a86f  lea     rax, [rdi+20h]
0x14002a873  mov     [rbp+57h+var_40], rax
0x14002a877  mov     rax, [rbx+198h]
0x14002a87e  call    _guard_dispatch_icall
0x14002a883  movsxd  rsi, eax
0x14002a886  test    eax, eax
0x14002a888  jns     short loc_14002A8E8
0x14002a88a  mov     r8d, [rbx+310h]
0x14002a891  lea     ecx, [r15+1]
0x14002a895  mov     rdx, [rbx+9B8h]
0x14002a89c  mov     r9, rsi
0x14002a89f  call    cs:__imp_WdLogSingleEntry3
0x14002a8a6  nop     dword ptr [rax+rax+00h]
0x14002a8ab  mov     r14d, 0D3Eh
0x14002a8b1  mov     cs:WdLogGlobalForLineNumber, r14d
0x14002a8b8  call    cs:__imp_WdLogNewEntry5_WdError
0x14002a8bf  nop     dword ptr [rax+rax+00h]
0x14002a8c4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a8cb  mov     [rax+18h], rcx
0x14002a8cf  mov     ecx, cs:dword_14003E570
0x14002a8d5  mov     [rax+20h], rcx
0x14002a8d9  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002a8e1  mov     cs:WdLogGlobalForLineNumber, r14d
0x14002a8e8  mov     rcx, rdi; pv
0x14002a8eb  call    cs:__imp_EngFreeMem
0x14002a8f2  nop     dword ptr [rax+rax+00h]
0x14002a8f7  jmp     short loc_14002A8FF
0x14002a8f9  mov     r15d, 1
0x14002a8ff  cmp     r12d, 2
0x14002a903  jnz     loc_14002ACF6
0x14002a909  test    esi, esi
0x14002a90b  js      loc_14002ACF6
0x14002a911  mov     r8, [rbx+0AD0h]
0x14002a918  lea     r14d, [r12+1]
0x14002a91d  mov     rdx, [rbx+0AD8h]
0x14002a924  mov     [rbp+57h+var_90], r14d
0x14002a928  movups  xmm0, xmmword ptr [r8]
0x14002a92c  movdqu  [rbp+57h+var_54], xmm0
0x14002a931  mov     eax, [rdx+4]
0x14002a934  mov     [rbp+57h+var_60], eax
0x14002a937  mov     ecx, [r8+0Ch]
0x14002a93b  sub     ecx, [r8+4]
0x14002a93f  add     ecx, [rdx+4]
0x14002a942  mov     [rbp+57h+var_58], ecx
0x14002a945  mov     eax, [rdx]
0x14002a947  mov     [rbp+57h+var_64], eax
0x14002a94a  mov     ecx, [r8+8]
0x14002a94e  sub     ecx, [r8]
0x14002a951  add     ecx, [rdx]
0x14002a953  mov     rax, [rbx+0AC8h]
0x14002a95a  mov     [rbp+57h+var_5C], ecx
0x14002a95d  test    rax, rax
0x14002a960  jz      loc_14002ACC7
0x14002a966  cmp     byte ptr [rax+14h], 0
0x14002a96a  jz      loc_14002ACC7
0x14002a970  mov     rcx, [rbx+308h]; Lookaside
0x14002a977  call    cs:__imp_ExAllocateFromLookasideListEx
0x14002a97e  nop     dword ptr [rax+rax+00h]
0x14002a983  mov     rdi, rax
0x14002a986  test    rax, rax
0x14002a989  jnz     short loc_14002A9DE
0x14002a98b  lea     ecx, [rax+6]
0x14002a98e  call    cs:__imp_WdLogSingleEntry0
0x14002a995  nop     dword ptr [rax+rax+00h]
0x14002a99a  mov     ebx, 0D5Bh
0x14002a99f  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a9a5  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002a9ac  nop     dword ptr [rax+rax+00h]
0x14002a9b1  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a9b8  mov     esi, 0C0000017h
0x14002a9bd  mov     [rax+18h], rcx
0x14002a9c1  mov     ecx, cs:dword_14003E570
0x14002a9c7  mov     [rax+20h], rcx
0x14002a9cb  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002a9d3  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a9d9  jmp     loc_14002ACF6
0x14002a9de  mov     r10, [rbx+0AC8h]
0x14002a9e5  mov     al, [r10+14h]
0x14002a9e9  cmp     al, r15b
0x14002a9ec  jnz     short loc_14002AA11
0x14002a9ee  mov     dword ptr [rdi], 1
0x14002a9f4  lea     r12, [rdi+4]
0x14002a9f8  mov     rax, [rbx+0AC8h]
0x14002a9ff  xor     r15d, r15d
0x14002aa02  movups  xmm0, xmmword ptr [rax+4]
0x14002aa06  movdqu  xmmword ptr [r12], xmm0
0x14002aa0c  jmp     loc_14002AAC9
0x14002aa11  cmp     al, r14b
0x14002aa14  jz      short loc_14002AA6F
0x14002aa16  mov     ecx, r15d
0x14002aa19  call    cs:__imp_WdLogSingleEntry0
0x14002aa20  nop     dword ptr [rax+rax+00h]
0x14002aa25  mov     r15d, 0D69h
0x14002aa2b  mov     cs:WdLogGlobalForLineNumber, r15d
0x14002aa32  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002aa39  nop     dword ptr [rax+rax+00h]
0x14002aa3e  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002aa45  mov     [rax+18h], rcx
0x14002aa49  mov     ecx, cs:dword_14003E570
0x14002aa4f  mov     [rax+20h], rcx
0x14002aa53  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002aa5b  mov     cs:WdLogGlobalForLineNumber, r15d
0x14002aa62  mov     r15d, 1
0x14002aa68  mov     r10, [rbx+0AC8h]
0x14002aa6f  mov     rax, [rbx+0AD0h]
0x14002aa76  mov     rcx, [rbx+0AD8h]
0x14002aa7d  mov     r8d, [rax+4]
0x14002aa81  mov     eax, [rax]
0x14002aa83  mov     edx, [rcx+4]
0x14002aa86  cmp     [rcx], eax
0x14002aa88  jge     short loc_14002AA98
0x14002aa8a  cmp     edx, r8d
0x14002aa8d  mov     eax, 1
0x14002aa92  cmovge  r14d, eax
0x14002aa96  jmp     short loc_14002AAA6
0x14002aa98  xor     r14d, r14d
0x14002aa9b  cmp     edx, r8d
0x14002aa9e  lea     eax, [r14+2]
0x14002aaa2  cmovl   r14d, eax
0x14002aaa6  mov     r9d, r14d; iDirection
0x14002aaa9  mov     [rsp+0E0h+cLimit], 14h; cLimit
0x14002aab1  xor     r8d, r8d; iType
0x14002aab4  xor     edx, edx; bAll
0x14002aab6  mov     rcx, r10; pco
0x14002aab9  call    cs:__imp_CLIPOBJ_cEnumStart
0x14002aac0  nop     dword ptr [rax+rax+00h]
0x14002aac5  lea     r12, [rdi+4]
0x14002aac9  test    r15d, r15d
0x14002aacc  jz      short loc_14002AAEC
0x14002aace  mov     rcx, [rbx+0AC8h]; pco
0x14002aad5  mov     r8, rdi; pul
0x14002aad8  mov     edx, 144h; cj
0x14002aadd  call    cs:__imp_CLIPOBJ_bEnum
0x14002aae4  nop     dword ptr [rax+rax+00h]
0x14002aae9  mov     r15d, eax
0x14002aaec  mov     [rbp+57h+var_44], 0
0x14002aaf3  mov     [rbp+57h+var_40], r12
0x14002aaf7  cmp     dword ptr [rdi], 14h
0x14002aafa  jbe     short loc_14002AB4A
0x14002aafc  mov     ecx, 1
0x14002ab01  call    cs:__imp_WdLogSingleEntry0
0x14002ab08  nop     dword ptr [rax+rax+00h]
0x14002ab0d  mov     cs:WdLogGlobalForLineNumber, 0D9Bh
0x14002ab17  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002ab1e  nop     dword ptr [rax+rax+00h]
0x14002ab23  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ab2a  mov     [rax+18h], rcx
0x14002ab2e  mov     ecx, cs:dword_14003E570
0x14002ab34  mov     [rax+20h], rcx
0x14002ab38  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002ab40  mov     cs:WdLogGlobalForLineNumber, 0D9Bh
0x14002ab4a  xor     r10d, r10d
0x14002ab4d  cmp     [rdi], r10d
0x14002ab50  jbe     loc_14002AC84
0x14002ab56  mov     rax, [rbx+0AD0h]
0x14002ab5d  mov     r9d, r10d
0x14002ab60  shl     r9, 4
0x14002ab64  mov     r8d, [rax]
0x14002ab67  mov     eax, [r9+rdi+4]
0x14002ab6c  cmp     eax, r8d
0x14002ab6f  jge     short loc_14002AB78
0x14002ab71  mov     [r9+rdi+4], r8d
0x14002ab76  jmp     short loc_14002AB7B
0x14002ab78  mov     r8d, eax
0x14002ab7b  mov     rax, [rbx+0AD0h]
0x14002ab82  mov     edx, [rax+8]
0x14002ab85  mov     eax, [r9+rdi+0Ch]
0x14002ab8a  cmp     eax, edx
0x14002ab8c  jle     short loc_14002AB95
0x14002ab8e  mov     [r9+rdi+0Ch], edx
0x14002ab93  jmp     short loc_14002AB97
0x14002ab95  mov     edx, eax
0x14002ab97  mov     rax, [rbx+0AD0h]
0x14002ab9e  mov     ecx, [rax+4]
0x14002aba1  mov     eax, [r9+rdi+8]
0x14002aba6  cmp     eax, ecx
0x14002aba8  jge     short loc_14002ABB1
0x14002abaa  mov     [r9+rdi+8], ecx
0x14002abaf  jmp     short loc_14002ABB3
0x14002abb1  mov     ecx, eax
0x14002abb3  mov     r14, [rbx+0AD0h]
0x14002abba  mov     r11d, [r9+rdi+10h]
0x14002abbf  mov     eax, [r14+0Ch]
0x14002abc3  cmp     r11d, eax
0x14002abc6  jle     short loc_14002ABD6
0x14002abc8  mov     [r9+rdi+10h], eax
0x14002abcd  mov     r14, [rbx+0AD0h]
0x14002abd4  jmp     short loc_14002ABD9
0x14002abd6  mov     eax, r11d
0x14002abd9  cmp     ecx, eax
0x14002abdb  jge     loc_14002AC78
0x14002abe1  cmp     r8d, edx
0x14002abe4  jge     loc_14002AC78
0x14002abea  mov     rax, [rbx+0AD8h]
0x14002abf1  mov     edx, [rax]
0x14002abf3  sub     edx, [r14]
0x14002abf6  mov     eax, [rbp+57h+var_44]
0x14002abf9  add     edx, r8d
0x14002abfc  add     rax, rax
0x14002abff  mov     [rdi+rax*8+4], edx
0x14002ac03  mov     rdx, [rbx+0AD8h]
0x14002ac0a  mov     rax, [rbx+0AD0h]
0x14002ac11  mov     r8d, [rdx]
0x14002ac14  sub     r8d, [rax]
0x14002ac17  add     r8d, [r9+rdi+0Ch]
0x14002ac1c  mov     eax, [rbp+57h+var_44]
0x14002ac1f  add     rax, rax
0x14002ac22  mov     [rdi+rax*8+0Ch], r8d
0x14002ac27  mov     rdx, [rbx+0AD8h]
0x14002ac2e  mov     rax, [rbx+0AD0h]
0x14002ac35  mov     r8d, [rdx+4]
0x14002ac39  sub     r8d, [rax+4]
0x14002ac3d  add     r8d, [r9+rdi+8]
0x14002ac42  mov     eax, [rbp+57h+var_44]
0x14002ac45  add     rax, rax
0x14002ac48  mov     [rdi+rax*8+8], r8d
0x14002ac4d  mov     rax, [rbx+0AD0h]
0x14002ac54  mov     rdx, [rbx+0AD8h]
0x14002ac5b  mov     r8d, [rdx+4]
0x14002ac5f  sub     r8d, [rax+4]
0x14002ac63  mov     eax, [rbp+57h+var_44]
0x14002ac66  add     r8d, [r9+rdi+10h]
0x14002ac6b  inc     rax
0x14002ac6e  add     rax, rax
0x14002ac71  mov     [rdi+rax*8], r8d
0x14002ac75  inc     [rbp+57h+var_44]
0x14002ac78  inc     r10d
0x14002ac7b  cmp     r10d, [rdi]
0x14002ac7e  jb      loc_14002AB56
  ... truncated ...
```
