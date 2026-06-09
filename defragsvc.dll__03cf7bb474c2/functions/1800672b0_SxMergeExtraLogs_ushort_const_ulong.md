# SxMergeExtraLogs(ushort const *,ulong)

- ea: `0x1800672b0`
- end: `0x18006753b`
- name: `?SxMergeExtraLogs@@YAJPEBGK@Z`
- size: `651`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180067544`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x18002ce84`
- `0x180038c3c`
- `0x180066fc8`
- `0x1800672b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067406`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800674ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800674ab`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800674a1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800674a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SxMergeExtraLogs(const unsigned __int16 *a1, unsigned int a2)
{
  __int16 v3; // ax
  unsigned int v4; // esi
  int i; // ebx
  const unsigned __int16 *v6; // rdx
  signed int v7; // eax
  __int64 v8; // r9
  signed int LastError; // eax
  unsigned int v10; // ebx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-29h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v14; // [rsp+50h] [rbp-9h] BYREF
  __int16 v15; // [rsp+54h] [rbp-5h]
  __int16 v16; // [rsp+56h] [rbp-3h]
  unsigned int v17; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v18; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+D0h] [rbp+77h] BYREF

  v18 = a2;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxMergeExtraLogs", 0x159u, 1u);
  v19 = 0;
  lpFileName[0] = &qword_18006F470;
  lpNewFileName[0] = &qword_18006F470;
  v18 = 0;
  v17 = 0;
  lpFileName[1] = 0;
  lpNewFileName[1] = 0;
  if ( !a1 )
  {
    v14 = -2147024809;
    v3 = 356;
    goto LABEL_33;
  }
  v14 = 0;
  v15 = 357;
  v14 = SxGet0XLogFileCount(a1, &v19, &v18, &v17);
  v3 = 364;
  if ( v14 < 0 )
  {
LABEL_33:
    v16 = v3;
    goto LABEL_34;
  }
  v15 = 364;
  if ( v18 )
  {
    v4 = 4;
    for ( i = 4; i >= (signed int)-v17; --i )
    {
      v6 = L"%s.%d.%s";
      if ( i < (int)(5 - v18) )
      {
        v8 = (unsigned int)-i;
        if ( i > 0 )
          v8 = (unsigned int)i;
        if ( i < 0 )
          v6 = L"%s.0.%d.%s";
        v14 = CBsString::Format((CBsString *)lpFileName, v6, a1, v8, L"etl");
        v3 = 400;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 400;
        v14 = CBsString::Format((CBsString *)lpNewFileName, L"%s.%d.%s", a1, v4, L"etl");
        v3 = 405;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 405;
        if ( MoveFileExW(lpFileName[0], lpNewFileName[0], 1u) )
        {
          --v4;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError != 2 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v14 = LastError;
            v3 = 410;
            goto LABEL_33;
          }
          v14 = 0;
          v15 = 410;
        }
      }
      else
      {
        v14 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, (unsigned int)i, L"etl");
        v3 = 384;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 384;
        if ( !DeleteFileW(lpFileName[0]) )
        {
          v7 = GetLastError();
          if ( v7 != 2 )
          {
            if ( v7 > 0 )
              v7 = (unsigned __int16)v7 | 0x80070000;
            v14 = v7;
            v16 = 388;
            break;
          }
          v14 = 0;
          v15 = 388;
        }
      }
    }
  }
  else
  {
    v14 = 0;
    v15 = 369;
  }
LABEL_34:
  v10 = v14;
  CBsString::_Release((CBsString *)lpNewFileName);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v10;
}

```

## disassembly

