# RasLineClose

- ea: `0x180023610`
- end: `0x180023a0c`
- name: `RasLineClose`
- size: `1020`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18000f108`
- `0x18000ff60`
- `0x180012b00`
- `0x180013040`

## callees

- `0x18002251c`
- `0x180023610`
- `0x180026c4c`
- `0x180027ba4`
- `0x1800281f0`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800239cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800239cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800239a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800239d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800239a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800239d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800239c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800239c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023675`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023675`
- `rtutils!TracePrintfA` at `0x1800236ed`
- `rtutils!TracePrintfA` at `0x180023777`
- `rtutils!TracePrintfA` at `0x180023813`
- `rtutils!TracePrintfA` at `0x1800238ad`
- `rtutils!TracePrintfA` at `0x180023948`
- `rtutils!TracePrintfA` at `0x1800236ed`
- `rtutils!TracePrintfA` at `0x180023777`
- `rtutils!TracePrintfA` at `0x180023813`
- `rtutils!TracePrintfA` at `0x1800238ad`
- `rtutils!TracePrintfA` at `0x180023948`

## string_xrefs

- `0x180023722`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180023770`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineClose(unsigned int a1)
{
  _QWORD *v2; // rsi
  DWORD v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int *v6; // r15
  _DWORD *v7; // rdi
  _DWORD *v8; // rax
  int v9; // r12d
  unsigned int v10; // eax
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  _DWORD *v13; // rdi
  LPVOID v14; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPVOID lpInBuffer; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int *v19; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v2 = 0;
  lpInBuffer = 0;
  v19 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v3 = WaitForSingleObject(g_hRasOpenLinesMutex, 0xFFFFFFFF);
  v4 = v3;
  if ( v3 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineClose: WaitForSingleObject failed with error 0x%x", v3);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v20);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineClose: WaitForSingleObject failed with error 0x%x", v3);
    }
  }
  else
  {
    v5 = GetLineObjWithWriteLock(a1, &v19);
    v4 = v5;
    if ( v5 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", v5);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v20);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", v5);
      }
    }
    else
    {
      v6 = v19;
      v7 = 0;
      v8 = g_pRasOpenLines;
      v9 = v19[1];
      while ( v8 )
      {
        if ( v9 == v8[3] )
        {
          v7 = v8;
          break;
        }
        v8 = *(_DWORD **)v8;
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v20,
            L"RasLineClose: RasTapi line handle (%p). Reference count (0x%x)",
            a1,
            (unsigned int)v7[5]);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v20);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "RasLineClose: RasTapi line handle (%p). Reference count (0x%x)",
          (const void *)a1,
          v7[5]);
      }
      v10 = v7[5];
      if ( v10 > 1 )
      {
        v7[5] = v10 - 1;
        ReleaseObjWriteLock(a1);
      }
      else
      {
        v4 = PrepareSyncRequest(0x7030103u, v9, 0x10u, &lpInBuffer);
        if ( v4 )
        {
          ReleaseObjWriteLock(a1);
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v20) = 0;
              FormatRRASErrorString(&v20, L"RasLineClose: PrepareSyncRequest failed with error (0x%x)", v4);
              ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC40,
                &v20);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "RasLineClose: PrepareSyncRequest failed with error (0x%x)", v4);
          }
          v2 = lpInBuffer;
        }
        else
        {
          v2 = lpInBuffer;
          *v6 = 1482184792;
          v2[7] = *((_QWORD *)v6 + 2);
          v11 = SyncDriverRequest(0x8FFF23CC, v2);
          v4 = v11;
          if ( v11 )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( qword_18003EC40 )
              {
                LOWORD(v20) = 0;
                FormatRRASErrorString(
                  &v20,
                  L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE) failed with error (0x%x)",
                  v11);
                ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  qword_18003EC40,
                  &v20);
              }
            }
            else if ( dwTraceId != -1 )
            {
              TracePrintfA(dwTraceId, "RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE) failed with error (0x%x)", v11);
            }
          }
          ReleaseObjWriteLock(a1);
          CloseObjHandle(a1);
          --v7[5];
          v12 = 0;
          v13 = g_pRasOpenLines;
          if ( g_pRasOpenLines )
          {
            while ( 1 )
            {
              v14 = *(LPVOID *)v13;
              if ( v9 == v13[3] )
                break;
              v12 = v13;
              v13 = *(_DWORD **)v13;
              if ( !v14 )
                goto LABEL_47;
            }
            if ( v12 )
              *v12 = v14;
            else
              g_pRasOpenLines = *(LPVOID *)v13;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v13);
          }
        }
      }
    }
