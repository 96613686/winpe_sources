# GetCurrentUserSidInternal(void * *)

- ea: `0x180008520`
- end: `0x180008930`
- name: `?GetCurrentUserSidInternal@@YAJPEAPEAX@Z`
- size: `1040`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008044`

## callees

- `0x180008520`
- `0x18001b914`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008770`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008770`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800087b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800087b2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008599`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000860e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008599`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000860e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000871b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000871b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008707`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000877e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008707`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000877e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008792`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008832`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800086a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800086a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000854c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000854c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008690`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000856b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000856b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088fa`

## string_xrefs

- `0x1800086e0`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x18000874f`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x180008819`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x18000885a`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x180008878`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x18000889b`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x1800088be`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x1800088dc`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSidInternal(void **a1)
{
  PSID *v2; // rdi
  void *v3; // rsi
  HANDLE CurrentThread; // rax
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  signed int v7; // eax
  signed int v8; // ebx
  HANDLE CurrentProcess; // rax
  signed int v11; // eax
  HANDLE v12; // rax
  signed int v13; // eax
  DWORD LengthSid; // ebp
  HANDLE v15; // rax
  void *v16; // rax
  signed int v17; // eax
  signed int LastError; // eax
  HANDLE v19; // rax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  int ReturnLengtha; // [rsp+20h] [rbp-38h]
  int ReturnLengthb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_2:
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v8 = -2147418113;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)0x8000FFFFLL,
        ReturnLengtha);
    }
    else if ( GetLastError() == 122 )
    {
      v5 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v2 = (PSID *)HeapAlloc(ProcessHeap, 0, v5);
      if ( v2 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        {
          LengthSid = GetLengthSid(*v2);
          v15 = GetProcessHeap();
          v16 = HeapAlloc(v15, 0, LengthSid);
          v3 = v16;
          if ( v16 )
          {
            if ( CopySid(LengthSid, v16, *v2) )
            {
              *a1 = v3;
              v8 = 0;
              v3 = 0;
            }
            else
            {
              LastError = GetLastError();
              v8 = LastError;
              if ( LastError > 0 )
                v8 = (unsigned __int16)LastError | 0x80070000;
              if ( v8 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x30,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
                  (const char *)(unsigned int)v8,
                  ReturnLengthb);
            }
          }
          else
          {
            v8 = -2147024882;
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2F,
              (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
              (const char *)0x8007000ELL,
              ReturnLengthb);
          }
        }
        else
        {
          v7 = GetLastError();
          v8 = v7;
          if ( v7 > 0 )
            v8 = (unsigned __int16)v7 | 0x80070000;
          if ( v8 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2B,
              (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
              (const char *)(unsigned int)v8,
              ReturnLengthb);
        }
      }
      else
      {
        v8 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
          (const char *)0x8007000ELL,
          ReturnLengtha);
      }
    }
    else
    {
      v17 = GetLastError();
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
          (const char *)(unsigned int)v8,
          ReturnLengtha);
    }
    goto LABEL_10;
  }
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_2;
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
  }
  else
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
  }
