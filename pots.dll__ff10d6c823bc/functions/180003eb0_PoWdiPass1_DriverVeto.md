# PoWdiPass1_DriverVeto

- ea: `0x180003eb0`
- end: `0x180003f78`
- name: `PoWdiPass1_DriverVeto`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800018a8`
- `0x1800022dc`
- `0x1800039b0`
- `0x180003eb0`
- `0x180004930`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180003f2f`
- `msvcrt!wcsrchr` at `0x180003f2f`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiPass1_DriverVeto(struct _EVENT_RECORD *a1, _DWORD *a2, __int64 a3)
{
  bool v3; // zf
  TDHSTATUS result; // eax
  unsigned __int64 v6; // rcx
  wchar_t *v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // [rsp+30h] [rbp-A8h] BYREF
  wchar_t Str[64]; // [rsp+40h] [rbp-98h] BYREF

  v3 = a2[2] == 0;
  LODWORD(v9) = 0;
  if ( v3 )
    a2[2] = 3;
  result = PoWdiGetProperty(a1, (ULONGLONG)L"DriverName", a3, (BYTE *)Str, 0x7Eu, (ULONG *)&v9);
  if ( !result && (unsigned int)v9 <= 0x7E )
  {
    v6 = (unsigned int)v9 & 0xFFFFFFFE;
    if ( v6 >= 0x80 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)Str + v6) = 0;
    v7 = wcsrchr(Str, 0x5Cu);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = Str;
    return PoWdiLogVetoTelemetry((unsigned int)a2[3], a2[1], 3, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180003eb0  push    rbx
0x180003eb2  sub     rsp, 0D0h
0x180003eb9  mov     rax, cs:__security_cookie
0x180003ec0  xor     rax, rsp
0x180003ec3  mov     [rsp+0D8h+var_18], rax
0x180003ecb  cmp     dword ptr [rdx+8], 0
0x180003ecf  mov     rbx, rdx
0x180003ed2  mov     dword ptr [rsp+0D8h+var_A8], 0
0x180003eda  jnz     short loc_180003EE3
0x180003edc  mov     dword ptr [rdx+8], 3
0x180003ee3  lea     rax, [rsp+0D8h+var_A8]
0x180003ee8  mov     [rsp+0D8h+var_B0], rax; __int64
0x180003eed  lea     r9, [rsp+0D8h+Str]
0x180003ef2  lea     rdx, aDrivername; "DriverName"
0x180003ef9  mov     [rsp+0D8h+var_B8], 7Eh ; '~'; int
0x180003f01  call    PoWdiGetProperty
0x180003f06  test    eax, eax
0x180003f08  jnz     short loc_180003F59
0x180003f0a  cmp     dword ptr [rsp+0D8h+var_A8], 7Eh ; '~'
0x180003f0f  ja      short loc_180003F59
0x180003f11  mov     ecx, dword ptr [rsp+0D8h+var_A8]
0x180003f15  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180003f19  cmp     rcx, 80h
0x180003f20  jnb     short loc_180003F72
0x180003f22  mov     [rsp+rcx+0D8h+Str], ax
0x180003f27  lea     edx, [rax+5Ch]; Ch
0x180003f2a  lea     rcx, [rsp+0D8h+Str]; Str
0x180003f2f  call    cs:__imp_wcsrchr
0x180003f35  test    rax, rax
0x180003f38  jz      short loc_180003F40
0x180003f3a  add     rax, 2
0x180003f3e  jmp     short loc_180003F45
0x180003f40  lea     rax, [rsp+0D8h+Str]
0x180003f45  mov     edx, [rbx+4]
0x180003f48  mov     r9, rax
0x180003f4b  mov     ecx, [rbx+0Ch]
0x180003f4e  mov     r8d, 3
0x180003f54  call    PoWdiLogVetoTelemetry
0x180003f59  mov     rcx, [rsp+0D8h+var_18]
0x180003f61  xor     rcx, rsp; StackCookie
0x180003f64  call    __security_check_cookie
0x180003f69  add     rsp, 0D0h
0x180003f70  pop     rbx
0x180003f71  retn
0x180003f72  call    __report_rangecheckfailure
```
