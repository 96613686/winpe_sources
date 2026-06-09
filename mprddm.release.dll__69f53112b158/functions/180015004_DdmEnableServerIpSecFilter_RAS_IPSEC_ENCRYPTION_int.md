# DdmEnableServerIpSecFilter(_RAS_IPSEC_ENCRYPTION,int)

- ea: `0x180015004`
- end: `0x1800154a5`
- name: `?DdmEnableServerIpSecFilter@@YAKW4_RAS_IPSEC_ENCRYPTION@@H@Z`
- size: `1185`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800085e0`
- `0x18000b6b0`
- `0x180014860`

## callees

- `0x180007c0c`
- `0x180015004`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800152a2`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800152a2`
- `KERNEL32!HeapAlloc` at `0x1800150cf`
- `KERNEL32!HeapAlloc` at `0x1800150cf`
- `KERNEL32!CloseHandle` at `0x1800153d2`
- `KERNEL32!CloseHandle` at `0x1800153d2`
- `KERNEL32!GetLastError` at `0x18001514c`
- `KERNEL32!GetLastError` at `0x1800152be`
- `KERNEL32!GetLastError` at `0x18001514c`
- `KERNEL32!GetLastError` at `0x1800152be`
- `KERNEL32!CreateEventW` at `0x180015137`
- `KERNEL32!CreateEventW` at `0x180015137`
- `KERNEL32!HeapFree` at `0x1800153ee`
- `KERNEL32!HeapFree` at `0x1800153ee`
- `rtutils!RouterLogEventW` at `0x180015110`
- `rtutils!RouterLogEventW` at `0x180015110`

## string_xrefs

- `0x180015170`: `DdmEnableServerIpSecFilter: CreateEvent failed with 0x%x`
- `0x180015360`: `DdmEnableServerIpSecFilterEx completed async with return code 0x%x`

## pseudocode

```c
__int64 __fastcall DdmEnableServerIpSecFilter(int a1, int a2)
{
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rax
  _OWORD *v7; // rax
  void *v8; // rsi
  unsigned int v9; // ebx
  HANDLE EventW; // rax
  __int64 v11; // r8
  DWORD LastError; // eax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // eax
  DWORD v17; // eax
  DWORD v18; // r14d
  DWORD v19; // eax
  __int64 *v20; // rdx
  const wchar_t *v21; // rcx
  void *v22; // rcx
  DWORD dwErrorCode_8[4]; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v25[16]; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v26; // [rsp+58h] [rbp-B0h]
  int v27; // [rsp+60h] [rbp-A8h]
  int v28; // [rsp+64h] [rbp-A4h]
  int v29; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v30[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  v29 = 0;
  *(_OWORD *)dwErrorCode_8 = 0;
  memset_0(v30, 0, sizeof(v30));
  v5 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( aDdmenableserve_2[v6] );
    v26 = L"DdmEnableServerIpSecFilter Enter";
    v27 = 2 * v6 + 2;
    v28 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, v25);
  }
  v7 = HeapAlloc(hHeap, 8u, 0x18u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 8;
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, 8u);
    goto LABEL_45;
  }
  *v7 = 0;
  *((_QWORD *)v7 + 2) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v8 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"DdmEnableServerIpSecFilter: CreateEvent failed with 0x%x", LastError);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v30[2 * v14 - 4] );
    goto LABEL_39;
  }
  *(_DWORD *)v8 = a1;
  *((_DWORD *)v8 + 1) = a2;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v15 = -1;
    do
      ++v15;
    while ( aQueueWorkItemF[v15] );
    v26 = L"queue work item for DdmEnableServerIpSecFilterEx";
    v27 = 2 * v15 + 2;
    v28 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v11, 2, v25);
  }
  v16 = (*(__int64 (__fastcall **)(DdmThreadPool *, void (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *, _QWORD))(*(_QWORD *)qword_1800CF678 + 16LL))(
          qword_1800CF678,
          DdmEnableServerIpSecFilterCallback,
          v8,
          0);
  v9 = v16;
  if ( v16 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"DdmEnableServerIpSecFilter: QueueWorkItem failed with 0x%x", v16);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v30[2 * v14 - 4] );
    goto LABEL_39;
  }
  *(_QWORD *)dwErrorCode_8 = *((_QWORD *)v8 + 1);
  *(_QWORD *)&dwErrorCode_8[2] = *((_QWORD *)qword_1800CF678 + 13);
  v17 = WaitForMultipleObjectsEx(2u, (const HANDLE *)dwErrorCode_8, 0, 0xFFFFFFFF, 1);
  v18 = v17;
  if ( !v17 )
  {
    v9 = *((_DWORD *)v8 + 4);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"DdmEnableServerIpSecFilterEx completed async with return code 0x%x", v9);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_42;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v30[2 * v14 - 4] );
