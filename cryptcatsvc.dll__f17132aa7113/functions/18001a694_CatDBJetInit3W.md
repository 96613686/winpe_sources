# _CatDBJetInit3W

- ea: `0x18001a694`
- end: `0x18001a893`
- name: `_CatDBJetInit3W`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180019fe0`

## callees

- `0x1800015b0`
- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x180013628`
- `0x18001a694`
- `0x18001b4dc`
- `0x18001db50`
- `0x18001f748`
- `0x18001f81c`

## import_xrefs

- `ESENT!JetInit3W` at `0x18001a84e`
- `ESENT!JetInit3W` at `0x18001a84e`
- `ESENT!JetGetDatabaseFileInfoW` at `0x18001a778`
- `ESENT!JetGetDatabaseFileInfoW` at `0x18001a778`
- `ESENT!JetSetSystemParameterW` at `0x18001a80f`
- `ESENT!JetSetSystemParameterW` at `0x18001a80f`
- `ESENT!JetInit` at `0x18001a702`
- `ESENT!JetInit` at `0x18001a702`

## pseudocode

```c
__int64 __fastcall CatDBJetInit3W(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // edi
  __int64 v5; // rsi
  WCHAR *v6; // r15
  JET_ERR DatabaseFileInfoW; // eax
  unsigned int v8; // r14d
  const WCHAR *szParam; // rax
  JET_ERR v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  int v15; // [rsp+28h] [rbp-D8h]
  JET_RSTINFO_W prstInfo; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pvResult[36]; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+84h] [rbp-7Ch]
  JET_PCWSTR szDatabaseName[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v20; // [rsp+150h] [rbp+50h]
  __int64 v21; // [rsp+160h] [rbp+60h]
  __int64 v22; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v23[9]; // [rsp+178h] [rbp+78h] BYREF

  v21 = 0;
  *(_OWORD *)szDatabaseName = 0;
  v20 = 0;
  memset_0(pvResult, 0, 0xD8u);
  v3 = _CatDBGetDatabaseFileNames((unsigned __int16 **const)szDatabaseName);
  if ( v3 )
  {
    v4 = 0;
    v22 = 0;
    memset_0(v23, 0, sizeof(v23));
    *(&prstInfo.cbStruct + 1) = 0;
    v5 = 0;
    prstInfo.cbStruct = 48;
    prstInfo.rgrstmap = (JET_RSTMAP_W *)&v22;
    memset(&prstInfo.crstmap, 0, 32);
    prstInfo.crstmap = v3;
    do
    {
      v6 = (WCHAR *)szDatabaseName[v5];
      v23[2 * (unsigned int)v5] = v6;
      DatabaseFileInfoW = JetGetDatabaseFileInfoW(v6, pvResult, 0xD8u, 0xEu);
      v8 = DatabaseFileInfoW;
      if ( DatabaseFileInfoW || v18 != 2 )
      {
        if ( CatHelperCheckJetErrForCorruption(DatabaseFileInfoW) )
        {
          v4 = v8;
          ErrLog_LogPrintfW(0, 1, L"Init:: Database corrupted (%d) %s", v8, v6);
        }
      }
      else
      {
        *a2 = 0;
        CatDBSetWriteJetDatabaseParams();
        ErrLog_LogString(0, L"Init:: Database previously shutdown dirty ", v6, v8 + 1);
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < v3 );
    if ( !v4 )
    {
      szParam = L"Off";
      if ( !*a2 )
        szParam = L"On";
      v10 = JetSetSystemParameterW(&g_JetInstance, 0, 0x22u, 0, szParam);
      if ( (unsigned int)_CatDBJET_errFailure(v10) )
      {
        v11 = _CatDBMapJetError(v10);
        ErrLog_LogError(v13, v12, 0x3FAu, v11, 0, v15);
      }
      v4 = JetInit3W(&g_JetInstance, &prstInfo, 0);
    }
    do
      _CatDBFree((void *)szDatabaseName[--v3]);
    while ( v3 );
  }
  else
  {
    return (unsigned int)JetInit(&g_JetInstance);
  }
  return v4;
}

```

