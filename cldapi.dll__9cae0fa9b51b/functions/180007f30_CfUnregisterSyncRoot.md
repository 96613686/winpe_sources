# CfUnregisterSyncRoot

- ea: `0x180007f30`
- end: `0x1800082a8`
- name: `CfUnregisterSyncRoot`
- size: `888`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800046bc`
- `0x180007f30`
- `0x180010294`
- `0x1800118f4`
- `0x180012054`
- `0x180012354`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007f8e`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180008276`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007f8e`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180008276`
- `ntdll!RtlNtStatusToDosError` at `0x18000802c`
- `ntdll!RtlNtStatusToDosError` at `0x18000802c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081b1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007fb6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007fb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000823c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000823c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008250`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000819d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000819d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008267`

## string_xrefs

- `0x180007fe1`: `SyncRootPath can't be NULL`
- `0x18000804b`: `CfpCreateFile Failed`

## pseudocode

```c
__int64 __fastcall CfUnregisterSyncRoot(__int64 a1)
{
  char *v2; // rsi
  __int64 v3; // rcx
  char *v4; // r14
  _DWORD *v5; // r15
  char v6; // r12
  int SyncRootInfoByHandle; // ebx
  const wchar_t *v8; // rdi
  __int64 v9; // rdx
  NTSTATUS File; // eax
  signed int v11; // eax
  int v12; // r12d
  unsigned int v13; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  int v16; // ecx
  int v17; // edx
  signed int LastError; // eax
  HANDLE v19; // rax
  __int64 v20; // rcx
  HANDLE FileHandle; // [rsp+28h] [rbp-D8h]
  char v23; // [rsp+50h] [rbp-B0h]
  __int64 FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v29; // [rsp+D4h] [rbp-2Ch] BYREF
  char v30; // [rsp+2D4h] [rbp+1D4h] BYREF

  memset_0(v28, 0, 0x404u);
  LODWORD(v2) = 0;
  LOBYTE(v3) = 2;
  UnbiasedTime = 0;
  v4 = 0;
  FileInformation = 0;
  v5 = 0;
  v23 = RtlSetThreadPlaceholderCompatibilityMode(v3);
  v6 = v23;
  memset_0(v26, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByHandle = a1 == 0 ? 0x57 : 0;
  if ( !a1 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle > -1 )
  {
    SyncRootInfoByHandle = GlobalPortInit(0);
    if ( SyncRootInfoByHandle > -1 )
    {
      LODWORD(FileHandle) = 2097185;
      File = CfpCreateFile(a1, v9, 129, 7);
      v11 = RtlNtStatusToDosError(File);
      SyncRootInfoByHandle = v11;
      if ( v11 > 0 )
        SyncRootInfoByHandle = (unsigned __int16)v11 | 0x80070000;
      if ( SyncRootInfoByHandle > -1 )
      {
        v4 = &v30;
        v2 = &v29;
        if ( (int)CfpGetSyncRootInfoByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0) < 0 )
        {
          v4 = 0;
          LODWORD(v2) = 0;
        }
        v12 = 0;
        while ( 1 )
        {
          if ( v5 )
          {
            v13 = v5[263] + 1056;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v5);
          }
          else
          {
            v13 = 1056;
          }
          v15 = GetProcessHeap();
          v5 = HeapAlloc(v15, 0, v13);
          SyncRootInfoByHandle = v5 == 0 ? 8 : 0;
          if ( !v5 )
            SyncRootInfoByHandle |= 0x80070000;
          if ( SyncRootInfoByHandle < 0 )
          {
            v8 = L"Allocating Memory for syncRootStdInfo Failed";
            goto LABEL_37;
          }
          SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0);
          if ( SyncRootInfoByHandle != -2147024662 )
            break;
          if ( ++v12 >= 2 )
            goto LABEL_25;
        }
        if ( SyncRootInfoByHandle <= -1 )
        {
LABEL_25:
          v8 = L"CfpGetSyncRootInfoByHandle Failed";
          goto LABEL_37;
        }
        v16 = v5[6];
        if ( !v16 || (unsigned int)(v16 + 0x3FFFFFFF) <= 1 || (v16 & 0x40) != 0 )
        {
          if ( GetFileInformationByHandleEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, FileAttributeTagInfo, &FileInformation, 8u) )
          {
            SyncRootInfoByHandle = 0;
          }
          else
          {
            LastError = GetLastError();
            SyncRootInfoByHandle = LastError;
            if ( LastError > 0 )
              SyncRootInfoByHandle = (unsigned __int16)LastError | 0x80070000;
          }
          if ( SyncRootInfoByHandle > -1 )
          {
            v8 = 0;
            CfpRecurseDirectory(-1, v17, FileInformation, SHIDWORD(FileInformation), 0, FileHandle);
            RevertSyncRoot((HANDLE)0xFFFFFFFFFFFFFFFFLL);
          }
          else
          {
            v8 = L"GetFileInformationByHandleEx Failed";
          }
        }
        else
        {
          SyncRootInfoByHandle = -2147024516;
          v8 = L"Can't unregister when a provider is Connected";
        }
LABEL_37:
        v6 = v23;
      }
      else
      {
        v8 = L"CfpCreateFile Failed";
      }
    }
    else
    {
      v8 = L"GlobalPortInit Failed";
    }
  }
  else
  {
    v8 = L"SyncRootPath can't be NULL";
  }
  v27 = v8;
  TlmLogApiReliability(10, 0, a1, (_DWORD)v2, (__int64)v4, UnbiasedTime, (__int64)v26, SyncRootInfoByHandle);
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  v20 = -1;
  LOBYTE(v20) = v6;
  RtlSetThreadPlaceholderCompatibilityMode(v20);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x180007f30  push    rbp
0x180007f32  push    rbx
0x180007f33  push    rsi
0x180007f34  push    rdi
0x180007f35  push    r12
0x180007f37  push    r13
0x180007f39  push    r14
0x180007f3b  push    r15
0x180007f3d  lea     rbp, [rsp-3F8h]
0x180007f45  sub     rsp, 4F8h
0x180007f4c  mov     rax, cs:__security_cookie
0x180007f53  xor     rax, rsp
0x180007f56  mov     [rbp+430h+var_50], rax
0x180007f5d  mov     r13, rcx
0x180007f60  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007f64  lea     rcx, [rbp+430h+var_460]; void *
0x180007f68  mov     [rsp+530h+hFile], rdi
0x180007f6d  xor     edx, edx; Val
0x180007f6f  mov     r8d, 404h; Size
0x180007f75  call    memset_0
0x180007f7a  xor     esi, esi
0x180007f7c  mov     cl, 2
0x180007f7e  mov     [rsp+530h+UnbiasedTime], rsi
0x180007f83  xor     r14d, r14d
0x180007f86  mov     [rsp+530h+FileInformation], rsi
0x180007f8b  xor     r15d, r15d
0x180007f8e  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x180007f95  nop     dword ptr [rax+rax+00h]
0x180007f9a  xor     edx, edx; Val
0x180007f9c  lea     r8d, [rdi+59h]; Size
0x180007fa0  lea     rcx, [rsp+530h+var_4C0]; void *
0x180007fa5  mov     [rsp+530h+var_4E0], al
0x180007fa9  mov     r12b, al
0x180007fac  call    memset_0
0x180007fb1  lea     rcx, [rsp+530h+UnbiasedTime]; UnbiasedTime
0x180007fb6  call    cs:__imp_QueryUnbiasedInterruptTime
0x180007fbd  nop     dword ptr [rax+rax+00h]
0x180007fc2  mov     rcx, r13
0x180007fc5  neg     rcx
0x180007fc8  sbb     ebx, ebx
0x180007fca  not     ebx
0x180007fcc  and     ebx, 57h
0x180007fcf  mov     ecx, ebx
0x180007fd1  or      ecx, 80070000h
0x180007fd7  test    r13, r13
0x180007fda  cmovz   ebx, ecx
0x180007fdd  cmp     ebx, edi
0x180007fdf  jg      short loc_180007FED
0x180007fe1  lea     rdi, aSyncrootpathCa; "SyncRootPath can't be NULL"
0x180007fe8  jmp     loc_180008203
0x180007fed  xor     ecx, ecx
0x180007fef  call    GlobalPortInit
0x180007ff4  mov     ebx, eax
0x180007ff6  cmp     eax, edi
0x180007ff8  jg      short loc_180008006
0x180007ffa  lea     rdi, aGlobalportinit; "GlobalPortInit Failed"
0x180008001  jmp     loc_180008203
0x180008006  mov     r9d, 7
0x18000800c  lea     rax, [rsp+530h+hFile]
0x180008011  mov     [rsp+530h+var_4F8], rax
0x180008016  mov     rcx, r13
0x180008019  mov     dword ptr [rsp+530h+FileHandle], 200021h; FileHandle
0x180008021  lea     r8d, [r9+7Ah]
0x180008025  call    CfpCreateFile
0x18000802a  mov     ecx, eax; Status
0x18000802c  call    cs:__imp_RtlNtStatusToDosError
0x180008033  nop     dword ptr [rax+rax+00h]
0x180008038  mov     ebx, eax
0x18000803a  test    eax, eax
0x18000803c  jle     short loc_180008047
0x18000803e  movzx   ebx, ax
0x180008041  or      ebx, 80070000h
0x180008047  cmp     ebx, edi
0x180008049  jg      short loc_180008057
0x18000804b  lea     rdi, aCfpcreatefileF; "CfpCreateFile Failed"
0x180008052  jmp     loc_180008203
0x180008057  mov     rcx, [rsp+530h+hFile]; hFile
0x18000805c  lea     r8, [rbp+430h+var_460]
0x180008060  mov     r9d, 404h
0x180008066  mov     [rsp+530h+var_510], rsi; __int64
0x18000806b  mov     edx, 2
0x180008070  call    CfpGetSyncRootInfoByHandle
0x180008075  xor     ecx, ecx
0x180008077  lea     r14, [rbp+430h+var_25C]
0x18000807e  test    eax, eax
0x180008080  lea     rsi, [rbp+430h+var_45C]
0x180008084  cmovs   r14, rcx
0x180008088  cmovs   rsi, rcx
0x18000808c  xor     r12d, r12d
0x18000808f  test    r15, r15
0x180008092  jnz     short loc_18000809B
0x180008094  mov     edi, 420h
0x180008099  jmp     short loc_1800080C8
0x18000809b  mov     edi, [r15+41Ch]
0x1800080a2  add     edi, 420h
0x1800080a8  call    cs:__imp_GetProcessHeap
0x1800080af  nop     dword ptr [rax+rax+00h]
0x1800080b4  mov     r8, r15; lpMem
0x1800080b7  xor     edx, edx; dwFlags
0x1800080b9  mov     rcx, rax; hHeap
0x1800080bc  call    cs:__imp_HeapFree
0x1800080c3  nop     dword ptr [rax+rax+00h]
0x1800080c8  call    cs:__imp_GetProcessHeap
0x1800080cf  nop     dword ptr [rax+rax+00h]
0x1800080d4  mov     r8d, edi; dwBytes
0x1800080d7  xor     edx, edx; dwFlags
0x1800080d9  mov     rcx, rax; hHeap
0x1800080dc  call    cs:__imp_HeapAlloc
0x1800080e3  nop     dword ptr [rax+rax+00h]
0x1800080e8  mov     r15, rax
0x1800080eb  neg     rax
0x1800080ee  sbb     ebx, ebx
0x1800080f0  not     ebx
0x1800080f2  and     ebx, 8
0x1800080f5  mov     eax, ebx
0x1800080f7  or      eax, 80070000h
0x1800080fc  test    r15, r15
0x1800080ff  cmovz   ebx, eax
0x180008102  test    ebx, ebx
0x180008104  jz      short loc_180008108
0x180008106  js      short loc_18000813E
0x180008108  mov     rcx, [rsp+530h+hFile]; hFile
0x18000810d  mov     r9d, edi
0x180008110  mov     r8, r15
0x180008113  mov     [rsp+530h+var_510], 0; __int64
0x18000811c  mov     edx, 1
0x180008121  call    CfpGetSyncRootInfoByHandle
0x180008126  mov     ebx, eax
0x180008128  cmp     eax, 800700EAh
0x18000812d  jnz     short loc_18000814A
0x18000812f  inc     r12d
0x180008132  cmp     r12d, 2
0x180008136  jl      loc_18000808F
0x18000813c  jmp     short loc_18000814F
0x18000813e  lea     rdi, aAllocatingMemo; "Allocating Memory for syncRootStdInfo F"...
0x180008145  jmp     loc_1800081FE
0x18000814a  cmp     ebx, 0FFFFFFFFh
0x18000814d  jg      short loc_18000815B
0x18000814f  lea     rdi, aCfpgetsyncroot; "CfpGetSyncRootInfoByHandle Failed"
0x180008156  jmp     loc_1800081FE
0x18000815b  mov     ecx, [r15+18h]
0x18000815f  test    ecx, ecx
0x180008161  jz      short loc_18000817A
0x180008163  lea     eax, [rcx+3FFFFFFFh]
0x180008169  cmp     eax, 1
0x18000816c  jbe     short loc_18000817A
0x18000816e  test    cl, 40h
0x180008171  jnz     short loc_18000817A
0x180008173  mov     ebx, 8007017Ch
0x180008178  jmp     short loc_180008180
0x18000817a  test    ebx, ebx
0x18000817c  jz      short loc_180008189
0x18000817e  jns     short loc_180008189
0x180008180  lea     rdi, aCanTUnregister; "Can't unregister when a provider is Con"...
0x180008187  jmp     short loc_1800081FE
0x180008189  mov     rcx, [rsp+530h+hFile]; hFile
0x18000818e  lea     r8, [rsp+530h+FileInformation]; lpFileInformation
0x180008193  mov     r9d, 8; dwBufferSize
0x180008199  lea     edx, [r9+1]; FileInformationClass
0x18000819d  call    cs:__imp_GetFileInformationByHandleEx
0x1800081a4  nop     dword ptr [rax+rax+00h]
0x1800081a9  test    eax, eax
0x1800081ab  jz      short loc_1800081B1
0x1800081ad  xor     ebx, ebx
0x1800081af  jmp     short loc_1800081CC
0x1800081b1  call    cs:__imp_GetLastError
0x1800081b8  nop     dword ptr [rax+rax+00h]
0x1800081bd  mov     ebx, eax
0x1800081bf  test    eax, eax
0x1800081c1  jle     short loc_1800081CC
0x1800081c3  movzx   ebx, ax
0x1800081c6  or      ebx, 80070000h
0x1800081cc  cmp     ebx, 0FFFFFFFFh
0x1800081cf  jg      short loc_1800081DA
0x1800081d1  lea     rdi, aGetfileinforma; "GetFileInformationByHandleEx Failed"
0x1800081d8  jmp     short loc_1800081FE
0x1800081da  mov     r9d, dword ptr [rsp+530h+FileInformation+4]; int
0x1800081df  xor     edi, edi
0x1800081e1  mov     r8d, dword ptr [rsp+530h+FileInformation]; int
0x1800081e6  mov     rcx, [rsp+530h+hFile]; int
0x1800081eb  mov     dword ptr [rsp+530h+var_510], edi; int
0x1800081ef  call    CfpRecurseDirectory
0x1800081f4  mov     rcx, [rsp+530h+hFile]; hFile
0x1800081f9  call    RevertSyncRoot
0x1800081fe  mov     r12b, [rsp+530h+var_4E0]
0x180008203  mov     dword ptr [rsp+530h+var_4F8], ebx
0x180008207  lea     rax, [rsp+530h+var_4C0]
0x18000820c  mov     [rsp+530h+var_500], rax
0x180008211  mov     ecx, 0Ah
0x180008216  mov     rax, [rsp+530h+UnbiasedTime]
0x18000821b  mov     r9, rsi
0x18000821e  mov     [rsp+530h+FileHandle], rax
0x180008223  mov     r8, r13
0x180008226  xor     edx, edx
0x180008228  mov     [rsp+530h+var_510], r14
0x18000822d  mov     [rsp+530h+var_4B8], rdi
0x180008232  call    TlmLogApiReliability
0x180008237  test    r15, r15
0x18000823a  jz      short loc_18000825C
0x18000823c  call    cs:__imp_GetProcessHeap
0x180008243  nop     dword ptr [rax+rax+00h]
0x180008248  mov     r8, r15; lpMem
0x18000824b  xor     edx, edx; dwFlags
0x18000824d  mov     rcx, rax; hHeap
0x180008250  call    cs:__imp_HeapFree
0x180008257  nop     dword ptr [rax+rax+00h]
0x18000825c  mov     rcx, [rsp+530h+hFile]; hObject
0x180008261  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008265  jz      short loc_180008273
0x180008267  call    cs:__imp_CloseHandle
0x18000826e  nop     dword ptr [rax+rax+00h]
0x180008273  mov     cl, r12b
0x180008276  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x18000827d  nop     dword ptr [rax+rax+00h]
0x180008282  mov     eax, ebx
0x180008284  mov     rcx, [rbp+430h+var_50]
0x18000828b  xor     rcx, rsp; StackCookie
0x18000828e  call    __security_check_cookie
0x180008293  add     rsp, 4F8h
0x18000829a  pop     r15
0x18000829c  pop     r14
0x18000829e  pop     r13
0x1800082a0  pop     r12
0x1800082a2  pop     rdi
0x1800082a3  pop     rsi
0x1800082a4  pop     rbx
0x1800082a5  pop     rbp
0x1800082a6  retn
```
