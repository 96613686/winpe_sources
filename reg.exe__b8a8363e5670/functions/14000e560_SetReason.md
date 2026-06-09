# SetReason

- ea: `0x14000e560`
- end: `0x14000e5f8`
- name: `SetReason`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140002ce4`
- `0x1400031f4`
- `0x1400038f8`
- `0x1400075ac`
- `0x140007cbc`
- `0x140008cbc`
- `0x140009c68`
- `0x140009f80`
- `0x14000a0e0`
- `0x14000a6d8`
- `0x14000e484`
- `0x14000e600`

## callees

- `0x14000dab0`
- `0x14000e560`
- `0x14000f638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e593`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e593`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5e5`

## pseudocode

```c
__int64 __fastcall SetReason(const WCHAR *a1)
{
  DWORD LastError; // edi
  DWORD v3; // ecx

  LastError = GetLastError();
  if ( !a1 )
  {
    if ( GetLastError() )
      return 0;
    v3 = 87;
LABEL_4:
    SetLastError(v3);
    return 0;
  }
  if ( !(unsigned int)InitGlobals() )
    return 0;
  if ( !(unsigned int)DynArraySetString(qword_140015218, 0, a1, 0) )
  {
    if ( GetLastError() )
      return 0;
    v3 = 8;
    goto LABEL_4;
  }
  SetLastError(LastError);
  return 1;
}

```

## disassembly

```asm
0x14000e560  mov     [rsp+arg_0], rbx
0x14000e565  push    rdi
0x14000e566  sub     rsp, 20h
0x14000e56a  mov     rbx, rcx
0x14000e56d  call    cs:__imp_GetLastError
0x14000e574  nop     dword ptr [rax+rax+00h]
0x14000e579  mov     edi, eax
0x14000e57b  test    rbx, rbx
0x14000e57e  jnz     short loc_14000E5AD
0x14000e580  call    cs:__imp_GetLastError
0x14000e587  nop     dword ptr [rax+rax+00h]
0x14000e58c  test    eax, eax
0x14000e58e  jnz     short loc_14000E59F
0x14000e590  lea     ecx, [rbx+57h]; dwErrCode
0x14000e593  call    cs:__imp_SetLastError
0x14000e59a  nop     dword ptr [rax+rax+00h]
0x14000e59f  xor     eax, eax
0x14000e5a1  mov     rbx, [rsp+28h+arg_0]
0x14000e5a6  add     rsp, 20h
0x14000e5aa  pop     rdi
0x14000e5ab  retn
0x14000e5ad  call    InitGlobals
0x14000e5b2  test    eax, eax
0x14000e5b4  jz      short loc_14000E59F
0x14000e5b6  mov     rcx, cs:qword_140015218
0x14000e5bd  xor     r9d, r9d
0x14000e5c0  mov     r8, rbx
0x14000e5c3  xor     edx, edx
0x14000e5c5  call    DynArraySetString
0x14000e5ca  test    eax, eax
0x14000e5cc  jnz     short loc_14000E5E3
0x14000e5ce  call    cs:__imp_GetLastError
0x14000e5d5  nop     dword ptr [rax+rax+00h]
0x14000e5da  test    eax, eax
0x14000e5dc  jnz     short loc_14000E59F
0x14000e5de  lea     ecx, [rax+8]
0x14000e5e1  jmp     short loc_14000E593
0x14000e5e3  mov     ecx, edi; dwErrCode
0x14000e5e5  call    cs:__imp_SetLastError
0x14000e5ec  nop     dword ptr [rax+rax+00h]
0x14000e5f1  mov     eax, 1
0x14000e5f6  jmp     short loc_14000E5A1
```
