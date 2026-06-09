# ConfigureMiniports

- ea: `0x180045ee8`
- end: `0x18004608b`
- name: `ConfigureMiniports`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800115c8`
- `0x180011eb0`
- `0x180046254`

## callees

- `0x180045e7c`
- `0x180045ee8`
- `0x180046254`
- `0x180046658`
- `0x1800469b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046076`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045ff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045ff0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045f7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045f7c`
- `KERNEL32!CreateMutexW` at `0x180045f60`
- `KERNEL32!CreateMutexW` at `0x180045f60`
- `KERNEL32!ReleaseMutex` at `0x18004606d`
- `KERNEL32!ReleaseMutex` at `0x18004606d`
- `KERNEL32!GetProcessHeap` at `0x180045fe2`
- `KERNEL32!GetProcessHeap` at `0x180045fe2`

## pseudocode

```c
__int64 __fastcall ConfigureMiniports(unsigned int a1, unsigned int a2, _QWORD **a3)
{
  int v6; // eax
  int v7; // edx
  int updated; // eax
  unsigned int v9; // edi
  HANDLE MutexW; // rax
  void *v11; // r15
  signed int v12; // eax
  _QWORD *v13; // rbx
  __int64 v14; // rbp
  _QWORD *v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v17; // r14d
  unsigned int i; // ecx
  unsigned int inited; // eax
  _QWORD *v21; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+88h] [rbp+20h] BYREF

  v21 = 0;
  v22 = 0;
  v6 = a2 & 0x10;
  v7 = 8;
  if ( (a2 & 8) != 0 && v6 )
    goto LABEL_3;
  if ( (a2 & 1) != 0 && v6 )
  {
    v7 = 1;
LABEL_3:
    updated = UpdateMiniportsEnabledRegistry(a1, v7);
    goto LABEL_4;
  }
  MutexW = CreateMutexW(0, 0, L"Global\\RasMpDevices");
  v11 = MutexW;
  if ( MutexW )
  {
    v12 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
    v9 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_35;
    }
    v9 = 0;
    if ( (a2 & 2) != 0 )
    {
      if ( a2 == 2 )
      {
        if ( a3 )
        {
          v13 = *a3;
          if ( *a3 )
          {
            v14 = 0;
            if ( *v13 )
            {
              do
              {
                ClosePDeviceEntry((LPVOID)v13[v14]);
                v14 = (unsigned int)(v14 + 1);
              }
              while ( v13[v14] );
            }
            v15 = *a3;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v15);
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
      goto LABEL_34;
    }
    if ( (a2 & 1) != 0 )
    {
      v17 = 0;
      for ( i = a1; i; i >>= 1 )
        v17 += i & 1;
      inited = InitRrasRootEnum(&v22);
      v9 = inited;
      if ( inited )
      {
        if ( inited != -2147024713 )
          goto LABEL_34;
      }
      else if ( !v22 )
      {
LABEL_31:
        v9 = 1;
        goto LABEL_34;
      }
      v9 = CreateMiniportDevices(a1, v17, a2, &v21);
      if ( !v9 )
      {
        if ( v21 )
        {
          if ( a3 )
            *a3 = v21;
          goto LABEL_34;
        }
        goto LABEL_31;
      }
    }
LABEL_34:
    ReleaseMutex(v11);
LABEL_35:
    CloseHandle(v11);
    return v9;
  }
  updated = GetLastError();
LABEL_4:
  v9 = updated;
  if ( updated > 0 )
    return (unsigned __int16)updated | 0x80070000;
  return v9;
}

```

## disassembly

