# EdpCredSvcShouldCheckCaller(int *)

- ea: `0x1800861ec`
- end: `0x180086493`
- name: `?EdpCredSvcShouldCheckCaller@@YAJPEAH@Z`
- size: `679`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800878ac`
- `0x1800895e8`
- `0x18008b678`
- `0x180095594`
- `0x1800a1540`
- `0x1800a8660`
- `0x1800ad2d0`
- `0x1800bc65c`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800861ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800862d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800862d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800862c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008643c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800862c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008643c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008644a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008644a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008639c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008639c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086344`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086429`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086344`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086429`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008636e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008636e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008626d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008630d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008626d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008630d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008635d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008635d`

## string_xrefs

- `0x1800863c6`: `Thread is not impersonating`
- `0x180086388`: `Thread is impersonating allowed principal`

## pseudocode

```c
__int64 __fastcall EdpCredSvcShouldCheckCaller(int *a1)
{
  PSID *v1; // r14
  unsigned int v3; // edi
  int v4; // esi
  signed int LastError; // eax
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  signed int v8; // eax
  __int64 v9; // rbx
  signed int v10; // eax
  HANDLE v11; // rax
  char ReturnLength; // [rsp+20h] [rbp-20h]
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  DWORD v15; // [rsp+88h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+50h] BYREF

  v1 = 0;
  v15 = 0;
  TokenInformationLength = 0;
  hMem = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 179);
  if ( a1 )
  {
    v3 = 0;
    *a1 = 0;
    if ( NtCurrentTeb()->IsImpersonating )
    {
      v4 = 1;
      if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, 0, 0, &TokenInformationLength)
        && GetLastError() != 122 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        ReturnLength = -53;
LABEL_8:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v3, 38, ReturnLength);
        goto LABEL_28;
      }
      v6 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v1 = (PSID *)HeapAlloc(ProcessHeap, 8u, v6);
      if ( v1 )
      {
        if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, v1, TokenInformationLength, &v15) )
        {
          v9 = 0;
          while ( 1 )
          {
            if ( hMem )
            {
              LocalFree(hMem);
              hMem = 0;
            }
            if ( !ConvertStringSidToSidW(off_1800E26B8[v9], &hMem) )
              break;
            if ( EqualSid(hMem, *v1) )
            {
              v4 = 0;
              fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
                (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
                (unsigned int)L"Thread is impersonating allowed principal",
                v9,
                38,
                236);
              goto LABEL_28;
            }
            v9 = (unsigned int)(v9 + 1);
            if ( (_DWORD)v9 )
              goto LABEL_28;
          }
          v10 = GetLastError();
          v3 = v10;
          if ( v10 > 0 )
            v3 = (unsigned __int16)v10 | 0x80070000;
          ReturnLength = -30;
        }
        else
        {
          v8 = GetLastError();
          v3 = v8;
          if ( v8 > 0 )
            v3 = (unsigned __int16)v8 | 0x80070000;
          ReturnLength = -39;
        }
        goto LABEL_8;
      }
      v3 = -2147024882;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 38, 209);
    }
    else
    {
      v4 = 0;
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Thread is not impersonating",
        0,
        38,
        191);
    }
LABEL_28:
    *a1 = v4;
    goto LABEL_30;
  }
  v3 = -2147467261;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 38, 182);
LABEL_30:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v1 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v1);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v3,
    38,
    251);
  return v3;
}

```

## disassembly

