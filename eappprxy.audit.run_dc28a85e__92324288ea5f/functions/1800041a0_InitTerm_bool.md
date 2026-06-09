# InitTerm(bool)

- ea: `0x1800041a0`
- end: `0x180004203`
- name: `?InitTerm@@YAJ_N@Z`
- size: `99`
- prototype: `int(bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000607c`

## callees

- `0x1800041a0`
- `0x18000dc34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800041b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800041b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800041e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800041e9`

## pseudocode

```c
int __fastcall InitTerm(bool a1)
{
  int result; // eax

  if ( !a1 )
  {
    DeleteCriticalSection(&CriticalSection);
    return EapHost::EapError::InitEapErrorLocks(a1);
  }
  if ( InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x3E8u) )
    return EapHost::EapError::InitEapErrorLocks(a1);
  result = GetLastError();
  if ( !result )
    return EapHost::EapError::InitEapErrorLocks(a1);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800041a0  push    rbx
0x1800041a2  sub     rsp, 20h
0x1800041a6  mov     bl, cl
0x1800041a8  test    cl, cl
0x1800041aa  lea     rcx, CriticalSection; lpCriticalSection
0x1800041b1  jz      short loc_1800041E9
0x1800041b3  mov     edx, 3E8h; dwSpinCount
0x1800041b8  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800041bf  nop     dword ptr [rax+rax+00h]
0x1800041c4  test    eax, eax
0x1800041c6  jnz     short loc_1800041F5
0x1800041c8  call    cs:__imp_GetLastError
0x1800041cf  nop     dword ptr [rax+rax+00h]
0x1800041d4  test    eax, eax
0x1800041d6  jz      short loc_1800041F5
0x1800041d8  jle     short loc_1800041FC
0x1800041da  movzx   eax, ax
0x1800041dd  or      eax, 80070000h
0x1800041e2  add     rsp, 20h
0x1800041e6  pop     rbx
0x1800041e7  retn
0x1800041e9  call    cs:__imp_DeleteCriticalSection
0x1800041f0  nop     dword ptr [rax+rax+00h]
0x1800041f5  mov     cl, bl; bool
0x1800041f7  call    ?InitEapErrorLocks@EapError@EapHost@@SAJ_N@Z; EapHost::EapError::InitEapErrorLocks(bool)
0x1800041fc  add     rsp, 20h
0x180004200  pop     rbx
0x180004201  retn
```