```asm
0x1800672b0  mov     [rsp-8+arg_8], edx
0x1800672b4  push    rbp
0x1800672b5  push    rbx
0x1800672b6  push    rsi
0x1800672b7  push    rdi
0x1800672b8  push    r13
0x1800672ba  lea     rbp, [rsp-37h]
0x1800672bf  sub     rsp, 90h
0x1800672c6  mov     rdi, rcx
0x1800672c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800672d0  lea     rax, WPP_GLOBAL_Control
0x1800672d7  cmp     rcx, rax
0x1800672da  jz      short loc_1800672FA
0x1800672dc  test    dword ptr [rcx+1Ch], 20000000h
0x1800672e3  jz      short loc_1800672FA
0x1800672e5  mov     rcx, [rcx+10h]
0x1800672e9  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800672f0  mov     edx, 13h
0x1800672f5  call    WPP_SF_
0x1800672fa  mov     r9d, 1; unsigned __int16
0x180067300  lea     rdx, aSxmergeextralo; "SxMergeExtraLogs"
0x180067307  mov     r8d, 159h; unsigned __int16
0x18006730d  lea     rcx, [rbp+57h+var_60]; this
0x180067311  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180067316  mov     [rbp+57h+arg_10], 0
0x18006731d  lea     rax, qword_18006F470
0x180067324  mov     [rbp+57h+lpFileName], rax
0x180067328  mov     [rbp+57h+lpNewFileName], rax
0x18006732c  mov     [rbp+57h+arg_8], 0
0x180067333  mov     [rbp+57h+arg_0], 0
0x18006733a  mov     [rbp+57h+var_78], 0
0x180067342  mov     [rbp+57h+var_68], 0
0x18006734a  test    rdi, rdi
0x18006734d  jz      loc_1800674FD
0x180067353  mov     eax, 165h
0x180067358  mov     [rbp+57h+var_60], 0
0x18006735f  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180067363  mov     [rbp+57h+var_5C], ax
0x180067367  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x18006736b  mov     rcx, rdi; unsigned __int16 *
0x18006736e  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180067372  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x180067377  mov     [rbp+57h+var_60], eax
0x18006737a  test    eax, eax
0x18006737c  mov     eax, 16Ch
0x180067381  js      loc_180067509
0x180067387  cmp     [rbp+57h+arg_8], 0
0x18006738b  mov     [rbp+57h+var_5C], ax
0x18006738f  jnz     short loc_1800673A6
0x180067391  mov     eax, 171h
0x180067396  mov     [rbp+57h+var_60], 0
0x18006739d  mov     [rbp+57h+var_5C], ax
0x1800673a1  jmp     loc_18006750D
0x1800673a6  mov     esi, 4
0x1800673ab  mov     r13d, 184h
0x1800673b1  mov     ebx, esi
0x1800673b3  mov     eax, [rbp+57h+arg_0]
0x1800673b6  lea     rcx, aEtl; "etl"
0x1800673bd  neg     eax
0x1800673bf  cmp     ebx, eax
0x1800673c1  jl      loc_18006750D
0x1800673c7  mov     eax, 5
0x1800673cc  mov     [rsp+0B0h+var_90], rcx
0x1800673d1  sub     eax, [rbp+57h+arg_8]
0x1800673d4  lea     rdx, aSDS; "%s.%d.%s"
0x1800673db  lea     rcx, [rbp+57h+lpFileName]; this
0x1800673df  mov     r9d, ebx
0x1800673e2  mov     r8, rdi
0x1800673e5  cmp     ebx, eax
0x1800673e7  jl      short loc_180067434
0x1800673e9  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800673ee  mov     [rbp+57h+var_60], eax
0x1800673f1  test    eax, eax
0x1800673f3  mov     eax, 180h
0x1800673f8  js      loc_180067509
0x1800673fe  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180067402  mov     [rbp+57h+var_5C], ax
0x180067406  call    cs:__imp_DeleteFileW
0x18006740c  test    eax, eax
0x18006740e  jnz     loc_1800674CA
0x180067414  call    cs:__imp_GetLastError
0x18006741a  cmp     eax, 2
0x18006741d  jnz     loc_1800674D1
0x180067423  mov     [rbp+57h+var_60], 0
0x18006742a  mov     [rbp+57h+var_5C], r13w
0x18006742f  jmp     loc_1800674CA
0x180067434  neg     r9d
0x180067437  lea     rax, aS0DS; "%s.0.%d.%s"
0x18006743e  cmovs   r9d, ebx
0x180067442  test    ebx, ebx
0x180067444  cmovs   rdx, rax; unsigned __int16 *
0x180067448  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18006744d  mov     [rbp+57h+var_60], eax
0x180067450  test    eax, eax
0x180067452  mov     eax, 190h
0x180067457  js      loc_180067509
0x18006745d  mov     [rbp+57h+var_5C], ax
0x180067461  lea     rdx, aSDS; "%s.%d.%s"
0x180067468  lea     rax, aEtl; "etl"
0x18006746f  mov     r9d, esi
0x180067472  mov     r8, rdi
0x180067475  mov     [rsp+0B0h+var_90], rax
0x18006747a  lea     rcx, [rbp+57h+lpNewFileName]; this
0x18006747e  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180067483  mov     [rbp+57h+var_60], eax
0x180067486  test    eax, eax
0x180067488  mov     eax, 195h
0x18006748d  js      short loc_180067509
0x18006748f  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180067493  mov     r8d, 1; dwFlags
0x180067499  mov     rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x18006749d  mov     [rbp+57h+var_5C], ax
0x1800674a1  call    cs:__imp_MoveFileExW
0x1800674a7  test    eax, eax
0x1800674a9  jnz     short loc_1800674C8
0x1800674ab  call    cs:__imp_GetLastError
0x1800674b1  cmp     eax, 2
0x1800674b4  jnz     short loc_1800674E7
0x1800674b6  mov     eax, 19Ah
0x1800674bb  mov     [rbp+57h+var_60], 0
0x1800674c2  mov     [rbp+57h+var_5C], ax
0x1800674c6  jmp     short loc_1800674CA
0x1800674c8  dec     esi
0x1800674ca  dec     ebx
0x1800674cc  jmp     loc_1800673B3
0x1800674d1  test    eax, eax
0x1800674d3  jle     short loc_1800674DD
0x1800674d5  movzx   eax, ax
0x1800674d8  or      eax, 80070000h
0x1800674dd  mov     [rbp+57h+var_60], eax
0x1800674e0  mov     [rbp+57h+var_5A], r13w
0x1800674e5  jmp     short loc_18006750D
0x1800674e7  test    eax, eax
0x1800674e9  jle     short loc_1800674F3
0x1800674eb  movzx   eax, ax
0x1800674ee  or      eax, 80070000h
0x1800674f3  mov     [rbp+57h+var_60], eax
0x1800674f6  mov     eax, 19Ah
0x1800674fb  jmp     short loc_180067509
0x1800674fd  mov     [rbp+57h+var_60], 80070057h
0x180067504  mov     eax, 164h
0x180067509  mov     [rbp+57h+var_5A], ax
0x18006750d  mov     ebx, [rbp+57h+var_60]
0x180067510  lea     rcx, [rbp+57h+lpNewFileName]; this
0x180067514  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180067519  lea     rcx, [rbp+57h+lpFileName]; this
0x18006751d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180067522  lea     rcx, [rbp+57h+var_60]; this
0x180067526  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18006752b  mov     eax, ebx
0x18006752d  add     rsp, 90h
0x180067534  pop     r13
0x180067536  pop     rdi
0x180067537  pop     rsi
0x180067538  pop     rbx
0x180067539  pop     rbp
0x18006753a  retn
```
