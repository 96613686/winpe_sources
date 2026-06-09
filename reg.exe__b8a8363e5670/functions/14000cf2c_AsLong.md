# AsLong

- ea: `0x14000cf2c`
- end: `0x14000d050`
- name: `AsLong`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400056ec`
- `0x14000672c`
- `0x140006e6c`

## callees

- `0x14000cf2c`
- `0x14000d900`
- `0x14000dab0`
- `0x14000f15c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000cfb5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000cff4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000cfb5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000cff4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000cfd8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000cfd8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000cfe6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000cfe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d036`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d036`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000cfa5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d00f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000cfa5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d00f`

## pseudocode

```c
__int64 __fastcall AsLong(WCHAR *a1, int a2)
{
  WCHAR *TempBuffer; // rax
  const wchar_t *v5; // rbx
  DWORD v6; // ecx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  wchar_t *EndPtr; // [rsp+40h] [rbp+18h] BYREF

  EndPtr = 0;
  if ( (unsigned int)(a2 - 2) <= 0x22 && a1 )
  {
    if ( !(unsigned int)InitGlobals() )
      return 0;
    TempBuffer = (WCHAR *)GetTempBuffer(0, a1, 0, 0);
    v5 = TempBuffer;
    if ( !TempBuffer )
    {
      if ( !GetLastError() )
      {
        v6 = 8;
LABEL_17:
        SetLastError(v6);
        return 0;
      }
      return 0;
    }
    TrimString2(TempBuffer);
    if ( lstrlenW(v5) )
    {
      *(_DWORD *)_o__errno() = 0;
      v7 = *v5 == 45 ? wcstol(v5, &EndPtr, a2) : wcstoul(v5, &EndPtr, a2);
      v8 = v7;
      if ( *(_DWORD *)_o__errno() != 34 && (!EndPtr || !lstrlenW(EndPtr)) )
        return v8;
    }
  }
  if ( !GetLastError() )
  {
    v6 = 87;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x14000cf2c  mov     [rsp+arg_0], rbx
0x14000cf31  push    rdi
0x14000cf32  sub     rsp, 20h
0x14000cf36  lea     eax, [rdx-2]
0x14000cf39  mov     [rsp+28h+EndPtr], 0
0x14000cf42  mov     edi, edx
0x14000cf44  mov     rbx, rcx
0x14000cf47  cmp     eax, 22h ; '"'
0x14000cf4a  ja      loc_14000D023
0x14000cf50  test    rcx, rcx
0x14000cf53  jz      loc_14000D023
0x14000cf59  call    InitGlobals
0x14000cf5e  test    eax, eax
0x14000cf60  jz      loc_14000D042
0x14000cf66  xor     r9d, r9d
0x14000cf69  xor     r8d, r8d
0x14000cf6c  mov     rdx, rbx
0x14000cf6f  xor     ecx, ecx
0x14000cf71  call    GetTempBuffer
0x14000cf76  mov     rbx, rax
0x14000cf79  test    rax, rax
0x14000cf7c  jnz     short loc_14000CF9A
0x14000cf7e  call    cs:__imp_GetLastError
0x14000cf85  nop     dword ptr [rax+rax+00h]
0x14000cf8a  test    eax, eax
0x14000cf8c  jnz     loc_14000D042
0x14000cf92  lea     ecx, [rbx+8]
0x14000cf95  jmp     loc_14000D036
0x14000cf9a  mov     rcx, rbx; lpString
0x14000cf9d  call    TrimString2
0x14000cfa2  mov     rcx, rbx; lpString
0x14000cfa5  call    cs:__imp_lstrlenW
0x14000cfac  nop     dword ptr [rax+rax+00h]
0x14000cfb1  test    eax, eax
0x14000cfb3  jz      short loc_14000D023
0x14000cfb5  call    cs:__imp__o__errno
0x14000cfbc  nop     dword ptr [rax+rax+00h]
0x14000cfc1  mov     r8d, edi; Radix
0x14000cfc4  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x14000cfc9  mov     rcx, rbx; String
0x14000cfcc  mov     dword ptr [rax], 0
0x14000cfd2  cmp     word ptr [rbx], 2Dh ; '-'
0x14000cfd6  jnz     short loc_14000CFE6
0x14000cfd8  call    cs:__imp_wcstol
0x14000cfdf  nop     dword ptr [rax+rax+00h]
0x14000cfe4  jmp     short loc_14000CFF2
0x14000cfe6  call    cs:__imp_wcstoul
0x14000cfed  nop     dword ptr [rax+rax+00h]
0x14000cff2  mov     ebx, eax
0x14000cff4  call    cs:__imp__o__errno
0x14000cffb  nop     dword ptr [rax+rax+00h]
0x14000d000  cmp     dword ptr [rax], 22h ; '"'
0x14000d003  jz      short loc_14000D023
0x14000d005  mov     rcx, [rsp+28h+EndPtr]; lpString
0x14000d00a  test    rcx, rcx
0x14000d00d  jz      short loc_14000D01F
0x14000d00f  call    cs:__imp_lstrlenW
0x14000d016  nop     dword ptr [rax+rax+00h]
0x14000d01b  test    eax, eax
0x14000d01d  jnz     short loc_14000D023
0x14000d01f  mov     eax, ebx
0x14000d021  jmp     short loc_14000D044
0x14000d023  call    cs:__imp_GetLastError
0x14000d02a  nop     dword ptr [rax+rax+00h]
0x14000d02f  test    eax, eax
0x14000d031  jnz     short loc_14000D042
0x14000d033  lea     ecx, [rax+57h]; dwErrCode
0x14000d036  call    cs:__imp_SetLastError
0x14000d03d  nop     dword ptr [rax+rax+00h]
0x14000d042  xor     eax, eax
0x14000d044  mov     rbx, [rsp+28h+arg_0]
0x14000d049  add     rsp, 20h
0x14000d04d  pop     rdi
0x14000d04e  retn
```