LABEL_10:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v2);
  }
  if ( v3 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008520  push    rbx
0x180008522  push    rsi
0x180008523  sub     rsp, 48h
0x180008527  mov     [rsp+58h+var_18], rdi
0x18000852c  mov     [rsp+58h+var_20], r14
0x180008531  mov     r14, rcx
0x180008534  mov     [rsp+58h+var_28], r15
0x180008539  xor     r15d, r15d
0x18000853c  mov     edi, r15d
0x18000853f  mov     [rsp+58h+TokenHandle], r15
0x180008544  mov     [rsp+58h+TokenInformationLength], r15d
0x180008549  mov     esi, r15d
0x18000854c  call    cs:__imp_GetCurrentThread
0x180008553  nop     dword ptr [rax+rax+00h]
0x180008558  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000855d  mov     edx, 8; DesiredAccess
0x180008562  mov     rcx, rax; ThreadHandle
0x180008565  mov     r8d, 1; OpenAsSelf
0x18000856b  call    cs:__imp_OpenThreadToken
0x180008572  nop     dword ptr [rax+rax+00h]
0x180008577  test    eax, eax
0x180008579  jz      loc_180008679
0x18000857f  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180008584  lea     rax, [rsp+58h+TokenInformationLength]
0x180008589  xor     r9d, r9d; TokenInformationLength
0x18000858c  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x180008591  xor     r8d, r8d; TokenInformation
0x180008594  mov     edx, 1; TokenInformationClass
0x180008599  call    cs:__imp_GetTokenInformation
0x1800085a0  nop     dword ptr [rax+rax+00h]
0x1800085a5  test    eax, eax
0x1800085a7  jnz     loc_180008873
0x1800085ad  call    cs:__imp_GetLastError
0x1800085b4  nop     dword ptr [rax+rax+00h]
0x1800085b9  cmp     eax, 7Ah ; 'z'
0x1800085bc  jnz     loc_1800087F1
0x1800085c2  mov     ebx, [rsp+58h+TokenInformationLength]
0x1800085c6  call    cs:__imp_GetProcessHeap
0x1800085cd  nop     dword ptr [rax+rax+00h]
0x1800085d2  mov     r8d, ebx; dwBytes
0x1800085d5  xor     edx, edx; dwFlags
0x1800085d7  mov     rcx, rax; hHeap
0x1800085da  call    cs:__imp_HeapAlloc
0x1800085e1  nop     dword ptr [rax+rax+00h]
0x1800085e6  mov     rdi, rax
0x1800085e9  test    rax, rax
0x1800085ec  jz      loc_180008896
0x1800085f2  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800085f7  lea     rax, [rsp+58h+TokenInformationLength]
0x1800085fc  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180008601  mov     r8, rdi; TokenInformation
0x180008604  mov     edx, 1; TokenInformationClass
0x180008609  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000860e  call    cs:__imp_GetTokenInformation
0x180008615  nop     dword ptr [rax+rax+00h]
0x18000861a  test    eax, eax
0x18000861c  jnz     loc_180008768
0x180008622  call    cs:__imp_GetLastError
0x180008629  nop     dword ptr [rax+rax+00h]
0x18000862e  mov     ebx, eax
0x180008630  test    eax, eax
0x180008632  jg      loc_1800086F9
0x180008638  test    ebx, ebx
0x18000863a  js      loc_1800088B9
0x180008640  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180008645  mov     r15, [rsp+58h+var_28]
0x18000864a  mov     r14, [rsp+58h+var_20]
0x18000864f  test    rcx, rcx
0x180008652  jnz     loc_1800088FA
0x180008658  test    rdi, rdi
0x18000865b  jnz     loc_180008707
0x180008661  mov     rdi, [rsp+58h+var_18]
0x180008666  test    rsi, rsi
0x180008669  jnz     loc_18000890B
0x18000866f  mov     eax, ebx
0x180008671  add     rsp, 48h
0x180008675  pop     rsi
0x180008676  pop     rbx
0x180008677  retn
0x180008679  call    cs:__imp_GetLastError
0x180008680  nop     dword ptr [rax+rax+00h]
0x180008685  cmp     eax, 3F0h
0x18000868a  jnz     loc_18000872C
0x180008690  call    cs:__imp_GetCurrentProcess
0x180008697  nop     dword ptr [rax+rax+00h]
0x18000869c  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800086a1  mov     edx, 8; DesiredAccess
0x1800086a6  mov     rcx, rax; ProcessHandle
0x1800086a9  call    cs:__imp_OpenProcessToken
0x1800086b0  nop     dword ptr [rax+rax+00h]
0x1800086b5  test    eax, eax
0x1800086b7  jnz     loc_18000857F
0x1800086bd  call    cs:__imp_GetLastError
0x1800086c4  nop     dword ptr [rax+rax+00h]
0x1800086c9  mov     ebx, eax
0x1800086cb  test    eax, eax
0x1800086cd  jg      loc_1800087E3
0x1800086d3  test    ebx, ebx
0x1800086d5  jns     loc_180008640
0x1800086db  mov     rcx, [rsp+58h]; this
0x1800086e0  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800086e7  mov     r9d, ebx; char *
0x1800086ea  mov     edx, 23h ; '#'; void *
0x1800086ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800086f4  jmp     loc_180008640
0x1800086f9  movzx   ebx, ax
0x1800086fc  or      ebx, 80070000h
0x180008702  jmp     loc_180008638
0x180008707  call    cs:__imp_GetProcessHeap
0x18000870e  nop     dword ptr [rax+rax+00h]
0x180008713  mov     r8, rdi; lpMem
0x180008716  xor     edx, edx; dwFlags
0x180008718  mov     rcx, rax; hHeap
0x18000871b  call    cs:__imp_HeapFree
0x180008722  nop     dword ptr [rax+rax+00h]
0x180008727  jmp     loc_180008661
0x18000872c  call    cs:__imp_GetLastError
0x180008733  nop     dword ptr [rax+rax+00h]
0x180008738  mov     ebx, eax
0x18000873a  test    eax, eax
0x18000873c  jg      loc_1800087D5
0x180008742  test    ebx, ebx
0x180008744  jns     loc_180008640
0x18000874a  mov     rcx, [rsp+58h]; this
0x18000874f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x180008756  mov     r9d, ebx; char *
0x180008759  mov     edx, 20h ; ' '; void *
0x18000875e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008763  jmp     loc_180008640
0x180008768  mov     rcx, [rdi]; pSid
0x18000876b  mov     [rsp+58h+arg_0], rbp
0x180008770  call    cs:__imp_GetLengthSid
0x180008777  nop     dword ptr [rax+rax+00h]
0x18000877c  mov     ebp, eax
0x18000877e  call    cs:__imp_GetProcessHeap
0x180008785  nop     dword ptr [rax+rax+00h]
0x18000878a  mov     r8d, ebp; dwBytes
0x18000878d  xor     edx, edx; dwFlags
0x18000878f  mov     rcx, rax; hHeap
0x180008792  call    cs:__imp_HeapAlloc
0x180008799  nop     dword ptr [rax+rax+00h]
0x18000879e  mov     rsi, rax
0x1800087a1  test    rax, rax
0x1800087a4  jz      loc_1800088D7
0x1800087aa  mov     r8, [rdi]; pSourceSid
0x1800087ad  mov     rdx, rax; pDestinationSid
0x1800087b0  mov     ecx, ebp; nDestinationSidLength
0x1800087b2  call    cs:__imp_CopySid
0x1800087b9  nop     dword ptr [rax+rax+00h]
0x1800087be  test    eax, eax
0x1800087c0  jz      short loc_180008832
0x1800087c2  mov     [r14], rsi
0x1800087c5  mov     ebx, r15d
0x1800087c8  mov     rsi, r15
0x1800087cb  mov     rbp, [rsp+58h+arg_0]
0x1800087d0  jmp     loc_180008640
0x1800087d5  movzx   ebx, ax
0x1800087d8  or      ebx, 80070000h
0x1800087de  jmp     loc_180008742
0x1800087e3  movzx   ebx, ax
0x1800087e6  or      ebx, 80070000h
0x1800087ec  jmp     loc_1800086D3
0x1800087f1  call    cs:__imp_GetLastError
0x1800087f8  nop     dword ptr [rax+rax+00h]
0x1800087fd  mov     ebx, eax
0x1800087ff  test    eax, eax
0x180008801  jle     short loc_18000880C
0x180008803  movzx   ebx, ax
0x180008806  or      ebx, 80070000h
0x18000880c  test    ebx, ebx
0x18000880e  jns     loc_180008640
0x180008814  mov     rcx, [rsp+58h]; this
0x180008819  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x180008820  mov     r9d, ebx; char *
0x180008823  mov     edx, 26h ; '&'; void *
0x180008828  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000882d  jmp     loc_180008640
0x180008832  call    cs:__imp_GetLastError
0x180008839  nop     dword ptr [rax+rax+00h]
0x18000883e  mov     ebx, eax
0x180008840  test    eax, eax
0x180008842  jle     short loc_18000884D
0x180008844  movzx   ebx, ax
0x180008847  or      ebx, 80070000h
0x18000884d  test    ebx, ebx
0x18000884f  jns     loc_1800087CB
0x180008855  mov     rcx, [rsp+58h]; this
0x18000885a  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x180008861  mov     r9d, ebx; char *
0x180008864  mov     edx, 30h ; '0'; void *
0x180008869  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000886e  jmp     loc_1800087CB
0x180008873  mov     rcx, [rsp+58h]; this
0x180008878  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x18000887f  mov     ebx, 8000FFFFh
0x180008884  mov     edx, 25h ; '%'; void *
0x180008889  mov     r9d, ebx; char *
0x18000888c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008891  jmp     loc_180008640
0x180008896  mov     rcx, [rsp+58h]; this
0x18000889b  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800088a2  mov     ebx, 8007000Eh
0x1800088a7  mov     edx, 28h ; '('; void *
0x1800088ac  mov     r9d, ebx; char *
0x1800088af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800088b4  jmp     loc_180008640
0x1800088b9  mov     rcx, [rsp+58h]; this
0x1800088be  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800088c5  mov     r9d, ebx; char *
0x1800088c8  mov     edx, 2Bh ; '+'; void *
0x1800088cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800088d2  jmp     loc_180008640
0x1800088d7  mov     rcx, [rsp+58h]; this
0x1800088dc  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800088e3  mov     ebx, 8007000Eh
0x1800088e8  mov     edx, 2Fh ; '/'; void *
0x1800088ed  mov     r9d, ebx; char *
0x1800088f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800088f5  jmp     loc_1800087CB
0x1800088fa  call    cs:__imp_CloseHandle
0x180008901  nop     dword ptr [rax+rax+00h]
0x180008906  jmp     loc_180008658
0x18000890b  call    cs:__imp_GetProcessHeap
0x180008912  nop     dword ptr [rax+rax+00h]
0x180008917  mov     r8, rsi; lpMem
0x18000891a  xor     edx, edx; dwFlags
0x18000891c  mov     rcx, rax; hHeap
0x18000891f  call    cs:__imp_HeapFree
0x180008926  nop     dword ptr [rax+rax+00h]
0x18000892b  jmp     loc_18000866F
```
