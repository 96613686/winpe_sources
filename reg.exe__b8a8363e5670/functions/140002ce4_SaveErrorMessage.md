# SaveErrorMessage

- ea: `0x140002ce4`
- end: `0x140002d39`
- name: `SaveErrorMessage`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
- callee_count: `4`
- tags: ``

## callers

- `0x140001e90`
- `0x14000263c`
- `0x140002a78`
- `0x1400031f4`
- `0x1400033d8`
- `0x1400038f8`
- `0x140003c24`
- `0x140003e34`
- `0x1400040b8`
- `0x14000426c`
- `0x14000456c`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140004e84`
- `0x140005910`
- `0x140005c78`
- `0x140005ef0`
- `0x1400061e4`
- `0x14000672c`
- `0x140006e6c`
- `0x1400073d4`
- `0x1400075ac`
- `0x14000799c`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x140008cbc`
- `0x1400090a8`
- `0x140009374`
- `0x14000957c`
- `0x140009c68`
- `0x140009f80`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000a4e4`
- `0x14000a6d8`
- `0x14000aa4c`

## callees

- `0x140002ce4`
- `0x14000d694`
- `0x14000e484`
- `0x14000e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002cec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d06`

## pseudocode

```c
__int64 __fastcall SaveErrorMessage(__int64 LastError)
{
  __int64 *ResString2FromModule; // rax

  if ( (int)LastError < 0 )
    LastError = GetLastError();
  if ( (_DWORD)LastError == 2 || (_DWORD)LastError == 3 )
  {
    ResString2FromModule = GetResString2FromModule(LastError, 0xBFu, 0);
    SetReason(ResString2FromModule);
  }
  else
  {
    SetLastError(LastError);
    SaveLastError();
  }
  return 1;
}

```

## disassembly

```asm
0x140002ce4  sub     rsp, 28h
0x140002ce8  test    ecx, ecx
0x140002cea  jns     short loc_140002CFA
0x140002cec  call    cs:__imp_GetLastError
0x140002cf3  nop     dword ptr [rax+rax+00h]
0x140002cf8  mov     ecx, eax; dwErrCode
0x140002cfa  mov     eax, ecx
0x140002cfc  sub     eax, 2
0x140002cff  jz      short loc_140002D19
0x140002d01  cmp     eax, 1
0x140002d04  jz      short loc_140002D19
0x140002d06  call    cs:__imp_SetLastError
0x140002d0d  nop     dword ptr [rax+rax+00h]
0x140002d12  call    SaveLastError
0x140002d17  jmp     short loc_140002D2E
0x140002d19  xor     r8d, r8d
0x140002d1c  mov     edx, 0BFh
0x140002d21  call    GetResString2FromModule
0x140002d26  mov     rcx, rax
0x140002d29  call    SetReason
0x140002d2e  mov     eax, 1
0x140002d33  add     rsp, 28h
0x140002d37  retn
```
