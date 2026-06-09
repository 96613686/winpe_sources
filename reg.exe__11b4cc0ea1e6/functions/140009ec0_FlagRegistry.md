# FlagRegistry

- ea: `0x140009ec0`
- end: `0x14000a09a`
- name: `FlagRegistry`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002b70`
- `0x140002f30`
- `0x140009ec0`
- `0x14000a0a0`
- `0x14000a3f8`
- `0x14000dbe8`
- `0x14000dc24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009faa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009faa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a003`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a059`

## pseudocode

```c
__int64 __fastcall FlagRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // esi
  REGSAM v6; // r9d
  unsigned int v7; // eax
  unsigned int v8; // ebx
  FILE *v9; // rax
  unsigned int SetFlags; // r14d
  FILE *v12; // rax
  FILE *v13; // rax
  int v14; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v16[4]; // [rsp+40h] [rbp-69h] BYREF
  int v17; // [rsp+44h] [rbp-65h]
  HKEY hKey; // [rsp+48h] [rbp-61h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-19h]
  const WCHAR *v20; // [rsp+98h] [rbp-11h]
  int v21; // [rsp+C8h] [rbp+1Fh]
  int v22; // [rsp+CCh] [rbp+23h]

  v14 = 0;
  v17 = 0;
  memset_0(v16, 0, 0x94u);
  phkResult = 0;
  if ( a1 && a2 )
  {
    InitGlobalData(11, v16);
    if ( !(unsigned int)ParseFlagsCmdLine(a1, a2, v16, &v14) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_12:
      FreeGlobalData(v16);
      return v5;
    }
    if ( v14 == 1 )
    {
      Usage(11);
      v5 = 0;
      goto LABEL_12;
    }
    if ( v21 )
      v6 = v22 | 0xF003F;
    else
      v6 = v22 | 0x20019;
    v7 = RegOpenKeyExW(hKey, lpSubKey, 0, v6, &phkResult);
    v8 = v7;
    if ( v7 )
    {
      SaveErrorMessage(v7);
      v9 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v9);
      v5 = v8;
      goto LABEL_12;
    }
    SetFlags = QuerySetFlags(phkResult, v20, (__int64)v16);
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    FreeGlobalData(v16);
    SaveErrorMessage(SetFlags);
    v12 = o___acrt_iob_func_0((unsigned int)(SetFlags != 0) + 1);
    ShowLastErrorEx(v12);
    return SetFlags != 0;
  }
  else
  {
    SetLastError(0x57u);
    v13 = o___acrt_iob_func_0(2u);
    ShowLastError(v13);
    return 1;
  }
}

```

## disassembly

