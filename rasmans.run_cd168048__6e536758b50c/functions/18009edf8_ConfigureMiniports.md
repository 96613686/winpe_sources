# ConfigureMiniports

- ea: `0x18009edf8`
- end: `0x18009efc6`
- name: `ConfigureMiniports`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800073ac`
- `0x18000acb4`
- `0x18009f1e8`

## callees

- `0x18009ed6c`
- `0x18009edf8`
- `0x18009f1e8`
- `0x18009f624`
- `0x18009fa1c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009efaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009efaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ee84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ee84`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009ef9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009ef9b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ee98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ee98`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18009ee70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18009ee70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ef18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ef18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ef04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ef04`

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
0x18009edf8  mov     rax, rsp
0x18009edfb  mov     [rax+20h], r9
0x18009edff  push    rbx
0x18009ee00  push    rbp
0x18009ee01  push    rsi
0x18009ee02  push    rdi
0x18009ee03  push    r14
0x18009ee05  push    r15
0x18009ee07  sub     rsp, 38h
0x18009ee0b  mov     qword ptr [rax-48h], 0
0x18009ee13  mov     ebx, edx
0x18009ee15  mov     qword ptr [rax+20h], 0
0x18009ee1d  mov     rsi, r8
0x18009ee20  mov     eax, edx
0x18009ee22  mov     ebp, ecx
0x18009ee24  and     eax, 10h
0x18009ee27  mov     edx, 8
0x18009ee2c  test    dl, bl
0x18009ee2e  jz      short loc_18009EE51
0x18009ee30  test    eax, eax
0x18009ee32  jz      short loc_18009EE51
0x18009ee34  call    UpdateMiniportsEnabledRegistry
0x18009ee39  mov     edi, eax
0x18009ee3b  test    eax, eax
0x18009ee3d  jle     loc_18009EFB6
0x18009ee43  movzx   edi, ax
0x18009ee46  or      edi, 80070000h
0x18009ee4c  jmp     loc_18009EFB6
0x18009ee51  mov     r14d, ebx
0x18009ee54  and     r14d, 1
0x18009ee58  jz      short loc_18009EE65
0x18009ee5a  test    eax, eax
0x18009ee5c  jz      short loc_18009EE65
0x18009ee5e  mov     edx, 1
0x18009ee63  jmp     short loc_18009EE34
0x18009ee65  lea     r8, aGlobalRasmpdev; "Global\\RasMpDevices"
0x18009ee6c  xor     edx, edx; bInitialOwner
0x18009ee6e  xor     ecx, ecx; lpMutexAttributes
0x18009ee70  call    cs:__imp_CreateMutexW
0x18009ee77  nop     dword ptr [rax+rax+00h]
0x18009ee7c  mov     r15, rax
0x18009ee7f  test    rax, rax
0x18009ee82  jnz     short loc_18009EE92
0x18009ee84  call    cs:__imp_GetLastError
0x18009ee8b  nop     dword ptr [rax+rax+00h]
0x18009ee90  jmp     short loc_18009EE39
0x18009ee92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009ee95  mov     rcx, r15; hHandle
0x18009ee98  call    cs:__imp_WaitForSingleObject
0x18009ee9f  nop     dword ptr [rax+rax+00h]
0x18009eea4  mov     edi, eax
0x18009eea6  test    eax, eax
0x18009eea8  jz      short loc_18009EEBE
0x18009eeaa  jle     loc_18009EFA7
0x18009eeb0  movzx   edi, ax
0x18009eeb3  or      edi, 80070000h
0x18009eeb9  jmp     loc_18009EFA7
0x18009eebe  xor     edi, edi
0x18009eec0  test    bl, 2
0x18009eec3  jz      short loc_18009EF26
0x18009eec5  cmp     ebx, 2
0x18009eec8  jz      short loc_18009EED4
0x18009eeca  mov     edi, 80070057h
0x18009eecf  jmp     loc_18009EF98
0x18009eed4  test    rsi, rsi
0x18009eed7  jz      loc_18009EF98
0x18009eedd  mov     rbx, [rsi]
0x18009eee0  test    rbx, rbx
0x18009eee3  jz      loc_18009EF98
0x18009eee9  xor     ebp, ebp
0x18009eeeb  cmp     [rbx], rdi
0x18009eeee  jz      short loc_18009EF01
0x18009eef0  mov     rcx, [rbx+rbp*8]; lpMem
0x18009eef4  call    ClosePDeviceEntry
0x18009eef9  inc     ebp
0x18009eefb  cmp     [rbx+rbp*8], rdi
0x18009eeff  jnz     short loc_18009EEF0
0x18009ef01  mov     rbx, [rsi]
0x18009ef04  call    cs:__imp_GetProcessHeap
0x18009ef0b  nop     dword ptr [rax+rax+00h]
0x18009ef10  mov     r8, rbx; lpMem
0x18009ef13  xor     edx, edx; dwFlags
0x18009ef15  mov     rcx, rax; hHeap
0x18009ef18  call    cs:__imp_HeapFree
0x18009ef1f  nop     dword ptr [rax+rax+00h]
0x18009ef24  jmp     short loc_18009EF98
0x18009ef26  test    r14d, r14d
0x18009ef29  jz      short loc_18009EF98
0x18009ef2b  xor     r14d, r14d
0x18009ef2e  mov     ecx, ebp
0x18009ef30  test    ebp, ebp
0x18009ef32  jz      short loc_18009EF40
0x18009ef34  mov     eax, ecx
0x18009ef36  and     eax, 1
0x18009ef39  add     r14d, eax
0x18009ef3c  shr     ecx, 1
0x18009ef3e  jnz     short loc_18009EF34
0x18009ef40  lea     rcx, [rsp+68h+arg_18]
0x18009ef48  call    InitRrasRootEnum
0x18009ef4d  mov     edi, eax
0x18009ef4f  test    eax, eax
0x18009ef51  jnz     short loc_18009EF60
0x18009ef53  cmp     [rsp+68h+arg_18], 0
0x18009ef5c  jnz     short loc_18009EF67
0x18009ef5e  jmp     short loc_18009EF89
0x18009ef60  cmp     eax, 800700B7h
0x18009ef65  jnz     short loc_18009EF98
0x18009ef67  lea     r9, [rsp+68h+var_48]
0x18009ef6c  mov     r8d, ebx
0x18009ef6f  mov     edx, r14d
0x18009ef72  mov     ecx, ebp
0x18009ef74  call    CreateMiniportDevices
0x18009ef79  mov     edi, eax
0x18009ef7b  test    eax, eax
0x18009ef7d  jnz     short loc_18009EF98
0x18009ef7f  mov     rax, [rsp+68h+var_48]
0x18009ef84  test    rax, rax
0x18009ef87  jnz     short loc_18009EF90
0x18009ef89  mov     edi, 1
0x18009ef8e  jmp     short loc_18009EF98
0x18009ef90  test    rsi, rsi
0x18009ef93  jz      short loc_18009EF98
0x18009ef95  mov     [rsi], rax
0x18009ef98  mov     rcx, r15; hMutex
0x18009ef9b  call    cs:__imp_ReleaseMutex
0x18009efa2  nop     dword ptr [rax+rax+00h]
0x18009efa7  mov     rcx, r15; hObject
0x18009efaa  call    cs:__imp_CloseHandle
0x18009efb1  nop     dword ptr [rax+rax+00h]
0x18009efb6  mov     eax, edi
0x18009efb8  add     rsp, 38h
0x18009efbc  pop     r15
0x18009efbe  pop     r14
0x18009efc0  pop     rdi
0x18009efc1  pop     rsi
0x18009efc2  pop     rbp
0x18009efc3  pop     rbx
0x18009efc4  retn
```
