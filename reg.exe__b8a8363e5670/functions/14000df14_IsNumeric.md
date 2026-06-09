# IsNumeric

- ea: `0x14000df14`
- end: `0x14000e047`
- name: `IsNumeric`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400056ec`
- `0x14000672c`
- `0x140006e6c`

## callees

- `0x14000d900`
- `0x14000df14`
- `0x14000f15c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dfa7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dfe3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dfa7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dfe3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000dfc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000dfc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000dfd7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000dfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e028`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000df85`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dffe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000df85`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dffe`

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
0x14000df14  mov     [rsp+arg_0], rbx
0x14000df19  mov     [rsp+arg_8], rsi
0x14000df1e  push    rdi
0x14000df1f  sub     rsp, 20h
0x14000df23  lea     eax, [rdx-2]
0x14000df26  mov     [rsp+28h+EndPtr], 0
0x14000df2f  mov     esi, r8d
0x14000df32  mov     edi, edx
0x14000df34  cmp     eax, 22h ; '"'
0x14000df37  ja      loc_14000E015
0x14000df3d  test    rcx, rcx
0x14000df40  jz      loc_14000E015
0x14000df46  mov     rdx, rcx
0x14000df49  xor     r9d, r9d
0x14000df4c  xor     ecx, ecx
0x14000df4e  xor     r8d, r8d
0x14000df51  call    GetTempBuffer
0x14000df56  mov     rbx, rax
0x14000df59  test    rax, rax
0x14000df5c  jnz     short loc_14000DF7A
0x14000df5e  call    cs:__imp_GetLastError
0x14000df65  nop     dword ptr [rax+rax+00h]
0x14000df6a  test    eax, eax
0x14000df6c  jnz     loc_14000E034
0x14000df72  lea     ecx, [rbx+8]
0x14000df75  jmp     loc_14000E028
0x14000df7a  mov     rcx, rbx; lpString
0x14000df7d  call    TrimString2
0x14000df82  mov     rcx, rbx; lpString
0x14000df85  call    cs:__imp_lstrlenW
0x14000df8c  nop     dword ptr [rax+rax+00h]
0x14000df91  test    eax, eax
0x14000df93  jz      loc_14000E034
0x14000df99  test    esi, esi
0x14000df9b  jnz     short loc_14000DFA7
0x14000df9d  cmp     word ptr [rbx], 2Dh ; '-'
0x14000dfa1  jz      loc_14000E034
0x14000dfa7  call    cs:__imp__o__errno
0x14000dfae  nop     dword ptr [rax+rax+00h]
0x14000dfb3  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x14000dfb8  mov     r8d, edi; Radix
0x14000dfbb  mov     rcx, rbx; String
0x14000dfbe  mov     dword ptr [rax], 0
0x14000dfc4  cmp     esi, 1
0x14000dfc7  jnz     short loc_14000DFD7
0x14000dfc9  call    cs:__imp_wcstol
0x14000dfd0  nop     dword ptr [rax+rax+00h]
0x14000dfd5  jmp     short loc_14000DFE3
0x14000dfd7  call    cs:__imp_wcstoul
0x14000dfde  nop     dword ptr [rax+rax+00h]
0x14000dfe3  call    cs:__imp__o__errno
0x14000dfea  nop     dword ptr [rax+rax+00h]
0x14000dfef  cmp     dword ptr [rax], 22h ; '"'
0x14000dff2  jz      short loc_14000E034
0x14000dff4  mov     rcx, [rsp+28h+EndPtr]; lpString
0x14000dff9  test    rcx, rcx
0x14000dffc  jz      short loc_14000E00E
0x14000dffe  call    cs:__imp_lstrlenW
0x14000e005  nop     dword ptr [rax+rax+00h]
0x14000e00a  test    eax, eax
0x14000e00c  jnz     short loc_14000E034
0x14000e00e  mov     eax, 1
0x14000e013  jmp     short loc_14000E036
0x14000e015  call    cs:__imp_GetLastError
0x14000e01c  nop     dword ptr [rax+rax+00h]
0x14000e021  test    eax, eax
0x14000e023  jnz     short loc_14000E034
0x14000e025  lea     ecx, [rax+57h]; dwErrCode
0x14000e028  call    cs:__imp_SetLastError
0x14000e02f  nop     dword ptr [rax+rax+00h]
0x14000e034  xor     eax, eax
0x14000e036  mov     rbx, [rsp+28h+arg_0]
0x14000e03b  mov     rsi, [rsp+28h+arg_8]
0x14000e040  add     rsp, 20h
0x14000e044  pop     rdi
0x14000e045  retn
```
