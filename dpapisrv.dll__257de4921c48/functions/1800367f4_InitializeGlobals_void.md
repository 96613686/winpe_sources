# InitializeGlobals(void)

- ea: `0x1800367f4`
- end: `0x180036945`
- name: `?InitializeGlobals@@YAKXZ`
- size: `337`
- prototype: `NTSTATUS(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800280a8`

## callees

- `0x18000b680`
- `0x180013f2c`
- `0x1800367f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036868`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036868`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036887`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368b8`
- `ntdll!RtlInitializeCriticalSection` at `0x180036807`
- `ntdll!RtlInitializeCriticalSection` at `0x180036904`
- `ntdll!RtlInitializeCriticalSection` at `0x180036925`
- `ntdll!RtlInitializeCriticalSection` at `0x180036807`
- `ntdll!RtlInitializeCriticalSection` at `0x180036904`
- `ntdll!RtlInitializeCriticalSection` at `0x180036925`

## pseudocode

```c
NTSTATUS InitializeGlobals(void)
{
  NTSTATUS result; // eax
  void *v1; // rcx
  DWORD LastError; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF

  dwDisposition = 0;
  result = RtlInitializeCriticalSection(&stru_18004C978);
  if ( result >= 0 )
  {
    dword_18004CCB4 = 1;
    result = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Cryptography\\Protect\\Providers\\df9d8cd0-1501-11d1-8c7a-00c04fc297eb",
               0,
               0,
               0,
               0x11u,
               0,
               &hKey,
               &dwDisposition);
    if ( !result )
    {
      hObject = CreateEventW(0, 0, 1, 0);
      if ( !hObject )
      {
        v1 = &WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            15,
            WPP_c311ca3328b03ff90a5c1865b7fbbc75_Traceguids,
            LastError);
        }
      }
      UpdateGlobals((int)v1);
      qword_18004C970 = (__int64)&qword_18004C968;
      qword_18004C968 = (__int64)&qword_18004C968;
      result = RtlInitializeCriticalSection(&CriticalSection);
      if ( result >= 0 )
      {
        dword_18004CCA8 = 1;
        result = RtlInitializeCriticalSection(&stru_18004C940);
        if ( result >= 0 )
          dword_18004CCB8 = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800367f4  sub     rsp, 58h
0x1800367f8  lea     rcx, stru_18004C978; CriticalSection
0x1800367ff  mov     [rsp+58h+dwDisposition], 0
0x180036807  call    cs:__imp_RtlInitializeCriticalSection
0x18003680e  nop     dword ptr [rax+rax+00h]
0x180036813  test    eax, eax
0x180036815  js      loc_18003693F
0x18003681b  lea     rax, [rsp+58h+dwDisposition]
0x180036820  mov     cs:dword_18004CCB4, 1
0x18003682a  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18003682f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Cryptography\\Prot"...
0x180036836  lea     rax, hKey
0x18003683d  xor     r9d, r9d; lpClass
0x180036840  mov     [rsp+58h+phkResult], rax; phkResult
0x180036845  xor     r8d, r8d; Reserved
0x180036848  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036851  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036858  mov     [rsp+58h+samDesired], 11h; samDesired
0x180036860  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180036868  call    cs:__imp_RegCreateKeyExW
0x18003686f  nop     dword ptr [rax+rax+00h]
0x180036874  test    eax, eax
0x180036876  jnz     loc_18003693F
0x18003687c  xor     r9d, r9d; lpName
0x18003687f  lea     r8d, [rax+1]; bInitialState
0x180036883  xor     edx, edx; bManualReset
0x180036885  xor     ecx, ecx; lpEventAttributes
0x180036887  call    cs:__imp_CreateEventW
0x18003688e  nop     dword ptr [rax+rax+00h]
0x180036893  mov     cs:hObject, rax
0x18003689a  test    rax, rax
0x18003689d  jnz     short loc_1800368E3
0x18003689f  mov     rax, cs:WPP_GLOBAL_Control
0x1800368a6  lea     rcx, WPP_GLOBAL_Control
0x1800368ad  cmp     rax, rcx
0x1800368b0  jz      short loc_1800368E3
0x1800368b2  test    byte ptr [rax+1Ch], 8
0x1800368b6  jz      short loc_1800368E3
0x1800368b8  call    cs:__imp_GetLastError
0x1800368bf  nop     dword ptr [rax+rax+00h]
0x1800368c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368cb  lea     r8, WPP_c311ca3328b03ff90a5c1865b7fbbc75_Traceguids
0x1800368d2  mov     edx, 0Fh
0x1800368d7  mov     r9d, eax
0x1800368da  mov     rcx, [rcx+10h]
0x1800368de  call    WPP_SF_d
0x1800368e3  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x1800368e8  lea     rax, qword_18004C968
0x1800368ef  lea     rcx, CriticalSection; CriticalSection
0x1800368f6  mov     cs:qword_18004C970, rax
0x1800368fd  mov     cs:qword_18004C968, rax
0x180036904  call    cs:__imp_RtlInitializeCriticalSection
0x18003690b  nop     dword ptr [rax+rax+00h]
0x180036910  test    eax, eax
0x180036912  js      short loc_18003693F
0x180036914  lea     rcx, stru_18004C940; CriticalSection
0x18003691b  mov     cs:dword_18004CCA8, 1
0x180036925  call    cs:__imp_RtlInitializeCriticalSection
0x18003692c  nop     dword ptr [rax+rax+00h]
0x180036931  test    eax, eax
0x180036933  js      short loc_18003693F
0x180036935  mov     cs:dword_18004CCB8, 1
0x18003693f  add     rsp, 58h
0x180036943  retn
```