## disassembly

```asm
0x18001a694  mov     [rsp-8+arg_0], rbx
0x18001a699  mov     [rsp-8+arg_10], rsi
0x18001a69e  push    rbp
0x18001a69f  push    rdi
0x18001a6a0  push    r12
0x18001a6a2  push    r14
0x18001a6a4  push    r15
0x18001a6a6  lea     rbp, [rsp-0D0h]
0x18001a6ae  sub     rsp, 1D0h
0x18001a6b5  mov     rax, cs:__security_cookie
0x18001a6bc  xor     rax, rsp
0x18001a6bf  mov     [rbp+0F0h+var_30], rax
0x18001a6c6  xorps   xmm0, xmm0
0x18001a6c9  lea     rcx, [rsp+1F0h+pvResult]; void *
0x18001a6ce  mov     r12, rdx
0x18001a6d1  xor     eax, eax
0x18001a6d3  xor     edx, edx; Val
0x18001a6d5  mov     [rbp+0F0h+var_90], rax
0x18001a6d9  mov     r8d, 0D8h; Size
0x18001a6df  movups  xmmword ptr [rbp+0F0h+szDatabaseName], xmm0
0x18001a6e3  movups  [rbp+0F0h+var_A0], xmm0
0x18001a6e7  call    memset_0
0x18001a6ec  lea     rcx, [rbp+0F0h+szDatabaseName]; unsigned __int16 **
0x18001a6f0  call    ?_CatDBGetDatabaseFileNames@@YAKQEAPEAG@Z; _CatDBGetDatabaseFileNames(ushort * * const)
0x18001a6f5  mov     ebx, eax
0x18001a6f7  test    eax, eax
0x18001a6f9  jnz     short loc_18001A70F
0x18001a6fb  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x18001a702  call    cs:__imp_JetInit
0x18001a708  mov     edi, eax
0x18001a70a  jmp     loc_18001A866
0x18001a70f  xor     edi, edi
0x18001a711  lea     rcx, [rbp+0F0h+var_78]; void *
0x18001a715  xor     edx, edx; Val
0x18001a717  mov     [rbp+0F0h+var_80], rdi
0x18001a71b  lea     r8d, [rdi+48h]; Size
0x18001a71f  call    memset_0
0x18001a724  xorps   xmm0, xmm0
0x18001a727  lea     rax, [rbp+0F0h+var_80]
0x18001a72b  movups  xmmword ptr [rsp+1F0h+prstInfo.cbStruct], xmm0
0x18001a730  xor     esi, esi
0x18001a732  mov     [rsp+1F0h+prstInfo.cbStruct], 30h ; '0'
0x18001a73a  mov     [rsp+1F0h+prstInfo.rgrstmap], rax
0x18001a73f  movups  xmmword ptr [rsp+1F0h+prstInfo.crstmap], xmm0
0x18001a744  mov     [rsp+1F0h+prstInfo.crstmap], ebx
0x18001a748  movups  xmmword ptr [rsp+1F0h+prstInfo.logtimeStop.bMonth], xmm0
0x18001a74d  test    ebx, ebx
0x18001a74f  jz      loc_18001A7E3
0x18001a755  mov     r15, [rbp+rsi*8+0F0h+szDatabaseName]
0x18001a75a  lea     rdx, [rsp+1F0h+pvResult]; pvResult
0x18001a75f  mov     eax, esi
0x18001a761  mov     r9d, 0Eh; InfoLevel
0x18001a767  add     rax, rax
0x18001a76a  mov     r8d, 0D8h; cbMax
0x18001a770  mov     rcx, r15; szDatabaseName
0x18001a773  mov     [rbp+rax*8+0F0h+var_78], r15
0x18001a778  call    cs:__imp_JetGetDatabaseFileInfoW
0x18001a77e  mov     r14d, eax
0x18001a781  test    eax, eax
0x18001a783  jnz     short loc_18001A7AB
0x18001a785  cmp     [rbp+0F0h+var_16C], 2
0x18001a789  jnz     short loc_18001A7AB
0x18001a78b  mov     [r12], eax
0x18001a78f  call    _CatDBSetWriteJetDatabaseParams
0x18001a794  lea     r9d, [r14+1]; int
0x18001a798  mov     r8, r15; unsigned __int16 *
0x18001a79b  lea     rdx, aInitDatabasePr; "Init:: Database previously shutdown dir"...
0x18001a7a2  xor     ecx, ecx; unsigned __int16 *
0x18001a7a4  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x18001a7a9  jmp     short loc_18001A7D5
0x18001a7ab  mov     ecx, r14d; int
0x18001a7ae  call    ?CatHelperCheckJetErrForCorruption@@YA_NJ@Z; CatHelperCheckJetErrForCorruption(long)
0x18001a7b3  test    al, al
0x18001a7b5  jz      short loc_18001A7D5
0x18001a7b7  mov     r9d, r14d
0x18001a7ba  mov     [rsp+1F0h+szParam], r15
0x18001a7bf  lea     r8, aInitDatabaseCo; "Init:: Database corrupted (%d) %s"
0x18001a7c6  mov     edx, 1; int
0x18001a7cb  xor     ecx, ecx; unsigned __int16 *
0x18001a7cd  mov     edi, r14d
0x18001a7d0  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x18001a7d5  inc     esi
0x18001a7d7  cmp     esi, ebx
0x18001a7d9  jb      loc_18001A755
0x18001a7df  test    edi, edi
0x18001a7e1  jnz     short loc_18001A856
0x18001a7e3  cmp     dword ptr [r12], 0
0x18001a7e8  lea     rcx, szParam; "On"
0x18001a7ef  lea     rax, aOff; "Off"
0x18001a7f6  cmovz   rax, rcx
0x18001a7fa  xor     r9d, r9d; lParam
0x18001a7fd  xor     edx, edx; sesid
0x18001a7ff  mov     [rsp+1F0h+szParam], rax; szParam
0x18001a804  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x18001a80b  lea     r8d, [r9+22h]; paramid
0x18001a80f  call    cs:__imp_JetSetSystemParameterW
0x18001a815  mov     ecx, eax; int
0x18001a817  mov     edi, eax
0x18001a819  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a81e  test    eax, eax
0x18001a820  jz      short loc_18001A83F
0x18001a822  mov     ecx, edi; int
0x18001a824  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001a829  mov     r9d, eax; unsigned int
0x18001a82c  mov     dword ptr [rsp+1F0h+szParam], 0; int
0x18001a834  mov     r8d, 3FAh; unsigned int
0x18001a83a  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001a83f  xor     r8d, r8d; grbit
0x18001a842  lea     rdx, [rsp+1F0h+prstInfo]; prstInfo
0x18001a847  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x18001a84e  call    cs:__imp_JetInit3W
0x18001a854  mov     edi, eax
0x18001a856  dec     ebx
0x18001a858  mov     rcx, [rbp+rbx*8+0F0h+szDatabaseName]; void *
0x18001a85d  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001a862  test    ebx, ebx
0x18001a864  jnz     short loc_18001A856
0x18001a866  mov     eax, edi
0x18001a868  mov     rcx, [rbp+0F0h+var_30]
0x18001a86f  xor     rcx, rsp; StackCookie
0x18001a872  call    __security_check_cookie
0x18001a877  lea     r11, [rsp+1F0h+var_20]
0x18001a87f  mov     rbx, [r11+30h]
0x18001a883  mov     rsi, [r11+40h]
0x18001a887  mov     rsp, r11
0x18001a88a  pop     r15
0x18001a88c  pop     r14
0x18001a88e  pop     r12
0x18001a890  pop     rdi
0x18001a891  pop     rbp
0x18001a892  retn
```
