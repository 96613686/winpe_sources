# SxRotateLogs(ushort const *,ulong)

- ea: `0x180067544`
- end: `0x1800677ab`
- name: `?SxRotateLogs@@YAJPEBGK@Z`
- size: `615`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a4b0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x18001913c`
- `0x18002ce84`
- `0x180038c3c`
- `0x180043530`
- `0x1800672b0`
- `0x180067544`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006768f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006768f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180067625`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180067625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676f9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800676ef`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800676ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SxRotateLogs(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  signed int v3; // ebx
  __int16 v4; // ax
  int v5; // r14d
  const WCHAR *v6; // rsi
  DWORD LastError; // eax
  __int64 v8; // rcx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+50h] [rbp-19h] BYREF
  __int16 v13; // [rsp+54h] [rbp-15h]
  __int16 v14; // [rsp+56h] [rbp-13h]

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxRotateLogs", 0x1BAu, 1u);
  lpExistingFileName[1] = 0;
  lpExistingFileName[0] = &qword_18006F470;
  lpFileName[0] = &qword_18006F470;
  lpFileName[1] = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 450;
LABEL_24:
    v12 = v3;
    goto LABEL_25;
  }
  v12 = 0;
  v13 = 451;
  SxMergeExtraLogs(a1, v2);
  v3 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 0, L"etl");
  v12 = v3;
  v4 = 458;
  if ( v3 < 0 )
    goto LABEL_25;
  v13 = 458;
  if ( GetFileAttributesW(lpFileName[0]) == -1 && GetLastError() - 2 <= 1 )
  {
    v3 = 0;
    v12 = 0;
    v13 = 466;
    goto LABEL_26;
  }
  v5 = 4;
  v3 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 4, L"etl");
  v12 = v3;
  v4 = 471;
  if ( v3 < 0 )
  {
LABEL_25:
    v14 = v4;
    goto LABEL_26;
  }
  v6 = lpFileName[0];
  v13 = 471;
  DeleteFileW(lpFileName[0]);
  v3 = v12;
  while ( v5 )
  {
    v3 = CBsString::Format((CBsString *)lpExistingFileName, L"%s.%d.%s", a1, (unsigned int)--v5, L"etl");
    v12 = v3;
    v4 = 478;
    if ( v3 < 0 )
      goto LABEL_25;
    v13 = 478;
    if ( !MoveFileExW(lpExistingFileName[0], v6, 1u) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0x20 || (v8 = 0x100000024LL, !_bittest64(&v8, LastError)) )
      {
        if ( (int)LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v4 = 491;
        goto LABEL_24;
      }
      v12 = 0;
      v13 = 491;
    }
    SxCompressLogFile(v6);
    v12 = CBsString::Set((CBsString *)lpFileName, lpExistingFileName[0]);
    v3 = v12;
    if ( v12 < 0 )
    {
      v14 = 498;
      break;
    }
    v6 = lpFileName[0];
    v13 = 498;
  }
LABEL_26:
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180067544  push    rbp
0x180067546  push    rbx
0x180067547  push    rsi
0x180067548  push    rdi
0x180067549  push    r13
0x18006754b  push    r14
0x18006754d  lea     rbp, [rsp-2Fh]
0x180067552  sub     rsp, 98h
0x180067559  mov     rdi, rcx
0x18006755c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067563  lea     rax, WPP_GLOBAL_Control
0x18006756a  cmp     rcx, rax
0x18006756d  jz      short loc_18006758D
0x18006756f  test    dword ptr [rcx+1Ch], 20000000h
0x180067576  jz      short loc_18006758D
0x180067578  mov     rcx, [rcx+10h]
0x18006757c  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x180067583  mov     edx, 14h
0x180067588  call    WPP_SF_
0x18006758d  mov     r9d, 1; unsigned __int16
0x180067593  lea     rdx, aSxrotatelogs; "SxRotateLogs"
0x18006759a  mov     r8d, 1BAh; unsigned __int16
0x1800675a0  lea     rcx, [rbp+57h+var_70]; this
0x1800675a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800675a9  mov     [rbp+57h+var_78], 0
0x1800675b1  lea     rax, qword_18006F470
0x1800675b8  mov     [rbp+57h+lpExistingFileName], rax
0x1800675bc  mov     [rbp+57h+lpFileName], rax
0x1800675c0  mov     [rbp+57h+var_88], 0
0x1800675c8  test    rdi, rdi
0x1800675cb  jz      loc_18006776D
0x1800675d1  mov     eax, 1C3h
0x1800675d6  mov     [rbp+57h+var_70], 0
0x1800675dd  mov     rcx, rdi; unsigned __int16 *
0x1800675e0  mov     [rbp+57h+var_6C], ax
0x1800675e4  call    ?SxMergeExtraLogs@@YAJPEBGK@Z; SxMergeExtraLogs(ushort const *,ulong)
0x1800675e9  lea     rsi, aEtl; "etl"
0x1800675f0  xor     r9d, r9d
0x1800675f3  mov     r8, rdi
0x1800675f6  mov     [rsp+0C0h+var_A0], rsi
0x1800675fb  lea     rdx, aSDS; "%s.%d.%s"
0x180067602  lea     rcx, [rbp+57h+lpFileName]; this
0x180067606  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18006760b  mov     ebx, eax
0x18006760d  mov     [rbp+57h+var_70], eax
0x180067610  test    eax, eax
0x180067612  mov     eax, 1CAh
0x180067617  js      loc_18006777A
0x18006761d  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180067621  mov     [rbp+57h+var_6C], ax
0x180067625  call    cs:__imp_GetFileAttributesW
0x18006762b  cmp     eax, 0FFFFFFFFh
0x18006762e  jnz     short loc_180067651
0x180067630  call    cs:__imp_GetLastError
0x180067636  add     eax, 0FFFFFFFEh
0x180067639  cmp     eax, 1
0x18006763c  ja      short loc_180067651
0x18006763e  xor     ebx, ebx
0x180067640  mov     eax, 1D2h
0x180067645  mov     [rbp+57h+var_70], ebx
0x180067648  mov     [rbp+57h+var_6C], ax
0x18006764c  jmp     loc_18006777E
0x180067651  mov     r14d, 4
0x180067657  mov     [rsp+0C0h+var_A0], rsi
0x18006765c  mov     r9d, r14d
0x18006765f  lea     rdx, aSDS; "%s.%d.%s"
0x180067666  mov     r8, rdi
0x180067669  lea     rcx, [rbp+57h+lpFileName]; this
0x18006766d  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180067672  mov     ebx, eax
0x180067674  mov     [rbp+57h+var_70], eax
0x180067677  test    eax, eax
0x180067679  mov     eax, 1D7h
0x18006767e  js      loc_18006777A
0x180067684  mov     rsi, [rbp+57h+lpFileName]
0x180067688  mov     rcx, rsi; lpFileName
0x18006768b  mov     [rbp+57h+var_6C], ax
0x18006768f  call    cs:__imp_DeleteFileW
0x180067695  mov     ebx, [rbp+57h+var_70]
0x180067698  mov     r13d, 1F2h
0x18006769e  test    r14d, r14d
0x1800676a1  jz      loc_18006777E
0x1800676a7  lea     rax, aEtl; "etl"
0x1800676ae  dec     r14d
0x1800676b1  mov     r9d, r14d
0x1800676b4  mov     [rsp+0C0h+var_A0], rax
0x1800676b9  mov     r8, rdi
0x1800676bc  lea     rdx, aSDS; "%s.%d.%s"
0x1800676c3  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800676c7  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800676cc  mov     ebx, eax
0x1800676ce  mov     [rbp+57h+var_70], eax
0x1800676d1  test    eax, eax
0x1800676d3  mov     eax, 1DEh
0x1800676d8  js      loc_18006777A
0x1800676de  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800676e2  mov     r8d, 1; dwFlags
0x1800676e8  mov     rdx, rsi; lpNewFileName
0x1800676eb  mov     [rbp+57h+var_6C], ax
0x1800676ef  call    cs:__imp_MoveFileExW
0x1800676f5  test    eax, eax
0x1800676f7  jnz     short loc_180067726
0x1800676f9  call    cs:__imp_GetLastError
0x1800676ff  mov     ebx, eax
0x180067701  cmp     eax, 20h ; ' '
0x180067704  ja      short loc_180067752
0x180067706  mov     rcx, 100000024h
0x180067710  bt      rcx, rbx
0x180067714  jnb     short loc_180067752
0x180067716  mov     eax, 1EBh
0x18006771b  mov     [rbp+57h+var_70], 0
0x180067722  mov     [rbp+57h+var_6C], ax
0x180067726  mov     rcx, rsi; lpFileName
0x180067729  call    ?SxCompressLogFile@@YAJPEBG@Z; SxCompressLogFile(ushort const *)
0x18006772e  mov     rdx, [rbp+57h+lpExistingFileName]; unsigned __int16 *
0x180067732  lea     rcx, [rbp+57h+lpFileName]; this
0x180067736  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18006773b  mov     [rbp+57h+var_70], eax
0x18006773e  mov     ebx, eax
0x180067740  test    eax, eax
0x180067742  js      short loc_180067766
0x180067744  mov     rsi, [rbp+57h+lpFileName]
0x180067748  mov     [rbp+57h+var_6C], r13w
0x18006774d  jmp     loc_18006769E
0x180067752  test    ebx, ebx
0x180067754  jle     short loc_18006775F
0x180067756  movzx   ebx, bx
0x180067759  or      ebx, 80070000h
0x18006775f  mov     eax, 1EBh
0x180067764  jmp     short loc_180067777
0x180067766  mov     [rbp+57h+var_6A], r13w
0x18006776b  jmp     short loc_18006777E
0x18006776d  mov     ebx, 80070057h
0x180067772  mov     eax, 1C2h
0x180067777  mov     [rbp+57h+var_70], ebx
0x18006777a  mov     [rbp+57h+var_6A], ax
0x18006777e  lea     rcx, [rbp+57h+lpFileName]; this
0x180067782  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180067787  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x18006778b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180067790  lea     rcx, [rbp+57h+var_70]; this
0x180067794  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180067799  mov     eax, ebx
0x18006779b  add     rsp, 98h
0x1800677a2  pop     r14
0x1800677a4  pop     r13
0x1800677a6  pop     rdi
0x1800677a7  pop     rsi
0x1800677a8  pop     rbx
0x1800677a9  pop     rbp
0x1800677aa  retn
```