```asm
0x180045ee8  mov     rax, rsp
0x180045eeb  mov     [rax+20h], r9
0x180045eef  push    rbx
0x180045ef0  push    rbp
0x180045ef1  push    rsi
0x180045ef2  push    rdi
0x180045ef3  push    r14
0x180045ef5  push    r15
0x180045ef7  sub     rsp, 38h
0x180045efb  mov     qword ptr [rax-48h], 0
0x180045f03  mov     ebx, edx
0x180045f05  mov     qword ptr [rax+20h], 0
0x180045f0d  mov     rsi, r8
0x180045f10  mov     eax, edx
0x180045f12  mov     ebp, ecx
0x180045f14  and     eax, 10h
0x180045f17  mov     edx, 8
0x180045f1c  test    dl, bl
0x180045f1e  jz      short loc_180045F41
0x180045f20  test    eax, eax
0x180045f22  jz      short loc_180045F41
0x180045f24  call    UpdateMiniportsEnabledRegistry
0x180045f29  mov     edi, eax
0x180045f2b  test    eax, eax
0x180045f2d  jle     loc_18004607C
0x180045f33  movzx   edi, ax
0x180045f36  or      edi, 80070000h
0x180045f3c  jmp     loc_18004607C
0x180045f41  mov     r14d, ebx
0x180045f44  and     r14d, 1
0x180045f48  jz      short loc_180045F55
0x180045f4a  test    eax, eax
0x180045f4c  jz      short loc_180045F55
0x180045f4e  mov     edx, 1
0x180045f53  jmp     short loc_180045F24
0x180045f55  lea     r8, Name; "Global\\RasMpDevices"
0x180045f5c  xor     edx, edx; bInitialOwner
0x180045f5e  xor     ecx, ecx; lpMutexAttributes
0x180045f60  call    cs:__imp_CreateMutexW
0x180045f66  mov     r15, rax
0x180045f69  test    rax, rax
0x180045f6c  jnz     short loc_180045F76
0x180045f6e  call    cs:__imp_GetLastError
0x180045f74  jmp     short loc_180045F29
0x180045f76  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180045f79  mov     rcx, r15; hHandle
0x180045f7c  call    cs:__imp_WaitForSingleObject
0x180045f82  mov     edi, eax
0x180045f84  test    eax, eax
0x180045f86  jz      short loc_180045F9C
0x180045f88  jle     loc_180046073
0x180045f8e  movzx   edi, ax
0x180045f91  or      edi, 80070000h
0x180045f97  jmp     loc_180046073
0x180045f9c  xor     edi, edi
0x180045f9e  test    bl, 2
0x180045fa1  jz      short loc_180045FF8
0x180045fa3  cmp     ebx, 2
0x180045fa6  jz      short loc_180045FB2
0x180045fa8  mov     edi, 80070057h
0x180045fad  jmp     loc_18004606A
0x180045fb2  test    rsi, rsi
0x180045fb5  jz      loc_18004606A
0x180045fbb  mov     rbx, [rsi]
0x180045fbe  test    rbx, rbx
0x180045fc1  jz      loc_18004606A
0x180045fc7  xor     ebp, ebp
0x180045fc9  cmp     [rbx], rdi
0x180045fcc  jz      short loc_180045FDF
0x180045fce  mov     rcx, [rbx+rbp*8]; lpMem
0x180045fd2  call    ClosePDeviceEntry
0x180045fd7  inc     ebp
0x180045fd9  cmp     [rbx+rbp*8], rdi
0x180045fdd  jnz     short loc_180045FCE
0x180045fdf  mov     rbx, [rsi]
0x180045fe2  call    cs:__imp_GetProcessHeap
0x180045fe8  mov     r8, rbx; lpMem
0x180045feb  xor     edx, edx; dwFlags
0x180045fed  mov     rcx, rax; hHeap
0x180045ff0  call    cs:__imp_HeapFree
0x180045ff6  jmp     short loc_18004606A
0x180045ff8  test    r14d, r14d
0x180045ffb  jz      short loc_18004606A
0x180045ffd  xor     r14d, r14d
0x180046000  mov     ecx, ebp
0x180046002  test    ebp, ebp
0x180046004  jz      short loc_180046012
0x180046006  mov     eax, ecx
0x180046008  and     eax, 1
0x18004600b  add     r14d, eax
0x18004600e  shr     ecx, 1
0x180046010  jnz     short loc_180046006
0x180046012  lea     rcx, [rsp+68h+arg_18]
0x18004601a  call    InitRrasRootEnum
0x18004601f  mov     edi, eax
0x180046021  test    eax, eax
0x180046023  jnz     short loc_180046032
0x180046025  cmp     [rsp+68h+arg_18], 0
0x18004602e  jnz     short loc_180046039
0x180046030  jmp     short loc_18004605B
0x180046032  cmp     eax, 800700B7h
0x180046037  jnz     short loc_18004606A
0x180046039  lea     r9, [rsp+68h+var_48]
0x18004603e  mov     r8d, ebx
0x180046041  mov     edx, r14d
0x180046044  mov     ecx, ebp
0x180046046  call    CreateMiniportDevices
0x18004604b  mov     edi, eax
0x18004604d  test    eax, eax
0x18004604f  jnz     short loc_18004606A
0x180046051  mov     rax, [rsp+68h+var_48]
0x180046056  test    rax, rax
0x180046059  jnz     short loc_180046062
0x18004605b  mov     edi, 1
0x180046060  jmp     short loc_18004606A
0x180046062  test    rsi, rsi
0x180046065  jz      short loc_18004606A
0x180046067  mov     [rsi], rax
0x18004606a  mov     rcx, r15; hMutex
0x18004606d  call    cs:__imp_ReleaseMutex
0x180046073  mov     rcx, r15; hObject
0x180046076  call    cs:__imp_CloseHandle
0x18004607c  mov     eax, edi
0x18004607e  add     rsp, 38h
0x180046082  pop     r15
0x180046084  pop     r14
0x180046086  pop     rdi
0x180046087  pop     rsi
0x180046088  pop     rbp
0x180046089  pop     rbx
0x18004608a  retn
```
