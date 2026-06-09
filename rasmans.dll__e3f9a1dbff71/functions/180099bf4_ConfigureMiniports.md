# ConfigureMiniports

- ea: `0x180099bf4`
- end: `0x180099d97`
- name: `ConfigureMiniports`
- size: `419`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, _QWORD **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800074c8`
- `0x18000aa60`
- `0x180099f60`

## callees

- `0x180099b88`
- `0x180099bf4`
- `0x180099f60`
- `0x18009a368`
- `0x18009a6f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099d82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c7a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180099c6c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180099c6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180099d79`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180099d79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099c88`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099c88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099cfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099cfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099cee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099cee`

## pseudocode

```c
__int64 __fastcall ConfigureMiniports(unsigned int a1, unsigned int a2, _QWORD **a3)
{
  signed int updated; // eax
  unsigned int v7; // edi
  HANDLE MutexW; // rax
  void *v9; // r15
  signed int v10; // eax
  _QWORD *v11; // rbx
  __int64 v12; // rbp
  _QWORD *v13; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v15; // r14d
  unsigned int i; // ecx
  unsigned int inited; // eax
  _QWORD *v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  v19 = 0;
  v20 = 0;
  if ( (a2 & 8) != 0 && (a2 & 0x10) != 0 || (a2 & 1) != 0 && (a2 & 0x10) != 0 )
  {
    updated = UpdateMiniportsEnabledRegistry();
    goto LABEL_4;
  }
  MutexW = CreateMutexW(0, 0, L"Global\\RasMpDevices");
  v9 = MutexW;
  if ( MutexW )
  {
    v10 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
    v7 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_34;
    }
    v7 = 0;
    if ( (a2 & 2) != 0 )
    {
      if ( a2 == 2 )
      {
        if ( a3 )
        {
          v11 = *a3;
          if ( *a3 )
          {
            v12 = 0;
            if ( *v11 )
            {
              do
              {
                ClosePDeviceEntry((LPVOID)v11[v12]);
                v12 = (unsigned int)(v12 + 1);
              }
              while ( v11[v12] );
            }
            v13 = *a3;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v13);
          }
        }
      }
      else
      {
        v7 = -2147024809;
      }
      goto LABEL_33;
    }
    if ( (a2 & 1) != 0 )
    {
      v15 = 0;
      for ( i = a1; i; i >>= 1 )
        v15 += i & 1;
      inited = InitRrasRootEnum(&v20);
      v7 = inited;
      if ( inited )
      {
        if ( inited != -2147024713 )
          goto LABEL_33;
      }
      else if ( !v20 )
      {
LABEL_30:
        v7 = 1;
        goto LABEL_33;
      }
      v7 = CreateMiniportDevices(a1, v15, a2, &v19);
      if ( !v7 )
      {
        if ( v19 )
        {
          if ( a3 )
            *a3 = v19;
          goto LABEL_33;
        }
        goto LABEL_30;
      }
    }
LABEL_33:
    ReleaseMutex(v9);
LABEL_34:
    CloseHandle(v9);
    return v7;
  }
  updated = GetLastError();
LABEL_4:
  v7 = updated;
  if ( updated > 0 )
    return (unsigned __int16)updated | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180099bf4  mov     rax, rsp