```asm
0x140009ec0  mov     [rsp-8+arg_0], rbx
0x140009ec5  mov     [rsp-8+arg_10], rsi
0x140009eca  push    rbp
0x140009ecb  push    rdi
0x140009ecc  push    r14
0x140009ece  lea     rbp, [rsp-47h]
0x140009ed3  sub     rsp, 0F0h
0x140009eda  mov     rax, cs:__security_cookie
0x140009ee1  xor     rax, rsp
0x140009ee4  mov     [rbp+57h+var_20], rax
0x140009ee8  mov     rbx, rdx
0x140009eeb  mov     [rbp+57h+var_D0], 0
0x140009ef2  mov     edi, ecx
0x140009ef4  xor     eax, eax
0x140009ef6  xor     edx, edx; Val
0x140009ef8  mov     [rbp+57h+var_BC], eax
0x140009efb  lea     rcx, [rbp+57h+var_C0]; void *
0x140009eff  mov     r8d, 94h; Size
0x140009f05  call    memset_0
0x140009f0a  mov     [rbp+57h+var_C8], 0
0x140009f12  test    edi, edi
0x140009f14  jz      loc_14000A054
0x140009f1a  test    rbx, rbx
0x140009f1d  jz      loc_14000A054
0x140009f23  mov     r14d, 0Bh
0x140009f29  lea     rdx, [rbp+57h+var_C0]
0x140009f2d  mov     ecx, r14d
0x140009f30  call    InitGlobalData
0x140009f35  lea     r9, [rbp+57h+var_D0]
0x140009f39  mov     rdx, rbx
0x140009f3c  lea     r8, [rbp+57h+var_C0]
0x140009f40  mov     ecx, edi
0x140009f42  call    ParseFlagsCmdLine
0x140009f47  test    eax, eax
0x140009f49  jnz     short loc_140009F66
0x140009f4b  lea     ecx, [rax+2]; Ix
0x140009f4e  call    _o___acrt_iob_func_0
0x140009f53  mov     rcx, rax
0x140009f56  mov     edx, 20000h
0x140009f5b  call    ShowLastErrorEx
0x140009f60  lea     esi, [r14-0Ah]
0x140009f64  jmp     short loc_140009FD6
0x140009f66  mov     esi, 1
0x140009f6b  cmp     [rbp+57h+var_D0], esi
0x140009f6e  jnz     short loc_140009F7C
0x140009f70  mov     ecx, r14d
0x140009f73  call    Usage
0x140009f78  xor     esi, esi
0x140009f7a  jmp     short loc_140009FD6
0x140009f7c  mov     r9d, [rbp+57h+var_34]
0x140009f80  lea     rax, [rbp+57h+var_C8]
0x140009f84  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140009f88  xor     r8d, r8d; ulOptions
0x140009f8b  mov     rcx, [rbp+57h+hKey]; hKey
0x140009f8f  mov     [rsp+100h+phkResult], rax; phkResult
0x140009f94  cmp     [rbp+57h+var_38], r8d
0x140009f98  jnz     short loc_140009FA3
0x140009f9a  or      r9d, 20019h
0x140009fa1  jmp     short loc_140009FAA
0x140009fa3  or      r9d, 0F003Fh; samDesired
0x140009faa  call    cs:__imp_RegOpenKeyExW
0x140009fb0  mov     ebx, eax
0x140009fb2  test    eax, eax
0x140009fb4  jz      short loc_140009FE6
0x140009fb6  mov     ecx, eax
0x140009fb8  call    SaveErrorMessage
0x140009fbd  mov     ecx, 2; Ix
0x140009fc2  call    _o___acrt_iob_func_0
0x140009fc7  mov     rcx, rax
0x140009fca  mov     edx, 20001h
0x140009fcf  call    ShowLastErrorEx
0x140009fd4  mov     esi, ebx
0x140009fd6  lea     rcx, [rbp+57h+var_C0]
0x140009fda  call    FreeGlobalData
0x140009fdf  mov     eax, esi
0x140009fe1  jmp     loc_14000A076
0x140009fe6  mov     rdx, [rbp+57h+var_68]
0x140009fea  lea     r8, [rbp+57h+var_C0]
0x140009fee  mov     rcx, [rbp+57h+var_C8]
0x140009ff2  call    QuerySetFlags
0x140009ff7  mov     rcx, [rbp+57h+var_C8]; hKey
0x140009ffb  mov     r14d, eax
0x140009ffe  test    rcx, rcx
0x14000a001  jz      short loc_14000A011
0x14000a003  call    cs:__imp_RegCloseKey
0x14000a009  mov     [rbp+57h+var_C8], 0
0x14000a011  lea     rcx, [rbp+57h+var_C0]
0x14000a015  call    FreeGlobalData
0x14000a01a  xor     edi, edi
0x14000a01c  mov     ecx, r14d
0x14000a01f  test    r14d, r14d
0x14000a022  setnz   dil
0x14000a026  call    SaveErrorMessage
0x14000a02b  mov     eax, r14d
0x14000a02e  neg     eax
0x14000a030  sbb     ebx, ebx
0x14000a032  neg     ebx
0x14000a034  neg     r14d
0x14000a037  sbb     ecx, ecx
0x14000a039  neg     ecx
0x14000a03b  add     ecx, esi; Ix
0x14000a03d  call    _o___acrt_iob_func_0
0x14000a042  mov     rcx, rax
0x14000a045  lea     edx, [rbx+20000h]
0x14000a04b  call    ShowLastErrorEx
0x14000a050  mov     eax, edi
0x14000a052  jmp     short loc_14000A076
0x14000a054  mov     ecx, 57h ; 'W'; dwErrCode
0x14000a059  call    cs:__imp_SetLastError
0x14000a05f  mov     ecx, 2; Ix
0x14000a064  call    _o___acrt_iob_func_0
0x14000a069  mov     rcx, rax
0x14000a06c  call    ShowLastError
0x14000a071  mov     eax, 1
0x14000a076  mov     rcx, [rbp+57h+var_20]
0x14000a07a  xor     rcx, rsp; StackCookie
0x14000a07d  call    __security_check_cookie
0x14000a082  lea     r11, [rsp+100h+var_10]
0x14000a08a  mov     rbx, [r11+20h]
0x14000a08e  mov     rsi, [r11+30h]
0x14000a092  mov     rsp, r11
0x14000a095  pop     r14
0x14000a097  pop     rdi
0x14000a098  pop     rbp
0x14000a099  retn
```
