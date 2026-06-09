# FwppSessionCreate

- ea: `0x180007550`
- end: `0x180007b59`
- name: `FwppSessionCreate`
- size: `1545`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x180007380`
- `0x180008470`
- `0x180009340`

## callees

- `0x1800027f0`
- `0x1800034e0`
- `0x180003704`
- `0x180007550`
- `0x180007e38`
- `0x180008bd0`
- `0x18000b0e0`
- `0x18000bdd0`
- `0x18000c8a0`
- `0x18000cc40`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`
- `0x18004b010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180007b08`
- `ntdll!RtlNtStatusToDosError` at `0x180007b08`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800079fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800079fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800079a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800079a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180007a8e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180007a8e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007743`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007743`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007607`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007607`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076e8`
- `RPCRT4!NdrClientCall3` at `0x180007949`
- `RPCRT4!NdrClientCall3` at `0x180007949`
- `RPCRT4!RpcBindingBind` at `0x1800077bc`
- `RPCRT4!RpcBindingBind` at `0x1800077bc`

## string_xrefs

- `0x180007573`: `FwppSessionCreate`
- `0x180007977`: `FwppSessionCreate`
- `0x180007960`: `FwppProxyEngineOpen`
- `0x1800079f7`: `bfe.dll`
- `0x180007ab2`: `OpenEventW`

## pseudocode

```c
__int64 __fastcall FwppSessionCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v5; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v8; // rcx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  int v11; // r8d
  __int64 Local; // rbx
  int v13; // ecx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  RPC_STATUS v17; // eax
  int v18; // r8d
  signed int v19; // esi
  _QWORD *v20; // rcx
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v22; // rcx
  __int64 LastError; // r8
  const char *v24; // rdx
  __int64 (*ProcAddress)(void); // rax
  __int64 v26; // rax
  HANDLE v27; // rax
  __int64 v29; // [rsp+30h] [rbp-79h]
  int v30; // [rsp+58h] [rbp-51h] BYREF
  __int64 v31; // [rsp+60h] [rbp-49h] BYREF
  _QWORD *v32; // [rsp+68h] [rbp-41h] BYREF
  HMODULE hLibModule; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR lpName; // [rsp+78h] [rbp-31h] BYREF
  __int64 v35; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v36[16]; // [rsp+88h] [rbp-21h] BYREF
  const char *v37; // [rsp+98h] [rbp-11h]
  __int64 v38; // [rsp+A0h] [rbp-9h]
  int *v39; // [rsp+A8h] [rbp-1h]
  __int64 v40; // [rsp+B0h] [rbp+7h]

  v5 = 10;
  if ( (_DWORD)a2 != -1 )
    v5 = a2;
  v32 = 0;
  v31 = 0;
  hLibModule = 0;
  *a5 = 0;
  v35 = 0;
  lpName = 0;
  if ( a1 || v5 != 10 || a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, a3, 0, (__int64)"FwppSessionCreate", -1073741637);
    }
    Local = RtlNtStatusToDosError(-1073741637);
    WfpCallUsermodeErrorUTMacro("FwppSessionCreate", Local);
    if ( (int)Local > 0 )
      LODWORD(Local) = (unsigned __int16)Local | 0x80070000;
    Local = (int)Local;
  }
  else
  {
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(0, a2, 0);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v32 = HeapAlloc(gWfpHeap, 0, 0x78u);
      v9 = v32;
      if ( v32 )
      {
        Local = 0;
        if ( gWfpTrackHeapAllocs )
          _InterlockedIncrement(&gWfpNumHeapAllocs);
      }
      else
      {
        v10 = WfpReportSysErrorAsNtStatus(v8, "HeapAlloc", 3221225495LL);
        Local = v10;
        if ( v10 )
        {
          v13 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, 0, (__int64)"WfpMemAlloc25B", v10);
          }
          if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
          {
            v30 = Local;
            v39 = &v30;
            v37 = "WfpMemAlloc25B";
            v38 = 15;
            v40 = 4;
            McGenEventWrite_EtwEventWriteTransfer(v13, (unsigned int)WFP_USERMODE_ERROR, v11, 3, (__int64)v36);
          }
        }
      }
    }
    else
    {
      v14 = HeapAlloc(gWfpHeap, 0, 0x78u);
      v32 = v14;
      v9 = v14;
      if ( v14 )
      {
        Local = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v14));
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v15, "HeapAlloc", 3221225495LL);
        Local = v16;
        if ( v16 )
          WfpReportError(v16, "WfpMemAlloc");
      }
    }
    if ( Local )
    {
      WfpReportError(Local, "WfpPoolAllocNonPaged");
      goto LABEL_50;
    }
    *(_OWORD *)v9 = 0;
    *((_OWORD *)v9 + 1) = 0;
    *((_OWORD *)v9 + 2) = 0;
    *((_OWORD *)v9 + 3) = 0;
    *((_OWORD *)v9 + 4) = 0;
    *((_OWORD *)v9 + 5) = 0;
    *((_OWORD *)v9 + 6) = 0;
    v9[14] = 0;
    Local = FwppRpcBindingCreateLocal(qword_18006AC18, 0, v9);
    if ( !Local )
    {
      v17 = RpcBindingBind(0, (RPC_BINDING_HANDLE)*v9, qword_18005CFB0);
      v19 = v17;
      if ( v17 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(v29) = v17;
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v18, 0, (__int64)"RpcBindingBind", v29);
          v20 = WPP_GLOBAL_Control;
        }
        if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
        {
          v30 = v19;
          v39 = &v30;
          v37 = "RpcBindingBind";
          v38 = 15;
          v40 = 4;
          McGenEventWrite_EtwEventWriteTransfer((_DWORD)v20, (unsigned int)WFP_USERMODE_ERROR, v18, 3, (__int64)v36);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        Local = v19;
        if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 25) >= 2u && (*((_BYTE *)v20 + 28) & 1) != 0 )
        {
          LODWORD(v29) = v19;
          WPP_SF_Ssd(v20[2], 26, v18, 0, (__int64)"FwppRpcBindingBind", v29);
        }
        if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
        {
          v30 = v19;
          v39 = &v30;
          v37 = "FwppRpcBindingBind";
          v38 = 19;
          v40 = 4;
          McGenEventWrite_EtwEventWriteTransfer((_DWORD)v20, (unsigned int)WFP_USERMODE_ERROR, v18, 3, (__int64)v36);
        }
        goto LABEL_50;
      }
      Local = BfeGetThreadPreferredUILanguages(&v31);
      if ( Local )
        goto LABEL_50;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                2u,
                                0,
                                *v9,
                                a4,
                                v31,
                                v9 + 1,
                                &lpName,
                                &v35).Pointer;
      if ( Pointer )
      {
        LastError = Pointer;
        v24 = "FwppProxyEngineOpen";
        goto LABEL_49;
      }
      if ( v35 )
      {
        if ( GetModuleHandleExW(0, L"bfe.dll", &hLibModule)
          && (ProcAddress = GetProcAddress(hLibModule, "BfeGetDirectDispatchTable")) != 0 )
        {
          v26 = ProcAddress();
          g_pBfeDirectDispatchTable = v26;
        }
        else
        {
          v26 = g_pBfeDirectDispatchTable;
        }
        if ( v26 )
          v9[14] = v35;
      }
      Local = FwppRpcBindingCreateLocal(qword_18006AC08, 0, v9 + 2);
      if ( !Local )
      {
        Local = WfpCriticalSectionCreate(v9 + 4);
        if ( !Local )
        {
          *((_BYTE *)v9 + 80) = 1;
          v27 = OpenEventW(0x100000u, 0, lpName);
          v9[11] = v27;
          if ( v27 )
          {
            *a5 = v9;
            goto LABEL_50;
          }
          LastError = GetLastError();
          v24 = "OpenEventW";
LABEL_49:
          Local = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WfpReportSysErrorAsWinError)(
                    (CLIENT_CALL_RETURN)v22.Simple,
                    v24,
                    LastError);
        }
      }
    }
  }
