# GetRIMDeviceInstancePath

- ea: `0x180121c84`
- end: `0x180121dac`
- name: `GetRIMDeviceInstancePath`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180121f24`

## callees

- `0x18002f9b4`
- `0x18008ead4`
- `0x1800af9b8`
- `0x1800f2478`
- `0x180121c84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180121d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180121d82`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x180121cc6`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x180121d53`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x180121cc6`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x180121d53`

## pseudocode

```c
int __fastcall GetRIMDeviceInstancePath(__int64 a1, __int64 a2, HSTRING *a3)
{
  int v6; // eax
  int v8; // r14d
  unsigned __int64 v9; // rax
  const WCHAR *v10; // rax
  const WCHAR *v11; // rbx
  int v12; // ebx
  int v13; // eax
  HRESULT String; // eax
  int v15[4]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v16; // [rsp+30h] [rbp-38h]
  __int64 v17; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  const WCHAR *v19; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 0;
  v15[0] = 4;
  v6 = RIMGetDeviceProperties(a1, a2, v15);
  if ( v6 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x28,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
             (const char *)(unsigned int)v6,
             v15[0]);
  v8 = v15[2];
  v9 = 2LL * (unsigned int)v15[2];
  if ( !is_mul_ok((unsigned int)v15[2], 2u) )
    v9 = -1;
  v10 = (const WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v10;
  v11 = v10;
  if ( v10 )
  {
    *(_QWORD *)&v16 = v10;
    v13 = RIMGetDeviceProperties(a1, a2, v15);
    if ( v13 >= 0 )
      String = WindowsCreateString(v11, v8 - 1, a3);
    else
      String = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x30,
                 (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
                 (const char *)(unsigned int)v13,
                 v15[0]);
    v12 = String;
  }
  else
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
      (const char *)0x8007000ELL,
      v15[0]);
  }
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v19);
  return v12;
}

```

## disassembly

```asm
0x180121c84  mov     r11, rsp
0x180121c87  mov     [r11+8], rbx
0x180121c8b  mov     [r11+10h], rbp
0x180121c8f  push    rsi
0x180121c90  push    rdi
0x180121c91  push    r14
0x180121c93  sub     rsp, 50h
0x180121c97  xorps   xmm0, xmm0
0x180121c9a  mov     qword ptr [r8], 0
0x180121ca1  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180121ca6  xor     eax, eax
0x180121ca8  mov     rdi, r8
0x180121cab  movups  [rsp+68h+var_38], xmm0
0x180121cb0  mov     [r11-28h], rax
0x180121cb4  lea     r8, [r11-48h]
0x180121cb8  mov     [rsp+68h+var_48], 4; int
0x180121cc0  mov     rsi, rdx
0x180121cc3  mov     rbp, rcx
0x180121cc6  call    cs:__imp_RIMGetDeviceProperties
0x180121ccc  test    eax, eax
0x180121cce  jns     short loc_180121CEE
0x180121cd0  mov     rcx, [rsp+68h]; this
0x180121cd5  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x180121cdc  mov     r9d, eax; char *
0x180121cdf  mov     edx, 28h ; '('; void *
0x180121ce4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180121ce9  jmp     loc_180121D99
0x180121cee  mov     r14d, [rsp+68h+var_48+8]
0x180121cf3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180121cfa  mov     eax, 2
0x180121cff  mul     r14
0x180121d02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180121d09  cmovb   rax, rcx
0x180121d0d  mov     rcx, rax; unsigned __int64
0x180121d10  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180121d15  mov     [rsp+68h+arg_10], rax
0x180121d1d  mov     rbx, rax
0x180121d20  test    rax, rax
0x180121d23  jnz     short loc_180121D43
0x180121d25  mov     rcx, [rsp+68h]; this
0x180121d2a  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x180121d31  mov     ebx, 8007000Eh
0x180121d36  lea     edx, [rax+2Dh]; void *
0x180121d39  mov     r9d, ebx; char *
0x180121d3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121d41  jmp     short loc_180121D8A
0x180121d43  lea     r8, [rsp+68h+var_48]
0x180121d48  mov     qword ptr [rsp+68h+var_38], rbx
0x180121d4d  mov     rdx, rsi
0x180121d50  mov     rcx, rbp
0x180121d53  call    cs:__imp_RIMGetDeviceProperties
0x180121d59  test    eax, eax
0x180121d5b  jns     short loc_180121D78
0x180121d5d  mov     rcx, [rsp+68h]; this
0x180121d62  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x180121d69  mov     r9d, eax; char *
0x180121d6c  mov     edx, 30h ; '0'; void *
0x180121d71  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180121d76  jmp     short loc_180121D88
0x180121d78  lea     edx, [r14-1]; length
0x180121d7c  mov     r8, rdi; string
0x180121d7f  mov     rcx, rbx; sourceString
0x180121d82  call    cs:__imp_WindowsCreateString
0x180121d88  mov     ebx, eax
0x180121d8a  lea     rcx, [rsp+68h+arg_10]
0x180121d92  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x180121d97  mov     eax, ebx
0x180121d99  mov     rbx, [rsp+68h+arg_0]
0x180121d9e  mov     rbp, [rsp+68h+arg_8]
0x180121da3  add     rsp, 50h
0x180121da7  pop     r14
0x180121da9  pop     rdi
0x180121daa  pop     rsi
0x180121dab  retn
```
