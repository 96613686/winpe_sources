# win_dox::CopyByteVector(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800c8424`
- end: `0x1800c84ec`
- name: `?CopyByteVector@win_dox@@YAPEAEAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800c7ff0`
- `0x1800c8100`
- `0x1800c8210`
- `0x1800c8320`

## callees

- `0x18002db70`
- `0x1800c8424`
- `0x1800cd6fc`
- `0x1800d6348`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8461`

## string_xrefs

- `0x1800c846f`: `Unable to copy buffer`

## pseudocode

```c
void *__fastcall win_dox::CopyByteVector(__int64 a1)
{
  SIZE_T v2; // rbx
  void *v3; // rax
  void *v4; // rdi
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  if ( *(_QWORD *)(a1 + 8) )
    v2 = *(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8);
  else
    v2 = 0;
  v3 = CoTaskMemAlloc(v2);
  v4 = v3;
  if ( !v3 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1Eu,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy buffer");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memcpy_0(v3, *(const void **)(a1 + 8), v2);
  return v4;
}

```

## disassembly

```asm
0x1800c8424  mov     [rsp+arg_8], rbx
0x1800c8429  mov     [rsp+arg_10], rsi
0x1800c842e  push    rdi
0x1800c842f  sub     rsp, 0F0h
0x1800c8436  mov     rax, cs:__security_cookie
0x1800c843d  xor     rax, rsp
0x1800c8440  mov     [rsp+0F8h+var_18], rax
0x1800c8448  cmp     qword ptr [rcx+8], 0
0x1800c844d  mov     rsi, rcx
0x1800c8450  jnz     short loc_1800C8456
0x1800c8452  xor     ebx, ebx
0x1800c8454  jmp     short loc_1800C845E
0x1800c8456  mov     rbx, [rcx+10h]
0x1800c845a  sub     rbx, [rcx+8]
0x1800c845e  mov     rcx, rbx; cb
0x1800c8461  call    cs:__imp_CoTaskMemAlloc
0x1800c8467  mov     rdi, rax
0x1800c846a  test    rax, rax
0x1800c846d  jnz     short loc_1800C84B5
0x1800c846f  lea     rax, aUnableToCopyBu; "Unable to copy buffer"
0x1800c8476  mov     [rsp+0F8h+var_C8], rax; struct win_musl::TStringEllipseBase *
0x1800c847b  lea     r9, word_180139126
0x1800c8482  mov     [rsp+0F8h+var_D0], 8007000Eh; unsigned int
0x1800c848a  lea     r8, aNoFilename; "(no filename)"
0x1800c8491  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800c8496  mov     [rsp+0F8h+var_D8], 1Eh; unsigned int
0x1800c849e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c84a3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c84aa  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800c84af  call    _CxxThrowException_0
0x1800c84b5  mov     rdx, [rsi+8]; Src
0x1800c84b9  mov     r8, rbx; Size
0x1800c84bc  mov     rcx, rdi; void *
0x1800c84bf  call    memcpy_0
0x1800c84c4  mov     rax, rdi
0x1800c84c7  mov     rcx, [rsp+0F8h+var_18]
0x1800c84cf  xor     rcx, rsp; StackCookie
0x1800c84d2  call    __security_check_cookie
0x1800c84d7  lea     r11, [rsp+0F8h+var_8]
0x1800c84df  mov     rbx, [r11+18h]
0x1800c84e3  mov     rsi, [r11+20h]
0x1800c84e7  mov     rsp, r11
0x1800c84ea  pop     rdi
0x1800c84eb  retn
```
