# AslLogDebugVPrintf

- ea: `0x1800092ac`
- end: `0x1800098a5`
- name: `AslLogDebugVPrintf`
- size: `1529`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800089d0`

## callees

- `0x180004b60`
- `0x180005430`
- `0x1800054a0`
- `0x180007200`
- `0x180007668`
- `0x1800076f8`
- `0x1800081f6`
- `0x180008202`
- `0x18000820e`
- `0x18000827a`
- `0x180008bbc`
- `0x180008c40`
- `0x180008d4c`
- `0x180008e54`
- `0x180008ea8`
- `0x180008f00`
- `0x18000908c`
- `0x1800092ac`
- `0x18000c030`
- `0x18000c0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009856`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009856`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800093b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800093b1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009875`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009875`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000986b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000986b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800096a5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800096a5`

## string_xrefs

- `0x1800093a8`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 a1, int a2, const char *a3, __int64 a4, char *a5, char *a6)
{
  HMODULE *v6; // r15
  HMODULE v9; // rax
  HMODULE *v10; // rbx
  int v11; // ecx
  unsigned int v12; // r12d
  unsigned __int64 v13; // r14
  FARPROC ConstructPartialMsgIfA; // rax
  HMODULE v15; // rcx
  HANDLE FileW_0; // rax
  DWORD LastError_0; // eax
  char v18; // al
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rcx
  int v21; // eax
  unsigned __int16 *v22; // rbx
  unsigned __int64 v23; // rdi
  int v24; // eax
  unsigned __int64 i; // rax
  unsigned __int16 v26; // cx
  unsigned __int64 v27; // rbx
  int v28; // eax
  unsigned __int64 v29; // r10
  CHAR v30; // al
  int v31; // ecx
  const char *v32; // rax
  __int64 v33; // rax
  char *v34; // rdi
  unsigned __int64 v35; // rbx
  int v36; // eax
  __int64 v37; // r8
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rax
  char v40; // cl
  unsigned __int64 v41; // rax
  char *v42; // rcx
  unsigned __int64 v43; // rcx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char v45; // [rsp+50h] [rbp-B0h]
  char v46; // [rsp+51h] [rbp-AFh]
  int v47; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v49; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp-98h]
  const char *v51; // [rsp+70h] [rbp-90h]
  char *v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  char *v54; // [rsp+88h] [rbp-78h]
  CHAR MultiByteStr[1024]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR WideCharStr[1024]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v57[1024]; // [rsp+C90h] [rbp+B90h] BYREF

  v6 = (HMODULE *)g_PcapLogDebug;
  v53 = a4;
  v51 = a3;
  v54 = a5;
  v52 = a6;
  if ( g_PcapLogDebug )
  {
    dwErrCode = GetLastError_0();
    MultiByteStr[0] = 0;
    if ( a2 != 3 || (v9 = *v6, ((_BYTE)(*v6)[20] & 0x10) != 0) )
    {
      v9 = *v6;
      v45 = 1;
    }
    else
    {
      v45 = 0;
    }
    v10 = v6 + 90;
    v11 = (_DWORD)v9[20] & 0x100;
    v12 = 3;
    v47 = v11;
    if ( a2 < 3 )
      v12 = a2;
    if ( !*v10 && qword_180014808 )
    {
      dword_180014814 = 0;
      qword_180014808 = 0;
      WdsSetupLogMessageA = 0;
    }
    v13 = -1;
    if ( !dword_180014814 )
    {
      dword_180014814 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", v6 + 90) )
      {
        ConstructPartialMsgIfA = GetProcAddress_0(*v10, "ConstructPartialMsgIfA");
        v15 = *v10;
        qword_180014808 = (__int64)ConstructPartialMsgIfA;
        WdsSetupLogMessageA = (__int64)GetProcAddress_0(v15, "WdsSetupLogMessageA");
      }
      FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW_0 == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v11 = v47;
        if ( LastError_0 == 231 )
          dword_180014804 = 1;
      }
      else
      {
        dword_180014804 = 1;
        CloseHandle_0(FileW_0);
        v11 = v47;
      }
    }
    if ( !qword_180014808 || (v18 = 1, !WdsSetupLogMessageA) )
      v18 = 0;
    v46 = v18;
    if ( v45 || a2 == 1 || v18 || dword_180014804 || v11 )
    {
      v48 = 1022;
      v49 = WideCharStr;
      if ( (int)RtlStringCchPrintfW(v57, 0x400u, L"%hs", a5) < 0 )
        RtlStringCchCopyW(v57, 0x400u, L"ASL_LOG FAIL: ");
      v19 = v57[0];
      if ( v57[0] )
      {
        v20 = v57;
        do
        {
          if ( v19 == 37 )
          {
            do
            {
              do
                ++v20;
              while ( *v20 == 46 );
            }
            while ( (unsigned __int16)(*v20 - 48) <= 9u );
            if ( *v20 == 115 )
            {
              *v20 = 83;
            }
            else if ( *v20 == 83 )
            {
              *v20 = 115;
            }
          }
          v19 = *++v20;
        }
        while ( *v20 );
      }
      v21 = a4;
      if ( a4 == -1 )
        v21 = 0;
      if ( (int)RtlStringCchPrintfExW(
                  WideCharStr,
                  0x3FEu,
                  &v49,
                  &v48,
                  0x100u,
                  L"%hs,%hs,%d,",
                  (&off_18000E4A8)[2 * (int)v12],
                  v51,
                  v21) < 0 )
        RtlStringCchCopyW(WideCharStr, 0x400u, L"ASL_LOG FAIL: ");
      v22 = v49;
      v23 = v48;
      v24 = RtlStringCchVPrintfExW(v49, v48, &v49, &v48, dwCreationDisposition, v57, v52);
      if ( (int)(v24 + 0x80000000) >= 0 && v24 != -2147483643 )
        RtlStringCchCopyW(v49, v48, L"Message too long!");
      for ( i = 0; i < v23; ++i )
      {
        v26 = v22[i];
        if ( !v26 )
          break;
        if ( v26 == 10 || v26 == 13 )
        {
          v22[i] = 35;
        }
        else if ( v26 == 44 )
        {
          v22[i] = 95;
        }
      }
      RtlStringCchCatW(v22, v23, L"\r\n");
      v27 = -1;
      do
        ++v27;
      while ( WideCharStr[v27] );
      if ( dword_180014804 )
        AslLogpWritePipe(WideCharStr, 2 * v27);
      v28 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0);
      LODWORD(v29) = 0;
      if ( v28 )
      {
        v30 = MultiByteStr[0];
      }
      else
      {
        v30 = 0;
        MultiByteStr[0] = 0;
      }
      if ( !v30 )
      {
        v31 = v53;
        if ( v53 == -1 )
          v31 = 0;
        v32 = v51;
        if ( !v51 )
          v32 = (const char *)&dword_18000F424;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v27, "%s,%s,%d,", (&off_18000E4A8)[2 * (int)v12], v32, v31) < 0 )
          RtlStringCchCopyA(MultiByteStr, v27, "ASL_LOG FAIL: ");
        v33 = -1;
        do
          ++v33;
        while ( MultiByteStr[v33] );
        v34 = &MultiByteStr[v33];
        v35 = v27 - v33;
        v36 = RtlStringCchVPrintfA(&MultiByteStr[v33], v35, v54, v52);
        v29 = 0;
        if ( v36 < 0 )
          RtlStringCchCopyA(v34, v35, "Message too long!");
        v38 = v35 + 2;
        v39 = v29;
        if ( v35 != -2 )
        {
          do
          {
            v40 = v34[v39];
            if ( !v40 )
              break;
            if ( v40 == 10 || v40 == 13 )
            {
              v34[v39] = 35;
            }
            else if ( v40 == 44 )
            {
              v34[v39] = 95;
            }
            ++v39;
          }
          while ( v39 < v38 );
          if ( v38 <= 0x7FFFFFFF )
          {
            v41 = v35 + 2;
            v42 = v34;
            do
            {
              if ( *v42 == (_BYTE)v29 )
                break;
              ++v42;
              --v41;
            }
            while ( v41 );
            v43 = v41 ? v38 - v41 : v29;
            if ( v41 )
            {
              RtlStringCopyWorkerA(&v34[v43], v38 - v43, v37, "\r\n");
              LODWORD(v29) = 0;
            }
          }
        }
      }
      do
        ++v13;
      while ( MultiByteStr[v13] != (_BYTE)v29 );
      if ( v45 != (_BYTE)v29 || v47 != (_DWORD)v29 )
        AslLogpWriteLog((struct _ASL_LOG *)v6, MultiByteStr, v13);
      if ( a2 == 1 )
        AslLogpWriteEtw((__int64)v6, v12, (__int64)MultiByteStr);
      if ( v46 )
        AslLogpWritePanther(v6, v12, v51, v53, MultiByteStr);
      SetLastError(dwErrCode);
      if ( v12 == 1 && ((_BYTE)(*v6)[20] & 2) != 0 )
      {
        if ( IsDebuggerPresent() )
          DebugBreak();
      }
    }
  }
}

```

