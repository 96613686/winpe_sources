# CMpeg2SharedMem::Create_(ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800b45bc`
- end: `0x1800b4809`
- name: `?Create_@CMpeg2SharedMem@@AEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(CMpeg2SharedMem *__hidden this, LPCWSTR lpName, DWORD dwMaximumSizeLow, LPSECURITY_ATTRIBUTES lpFileMappingAttributes)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b407c`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180051ce4`
- `0x180087490`
- `0x1800b45bc`
- `0x1800b4810`
- `0x1800b4e78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b45fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b47b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b45fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b47b8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b4653`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b4653`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800b46b6`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800b46b6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b4742`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b4742`

## string_xrefs

- `0x1800b45d7`: `CMpeg2SharedMem::Create_`

## pseudocode

```c
__int64 __fastcall CMpeg2SharedMem::Create_(
        HANDLE *this,
        LPCWSTR lpName,
        DWORD dwMaximumSizeLow,
        LPSECURITY_ATTRIBUTES lpFileMappingAttributes)
{
  char CurrentProcessId; // al
  int v9; // edx
  int v10; // r8d
  HANDLE FileMappingW; // rax
  DWORD LastError; // eax
  int v13; // edi
  HANDLE v14; // rax
  DWORD v15; // eax
  signed int v16; // ebx
  LPVOID v17; // rax
  signed int v18; // eax
  char v19; // al
  char v21; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CMpeg2SharedMem::Create_", 74);
  if ( (unsigned __int8)byte_1800EACCB >= 2u )
  {
    CurrentProcessId = GetCurrentProcessId();
    WPP_SF_qSDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      v9,
      v10,
      (_DWORD)this,
      (__int64)lpName,
      dwMaximumSizeLow,
      (char)lpFileMappingAttributes,
      CurrentProcessId);
  }
  CMpeg2SharedMem::Free_((CMpeg2SharedMem *)this);
  *((_DWORD *)this + 4) = dwMaximumSizeLow;
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   lpFileMappingAttributes,
                   4u,
                   0,
                   dwMaximumSizeLow,
                   lpName);
  this[3] = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( byte_1800EACCB )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        13,
        &WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids,
        this,
        LastError);
    if ( v13 == 5 )
    {
      v14 = OpenFileMappingW(4u, 0, lpName);
      this[3] = v14;
      if ( v14 )
        goto LABEL_16;
      v15 = GetLastError();
      v13 = v15;
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 14, &WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids, this, v15);
    }
    if ( v13 )
    {
      if ( v13 > 0 )
        v16 = (unsigned __int16)v13 | 0x80070000;
      else
        v16 = v13;
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 15, &WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids, this, v13);
LABEL_22:
      if ( v16 < 0 )
        CMpeg2SharedMem::Free_((CMpeg2SharedMem *)this);
      goto LABEL_26;
    }
  }
LABEL_16:
  v17 = MapViewOfFile(this[3], 6u, 0, 0, 0);
  this[1] = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v16 = (unsigned __int16)v18 | 0x80070000;
    else
      v16 = v18;
    if ( byte_1800EACCB )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, &WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids, this, v18);
    goto LABEL_22;
  }
  v16 = 0;
  if ( (unsigned __int8)byte_1800EACCB >= 2u )
  {
    v19 = GetCurrentProcessId();
    WPP_SF_qSD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      17,
      (unsigned int)&WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids,
      (_DWORD)this,
      (__int64)lpName,
      v19);
  }
