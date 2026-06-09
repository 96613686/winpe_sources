# IsNumeric

- ea: `0x14000d4cc`
- end: `0x14000d5bd`
- name: `IsNumeric`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400053e0`
- `0x140006394`
- `0x140006a5c`

## callees

- `0x14000cf88`
- `0x14000d4cc`
- `0x14000e4e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d548`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d572`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d548`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d572`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000d564`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000d564`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000d56c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000d56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d5a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d5a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d534`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d587`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d534`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d587`

## pseudocode

```c
__int64 __fastcall IsNumeric(WCHAR *a1, int a2, int a3)
{
  WCHAR *TempBuffer; // rax
  const wchar_t *v6; // rbx
  DWORD v7; // ecx
  wchar_t *EndPtr; // [rsp+48h] [rbp+20h] BYREF

  EndPtr = 0;
  if ( (unsigned int)(a2 - 2) <= 0x22 && a1 )
  {
    TempBuffer = (WCHAR *)GetTempBuffer(0, a1, 0, 0);
    v6 = TempBuffer;
    if ( TempBuffer )
    {
      TrimString2(TempBuffer);
      if ( lstrlenW(v6) && (a3 || *v6 != 45) )
      {
        *(_DWORD *)_o__errno() = 0;
        if ( a3 == 1 )
          wcstol(v6, &EndPtr, a2);
        else
          wcstoul(v6, &EndPtr, a2);
        if ( *(_DWORD *)_o__errno() != 34 && (!EndPtr || !lstrlenW(EndPtr)) )
          return 1;
      }
    }
    else if ( !GetLastError() )
    {
      v7 = 8;
LABEL_18:
      SetLastError(v7);
    }
  }
  else if ( !GetLastError() )
  {
    v7 = 87;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d4cc  mov     [rsp+arg_0], rbx
0x14000d4d1  mov     [rsp+arg_8], rsi
0x14000d4d6  push    rdi
0x14000d4d7  sub     rsp, 20h
0x14000d4db  lea     eax, [rdx-2]
0x14000d4de  mov     [rsp+28h+EndPtr], 0
0x14000d4e7  mov     esi, r8d
0x14000d4ea  mov     edi, edx
0x14000d4ec  cmp     eax, 22h ; '"'
0x14000d4ef  ja      loc_14000D598
0x14000d4f5  test    rcx, rcx
0x14000d4f8  jz      loc_14000D598
0x14000d4fe  mov     rdx, rcx
0x14000d501  xor     r9d, r9d
0x14000d504  xor     ecx, ecx
0x14000d506  xor     r8d, r8d
0x14000d509  call    GetTempBuffer
0x14000d50e  mov     rbx, rax
0x14000d511  test    rax, rax
0x14000d514  jnz     short loc_14000D529
0x14000d516  call    cs:__imp_GetLastError
0x14000d51c  test    eax, eax
0x14000d51e  jnz     loc_14000D5AB
0x14000d524  lea     ecx, [rbx+8]
0x14000d527  jmp     short loc_14000D5A5
0x14000d529  mov     rcx, rbx; lpString
0x14000d52c  call    TrimString2
0x14000d531  mov     rcx, rbx; lpString
0x14000d534  call    cs:__imp_lstrlenW
0x14000d53a  test    eax, eax
0x14000d53c  jz      short loc_14000D5AB
0x14000d53e  test    esi, esi
0x14000d540  jnz     short loc_14000D548
0x14000d542  cmp     word ptr [rbx], 2Dh ; '-'
0x14000d546  jz      short loc_14000D5AB
0x14000d548  call    cs:__imp__o__errno
0x14000d54e  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x14000d553  mov     r8d, edi; Radix
0x14000d556  mov     rcx, rbx; String
0x14000d559  mov     dword ptr [rax], 0
0x14000d55f  cmp     esi, 1
0x14000d562  jnz     short loc_14000D56C
0x14000d564  call    cs:__imp_wcstol
0x14000d56a  jmp     short loc_14000D572
0x14000d56c  call    cs:__imp_wcstoul
0x14000d572  call    cs:__imp__o__errno
0x14000d578  cmp     dword ptr [rax], 22h ; '"'
0x14000d57b  jz      short loc_14000D5AB
0x14000d57d  mov     rcx, [rsp+28h+EndPtr]; lpString
0x14000d582  test    rcx, rcx
0x14000d585  jz      short loc_14000D591
0x14000d587  call    cs:__imp_lstrlenW
0x14000d58d  test    eax, eax
0x14000d58f  jnz     short loc_14000D5AB
0x14000d591  mov     eax, 1
0x14000d596  jmp     short loc_14000D5AD
0x14000d598  call    cs:__imp_GetLastError
0x14000d59e  test    eax, eax
0x14000d5a0  jnz     short loc_14000D5AB
0x14000d5a2  lea     ecx, [rax+57h]; dwErrCode
0x14000d5a5  call    cs:__imp_SetLastError
0x14000d5ab  xor     eax, eax
0x14000d5ad  mov     rbx, [rsp+28h+arg_0]
0x14000d5b2  mov     rsi, [rsp+28h+arg_8]
0x14000d5b7  add     rsp, 20h
0x14000d5bb  pop     rdi
0x14000d5bc  retn
```
