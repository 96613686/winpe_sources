# InitializeDHCPClientForiSNS

- ea: `0x18001b834`
- end: `0x18001bb21`
- name: `InitializeDHCPClientForiSNS`
- size: `749`
- prototype: `DWORD __fastcall(HANDLE **, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009408`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x18001b4c0`
- `0x18001b834`
- `0x18001bb28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b900`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b996`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b9c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b9df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ba69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001baaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001babd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b900`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b996`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b9c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b9df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ba69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001baaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001babd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b8a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b953`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b9b7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ba07`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b8a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b953`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b9b7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ba07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba5c`
- `WS2_32!__imp_WSAStartup` at `0x18001b91b`
- `WS2_32!__imp_WSAStartup` at `0x18001b91b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b92b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b92b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba9e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001b8ee`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001b8ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ba3e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ba3e`
- `IPHLPAPI!GetAdaptersInfo` at `0x18001b940`
- `IPHLPAPI!GetAdaptersInfo` at `0x18001b96d`
- `IPHLPAPI!GetAdaptersInfo` at `0x18001b940`
- `IPHLPAPI!GetAdaptersInfo` at `0x18001b96d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001ba8a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001ba8a`

## pseudocode

```c
DWORD __fastcall InitializeDHCPClientForiSNS(HANDLE **a1, _DWORD *a2)
{
  HANDLE **v3; // r14
  HANDLE *v5; // rax
  HANDLE *v6; // rbx
  HANDLE MutexA; // rax
  ULONG AdaptersInfo; // edi
  struct _IP_ADAPTER_INFO *v9; // rax
  struct _IP_ADAPTER_INFO *v10; // rsi
  DWORD v11; // r14d
  struct _IP_ADAPTER_INFO *v12; // rax
  HANDLE *v13; // rax
  HANDLE *v14; // r15
  DWORD v15; // ebp
  struct _IP_ADAPTER_INFO *v16; // r13
  _QWORD *v17; // rax
  HANDLE v18; // rax
  DWORD i; // r14d
  HANDLE *v20; // rax
  int v21; // ecx
  ULONG SizePointer; // [rsp+30h] [rbp-208h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-204h] BYREF
  void *Block; // [rsp+38h] [rbp-200h]
  HANDLE **v25; // [rsp+40h] [rbp-1F8h]
  WSAData WSAData; // [rsp+50h] [rbp-1E8h] BYREF

  v25 = a1;
  v3 = a1;
  SizePointer = 0;
  ThreadId = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !v3 )
    return 87;
  *v3 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = (HANDLE *)malloc(0x20u);
  v6 = v5;
  if ( !v5 )
    return 8;
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  *((_DWORD *)v5 + 6) = 2;
  *((_DWORD *)v5 + 7) = 1000;
  ReadRegistryParameters();
  v6[1] = v6;
  *v6 = v6;
  MutexA = CreateMutexA(0, 0, 0);
  v6[2] = MutexA;
  if ( !MutexA )
  {
    free(v6);
    return GetLastError();
  }
  AdaptersInfo = WSAStartup(0x202u, &WSAData);
  if ( !AdaptersInfo )
  {
    AdaptersInfo = 0;
    if ( GetAdaptersInfo(0, &SizePointer) == 111 )
    {
      v9 = (struct _IP_ADAPTER_INFO *)malloc(SizePointer);
      v10 = v9;
      if ( v9 )
      {
        AdaptersInfo = GetAdaptersInfo(v9, &SizePointer);
        if ( !AdaptersInfo )
        {
          v11 = 0;
          v12 = v10;
          do
          {
            v12 = v12->Next;
            ++v11;
          }
          while ( v12 );
          if ( !v11 )
          {
            free(v10);
            CloseHandle(v6[2]);
            AdaptersInfo = 232;
            goto LABEL_20;
          }
          v13 = (HANDLE *)malloc(8LL * v11);
          v14 = v13;
          if ( !v13 )
          {
            free(v10);
            CloseHandle(v6[2]);
            AdaptersInfo = 8;
            goto LABEL_20;
          }
          memset_0(v13, 0, 8LL * v11);
          v15 = 0;
          v16 = v10;
          while ( v15 < v11 )
          {
            v17 = malloc(0x10u);
            Block = v17;
            if ( !v17 )
            {
              AdaptersInfo = 8;
              break;
            }
            *v17 = v6;
            v17[1] = v16;
            v18 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FindDHCPServersThreadRoutine, v17, 0, &ThreadId);
            v14[v15] = v18;
            if ( !v18 )
            {
              AdaptersInfo = GetLastError();
              free(Block);
              break;
            }
            v16 = v16->Next;
            ++v15;
            if ( !v16 )
              break;
          }
          if ( v15 )
          {
            WaitForMultipleObjects(v15, v14, 1, 0xFFFFFFFF);
            for ( i = 0; i < v15; ++i )
              CloseHandle(v14[i]);
          }
          free(v14);
          v3 = v25;
        }
        free(v10);
        if ( AdaptersInfo )
        {
          DeinitializeDHCPClientForiSNS(v6);
          return AdaptersInfo;
        }
      }
    }
    *v3 = v6;
    if ( a2 )
    {
      v20 = (HANDLE *)*v6;
      v21 = 0;
      while ( v20 && v20 != v6 )
      {
        v20 = (HANDLE *)*v20;
        ++v21;
      }
      *a2 = v21;
    }
    return AdaptersInfo;
  }
  CloseHandle(v6[2]);