0x180099bf7  mov     [rax+20h], r9
0x180099bfb  push    rbx
0x180099bfc  push    rbp
0x180099bfd  push    rsi
0x180099bfe  push    rdi
0x180099bff  push    r14
0x180099c01  push    r15
0x180099c03  sub     rsp, 38h
0x180099c07  mov     qword ptr [rax-48h], 0
0x180099c0f  mov     ebx, edx
0x180099c11  mov     qword ptr [rax+20h], 0
0x180099c19  mov     rsi, r8
0x180099c1c  mov     eax, edx
0x180099c1e  mov     ebp, ecx
0x180099c20  and     eax, 10h
0x180099c23  mov     edx, 8
0x180099c28  test    dl, bl
0x180099c2a  jz      short loc_180099C4D
0x180099c2c  test    eax, eax
0x180099c2e  jz      short loc_180099C4D
0x180099c30  call    UpdateMiniportsEnabledRegistry
0x180099c35  mov     edi, eax
0x180099c37  test    eax, eax
0x180099c39  jle     loc_180099D88
0x180099c3f  movzx   edi, ax
0x180099c42  or      edi, 80070000h
0x180099c48  jmp     loc_180099D88
0x180099c4d  mov     r14d, ebx
0x180099c50  and     r14d, 1
0x180099c54  jz      short loc_180099C61
0x180099c56  test    eax, eax
0x180099c58  jz      short loc_180099C61
0x180099c5a  mov     edx, 1
0x180099c5f  jmp     short loc_180099C30
0x180099c61  lea     r8, aGlobalRasmpdev; "Global\\RasMpDevices"
0x180099c68  xor     edx, edx; bInitialOwner
0x180099c6a  xor     ecx, ecx; lpMutexAttributes
0x180099c6c  call    cs:__imp_CreateMutexW
0x180099c72  mov     r15, rax
0x180099c75  test    rax, rax
0x180099c78  jnz     short loc_180099C82
0x180099c7a  call    cs:__imp_GetLastError
0x180099c80  jmp     short loc_180099C35
0x180099c82  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180099c85  mov     rcx, r15; hHandle
0x180099c88  call    cs:__imp_WaitForSingleObject
0x180099c8e  mov     edi, eax
0x180099c90  test    eax, eax
0x180099c92  jz      short loc_180099CA8
0x180099c94  jle     loc_180099D7F
0x180099c9a  movzx   edi, ax
0x180099c9d  or      edi, 80070000h
0x180099ca3  jmp     loc_180099D7F
0x180099ca8  xor     edi, edi
0x180099caa  test    bl, 2
0x180099cad  jz      short loc_180099D04
0x180099caf  cmp     ebx, 2
0x180099cb2  jz      short loc_180099CBE
0x180099cb4  mov     edi, 80070057h
0x180099cb9  jmp     loc_180099D76
0x180099cbe  test    rsi, rsi
0x180099cc1  jz      loc_180099D76
0x180099cc7  mov     rbx, [rsi]
0x180099cca  test    rbx, rbx
0x180099ccd  jz      loc_180099D76
0x180099cd3  xor     ebp, ebp
0x180099cd5  cmp     [rbx], rdi
0x180099cd8  jz      short loc_180099CEB
0x180099cda  mov     rcx, [rbx+rbp*8]; lpMem
0x180099cde  call    ClosePDeviceEntry
0x180099ce3  inc     ebp
0x180099ce5  cmp     [rbx+rbp*8], rdi
0x180099ce9  jnz     short loc_180099CDA
0x180099ceb  mov     rbx, [rsi]
0x180099cee  call    cs:__imp_GetProcessHeap
0x180099cf4  mov     r8, rbx; lpMem
0x180099cf7  xor     edx, edx; dwFlags
0x180099cf9  mov     rcx, rax; hHeap
0x180099cfc  call    cs:__imp_HeapFree
0x180099d02  jmp     short loc_180099D76
0x180099d04  test    r14d, r14d
0x180099d07  jz      short loc_180099D76
0x180099d09  xor     r14d, r14d
0x180099d0c  mov     ecx, ebp
0x180099d0e  test    ebp, ebp
0x180099d10  jz      short loc_180099D1E
0x180099d12  mov     eax, ecx
0x180099d14  and     eax, 1
0x180099d17  add     r14d, eax
0x180099d1a  shr     ecx, 1
0x180099d1c  jnz     short loc_180099D12
0x180099d1e  lea     rcx, [rsp+68h+arg_18]
0x180099d26  call    InitRrasRootEnum
0x180099d2b  mov     edi, eax
0x180099d2d  test    eax, eax
0x180099d2f  jnz     short loc_180099D3E
0x180099d31  cmp     [rsp+68h+arg_18], 0
0x180099d3a  jnz     short loc_180099D45
0x180099d3c  jmp     short loc_180099D67
0x180099d3e  cmp     eax, 800700B7h
0x180099d43  jnz     short loc_180099D76
0x180099d45  lea     r9, [rsp+68h+var_48]
0x180099d4a  mov     r8d, ebx
0x180099d4d  mov     edx, r14d
0x180099d50  mov     ecx, ebp
0x180099d52  call    CreateMiniportDevices
0x180099d57  mov     edi, eax
0x180099d59  test    eax, eax
0x180099d5b  jnz     short loc_180099D76
0x180099d5d  mov     rax, [rsp+68h+var_48]
0x180099d62  test    rax, rax
0x180099d65  jnz     short loc_180099D6E
0x180099d67  mov     edi, 1
0x180099d6c  jmp     short loc_180099D76
0x180099d6e  test    rsi, rsi
0x180099d71  jz      short loc_180099D76
0x180099d73  mov     [rsi], rax
0x180099d76  mov     rcx, r15; hMutex
0x180099d79  call    cs:__imp_ReleaseMutex
0x180099d7f  mov     rcx, r15; hObject
0x180099d82  call    cs:__imp_CloseHandle
0x180099d88  mov     eax, edi
0x180099d8a  add     rsp, 38h
0x180099d8e  pop     r15
0x180099d90  pop     r14
0x180099d92  pop     rdi
0x180099d93  pop     rsi
0x180099d94  pop     rbp
0x180099d95  pop     rbx
0x180099d96  retn
```
