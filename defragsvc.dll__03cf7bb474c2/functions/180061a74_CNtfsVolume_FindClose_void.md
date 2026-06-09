# CNtfsVolume::_FindClose(void *)

- ea: `0x180061a74`
- end: `0x180061b40`
- name: `?_FindClose@CNtfsVolume@@AEAAJPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(CNtfsVolume *this, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a988`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180061a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061aab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061aab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b1f`
- `ntdll!NtClose` at `0x180061aec`
- `ntdll!NtClose` at `0x180061aec`
- `ntdll!RtlEnterCriticalSection` at `0x180061ac4`
- `ntdll!RtlEnterCriticalSection` at `0x180061ac4`
- `ntdll!RtlLeaveCriticalSection` at `0x180061ae3`
- `ntdll!RtlLeaveCriticalSection` at `0x180061ae3`
- `ntdll!RtlDeleteCriticalSection` at `0x180061b02`
- `ntdll!RtlDeleteCriticalSection` at `0x180061b02`
- `ntdll!RtlNtStatusToDosError` at `0x180061b17`
- `ntdll!RtlNtStatusToDosError` at `0x180061b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b0b`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_FindClose(CNtfsVolume *this, char *a2)
{
  unsigned int v3; // edi
  void *v4; // rbx
  void *v5; // r14
  int v6; // eax
  DWORD v7; // eax
  unsigned int v9; // [rsp+20h] [rbp-68h] BYREF
  __int16 v10; // [rsp+24h] [rbp-64h]

  v3 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CNtfsVolume::_FindClose", 2369, 1);
  if ( a2 == (char *)-1LL )
  {
    SetLastError(6u);
    v10 = 2379;
  }
  else
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 32));
    v4 = *(void **)a2;
    v5 = (void *)*((_QWORD *)a2 + 1);
    *(_QWORD *)a2 = -1;
    *((_QWORD *)a2 + 1) = 0;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 32));
    v6 = NtClose(v4);
    if ( v6 < 0 )
    {
      v7 = RtlNtStatusToDosError(v6);
      SetLastError(v7);
    }
    else
    {
      CoTaskMemFree(v5);
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 32));
      CoTaskMemFree(a2);
      v3 = 0;
    }
  }
  v9 = v3;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v3;
}

```

## disassembly

```asm
0x180061a74  push    rbx
0x180061a76  push    rbp
0x180061a77  push    rsi
0x180061a78  push    rdi
0x180061a79  push    r14
0x180061a7b  sub     rsp, 60h
0x180061a7f  mov     rsi, rdx
0x180061a82  mov     edi, 1
0x180061a87  mov     r9d, edi; unsigned __int16
0x180061a8a  mov     r8d, 941h; unsigned __int16
0x180061a90  lea     rdx, aCntfsvolumeFin_2; "CNtfsVolume::_FindClose"
0x180061a97  lea     rcx, [rsp+88h+var_68]; this
0x180061a9c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180061aa1  nop
0x180061aa2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180061aa6  jnz     short loc_180061ABD
0x180061aa8  lea     ecx, [rdi+5]; dwErrCode
0x180061aab  call    cs:__imp_SetLastError
0x180061ab1  mov     eax, 94Bh
0x180061ab6  mov     [rsp+88h+var_64], ax
0x180061abb  jmp     short loc_180061B25
0x180061abd  lea     rbp, [rsi+20h]
0x180061ac1  mov     rcx, rbp; CriticalSection
0x180061ac4  call    cs:__imp_RtlEnterCriticalSection
0x180061aca  mov     rbx, [rsi]
0x180061acd  mov     r14, [rsi+8]
0x180061ad1  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180061ad8  mov     qword ptr [rsi+8], 0
0x180061ae0  mov     rcx, rbp; CriticalSection
0x180061ae3  call    cs:__imp_RtlLeaveCriticalSection
0x180061ae9  mov     rcx, rbx; Handle
0x180061aec  call    cs:__imp_NtClose
0x180061af2  test    eax, eax
0x180061af4  js      short loc_180061B15
0x180061af6  mov     rcx, r14; pv
0x180061af9  call    cs:__imp_CoTaskMemFree
0x180061aff  mov     rcx, rbp; CriticalSection
0x180061b02  call    cs:__imp_RtlDeleteCriticalSection
0x180061b08  mov     rcx, rsi; pv
0x180061b0b  call    cs:__imp_CoTaskMemFree
0x180061b11  xor     edi, edi
0x180061b13  jmp     short loc_180061B25
0x180061b15  mov     ecx, eax; Status
0x180061b17  call    cs:__imp_RtlNtStatusToDosError
0x180061b1d  mov     ecx, eax; dwErrCode
0x180061b1f  call    cs:__imp_SetLastError
0x180061b25  mov     [rsp+88h+var_68], edi
0x180061b29  lea     rcx, [rsp+88h+var_68]; this
0x180061b2e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180061b33  mov     eax, edi
0x180061b35  add     rsp, 60h
0x180061b39  pop     r14
0x180061b3b  pop     rdi
0x180061b3c  pop     rsi
0x180061b3d  pop     rbp
0x180061b3e  pop     rbx
0x180061b3f  retn
```