LABEL_39:
    v20 = RasDdmTraceError;
LABEL_40:
    v21 = (const wchar_t *)&v29;
LABEL_41:
    v26 = v21;
    v27 = 2 * v14 + 2;
    v28 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v20, v13, 2, v25);
    goto LABEL_42;
  }
  if ( v17 != 1 )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_42;
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"WaitForMultipleObjectsEx returned %d, GetLastError=%d", v18, v19);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_42;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v30[2 * v14 - 4] );
    v20 = RasDdmTraceInfo;
    goto LABEL_40;
  }
  v9 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v21 = L"TP uninitialized -- DdmEnableServerIpSecFilterEx work may have been canceled";
    v14 = -1;
    do
      ++v14;
    while ( aTpUninitialize[v14] );
    v20 = RasDdmTraceInfo;
    goto LABEL_41;
  }
LABEL_42:
  v22 = (void *)*((_QWORD *)v8 + 1);
  if ( v22 )
  {
    CloseHandle(v22);
    *((_QWORD *)v8 + 1) = 0;
  }
  HeapFree(hHeap, 0, v8);
LABEL_45:
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, L"DdmEnableServerIpSecFilter Return 0x%x", v9);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v5;
      while ( *(_WORD *)&v30[2 * v5 - 4] );
      v28 = 0;
      v27 = 2 * v5 + 2;
      v26 = (const wchar_t *)&v29;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v29, 2, v25);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180015004  mov     rax, rsp
