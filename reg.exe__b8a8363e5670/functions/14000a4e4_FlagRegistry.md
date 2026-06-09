# FlagRegistry

- ea: `0x14000a4e4`
- end: `0x14000a6d1`
- name: `FlagRegistry`
- size: `493`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002ce4`
- `0x140003068`
- `0x14000a4e4`
- `0x14000a6d8`
- `0x14000aa4c`
- `0x14000e75c`
- `0x14000e798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a5ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a62d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a62d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a689`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a689`

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
  _WORD *v20; // [rsp+98h] [rbp-11h]
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
0x14000a4e4  mov     [rsp-8+arg_0], rbx
0x14000a4e9  mov     [rsp-8+arg_10], rsi
0x14000a4ee  push    rbp
0x14000a4ef  push    rdi
0x14000a4f0  push    r14
0x14000a4f2  lea     rbp, [rsp-47h]
0x14000a4f7  sub     rsp, 0F0h
0x14000a4fe  mov     rax, cs:__security_cookie
0x14000a505  xor     rax, rsp
0x14000a508  mov     [rbp+57h+var_20], rax
0x14000a50c  mov     rbx, rdx
0x14000a50f  mov     [rbp+57h+var_D0], 0
0x14000a516  mov     edi, ecx
0x14000a518  xor     eax, eax
0x14000a51a  xor     edx, edx; Val
0x14000a51c  mov     [rbp+57h+var_BC], eax
0x14000a51f  lea     rcx, [rbp+57h+var_C0]; void *
0x14000a523  mov     r8d, 94h; Size
0x14000a529  call    memset_0
0x14000a52e  mov     [rbp+57h+var_C8], 0
0x14000a536  test    edi, edi
0x14000a538  jz      loc_14000A684
0x14000a53e  test    rbx, rbx
0x14000a541  jz      loc_14000A684
0x14000a547  mov     r14d, 0Bh
0x14000a54d  lea     rdx, [rbp+57h+var_C0]
0x14000a551  mov     ecx, r14d
0x14000a554  call    InitGlobalData
0x14000a559  lea     r9, [rbp+57h+var_D0]
0x14000a55d  mov     rdx, rbx
0x14000a560  lea     r8, [rbp+57h+var_C0]
0x14000a564  mov     ecx, edi
0x14000a566  call    ParseFlagsCmdLine
0x14000a56b  test    eax, eax
0x14000a56d  jnz     short loc_14000A58A
0x14000a56f  lea     ecx, [rax+2]; Ix
0x14000a572  call    _o___acrt_iob_func_0
0x14000a577  mov     rcx, rax
0x14000a57a  mov     edx, 20000h
0x14000a57f  call    ShowLastErrorEx
0x14000a584  lea     esi, [r14-0Ah]
0x14000a588  jmp     short loc_14000A600
0x14000a58a  mov     esi, 1
0x14000a58f  cmp     [rbp+57h+var_D0], esi
0x14000a592  jnz     short loc_14000A5A0
0x14000a594  mov     ecx, r14d
0x14000a597  call    Usage
0x14000a59c  xor     esi, esi
0x14000a59e  jmp     short loc_14000A600
0x14000a5a0  mov     r9d, [rbp+57h+var_34]
0x14000a5a4  lea     rax, [rbp+57h+var_C8]
0x14000a5a8  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x14000a5ac  xor     r8d, r8d; ulOptions
0x14000a5af  mov     rcx, [rbp+57h+hKey]; hKey
0x14000a5b3  mov     [rsp+100h+phkResult], rax; phkResult
0x14000a5b8  cmp     [rbp+57h+var_38], r8d
0x14000a5bc  jnz     short loc_14000A5C7
0x14000a5be  or      r9d, 20019h
0x14000a5c5  jmp     short loc_14000A5CE
0x14000a5c7  or      r9d, 0F003Fh; samDesired
0x14000a5ce  call    cs:__imp_RegOpenKeyExW
0x14000a5d5  nop     dword ptr [rax+rax+00h]
0x14000a5da  mov     ebx, eax
0x14000a5dc  test    eax, eax
0x14000a5de  jz      short loc_14000A610
0x14000a5e0  mov     ecx, eax
0x14000a5e2  call    SaveErrorMessage
0x14000a5e7  mov     ecx, 2; Ix
0x14000a5ec  call    _o___acrt_iob_func_0
0x14000a5f1  mov     rcx, rax
0x14000a5f4  mov     edx, 20001h
0x14000a5f9  call    ShowLastErrorEx
0x14000a5fe  mov     esi, ebx
0x14000a600  lea     rcx, [rbp+57h+var_C0]
0x14000a604  call    FreeGlobalData
0x14000a609  mov     eax, esi
0x14000a60b  jmp     loc_14000A6AC
0x14000a610  mov     rdx, [rbp+57h+var_68]
0x14000a614  lea     r8, [rbp+57h+var_C0]
0x14000a618  mov     rcx, [rbp+57h+var_C8]
0x14000a61c  call    QuerySetFlags
0x14000a621  mov     rcx, [rbp+57h+var_C8]; hKey
0x14000a625  mov     r14d, eax
0x14000a628  test    rcx, rcx
0x14000a62b  jz      short loc_14000A641
0x14000a62d  call    cs:__imp_RegCloseKey
0x14000a634  nop     dword ptr [rax+rax+00h]
0x14000a639  mov     [rbp+57h+var_C8], 0
0x14000a641  lea     rcx, [rbp+57h+var_C0]
0x14000a645  call    FreeGlobalData
0x14000a64a  xor     edi, edi
0x14000a64c  mov     ecx, r14d
0x14000a64f  test    r14d, r14d
0x14000a652  setnz   dil
0x14000a656  call    SaveErrorMessage
0x14000a65b  mov     eax, r14d
0x14000a65e  neg     eax
0x14000a660  sbb     ebx, ebx
0x14000a662  neg     ebx
0x14000a664  neg     r14d
0x14000a667  sbb     ecx, ecx
0x14000a669  neg     ecx
0x14000a66b  add     ecx, esi; Ix
0x14000a66d  call    _o___acrt_iob_func_0
0x14000a672  mov     rcx, rax
0x14000a675  lea     edx, [rbx+20000h]
0x14000a67b  call    ShowLastErrorEx
0x14000a680  mov     eax, edi
0x14000a682  jmp     short loc_14000A6AC
0x14000a684  mov     ecx, 57h ; 'W'; dwErrCode
0x14000a689  call    cs:__imp_SetLastError
0x14000a690  nop     dword ptr [rax+rax+00h]
0x14000a695  mov     ecx, 2; Ix
0x14000a69a  call    _o___acrt_iob_func_0
0x14000a69f  mov     rcx, rax
0x14000a6a2  call    ShowLastError
0x14000a6a7  mov     eax, 1
0x14000a6ac  mov     rcx, [rbp+57h+var_20]
0x14000a6b0  xor     rcx, rsp; StackCookie
0x14000a6b3  call    __security_check_cookie
0x14000a6b8  lea     r11, [rsp+100h+var_10]
0x14000a6c0  mov     rbx, [r11+20h]
0x14000a6c4  mov     rsi, [r11+30h]
0x14000a6c8  mov     rsp, r11
0x14000a6cb  pop     r14
0x14000a6cd  pop     rdi
0x14000a6ce  pop     rbp
0x14000a6cf  retn
```
