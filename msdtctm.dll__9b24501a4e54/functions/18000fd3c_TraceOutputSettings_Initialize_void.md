# TraceOutputSettings::Initialize(void *)

- ea: `0x18000fd3c`
- end: `0x18000fdfc`
- name: `?Initialize@TraceOutputSettings@@SAKPEAX@Z`
- size: `192`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ca0`

## callees

- `0x18000b450`
- `0x18000fd3c`
- `0x1800b83d6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fdf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b8a0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fdf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b8a0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fd52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fd52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fda7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fda7`

## string_xrefs

- `0x18000fda0`: `Unable to open MSDTC\Tracing settings key\n`

## pseudocode

```c
__int64 __fastcall TraceOutputSettings::Initialize(void *a1)
{
  LSTATUS v1; // ebx
  __int64 v3; // [rsp+0h] [rbp-48h] BYREF
  __int64 *v4; // [rsp+30h] [rbp-18h]
  unsigned int v5; // [rsp+50h] [rbp+8h]

  v4 = &v3;
  EnterCriticalSection(&stru_1801535E0);
  if ( TraceOutputSettings::fInitialized )
    goto LABEL_8;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\MSDTC\\Tracing",
         0,
         0x20119u,
         &TraceOutputSettings::hkConfiguration);
  if ( !v1 )
  {
    TraceOutputSettings::ReadConfiguration_Locked();
    TraceOutputSettings::fInitialized = 1;
LABEL_8:
    LeaveCriticalSection(&stru_1801535E0);
    return 0;
  }
  TraceOutputSettings::hkConfiguration = 0;
  OutputDebugStringW(L"Unable to open MSDTC\\Tracing settings key\n");
  if ( v1 > 0 )
    v5 = (unsigned __int16)v1 | 0x80070000;
  else
    v5 = v1;
  local_unwind_0(v4, &loc_18000FDD5);
  return v5;
}

```

## disassembly

```asm
0x18000fd3c  mov     [rsp+arg_0], rcx
0x18000fd41  push    rbx
0x18000fd42  sub     rsp, 40h
0x18000fd46  mov     [rsp+48h+var_18], rsp
0x18000fd4b  lea     rcx, stru_1801535E0; lpCriticalSection
0x18000fd52  call    cs:__imp_EnterCriticalSection
0x18000fd58  nop
0x18000fd59  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x18000fd60  jnz     loc_18000FDEB
0x18000fd66  lea     rax, ?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; HKEY__ * TraceOutputSettings::hkConfiguration
0x18000fd6d  mov     [rsp+48h+phkResult], rax; phkResult
0x18000fd72  mov     r9d, 20119h; samDesired
0x18000fd78  xor     r8d, r8d; ulOptions
0x18000fd7b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MSDTC\\Tracing"
0x18000fd82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fd89  call    cs:__imp_RegOpenKeyExW
0x18000fd8f  mov     ebx, eax
0x18000fd91  test    eax, eax
0x18000fd93  jz      short loc_18000FDDF
0x18000fd95  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x18000fda0  lea     rcx, aUnableToOpenMs; "Unable to open MSDTC\\Tracing settings "...
0x18000fda7  call    cs:__imp_OutputDebugStringW
0x18000fdad  test    ebx, ebx
0x18000fdaf  jg      short loc_18000FDB7
0x18000fdb1  mov     dword ptr [rsp+48h+arg_0], ebx
0x18000fdb5  jmp     short loc_18000FDC3
0x18000fdb7  movzx   eax, bx
0x18000fdba  or      eax, 80070000h
0x18000fdbf  mov     dword ptr [rsp+48h+arg_0], eax
0x18000fdc3  lea     rdx, loc_18000FDD5
0x18000fdca  mov     rcx, [rsp+48h+var_18]
0x18000fdcf  call    _local_unwind_0
0x18000fdd4  nop
0x18000fdd5  mov     eax, dword ptr [rsp+48h+arg_0]
0x18000fdd9  add     rsp, 40h
0x18000fddd  pop     rbx
0x18000fdde  retn
0x18000fddf  call    ?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ; TraceOutputSettings::ReadConfiguration_Locked(void)
0x18000fde4  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 1; bool TraceOutputSettings::fInitialized
0x18000fdeb  lea     rcx, stru_1801535E0; lpCriticalSection
0x18000fdf2  call    cs:__imp_LeaveCriticalSection
0x18000fdf8  xor     eax, eax
0x18000fdfa  jmp     short loc_18000FDD9
0x1800b89fb  push    rbp
0x1800b89fd  sub     rsp, 30h
0x1800b8a01  mov     rbp, rdx
0x1800b8a04  lea     rcx, stru_1801535E0; lpCriticalSection
0x1800b8a0b  call    cs:__imp_LeaveCriticalSection
0x1800b8a11  nop
0x1800b8a12  add     rsp, 30h
0x1800b8a16  pop     rbp
0x1800b8a17  retn
```
