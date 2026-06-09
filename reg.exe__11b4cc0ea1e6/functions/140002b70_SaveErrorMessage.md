# SaveErrorMessage

- ea: `0x140002b70`
- end: `0x140002bb8`
- name: `SaveErrorMessage`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
- callee_count: `4`
- tags: ``

## callers

- `0x140001e90`
- `0x1400024a4`
- `0x140002940`
- `0x1400030b8`
- `0x14000329c`
- `0x14000375c`
- `0x140003a58`
- `0x140003c48`
- `0x140003ec4`
- `0x14000406c`
- `0x140004354`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140004bbc`
- `0x1400055f8`
- `0x140005940`
- `0x140005bac`
- `0x140005e84`
- `0x140006394`
- `0x140006a5c`
- `0x140006f9c`
- `0x140007170`
- `0x14000752c`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x140008788`
- `0x140008b4c`
- `0x140008dfc`
- `0x140008fe8`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ae4`
- `0x140009d40`
- `0x140009ec0`
- `0x14000a0a0`
- `0x14000a3f8`

## callees

- `0x140002b70`
- `0x14000cd48`
- `0x14000d978`
- `0x14000da24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b8c`

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
0x140002b70  sub     rsp, 28h
0x140002b74  test    ecx, ecx
0x140002b76  jns     short loc_140002B80
0x140002b78  call    cs:__imp_GetLastError
0x140002b7e  mov     ecx, eax; dwErrCode
0x140002b80  mov     eax, ecx
0x140002b82  sub     eax, 2
0x140002b85  jz      short loc_140002B99
0x140002b87  cmp     eax, 1
0x140002b8a  jz      short loc_140002B99
0x140002b8c  call    cs:__imp_SetLastError
0x140002b92  call    SaveLastError
0x140002b97  jmp     short loc_140002BAE
0x140002b99  xor     r8d, r8d
0x140002b9c  mov     edx, 0BFh
0x140002ba1  call    GetResString2FromModule
0x140002ba6  mov     rcx, rax
0x140002ba9  call    SetReason
0x140002bae  mov     eax, 1
0x140002bb3  add     rsp, 28h
0x140002bb7  retn
```
