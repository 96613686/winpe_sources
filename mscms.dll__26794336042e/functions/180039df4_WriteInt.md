# WriteInt

- ea: `0x180039df4`
- end: `0x180039e6d`
- name: `WriteInt`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1800306f0`
- `0x1800308a4`
- `0x180030ab8`
- `0x180031a00`
- `0x180031cd4`
- `0x180032dd8`
- `0x1800333e4`
- `0x180034f88`
- `0x180035f30`
- `0x180037340`
- `0x180038458`
- `0x180038b98`
- `0x180038f0c`

## callees

- `0x180039224`
- `0x180039df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e3f`

## pseudocode

```c
__int64 __fastcall WriteInt(STRSAFE_LPSTR *a1, _DWORD *a2, int a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  size_t v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = (unsigned int)*a2;
  if ( StringCchPrintfExA(*a1, v8, 0, &v8, 0x1000u, "%lu ", a3) >= 0 )
  {
    v5 = 1;
    v6 = v8;
    *a1 += (unsigned int)*a2 - v8;
    *a2 = v6;
  }
  else
  {
    v5 = 0;
    SetLastError(0x7Au);
  }
  return v5;
}

```

## disassembly

```asm
0x180039df4  mov     r11, rsp
0x180039df7  mov     [r11+8], rbx
0x180039dfb  mov     [r11+18h], rsi
0x180039dff  push    rdi
0x180039e00  sub     rsp, 40h
0x180039e04  mov     [r11-18h], r8d
0x180039e08  lea     rax, aLu; "%lu "
0x180039e0f  mov     rdi, rdx
0x180039e12  mov     [r11-20h], rax
0x180039e16  mov     edx, [rdx]; cchDest
0x180039e18  lea     r9, [r11+10h]; pcchRemaining
0x180039e1c  mov     rsi, rcx
0x180039e1f  mov     [r11+10h], rdx
0x180039e23  mov     rcx, [rcx]; pszDest
0x180039e26  xor     r8d, r8d; ppszDestEnd
0x180039e29  mov     [rsp+48h+dwFlags], 1000h; dwFlags
0x180039e31  call    StringCchPrintfExA
0x180039e36  test    eax, eax
0x180039e38  jns     short loc_180039E47
0x180039e3a  xor     ebx, ebx
0x180039e3c  lea     ecx, [rbx+7Ah]; dwErrCode
0x180039e3f  call    cs:__imp_SetLastError
0x180039e45  jmp     short loc_180039E5B
0x180039e47  mov     ecx, [rdi]
0x180039e49  mov     ebx, 1
0x180039e4e  mov     rdx, [rsp+48h+arg_8]
0x180039e53  sub     rcx, rdx
0x180039e56  add     [rsi], rcx
0x180039e59  mov     [rdi], edx
0x180039e5b  mov     rsi, [rsp+48h+arg_10]
0x180039e60  mov     eax, ebx
0x180039e62  mov     rbx, [rsp+48h+arg_0]
0x180039e67  add     rsp, 40h
0x180039e6b  pop     rdi
0x180039e6c  retn
```