```asm
0x1800861ec  push    rbp
0x1800861ee  push    rbx
0x1800861ef  push    rsi
0x1800861f0  push    rdi
0x1800861f1  push    r13
0x1800861f3  push    r14
0x1800861f5  push    r15
0x1800861f7  mov     rbp, rsp
0x1800861fa  sub     rsp, 40h
0x1800861fe  xor     r14d, r14d
0x180086201  mov     [rbp+arg_8], 0
0x180086208  lea     r8, sourceString
0x18008620f  mov     [rbp+TokenInformationLength], r14d
0x180086213  lea     rdx, EFS_TRACE_ENTER_EVENT
0x18008621a  mov     [rbp+hMem], r14
0x18008621e  mov     r15, rcx
0x180086221  mov     dword ptr [rsp+40h+ReturnLength], 1B3h
0x180086229  lea     r13d, [r14+26h]
0x18008622d  mov     r9d, r13d
0x180086230  call    fnEfsLogTrace1Strings
0x180086235  test    r15, r15
0x180086238  jz      loc_1800863F7
0x18008623e  xor     eax, eax
0x180086240  xor     edi, edi
0x180086242  mov     [r15], eax
0x180086245  mov     eax, gs:179Ch
0x18008624d  test    eax, eax
0x18008624f  jz      loc_1800863BE
0x180086255  lea     rax, [rbp+TokenInformationLength]
0x180086259  xor     r9d, r9d; TokenInformationLength
0x18008625c  lea     esi, [rdi+1]
0x18008625f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180086264  mov     edx, esi; TokenInformationClass
0x180086266  lea     rcx, [rdi-5]; TokenHandle
0x18008626a  xor     r8d, r8d; TokenInformation
0x18008626d  call    cs:__imp_GetTokenInformation
0x180086273  test    eax, eax
0x180086275  jnz     short loc_1800862BD
0x180086277  call    cs:__imp_GetLastError
0x18008627d  cmp     eax, 7Ah ; 'z'
0x180086280  jz      short loc_1800862BD
0x180086282  call    cs:__imp_GetLastError
0x180086288  mov     edi, eax
0x18008628a  test    eax, eax
0x18008628c  jle     short loc_180086297
0x18008628e  movzx   edi, ax
0x180086291  or      edi, 80070000h
0x180086297  mov     dword ptr [rsp+40h+ReturnLength], 1CBh
0x18008629f  mov     r8d, edi
0x1800862a2  mov     rcx, cs:g_hPublisher
0x1800862a9  lea     rdx, EFS_TRACE_ERROR
0x1800862b0  mov     r9d, r13d
0x1800862b3  call    fnEfsLogTrace1
0x1800862b8  jmp     loc_1800863F2
0x1800862bd  mov     ebx, [rbp+TokenInformationLength]
0x1800862c0  call    cs:__imp_GetProcessHeap
0x1800862c6  mov     r8d, ebx; dwBytes
0x1800862c9  mov     edx, 8; dwFlags
0x1800862ce  mov     rcx, rax; hHeap
0x1800862d1  call    cs:__imp_HeapAlloc
0x1800862d7  mov     r14, rax
0x1800862da  test    rax, rax
0x1800862dd  jnz     short loc_1800862F4
0x1800862df  mov     edi, 8007000Eh
0x1800862e4  mov     dword ptr [rsp+40h+ReturnLength], 1D1h
0x1800862ec  mov     r8d, 8007000Eh
0x1800862f2  jmp     short loc_1800862A2
0x1800862f4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800862f8  lea     rax, [rbp+arg_8]
0x1800862fc  mov     r8, r14; TokenInformation
0x1800862ff  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180086304  mov     edx, esi; TokenInformationClass
0x180086306  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18008630d  call    cs:__imp_GetTokenInformation
0x180086313  test    eax, eax
0x180086315  jnz     short loc_180086339
0x180086317  call    cs:__imp_GetLastError
0x18008631d  mov     edi, eax
0x18008631f  test    eax, eax
0x180086321  jle     short loc_18008632C
0x180086323  movzx   edi, ax
0x180086326  or      edi, 80070000h
0x18008632c  mov     dword ptr [rsp+40h+ReturnLength], 1D9h
0x180086334  jmp     loc_18008629F
0x180086339  xor     ebx, ebx
0x18008633b  mov     rcx, [rbp+hMem]; hMem
0x18008633f  test    rcx, rcx
0x180086342  jz      short loc_18008634E
0x180086344  call    cs:__imp_LocalFree
0x18008634a  mov     [rbp+hMem], rdi
0x18008634e  lea     rax, off_1800E26B8; "S-1-5-18"
0x180086355  mov     rcx, [rax+rbx*8]; StringSid
0x180086359  lea     rdx, [rbp+hMem]; Sid
0x18008635d  call    cs:__imp_ConvertStringSidToSidW
0x180086363  test    eax, eax
0x180086365  jz      short loc_18008639C
0x180086367  mov     rdx, [r14]; pSid2
0x18008636a  mov     rcx, [rbp+hMem]; pSid1
0x18008636e  call    cs:__imp_EqualSid
0x180086374  test    eax, eax
0x180086376  jnz     short loc_180086380
0x180086378  add     ebx, esi
0x18008637a  cmp     ebx, esi
0x18008637c  jb      short loc_18008633B
0x18008637e  jmp     short loc_1800863F2
0x180086380  mov     [rsp+40h+var_10], 1ECh
0x180086388  lea     r9, aThreadIsImpers; "Thread is impersonating allowed princip"...
0x18008638f  mov     [rsp+40h+var_18], r13d
0x180086394  xor     esi, esi
0x180086396  mov     dword ptr [rsp+40h+ReturnLength], ebx
0x18008639a  jmp     short loc_1800863D8
0x18008639c  call    cs:__imp_GetLastError
0x1800863a2  mov     edi, eax
0x1800863a4  test    eax, eax
0x1800863a6  jle     short loc_1800863B1
0x1800863a8  movzx   edi, ax
0x1800863ab  or      edi, 80070000h
0x1800863b1  mov     dword ptr [rsp+40h+ReturnLength], 1E2h
0x1800863b9  jmp     loc_18008629F
0x1800863be  mov     [rsp+40h+var_10], 1BFh
0x1800863c6  lea     r9, aThreadIsNotImp; "Thread is not impersonating"
0x1800863cd  xor     esi, esi
0x1800863cf  mov     [rsp+40h+var_18], r13d
0x1800863d4  mov     dword ptr [rsp+40h+ReturnLength], esi
0x1800863d8  mov     rcx, cs:g_hPublisher
0x1800863df  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x1800863e6  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x1800863ed  call    fnEfsLogTrace1String1Dword
0x1800863f2  mov     [r15], esi
0x1800863f5  jmp     short loc_180086420
0x1800863f7  mov     rcx, cs:g_hPublisher
0x1800863fe  lea     rdx, EFS_TRACE_ERROR
0x180086405  mov     r9d, r13d
0x180086408  mov     dword ptr [rsp+40h+ReturnLength], 1B6h
0x180086410  mov     r8d, 80004003h
0x180086416  mov     edi, 80004003h
0x18008641b  call    fnEfsLogTrace1
0x180086420  mov     rcx, [rbp+hMem]; hMem
0x180086424  test    rcx, rcx
0x180086427  jz      short loc_180086437
0x180086429  call    cs:__imp_LocalFree
0x18008642f  mov     [rbp+hMem], 0
0x180086437  test    r14, r14
0x18008643a  jz      short loc_180086450
0x18008643c  call    cs:__imp_GetProcessHeap
0x180086442  mov     r8, r14; lpMem
0x180086445  xor     edx, edx; dwFlags
0x180086447  mov     rcx, rax; hHeap
0x18008644a  call    cs:__imp_HeapFree
0x180086450  mov     rcx, cs:g_hPublisher
0x180086457  lea     r9, sourceString
0x18008645e  mov     [rsp+40h+var_10], 1FBh
0x180086466  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x18008646d  mov     [rsp+40h+var_18], r13d
0x180086472  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180086479  mov     dword ptr [rsp+40h+ReturnLength], edi
0x18008647d  call    fnEfsLogTrace1String1Dword
0x180086482  mov     eax, edi
0x180086484  add     rsp, 40h
0x180086488  pop     r15
0x18008648a  pop     r14
0x18008648c  pop     r13
0x18008648e  pop     rdi
0x18008648f  pop     rsi
0x180086490  pop     rbx
0x180086491  pop     rbp
0x180086492  retn
```
