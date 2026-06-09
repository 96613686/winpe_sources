# RasLineGetID

- ea: `0x18008cb84`
- end: `0x18008d128`
- name: `RasLineGetID`
- size: `1444`
- prototype: `__int64 __fastcall(int, int, int, int, wchar_t *String1, void *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180029100`
- `0x180042f70`

## callees

- `0x180002be6`
- `0x1800755b8`
- `0x18008a88c`
- `0x18008cb84`
- `0x18008e6f4`
- `0x18008ed64`
- `0x18008f50c`
- `0x18008f82c`
- `0x180090714`
- `0x180092a86`
- `0x180092a92`
- `0x180092aaa`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18008cf92`
- `KERNEL32!GetProcessHeap` at `0x18008cf92`
- `KERNEL32!HeapFree` at `0x18008cfa6`
- `KERNEL32!HeapFree` at `0x18008cfa6`
- `rtutils!TracePrintfA` at `0x18008ccc9`
- `rtutils!TracePrintfA` at `0x18008cd37`
- `rtutils!TracePrintfA` at `0x18008ce0e`
- `rtutils!TracePrintfA` at `0x18008ce5e`
- `rtutils!TracePrintfA` at `0x18008cefc`
- `rtutils!TracePrintfA` at `0x18008cfdf`
- `rtutils!TracePrintfA` at `0x18008d117`
- `rtutils!TracePrintfA` at `0x18008ccc9`
- `rtutils!TracePrintfA` at `0x18008cd37`
- `rtutils!TracePrintfA` at `0x18008ce0e`
- `rtutils!TracePrintfA` at `0x18008ce5e`
- `rtutils!TracePrintfA` at `0x18008cefc`
- `rtutils!TracePrintfA` at `0x18008cfdf`
- `rtutils!TracePrintfA` at `0x18008d117`

## string_xrefs

- `0x18008cc43`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008cdbf`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008ccc2`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008ce07`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetID(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        wchar_t *String1,
        unsigned int *a6)
{
  void *v7; // rdi
  __int64 v8; // rax
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  unsigned int LineObjWithReadLock; // eax
  unsigned int NDProxyHandle; // esi
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  unsigned int *v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // eax
  char *v23; // r14
  const wchar_t *v24; // rdx
  HANDLE ProcessHeap; // rax
  __int64 v26; // r8
  char *v27; // rdx
  signed __int64 v28; // r12
  __int16 v29; // ax
  char *v30; // rax
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  char v36[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v7 = 0;
  lpMem = 0;
  v34 = 0;
  v8 = -1;
  v33 = 0;
  v10 = a3;
  do
    ++v8;
  while ( String1[v8] );
  v35 = 0;
  v11 = v8 + 1;
  memset_0(v36, 0, sizeof(v36));
  if ( a4 != 1 )
  {
    if ( a4 != 4 )
    {
LABEL_73:
      NDProxyHandle = 87;
      if ( gIsndpspEtwTracingAvailable )
      {
        v14 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
        if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
        {
          v15 = L"RasLineGetID: Invalid input parameters";
          goto LABEL_8;
        }
        goto LABEL_9;
      }
      if ( dwTraceId == -1 )
        goto LABEL_9;
      TracePrintfA(dwTraceId, "RasLineGetID: Invalid input parameters");
      goto LABEL_51;
    }
    v18 = GetCallObjWithReadLock(v10, &v33);
    NDProxyHandle = v18;
    if ( v18 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v18);
        goto LABEL_53;
      }
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v18);
        v19 = xmmword_1800D0BE0;
        v20 = (const wchar_t *)&v35;
LABEL_27:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v19, v20);
        goto LABEL_53;
      }
      goto LABEL_53;
    }
    v21 = *a6;
    a6[1] = 28;
    if ( v21 < 0x1C )
    {
      NDProxyHandle = 122;
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
        goto LABEL_53;
      }
      v19 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
      if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
      {
        v20 = L"RasLineGetID: Insufficient buffer passed by caller";
        goto LABEL_27;
      }
