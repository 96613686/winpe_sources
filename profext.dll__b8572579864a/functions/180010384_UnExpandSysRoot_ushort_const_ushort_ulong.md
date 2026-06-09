# UnExpandSysRoot(ushort const *,ushort *,ulong)

- ea: `0x180010384`
- end: `0x180010543`
- name: `?UnExpandSysRoot@@YAHPEBGPEAGK@Z`
- size: `447`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180022610`

## callees

- `0x180002030`
- `0x180006400`
- `0x180006760`
- `0x180010384`
- `0x18001b914`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800104de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800104de`
- `ntdll!RtlNtStatusToDosError` at `0x1800103ff`
- `ntdll!RtlNtStatusToDosError` at `0x1800103ff`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800103f1`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800103f1`

## string_xrefs

- `0x180010428`: `onecore\ds\security\gina\profile\profext\setup.cpp`
- `0x180010495`: `onecore\ds\security\gina\profile\profext\setup.cpp`

## pseudocode

```c
__int64 __fastcall UnExpandSysRoot(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  NTSTATUS v5; // eax
  signed int v6; // eax
  bool v7; // sf
  __int64 v8; // rdx
  unsigned __int64 v10; // r9
  int v11; // eax
  unsigned __int64 v12; // r10
  unsigned __int64 v13; // rbp
  unsigned __int16 *v14; // rcx
  int v15; // eax
  unsigned __int64 v16[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = 0;
  if ( a1 && *a1 )
  {
    v16[0] = 0;
    v5 = RtlExpandEnvironmentStrings(0, L"%SystemRoot%", 12, String1);
    v6 = RtlNtStatusToDosError(v5);
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
    {
      v8 = 189;
LABEL_7:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
        (const char *)(unsigned int)v6,
        260);
      StringCchCopyW(a2, 0x104u, a1);
      return 0;
    }
    v16[0] = 0;
    v6 = StringCchLengthW(String1, 0x7FFFFFFFu, v16);
    if ( v6 < 0 )
    {
      v8 = 197;
      goto LABEL_7;
    }
    v11 = StringCchLengthW(a1, v10, v16);
    if ( v11 >= 0 )
    {
      v13 = v12;
      v2 = 1;
      if ( v16[0] >= v12 )
      {
        v15 = CompareStringOrdinal(String1, v12, a1, v12, 1);
        v14 = a2;
        if ( v15 == 2 )
        {
          StringCchCopyW(a2, 0x104u, L"%SystemRoot%");
          StringCchCatW(a2, 0x104u, &a1[v13]);
          return v2;
        }
LABEL_14:
        StringCchCopyW(v14, 0x104u, a1);
        return v2;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
        (const char *)(unsigned int)v11,
        260);
    }
    v14 = a2;
    goto LABEL_14;
  }
  *a2 = 0;
  return 1;
}

```

## disassembly

