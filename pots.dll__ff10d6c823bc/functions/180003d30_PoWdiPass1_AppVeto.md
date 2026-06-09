# PoWdiPass1_AppVeto

- ea: `0x180003d30`
- end: `0x180003dfa`
- name: `PoWdiPass1_AppVeto`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800018a8`
- `0x1800022dc`
- `0x1800039b0`
- `0x180003d30`
- `0x180004930`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180003db2`
- `msvcrt!wcsrchr` at `0x180003db2`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiPass1_AppVeto(struct _EVENT_RECORD *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  TDHSTATUS result; // eax
  unsigned __int64 v6; // rcx
  wchar_t *v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // [rsp+30h] [rbp-238h] BYREF
  wchar_t Str[264]; // [rsp+40h] [rbp-228h] BYREF

  v3 = *(_DWORD *)(a2 + 8) == 0;
  LODWORD(v9) = 0;
  if ( v3 )
    *(_DWORD *)(a2 + 8) = 3;
  result = PoWdiGetProperty(a1, (ULONGLONG)L"AppName", a3, (BYTE *)Str, 0x206u, (ULONG *)&v9);
  if ( !result && (unsigned int)v9 <= 0x206 )
  {
    v6 = (unsigned int)v9 & 0xFFFFFFFE;
    if ( v6 >= 0x208 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)Str + v6) = 0;
    v7 = wcsrchr(Str, 0x5Cu);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = Str;
    return PoWdiLogVetoTelemetry(0, *(_DWORD *)(a2 + 4), 1, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180003d30  push    rbx
0x180003d32  sub     rsp, 260h
0x180003d39  mov     rax, cs:__security_cookie
0x180003d40  xor     rax, rsp
0x180003d43  mov     [rsp+268h+var_18], rax
0x180003d4b  cmp     dword ptr [rdx+8], 0
0x180003d4f  mov     rbx, rdx
0x180003d52  mov     dword ptr [rsp+268h+var_238], 0
0x180003d5a  jnz     short loc_180003D63
0x180003d5c  mov     dword ptr [rdx+8], 3
0x180003d63  lea     rax, [rsp+268h+var_238]
0x180003d68  mov     [rsp+268h+var_240], rax; __int64
0x180003d6d  lea     r9, [rsp+268h+Str]
0x180003d72  lea     rdx, aAppname; "AppName"
0x180003d79  mov     [rsp+268h+var_248], 206h; int
0x180003d81  call    PoWdiGetProperty
0x180003d86  test    eax, eax
0x180003d88  jnz     short loc_180003DDB
0x180003d8a  cmp     dword ptr [rsp+268h+var_238], 206h
0x180003d92  ja      short loc_180003DDB
0x180003d94  mov     ecx, dword ptr [rsp+268h+var_238]
0x180003d98  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180003d9c  cmp     rcx, 208h
0x180003da3  jnb     short loc_180003DF4
0x180003da5  mov     [rsp+rcx+268h+Str], ax
0x180003daa  lea     edx, [rax+5Ch]; Ch
0x180003dad  lea     rcx, [rsp+268h+Str]; Str
0x180003db2  call    cs:__imp_wcsrchr
0x180003db8  test    rax, rax
0x180003dbb  jz      short loc_180003DC3
0x180003dbd  add     rax, 2
0x180003dc1  jmp     short loc_180003DC8
0x180003dc3  lea     rax, [rsp+268h+Str]
0x180003dc8  mov     edx, [rbx+4]
0x180003dcb  mov     r9, rax
0x180003dce  mov     r8d, 1
0x180003dd4  xor     ecx, ecx
0x180003dd6  call    PoWdiLogVetoTelemetry
0x180003ddb  mov     rcx, [rsp+268h+var_18]
0x180003de3  xor     rcx, rsp; StackCookie
0x180003de6  call    __security_check_cookie
0x180003deb  add     rsp, 260h
0x180003df2  pop     rbx
0x180003df3  retn
0x180003df4  call    __report_rangecheckfailure
```
