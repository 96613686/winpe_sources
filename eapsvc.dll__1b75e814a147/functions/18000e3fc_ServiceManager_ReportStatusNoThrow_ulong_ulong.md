# ServiceManager::ReportStatusNoThrow(ulong,ulong)

- ea: `0x18000e3fc`
- end: `0x18000e4a5`
- name: `?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z`
- size: `169`
- prototype: `__int64 __fastcall(ServiceManager *this, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e21c`
- `0x18000e2bc`

## callees

- `0x18000e3fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e414`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e494`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e489`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e47b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e47b`

## pseudocode

```c
__int64 __fastcall ServiceManager::ReportStatusNoThrow(ServiceManager *this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  int v7; // ecx
  bool v8; // zf
  DWORD LastError; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a2 )
  {
    *((_DWORD *)this + 29) = a2;
    *((_DWORD *)this + 31) = a3;
    if ( (unsigned int)(a2 - 2) <= 1 )
    {
      ++*((_DWORD *)this + 33);
      v7 = *((_DWORD *)this + 21);
    }
    else
    {
      *((_DWORD *)this + 33) = 0;
      v7 = 0;
    }
    *((_DWORD *)this + 34) = v7;
    if ( a2 == 4 )
    {
      v8 = *((_BYTE *)this + 140) == 0;
      *((_DWORD *)this + 30) = 133;
      if ( !v8 )
        *((_DWORD *)this + 30) = 197;
    }
    else
    {
      *((_DWORD *)this + 30) = 0;
    }
  }
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 13), (LPSERVICE_STATUS)this + 4) )
    LastError = 0;
  else
    LastError = GetLastError();
  LeaveCriticalSection(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000e3fc  push    rbx
0x18000e3fe  push    rbp
0x18000e3ff  push    rsi
0x18000e400  push    rdi
0x18000e401  sub     rsp, 28h
0x18000e405  lea     rsi, [rcx+18h]
0x18000e409  mov     rbx, rcx
0x18000e40c  mov     rcx, rsi; lpCriticalSection
0x18000e40f  mov     ebp, r8d
0x18000e412  mov     edi, edx
0x18000e414  call    cs:__imp_EnterCriticalSection
0x18000e41a  test    edi, edi
0x18000e41c  jz      short loc_18000E473
0x18000e41e  lea     eax, [rdi-2]
0x18000e421  mov     [rbx+74h], edi
0x18000e424  cmp     eax, 1
0x18000e427  mov     [rbx+7Ch], ebp
0x18000e42a  mov     eax, 88h
0x18000e42f  mov     rdx, rbx
0x18000e432  jbe     short loc_18000E442
0x18000e434  mov     dword ptr [rbx+84h], 0
0x18000e43e  xor     ecx, ecx
0x18000e440  jmp     short loc_18000E44B
0x18000e442  inc     dword ptr [rbx+84h]
0x18000e448  mov     ecx, [rbx+54h]
0x18000e44b  mov     [rdx+rax], ecx
0x18000e44e  cmp     edi, 4
0x18000e451  jnz     short loc_18000E46C
0x18000e453  cmp     byte ptr [rbx+8Ch], 0
0x18000e45a  mov     dword ptr [rbx+78h], 85h
0x18000e461  jz      short loc_18000E473
0x18000e463  mov     dword ptr [rbx+78h], 0C5h
0x18000e46a  jmp     short loc_18000E473
0x18000e46c  mov     dword ptr [rbx+78h], 0
0x18000e473  mov     rcx, [rbx+68h]; hServiceStatus
0x18000e477  lea     rdx, [rbx+70h]; lpServiceStatus
0x18000e47b  call    cs:__imp_SetServiceStatus
0x18000e481  test    eax, eax
0x18000e483  jz      short loc_18000E489
0x18000e485  xor     ebx, ebx
0x18000e487  jmp     short loc_18000E491
0x18000e489  call    cs:__imp_GetLastError
0x18000e48f  mov     ebx, eax
0x18000e491  mov     rcx, rsi; lpCriticalSection
0x18000e494  call    cs:__imp_LeaveCriticalSection
0x18000e49a  mov     eax, ebx
0x18000e49c  add     rsp, 28h
0x18000e4a0  pop     rdi
0x18000e4a1  pop     rsi
0x18000e4a2  pop     rbp
0x18000e4a3  pop     rbx
0x18000e4a4  retn
```
