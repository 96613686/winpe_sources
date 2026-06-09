# MatchOneEntry

- ea: `0x180059748`
- end: `0x1800598fc`
- name: `MatchOneEntry`
- size: `436`
- prototype: `int __fastcall(void *hFile, unsigned __int8 *pBuf, SPatternEntry *pEntry, int *pfLook, int *plLastOffset, unsigned int *pulLastCb)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059b80`

## callees

- `0x18004d474`
- `0x1800592bc`
- `0x180059748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005982f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005987b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005982f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005987b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800597c4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800597c4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800597ed`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800597ed`

## string_xrefs

- `0x18005984d`: `com\ole32\com\class\pattbl.cxx`
- `0x180059899`: `com\ole32\com\class\pattbl.cxx`

## pseudocode

```c
__int64 __fastcall MatchOneEntry(
        void *hFile,
        unsigned __int8 *pBuf,
        SPatternEntry *pEntry,
        int *pfLook,
        int *plLastOffset,
        unsigned int *pulLastCb)
{
  int *v6; // r15
  unsigned int *p_ulCb; // r10
  unsigned int *v8; // rsi
  LONG lFileOffset; // edx
  unsigned int v14; // edi
  unsigned int *v15; // rbx
  DWORD file; // eax
  DWORD LastError; // eax
  __int64 v18; // r10
  $51B8AC67E82C414CCD5269CA8620DDC1 *v19; // r9
  __int64 v20; // r8
  unsigned __int8 *v21; // rdx
  const wchar_t *v23; // [rsp+20h] [rbp-38h]
  const wchar_t *v24; // [rsp+20h] [rbp-38h]
  unsigned int cbRead; // [rsp+70h] [rbp+18h] BYREF

  v6 = plLastOffset;
  p_ulCb = &pEntry->ulCb;
  v8 = pulLastCb;
  lFileOffset = pEntry->lFileOffset;
  v14 = 1;
  if ( lFileOffset != *plLastOffset || *p_ulCb > *pulLastCb )
  {
    cbRead = 0;
    *pfLook = 0;
    v15 = &pEntry->ulCb;
    LODWORD(plLastOffset) = lFileOffset >> 31;
    if ( SetFilePointer(hFile, lFileOffset, (PLONG)&plLastOffset, (lFileOffset >> 31) & 2) == -1 )
    {
      p_ulCb = v15;
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      {
        LastError = GetLastError();
        ComTraceMessageT<unsigned long>(
          "com\\ole32\\com\\class\\pattbl.cxx",
          "MatchOneEntry",
          126,
          VERBOSE,
          v23,
          LastError);
        p_ulCb = v15;
      }
    }
    else
    {
      if ( ReadFile(hFile, pBuf, *v15, &cbRead, 0) )
      {
        *v6 = pEntry->lFileOffset;
        *v8 = *v15;
        *pfLook = 1;
        goto LABEL_13;
      }
      p_ulCb = v15;
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      {
        file = GetLastError();
        ComTraceMessageT<unsigned long>("com\\ole32\\com\\class\\pattbl.cxx", "MatchOneEntry", 121, VERBOSE, v24, file);
        p_ulCb = &pEntry->ulCb;
      }
    }
  }
  v15 = p_ulCb;
  if ( !*pfLook )
    return 0;
LABEL_13:
  v18 = *v15;
  v19 = &pEntry->28;
  v20 = 0;
  v21 = &pEntry->abData[v18];
  while ( (unsigned int)v20 < (unsigned int)v18 )
  {
    if ( (v19->abData[0] & pBuf[v20]) != *v21 )
      return 0;
    v19 = ($51B8AC67E82C414CCD5269CA8620DDC1 *)((char *)v19 + 1);
    ++v21;
    v20 = (unsigned int)(v20 + 1);
  }
  return v14;
}

