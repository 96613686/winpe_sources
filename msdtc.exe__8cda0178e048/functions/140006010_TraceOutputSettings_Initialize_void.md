# TraceOutputSettings::Initialize(void *)

- ea: `0x140006010`
- end: `0x1400060d0`
- name: `?Initialize@TraceOutputSettings@@SAKPEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400011e0`

## callees

- `0x140006010`
- `0x1400060d8`
- `0x140006ed6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000605d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000605d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000607b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000607b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400060c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400060c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007172`

## string_xrefs

- `0x140006074`: `Unable to open MSDTC\Tracing settings key\n`

## pseudocode

```c
__int64 __fastcall TraceOutputSettings::Initialize(void *a1)
{
  LSTATUS v1; // ebx
  __int64 v3; // [rsp+0h] [rbp-48h] BYREF
  __int64 *v4; // [rsp+30h] [rbp-18h]
  unsigned int v5; // [rsp+50h] [rbp+8h]

  v4 = &v3;
  EnterCriticalSection(&stru_140010798);
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
    LeaveCriticalSection(&stru_140010798);
    return 0;
  }
  TraceOutputSettings::hkConfiguration = 0;
  OutputDebugStringW(L"Unable to open MSDTC\\Tracing settings key\n");
  if ( v1 > 0 )
    v5 = (unsigned __int16)v1 | 0x80070000;
  else
    v5 = v1;
  local_unwind_0(v4, &loc_1400060A9);
  return v5;
}

```

## disassembly

```asm
0x140006010  mov     [rsp+arg_0], rcx
0x140006015  push    rbx
0x140006016  sub     rsp, 40h
0x14000601a  mov     [rsp+48h+var_18], rsp
0x14000601f  lea     rcx, stru_140010798; lpCriticalSection
0x140006026  call    cs:__imp_EnterCriticalSection
0x14000602c  nop
0x14000602d  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x140006034  jnz     loc_1400060BF
0x14000603a  lea     rax, ?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; HKEY__ * TraceOutputSettings::hkConfiguration
0x140006041  mov     [rsp+48h+phkResult], rax; phkResult
0x140006046  mov     r9d, 20119h; samDesired
0x14000604c  xor     r8d, r8d; ulOptions
0x14000604f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MSDTC\\Tracing"
0x140006056  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000605d  call    cs:__imp_RegOpenKeyExW
0x140006063  mov     ebx, eax
0x140006065  test    eax, eax
0x140006067  jz      short loc_1400060B3
0x140006069  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x140006074  lea     rcx, aUnableToOpenMs; "Unable to open MSDTC\\Tracing settings "...
0x14000607b  call    cs:__imp_OutputDebugStringW
0x140006081  test    ebx, ebx
0x140006083  jg      short loc_14000608B
0x140006085  mov     dword ptr [rsp+48h+arg_0], ebx
0x140006089  jmp     short loc_140006097
0x14000608b  movzx   eax, bx
0x14000608e  or      eax, 80070000h
0x140006093  mov     dword ptr [rsp+48h+arg_0], eax
0x140006097  lea     rdx, loc_1400060A9
0x14000609e  mov     rcx, [rsp+48h+var_18]
0x1400060a3  call    _local_unwind_0
0x1400060a8  nop
0x1400060a9  mov     eax, dword ptr [rsp+48h+arg_0]
0x1400060ad  add     rsp, 40h
0x1400060b1  pop     rbx
0x1400060b2  retn
0x1400060b3  call    ?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ; TraceOutputSettings::ReadConfiguration_Locked(void)
0x1400060b8  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 1; bool TraceOutputSettings::fInitialized
0x1400060bf  lea     rcx, stru_140010798; lpCriticalSection
0x1400060c6  call    cs:__imp_LeaveCriticalSection
0x1400060cc  xor     eax, eax
0x1400060ce  jmp     short loc_1400060AD
0x140007162  push    rbp
0x140007164  sub     rsp, 30h
0x140007168  mov     rbp, rdx
0x14000716b  lea     rcx, stru_140010798; lpCriticalSection
0x140007172  call    cs:__imp_LeaveCriticalSection
0x140007178  nop
0x140007179  add     rsp, 30h
0x14000717d  pop     rbp
0x14000717e  retn
```
