# MprConfigServerConnect

- ea: `0x1800265c0`
- end: `0x1800267e2`
- name: `MprConfigServerConnect`
- size: `546`
- prototype: `DWORD __stdcall(LPWSTR lpwsServerName, HANDLE *phMprConfig)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036c94`

## callees

- `0x18000a704`
- `0x18001833c`
- `0x1800265c0`
- `0x1800267f0`
- `0x180032b64`
- `0x180032c60`
- `0x180032d10`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026651`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800266ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800266ba`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180026739`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180026739`
- `rtutils!TraceRegisterExW` at `0x1800265f9`
- `rtutils!TraceRegisterExW` at `0x1800265f9`

## pseudocode

```c
DWORD __stdcall MprConfigServerConnect(LPWSTR lpwsServerName, HANDLE *phMprConfig)
{
  _DWORD *v4; // rbx
  DWORD result; // eax
  __int64 v6; // rdx
  DWORD v7; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  int v10; // r9d
  _DWORD *v11; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v11 = 0;
  if ( g_dwTraceHandle == -1 )
    g_dwTraceHandle = TraceRegisterExW(L"MPRAPI", 0);
  if ( !phMprConfig )
    return 87;
  *phMprConfig = 0;
  if ( lpwsServerName )
  {
    v6 = -1;
    do
      ++v6;
    while ( lpwsServerName[v6] );
  }
  result = FormatServerNameForMprCfgApis(lpwsServerName);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( g_htabServers )
    {
      v7 = HashTabFind(g_htabServers, 0, &v11);
      v4 = v11;
    }
    else
    {
      v7 = 1168;
    }
    if ( !v7 )
    {
      ++v4[34];
LABEL_28:
      *phMprConfig = v4;
      goto LABEL_29;
    }
    if ( v7 == 1168 )
    {
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, 0xD8u);
      v4 = v9;
      if ( !v9 )
      {
        v7 = 8;
        goto LABEL_30;
      }
      memset_0(v9, 0, 0xD8u);
      *((_QWORD *)v4 + 11) = v4 + 20;
      *((_QWORD *)v4 + 10) = v4 + 20;
      *((_QWORD *)v4 + 14) = v4 + 26;
      *((_QWORD *)v4 + 13) = v4 + 26;
      *((_QWORD *)v4 + 1) = 0;
      v4[34] = 1;
      *v4 = 53195;
      v7 = GuidMapInit(0, v4 + 32);
      if ( !v7 )
      {
        if ( lpwsServerName && *lpwsServerName )
        {
          v7 = RegConnectRegistryW(lpwsServerName, HKEY_LOCAL_MACHINE, (PHKEY)v4 + 2);
          if ( v7 )
            goto LABEL_29;
        }
        else
        {
          *((_QWORD *)v4 + 2) = -2147483646;
        }
        if ( g_htabServers
          || (v7 = HashTabCreate(13, (unsigned int)ServerCbHash, (unsigned int)ServerCbCompare, v10)) == 0 )
        {
          v7 = HashTabInsert(g_htabServers, *((_QWORD *)v4 + 1), v4);
        }
        if ( v7 )
          goto LABEL_30;
        v7 = 0;
        goto LABEL_28;
      }
    }
LABEL_29:
    if ( !v7 )
    {
LABEL_32:
      LeaveCriticalSection(&CfgLock);
      return v7;
    }
LABEL_30:
    if ( v4 )
      MprConfigServerDisconnect(v4);
    goto LABEL_32;
  }
  return result;
}

```

## disassembly

