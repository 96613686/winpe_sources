# CWMIContext::GetUserThreadLocale(void)

- ea: `0x18000b650`
- end: `0x18000b725`
- name: `?GetUserThreadLocale@CWMIContext@@UEAAKXZ`
- size: `213`
- prototype: `unsigned int __fastcall(CWMIContext *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b650`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b6cd`
- `KERNEL32!GetLastError` at `0x18000b6cd`
- `KERNEL32!LocaleNameToLCID` at `0x18000b6b8`
- `KERNEL32!LocaleNameToLCID` at `0x18000b6b8`
- `KERNEL32!GetThreadLocale` at `0x18000b677`
- `KERNEL32!GetThreadLocale` at `0x18000b677`

## pseudocode

```c
__int64 __fastcall CWMIContext::GetUserThreadLocale(CWMIContext *this)
{
  LCID ThreadLocale; // eax
  __int64 v3; // r9
  LCID v4; // esi
  unsigned int v5; // eax
  __int64 v6; // r8
  LCID v7; // eax
  void (__fastcall *v8)(CWMIContext *, const wchar_t *, __int64); // rbx
  __int64 LastError; // r8
  WCHAR Name[128]; // [rsp+20h] [rbp-118h] BYREF

  ThreadLocale = GetThreadLocale();
  v3 = *((_QWORD *)this + 3);
  Name[0] = 0;
  v4 = ThreadLocale;
  if ( !v3 || !*(_QWORD *)v3 )
  {
    v6 = 4;
    goto LABEL_8;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, WCHAR *))(*(_QWORD *)v3 + 72LL))(v3, 0, Name);
  v6 = v5;
  if ( v5 )
  {
LABEL_8:
    (*(void (__fastcall **)(CWMIContext *, const wchar_t *, __int64))(*(_QWORD *)this + 16LL))(
      this,
      L"MI_GetLocale failed with error %d",
      v6);
    return v4;
  }
  v7 = LocaleNameToLCID(Name, 0);
  if ( v7 )
  {
    return v7;
  }
  else
  {
    v8 = *(void (__fastcall **)(CWMIContext *, const wchar_t *, __int64))(*(_QWORD *)this + 16LL);
    LastError = GetLastError();
    v8(this, L"LocaleNameToLCID failed with error %d", LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b650  mov     [rsp+arg_8], rbx
0x18000b655  mov     [rsp+arg_10], rsi
0x18000b65a  push    rdi
0x18000b65b  sub     rsp, 130h
0x18000b662  mov     rax, cs:__security_cookie
0x18000b669  xor     rax, rsp
0x18000b66c  mov     [rsp+138h+var_18], rax
0x18000b674  mov     rdi, rcx
0x18000b677  call    cs:__imp_GetThreadLocale
0x18000b67d  mov     r9, [rdi+18h]
0x18000b681  xor     ecx, ecx
0x18000b683  mov     [rsp+138h+Name], cx
0x18000b688  mov     esi, eax
0x18000b68a  test    r9, r9
0x18000b68d  jz      short loc_18000B6E2
0x18000b68f  mov     rax, [r9]
0x18000b692  test    rax, rax
0x18000b695  jz      short loc_18000B6E2
0x18000b697  mov     rax, [rax+48h]
0x18000b69b  lea     r8, [rsp+138h+Name]
0x18000b6a0  xor     edx, edx
0x18000b6a2  mov     rcx, r9
0x18000b6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6aa  mov     r8d, eax
0x18000b6ad  test    eax, eax
0x18000b6af  jnz     short loc_18000B6E8
0x18000b6b1  xor     edx, edx; dwFlags
0x18000b6b3  lea     rcx, [rsp+138h+Name]; lpName
0x18000b6b8  call    cs:__imp_LocaleNameToLCID
0x18000b6be  test    eax, eax
0x18000b6c0  jz      short loc_18000B6C6
0x18000b6c2  mov     esi, eax
0x18000b6c4  jmp     short loc_18000B6FE
0x18000b6c6  mov     rax, [rdi]
0x18000b6c9  mov     rbx, [rax+10h]
0x18000b6cd  call    cs:__imp_GetLastError
0x18000b6d3  mov     r8d, eax
0x18000b6d6  lea     rdx, aLocalenametolc; "LocaleNameToLCID failed with error %d"
0x18000b6dd  mov     rax, rbx
0x18000b6e0  jmp     short loc_18000B6F6
0x18000b6e2  mov     r8d, 4
0x18000b6e8  mov     rax, [rdi]
0x18000b6eb  lea     rdx, aMiGetlocaleFai; "MI_GetLocale failed with error %d"
0x18000b6f2  mov     rax, [rax+10h]
0x18000b6f6  mov     rcx, rdi
0x18000b6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6fe  mov     eax, esi
0x18000b700  mov     rcx, [rsp+138h+var_18]
0x18000b708  xor     rcx, rsp; StackCookie
0x18000b70b  call    __security_check_cookie
0x18000b710  lea     r11, [rsp+138h+var_8]
0x18000b718  mov     rbx, [r11+18h]
0x18000b71c  mov     rsi, [r11+20h]
0x18000b720  mov     rsp, r11
0x18000b723  pop     rdi
0x18000b724  retn
```
