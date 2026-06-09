# RasLineClose

- ea: `0x18008ba58`
- end: `0x18008bea5`
- name: `RasLineClose`
- size: `1101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800205b0`
- `0x180029100`

## callees

- `0x1800755b8`
- `0x18008a88c`
- `0x18008ba58`
- `0x18008e6f4`
- `0x18008f69c`
- `0x18008fd44`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18008be41`
- `KERNEL32!ReleaseMutex` at `0x18008be41`
- `KERNEL32!GetProcessHeap` at `0x18008be0b`
- `KERNEL32!GetProcessHeap` at `0x18008be52`
- `KERNEL32!GetProcessHeap` at `0x18008be0b`
- `KERNEL32!GetProcessHeap` at `0x18008be52`
- `KERNEL32!WaitForSingleObject` at `0x18008bac6`
- `KERNEL32!WaitForSingleObject` at `0x18008bac6`
- `KERNEL32!HeapFree` at `0x18008be1f`
- `KERNEL32!HeapFree` at `0x18008be66`
- `KERNEL32!HeapFree` at `0x18008be1f`
- `KERNEL32!HeapFree` at `0x18008be66`
- `rtutils!TracePrintfA` at `0x18008bb45`
- `rtutils!TracePrintfA` at `0x18008bbd5`
- `rtutils!TracePrintfA` at `0x18008bc78`
- `rtutils!TracePrintfA` at `0x18008bd18`
- `rtutils!TracePrintfA` at `0x18008bdb7`
- `rtutils!TracePrintfA` at `0x18008bb45`
- `rtutils!TracePrintfA` at `0x18008bbd5`
- `rtutils!TracePrintfA` at `0x18008bc78`
- `rtutils!TracePrintfA` at `0x18008bd18`
- `rtutils!TracePrintfA` at `0x18008bdb7`

## string_xrefs

- `0x18008bb87`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008bbce`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineClose(unsigned int a1)
{
  _QWORD *v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  DWORD v5; // eax
  unsigned int *v6; // r15
  _DWORD *v7; // r14
  _DWORD *v8; // rax
  unsigned int v9; // r12d
  unsigned int v10; // eax
  DWORD v11; // eax
  _QWORD *v12; // rcx
  _DWORD *v13; // rdi
  LPVOID v14; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPVOID lpInBuffer; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int *v19; // [rsp+30h] [rbp-D8h] BYREF
  int v20; // [rsp+38h] [rbp-D0h] BYREF
  char v21[2044]; // [rsp+3Ch] [rbp-CCh] BYREF

  lpInBuffer = 0;
  v19 = 0;
  v20 = 0;
  v2 = 0;
  memset_0(v21, 0, sizeof(v21));
  v3 = WaitForSingleObject(g_hRasOpenLinesMutex, 0xFFFFFFFF);
  v4 = v3;
  if ( v3 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineClose: WaitForSingleObject failed with error 0x%x", v3);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v20);
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
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", v5);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v20);
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
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v20,
            L"RasLineClose: RasTapi line handle (%p). Reference count (0x%x)",
            a1,
            (unsigned int)v7[5]);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v20);
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
        v4 = PrepareSyncRequest(117637379, v9, 16, &lpInBuffer);
        if ( v4 )
        {
          ReleaseObjWriteLock(a1);
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              LOWORD(v20) = 0;
              FormatRRASErrorString(&v20, L"RasLineClose: PrepareSyncRequest failed with error (0x%x)", v4);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800D0BE0,
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
              if ( (_QWORD)xmmword_1800D0BE0 )
              {
                LOWORD(v20) = 0;
                FormatRRASErrorString(
                  &v20,
                  L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE) failed with error (0x%x)",
                  v11);
                ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  xmmword_1800D0BE0,
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
0x18008ba58  mov     rax, rsp
0x18008ba5b  mov     [rax+10h], rbx
0x18008ba5f  mov     [rax+18h], rsi
0x18008ba63  mov     [rax+20h], rdi
0x18008ba67  push    rbp
0x18008ba68  push    r12
0x18008ba6a  push    r13
0x18008ba6c  push    r14
0x18008ba6e  push    r15
0x18008ba70  lea     rbp, [rax-768h]
0x18008ba77  sub     rsp, 840h
0x18008ba7e  mov     rax, cs:__security_cookie
0x18008ba85  xor     rax, rsp
0x18008ba88  mov     [rbp+760h+var_30], rax
0x18008ba8f  xor     r13d, r13d
0x18008ba92  mov     edi, ecx
0x18008ba94  lea     rcx, [rsp+860h+var_82C]; void *
0x18008ba99  mov     [rsp+860h+lpInBuffer], r13
0x18008ba9e  xor     edx, edx; Val
0x18008baa0  mov     [rsp+860h+var_838], r13
0x18008baa5  mov     r8d, 7FCh; Size
0x18008baab  mov     [rsp+860h+var_830], r13d
0x18008bab0  mov     esi, r13d
0x18008bab3  call    memset_0
0x18008bab8  mov     rcx, cs:g_hRasOpenLinesMutex; hHandle
0x18008babf  or      r14d, 0FFFFFFFFh
0x18008bac3  mov     edx, r14d; dwMilliseconds
0x18008bac6  call    cs:__imp_WaitForSingleObject
0x18008bacd  nop     dword ptr [rax+rax+00h]
0x18008bad2  mov     ebx, eax
0x18008bad4  test    eax, eax
0x18008bad6  jz      short loc_18008BB56
0x18008bad8  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008badf  jz      short loc_18008BB2C
0x18008bae1  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bae8  jz      loc_18008BE72
0x18008baee  mov     r8d, eax
0x18008baf1  mov     word ptr [rsp+860h+var_830], r13w
0x18008baf7  lea     rdx, aRaslinecloseWa_0; "RasLineClose: WaitForSingleObject faile"...
0x18008bafe  lea     rcx, [rsp+860h+var_830]
0x18008bb03  call    FormatRRASErrorString
0x18008bb08  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bb0f  lea     r8, [rsp+860h+var_830]
0x18008bb14  mov     rcx, cs:gNdpspEtwContext
0x18008bb1b  mov     rax, cs:gNdpspTemplateFunc
0x18008bb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bb27  jmp     loc_18008BE72
0x18008bb2c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bb32  cmp     ecx, r14d
0x18008bb35  jz      loc_18008BE72
0x18008bb3b  mov     r8d, ebx
0x18008bb3e  lea     rdx, aRaslinecloseWa; "RasLineClose: WaitForSingleObject faile"...
0x18008bb45  call    cs:__imp_TracePrintfA
0x18008bb4c  nop     dword ptr [rax+rax+00h]
0x18008bb51  jmp     loc_18008BE72
0x18008bb56  lea     rdx, [rsp+860h+var_838]
0x18008bb5b  mov     ecx, edi
0x18008bb5d  call    GetLineObjWithWriteLock
0x18008bb62  mov     ebx, eax
0x18008bb64  test    eax, eax
0x18008bb66  jz      short loc_18008BBE6
0x18008bb68  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bb6f  jz      short loc_18008BBBC
0x18008bb71  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bb78  jz      loc_18008BE3A
0x18008bb7e  mov     r8d, eax
0x18008bb81  mov     word ptr [rsp+860h+var_830], r13w
0x18008bb87  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x18008bb8e  lea     rcx, [rsp+860h+var_830]
0x18008bb93  call    FormatRRASErrorString
0x18008bb98  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bb9f  lea     r8, [rsp+860h+var_830]
0x18008bba4  mov     rcx, cs:gNdpspEtwContext
0x18008bbab  mov     rax, cs:gNdpspTemplateFunc
0x18008bbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bbb7  jmp     loc_18008BE3A
0x18008bbbc  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bbc2  cmp     ecx, r14d
0x18008bbc5  jz      loc_18008BE3A
0x18008bbcb  mov     r8d, eax
0x18008bbce  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x18008bbd5  call    cs:__imp_TracePrintfA
0x18008bbdc  nop     dword ptr [rax+rax+00h]
0x18008bbe1  jmp     loc_18008BE3A
0x18008bbe6  mov     r15, [rsp+860h+var_838]
0x18008bbeb  mov     r14, r13
0x18008bbee  mov     rax, cs:g_pRasOpenLines
0x18008bbf5  mov     r12d, [r15+4]
0x18008bbf9  jmp     short loc_18008BC04
0x18008bbfb  cmp     r12d, [rax+0Ch]
0x18008bbff  jz      short loc_18008BC0B
0x18008bc01  mov     rax, [rax]
0x18008bc04  test    rax, rax
0x18008bc07  jnz     short loc_18008BBFB
0x18008bc09  jmp     short loc_18008BC0E
0x18008bc0b  mov     r14, rax
0x18008bc0e  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bc15  jz      short loc_18008BC5F
0x18008bc17  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bc1e  jz      short loc_18008BC84
0x18008bc20  mov     word ptr [rsp+860h+var_830], r13w
0x18008bc26  lea     rdx, aRaslinecloseRa_0; "RasLineClose: RasTapi line handle (%p)."...
0x18008bc2d  mov     r9d, [r14+14h]
0x18008bc31  lea     rcx, [rsp+860h+var_830]
0x18008bc36  mov     r8d, edi
0x18008bc39  call    FormatRRASErrorString
0x18008bc3e  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bc45  lea     r8, [rsp+860h+var_830]
0x18008bc4a  mov     rcx, cs:gNdpspEtwContext
0x18008bc51  mov     rax, cs:gNdpspTemplateFunc
0x18008bc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc5d  jmp     short loc_18008BC84
0x18008bc5f  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bc65  cmp     ecx, 0FFFFFFFFh
0x18008bc68  jz      short loc_18008BC84
0x18008bc6a  mov     r9d, [r14+14h]
0x18008bc6e  lea     rdx, aRaslinecloseRa; "RasLineClose: RasTapi line handle (%p)."...
0x18008bc75  mov     r8d, edi
0x18008bc78  call    cs:__imp_TracePrintfA
0x18008bc7f  nop     dword ptr [rax+rax+00h]
0x18008bc84  mov     eax, [r14+14h]
0x18008bc88  cmp     eax, 1
0x18008bc8b  ja      loc_18008BE2D
0x18008bc91  lea     r9, [rsp+860h+lpInBuffer]
0x18008bc96  mov     r8d, 10h
0x18008bc9c  mov     edx, r12d
0x18008bc9f  mov     ecx, 7030103h
0x18008bca4  call    PrepareSyncRequest
0x18008bca9  mov     ebx, eax
0x18008bcab  test    eax, eax
0x18008bcad  jz      short loc_18008BD2E
0x18008bcaf  mov     ecx, edi
0x18008bcb1  call    ReleaseObjWriteLock
0x18008bcb6  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bcbd  jz      short loc_18008BD03
0x18008bcbf  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bcc6  jz      short loc_18008BD24
0x18008bcc8  mov     r8d, ebx
0x18008bccb  mov     word ptr [rsp+860h+var_830], r13w
0x18008bcd1  lea     rdx, aRaslineclosePr_0; "RasLineClose: PrepareSyncRequest failed"...
0x18008bcd8  lea     rcx, [rsp+860h+var_830]
0x18008bcdd  call    FormatRRASErrorString
0x18008bce2  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bce9  lea     r8, [rsp+860h+var_830]
0x18008bcee  mov     rcx, cs:gNdpspEtwContext
0x18008bcf5  mov     rax, cs:gNdpspTemplateFunc
0x18008bcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bd01  jmp     short loc_18008BD24
0x18008bd03  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bd09  cmp     ecx, 0FFFFFFFFh
0x18008bd0c  jz      short loc_18008BD24
0x18008bd0e  mov     r8d, ebx
0x18008bd11  lea     rdx, aRaslineclosePr; "RasLineClose: PrepareSyncRequest failed"...
0x18008bd18  call    cs:__imp_TracePrintfA
0x18008bd1f  nop     dword ptr [rax+rax+00h]
0x18008bd24  mov     rsi, [rsp+860h+lpInBuffer]
0x18008bd29  jmp     loc_18008BE3A
0x18008bd2e  mov     rsi, [rsp+860h+lpInBuffer]
0x18008bd33  mov     ecx, 8FFF23CCh; dwIoControlCode
0x18008bd38  mov     dword ptr [r15], 58585858h
0x18008bd3f  mov     rdx, rsi; lpInBuffer
0x18008bd42  mov     rax, [r15+10h]
0x18008bd46  mov     [rsi+38h], rax
0x18008bd4a  call    SyncDriverRequest
0x18008bd4f  mov     ebx, eax
0x18008bd51  test    eax, eax
0x18008bd53  jz      short loc_18008BDC3
0x18008bd55  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bd5c  jz      short loc_18008BDA2
0x18008bd5e  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bd65  jz      short loc_18008BDC3
0x18008bd67  mov     r8d, eax
0x18008bd6a  mov     word ptr [rsp+860h+var_830], r13w
0x18008bd70  lea     rdx, aRaslinecloseSy; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x18008bd77  lea     rcx, [rsp+860h+var_830]
0x18008bd7c  call    FormatRRASErrorString
0x18008bd81  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bd88  lea     r8, [rsp+860h+var_830]
0x18008bd8d  mov     rcx, cs:gNdpspEtwContext
0x18008bd94  mov     rax, cs:gNdpspTemplateFunc
0x18008bd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bda0  jmp     short loc_18008BDC3
0x18008bda2  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bda8  cmp     ecx, 0FFFFFFFFh
0x18008bdab  jz      short loc_18008BDC3
0x18008bdad  mov     r8d, eax
0x18008bdb0  lea     rdx, aRaslinecloseSy_0; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x18008bdb7  call    cs:__imp_TracePrintfA
0x18008bdbe  nop     dword ptr [rax+rax+00h]
0x18008bdc3  mov     ecx, edi
0x18008bdc5  call    ReleaseObjWriteLock
0x18008bdca  mov     ecx, edi
0x18008bdcc  call    CloseObjHandle
0x18008bdd1  dec     dword ptr [r14+14h]
0x18008bdd5  mov     rcx, r13
0x18008bdd8  mov     rdi, cs:g_pRasOpenLines
0x18008bddf  test    rdi, rdi
0x18008bde2  jz      short loc_18008BE3A
0x18008bde4  mov     rax, [rdi]
0x18008bde7  cmp     r12d, [rdi+0Ch]
0x18008bdeb  jz      short loc_18008BDFA
0x18008bded  mov     rcx, rdi
0x18008bdf0  mov     rdi, rax
0x18008bdf3  test    rax, rax
0x18008bdf6  jnz     short loc_18008BDE4
0x18008bdf8  jmp     short loc_18008BE3A
0x18008bdfa  test    rcx, rcx
0x18008bdfd  jz      short loc_18008BE04
0x18008bdff  mov     [rcx], rax
0x18008be02  jmp     short loc_18008BE0B
0x18008be04  mov     cs:g_pRasOpenLines, rax
0x18008be0b  call    cs:__imp_GetProcessHeap
0x18008be12  nop     dword ptr [rax+rax+00h]
0x18008be17  mov     r8, rdi; lpMem
0x18008be1a  xor     edx, edx; dwFlags
0x18008be1c  mov     rcx, rax; hHeap
0x18008be1f  call    cs:__imp_HeapFree
0x18008be26  nop     dword ptr [rax+rax+00h]
0x18008be2b  jmp     short loc_18008BE3A
0x18008be2d  dec     eax
0x18008be2f  mov     ecx, edi
0x18008be31  mov     [r14+14h], eax
0x18008be35  call    ReleaseObjWriteLock
0x18008be3a  mov     rcx, cs:g_hRasOpenLinesMutex; hMutex
0x18008be41  call    cs:__imp_ReleaseMutex
0x18008be48  nop     dword ptr [rax+rax+00h]
0x18008be4d  test    rsi, rsi
0x18008be50  jz      short loc_18008BE72
0x18008be52  call    cs:__imp_GetProcessHeap
0x18008be59  nop     dword ptr [rax+rax+00h]
0x18008be5e  mov     r8, rsi; lpMem
0x18008be61  xor     edx, edx; dwFlags
0x18008be63  mov     rcx, rax; hHeap
0x18008be66  call    cs:__imp_HeapFree
0x18008be6d  nop     dword ptr [rax+rax+00h]
0x18008be72  mov     eax, ebx
0x18008be74  mov     rcx, [rbp+760h+var_30]
0x18008be7b  xor     rcx, rsp; StackCookie
0x18008be7e  call    __security_check_cookie
0x18008be83  lea     r11, [rsp+860h+var_20]
0x18008be8b  mov     rbx, [r11+38h]
0x18008be8f  mov     rsi, [r11+40h]
0x18008be93  mov     rdi, [r11+48h]
0x18008be97  mov     rsp, r11
0x18008be9a  pop     r15
0x18008be9c  pop     r14
0x18008be9e  pop     r13
0x18008bea0  pop     r12
0x18008bea2  pop     rbp
0x18008bea3  retn
```