```asm
0x1800265c0  mov     rax, rsp
0x1800265c3  mov     [rax+8], rbx
0x1800265c7  push    rsi
0x1800265c8  push    rdi
0x1800265c9  push    r12
0x1800265cb  push    r14
0x1800265cd  push    r15
0x1800265cf  sub     rsp, 50h
0x1800265d3  mov     r14, rdx
0x1800265d6  mov     rsi, rcx
0x1800265d9  xor     r12d, r12d
0x1800265dc  mov     ebx, r12d
0x1800265df  mov     [rax+18h], rbx
0x1800265e3  mov     [rax+10h], r12
0x1800265e7  cmp     cs:g_dwTraceHandle, 0FFFFFFFFh
0x1800265ee  jnz     short loc_180026605
0x1800265f0  xor     edx, edx; dwFlags
0x1800265f2  lea     rcx, aMprapi; "MPRAPI"
0x1800265f9  call    cs:__imp_TraceRegisterExW
0x1800265ff  mov     cs:g_dwTraceHandle, eax
0x180026605  test    r14, r14
0x180026608  jnz     short loc_180026613
0x18002660a  lea     eax, [r14+57h]
0x18002660e  jmp     loc_1800267CD
0x180026613  mov     [r14], r12
0x180026616  test    rsi, rsi
0x180026619  jnz     short loc_180026620
0x18002661b  mov     edx, r12d
0x18002661e  jmp     short loc_180026632
0x180026620  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026624  inc     rdx
0x180026627  cmp     [rsi+rdx*2], r12w
0x18002662c  jnz     short loc_180026624
0x18002662e  mov     [rsp+78h+var_38], edx
0x180026632  lea     r8, [rsp+78h+arg_8]
0x18002663a  mov     rcx, rsi; lpString1
0x18002663d  call    FormatServerNameForMprCfgApis
0x180026642  test    eax, eax
0x180026644  jnz     loc_1800267CD
0x18002664a  lea     rcx, CfgLock; lpCriticalSection
0x180026651  call    cs:__imp_EnterCriticalSection
0x180026657  mov     rcx, cs:g_htabServers
0x18002665e  mov     r15, [rsp+78h+arg_8]
0x180026666  test    rcx, rcx
0x180026669  jnz     short loc_180026672
0x18002666b  mov     edi, 490h
0x180026670  jmp     short loc_18002668C
0x180026672  lea     r8, [rsp+78h+arg_10]
0x18002667a  mov     rdx, r15
0x18002667d  call    HashTabFind
0x180026682  mov     edi, eax
0x180026684  mov     rbx, [rsp+78h+arg_10]
0x18002668c  test    edi, edi
0x18002668e  jnz     short loc_18002669B
0x180026690  inc     dword ptr [rbx+88h]
0x180026696  jmp     loc_1800267A3
0x18002669b  cmp     edi, 490h
0x1800266a1  jnz     loc_1800267A6
0x1800266a7  call    cs:__imp_GetProcessHeap
0x1800266ad  mov     rcx, rax; hHeap
0x1800266b0  mov     edi, 0D8h
0x1800266b5  mov     r8d, edi; dwBytes
0x1800266b8  xor     edx, edx; dwFlags
0x1800266ba  call    cs:__imp_HeapAlloc
0x1800266c0  mov     rbx, rax
0x1800266c3  test    rax, rax
0x1800266c6  jnz     short loc_1800266D0
0x1800266c8  lea     edi, [rax+8]
0x1800266cb  jmp     loc_1800267AA
0x1800266d0  mov     r8, rdi; Size
0x1800266d3  xor     edx, edx; Val
0x1800266d5  mov     rcx, rbx; void *
0x1800266d8  call    memset_0
0x1800266dd  lea     rax, [rbx+50h]
0x1800266e1  mov     [rax+8], rax
0x1800266e5  mov     [rax], rax
0x1800266e8  lea     rax, [rbx+68h]
0x1800266ec  mov     [rax+8], rax
0x1800266f0  mov     [rax], rax
0x1800266f3  mov     [rbx+8], r15
0x1800266f7  mov     dword ptr [rbx+88h], 1
0x180026701  mov     dword ptr [rbx], 0CFCBh
0x180026707  lea     rdx, [rbx+80h]
0x18002670e  mov     rcx, r15
0x180026711  call    GuidMapInit
0x180026716  mov     edi, eax
0x180026718  test    eax, eax
0x18002671a  jnz     loc_1800267A6
0x180026720  test    rsi, rsi
0x180026723  jz      short loc_180026747
0x180026725  cmp     [rsi], r12w
0x180026729  jz      short loc_180026747
0x18002672b  lea     r8, [rbx+10h]; phkResult
0x18002672f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180026736  mov     rcx, rsi; lpMachineName
0x180026739  call    cs:__imp_RegConnectRegistryW
0x18002673f  mov     edi, eax
0x180026741  test    eax, eax
0x180026743  jz      short loc_18002674F
0x180026745  jmp     short loc_1800267A6
0x180026747  mov     qword ptr [rbx+10h], 0FFFFFFFF80000002h
0x18002674f  cmp     cs:g_htabServers, r12
0x180026756  jnz     short loc_180026787
0x180026758  lea     rax, g_htabServers
0x18002675f  mov     [rsp+78h+var_48], rax
0x180026764  mov     [rsp+78h+var_50], r12
0x180026769  lea     r8, ServerCbCompare
0x180026770  lea     rdx, ServerCbHash
0x180026777  mov     ecx, 0Dh
0x18002677c  call    HashTabCreate
0x180026781  mov     edi, eax
0x180026783  test    eax, eax
0x180026785  jnz     short loc_18002679C
0x180026787  mov     r8, rbx
0x18002678a  mov     rdx, [rbx+8]
0x18002678e  mov     rcx, cs:g_htabServers
0x180026795  call    HashTabInsert
0x18002679a  mov     edi, eax
0x18002679c  test    edi, edi
0x18002679e  jnz     short loc_1800267AA
0x1800267a0  mov     edi, r12d
0x1800267a3  mov     [r14], rbx
0x1800267a6  test    edi, edi
0x1800267a8  jz      short loc_1800267B7
0x1800267aa  test    rbx, rbx
0x1800267ad  jz      short loc_1800267B7
0x1800267af  mov     rcx, rbx; hMprConfig
0x1800267b2  call    MprConfigServerDisconnect
0x1800267b7  lea     rcx, CfgLock; lpCriticalSection
0x1800267be  call    cs:__imp_LeaveCriticalSection
0x1800267c4  mov     eax, edi
0x1800267c6  jmp     short loc_1800267CD
0x1800267c8  mov     eax, 57h ; 'W'
0x1800267cd  mov     rbx, [rsp+78h+arg_0]
0x1800267d5  add     rsp, 50h
0x1800267d9  pop     r15
0x1800267db  pop     r14
0x1800267dd  pop     r12
0x1800267df  pop     rdi
0x1800267e0  pop     rsi
0x1800267e1  retn
```
