# MprConfigInterfaceSetInfo

- ea: `0x180024f80`
- end: `0x18002517a`
- name: `MprConfigInterfaceSetInfo`
- size: `506`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwLevel, LPBYTE lpbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180024f80`
- `0x180027d5c`
- `0x18002ecc4`
- `0x180051112`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024fcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025111`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025111`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025130`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800250b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800250b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002511f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002513e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002511f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002513e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025034`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025100`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025034`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025100`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002507f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002507f`

## pseudocode

```c
DWORD __stdcall MprConfigInterfaceSetInfo(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwLevel, LPBYTE lpbBuffer)
{
  DWORD result; // eax
  LPBYTE v8; // rsi
  DWORD v9; // ebx
  __int64 v10; // rcx
  void *v11; // rsi
  LSTATUS v12; // eax
  unsigned int SizeOfMultiSz; // eax
  size_t cbData; // r14
  HANDLE v15; // rax
  void *v16; // rax
  HANDLE ProcessHeap; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  LSTATUS v20; // [rsp+68h] [rbp+20h] BYREF

  if ( lpbBuffer && dwLevel <= 1 && hRouterInterface )
  {
    result = MprConfigServerValidateCb(hMprConfig);
    if ( result )
      return result;
    EnterCriticalSection(&CfgLock);
    if ( *((_DWORD *)hRouterInterface + 14) )
    {
      LeaveCriticalSection(&CfgLock);
      return 905;
    }
    if ( dwLevel <= 1 )
    {
      v8 = lpbBuffer + 528;
      if ( (unsigned int)(*((_DWORD *)lpbBuffer + 133) - 3) <= 1 && !*(_DWORD *)v8 )
        goto LABEL_27;
      v20 = RegSetValueExW(*((HKEY *)hRouterInterface + 5), L"Enabled", 0, 4u, lpbBuffer + 528, 4u);
      v9 = v20;
      if ( v20 )
        goto LABEL_26;
      *((_DWORD *)hRouterInterface + 7) = *(_DWORD *)v8;
      if ( dwLevel == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)hRouterInterface + 6) - 3) > 1 )
        {
          v10 = *((_QWORD *)lpbBuffer + 69);
          if ( !v10 )
          {
            v11 = 0;
            v12 = RegDeleteValueW(*((HKEY *)hRouterInterface + 5), L"DialoutHours");
LABEL_19:
            v9 = v12;
            if ( v12 )
            {
              if ( v11 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v11);
              }
              goto LABEL_26;
            }
            v18 = (void *)*((_QWORD *)hRouterInterface + 4);
            if ( v18 )
            {
              v19 = GetProcessHeap();
              HeapFree(v19, 0, v18);
            }
            *((_QWORD *)hRouterInterface + 4) = v11;
            goto LABEL_25;
          }
          SizeOfMultiSz = MprUtilGetSizeOfMultiSz(v10, 2000, &v20);
          v9 = v20;
          cbData = SizeOfMultiSz;
          if ( !v20 )
          {
            v15 = GetProcessHeap();
            v16 = HeapAlloc(v15, 0, (unsigned int)cbData);
            v11 = v16;
            if ( v16 )
            {
              memcpy_0(v16, *((const void **)lpbBuffer + 69), cbData);
              v12 = RegSetValueExW(
                      *((HKEY *)hRouterInterface + 5),
                      L"DialoutHours",
                      0,
                      7u,
                      *((const BYTE **)lpbBuffer + 69),
                      cbData);
              goto LABEL_19;
            }
            v9 = 8;
          }
LABEL_26:
          LeaveCriticalSection(&CfgLock);
          return v9;
        }
LABEL_27:
        v9 = 87;
        goto LABEL_26;
      }
    }
LABEL_25:
    v9 = 0;
    goto LABEL_26;
  }
  return 87;
}

