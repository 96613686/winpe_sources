# GetVersionFromProcess

- ea: `0x18002ff24`
- end: `0x18003005a`
- name: `GetVersionFromProcess`
- size: `310`
- prototype: `__int64 __fastcall(void *, wchar_t *Destination, rsize_t SizeInWords)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025920`

## callees

- `0x18000d264`
- `0x18002a7c8`
- `0x18002fa08`
- `0x18002fd30`
- `0x18002ff24`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x18002ffc6`
- `KERNEL32!ReadProcessMemory` at `0x18002ffc6`

## pseudocode

```c
__int64 __fastcall GetVersionFromProcess(void *a1, wchar_t *Destination, rsize_t SizeInWords, _DWORD *a4)
{
  rsize_t v4; // rbp
  __int64 result; // rax
  __int64 v9; // rax
  rsize_t v10; // rax
  unsigned __int8 *v11; // [rsp+30h] [rbp-268h] BYREF
  char *Buffer; // [rsp+38h] [rbp-260h] BYREF
  SIZE_T NumberOfBytesRead[2]; // [rsp+40h] [rbp-258h] BYREF
  wchar_t Source[264]; // [rsp+50h] [rbp-248h] BYREF

  v4 = (unsigned int)SizeInWords;
  if ( (Destination == 0) != ((_DWORD)SizeInWords == 0) )
    return 2147942487LL;
  v11 = 0;
  result = GetRemoteMscoreeBaseAddress(a1, &v11);
  if ( (int)result < 0 )
    return result;
  if ( !v11 )
    return 2147942487LL;
  Buffer = 0;
  NumberOfBytesRead[0] = 0;
  if ( !ReadProcessMemory(a1, (char *)&String1 + v11 - (unsigned __int8 *)g_hShimMod, &Buffer, 8u, NumberOfBytesRead) )
    return HRESULT_FROM_GetLastError();
  if ( !Buffer || !ReadRemoteUnicodeString(a1, Buffer, Source) )
    return 2147942487LL;
  v9 = -1;
  do
    ++v9;
  while ( Source[v9] );
  v10 = v9 + 1;
  if ( a4 )
    *a4 = v10;
  if ( v10 > v4 )
    return 2147942522LL;
  if ( Destination )
    wcsncpy_s(Destination, v4, Source, 0xFFFFFFFFFFFFFFFFuLL);
  return 0;
}

```

## disassembly

```asm
0x18002ff24  push    rbx
0x18002ff26  push    rbp
0x18002ff27  push    rsi
0x18002ff28  push    rdi
0x18002ff29  push    r14
0x18002ff2b  sub     rsp, 270h
0x18002ff32  mov     rax, cs:__security_cookie
0x18002ff39  xor     rax, rsp
0x18002ff3c  mov     [rsp+298h+var_38], rax
0x18002ff44  xor     r14d, r14d
0x18002ff47  mov     ebp, r8d
0x18002ff4a  test    r8d, r8d
0x18002ff4d  mov     rbx, rcx
0x18002ff50  mov     ecx, r14d
0x18002ff53  mov     eax, r14d
0x18002ff56  setz    cl
0x18002ff59  mov     rsi, r9
0x18002ff5c  test    rdx, rdx
0x18002ff5f  mov     rdi, rdx
0x18002ff62  setz    al
0x18002ff65  cmp     eax, ecx
0x18002ff67  jnz     loc_180030037
0x18002ff6d  lea     rdx, [rsp+298h+var_268]; unsigned __int8 **
0x18002ff72  mov     [rsp+298h+var_268], r14
0x18002ff77  mov     rcx, rbx; void *
0x18002ff7a  call    ?GetRemoteMscoreeBaseAddress@@YAJPEAXPEAPEAE@Z; GetRemoteMscoreeBaseAddress(void *,uchar * *)
0x18002ff7f  test    eax, eax
0x18002ff81  js      loc_18003003C
0x18002ff87  mov     rdx, [rsp+298h+var_268]
0x18002ff8c  test    rdx, rdx
0x18002ff8f  jz      loc_180030037
0x18002ff95  sub     rdx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimMod
0x18002ff9c  lea     rax, String1
0x18002ffa3  add     rdx, rax; lpBaseAddress
0x18002ffa6  mov     [rsp+298h+Buffer], r14
0x18002ffab  lea     rax, [rsp+298h+NumberOfBytesRead]
0x18002ffb0  mov     [rsp+298h+NumberOfBytesRead], r14
0x18002ffb5  lea     r9d, [r14+8]; nSize
0x18002ffb9  mov     [rsp+298h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18002ffbe  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x18002ffc3  mov     rcx, rbx; hProcess
0x18002ffc6  call    cs:__imp_ReadProcessMemory
0x18002ffcc  test    eax, eax
0x18002ffce  jnz     short loc_18002FFD7
0x18002ffd0  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002ffd5  jmp     short loc_18003003C
0x18002ffd7  mov     rdx, [rsp+298h+Buffer]; lpBaseAddress
0x18002ffdc  test    rdx, rdx
0x18002ffdf  jz      short loc_180030037
0x18002ffe1  lea     r8, [rsp+298h+Source]; lpBuffer
0x18002ffe6  mov     rcx, rbx; hProcess
0x18002ffe9  call    ?ReadRemoteUnicodeString@@YA_NPEAXPEAEPEAG_K@Z; ReadRemoteUnicodeString(void *,uchar *,ushort *,unsigned __int64)
0x18002ffee  test    al, al
0x18002fff0  jz      short loc_180030037
0x18002fff2  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002fff6  lea     rcx, [rsp+298h+Source]
0x18002fffb  mov     rax, r9
0x18002fffe  inc     rax
0x180030001  cmp     [rcx+rax*2], r14w
0x180030006  jnz     short loc_18002FFFE
0x180030008  inc     rax
0x18003000b  test    rsi, rsi
0x18003000e  jz      short loc_180030012
0x180030010  mov     [rsi], eax
0x180030012  mov     rdx, rbp; SizeInWords
0x180030015  cmp     rax, rbp
0x180030018  jbe     short loc_180030021
0x18003001a  mov     eax, 8007007Ah
0x18003001f  jmp     short loc_18003003C
0x180030021  test    rdi, rdi
0x180030024  jz      short loc_180030033
0x180030026  lea     r8, [rsp+298h+Source]; Source
0x18003002b  mov     rcx, rdi; Destination
0x18003002e  call    wcsncpy_s
0x180030033  xor     eax, eax
0x180030035  jmp     short loc_18003003C
0x180030037  mov     eax, 80070057h
0x18003003c  mov     rcx, [rsp+298h+var_38]
0x180030044  xor     rcx, rsp; StackCookie
0x180030047  call    __security_check_cookie
0x18003004c  add     rsp, 270h
0x180030053  pop     r14
0x180030055  pop     rdi
0x180030056  pop     rsi
0x180030057  pop     rbp
0x180030058  pop     rbx
0x180030059  retn
```