0x180015007  mov     [rax+8], rbx
0x18001500b  mov     [rax+10h], rsi
0x18001500f  mov     [rax+18h], rdi
0x180015013  mov     [rax+20h], r12
0x180015017  push    rbp
0x180015018  push    r14
0x18001501a  push    r15
0x18001501c  lea     rbp, [rax-788h]
0x180015023  sub     rsp, 870h
0x18001502a  mov     rax, cs:__security_cookie
0x180015031  xor     rax, rsp
0x180015034  mov     [rbp+780h+var_20], rax
0x18001503b  mov     ebx, edx
0x18001503d  mov     r14d, ecx
0x180015040  xorps   xmm0, xmm0
0x180015043  lea     rcx, [rsp+880h+var_81C]; void *
0x180015048  xor     r15d, r15d
0x18001504b  xor     edx, edx; Val
0x18001504d  mov     r8d, 7FCh; Size
0x180015053  mov     [rsp+880h+var_820], r15d
0x180015058  movups  xmmword ptr [rsp+880h+dwErrorCode+8], xmm0
0x18001505d  call    memset_0
0x180015062  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015066  test    cs:byte_1800CF404, 10h
0x18001506d  jz      short loc_1800150BB
0x18001506f  lea     rcx, aDdmenableserve_2; "DdmEnableServerIpSecFilter Enter"
0x180015076  mov     rax, rdi
0x180015079  inc     rax
0x18001507c  cmp     [rcx+rax*2], r15w
0x180015081  jnz     short loc_180015079
0x180015083  lea     eax, ds:2[rax*2]
0x18001508a  mov     [rsp+880h+var_830], rcx
0x18001508f  mov     [rsp+880h+var_828], eax
0x180015093  lea     rdx, RasDdmTraceInfo
0x18001509a  lea     rax, [rsp+880h+var_840]
0x18001509f  mov     [rsp+880h+var_824], r15d
0x1800150a4  mov     r9d, 2
0x1800150aa  mov     [rsp+880h+plpszSubStringArray], rax
0x1800150af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800150b6  call    McGenEventWrite_EventWriteTransfer
0x1800150bb  mov     rcx, cs:hHeap; hHeap
0x1800150c2  mov     r8d, 18h; dwBytes
0x1800150c8  lea     r12d, [r8-10h]
0x1800150cc  mov     edx, r12d; dwFlags
0x1800150cf  call    cs:__imp_HeapAlloc
0x1800150d6  nop     dword ptr [rax+rax+00h]
0x1800150db  mov     rsi, rax
0x1800150de  test    rax, rax
0x1800150e1  jnz     short loc_180015121
0x1800150e3  cmp     cs:dword_1800CF4E4, r15d
0x1800150ea  mov     ebx, r12d
0x1800150ed  jbe     loc_1800153FA
0x1800150f3  mov     rcx, cs:hLogHandle; hLogHandle
0x1800150fa  lea     edx, [rax+1]; dwEventType
0x1800150fd  mov     [rsp+880h+dwErrorCode], r12d; dwErrorCode
0x180015102  xor     r9d, r9d; dwSubStringCount
0x180015105  mov     r8d, 4E88h; dwMessageId
0x18001510b  mov     [rsp+880h+plpszSubStringArray], r15; plpszSubStringArray
0x180015110  call    cs:__imp_RouterLogEventW
0x180015117  nop     dword ptr [rax+rax+00h]
0x18001511c  jmp     loc_1800153FA
0x180015121  xorps   xmm0, xmm0
0x180015124  xor     eax, eax
0x180015126  movups  xmmword ptr [rsi], xmm0
0x180015129  xor     r9d, r9d; lpName
0x18001512c  mov     [rsi+10h], rax
0x180015130  xor     r8d, r8d; bInitialState
0x180015133  xor     edx, edx; bManualReset
0x180015135  xor     ecx, ecx; lpEventAttributes
0x180015137  call    cs:__imp_CreateEventW
0x18001513e  nop     dword ptr [rax+rax+00h]
0x180015143  mov     [rsi+8], rax
0x180015147  test    rax, rax
0x18001514a  jnz     short loc_1800151A5
0x18001514c  call    cs:__imp_GetLastError
0x180015153  nop     dword ptr [rax+rax+00h]
0x180015158  test    cs:byte_1800CF404, r12b
0x18001515f  mov     ebx, eax
0x180015161  jz      loc_1800153C9
0x180015167  mov     r8d, eax
0x18001516a  mov     word ptr [rsp+880h+var_820], r15w
0x180015170  lea     rdx, aDdmenableserve; "DdmEnableServerIpSecFilter: CreateEvent"...
0x180015177  lea     rcx, [rsp+880h+var_820]
0x18001517c  call    FormatRRASErrorString
0x180015181  test    cs:byte_1800CF404, r12b
0x180015188  jz      loc_1800153C9
0x18001518e  lea     rcx, [rsp+880h+var_820]
0x180015193  mov     rax, rdi
0x180015196  inc     rax
0x180015199  cmp     [rcx+rax*2], r15w
0x18001519e  jnz     short loc_180015196
0x1800151a0  jmp     loc_18001538C
0x1800151a5  mov     [rsi], r14d
0x1800151a8  mov     [rsi+4], ebx
0x1800151ab  test    cs:byte_1800CF404, 10h
0x1800151b2  jz      short loc_180015200
0x1800151b4  lea     rcx, aQueueWorkItemF; "queue work item for DdmEnableServerIpSe"...
0x1800151bb  mov     rax, rdi
0x1800151be  inc     rax
0x1800151c1  cmp     [rcx+rax*2], r15w
0x1800151c6  jnz     short loc_1800151BE
0x1800151c8  lea     eax, ds:2[rax*2]
0x1800151cf  mov     [rsp+880h+var_830], rcx
0x1800151d4  mov     [rsp+880h+var_828], eax
0x1800151d8  lea     rdx, RasDdmTraceInfo
0x1800151df  lea     rax, [rsp+880h+var_840]
0x1800151e4  mov     [rsp+880h+var_824], r15d
0x1800151e9  mov     r9d, 2
0x1800151ef  mov     [rsp+880h+plpszSubStringArray], rax
0x1800151f4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800151fb  call    McGenEventWrite_EventWriteTransfer
0x180015200  mov     rcx, cs:qword_1800CF678
0x180015207  lea     rdx, ?DdmEnableServerIpSecFilterCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DdmEnableServerIpSecFilterCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18001520e  xor     r9d, r9d
0x180015211  mov     r8, rsi
0x180015214  mov     rax, [rcx]
0x180015217  mov     rax, [rax+10h]
0x18001521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015220  mov     ebx, eax
0x180015222  test    eax, eax
0x180015224  jz      short loc_180015271
0x180015226  test    cs:byte_1800CF404, r12b
0x18001522d  jz      loc_1800153C9
0x180015233  mov     r8d, eax
0x180015236  mov     word ptr [rsp+880h+var_820], r15w
0x18001523c  lea     rdx, aDdmenableserve_5; "DdmEnableServerIpSecFilter: QueueWorkIt"...
0x180015243  lea     rcx, [rsp+880h+var_820]
0x180015248  call    FormatRRASErrorString
0x18001524d  test    cs:byte_1800CF404, r12b
0x180015254  jz      loc_1800153C9
0x18001525a  lea     rcx, [rsp+880h+var_820]
0x18001525f  mov     rax, rdi
0x180015262  inc     rax
0x180015265  cmp     [rcx+rax*2], r15w
0x18001526a  jnz     short loc_180015262
0x18001526c  jmp     loc_18001538C
0x180015271  mov     rax, [rsi+8]
0x180015275  lea     rdx, [rsp+880h+dwErrorCode+8]; lpHandles
0x18001527a  mov     qword ptr [rsp+880h+dwErrorCode+8], rax
0x18001527f  xor     r8d, r8d; bWaitAll
0x180015282  mov     rax, cs:qword_1800CF678
0x180015289  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001528d  mov     dword ptr [rsp+880h+plpszSubStringArray], 1; bAlertable
0x180015295  mov     rcx, [rax+68h]
0x180015299  mov     qword ptr [rsp+880h+var_848], rcx
0x18001529e  lea     ecx, [r8+2]; nCount
0x1800152a2  call    cs:__imp_WaitForMultipleObjectsEx
0x1800152a9  nop     dword ptr [rax+rax+00h]
0x1800152ae  mov     r14d, eax
0x1800152b1  test    eax, eax
0x1800152b3  jz      loc_18001534B
0x1800152b9  cmp     eax, 1
0x1800152bc  jz      short loc_18001531E
0x1800152be  call    cs:__imp_GetLastError
0x1800152c5  nop     dword ptr [rax+rax+00h]
0x1800152ca  test    cs:byte_1800CF404, 10h
0x1800152d1  mov     ebx, eax
0x1800152d3  jz      loc_1800153C9
0x1800152d9  mov     r9d, eax
0x1800152dc  mov     word ptr [rsp+880h+var_820], r15w
0x1800152e2  mov     r8d, r14d
0x1800152e5  lea     rdx, aWaitformultipl; "WaitForMultipleObjectsEx returned %d, G"...
0x1800152ec  lea     rcx, [rsp+880h+var_820]
0x1800152f1  call    FormatRRASErrorString
0x1800152f6  test    cs:byte_1800CF404, 10h
0x1800152fd  jz      loc_1800153C9
0x180015303  lea     rcx, [rsp+880h+var_820]
0x180015308  mov     rax, rdi
0x18001530b  inc     rax
0x18001530e  cmp     [rcx+rax*2], r15w
0x180015313  jnz     short loc_18001530B
0x180015315  lea     rdx, RasDdmTraceInfo
0x18001531c  jmp     short loc_180015393
0x18001531e  test    cs:byte_1800CF404, 10h
0x180015325  mov     ebx, r15d
0x180015328  jz      loc_1800153C9
0x18001532e  lea     rcx, aTpUninitialize; "TP uninitialized -- DdmEnableServerIpSe"...
0x180015335  mov     rax, rdi
0x180015338  inc     rax
0x18001533b  cmp     [rcx+rax*2], r15w
0x180015340  jnz     short loc_180015338
0x180015342  lea     rdx, RasDdmTraceInfo
0x180015349  jmp     short loc_180015398
0x18001534b  test    cs:byte_1800CF404, r12b
0x180015352  mov     ebx, [rsi+10h]
0x180015355  jz      short loc_1800153C9
0x180015357  mov     r8d, ebx
0x18001535a  mov     word ptr [rsp+880h+var_820], r15w
0x180015360  lea     rdx, aDdmenableserve_1; "DdmEnableServerIpSecFilterEx completed "...
0x180015367  lea     rcx, [rsp+880h+var_820]
0x18001536c  call    FormatRRASErrorString
0x180015371  test    cs:byte_1800CF404, r12b
0x180015378  jz      short loc_1800153C9
0x18001537a  lea     rcx, [rsp+880h+var_820]
0x18001537f  mov     rax, rdi
0x180015382  inc     rax
0x180015385  cmp     [rcx+rax*2], r15w
0x18001538a  jnz     short loc_180015382
0x18001538c  lea     rdx, RasDdmTraceError
0x180015393  lea     rcx, [rsp+880h+var_820]
0x180015398  lea     eax, ds:2[rax*2]
0x18001539f  mov     [rsp+880h+var_830], rcx
0x1800153a4  mov     [rsp+880h+var_828], eax
0x1800153a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800153af  lea     rax, [rsp+880h+var_840]
0x1800153b4  mov     [rsp+880h+var_824], r15d
0x1800153b9  mov     r9d, 2
0x1800153bf  mov     [rsp+880h+plpszSubStringArray], rax
0x1800153c4  call    McGenEventWrite_EventWriteTransfer
0x1800153c9  mov     rcx, [rsi+8]; hObject
0x1800153cd  test    rcx, rcx
0x1800153d0  jz      short loc_1800153E2
0x1800153d2  call    cs:__imp_CloseHandle
0x1800153d9  nop     dword ptr [rax+rax+00h]
0x1800153de  mov     [rsi+8], r15
0x1800153e2  mov     rcx, cs:hHeap; hHeap
0x1800153e9  mov     r8, rsi; lpMem
0x1800153ec  xor     edx, edx; dwFlags
0x1800153ee  call    cs:__imp_HeapFree
0x1800153f5  nop     dword ptr [rax+rax+00h]
0x1800153fa  test    cs:byte_1800CF404, 10h
0x180015401  jz      short loc_180015472
0x180015403  mov     r8d, ebx
0x180015406  mov     word ptr [rsp+880h+var_820], r15w
0x18001540c  lea     rdx, aDdmenableserve_7; "DdmEnableServerIpSecFilter Return 0x%x"
0x180015413  lea     rcx, [rsp+880h+var_820]
0x180015418  call    FormatRRASErrorString
0x18001541d  test    cs:byte_1800CF404, 10h
0x180015424  jz      short loc_180015472
0x180015426  lea     rax, [rsp+880h+var_820]
0x18001542b  inc     rdi
0x18001542e  cmp     [rax+rdi*2], r15w
0x180015433  jnz     short loc_18001542B
0x180015435  lea     eax, ds:2[rdi*2]
0x18001543c  mov     [rsp+880h+var_824], r15d
0x180015441  mov     [rsp+880h+var_828], eax
0x180015445  lea     r8, [rsp+880h+var_820]
0x18001544a  lea     rax, [rsp+880h+var_840]
0x18001544f  mov     [rsp+880h+var_830], r8
0x180015454  mov     r9d, 2
0x18001545a  mov     [rsp+880h+plpszSubStringArray], rax
0x18001545f  lea     rdx, RasDdmTraceInfo
0x180015466  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001546d  call    McGenEventWrite_EventWriteTransfer
0x180015472  mov     eax, ebx
0x180015474  mov     rcx, [rbp+780h+var_20]
0x18001547b  xor     rcx, rsp; StackCookie
0x18001547e  call    __security_check_cookie
0x180015483  lea     r11, [rsp+880h+var_10]
0x18001548b  mov     rbx, [r11+20h]
0x18001548f  mov     rsi, [r11+28h]
0x180015493  mov     rdi, [r11+30h]
0x180015497  mov     r12, [r11+38h]
0x18001549b  mov     rsp, r11
0x18001549e  pop     r15
0x1800154a0  pop     r14
0x1800154a2  pop     rbp
0x1800154a3  retn
```