```asm
0x180010384  mov     [rsp+arg_10], rbx
0x180010389  mov     [rsp+arg_18], rbp
0x18001038e  push    rsi
0x18001038f  push    rdi
0x180010390  push    r14
0x180010392  sub     rsp, 260h
0x180010399  mov     rax, cs:__security_cookie
0x1800103a0  xor     rax, rsp
0x1800103a3  mov     [rsp+278h+var_28], rax
0x1800103ab  xor     ebx, ebx
0x1800103ad  mov     rsi, rdx
0x1800103b0  mov     rdi, rcx
0x1800103b3  test    rcx, rcx
0x1800103b6  jz      loc_180010512
0x1800103bc  cmp     [rcx], bx
0x1800103bf  jz      loc_180010512
0x1800103c5  lea     rax, [rsp+278h+var_248]
0x1800103ca  mov     [rsp+278h+var_248], rbx
0x1800103cf  mov     [rsp+278h+var_250], rax
0x1800103d4  lea     r9, [rsp+278h+String1]
0x1800103d9  mov     r14d, 104h
0x1800103df  lea     r8d, [rbx+0Ch]
0x1800103e3  lea     rdx, aSystemroot; "%SystemRoot%"
0x1800103ea  mov     qword ptr [rsp+278h+bIgnoreCase], r14; int
0x1800103ef  xor     ecx, ecx
0x1800103f1  call    cs:__imp_RtlExpandEnvironmentStrings
0x1800103f8  nop     dword ptr [rax+rax+00h]
0x1800103fd  mov     ecx, eax; Status
0x1800103ff  call    cs:__imp_RtlNtStatusToDosError
0x180010406  nop     dword ptr [rax+rax+00h]
0x18001040b  test    eax, eax
0x18001040d  jle     short loc_180010419
0x18001040f  movzx   eax, ax
0x180010412  or      eax, 80070000h
0x180010417  test    eax, eax
0x180010419  jns     short loc_18001044C
0x18001041b  mov     edx, 0BDh; void *
0x180010420  mov     rcx, [rsp+278h]; this
0x180010428  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001042f  mov     r9d, eax; char *
0x180010432  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010437  mov     r8, rdi; unsigned __int16 *
0x18001043a  mov     rdx, r14; unsigned __int64
0x18001043d  mov     rcx, rsi; unsigned __int16 *
0x180010440  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010445  xor     eax, eax
0x180010447  jmp     loc_18001051A
0x18001044c  mov     r9d, 7FFFFFFFh
0x180010452  mov     [rsp+278h+var_248], rbx
0x180010457  mov     edx, r9d; unsigned __int64
0x18001045a  lea     r8, [rsp+278h+var_248]; unsigned __int64 *
0x18001045f  lea     rcx, [rsp+278h+String1]; unsigned __int16 *
0x180010464  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010469  test    eax, eax
0x18001046b  jns     short loc_180010474
0x18001046d  mov     edx, 0C5h
0x180010472  jmp     short loc_180010420
0x180010474  mov     r10d, dword ptr [rsp+278h+var_248]
0x180010479  lea     r8, [rsp+278h+var_248]; unsigned __int64 *
0x18001047e  mov     rdx, r9; unsigned __int64
0x180010481  mov     rcx, rdi; unsigned __int16 *
0x180010484  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010489  test    eax, eax
0x18001048b  jns     short loc_1800104AB
0x18001048d  mov     rcx, [rsp+278h]; this
0x180010495  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001049c  mov     r9d, eax; char *
0x18001049f  mov     edx, 0CDh; void *
0x1800104a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800104a9  jmp     short loc_1800104BA
0x1800104ab  mov     rbp, r10
0x1800104ae  mov     ebx, 1
0x1800104b3  cmp     [rsp+278h+var_248], r10
0x1800104b8  jnb     short loc_1800104CC
0x1800104ba  mov     rdx, r14; unsigned __int64
0x1800104bd  mov     rcx, rsi; unsigned __int16 *
0x1800104c0  mov     r8, rdi; unsigned __int16 *
0x1800104c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800104c8  mov     eax, ebx
0x1800104ca  jmp     short loc_18001051A
0x1800104cc  mov     r9d, r10d; cchCount2
0x1800104cf  mov     [rsp+278h+bIgnoreCase], ebx; bIgnoreCase
0x1800104d3  mov     r8, rdi; lpString2
0x1800104d6  lea     rcx, [rsp+278h+String1]; lpString1
0x1800104db  mov     edx, r10d; cchCount1
0x1800104de  call    cs:__imp_CompareStringOrdinal
0x1800104e5  nop     dword ptr [rax+rax+00h]
0x1800104ea  mov     rdx, r14; unsigned __int64
0x1800104ed  mov     rcx, rsi; unsigned __int16 *
0x1800104f0  cmp     eax, 2
0x1800104f3  jnz     short loc_1800104C0
0x1800104f5  lea     r8, aSystemroot; "%SystemRoot%"
0x1800104fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010501  lea     r8, [rdi+rbp*2]; unsigned __int16 *
0x180010505  mov     rdx, r14; unsigned __int64
0x180010508  mov     rcx, rsi; unsigned __int16 *
0x18001050b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010510  jmp     short loc_1800104C8
0x180010512  mov     [rdx], bx
0x180010515  mov     eax, 1
0x18001051a  mov     rcx, [rsp+278h+var_28]
0x180010522  xor     rcx, rsp; StackCookie
0x180010525  call    __security_check_cookie
0x18001052a  lea     r11, [rsp+278h+var_18]
0x180010532  mov     rbx, [r11+30h]
0x180010536  mov     rbp, [r11+38h]
0x18001053a  mov     rsp, r11
0x18001053d  pop     r14
0x18001053f  pop     rdi
0x180010540  pop     rsi
0x180010541  retn
```