LABEL_50:
  BfeFwpmLangInfoDestroy(&v31);
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  if ( Local )
  {
    FwppSessionDestroy(&v32);
    FwppDeepFree_GUID((LPVOID)lpName);
    WfpReportError(Local, "FwppSessionCreate");
  }
  else
  {
    FwppDeepFree_GUID((LPVOID)lpName);
  }
  return Local;
}

```

## disassembly

```asm
0x180007550  mov     r11, rsp
0x180007553  push    rbp
0x180007554  push    rbx
0x180007555  push    rdi
0x180007556  lea     rbp, [r11-57h]
0x18000755a  sub     rsp, 0E0h
0x180007561  mov     rax, cs:__security_cookie
0x180007568  xor     rax, rsp
0x18000756b  mov     [rbp+4Fh+var_40], rax
0x18000756f  mov     [r11-20h], r12
0x180007573  lea     rdi, aFwppsessioncre; "FwppSessionCreate"
0x18000757a  mov     [r11-28h], r13
0x18000757e  mov     eax, 0Ah
0x180007583  xor     r13d, r13d
0x180007586  mov     [r11-30h], r14
0x18000758a  cmp     edx, 0FFFFFFFFh
0x18000758d  mov     [r11-38h], r15
0x180007591  mov     r15, [rbp+4Fh+arg_20]
0x180007595  mov     r12, r9
0x180007598  cmovnz  eax, edx
0x18000759b  mov     [rbp+4Fh+var_90], r13
0x18000759f  mov     [rbp+4Fh+var_98], r13
0x1800075a3  mov     [rbp+4Fh+hLibModule], r13
0x1800075a7  mov     [r15], r13
0x1800075aa  mov     [rbp+4Fh+var_78], r13
0x1800075ae  mov     [rbp+4Fh+lpName], r13
0x1800075b2  test    rcx, rcx
0x1800075b5  jnz     loc_180007AC6
0x1800075bb  cmp     eax, 0Ah
0x1800075be  jnz     loc_180007AC6
0x1800075c4  test    r8, r8
0x1800075c7  jnz     loc_180007AC6
0x1800075cd  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800075d3  test    al, 10h
0x1800075d5  jz      short loc_1800075DC
0x1800075d7  and     eax, 1
0x1800075da  jmp     short loc_1800075E1
0x1800075dc  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800075e1  mov     rcx, cs:gWfpHeap; hHeap
0x1800075e8  lea     r14, WPP_GLOBAL_Control
0x1800075ef  xor     edx, edx; dwFlags
0x1800075f1  mov     [rsp+0F0h+arg_0], rsi
0x1800075f9  mov     r8d, 78h ; 'x'; dwBytes
0x1800075ff  test    eax, eax
0x180007601  jz      loc_1800076E8
0x180007607  call    cs:__imp_HeapAlloc
0x18000760e  nop     dword ptr [rax+rax+00h]
0x180007613  mov     [rbp+4Fh+var_90], rax
0x180007617  mov     rdi, rax
0x18000761a  test    rax, rax
0x18000761d  jnz     loc_1800076D3
0x180007623  mov     r8d, 0C0000017h
0x180007629  lea     rdx, aHeapalloc; "HeapAlloc"
0x180007630  call    WfpReportSysErrorAsNtStatus
0x180007635  mov     rbx, rax
0x180007638  test    rax, rax
0x18000763b  jz      loc_180007756
0x180007641  mov     rcx, cs:WPP_GLOBAL_Control
0x180007648  lea     rsi, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18000764f  cmp     rcx, r14
0x180007652  jz      short loc_18000767A
0x180007654  cmp     byte ptr [rcx+19h], 2
0x180007658  jb      short loc_18000767A
0x18000765a  test    byte ptr [rcx+1Ch], 1
0x18000765e  jz      short loc_18000767A
0x180007660  mov     rcx, [rcx+10h]
0x180007664  mov     edx, 1Ah
0x180007669  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x18000766d  xor     r9d, r9d
0x180007670  mov     [rsp+0F0h+var_D0], rsi
0x180007675  call    WPP_SF_Ssd
0x18000767a  cmp     cs:gWfpLogUserModeErrors, r13d
0x180007681  jz      loc_180007756
0x180007687  test    cs:byte_18007C665, 1
0x18000768e  jz      loc_180007756
0x180007694  lea     rax, [rbp+4Fh+var_A0]
0x180007698  mov     [rbp+4Fh+var_A0], ebx
0x18000769b  mov     [rbp+4Fh+var_50], rax
0x18000769f  lea     rdx, WFP_USERMODE_ERROR
0x1800076a6  lea     rax, [rbp+4Fh+var_70]
0x1800076aa  mov     [rbp+4Fh+var_60], rsi
0x1800076ae  mov     r9d, 3
0x1800076b4  mov     [rsp+0F0h+var_D0], rax
0x1800076b9  mov     [rbp+4Fh+var_58], 0Fh
0x1800076c1  mov     [rbp+4Fh+var_48], 4
0x1800076c9  call    McGenEventWrite_EtwEventWriteTransfer
0x1800076ce  jmp     loc_180007756
0x1800076d3  cmp     cs:gWfpTrackHeapAllocs, r13d
0x1800076da  mov     rbx, r13
0x1800076dd  jz      short loc_180007756
0x1800076df  lock inc cs:gWfpNumHeapAllocs
0x1800076e6  jmp     short loc_180007756
0x1800076e8  call    cs:__imp_HeapAlloc
0x1800076ef  nop     dword ptr [rax+rax+00h]
0x1800076f4  mov     [rbp+4Fh+var_90], rax
0x1800076f8  mov     rdi, rax
0x1800076fb  test    rax, rax
0x1800076fe  jnz     short loc_18000772B
0x180007700  mov     r8d, 0C0000017h
0x180007706  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000770d  call    WfpReportSysErrorAsNtStatus
0x180007712  mov     rbx, rax
0x180007715  test    rax, rax
0x180007718  jz      short loc_180007756
0x18000771a  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180007721  mov     rcx, rax
0x180007724  call    WfpReportError
0x180007729  jmp     short loc_180007756
0x18000772b  cmp     cs:gWfpTrackHeapBytes, r13d
0x180007732  mov     rbx, r13
0x180007735  jz      short loc_180007756
0x180007737  mov     rcx, cs:gWfpHeap; hHeap
0x18000773e  mov     r8, rax; lpMem
0x180007741  xor     edx, edx; dwFlags
0x180007743  call    cs:__imp_HeapSize
0x18000774a  nop     dword ptr [rax+rax+00h]
0x18000774f  lock add cs:gWfpHeapBytesAllocated, eax
0x180007756  test    rbx, rbx
0x180007759  jz      short loc_18000776F
0x18000775b  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180007762  mov     rcx, rbx
0x180007765  call    WfpReportError
0x18000776a  jmp     loc_18000796F
0x18000776f  xorps   xmm0, xmm0
0x180007772  lea     rcx, qword_18006AC18
0x180007779  movups  xmmword ptr [rdi], xmm0
0x18000777c  xor     eax, eax
0x18000777e  mov     r8, rdi
0x180007781  movups  xmmword ptr [rdi+10h], xmm0
0x180007785  xor     edx, edx
0x180007787  movups  xmmword ptr [rdi+20h], xmm0
0x18000778b  movups  xmmword ptr [rdi+30h], xmm0
0x18000778f  movups  xmmword ptr [rdi+40h], xmm0
0x180007793  movups  xmmword ptr [rdi+50h], xmm0
0x180007797  movups  xmmword ptr [rdi+60h], xmm0
0x18000779b  mov     [rdi+70h], rax
0x18000779f  call    FwppRpcBindingCreateLocal
0x1800077a4  mov     rbx, rax
0x1800077a7  test    rax, rax
0x1800077aa  jnz     loc_18000796F
0x1800077b0  mov     rdx, [rdi]; Binding
0x1800077b3  lea     r8, qword_18005CFB0; IfSpec
0x1800077ba  xor     ecx, ecx; pAsync
0x1800077bc  call    cs:__imp_RpcBindingBind
0x1800077c3  nop     dword ptr [rax+rax+00h]
0x1800077c8  mov     esi, eax
0x1800077ca  test    eax, eax
0x1800077cc  jz      loc_1800078FD
0x1800077d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077d9  lea     rbx, aRpcbindingbind_0; "RpcBindingBind"
0x1800077e0  cmp     rcx, r14
0x1800077e3  jz      short loc_180007812
0x1800077e5  cmp     byte ptr [rcx+19h], 2
0x1800077e9  jb      short loc_180007812
0x1800077eb  test    byte ptr [rcx+1Ch], 1
0x1800077ef  jz      short loc_180007812
0x1800077f1  mov     rcx, [rcx+10h]
0x1800077f5  mov     edx, 18h
0x1800077fa  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1800077fe  xor     r9d, r9d
0x180007801  mov     [rsp+0F0h+var_D0], rbx
0x180007806  call    WPP_SF_Ssd
0x18000780b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007812  cmp     cs:gWfpLogUserModeErrors, r13d
0x180007819  jz      short loc_180007865
0x18000781b  test    cs:byte_18007C665, 1
0x180007822  jz      short loc_180007865
0x180007824  lea     rax, [rbp+4Fh+var_A0]
0x180007828  mov     [rbp+4Fh+var_A0], esi
0x18000782b  mov     [rbp+4Fh+var_50], rax
0x18000782f  lea     rdx, WFP_USERMODE_ERROR
0x180007836  lea     rax, [rbp+4Fh+var_70]
0x18000783a  mov     [rbp+4Fh+var_60], rbx
0x18000783e  mov     r9d, 3
0x180007844  mov     [rsp+0F0h+var_D0], rax
0x180007849  mov     [rbp+4Fh+var_58], 0Fh
0x180007851  mov     [rbp+4Fh+var_48], 4
0x180007859  call    McGenEventWrite_EtwEventWriteTransfer
0x18000785e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007865  test    esi, esi
0x180007867  jle     short loc_180007872
0x180007869  movzx   esi, si
0x18000786c  or      esi, 80070000h
0x180007872  movsxd  rbx, esi
0x180007875  lea     rdi, aFwpprpcbinding_0; "FwppRpcBindingBind"
0x18000787c  cmp     rcx, r14
0x18000787f  jz      short loc_1800078A7
0x180007881  cmp     byte ptr [rcx+19h], 2
0x180007885  jb      short loc_1800078A7
0x180007887  test    byte ptr [rcx+1Ch], 1
0x18000788b  jz      short loc_1800078A7
0x18000788d  mov     rcx, [rcx+10h]
0x180007891  mov     edx, 1Ah
0x180007896  mov     dword ptr [rsp+0F0h+var_C8], esi
0x18000789a  xor     r9d, r9d
0x18000789d  mov     [rsp+0F0h+var_D0], rdi
0x1800078a2  call    WPP_SF_Ssd
0x1800078a7  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800078ae  jz      loc_18000796F
0x1800078b4  test    cs:byte_18007C665, 1
0x1800078bb  jz      loc_18000796F
0x1800078c1  lea     rax, [rbp+4Fh+var_A0]
0x1800078c5  mov     [rbp+4Fh+var_A0], esi
0x1800078c8  mov     [rbp+4Fh+var_50], rax
0x1800078cc  lea     rdx, WFP_USERMODE_ERROR
0x1800078d3  lea     rax, [rbp+4Fh+var_70]
0x1800078d7  mov     [rbp+4Fh+var_60], rdi
0x1800078db  mov     r9d, 3
0x1800078e1  mov     [rsp+0F0h+var_D0], rax
0x1800078e6  mov     [rbp+4Fh+var_58], 13h
0x1800078ee  mov     [rbp+4Fh+var_48], 4
0x1800078f6  call    McGenEventWrite_EtwEventWriteTransfer
0x1800078fb  jmp     short loc_18000796F
0x1800078fd  lea     rcx, [rbp+4Fh+var_98]
0x180007901  call    BfeGetThreadPreferredUILanguages
0x180007906  mov     rbx, rax
0x180007909  test    rax, rax
0x18000790c  jnz     short loc_18000796F
0x18000790e  mov     r9, [rdi]
0x180007911  lea     rcx, [rbp+4Fh+var_78]
0x180007915  mov     [rsp+40h], rcx
0x18000791a  lea     rax, [rdi+8]
0x18000791e  lea     rcx, [rbp+4Fh+lpName]
0x180007922  xor     r8d, r8d; pReturnValue
0x180007925  mov     [rsp+0F0h+var_B8], rcx
0x18000792a  mov     edx, 2; nProcNum
0x18000792f  mov     [rsp+0F0h+var_C0], rax
0x180007934  lea     rcx, pProxyInfo; pProxyInfo
0x18000793b  mov     rax, [rbp+4Fh+var_98]
0x18000793f  mov     [rsp+0F0h+var_C8], rax
0x180007944  mov     [rsp+0F0h+var_D0], r12
0x180007949  call    cs:__imp_NdrClientCall3
0x180007950  nop     dword ptr [rax+rax+00h]
0x180007955  test    eax, eax
0x180007957  jz      loc_1800079EB
0x18000795d  mov     r8d, eax
0x180007960  lea     rdx, aFwppproxyengin_1; "FwppProxyEngineOpen"
0x180007967  call    WfpReportSysErrorAsWinError
0x18000796c  mov     rbx, rax
0x18000796f  mov     rsi, [rsp+0F0h+arg_0]
0x180007977  lea     rdi, aFwppsessioncre; "FwppSessionCreate"
0x18000797e  lea     rcx, [rbp+4Fh+var_98]
0x180007982  call    BfeFwpmLangInfoDestroy
0x180007987  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x18000798b  mov     r15, [rsp+0F0h+var_30]
0x180007993  mov     r14, [rsp+0F0h+var_28]
0x18000799b  mov     r12, [rsp+0D8h]
0x1800079a3  test    rcx, rcx
0x1800079a6  jz      short loc_1800079B8
0x1800079a8  call    cs:__imp_FreeLibrary
0x1800079af  nop     dword ptr [rax+rax+00h]
0x1800079b4  mov     [rbp+4Fh+hLibModule], r13
0x1800079b8  mov     r13, [rsp+0F0h+var_20]
0x1800079c0  test    rbx, rbx
0x1800079c3  jz      loc_180007B35
0x1800079c9  lea     rcx, [rbp+4Fh+var_90]
0x1800079cd  call    FwppSessionDestroy
0x1800079d2  mov     rcx, [rbp+4Fh+lpName]; lpMem
0x1800079d6  call    FwppDeepFree_GUID
0x1800079db  mov     rdx, rdi
0x1800079de  mov     rcx, rbx
0x1800079e1  call    WfpReportError
0x1800079e6  jmp     loc_180007B3E
0x1800079eb  cmp     [rbp+4Fh+var_78], r13
0x1800079ef  jz      short loc_180007A4C
0x1800079f1  lea     r8, [rbp+4Fh+hLibModule]; phModule
0x1800079f5  xor     ecx, ecx; dwFlags
0x1800079f7  lea     rdx, aBfeDll; "bfe.dll"
0x1800079fe  call    cs:__imp_GetModuleHandleExW
0x180007a05  nop     dword ptr [rax+rax+00h]
0x180007a0a  test    eax, eax
0x180007a0c  jz      short loc_180007A38
0x180007a0e  mov     rcx, [rbp+4Fh+hLibModule]; hModule
0x180007a12  lea     rdx, aBfegetdirectdi; "BfeGetDirectDispatchTable"
0x180007a19  call    cs:__imp_GetProcAddress
0x180007a20  nop     dword ptr [rax+rax+00h]
0x180007a25  test    rax, rax
0x180007a28  jz      short loc_180007A38
0x180007a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a2f  mov     cs:g_pBfeDirectDispatchTable, rax
0x180007a36  jmp     short loc_180007A3F
0x180007a38  mov     rax, cs:g_pBfeDirectDispatchTable
0x180007a3f  test    rax, rax
0x180007a42  jz      short loc_180007A4C
0x180007a44  mov     rax, [rbp+4Fh+var_78]
0x180007a48  mov     [rdi+70h], rax
0x180007a4c  lea     r8, [rdi+10h]
0x180007a50  xor     edx, edx
0x180007a52  lea     rcx, qword_18006AC08
0x180007a59  call    FwppRpcBindingCreateLocal
0x180007a5e  mov     rbx, rax
0x180007a61  test    rax, rax
0x180007a64  jnz     loc_18000796F
0x180007a6a  lea     rcx, [rdi+20h]
0x180007a6e  call    WfpCriticalSectionCreate
0x180007a73  mov     rbx, rax
0x180007a76  test    rax, rax
0x180007a79  jnz     loc_18000796F
0x180007a7f  mov     byte ptr [rdi+50h], 1
0x180007a83  xor     edx, edx; bInheritHandle
  ... truncated ...
```