```

## disassembly

```asm
0x180024f80  mov     [rsp+arg_0], rbx
0x180024f85  mov     [rsp+arg_8], rbp
0x180024f8a  push    rsi
0x180024f8b  push    rdi
0x180024f8c  push    r14
0x180024f8e  sub     rsp, 30h
0x180024f92  mov     rbp, r9
0x180024f95  mov     r14d, r8d
0x180024f98  mov     rdi, rdx
0x180024f9b  test    r9, r9
0x180024f9e  jz      loc_180025162
0x180024fa4  cmp     r8d, 1
0x180024fa8  ja      loc_180025162
0x180024fae  test    rdx, rdx
0x180024fb1  jz      loc_180025162
0x180024fb7  call    MprConfigServerValidateCb
0x180024fbc  test    eax, eax
0x180024fbe  jnz     loc_180025167
0x180024fc4  lea     rcx, CfgLock; lpCriticalSection
0x180024fcb  call    cs:__imp_EnterCriticalSection
0x180024fd1  cmp     dword ptr [rdi+38h], 0
0x180024fd5  jz      short loc_180024FEE
0x180024fd7  lea     rcx, CfgLock; lpCriticalSection
0x180024fde  call    cs:__imp_LeaveCriticalSection
0x180024fe4  mov     eax, 389h
0x180024fe9  jmp     loc_180025167
0x180024fee  cmp     r14d, 1
0x180024ff2  ja      loc_180025148
0x180024ff8  mov     eax, [rbp+214h]
0x180024ffe  lea     rsi, [rbp+210h]
0x180025005  sub     eax, 3
0x180025008  cmp     eax, 1
0x18002500b  ja      short loc_180025016
0x18002500d  cmp     dword ptr [rsi], 0
0x180025010  jz      loc_18002515B
0x180025016  mov     rcx, [rdi+28h]; hKey
0x18002501a  lea     rdx, c_szEnabled; "Enabled"
0x180025021  mov     r9d, 4; dwType
0x180025027  xor     r8d, r8d; Reserved
0x18002502a  mov     [rsp+48h+cbData], r9d; cbData
0x18002502f  mov     [rsp+48h+lpData], rsi; lpData
0x180025034  call    cs:__imp_RegSetValueExW
0x18002503a  mov     [rsp+48h+arg_18], eax
0x18002503e  mov     ebx, eax
0x180025040  test    eax, eax
0x180025042  jnz     loc_18002514A
0x180025048  mov     eax, [rsi]
0x18002504a  mov     [rdi+1Ch], eax
0x18002504d  cmp     r14d, 1
0x180025051  jnz     loc_180025148
0x180025057  mov     eax, [rdi+18h]
0x18002505a  sub     eax, 3
0x18002505d  cmp     eax, r14d
0x180025060  jbe     loc_18002515B
0x180025066  mov     rcx, [rbp+228h]
0x18002506d  test    rcx, rcx
0x180025070  jnz     short loc_180025087
0x180025072  mov     rcx, [rdi+28h]; hKey
0x180025076  lea     rdx, c_szDialoutHours; "DialoutHours"
0x18002507d  xor     esi, esi
0x18002507f  call    cs:__imp_RegDeleteValueW
0x180025085  jmp     short loc_180025106
0x180025087  lea     r8, [rsp+48h+arg_18]
0x18002508c  mov     edx, 7D0h
0x180025091  call    MprUtilGetSizeOfMultiSz
0x180025096  mov     ebx, [rsp+48h+arg_18]
0x18002509a  mov     r14d, eax
0x18002509d  test    ebx, ebx
0x18002509f  jnz     loc_18002514A
0x1800250a5  call    cs:__imp_GetProcessHeap
0x1800250ab  mov     r8d, r14d; dwBytes
0x1800250ae  xor     edx, edx; dwFlags
0x1800250b0  mov     rcx, rax; hHeap
0x1800250b3  call    cs:__imp_HeapAlloc
0x1800250b9  mov     rsi, rax
0x1800250bc  test    rax, rax
0x1800250bf  jnz     short loc_1800250C9
0x1800250c1  lea     ebx, [rax+8]
0x1800250c4  jmp     loc_18002514A
0x1800250c9  mov     rdx, [rbp+228h]; Src
0x1800250d0  mov     r8, r14; Size
0x1800250d3  mov     rcx, rax; void *
0x1800250d6  call    memcpy_0
0x1800250db  mov     rax, [rbp+228h]
0x1800250e2  lea     rdx, c_szDialoutHours; "DialoutHours"
0x1800250e9  mov     rcx, [rdi+28h]; hKey
0x1800250ed  mov     r9d, 7; dwType
0x1800250f3  mov     [rsp+48h+cbData], r14d; cbData
0x1800250f8  xor     r8d, r8d; Reserved
0x1800250fb  mov     [rsp+48h+lpData], rax; lpData
0x180025100  call    cs:__imp_RegSetValueExW
0x180025106  mov     ebx, eax
0x180025108  test    eax, eax
0x18002510a  jz      short loc_180025127
0x18002510c  test    rsi, rsi
0x18002510f  jz      short loc_18002514A
0x180025111  call    cs:__imp_GetProcessHeap
0x180025117  mov     r8, rsi; lpMem
0x18002511a  xor     edx, edx; dwFlags
0x18002511c  mov     rcx, rax; hHeap
0x18002511f  call    cs:__imp_HeapFree
0x180025125  jmp     short loc_18002514A
0x180025127  mov     rbx, [rdi+20h]
0x18002512b  test    rbx, rbx
0x18002512e  jz      short loc_180025144
0x180025130  call    cs:__imp_GetProcessHeap
0x180025136  mov     r8, rbx; lpMem
0x180025139  xor     edx, edx; dwFlags
0x18002513b  mov     rcx, rax; hHeap
0x18002513e  call    cs:__imp_HeapFree
0x180025144  mov     [rdi+20h], rsi
0x180025148  xor     ebx, ebx
0x18002514a  lea     rcx, CfgLock; lpCriticalSection
0x180025151  call    cs:__imp_LeaveCriticalSection
0x180025157  mov     eax, ebx
0x180025159  jmp     short loc_180025167
0x18002515b  mov     ebx, 57h ; 'W'
0x180025160  jmp     short loc_18002514A
0x180025162  mov     eax, 57h ; 'W'
0x180025167  mov     rbx, [rsp+48h+arg_0]
0x18002516c  mov     rbp, [rsp+48h+arg_8]
0x180025171  add     rsp, 30h
0x180025175  pop     r14
0x180025177  pop     rdi
0x180025178  pop     rsi
0x180025179  retn
```