LABEL_53:
      if ( v33 )
        ReleaseObjReadLock(v10);
      goto LABEL_9;
    }
    if ( !v33 )
      return NDProxyHandle;
    v22 = PrepareSyncRequest(117637395, v33[1], v21 + 52 + 2 * v11, &lpMem);
    NDProxyHandle = v22;
    if ( v22 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v22);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v35);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v22);
      }
      v7 = lpMem;
      goto LABEL_51;
    }
    v7 = lpMem;
    v23 = (char *)lpMem + 48;
    *((_DWORD *)lpMem + 16) = 0;
    NDProxyHandle = GetNDProxyHandle((__int64)v33, (_QWORD *)v23 + 3);
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_50;
      }
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v24 = L"RasLineGetID: GetNDProxyHandle failed with error (0x%x)";
LABEL_49:
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, v24, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v35);
      }
    }
    else
    {
      *((_DWORD *)v23 + 8) = 4;
      *((_DWORD *)v23 + 9) = v11;
      v26 = v11;
      v27 = &v23[*a6 + 48];
      *((_DWORD *)v23 + 10) = *a6 + 48;
      *((_DWORD *)v23 + 11) = *a6;
      *((_DWORD *)v23 + 13) = 24;
      *((_DWORD *)v23 + 12) = 24;
      *(_QWORD *)(v23 + 60) = 0;
      *((_DWORD *)v23 + 14) = 0;
      if ( v11 )
      {
        if ( v11 <= 0x7FFFFFFE )
        {
          v28 = (char *)String1 - v27;
          do
          {
            v29 = *(_WORD *)&v27[v28];
            if ( !v29 )
              break;
            *(_WORD *)v27 = v29;
            v27 += 2;
            --v26;
          }
          while ( v26 );
          v30 = v27 - 2;
          if ( v26 )
            v30 = v27;
          *(_WORD *)v30 = 0;
        }
        else
        {
          *(_WORD *)v27 = 0;
        }
      }
      NDProxyHandle = SyncDriverRequest(0x8FFF23C8, v7);
      if ( !NDProxyHandle )
      {
        memcpy_0(a6, v23 + 44, *((unsigned int *)v23 + 13));
        goto LABEL_50;
      }
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)",
            NDProxyHandle);
        goto LABEL_50;
      }
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v24 = L"RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)";
        goto LABEL_49;
      }
    }
LABEL_50:
    v10 = a3;
LABEL_51:
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    goto LABEL_53;
  }
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v34);
  NDProxyHandle = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      goto LABEL_9;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      v14 = xmmword_1800D0BE0;
      v15 = (const wchar_t *)&v35;
LABEL_8:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v14, v15);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  if ( wcscmp_0(String1, L"LineGuid") )
    goto LABEL_73;
  a6[1] = 48;
  if ( *a6 >= 0x30 )
  {
    a6[2] = 48;
    a6[3] = 1;
    a6[4] = 24;
    a6[5] = 24;
    v17 = v34;
    memmove_0(a6 + 6, v34 + 10, 0x10u);
    a6[10] = v17[14];
    *((_BYTE *)a6 + 44) = 0;
  }
  else
  {
    NDProxyHandle = 122;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
      goto LABEL_9;
    }
    v14 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
    {
      v15 = L"RasLineGetID: Insufficient buffer passed by caller";
      goto LABEL_8;
    }
  }
LABEL_9:
  if ( v34 )
    ReleaseObjReadLock(a1);
  return NDProxyHandle;
}