LABEL_26:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800b45bc  mov     [rsp+arg_0], rbx
0x1800b45c1  mov     [rsp+arg_8], rbp
0x1800b45c6  push    rsi
0x1800b45c7  push    rdi
0x1800b45c8  push    r15
0x1800b45ca  sub     rsp, 40h
0x1800b45ce  mov     ebx, r8d
0x1800b45d1  mov     rbp, rdx
0x1800b45d4  mov     rsi, rcx
0x1800b45d7  lea     rdx, aCmpeg2sharedme_0; "CMpeg2SharedMem::Create_"
0x1800b45de  mov     r8d, 4Ah ; 'J'; int
0x1800b45e4  lea     rcx, [rsp+58h+arg_10]; this
0x1800b45e9  mov     rdi, r9
0x1800b45ec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b45f1  cmp     cs:byte_1800EACCB, 2
0x1800b45f8  jb      short loc_1800B462E
0x1800b45fa  call    cs:__imp_GetCurrentProcessId
0x1800b4601  nop     dword ptr [rax+rax+00h]
0x1800b4606  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b460d  mov     r9, rsi
0x1800b4610  mov     [rsp+58h+var_20], eax
0x1800b4614  mov     [rsp+58h+var_28], rdi
0x1800b4619  mov     dword ptr [rsp+58h+lpName], ebx
0x1800b461d  mov     rcx, [rcx+88h]
0x1800b4624  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbp
0x1800b4629  call    WPP_SF_qSDqD
0x1800b462e  mov     rcx, rsi; this
0x1800b4631  call    ?Free_@CMpeg2SharedMem@@AEAAXXZ; CMpeg2SharedMem::Free_(void)
0x1800b4636  xor     r9d, r9d; dwMaximumSizeHigh
0x1800b4639  mov     [rsi+10h], ebx
0x1800b463c  mov     [rsp+58h+lpName], rbp; lpName
0x1800b4641  mov     rdx, rdi; lpFileMappingAttributes
0x1800b4644  mov     [rsp+58h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800b4648  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800b464c  lea     ebx, [r9+4]
0x1800b4650  mov     r8d, ebx; flProtect
0x1800b4653  call    cs:__imp_CreateFileMappingW
0x1800b465a  nop     dword ptr [rax+rax+00h]
0x1800b465f  mov     [rsi+18h], rax
0x1800b4663  lea     r15, WPP_bda1015b036f3b4fdfb5a2956de48d7b_Traceguids
0x1800b466a  test    rax, rax
0x1800b466d  jnz     loc_1800B472B
0x1800b4673  call    cs:__imp_GetLastError
0x1800b467a  nop     dword ptr [rax+rax+00h]
0x1800b467f  mov     edi, eax
0x1800b4681  cmp     cs:byte_1800EACCB, 1
0x1800b4688  jb      short loc_1800B46AA
0x1800b468a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4691  lea     edx, [rbx+9]
0x1800b4694  mov     r9, rsi
0x1800b4697  mov     [rsp+58h+dwMaximumSizeLow], eax
0x1800b469b  mov     r8, r15
0x1800b469e  mov     rcx, [rcx+88h]
0x1800b46a5  call    WPP_SF_qD
0x1800b46aa  cmp     edi, 5
0x1800b46ad  jnz     short loc_1800B4704
0x1800b46af  mov     r8, rbp; lpName
0x1800b46b2  xor     edx, edx; bInheritHandle
0x1800b46b4  mov     ecx, ebx; dwDesiredAccess
0x1800b46b6  call    cs:__imp_OpenFileMappingW
0x1800b46bd  nop     dword ptr [rax+rax+00h]
0x1800b46c2  mov     [rsi+18h], rax
0x1800b46c6  test    rax, rax
0x1800b46c9  jnz     short loc_1800B472B
0x1800b46cb  call    cs:__imp_GetLastError
0x1800b46d2  nop     dword ptr [rax+rax+00h]
0x1800b46d7  mov     edi, eax
0x1800b46d9  cmp     cs:byte_1800EACCB, 1
0x1800b46e0  jb      short loc_1800B4704
0x1800b46e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b46e9  mov     edx, 0Eh
0x1800b46ee  mov     r9, rsi
0x1800b46f1  mov     [rsp+58h+dwMaximumSizeLow], eax
0x1800b46f5  mov     r8, r15
0x1800b46f8  mov     rcx, [rcx+88h]
0x1800b46ff  call    WPP_SF_qD
0x1800b4704  test    edi, edi
0x1800b4706  jz      short loc_1800B472B
0x1800b4708  jg      short loc_1800B470E
0x1800b470a  mov     ebx, edi
0x1800b470c  jmp     short loc_1800B4717
0x1800b470e  movzx   ebx, di
0x1800b4711  or      ebx, 80070000h
0x1800b4717  cmp     cs:byte_1800EACCB, 1
0x1800b471e  jb      short loc_1800B479F
0x1800b4720  mov     edx, 0Fh
0x1800b4725  mov     [rsp+58h+dwMaximumSizeLow], edi
0x1800b4729  jmp     short loc_1800B4786
0x1800b472b  mov     rcx, [rsi+18h]; hFileMappingObject
0x1800b472f  xor     r9d, r9d; dwFileOffsetLow
0x1800b4732  xor     r8d, r8d; dwFileOffsetHigh
0x1800b4735  mov     qword ptr [rsp+58h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800b473e  lea     edx, [r9+6]; dwDesiredAccess
0x1800b4742  call    cs:__imp_MapViewOfFile
0x1800b4749  nop     dword ptr [rax+rax+00h]
0x1800b474e  mov     [rsi+8], rax
0x1800b4752  test    rax, rax
0x1800b4755  jnz     short loc_1800B47AD
0x1800b4757  call    cs:__imp_GetLastError
0x1800b475e  nop     dword ptr [rax+rax+00h]
0x1800b4763  test    eax, eax
0x1800b4765  jg      short loc_1800B476B
0x1800b4767  mov     ebx, eax
0x1800b4769  jmp     short loc_1800B4774
0x1800b476b  movzx   ebx, ax
0x1800b476e  or      ebx, 80070000h
0x1800b4774  cmp     cs:byte_1800EACCB, 1
0x1800b477b  jb      short loc_1800B479F
0x1800b477d  mov     edx, 10h
0x1800b4782  mov     [rsp+58h+dwMaximumSizeLow], eax
0x1800b4786  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b478d  mov     r9, rsi
0x1800b4790  mov     r8, r15
0x1800b4793  mov     rcx, [rcx+88h]
0x1800b479a  call    WPP_SF_qD
0x1800b479f  test    ebx, ebx
0x1800b47a1  jns     short loc_1800B47E9
0x1800b47a3  mov     rcx, rsi; this
0x1800b47a6  call    ?Free_@CMpeg2SharedMem@@AEAAXXZ; CMpeg2SharedMem::Free_(void)
0x1800b47ab  jmp     short loc_1800B47E9
0x1800b47ad  xor     ebx, ebx
0x1800b47af  cmp     cs:byte_1800EACCB, 2
0x1800b47b6  jb      short loc_1800B47E9
0x1800b47b8  call    cs:__imp_GetCurrentProcessId
0x1800b47bf  nop     dword ptr [rax+rax+00h]
0x1800b47c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b47cb  lea     edx, [rbx+11h]
0x1800b47ce  mov     dword ptr [rsp+58h+lpName], eax
0x1800b47d2  mov     r9, rsi
0x1800b47d5  mov     r8, r15
0x1800b47d8  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbp
0x1800b47dd  mov     rcx, [rcx+88h]
0x1800b47e4  call    WPP_SF_qSD
0x1800b47e9  lea     rcx, [rsp+58h+arg_10]; this
0x1800b47ee  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b47f3  mov     rbp, [rsp+58h+arg_8]
0x1800b47f8  mov     eax, ebx
0x1800b47fa  mov     rbx, [rsp+58h+arg_0]
0x1800b47ff  add     rsp, 40h
0x1800b4803  pop     r15
0x1800b4805  pop     rdi
0x1800b4806  pop     rsi
0x1800b4807  retn
```
