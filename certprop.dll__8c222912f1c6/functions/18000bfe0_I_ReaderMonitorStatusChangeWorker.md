# I_ReaderMonitorStatusChangeWorker

- ea: `0x18000bfe0`
- end: `0x18000c62c`
- name: `I_ReaderMonitorStatusChangeWorker`
- size: `1612`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, LPSCARD_READERSTATEW *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004600`
- `0x18000af90`
- `0x18000bfe0`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18000c138`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18000c138`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18000c125`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18000c125`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c223`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c469`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c00d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c00d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c3be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c3be`
- `WinSCard!SCardGetStatusChangeW` at `0x18000c15b`
- `WinSCard!SCardGetStatusChangeW` at `0x18000c15b`

## pseudocode

```c
void __fastcall I_ReaderMonitorStatusChangeWorker(
        PTP_CALLBACK_INSTANCE Instance,
        LPSCARD_READERSTATEW *Context,
        PTP_WORK Work)
{
  DWORD CurrentThreadId; // eax
  size_t v6; // rdx
  int v7; // r12d
  int v8; // r10d
  STRSAFE_LPSTR v9; // rcx
  int v10; // ebp
  __int64 v11; // r14
  __int64 v12; // rdx
  char *v13; // rax
  __int64 v14; // rsi
  const char *v15; // r9
  char *v16; // r10
  __int64 v17; // r8
  char *v18; // rax
  LPSCARD_READERSTATEW v19; // rsi
  __int64 v20; // rcx
  LONG v21; // ebp
  unsigned int v22; // r10d
  unsigned int i; // ecx
  bool v24; // zf
  int v25; // r9d
  DWORD v26; // eax
  int v27; // r10d
  size_t v28; // rdx
  int v29; // r11d
  STRSAFE_LPSTR v30; // rcx
  char *v31; // rax
  char *v32; // r13
  const char *v33; // rax
  char *v34; // rax
  __int64 v35; // rdx
  unsigned int j; // ecx
  bool v37; // zf
  int v38; // r8d
  __int64 v39; // rdi
  char LastError; // al
  __int64 v41; // rcx
  __int64 v42; // rdi
  char v43; // al
  int v44; // r10d
  int v45; // r11d
  int v46; // r11d

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  v7 = -1;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180031404 = 0;
LABEL_7:
    v8 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v6 + 1);
    goto LABEL_8;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == CurrentThreadId )
  {
    goto LABEL_4;
  }
  v22 = -1;
  for ( i = 0; ; ++i )
  {
    v24 = i == 32;
    if ( i >= 0x20 )
      break;
    v25 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
    if ( v25 == CurrentThreadId )
    {
      v6 = i;
      `WppTraceIndent'::`2'::idxCurrentThread = i;
      v24 = i == 32;
      break;
    }
    if ( v22 == -1 && !v25 )
      v22 = i;
  }
  if ( !v24 )
  {
LABEL_4:
    if ( (v6 & 0x80000000) != 0LL )
    {
      v8 = 0;
      goto LABEL_8;
    }
    goto LABEL_7;
  }
  if ( v22 != -1 )
  {
    v6 = v22;
    `WppTraceIndent'::`2'::idxCurrentThread = v22;
    *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v22) = CurrentThreadId;
    *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v22 + 1) = 0;
    goto LABEL_4;
  }
  `WppTraceIndent'::`2'::idxCurrentThread = -2;
  v8 = 0;
LABEL_8:
  v9 = WPP_GLOBAL_Control;
  v10 = 1;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v8 >= 1 )
  {
    while ( !StringCbCatA(v9, v6, "..") && v45 + 1 <= v44 )
      ;
    v9 = WPP_GLOBAL_Control;
  }
  v11 = 256;
  v12 = 256;
  v13 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( 1 )
  {
    v14 = 2147483646;
    if ( !*v13 )
      break;
    ++v13;
    if ( !--v12 )
      goto LABEL_18;
  }
  v15 = ">";
  v16 = (char *)HotPatchSpareGlobals - v12;
  v17 = 2147483646;
  do
  {
    if ( !v17 )
      break;
    if ( !*v15 )
      break;
    *v16++ = *v15++;
    --v17;
    --v12;
  }
  while ( v12 );
  v18 = v16 - 1;
  if ( v12 )
    v18 = v16;
  *v18 = 0;