LABEL_47:
    ReleaseMutex(g_hRasOpenLinesMutex);
    if ( v2 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v2);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180023610  mov     [rsp-8+arg_8], rbx
0x180023615  mov     [rsp-8+arg_10], rsi
0x18002361a  push    rbp
0x18002361b  push    rdi
0x18002361c  push    r12
0x18002361e  push    r14
0x180023620  push    r15
0x180023622  lea     rbp, [rsp-740h]
0x18002362a  sub     rsp, 840h
0x180023631  mov     rax, cs:__security_cookie
0x180023638  xor     rax, rsp
0x18002363b  mov     [rbp+760h+var_30], rax
0x180023642  mov     r14d, ecx
0x180023645  xor     esi, esi
0x180023647  xor     eax, eax
0x180023649  mov     [rsp+860h+lpInBuffer], rsi
0x18002364e  lea     rcx, [rsp+860h+var_82C]; void *
0x180023653  mov     [rsp+860h+var_838], rsi
0x180023658  xor     edx, edx; Val
0x18002365a  mov     [rsp+860h+var_830], eax
0x18002365e  mov     r8d, 7FCh; Size
0x180023664  call    memset_0
0x180023669  mov     rcx, cs:g_hRasOpenLinesMutex; hHandle
0x180023670  or      edi, 0FFFFFFFFh
0x180023673  mov     edx, edi; dwMilliseconds
0x180023675  call    cs:__imp_WaitForSingleObject
0x18002367b  mov     ebx, eax
0x18002367d  test    eax, eax
0x18002367f  jz      short loc_1800236F8
0x180023681  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180023687  jz      short loc_1800236D5
0x180023689  cmp     cs:qword_18003EC40, rsi
0x180023690  jz      loc_1800239DF
0x180023696  xor     ecx, ecx
0x180023698  lea     rdx, aRaslinecloseWa_0; "RasLineClose: WaitForSingleObject faile"...
0x18002369f  mov     word ptr [rsp+860h+var_830], cx
0x1800236a4  mov     r8d, eax
0x1800236a7  lea     rcx, [rsp+860h+var_830]
0x1800236ac  call    FormatRRASErrorString
0x1800236b1  mov     rdx, cs:qword_18003EC40
0x1800236b8  lea     r8, [rsp+860h+var_830]
0x1800236bd  mov     rcx, cs:gNdpspEtwContext
0x1800236c4  mov     rax, cs:gNdpspTemplateFunc
0x1800236cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236d0  jmp     loc_1800239DF
0x1800236d5  mov     ecx, cs:dwTraceId; dwTraceID
0x1800236db  cmp     ecx, edi
0x1800236dd  jz      loc_1800239DF
0x1800236e3  mov     r8d, ebx
0x1800236e6  lea     rdx, aRaslinecloseWa; "RasLineClose: WaitForSingleObject faile"...
0x1800236ed  call    cs:__imp_TracePrintfA
0x1800236f3  jmp     loc_1800239DF
0x1800236f8  lea     rdx, [rsp+860h+var_838]
0x1800236fd  mov     ecx, r14d
0x180023700  call    GetLineObjWithWriteLock
0x180023705  mov     ebx, eax
0x180023707  test    eax, eax
0x180023709  jz      short loc_180023782
0x18002370b  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180023711  jz      short loc_18002375F
0x180023713  cmp     cs:qword_18003EC40, rsi
0x18002371a  jz      loc_1800239B9
0x180023720  xor     ecx, ecx
0x180023722  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x180023729  mov     word ptr [rsp+860h+var_830], cx
0x18002372e  mov     r8d, eax
0x180023731  lea     rcx, [rsp+860h+var_830]
0x180023736  call    FormatRRASErrorString
0x18002373b  mov     rdx, cs:qword_18003EC40
0x180023742  lea     r8, [rsp+860h+var_830]
0x180023747  mov     rcx, cs:gNdpspEtwContext
0x18002374e  mov     rax, cs:gNdpspTemplateFunc
0x180023755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002375a  jmp     loc_1800239B9
0x18002375f  mov     ecx, cs:dwTraceId; dwTraceID
0x180023765  cmp     ecx, edi
0x180023767  jz      loc_1800239B9
0x18002376d  mov     r8d, eax
0x180023770  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x180023777  call    cs:__imp_TracePrintfA
0x18002377d  jmp     loc_1800239B9
0x180023782  mov     r15, [rsp+860h+var_838]
0x180023787  xor     edi, edi
0x180023789  mov     rax, cs:g_pRasOpenLines
0x180023790  mov     r12d, [r15+4]
0x180023794  jmp     short loc_18002379F
0x180023796  cmp     r12d, [rax+0Ch]
0x18002379a  jz      short loc_1800237A6
0x18002379c  mov     rax, [rax]
0x18002379f  test    rax, rax
0x1800237a2  jnz     short loc_180023796
0x1800237a4  jmp     short loc_1800237A9
0x1800237a6  mov     rdi, rax
0x1800237a9  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x1800237af  jz      short loc_1800237FA
0x1800237b1  cmp     cs:qword_18003EC40, rsi
0x1800237b8  jz      short loc_180023819
0x1800237ba  xor     eax, eax
0x1800237bc  lea     rdx, aRaslinecloseRa_0; "RasLineClose: RasTapi line handle (%p)."...
0x1800237c3  mov     word ptr [rsp+860h+var_830], ax
0x1800237c8  lea     rcx, [rsp+860h+var_830]
0x1800237cd  mov     r9d, [rdi+14h]
0x1800237d1  mov     r8d, r14d
0x1800237d4  call    FormatRRASErrorString
0x1800237d9  mov     rdx, cs:qword_18003EC40
0x1800237e0  lea     r8, [rsp+860h+var_830]
0x1800237e5  mov     rcx, cs:gNdpspEtwContext
0x1800237ec  mov     rax, cs:gNdpspTemplateFunc
0x1800237f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f8  jmp     short loc_180023819
0x1800237fa  mov     ecx, cs:dwTraceId; dwTraceID
0x180023800  cmp     ecx, 0FFFFFFFFh
0x180023803  jz      short loc_180023819
0x180023805  mov     r9d, [rdi+14h]
0x180023809  lea     rdx, aRaslinecloseRa; "RasLineClose: RasTapi line handle (%p)."...
0x180023810  mov     r8d, r14d
0x180023813  call    cs:__imp_TracePrintfA
0x180023819  mov     eax, [rdi+14h]
0x18002381c  cmp     eax, 1
0x18002381f  ja      loc_1800239AC
0x180023825  lea     r9, [rsp+860h+lpInBuffer]
0x18002382a  mov     r8d, 10h
0x180023830  mov     edx, r12d
0x180023833  mov     ecx, 7030103h
0x180023838  call    PrepareSyncRequest
0x18002383d  mov     ebx, eax
0x18002383f  test    eax, eax
0x180023841  jz      short loc_1800238BD
0x180023843  mov     ecx, r14d
0x180023846  call    ReleaseObjWriteLock
0x18002384b  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180023851  jz      short loc_180023898
0x180023853  cmp     cs:qword_18003EC40, rsi
0x18002385a  jz      short loc_1800238B3
0x18002385c  xor     eax, eax
0x18002385e  lea     rdx, aRaslineclosePr_0; "RasLineClose: PrepareSyncRequest failed"...
0x180023865  mov     r8d, ebx
0x180023868  mov     word ptr [rsp+860h+var_830], ax
0x18002386d  lea     rcx, [rsp+860h+var_830]
0x180023872  call    FormatRRASErrorString
0x180023877  mov     rdx, cs:qword_18003EC40
0x18002387e  lea     r8, [rsp+860h+var_830]
0x180023883  mov     rcx, cs:gNdpspEtwContext
0x18002388a  mov     rax, cs:gNdpspTemplateFunc
0x180023891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023896  jmp     short loc_1800238B3
0x180023898  mov     ecx, cs:dwTraceId; dwTraceID
0x18002389e  cmp     ecx, 0FFFFFFFFh
0x1800238a1  jz      short loc_1800238B3
0x1800238a3  mov     r8d, ebx
0x1800238a6  lea     rdx, aRaslineclosePr; "RasLineClose: PrepareSyncRequest failed"...
0x1800238ad  call    cs:__imp_TracePrintfA
0x1800238b3  mov     rsi, [rsp+860h+lpInBuffer]
0x1800238b8  jmp     loc_1800239B9
0x1800238bd  mov     rsi, [rsp+860h+lpInBuffer]
0x1800238c2  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800238c7  mov     dword ptr [r15], 58585858h
0x1800238ce  mov     rdx, rsi; lpInBuffer
0x1800238d1  mov     rax, [r15+10h]
0x1800238d5  mov     [rsi+38h], rax
0x1800238d9  call    SyncDriverRequest
0x1800238de  mov     ebx, eax
0x1800238e0  test    eax, eax
0x1800238e2  jz      short loc_18002394E
0x1800238e4  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800238eb  jz      short loc_180023933
0x1800238ed  cmp     cs:qword_18003EC40, 0
0x1800238f5  jz      short loc_18002394E
0x1800238f7  xor     eax, eax
0x1800238f9  lea     rdx, aRaslinecloseSy; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180023900  mov     r8d, ebx
0x180023903  mov     word ptr [rsp+860h+var_830], ax
0x180023908  lea     rcx, [rsp+860h+var_830]
0x18002390d  call    FormatRRASErrorString
0x180023912  mov     rdx, cs:qword_18003EC40
0x180023919  lea     r8, [rsp+860h+var_830]
0x18002391e  mov     rcx, cs:gNdpspEtwContext
0x180023925  mov     rax, cs:gNdpspTemplateFunc
0x18002392c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023931  jmp     short loc_18002394E
0x180023933  mov     ecx, cs:dwTraceId; dwTraceID
0x180023939  cmp     ecx, 0FFFFFFFFh
0x18002393c  jz      short loc_18002394E
0x18002393e  mov     r8d, ebx
0x180023941  lea     rdx, aRaslinecloseSy_0; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180023948  call    cs:__imp_TracePrintfA
0x18002394e  mov     ecx, r14d
0x180023951  call    ReleaseObjWriteLock
0x180023956  mov     ecx, r14d
0x180023959  call    CloseObjHandle
0x18002395e  dec     dword ptr [rdi+14h]
0x180023961  xor     ecx, ecx
0x180023963  mov     rdi, cs:g_pRasOpenLines
0x18002396a  test    rdi, rdi
0x18002396d  jz      short loc_1800239B9
0x18002396f  mov     rax, [rdi]
0x180023972  cmp     r12d, [rdi+0Ch]
0x180023976  jz      short loc_180023985
0x180023978  mov     rcx, rdi
0x18002397b  mov     rdi, rax
0x18002397e  test    rax, rax
0x180023981  jnz     short loc_18002396F
0x180023983  jmp     short loc_1800239B9
0x180023985  test    rcx, rcx
0x180023988  jz      short loc_18002398F
0x18002398a  mov     [rcx], rax
0x18002398d  jmp     short loc_180023996
0x18002398f  mov     cs:g_pRasOpenLines, rax
0x180023996  call    cs:__imp_GetProcessHeap
0x18002399c  mov     r8, rdi; lpMem
0x18002399f  xor     edx, edx; dwFlags
0x1800239a1  mov     rcx, rax; hHeap
0x1800239a4  call    cs:__imp_HeapFree
0x1800239aa  jmp     short loc_1800239B9
0x1800239ac  dec     eax
0x1800239ae  mov     ecx, r14d
0x1800239b1  mov     [rdi+14h], eax
0x1800239b4  call    ReleaseObjWriteLock
0x1800239b9  mov     rcx, cs:g_hRasOpenLinesMutex; hMutex
0x1800239c0  call    cs:__imp_ReleaseMutex
0x1800239c6  test    rsi, rsi
0x1800239c9  jz      short loc_1800239DF
0x1800239cb  call    cs:__imp_GetProcessHeap
0x1800239d1  mov     r8, rsi; lpMem
0x1800239d4  xor     edx, edx; dwFlags
0x1800239d6  mov     rcx, rax; hHeap
0x1800239d9  call    cs:__imp_HeapFree
0x1800239df  mov     eax, ebx
0x1800239e1  mov     rcx, [rbp+760h+var_30]
0x1800239e8  xor     rcx, rsp; StackCookie
0x1800239eb  call    __security_check_cookie
0x1800239f0  lea     r11, [rsp+860h+var_20]
0x1800239f8  mov     rbx, [r11+38h]
0x1800239fc  mov     rsi, [r11+40h]
0x180023a00  mov     rsp, r11
0x180023a03  pop     r15
0x180023a05  pop     r14
0x180023a07  pop     r12
0x180023a09  pop     rdi
0x180023a0a  pop     rbp
0x180023a0b  retn
```