## disassembly

```asm
0x1800092ac  mov     [rsp-8+arg_0], rbx
0x1800092b1  push    rbp
0x1800092b2  push    rsi
0x1800092b3  push    rdi
0x1800092b4  push    r12
0x1800092b6  push    r13
0x1800092b8  push    r14
0x1800092ba  push    r15
0x1800092bc  lea     rbp, [rsp-13A0h]
0x1800092c4  mov     eax, 14A0h
0x1800092c9  call    _alloca_probe
0x1800092ce  sub     rsp, rax
0x1800092d1  mov     rax, cs:__security_cookie
0x1800092d8  xor     rax, rsp
0x1800092db  mov     [rbp+13D0h+var_40], rax
0x1800092e2  mov     r15, cs:?g_PcapLogDebug@@3_KA; unsigned __int64 g_PcapLogDebug
0x1800092e9  xor     r14d, r14d
0x1800092ec  mov     rsi, [rbp+13D0h+arg_20]
0x1800092f3  mov     rdi, r9
0x1800092f6  mov     rax, [rbp+13D0h+arg_28]
0x1800092fd  mov     r13d, edx
0x180009300  mov     [rbp+13D0h+var_1450], r9
0x180009304  mov     [rsp+14D0h+var_1460], r8
0x180009309  mov     [rbp+13D0h+var_1448], rsi
0x18000930d  mov     [rsp+14D0h+var_1458], rax
0x180009312  test    r15, r15
0x180009315  jz      loc_18000987B
0x18000931b  call    GetLastError_0
0x180009320  mov     [rsp+14D0h+dwErrCode], eax
0x180009324  mov     [rbp+13D0h+MultiByteStr], r14b
0x180009328  cmp     r13d, 3
0x18000932c  jnz     short loc_18000933E
0x18000932e  mov     rax, [r15]
0x180009331  test    byte ptr [rax+50h], 10h
0x180009335  jnz     short loc_18000933E
0x180009337  mov     [rsp+14D0h+var_1480], r14b
0x18000933c  jmp     short loc_180009346
0x18000933e  mov     rax, [r15]
0x180009341  mov     [rsp+14D0h+var_1480], 1
0x180009346  mov     ecx, [rax+50h]
0x180009349  lea     rbx, [r15+2D0h]
0x180009350  and     ecx, 100h
0x180009356  mov     r12d, 3
0x18000935c  cmp     r13d, r12d
0x18000935f  mov     [rsp+14D0h+var_147C], ecx
0x180009363  cmovl   r12d, r13d
0x180009367  cmp     [rbx], r14
0x18000936a  jnz     short loc_18000938A
0x18000936c  cmp     cs:qword_180014808, r14
0x180009373  jz      short loc_18000938A
0x180009375  mov     cs:dword_180014814, r14d
0x18000937c  mov     cs:qword_180014808, r14
0x180009383  mov     cs:WdsSetupLogMessageA, r14
0x18000938a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000938e  cmp     cs:dword_180014814, 0
0x180009395  jnz     loc_18000944A
0x18000939b  mov     r8, rbx; phModule
0x18000939e  mov     cs:dword_180014814, 1
0x1800093a8  lea     rdx, aWdscoreDll; "wdscore.dll"
0x1800093af  xor     ecx, ecx; dwFlags
0x1800093b1  call    cs:__imp_GetModuleHandleExA
0x1800093b7  test    eax, eax
0x1800093b9  jz      short loc_1800093E7
0x1800093bb  mov     rcx, [rbx]; hModule
0x1800093be  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x1800093c5  call    GetProcAddress_0
0x1800093ca  mov     rcx, [rbx]; hModule
0x1800093cd  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1800093d4  mov     cs:qword_180014808, rax
0x1800093db  call    GetProcAddress_0
0x1800093e0  mov     cs:WdsSetupLogMessageA, rax
0x1800093e7  xor     ebx, ebx
0x1800093e9  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1800093f0  mov     [rsp+14D0h+hTemplateFile], rbx; hTemplateFile
0x1800093f5  xor     r9d, r9d; lpSecurityAttributes
0x1800093f8  mov     [rsp+14D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800093fc  xor     r8d, r8d; dwShareMode
0x1800093ff  mov     edx, 40000000h; dwDesiredAccess
0x180009404  mov     [rsp+14D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000940c  call    CreateFileW_0
0x180009411  cmp     rax, r14
0x180009414  jnz     short loc_180009432
0x180009416  call    GetLastError_0
0x18000941b  mov     ecx, [rsp+14D0h+var_147C]
0x18000941f  cmp     eax, 0E7h
0x180009424  jnz     short loc_18000944C
0x180009426  mov     cs:dword_180014804, 1
0x180009430  jmp     short loc_18000944C
0x180009432  mov     rcx, rax; hObject
0x180009435  mov     cs:dword_180014804, 1
0x18000943f  call    CloseHandle_0
0x180009444  mov     ecx, [rsp+14D0h+var_147C]
0x180009448  jmp     short loc_18000944C
0x18000944a  xor     ebx, ebx
0x18000944c  cmp     cs:qword_180014808, rbx
0x180009453  jz      short loc_180009460
0x180009455  cmp     cs:WdsSetupLogMessageA, rbx
0x18000945c  mov     al, 1
0x18000945e  jnz     short loc_180009462
0x180009460  mov     al, bl
0x180009462  mov     [rsp+14D0h+var_147F], al
0x180009466  cmp     [rsp+14D0h+var_1480], bl
0x18000946a  jnz     short loc_180009486
0x18000946c  cmp     r13d, 1
0x180009470  jz      short loc_180009486
0x180009472  test    al, al
0x180009474  jnz     short loc_180009486
0x180009476  cmp     cs:dword_180014804, ebx
0x18000947c  jnz     short loc_180009486
0x18000947e  test    ecx, ecx
0x180009480  jz      loc_18000987B
0x180009486  mov     r9, rsi
0x180009489  mov     [rsp+14D0h+var_1478], 3FEh
0x180009492  lea     rax, [rbp+13D0h+WideCharStr]
0x180009499  mov     esi, 400h
0x18000949e  mov     edx, esi; unsigned __int64
0x1800094a0  mov     [rsp+14D0h+var_1470], rax
0x1800094a5  lea     r8, aHs_0; "%hs"
0x1800094ac  lea     rcx, [rbp+13D0h+var_840]; unsigned __int16 *
0x1800094b3  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800094b8  test    eax, eax
0x1800094ba  jns     short loc_1800094D1
0x1800094bc  lea     r8, aAslLogFail; "ASL_LOG FAIL: "
0x1800094c3  mov     edx, esi; unsigned __int64
0x1800094c5  lea     rcx, [rbp+13D0h+var_840]; unsigned __int16 *
0x1800094cc  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800094d1  movzx   eax, [rbp+13D0h+var_840]
0x1800094d8  test    ax, ax
0x1800094db  jz      short loc_18000952A
0x1800094dd  mov     edx, 53h ; 'S'
0x1800094e2  lea     rcx, [rbp+13D0h+var_840]
0x1800094e9  lea     r8d, [rdx+20h]
0x1800094ed  cmp     ax, 25h ; '%'
0x1800094f1  jnz     short loc_18000951E
0x1800094f3  add     rcx, 2
0x1800094f7  cmp     word ptr [rcx], 2Eh ; '.'
0x1800094fb  jz      short loc_1800094F3
0x1800094fd  movzx   eax, word ptr [rcx]
0x180009500  sub     ax, 30h ; '0'
0x180009504  cmp     ax, 9
0x180009508  jbe     short loc_1800094F3
0x18000950a  cmp     [rcx], r8w
0x18000950e  jnz     short loc_180009515
0x180009510  mov     [rcx], dx
0x180009513  jmp     short loc_18000951E
0x180009515  cmp     [rcx], dx
0x180009518  jnz     short loc_18000951E
0x18000951a  mov     [rcx], r8w
0x18000951e  add     rcx, 2
0x180009522  movzx   eax, word ptr [rcx]
0x180009525  test    ax, ax
0x180009528  jnz     short loc_1800094ED
0x18000952a  mov     eax, edi
0x18000952c  cmp     rdi, r14
0x18000952f  jnz     short loc_180009533
0x180009531  mov     eax, ebx
0x180009533  mov     [rsp+14D0h+var_1490], eax
0x180009537  lea     rcx, off_18000E4A8; "PRINT"
0x18000953e  mov     rax, [rsp+14D0h+var_1460]
0x180009543  lea     r9, [rsp+14D0h+var_1478]; unsigned __int64 *
0x180009548  mov     [rsp+14D0h+lpUsedDefaultChar], rax
0x18000954d  lea     r8, [rsp+14D0h+var_1470]; unsigned __int16 **
0x180009552  movsxd  rsi, r12d
0x180009555  mov     edx, 3FEh; unsigned __int64
0x18000955a  add     rsi, rsi
0x18000955d  mov     rax, [rcx+rsi*8]
0x180009561  lea     rcx, [rbp+13D0h+WideCharStr]; unsigned __int16 *
0x180009568  mov     [rsp+14D0h+hTemplateFile], rax
0x18000956d  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x180009574  mov     qword ptr [rsp+14D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180009579  mov     [rsp+14D0h+dwCreationDisposition], 100h; unsigned int
0x180009581  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180009586  test    eax, eax
0x180009588  jns     short loc_1800095A2
0x18000958a  lea     r8, aAslLogFail; "ASL_LOG FAIL: "
0x180009591  mov     edx, 400h; unsigned __int64
0x180009596  lea     rcx, [rbp+13D0h+WideCharStr]; unsigned __int16 *
0x18000959d  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800095a2  mov     rax, [rsp+14D0h+var_1458]
0x1800095a7  lea     r9, [rsp+14D0h+var_1478]; unsigned __int64 *
0x1800095ac  mov     rbx, [rsp+14D0h+var_1470]
0x1800095b1  lea     r8, [rsp+14D0h+var_1470]; unsigned __int16 **
0x1800095b6  mov     rdi, [rsp+14D0h+var_1478]
0x1800095bb  mov     rcx, rbx; unsigned __int16 *
0x1800095be  mov     [rsp+14D0h+hTemplateFile], rax; char *
0x1800095c3  mov     rdx, rdi; unsigned __int64
0x1800095c6  lea     rax, [rbp+13D0h+var_840]
0x1800095cd  mov     qword ptr [rsp+14D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800095d2  call    ?RtlStringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; RtlStringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x1800095d7  mov     edx, 80000000h
0x1800095dc  lea     ecx, [rax+rdx]
0x1800095df  test    edx, ecx
0x1800095e1  jnz     short loc_180009600
0x1800095e3  cmp     eax, 80000005h
0x1800095e8  jz      short loc_180009600
0x1800095ea  mov     rdx, [rsp+14D0h+var_1478]; unsigned __int64
0x1800095ef  lea     r8, aMessageTooLong; "Message too long!"
0x1800095f6  mov     rcx, [rsp+14D0h+var_1470]; unsigned __int16 *
0x1800095fb  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009600  xor     edx, edx
0x180009602  mov     eax, edx
0x180009604  test    rdi, rdi
0x180009607  jz      short loc_18000963A
0x180009609  movzx   ecx, word ptr [rbx+rax*2]
0x18000960d  test    cx, cx
0x180009610  jz      short loc_18000963A
0x180009612  cmp     cx, 0Ah
0x180009616  jz      short loc_18000962C
0x180009618  cmp     cx, 0Dh
0x18000961c  jz      short loc_18000962C
0x18000961e  cmp     cx, 2Ch ; ','
0x180009622  jnz     short loc_180009632
0x180009624  mov     word ptr [rbx+rax*2], 5Fh ; '_'
0x18000962a  jmp     short loc_180009632
0x18000962c  mov     word ptr [rbx+rax*2], 23h ; '#'
0x180009632  inc     rax
0x180009635  cmp     rax, rdi
0x180009638  jb      short loc_180009609
0x18000963a  lea     r8, asc_18000FBFC; "\r\n"
0x180009641  mov     rdx, rdi; unsigned __int64
0x180009644  mov     rcx, rbx; unsigned __int16 *
0x180009647  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000964c  lea     rax, [rbp+13D0h+WideCharStr]
0x180009653  mov     rbx, r14
0x180009656  xor     edi, edi
0x180009658  inc     rbx
0x18000965b  cmp     [rax+rbx*2], di
0x18000965f  jnz     short loc_180009658
0x180009661  cmp     cs:dword_180014804, edi
0x180009667  jz      short loc_180009679
0x180009669  lea     rdx, [rbx+rbx]; nNumberOfBytesToWrite
0x18000966d  lea     rcx, [rbp+13D0h+WideCharStr]; lpBuffer
0x180009674  call    ?AslLogpWritePipe@@YAXPEAX_K@Z; AslLogpWritePipe(void *,unsigned __int64)
0x180009679  mov     [rsp+14D0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000967e  lea     rax, [rbp+13D0h+MultiByteStr]
0x180009682  mov     [rsp+14D0h+hTemplateFile], rdi; lpDefaultChar
0x180009687  lea     r8, [rbp+13D0h+WideCharStr]; lpWideCharStr
0x18000968e  mov     [rsp+14D0h+dwFlagsAndAttributes], 400h; cbMultiByte
0x180009696  mov     r9d, r14d; cchWideChar
0x180009699  xor     edx, edx; dwFlags
0x18000969b  mov     qword ptr [rsp+14D0h+dwCreationDisposition], rax; lpMultiByteStr
0x1800096a0  mov     ecx, 0FDE9h; CodePage
0x1800096a5  call    cs:__imp_WideCharToMultiByte
0x1800096ab  xor     r10d, r10d
0x1800096ae  test    eax, eax
0x1800096b0  jnz     short loc_1800096BA
0x1800096b2  mov     al, r10b
0x1800096b5  mov     [rbp+13D0h+MultiByteStr], al
0x1800096b8  jmp     short loc_1800096BD
0x1800096ba  mov     al, [rbp+13D0h+MultiByteStr]
0x1800096bd  test    al, al
0x1800096bf  jnz     loc_1800097EE
0x1800096c5  mov     rax, [rbp+13D0h+var_1450]
0x1800096c9  mov     ecx, eax
0x1800096cb  cmp     rax, r14
0x1800096ce  jnz     short loc_1800096D3
0x1800096d0  mov     ecx, r10d
0x1800096d3  mov     rdx, [rsp+14D0h+var_1460]
0x1800096d8  lea     r8, dword_18000F424
0x1800096df  test    rdx, rdx
0x1800096e2  mov     [rsp+14D0h+dwFlagsAndAttributes], ecx
0x1800096e6  mov     rax, rdx
0x1800096e9  lea     r9, off_18000E4A8; "PRINT"
0x1800096f0  mov     r9, [r9+rsi*8]
0x1800096f4  lea     rcx, [rbp+13D0h+MultiByteStr]; char *
0x1800096f8  cmovz   rax, r8
0x1800096fc  mov     rdx, rbx; unsigned __int64
0x1800096ff  lea     r8, aSSD; "%s,%s,%d,"
0x180009706  mov     qword ptr [rsp+14D0h+dwCreationDisposition], rax
0x18000970b  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009710  test    eax, eax
0x180009712  jns     short loc_180009727
0x180009714  lea     r8, aAslLogFail_0; "ASL_LOG FAIL: "
0x18000971b  mov     rdx, rbx; unsigned __int64
0x18000971e  lea     rcx, [rbp+13D0h+MultiByteStr]; char *
0x180009722  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x180009727  lea     rcx, [rbp+13D0h+MultiByteStr]
0x18000972b  mov     rax, r14
0x18000972e  inc     rax
0x180009731  cmp     [rcx+rax], dil
0x180009735  jnz     short loc_18000972E
0x180009737  mov     r9, [rsp+14D0h+var_1458]; char *
0x18000973c  lea     rdi, [rbp+13D0h+MultiByteStr]
0x180009740  mov     r8, [rbp+13D0h+var_1448]; char *
0x180009744  add     rdi, rax
0x180009747  sub     rbx, rax
0x18000974a  mov     rcx, rdi; char *
0x18000974d  mov     rdx, rbx; unsigned __int64
0x180009750  call    ?RtlStringCchVPrintfA@@YAJPEAD_KPEBD0@Z; RtlStringCchVPrintfA(char *,unsigned __int64,char const *,char *)
0x180009755  xor     r10d, r10d
0x180009758  test    eax, eax
0x18000975a  jns     short loc_18000976E
0x18000975c  lea     r8, aMessageTooLong_0; "Message too long!"
0x180009763  mov     rdx, rbx; unsigned __int64
0x180009766  mov     rcx, rdi; char *
0x180009769  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x18000976e  lea     rdx, [rbx+2]
0x180009772  mov     rax, r10
0x180009775  test    rdx, rdx
0x180009778  jz      short loc_1800097EE
  ... truncated ...
```