LABEL_18:
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v9 != (STRSAFE_LPSTR)&WPP_GLOBAL_Control && (v9[28] & 2) != 0 && (unsigned __int8)v9[25] >= 5u )
    WPP_SF_s(
      *((_QWORD *)v9 + 2),
      218,
      &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      &`WppTraceIndent'::`2'::szIndentPrefix);
  if ( Context && *Context )
  {
    CallbackMayRunLong(Instance);
    v19 = *Context;
    SetEventWhenCallbackReturns(Instance, *(HANDLE *)&(*Context)[5].rgbAtr[12]);
    if ( !LODWORD(v19->szReader) || SetThreadToken(0, *(HANDLE *)&v19[3].rgbAtr[28]) )
    {
      v21 = SCardGetStatusChangeW(*(_QWORD *)&v19[3].rgbAtr[12], 0xFFFFFFFF, Context[1], *((_DWORD *)Context + 4));
      if ( LODWORD(v19->szReader) )
      {
        if ( !RevertToSelf() )
        {
          WppTraceIndent(v20, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
          {
            v39 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_sD(
              v39,
              221,
              (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent,
              LastError);
          }
        }
      }
      if ( v21 )
      {
        WppTraceIndent(v20, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            222,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v21);
        }
      }
      *(_DWORD *)&v19[5].rgbAtr[32] = v21;
      v10 = 1;
    }
    else
    {
      WppTraceIndent(v41, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v43 = GetLastError();
        WPP_SF_sD(v42, 220, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v43);
      }
    }
    v14 = 2147483646;
LABEL_39:
    HeapFree(hHeap, 0, Context);
    goto LABEL_40;
  }
  WppTraceIndent(v9, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Context )
    goto LABEL_39;
LABEL_40:
  v26 = GetCurrentThreadId();
  v27 = `WppTraceIndent'::`2'::idxCurrentThread;
  v28 = v26;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v27 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v26;
    dword_180031404 = 0;
LABEL_46:
    v29 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v27 + 1);
    goto LABEL_47;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == v26 )
  {
    goto LABEL_43;
  }
  for ( j = 0; ; ++j )
  {
    v37 = j == 32;
    if ( j >= 0x20 )
      break;
    v38 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
    if ( v38 == v26 )
    {
      v27 = j;
      `WppTraceIndent'::`2'::idxCurrentThread = j;
      v37 = j == 32;
      break;
    }
    if ( v7 == -1 && !v38 )
      v7 = j;
  }
  if ( !v37 )
  {
LABEL_43:
    if ( v27 < 0 )
    {
      v29 = 0;
      goto LABEL_47;
    }
    goto LABEL_46;
  }
  if ( v7 != -1 )
  {
    v27 = v7;
    `WppTraceIndent'::`2'::idxCurrentThread = v7;
    *(&`WppTraceIndent'::`2'::ThreadTable + v7) = v26;
    goto LABEL_43;
  }
  v27 = -2;
  v29 = 0;
  `WppTraceIndent'::`2'::idxCurrentThread = -2;
LABEL_47:
  v30 = WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v29 >= 1 )
  {
    do
    {
      if ( StringCbCatA(v30, v28, "..") )
        break;
      ++v10;
    }
    while ( v10 <= v46 );
    v30 = WPP_GLOBAL_Control;
  }
  v31 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v31 )
  {
    ++v31;
    if ( !--v11 )
      goto LABEL_57;
  }
  v32 = (char *)HotPatchSpareGlobals - v11;
  v33 = "<";
  do
  {
    if ( !v14 )
      break;
    if ( !*v33 )
      break;
    *v32++ = *v33++;
    --v14;
    --v11;
  }
  while ( v11 );
  v34 = v32 - 1;
  if ( v11 )
    v34 = v32;
  *v34 = 0;
