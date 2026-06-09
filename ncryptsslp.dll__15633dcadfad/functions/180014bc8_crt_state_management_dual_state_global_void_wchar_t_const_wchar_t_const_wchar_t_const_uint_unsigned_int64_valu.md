# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x180014bc8`
- end: `0x180014c0f`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014e3c`

## callees

- `0x180014bc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014bf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014bf2`

## pseudocode

```c
__int64 __fastcall __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
        __int64 a1,
        __int64 a2)
{
  DWORD LastError; // eax
  __int64 v5; // rax

  if ( *(_BYTE *)(a2 + 16) )
  {
    v5 = *(_QWORD *)(a2 + 8);
  }
  else
  {
    LastError = GetLastError();
    *(_QWORD *)(a2 + 8) = 0;
    *(_BYTE *)(a2 + 16) = 1;
    SetLastError(LastError);
    v5 = 0;
  }
  return a1 + 8 * v5;
}

```

## disassembly

```asm
0x180014bc8  mov     [rsp+arg_0], rbx
0x180014bcd  push    rdi
0x180014bce  sub     rsp, 20h
0x180014bd2  cmp     byte ptr [rdx+10h], 0
0x180014bd6  mov     rbx, rdx
0x180014bd9  mov     rdi, rcx
0x180014bdc  jnz     short loc_180014BFC
0x180014bde  call    cs:__imp_GetLastError
0x180014be4  mov     ecx, eax; dwErrCode
0x180014be6  mov     qword ptr [rbx+8], 0
0x180014bee  mov     byte ptr [rbx+10h], 1
0x180014bf2  call    cs:__imp_SetLastError
0x180014bf8  xor     eax, eax
0x180014bfa  jmp     short loc_180014C00
0x180014bfc  mov     rax, [rdx+8]
0x180014c00  mov     rbx, [rsp+28h+arg_0]
0x180014c05  lea     rax, [rdi+rax*8]
0x180014c09  add     rsp, 20h
0x180014c0d  pop     rdi
0x180014c0e  retn
```
