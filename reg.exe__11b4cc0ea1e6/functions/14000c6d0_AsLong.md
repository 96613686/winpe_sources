# AsLong

- ea: `0x14000c6d0`
- end: `0x14000c7b6`
- name: `AsLong`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400053e0`
- `0x140006394`
- `0x140006a5c`

## callees

- `0x14000c6d0`
- `0x14000cf88`
- `0x14000d114`
- `0x14000e4e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c746`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c773`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c746`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c773`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000c763`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000c763`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000c76b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14000c76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c796`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c7a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c7a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c73c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c788`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c73c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c788`

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
0x14000c6d0  mov     [rsp+arg_0], rbx
0x14000c6d5  push    rdi
0x14000c6d6  sub     rsp, 20h
0x14000c6da  lea     eax, [rdx-2]
0x14000c6dd  mov     [rsp+28h+EndPtr], 0
0x14000c6e6  mov     edi, edx
0x14000c6e8  mov     rbx, rcx
0x14000c6eb  cmp     eax, 22h ; '"'
0x14000c6ee  ja      loc_14000C796
0x14000c6f4  test    rcx, rcx
0x14000c6f7  jz      loc_14000C796
0x14000c6fd  call    InitGlobals
0x14000c702  test    eax, eax
0x14000c704  jz      loc_14000C7A9
0x14000c70a  xor     r9d, r9d
0x14000c70d  xor     r8d, r8d
0x14000c710  mov     rdx, rbx
0x14000c713  xor     ecx, ecx
0x14000c715  call    GetTempBuffer
0x14000c71a  mov     rbx, rax
0x14000c71d  test    rax, rax
0x14000c720  jnz     short loc_14000C731
0x14000c722  call    cs:__imp_GetLastError
0x14000c728  test    eax, eax
0x14000c72a  jnz     short loc_14000C7A9
0x14000c72c  lea     ecx, [rbx+8]
0x14000c72f  jmp     short loc_14000C7A3
0x14000c731  mov     rcx, rbx; lpString
0x14000c734  call    TrimString2
0x14000c739  mov     rcx, rbx; lpString
0x14000c73c  call    cs:__imp_lstrlenW
0x14000c742  test    eax, eax
0x14000c744  jz      short loc_14000C796
0x14000c746  call    cs:__imp__o__errno
0x14000c74c  mov     r8d, edi; Radix
0x14000c74f  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x14000c754  mov     rcx, rbx; String
0x14000c757  mov     dword ptr [rax], 0
0x14000c75d  cmp     word ptr [rbx], 2Dh ; '-'
0x14000c761  jnz     short loc_14000C76B
0x14000c763  call    cs:__imp_wcstol
0x14000c769  jmp     short loc_14000C771
0x14000c76b  call    cs:__imp_wcstoul
0x14000c771  mov     ebx, eax
0x14000c773  call    cs:__imp__o__errno
0x14000c779  cmp     dword ptr [rax], 22h ; '"'
0x14000c77c  jz      short loc_14000C796
0x14000c77e  mov     rcx, [rsp+28h+EndPtr]; lpString
0x14000c783  test    rcx, rcx
0x14000c786  jz      short loc_14000C792
0x14000c788  call    cs:__imp_lstrlenW
0x14000c78e  test    eax, eax
0x14000c790  jnz     short loc_14000C796
0x14000c792  mov     eax, ebx
0x14000c794  jmp     short loc_14000C7AB
0x14000c796  call    cs:__imp_GetLastError
0x14000c79c  test    eax, eax
0x14000c79e  jnz     short loc_14000C7A9
0x14000c7a0  lea     ecx, [rax+57h]; dwErrCode
0x14000c7a3  call    cs:__imp_SetLastError
0x14000c7a9  xor     eax, eax
0x14000c7ab  mov     rbx, [rsp+28h+arg_0]
0x14000c7b0  add     rsp, 20h
0x14000c7b4  pop     rdi
0x14000c7b5  retn
```