LABEL_57:
  if ( v27 >= 0 )
  {
    v35 = 8LL * v27;
    v24 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v35 + 4))-- == 1;
    if ( v24 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v35) = 0;
  }
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v30 != (STRSAFE_LPSTR)&WPP_GLOBAL_Control && (v30[28] & 2) != 0 && (unsigned __int8)v30[25] >= 5u )
    WPP_SF_s(
      *((_QWORD *)v30 + 2),
      223,
      &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      &`WppTraceIndent'::`2'::szIndentPrefix);
}

```

## disassembly

```asm
0x18000bfe0  mov     rax, rsp
0x18000bfe3  sub     rsp, 58h
0x18000bfe7  mov     [rax+8], rbx
0x18000bfeb  mov     rbx, rdx
0x18000bfee  mov     [rax+18h], rbp
0x18000bff2  mov     [rax+20h], rsi
0x18000bff6  mov     [rax-8], rdi
0x18000bffa  mov     rdi, rcx
0x18000bffd  mov     [rax-10h], r12
0x18000c001  mov     [rax-18h], r13
0x18000c005  mov     [rax-20h], r14
0x18000c009  mov     [rax-28h], r15
0x18000c00d  call    cs:__imp_GetCurrentThreadId
0x18000c013  movsxd  rdx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c01a  lea     r9, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000c021  mov     r12d, 0FFFFFFFFh
0x18000c027  xor     r15d, r15d
0x18000c02a  mov     r8d, eax
0x18000c02d  cmp     edx, r12d
0x18000c030  jz      short loc_18000C04E
0x18000c032  cmp     edx, 0FFFFFFFEh
0x18000c035  jz      loc_18000C190
0x18000c03b  cmp     [r9+rdx*8], eax
0x18000c03f  jnz     loc_18000C190
0x18000c045  test    edx, edx
0x18000c047  jns     short loc_18000C065
0x18000c049  mov     r10d, r15d
0x18000c04c  jmp     short loc_18000C072
0x18000c04e  mov     edx, r15d; cbDest
0x18000c051  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r8d; `WppTraceIndent'::`2'::ThreadTable
0x18000c058  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c05e  mov     cs:dword_180031404, r15d
0x18000c065  movsxd  rax, edx
0x18000c068  inc     dword ptr [r9+rax*8+4]
0x18000c06d  mov     r10d, [r9+rax*8+4]
0x18000c072  mov     rcx, cs:WPP_GLOBAL_Control; pszDest
0x18000c079  mov     ebp, 1
0x18000c07e  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000c085  test    byte ptr [rcx+1Ch], 2
0x18000c089  jnz     loc_18000C52C
0x18000c08f  mov     r14d, 100h
0x18000c095  lea     r11, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000c09c  mov     edx, r14d
0x18000c09f  mov     rax, r11
0x18000c0a2  cmp     byte ptr [rax], 0
0x18000c0a5  lea     r13, HotPatchSpareGlobals
0x18000c0ac  mov     esi, 7FFFFFFEh
0x18000c0b1  jnz     loc_18000C509
0x18000c0b7  mov     r10, r13
0x18000c0ba  lea     r9, asc_180027E34; ">"
0x18000c0c1  sub     r10, rdx
0x18000c0c4  mov     r8d, esi
0x18000c0c7  test    rdx, rdx
0x18000c0ca  jz      short loc_18000C0EA
0x18000c0cc  test    r8, r8
0x18000c0cf  jz      short loc_18000C0EA
0x18000c0d1  movzx   eax, byte ptr [r9]
0x18000c0d5  test    al, al
0x18000c0d7  jz      short loc_18000C0EA
0x18000c0d9  mov     [r10], al
0x18000c0dc  inc     r9
0x18000c0df  inc     r10
0x18000c0e2  dec     r8
0x18000c0e5  sub     rdx, rbp
0x18000c0e8  jnz     short loc_18000C0CC
0x18000c0ea  test    rdx, rdx
0x18000c0ed  lea     rax, [r10-1]
0x18000c0f1  cmovnz  rax, r10
0x18000c0f5  mov     byte ptr [rax], 0
0x18000c0f8  mov     cs:WPP_pszIndent, r11
0x18000c0ff  lea     rax, WPP_GLOBAL_Control
0x18000c106  cmp     rcx, rax
0x18000c109  jnz     loc_18000C42F
0x18000c10f  test    rbx, rbx
0x18000c112  jz      loc_18000C1F1
0x18000c118  cmp     qword ptr [rbx], 0
0x18000c11c  jz      loc_18000C1F1
0x18000c122  mov     rcx, rdi; pci
0x18000c125  call    cs:__imp_CallbackMayRunLong
0x18000c12b  mov     rsi, [rbx]
0x18000c12e  mov     rcx, rdi; pci
0x18000c131  mov     rdx, [rsi+168h]; evt
0x18000c138  call    cs:__imp_SetEventWhenCallbackReturns
0x18000c13e  cmp     dword ptr [rsi], 0
0x18000c141  jnz     loc_18000C460
0x18000c147  mov     r9d, [rbx+10h]; cReaders
0x18000c14b  mov     edx, 0FFFFFFFFh; dwTimeout
0x18000c150  mov     r8, [rbx+8]; rgReaderStates
0x18000c154  mov     rcx, [rsi+0E8h]; hContext
0x18000c15b  call    cs:__imp_SCardGetStatusChangeW
0x18000c161  cmp     dword ptr [rsi], 0
0x18000c164  mov     ebp, eax
0x18000c166  jnz     loc_18000C3BE
0x18000c16c  test    ebp, ebp
0x18000c16e  jnz     loc_18000C566
0x18000c174  lea     rdi, WPP_GLOBAL_Control
0x18000c17b  mov     [rsi+17Ch], ebp
0x18000c181  mov     ebp, 1
0x18000c186  mov     esi, 7FFFFFFEh
0x18000c18b  jmp     loc_18000C217
0x18000c190  mov     r10d, r12d
0x18000c193  mov     ecx, r15d
0x18000c196  cmp     ecx, 20h ; ' '
0x18000c199  jnb     short loc_18000C1D0
0x18000c19b  movsxd  rax, ecx
0x18000c19e  mov     r9d, [r9+rax*8]
0x18000c1a2  cmp     r9d, r8d
0x18000c1a5  jz      short loc_18000C1BE
0x18000c1a7  cmp     r10d, r12d
0x18000c1aa  jnz     short loc_18000C1B3
0x18000c1ac  test    r9d, r9d
0x18000c1af  cmovz   r10d, ecx
0x18000c1b3  inc     ecx
0x18000c1b5  lea     r9, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000c1bc  jmp     short loc_18000C196
0x18000c1be  mov     edx, ecx
0x18000c1c0  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c1c6  lea     r9, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000c1cd  cmp     ecx, 20h ; ' '
0x18000c1d0  jnz     loc_18000C045
0x18000c1d6  cmp     r10d, r12d
0x18000c1d9  jnz     loc_18000C4D5
0x18000c1df  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, 0FFFFFFFEh; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c1e9  mov     r10d, r15d
0x18000c1ec  jmp     loc_18000C072
0x18000c1f1  mov     edx, 2
0x18000c1f6  call    WppTraceIndent
0x18000c1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c202  lea     rdi, WPP_GLOBAL_Control
0x18000c209  cmp     rcx, rdi
0x18000c20c  jnz     loc_18000C5C0
0x18000c212  test    rbx, rbx
0x18000c215  jz      short loc_18000C229
0x18000c217  mov     rcx, cs:hHeap; hHeap
0x18000c21e  mov     r8, rbx; lpMem
0x18000c221  xor     edx, edx; dwFlags
0x18000c223  call    cs:__imp_HeapFree
0x18000c229  call    cs:__imp_GetCurrentThreadId
0x18000c22f  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c236  lea     rbx, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000c23d  mov     edx, eax; cbDest
0x18000c23f  cmp     r10d, r12d
0x18000c242  jz      short loc_18000C262
0x18000c244  cmp     r10d, 0FFFFFFFEh
0x18000c248  jz      loc_18000C33E
0x18000c24e  cmp     [rbx+r10*8], eax
0x18000c252  jnz     loc_18000C33E
0x18000c258  test    r10d, r10d
0x18000c25b  jns     short loc_18000C279
0x18000c25d  mov     r11d, r15d
0x18000c260  jmp     short loc_18000C281
0x18000c262  mov     r10d, r15d
0x18000c265  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r15d; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c26c  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::ThreadTable
0x18000c272  mov     cs:dword_180031404, r15d
0x18000c279  movsxd  rax, r10d
0x18000c27c  mov     r11d, [rbx+rax*8+4]
0x18000c281  mov     rcx, cs:WPP_GLOBAL_Control; pszDest
0x18000c288  mov     r12, [rsp+58h+var_10]
0x18000c28d  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000c294  test    byte ptr [rcx+1Ch], 2
0x18000c298  jnz     loc_18000C5F5
0x18000c29e  mov     rbp, [rsp+58h+arg_10]
0x18000c2a3  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000c2aa  mov     rax, r9
0x18000c2ad  cmp     byte ptr [rax], 0
0x18000c2b0  jnz     loc_18000C51A
0x18000c2b6  sub     r13, r14
0x18000c2b9  lea     rax, asc_180027E38; "<"
0x18000c2c0  test    r14, r14
0x18000c2c3  jz      short loc_18000C2E4
0x18000c2c5  test    rsi, rsi
0x18000c2c8  jz      short loc_18000C2E4
0x18000c2ca  movzx   edx, byte ptr [rax]
0x18000c2cd  test    dl, dl
0x18000c2cf  jz      short loc_18000C2E4
0x18000c2d1  mov     [r13+0], dl
0x18000c2d5  inc     rax
0x18000c2d8  inc     r13
0x18000c2db  dec     rsi
0x18000c2de  sub     r14, 1
0x18000c2e2  jnz     short loc_18000C2C5
0x18000c2e4  test    r14, r14
0x18000c2e7  lea     rax, [r13-1]
0x18000c2eb  cmovnz  rax, r13
0x18000c2ef  mov     byte ptr [rax], 0
0x18000c2f2  mov     r14, [rsp+58h+var_20]
0x18000c2f7  mov     r13, [rsp+58h+var_18]
0x18000c2fc  mov     rsi, [rsp+58h+arg_18]
0x18000c301  test    r10d, r10d
0x18000c304  jns     short loc_18000C326
0x18000c306  mov     r15, [rsp+58h+var_28]
0x18000c30b  mov     rbx, [rsp+58h+arg_0]
0x18000c310  mov     cs:WPP_pszIndent, r9
0x18000c317  cmp     rcx, rdi
0x18000c31a  mov     rdi, [rsp+58h+var_8]
0x18000c31f  jnz     short loc_18000C394
0x18000c321  add     rsp, 58h
0x18000c325  retn
0x18000c326  movsxd  rax, r10d
0x18000c329  lea     rdx, ds:0[rax*8]
0x18000c331  sub     dword ptr [rdx+rbx+4], 1
0x18000c336  jnz     short loc_18000C306
0x18000c338  mov     [rdx+rbx], r15d
0x18000c33c  jmp     short loc_18000C306
0x18000c33e  mov     ecx, r15d
0x18000c341  cmp     ecx, 20h ; ' '
0x18000c344  jnb     short loc_18000C36F
0x18000c346  movsxd  rax, ecx
0x18000c349  mov     r8d, [rbx+rax*8]
0x18000c34d  cmp     r8d, edx
0x18000c350  jz      short loc_18000C363
0x18000c352  cmp     r12d, 0FFFFFFFFh
0x18000c356  jnz     short loc_18000C35F
0x18000c358  test    r8d, r8d
0x18000c35b  cmovz   r12d, ecx
0x18000c35f  inc     ecx
0x18000c361  jmp     short loc_18000C341
0x18000c363  mov     r10d, ecx
0x18000c366  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c36c  cmp     ecx, 20h ; ' '
0x18000c36f  jnz     loc_18000C258
0x18000c375  cmp     r12d, 0FFFFFFFFh
0x18000c379  jnz     loc_18000C4EF
0x18000c37f  mov     r10d, 0FFFFFFFEh
0x18000c385  mov     r11d, r15d
0x18000c388  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c38f  jmp     loc_18000C281
0x18000c394  test    byte ptr [rcx+1Ch], 2
0x18000c398  jz      short loc_18000C321
0x18000c39a  cmp     byte ptr [rcx+19h], 5
0x18000c39e  jb      loc_18000C321
0x18000c3a4  mov     rcx, [rcx+10h]
0x18000c3a8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c3af  mov     edx, 0DFh
0x18000c3b4  call    WPP_SF_s
0x18000c3b9  jmp     loc_18000C321
0x18000c3be  call    cs:__imp_RevertToSelf
0x18000c3c4  test    eax, eax
0x18000c3c6  jnz     loc_18000C16C
0x18000c3cc  mov     edx, 2
0x18000c3d1  call    WppTraceIndent
0x18000c3d6  mov     rdi, cs:WPP_GLOBAL_Control
0x18000c3dd  lea     rax, WPP_GLOBAL_Control
0x18000c3e4  cmp     rdi, rax
0x18000c3e7  jz      loc_18000C16C
0x18000c3ed  test    byte ptr [rdi+1Ch], 1
0x18000c3f1  jz      loc_18000C16C
0x18000c3f7  cmp     byte ptr [rdi+19h], 3
0x18000c3fb  jb      loc_18000C16C
0x18000c401  mov     rdi, [rdi+10h]
0x18000c405  call    cs:__imp_GetLastError
0x18000c40b  mov     r9, cs:WPP_pszIndent
0x18000c412  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c419  mov     edx, 0DDh
0x18000c41e  mov     [rsp+58h+var_38], eax
0x18000c422  mov     rcx, rdi
0x18000c425  call    WPP_SF_sD
0x18000c42a  jmp     loc_18000C16C
0x18000c42f  test    byte ptr [rcx+1Ch], 2
0x18000c433  jz      loc_18000C10F
0x18000c439  cmp     byte ptr [rcx+19h], 5
0x18000c43d  jb      loc_18000C10F
0x18000c443  mov     rcx, [rcx+10h]
0x18000c447  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c44e  mov     edx, 0DAh
0x18000c453  mov     r9, r11
0x18000c456  call    WPP_SF_s
0x18000c45b  jmp     loc_18000C10F
0x18000c460  mov     rdx, [rsi+0F8h]; Token
0x18000c467  xor     ecx, ecx; Thread
0x18000c469  call    cs:__imp_SetThreadToken
0x18000c46f  test    eax, eax
0x18000c471  jnz     loc_18000C147
0x18000c477  mov     edx, 2
0x18000c47c  call    WppTraceIndent
0x18000c481  mov     rdi, cs:WPP_GLOBAL_Control
0x18000c488  lea     rax, WPP_GLOBAL_Control
0x18000c48f  cmp     rdi, rax
0x18000c492  jz      short loc_18000C4C9
0x18000c494  test    [rdi+1Ch], bpl
0x18000c498  jz      short loc_18000C4C9
0x18000c49a  cmp     byte ptr [rdi+19h], 3
0x18000c49e  jb      short loc_18000C4C9
0x18000c4a0  mov     rdi, [rdi+10h]
0x18000c4a4  call    cs:__imp_GetLastError
0x18000c4aa  mov     r9, cs:WPP_pszIndent
0x18000c4b1  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c4b8  mov     edx, 0DCh
0x18000c4bd  mov     [rsp+58h+var_38], eax
0x18000c4c1  mov     rcx, rdi
0x18000c4c4  call    WPP_SF_sD
0x18000c4c9  lea     rdi, WPP_GLOBAL_Control
0x18000c4d0  jmp     loc_18000C186
0x18000c4d5  movsxd  rax, r10d
0x18000c4d8  mov     edx, r10d
0x18000c4db  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000c4e1  mov     [r9+rax*8], r8d
0x18000c4e5  mov     [r9+rax*8+4], r15d
0x18000c4ea  jmp     loc_18000C045
  ... truncated ...
```