```

## disassembly

```asm
0x18008cb84  mov     [rsp-8+arg_8], rbx
0x18008cb89  push    rbp
0x18008cb8a  push    rsi
0x18008cb8b  push    rdi
0x18008cb8c  push    r12
0x18008cb8e  push    r13
0x18008cb90  push    r14
0x18008cb92  push    r15
0x18008cb94  lea     rbp, [rsp-750h]
0x18008cb9c  sub     rsp, 850h
0x18008cba3  mov     rax, cs:__security_cookie
0x18008cbaa  xor     rax, rsp
0x18008cbad  mov     [rbp+780h+var_40], rax
0x18008cbb4  mov     rbx, [rbp+780h+arg_28]
0x18008cbbb  mov     r13d, ecx
0x18008cbbe  mov     r12, [rbp+780h+String1]
0x18008cbc5  xor     ecx, ecx
0x18008cbc7  mov     edi, ecx
0x18008cbc9  mov     [rsp+880h+lpMem], rcx
0x18008cbce  mov     [rsp+880h+var_848], rcx
0x18008cbd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008cbd7  mov     [rsp+880h+var_850], rcx
0x18008cbdc  mov     esi, r9d
0x18008cbdf  mov     r14d, r8d
0x18008cbe2  mov     [rsp+880h+var_860], r8d
0x18008cbe7  inc     rax
0x18008cbea  cmp     [r12+rax*2], cx
0x18008cbef  jnz     short loc_18008CBE7
0x18008cbf1  mov     [rsp+880h+var_840], ecx
0x18008cbf5  lea     r15d, [rax+1]
0x18008cbf9  lea     rcx, [rsp+880h+var_83C]; void *
0x18008cbfe  xor     edx, edx; Val
0x18008cc00  mov     r8d, 7FCh; Size
0x18008cc06  call    memset_0
0x18008cc0b  cmp     esi, 1
0x18008cc0e  jnz     loc_18008CD8B
0x18008cc14  lea     rdx, [rsp+880h+var_848]
0x18008cc19  mov     ecx, r13d
0x18008cc1c  call    GetLineObjWithReadLock
0x18008cc21  xor     ecx, ecx
0x18008cc23  mov     esi, eax
0x18008cc25  test    eax, eax
0x18008cc27  jz      loc_18008CCD7
0x18008cc2d  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008cc33  jz      short loc_18008CCB4
0x18008cc35  cmp     qword ptr cs:xmmword_1800D0BE0, rcx
0x18008cc3c  jz      short loc_18008CC76
0x18008cc3e  mov     word ptr [rsp+880h+var_840], cx
0x18008cc43  lea     rdx, aRaslinegetidGe; "RasLineGetID: GetLineObjWithReadLock fa"...
0x18008cc4a  lea     rcx, [rsp+880h+var_840]
0x18008cc4f  mov     r8d, eax
0x18008cc52  call    FormatRRASErrorString
0x18008cc57  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008cc5e  lea     r8, [rsp+880h+var_840]
0x18008cc63  mov     rcx, cs:gNdpspEtwContext
0x18008cc6a  mov     rax, cs:gNdpspTemplateFunc
0x18008cc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc76  xor     ebx, ebx
0x18008cc78  cmp     [rsp+880h+var_848], rbx
0x18008cc7d  jz      short loc_18008CC87
0x18008cc7f  mov     ecx, r13d
0x18008cc82  call    ReleaseObjReadLock
0x18008cc87  mov     eax, esi
0x18008cc89  mov     rcx, [rbp+780h+var_40]
0x18008cc90  xor     rcx, rsp; StackCookie
0x18008cc93  call    __security_check_cookie
0x18008cc98  mov     rbx, [rsp+880h+arg_8]
0x18008cca0  add     rsp, 850h
0x18008cca7  pop     r15
0x18008cca9  pop     r14
0x18008ccab  pop     r13
0x18008ccad  pop     r12
0x18008ccaf  pop     rdi
0x18008ccb0  pop     rsi
0x18008ccb1  pop     rbp
0x18008ccb2  retn
0x18008ccb4  mov     ecx, cs:dwTraceId; dwTraceID
0x18008ccba  cmp     ecx, 0FFFFFFFFh
0x18008ccbd  jz      short loc_18008CC76
0x18008ccbf  mov     r8d, eax
0x18008ccc2  lea     rdx, aRaslinegetidGe_3; "RasLineGetID: GetLineObjWithReadLock fa"...
0x18008ccc9  call    cs:__imp_TracePrintfA
0x18008ccd0  nop     dword ptr [rax+rax+00h]
0x18008ccd5  jmp     short loc_18008CC76
0x18008ccd7  lea     rdx, aLineguid; "LineGuid"
0x18008ccde  mov     rcx, r12; String1
0x18008cce1  call    wcscmp_0
0x18008cce6  xor     ecx, ecx
0x18008cce8  test    eax, eax
0x18008ccea  jnz     loc_18008D0D8
0x18008ccf0  lea     eax, [rcx+30h]
0x18008ccf3  mov     [rbx+4], eax
0x18008ccf6  cmp     [rbx], eax
0x18008ccf8  jnb     short loc_18008CD48
0x18008ccfa  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008cd00  lea     esi, [rcx+7Ah]
0x18008cd03  jz      short loc_18008CD21
0x18008cd05  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008cd0c  test    rdx, rdx
0x18008cd0f  jz      loc_18008CC76
0x18008cd15  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x18008cd1c  jmp     loc_18008CC63
0x18008cd21  mov     ecx, cs:dwTraceId; dwTraceID
0x18008cd27  cmp     ecx, 0FFFFFFFFh
0x18008cd2a  jz      loc_18008CC76
0x18008cd30  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x18008cd37  call    cs:__imp_TracePrintfA
0x18008cd3e  nop     dword ptr [rax+rax+00h]
0x18008cd43  jmp     loc_18008CC76
0x18008cd48  mov     [rbx+8], eax
0x18008cd4b  lea     rdi, [rbx+18h]
0x18008cd4f  mov     eax, edi
0x18008cd51  mov     dword ptr [rbx+0Ch], 1
0x18008cd58  sub     eax, ebx
0x18008cd5a  mov     dword ptr [rbx+10h], 18h
0x18008cd61  mov     [rbx+14h], eax
0x18008cd64  mov     r8d, 10h; Size
0x18008cd6a  mov     rbx, [rsp+880h+var_848]
0x18008cd6f  mov     rcx, rdi; void *
0x18008cd72  lea     rdx, [rbx+28h]; Src
0x18008cd76  call    memmove_0
0x18008cd7b  mov     eax, [rbx+38h]
0x18008cd7e  xor     ebx, ebx
0x18008cd80  mov     [rdi+10h], eax
0x18008cd83  mov     [rdi+14h], bl
0x18008cd86  jmp     loc_18008CC78
0x18008cd8b  cmp     esi, 4
0x18008cd8e  jnz     loc_18008D0D6
0x18008cd94  lea     rdx, [rsp+880h+var_850]
0x18008cd99  mov     ecx, r14d
0x18008cd9c  call    GetCallObjWithReadLock
0x18008cda1  xor     ecx, ecx
0x18008cda3  mov     esi, eax
0x18008cda5  test    eax, eax
0x18008cda7  jz      short loc_18008CE1C
0x18008cda9  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008cdaf  jz      short loc_18008CDF9
0x18008cdb1  cmp     qword ptr cs:xmmword_1800D0BE0, rcx
0x18008cdb8  jz      short loc_18008CDF2
0x18008cdba  mov     word ptr [rsp+880h+var_840], cx
0x18008cdbf  lea     rdx, aRaslinegetidGe_0; "RasLineGetID: GetCallObjWithReadLock fa"...
0x18008cdc6  lea     rcx, [rsp+880h+var_840]
0x18008cdcb  mov     r8d, eax
0x18008cdce  call    FormatRRASErrorString
0x18008cdd3  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008cdda  lea     r8, [rsp+880h+var_840]
0x18008cddf  mov     rcx, cs:gNdpspEtwContext
0x18008cde6  mov     rax, cs:gNdpspTemplateFunc
0x18008cded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cdf2  xor     ebx, ebx
0x18008cdf4  jmp     loc_18008CFB2
0x18008cdf9  mov     ecx, cs:dwTraceId; dwTraceID
0x18008cdff  cmp     ecx, 0FFFFFFFFh
0x18008ce02  jz      short loc_18008CDF2
0x18008ce04  mov     r8d, eax
0x18008ce07  lea     rdx, aRaslinegetidGe_2; "RasLineGetID: GetCallObjWithReadLock fa"...
0x18008ce0e  call    cs:__imp_TracePrintfA
0x18008ce15  nop     dword ptr [rax+rax+00h]
0x18008ce1a  jmp     short loc_18008CDF2
0x18008ce1c  mov     eax, [rbx]
0x18008ce1e  mov     dword ptr [rbx+4], 1Ch
0x18008ce25  cmp     eax, 1Ch
0x18008ce28  jnb     short loc_18008CE6C
0x18008ce2a  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008ce30  mov     esi, 7Ah ; 'z'
0x18008ce35  jz      short loc_18008CE4C
0x18008ce37  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008ce3e  test    rdx, rdx
0x18008ce41  jz      short loc_18008CDF2
0x18008ce43  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x18008ce4a  jmp     short loc_18008CDDF
0x18008ce4c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008ce52  cmp     ecx, 0FFFFFFFFh
0x18008ce55  jz      short loc_18008CDF2
0x18008ce57  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x18008ce5e  call    cs:__imp_TracePrintfA
0x18008ce65  nop     dword ptr [rax+rax+00h]
0x18008ce6a  jmp     short loc_18008CDF2
0x18008ce6c  mov     rdx, [rsp+880h+var_850]
0x18008ce71  test    rdx, rdx
0x18008ce74  jz      loc_18008CC87
0x18008ce7a  mov     edx, [rdx+4]
0x18008ce7d  lea     r8d, [rax+34h]
0x18008ce81  lea     r8d, [r8+r15*2]
0x18008ce85  mov     ecx, 7030113h
0x18008ce8a  lea     r9, [rsp+880h+lpMem]
0x18008ce8f  call    PrepareSyncRequest
0x18008ce94  xor     ecx, ecx
0x18008ce96  mov     esi, eax
0x18008ce98  test    eax, eax
0x18008ce9a  jz      short loc_18008CF0F
0x18008ce9c  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008cea2  jz      short loc_18008CEE7
0x18008cea4  cmp     qword ptr cs:xmmword_1800D0BE0, rcx
0x18008ceab  jz      short loc_18008CF08
0x18008cead  mov     word ptr [rsp+880h+var_840], cx
0x18008ceb2  lea     rdx, aRaslinegetidPr_0; "RasLineGetID: PrepareSyncRequest failed"...
0x18008ceb9  lea     rcx, [rsp+880h+var_840]
0x18008cebe  mov     r8d, eax
0x18008cec1  call    FormatRRASErrorString
0x18008cec6  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008cecd  lea     r8, [rsp+880h+var_840]
0x18008ced2  mov     rcx, cs:gNdpspEtwContext
0x18008ced9  mov     rax, cs:gNdpspTemplateFunc
0x18008cee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cee5  jmp     short loc_18008CF08
0x18008cee7  mov     ecx, cs:dwTraceId; dwTraceID
0x18008ceed  cmp     ecx, 0FFFFFFFFh
0x18008cef0  jz      short loc_18008CF08
0x18008cef2  mov     r8d, eax
0x18008cef5  lea     rdx, aRaslinegetidPr; "RasLineGetID: PrepareSyncRequest failed"...
0x18008cefc  call    cs:__imp_TracePrintfA
0x18008cf03  nop     dword ptr [rax+rax+00h]
0x18008cf08  mov     rdi, [rsp+880h+lpMem]
0x18008cf0d  jmp     short loc_18008CF8B
0x18008cf0f  mov     rdi, [rsp+880h+lpMem]
0x18008cf14  lea     r14, [rdi+30h]
0x18008cf18  mov     [r14+10h], ecx
0x18008cf1c  lea     rdx, [r14+18h]
0x18008cf20  mov     rcx, [rsp+880h+var_850]
0x18008cf25  call    GetNDProxyHandle
0x18008cf2a  mov     esi, eax
0x18008cf2c  test    eax, eax
0x18008cf2e  jz      loc_18008CFED
0x18008cf34  xor     r14d, r14d
0x18008cf37  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008cf3e  jz      loc_18008CFCA
0x18008cf44  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008cf4b  jz      short loc_18008CF86
0x18008cf4d  lea     rdx, aRaslinegetidGe_1; "RasLineGetID: GetNDProxyHandle failed w"...
0x18008cf54  mov     r8d, esi
0x18008cf57  mov     word ptr [rsp+880h+var_840], r14w
0x18008cf5d  lea     rcx, [rsp+880h+var_840]
0x18008cf62  call    FormatRRASErrorString
0x18008cf67  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008cf6e  lea     r8, [rsp+880h+var_840]
0x18008cf73  mov     rcx, cs:gNdpspEtwContext
0x18008cf7a  mov     rax, cs:gNdpspTemplateFunc
0x18008cf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf86  mov     r14d, [rsp+880h+var_860]
0x18008cf8b  xor     ebx, ebx
0x18008cf8d  test    rdi, rdi
0x18008cf90  jz      short loc_18008CFB2
0x18008cf92  call    cs:__imp_GetProcessHeap
0x18008cf99  nop     dword ptr [rax+rax+00h]
0x18008cf9e  mov     r8, rdi; lpMem
0x18008cfa1  xor     edx, edx; dwFlags
0x18008cfa3  mov     rcx, rax; hHeap
0x18008cfa6  call    cs:__imp_HeapFree
0x18008cfad  nop     dword ptr [rax+rax+00h]
0x18008cfb2  cmp     [rsp+880h+var_850], rbx
0x18008cfb7  jz      loc_18008CC78
0x18008cfbd  mov     ecx, r14d
0x18008cfc0  call    ReleaseObjReadLock
0x18008cfc5  jmp     loc_18008CC78
0x18008cfca  mov     ecx, cs:dwTraceId; dwTraceID
0x18008cfd0  cmp     ecx, 0FFFFFFFFh
0x18008cfd3  jz      short loc_18008CF86
0x18008cfd5  lea     rdx, aRaslinegetidGe_4; "RasLineGetID: GetNDProxyHandle failed w"...
0x18008cfdc  mov     r8d, esi
0x18008cfdf  call    cs:__imp_TracePrintfA
0x18008cfe6  nop     dword ptr [rax+rax+00h]
0x18008cfeb  jmp     short loc_18008CF86
0x18008cfed  xor     esi, esi
0x18008cfef  mov     dword ptr [r14+20h], 4
0x18008cff7  mov     [r14+24h], r15d
0x18008cffb  mov     ecx, [rbx]
0x18008cffd  add     ecx, 30h ; '0'
0x18008d000  mov     r8d, r15d
0x18008d003  mov     edx, ecx
0x18008d005  add     rdx, r14
0x18008d008  mov     [r14+28h], ecx
0x18008d00c  mov     eax, [rbx]
0x18008d00e  mov     [r14+2Ch], eax
0x18008d012  mov     dword ptr [r14+34h], 18h
0x18008d01a  mov     dword ptr [r14+30h], 18h
0x18008d022  mov     [r14+3Ch], rsi
0x18008d026  mov     [r14+38h], esi
0x18008d02a  test    r15d, r15d
0x18008d02d  jz      short loc_18008D06E
0x18008d02f  cmp     r15d, 7FFFFFFFh
0x18008d036  ja      short loc_18008D041
0x18008d038  cmp     r15d, 7FFFFFFEh
0x18008d03f  jbe     short loc_18008D046
0x18008d041  mov     [rdx], si
0x18008d044  jmp     short loc_18008D06E
0x18008d046  sub     r12, rdx
0x18008d049  movzx   eax, word ptr [r12+rdx]
0x18008d04e  test    ax, ax
0x18008d051  jz      short loc_18008D060
0x18008d053  mov     [rdx], ax
0x18008d056  add     rdx, 2
0x18008d05a  sub     r8, 1
0x18008d05e  jnz     short loc_18008D049
0x18008d060  test    r8, r8
0x18008d063  lea     rax, [rdx-2]
0x18008d067  cmovnz  rax, rdx
0x18008d06b  mov     [rax], si
0x18008d06e  mov     rdx, rdi; lpInBuffer
0x18008d071  mov     ecx, 8FFF23C8h; dwIoControlCode
  ... truncated ...
```