```

## disassembly

```asm
0x180059748  mov     [rsp+arg_0], rbx
0x18005974d  mov     [rsp+arg_8], rbp
0x180059752  mov     [rsp+arg_18], rsi
0x180059757  push    rdi
0x180059758  push    r12
0x18005975a  push    r13
0x18005975c  push    r14
0x18005975e  push    r15
0x180059760  sub     rsp, 30h
0x180059764  mov     r15, [rsp+58h+cbMove]
0x18005976c  lea     r10, [pEntry+18h]
0x180059770  mov     rsi, [rsp+58h+arg_28]
0x180059778  mov     r13, pBuf
0x18005977b  mov     edx, [pEntry+14h]; lDistanceToMove
0x18005977f  mov     r14, pfLook
0x180059782  mov     rbp, pEntry
0x180059785  mov     r12, hFile
0x180059788  mov     edi, 1
0x18005978d  cmp     edx, [r15]
0x180059790  jnz     short loc_18005979D
0x180059792  mov     eax, [rsi]
0x180059794  cmp     [r10], eax
0x180059797  jbe     loc_1800598A8
0x18005979d  and     [rsp+58h+cbRead], 0
0x1800597a2  lea     pEntry, [rsp+58h+cbMove]; lpDistanceToMoveHigh
0x1800597aa  and     dword ptr [r14], 0
0x1800597ae  mov     r9d, edx
0x1800597b1  sar     r9d, 1Fh
0x1800597b5  mov     rbx, r10
0x1800597b8  mov     dword ptr [rsp+58h+cbMove], r9d
0x1800597c0  and     r9d, 2; dwMoveMethod
0x1800597c4  call    cs:__imp_SetFilePointer
0x1800597cb  nop     dword ptr [rax+rax+00h]
0x1800597d0  cmp     eax, 0FFFFFFFFh
0x1800597d3  jz      loc_18005985F
0x1800597d9  mov     r8d, [rbx]; nNumberOfBytesToRead
0x1800597dc  lea     pfLook, [rsp+58h+cbRead]; lpNumberOfBytesRead
0x1800597e1  and     [rsp+58h+var_38], 0
0x1800597e7  mov     pBuf, r13; lpBuffer
0x1800597ea  mov     hFile, r12; hFile
0x1800597ed  call    cs:__imp_ReadFile
0x1800597f4  nop     dword ptr [rax+rax+00h]
0x1800597f9  test    eax, eax
0x1800597fb  jz      short loc_18005980F
0x1800597fd  mov     eax, [rbp+14h]
0x180059800  mov     [r15], eax
0x180059803  mov     eax, [rbx]
0x180059805  mov     [rsi], eax
0x180059807  mov     [r14], edi
0x18005980a  jmp     loc_1800598B1
0x18005980f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180059816  mov     r10, rbx
0x180059819  jz      loc_1800598A8
0x18005981f  mov     esi, 3
0x180059824  mov     ecx, esi; level
0x180059826  call    IsWppLevelEnabled
0x18005982b  test    al, al
0x18005982d  jz      short loc_1800598A8
0x18005982f  call    cs:__imp_GetLastError
0x180059836  nop     dword ptr [rax+rax+00h]
0x18005983b  mov     r9d, esi; level
0x18005983e  lea     r8d, [rsi+76h]; line
0x180059842  lea     pBuf, aMatchoneentry; "MatchOneEntry"
0x180059849  mov     [rsp+58h+file], eax; file
0x18005984d  lea     hFile, aComOle32ComCla; "com\\ole32\\com\\class\\pattbl.cxx"
0x180059854  call    ??$ComTraceMessageT@K@@YAXPEBD0HW4TraceLevel@@PEBGK@Z; ComTraceMessageT<ulong>(char const *,char const *,int,TraceLevel,ushort const *,ulong)
0x180059859  lea     r10, [rbp+18h]
0x18005985d  jmp     short loc_1800598A8
0x18005985f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180059866  mov     r10, rbx
0x180059869  jz      short loc_1800598A8
0x18005986b  mov     esi, 3
0x180059870  mov     ecx, esi; level
0x180059872  call    IsWppLevelEnabled
0x180059877  test    al, al
0x180059879  jz      short loc_1800598A8
0x18005987b  call    cs:__imp_GetLastError
0x180059882  nop     dword ptr [rax+rax+00h]
0x180059887  mov     r9d, esi; level
0x18005988a  lea     r8d, [rsi+7Bh]; line
0x18005988e  lea     pBuf, aMatchoneentry; "MatchOneEntry"
0x180059895  mov     [rsp+58h+file], eax; file
0x180059899  lea     hFile, aComOle32ComCla; "com\\ole32\\com\\class\\pattbl.cxx"
0x1800598a0  call    ??$ComTraceMessageT@K@@YAXPEBD0HW4TraceLevel@@PEBGK@Z; ComTraceMessageT<ulong>(char const *,char const *,int,TraceLevel,ushort const *,ulong)
0x1800598a5  mov     r10, rbx
0x1800598a8  cmp     dword ptr [r14], 0
0x1800598ac  mov     rbx, r10
0x1800598af  jz      short loc_1800598DA
0x1800598b1  mov     r10d, [rbx]
0x1800598b4  lea     pfLook, [rbp+1Ch]
0x1800598b8  xor     r8d, r8d
0x1800598bb  lea     pBuf, [pfLook+r10]
0x1800598bf  cmp     r8d, r10d
0x1800598c2  jnb     short loc_1800598DC
0x1800598c4  mov     cl, [pEntry+r13]
0x1800598c8  and     cl, [pfLook]
0x1800598cb  cmp     cl, [pBuf]
0x1800598cd  jnz     short loc_1800598DA
0x1800598cf  add     pfLook, rdi
0x1800598d2  add     pBuf, rdi
0x1800598d5  add     r8d, edi
0x1800598d8  jmp     short loc_1800598BF
0x1800598da  xor     edi, edi
0x1800598dc  mov     rbx, [rsp+58h+arg_0]
0x1800598e1  mov     eax, edi
0x1800598e3  mov     rbp, [rsp+58h+arg_8]
0x1800598e8  mov     rsi, [rsp+58h+arg_18]
0x1800598ed  add     rsp, 30h
0x1800598f1  pop     r15
0x1800598f3  pop     r14
0x1800598f5  pop     r13
0x1800598f7  pop     r12
0x1800598f9  pop     rdi
0x1800598fa  retn
```