LABEL_20:
  free(v6);
  return AdaptersInfo;
}

```

## disassembly

```asm
0x18001b834  mov     [rsp+arg_10], rbx
0x18001b839  push    rbp
0x18001b83a  push    rsi
0x18001b83b  push    rdi
0x18001b83c  push    r12
0x18001b83e  push    r13
0x18001b840  push    r14
0x18001b842  push    r15
0x18001b844  sub     rsp, 200h
0x18001b84b  mov     rax, cs:__security_cookie
0x18001b852  xor     rax, rsp
0x18001b855  mov     [rsp+238h+var_48], rax
0x18001b85d  mov     r12, rdx
0x18001b860  mov     [rsp+238h+var_1F8], rcx
0x18001b865  mov     r14, rcx
0x18001b868  xor     r13d, r13d
0x18001b86b  xor     edx, edx; Val
0x18001b86d  mov     [rsp+238h+SizePointer], r13d
0x18001b872  lea     rcx, [rsp+238h+WSAData]; void *
0x18001b877  mov     [rsp+238h+ThreadId], r13d
0x18001b87c  mov     r8d, 198h; Size
0x18001b882  call    memset_0
0x18001b887  test    r14, r14
0x18001b88a  jnz     short loc_18001B895
0x18001b88c  lea     eax, [r14+57h]
0x18001b890  jmp     loc_18001BAF6
0x18001b895  mov     [r14], r13
0x18001b898  test    r12, r12
0x18001b89b  jz      short loc_18001B8A1
0x18001b89d  mov     [r12], r13d
0x18001b8a1  mov     ecx, 20h ; ' '; Size
0x18001b8a6  call    cs:__imp_malloc
0x18001b8ac  mov     rbx, rax
0x18001b8af  test    rax, rax
0x18001b8b2  jnz     short loc_18001B8BC
0x18001b8b4  lea     eax, [rbx+8]
0x18001b8b7  jmp     loc_18001BAF6
0x18001b8bc  mov     [rax], r13
0x18001b8bf  lea     rcx, [rax+18h]
0x18001b8c3  mov     [rax+8], r13
0x18001b8c7  lea     rdx, [rax+1Ch]
0x18001b8cb  mov     [rax+10h], r13
0x18001b8cf  mov     dword ptr [rcx], 2
0x18001b8d5  mov     dword ptr [rdx], 3E8h
0x18001b8db  call    ReadRegistryParameters
0x18001b8e0  xor     r8d, r8d; lpName
0x18001b8e3  mov     [rbx+8], rbx
0x18001b8e7  xor     edx, edx; bInitialOwner
0x18001b8e9  mov     [rbx], rbx
0x18001b8ec  xor     ecx, ecx; lpMutexAttributes
0x18001b8ee  call    cs:__imp_CreateMutexA
0x18001b8f4  mov     [rbx+10h], rax
0x18001b8f8  test    rax, rax
0x18001b8fb  jnz     short loc_18001B911
0x18001b8fd  mov     rcx, rbx; Block
0x18001b900  call    cs:__imp_free
0x18001b906  call    cs:__imp_GetLastError
0x18001b90c  jmp     loc_18001BAF6
0x18001b911  mov     ecx, 202h; wVersionRequested
0x18001b916  lea     rdx, [rsp+238h+WSAData]; lpWSAData
0x18001b91b  call    cs:__imp_WSAStartup
0x18001b921  mov     edi, eax
0x18001b923  test    eax, eax
0x18001b925  jz      short loc_18001B936
0x18001b927  mov     rcx, [rbx+10h]; hObject
0x18001b92b  call    cs:__imp_CloseHandle
0x18001b931  jmp     loc_18001B9DC
0x18001b936  lea     rdx, [rsp+238h+SizePointer]; SizePointer
0x18001b93b  xor     ecx, ecx; AdapterInfo
0x18001b93d  mov     edi, r13d
0x18001b940  call    cs:__imp_GetAdaptersInfo
0x18001b946  cmp     eax, 6Fh ; 'o'
0x18001b949  jnz     loc_18001BAD1
0x18001b94f  mov     ecx, [rsp+238h+SizePointer]; Size
0x18001b953  call    cs:__imp_malloc
0x18001b959  mov     rsi, rax
0x18001b95c  test    rax, rax
0x18001b95f  jz      loc_18001BAD1
0x18001b965  lea     rdx, [rsp+238h+SizePointer]; SizePointer
0x18001b96a  mov     rcx, rax; AdapterInfo
0x18001b96d  call    cs:__imp_GetAdaptersInfo
0x18001b973  mov     edi, eax
0x18001b975  test    eax, eax
0x18001b977  jnz     loc_18001BABA
0x18001b97d  mov     r14d, r13d
0x18001b980  mov     rax, rsi
0x18001b983  mov     rax, [rax]
0x18001b986  inc     r14d
0x18001b989  test    rax, rax
0x18001b98c  jnz     short loc_18001B983
0x18001b98e  test    r14d, r14d
0x18001b991  jnz     short loc_18001B9AD
0x18001b993  mov     rcx, rsi; Block
0x18001b996  call    cs:__imp_free
0x18001b99c  mov     rcx, [rbx+10h]; hObject
0x18001b9a0  call    cs:__imp_CloseHandle
0x18001b9a6  mov     edi, 0E8h
0x18001b9ab  jmp     short loc_18001B9DC
0x18001b9ad  mov     ebp, r14d
0x18001b9b0  shl     rbp, 3
0x18001b9b4  mov     rcx, rbp; Size
0x18001b9b7  call    cs:__imp_malloc
0x18001b9bd  mov     r15, rax
0x18001b9c0  test    rax, rax
0x18001b9c3  jnz     short loc_18001B9EA
0x18001b9c5  mov     rcx, rsi; Block
0x18001b9c8  call    cs:__imp_free
0x18001b9ce  mov     rcx, [rbx+10h]; hObject
0x18001b9d2  call    cs:__imp_CloseHandle
0x18001b9d8  lea     edi, [r15+8]
0x18001b9dc  mov     rcx, rbx; Block
0x18001b9df  call    cs:__imp_free
0x18001b9e5  jmp     loc_18001BAF4
0x18001b9ea  mov     r8, rbp; Size
0x18001b9ed  xor     edx, edx; Val
0x18001b9ef  mov     rcx, r15; void *
0x18001b9f2  call    memset_0
0x18001b9f7  mov     ebp, r13d
0x18001b9fa  mov     r13, rsi
0x18001b9fd  cmp     ebp, r14d
0x18001ba00  jnb     short loc_18001BA76
0x18001ba02  mov     ecx, 10h; Size
0x18001ba07  call    cs:__imp_malloc
0x18001ba0d  mov     [rsp+238h+Block], rax
0x18001ba12  test    rax, rax
0x18001ba15  jz      short loc_18001BA71
0x18001ba17  lea     rcx, [rsp+238h+ThreadId]
0x18001ba1c  mov     [rax], rbx
0x18001ba1f  mov     [rsp+238h+lpThreadId], rcx; lpThreadId
0x18001ba24  lea     r8, FindDHCPServersThreadRoutine; lpStartAddress
0x18001ba2b  xor     ecx, ecx; lpThreadAttributes
0x18001ba2d  mov     [rax+8], r13
0x18001ba31  mov     r9, rax; lpParameter
0x18001ba34  mov     [rsp+238h+dwCreationFlags], 0; dwCreationFlags
0x18001ba3c  xor     edx, edx; dwStackSize
0x18001ba3e  call    cs:__imp_CreateThread
0x18001ba44  mov     ecx, ebp
0x18001ba46  mov     [r15+rcx*8], rax
0x18001ba4a  test    rax, rax
0x18001ba4d  jz      short loc_18001BA5C
0x18001ba4f  mov     r13, [r13+0]
0x18001ba53  inc     ebp
0x18001ba55  test    r13, r13
0x18001ba58  jnz     short loc_18001B9FD
0x18001ba5a  jmp     short loc_18001BA76
0x18001ba5c  call    cs:__imp_GetLastError
0x18001ba62  mov     rcx, [rsp+238h+Block]; Block
0x18001ba67  mov     edi, eax
0x18001ba69  call    cs:__imp_free
0x18001ba6f  jmp     short loc_18001BA76
0x18001ba71  mov     edi, 8
0x18001ba76  xor     r13d, r13d
0x18001ba79  test    ebp, ebp
0x18001ba7b  jz      short loc_18001BAAC
0x18001ba7d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001ba81  lea     r8d, [r13+1]; bWaitAll
0x18001ba85  mov     rdx, r15; lpHandles
0x18001ba88  mov     ecx, ebp; nCount
0x18001ba8a  call    cs:__imp_WaitForMultipleObjects
0x18001ba90  mov     r14d, r13d
0x18001ba93  test    ebp, ebp
0x18001ba95  jz      short loc_18001BAAC
0x18001ba97  mov     ecx, r14d
0x18001ba9a  mov     rcx, [r15+rcx*8]; hObject
0x18001ba9e  call    cs:__imp_CloseHandle
0x18001baa4  inc     r14d
0x18001baa7  cmp     r14d, ebp
0x18001baaa  jb      short loc_18001BA97
0x18001baac  mov     rcx, r15; Block
0x18001baaf  call    cs:__imp_free
0x18001bab5  mov     r14, [rsp+238h+var_1F8]
0x18001baba  mov     rcx, rsi; Block
0x18001babd  call    cs:__imp_free
0x18001bac3  test    edi, edi
0x18001bac5  jz      short loc_18001BAD1
0x18001bac7  mov     rcx, rbx; Block
0x18001baca  call    DeinitializeDHCPClientForiSNS
0x18001bacf  jmp     short loc_18001BAF4
0x18001bad1  mov     [r14], rbx
0x18001bad4  test    r12, r12
0x18001bad7  jz      short loc_18001BAF4
0x18001bad9  mov     rax, [rbx]
0x18001badc  mov     ecx, r13d
0x18001badf  jmp     short loc_18001BAEB
0x18001bae1  cmp     rax, rbx
0x18001bae4  jz      short loc_18001BAF0
0x18001bae6  mov     rax, [rax]
0x18001bae9  inc     ecx
0x18001baeb  test    rax, rax
0x18001baee  jnz     short loc_18001BAE1
0x18001baf0  mov     [r12], ecx
0x18001baf4  mov     eax, edi
0x18001baf6  mov     rcx, [rsp+238h+var_48]
0x18001bafe  xor     rcx, rsp; StackCookie
0x18001bb01  call    __security_check_cookie
0x18001bb06  mov     rbx, [rsp+238h+arg_10]
0x18001bb0e  add     rsp, 200h
0x18001bb15  pop     r15
0x18001bb17  pop     r14
0x18001bb19  pop     r13
0x18001bb1b  pop     r12
0x18001bb1d  pop     rdi
0x18001bb1e  pop     rsi
0x18001bb1f  pop     rbp
0x18001bb20  retn
```
