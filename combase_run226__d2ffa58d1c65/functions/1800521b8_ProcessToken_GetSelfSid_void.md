# ProcessToken::GetSelfSid(void * *)

- ea: `0x1800521b8`
- end: `0x180052307`
- name: `?GetSelfSid@ProcessToken@@QEAAJPEAPEAX@Z`
- size: `335`
- prototype: `HRESULT __fastcall(ProcessToken *this, void **ppSelfSid)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ab0`
- `0x180051fdc`
- `0x180052bb8`
- `0x18005df80`
- `0x1800df088`
- `0x18012498c`

## callees

- `0x1800521b8`
- `0x18008db2c`
- `0x1801457c0`
- `0x1801999b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052220`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005229b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005229b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800522d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800522d2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800522b3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800522b3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180052287`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180052287`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180052216`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180052216`

## string_xrefs

- `0x180052265`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18005225e`: `ProcessToken::GetSelfSid`

## pseudocode

```c
__int64 __fastcall ProcessToken::GetSelfSid(ProcessToken *this, void **ppSelfSid)
{
  signed int LastError; // ebx
  bool v5; // sf
  DWORD LengthSid; // ebp
  void *v7; // rax
  void *v8; // rsi
  unsigned int lIgnore[4]; // [rsp+30h] [rbp-A8h] BYREF
  PSID aMemory[12]; // [rsp+40h] [rbp-98h] BYREF

  *ppSelfSid = 0;
  if ( g_processToken._pSelfSid )
  {
    *ppSelfSid = g_processToken._pSelfSid;
    return 0;
  }
  else
  {
    LastError = 0;
    lIgnore[0] = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, aMemory, 0x54u, lIgnore) )
      goto LABEL_11;
    LastError = GetLastError();
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\processtoken\\processtoken.cxx",
        "ProcessToken::GetSelfSid",
        958,
        ERRORS,
        L"%!WINERROR!",
        LastError);
    v5 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError < 0;
    }
    if ( !v5 )
    {
LABEL_11:
      LengthSid = GetLengthSid(aMemory[0]);
      v7 = HeapAlloc(g_hHeap, 0, LengthSid);
      v8 = v7;
      if ( v7 )
      {
        CopySid(LengthSid, v7, aMemory[0]);
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_processToken, (signed __int64)v8, 0) )
          HeapFree(g_hHeap, 0, v8);
        *ppSelfSid = g_processToken._pSelfSid;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x1800521b8  push    rbx
0x1800521ba  push    rbp
0x1800521bb  push    rsi
0x1800521bc  push    rdi
0x1800521bd  sub     rsp, 0B8h
0x1800521c4  mov     rax, cs:__security_cookie
0x1800521cb  xor     rax, rsp
0x1800521ce  mov     [rsp+0D8h+var_38], rax
0x1800521d6  mov     qword ptr [ppSelfSid], 0
0x1800521dd  mov     rdi, ppSelfSid
0x1800521e0  mov     rax, cs:?g_processToken@@3VProcessToken@@A._pSelfSid; ProcessToken g_processToken ...
0x1800521e7  test    rax, rax
0x1800521ea  jz      short loc_1800521F6
0x1800521ec  mov     [ppSelfSid], rax
0x1800521ef  xor     eax, eax
0x1800521f1  jmp     loc_1800522EB
0x1800521f6  xor     ebx, ebx
0x1800521f8  lea     rax, [rsp+0D8h+lIgnore]
0x1800521fd  lea     r8, [rsp+0D8h+aMemory]; TokenInformation
0x180052202  mov     [rsp+0D8h+lIgnore], ebx
0x180052206  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x18005220b  lea     r9d, [rbx+54h]; TokenInformationLength
0x18005220f  lea     edx, [rbx+1]; TokenInformationClass
0x180052212  lea     rcx, [rbx-4]; TokenHandle
0x180052216  call    cs:__imp_GetTokenInformation
0x18005221c  test    eax, eax
0x18005221e  jnz     short loc_180052282
0x180052220  call    cs:__imp_GetLastError
0x180052226  mov     ebx, eax
0x180052228  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005222e  test    eax, eax
0x180052230  jnz     short loc_180052245
0x180052232  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180052238  jz      short loc_180052271
0x18005223a  xor     ecx, ecx; level
0x18005223c  call    IsWppLevelEnabled
0x180052241  test    al, al
0x180052243  jz      short loc_180052271
0x180052245  lea     rax, aWinerror; "%!WINERROR!"
0x18005224c  mov     [rsp+0D8h+var_B0], ebx; <args_0>
0x180052250  xor     r9d, r9d; level
0x180052253  mov     [rsp+0D8h+ReturnLength], rax; format
0x180052258  mov     r8d, 3BEh; line
0x18005225e  lea     ppSelfSid, aProcesstokenGe; "ProcessToken::GetSelfSid"
0x180052265  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18005226c  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x180052271  test    ebx, ebx
0x180052273  jle     short loc_180052280
0x180052275  movzx   ebx, bx
0x180052278  or      ebx, 80070000h
0x18005227e  test    ebx, ebx
0x180052280  js      short loc_1800522E9
0x180052282  mov     rcx, [rsp+0D8h+aMemory]; pSid
0x180052287  call    cs:__imp_GetLengthSid
0x18005228d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180052294  xor     edx, edx; dwFlags
0x180052296  mov     r8d, eax; dwBytes
0x180052299  mov     ebp, eax
0x18005229b  call    cs:__imp_HeapAlloc
0x1800522a1  mov     rsi, rax
0x1800522a4  test    rax, rax
0x1800522a7  jz      short loc_1800522E4
0x1800522a9  mov     r8, [rsp+0D8h+aMemory]; pSourceSid
0x1800522ae  mov     ppSelfSid, rax; pDestinationSid
0x1800522b1  mov     ecx, ebp; nDestinationSidLength
0x1800522b3  call    cs:__imp_CopySid
0x1800522b9  xor     eax, eax
0x1800522bb  lock cmpxchg cs:?g_processToken@@3VProcessToken@@A._pSelfSid, rsi; ProcessToken g_processToken ...
0x1800522c4  jz      short loc_1800522D8
0x1800522c6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800522cd  mov     r8, rsi; lpMem
0x1800522d0  xor     edx, edx; dwFlags
0x1800522d2  call    cs:__imp_HeapFree
0x1800522d8  mov     rax, cs:?g_processToken@@3VProcessToken@@A._pSelfSid; ProcessToken g_processToken ...
0x1800522df  mov     [rdi], rax
0x1800522e2  jmp     short loc_1800522E9
0x1800522e4  mov     ebx, 8007000Eh
0x1800522e9  mov     eax, ebx
0x1800522eb  mov     rcx, [rsp+0D8h+var_38]
0x1800522f3  xor     rcx, rsp; StackCookie
0x1800522f6  call    __security_check_cookie
0x1800522fb  add     rsp, 0B8h
0x180052302  pop     rdi
0x180052303  pop     rsi
0x180052304  pop     rbp
0x180052305  pop     rbx
0x180052306  retn
```
