# MpConfigUtils::GetPartnerGUID(wchar_t * *)

- ea: `0x18014562c`
- end: `0x18014575e`
- name: `?GetPartnerGUID@MpConfigUtils@@YAJPEAPEA_W@Z`
- size: `306`
- prototype: `__int64 __fastcall(MpConfigUtils *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180160a54`

## callees

- `0x180064d10`
- `0x18010cb40`
- `0x18014562c`
- `0x1801458c0`
- `0x18023a310`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1801456b0`
- `MpClient!MpFreeMemory` at `0x1801456b0`
- `MpClient!MpConfigClose` at `0x18014567c`
- `MpClient!MpConfigClose` at `0x180145735`
- `MpClient!MpConfigClose` at `0x18014567c`
- `MpClient!MpConfigClose` at `0x180145735`
- `MpClient!MpConfigOpen` at `0x180145667`
- `MpClient!MpConfigOpen` at `0x180145667`
- `ole32!IIDFromString` at `0x180145711`
- `ole32!IIDFromString` at `0x180145711`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::GetPartnerGUID(MpConfigUtils *this, wchar_t **a2)
{
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  HRESULT ValueString; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  GUID iid; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF

  v13 = 0;
  v3 = MpConfigOpen(L".", &v13);
  v7 = v13;
  ValueString = v3;
  if ( v3 < 0 )
  {
LABEL_2:
    if ( v7 )
      MpConfigClose(v7, v4, v5, v6);
    return (unsigned int)ValueString;
  }
  v12 = 0;
  ValueString = MpConfigGetValueString(v13, L"PartnerGUID", &v12);
  if ( ValueString < 0
    || (memset(sz, 0, 0x4Eu),
        ValueString = StringCchPrintfW(sz, 0x27u, L"%s%s%s", &stru_18025EB84, v12, L"}"),
        ValueString < 0)
    || (iid = 0, ValueString = IIDFromString(sz, &iid), ValueString < 0) )
  {
    if ( v12 )
      MpFreeMemory(v12);
    v7 = v13;
    goto LABEL_2;
  }
  v10 = v12;
  v11 = v13;
  v12 = 0;
  *(_QWORD *)this = v10;
  if ( v11 )
    MpConfigClose(v11, v4, v5, v6);
  return 0;
}

```

## disassembly

```asm
0x18014562c  mov     [rsp-8+arg_8], rbx
0x180145631  mov     [rsp-8+arg_10], rdi
0x180145636  push    rbp
0x180145637  lea     rbp, [rsp-57h]
0x18014563c  sub     rsp, 0B0h
0x180145643  mov     rax, cs:__security_cookie
0x18014564a  xor     rax, rsp
0x18014564d  mov     [rbp+57h+var_10], rax
0x180145651  mov     rdi, rcx
0x180145654  mov     [rbp+57h+var_78], 0
0x18014565c  lea     rcx, asc_18025D638; "."
0x180145663  lea     rdx, [rbp+57h+var_78]
0x180145667  call    cs:__imp_MpConfigOpen
0x18014566d  mov     rcx, [rbp+57h+var_78]
0x180145671  mov     ebx, eax
0x180145673  test    eax, eax
0x180145675  jns     short loc_180145689
0x180145677  test    rcx, rcx
0x18014567a  jz      short loc_180145682
0x18014567c  call    cs:__imp_MpConfigClose
0x180145682  mov     eax, ebx
0x180145684  jmp     loc_18014573D
0x180145689  lea     r8, [rbp+57h+var_80]
0x18014568d  mov     [rbp+57h+var_80], 0
0x180145695  lea     rdx, aPartnerguid; "PartnerGUID"
0x18014569c  call    MpConfigGetValueString
0x1801456a1  mov     ebx, eax
0x1801456a3  test    eax, eax
0x1801456a5  jns     short loc_1801456BC
0x1801456a7  mov     rcx, [rbp+57h+var_80]
0x1801456ab  test    rcx, rcx
0x1801456ae  jz      short loc_1801456B6
0x1801456b0  call    cs:__imp_MpFreeMemory
0x1801456b6  mov     rcx, [rbp+57h+var_78]
0x1801456ba  jmp     short loc_180145677
0x1801456bc  xor     edx, edx; Val
0x1801456be  lea     rcx, [rbp+57h+sz]; void *
0x1801456c2  lea     r8d, [rdx+4Eh]; Size
0x1801456c6  call    memset
0x1801456cb  lea     rax, asc_18025EB80; "}"
0x1801456d2  mov     edx, 27h ; '''; unsigned __int64
0x1801456d7  mov     [rsp+0B0h+var_88], rax
0x1801456dc  lea     r9, stru_18025EB84
0x1801456e3  mov     rax, [rbp+57h+var_80]
0x1801456e7  lea     r8, aSSS; "%s%s%s"
0x1801456ee  lea     rcx, [rbp+57h+sz]; wchar_t *
0x1801456f2  mov     [rsp+0B0h+var_90], rax
0x1801456f7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801456fc  mov     ebx, eax
0x1801456fe  test    eax, eax
0x180145700  js      short loc_1801456A7
0x180145702  xorps   xmm0, xmm0
0x180145705  lea     rdx, [rbp+57h+iid]; lpiid
0x180145709  lea     rcx, [rbp+57h+sz]; lpsz
0x18014570d  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x180145711  call    cs:__imp_IIDFromString
0x180145717  mov     ebx, eax
0x180145719  test    eax, eax
0x18014571b  js      short loc_1801456A7
0x18014571d  mov     rax, [rbp+57h+var_80]
0x180145721  mov     rcx, [rbp+57h+var_78]
0x180145725  mov     [rbp+57h+var_80], 0
0x18014572d  mov     [rdi], rax
0x180145730  test    rcx, rcx
0x180145733  jz      short loc_18014573B
0x180145735  call    cs:__imp_MpConfigClose
0x18014573b  xor     eax, eax
0x18014573d  mov     rcx, [rbp+57h+var_10]
0x180145741  xor     rcx, rsp; StackCookie
0x180145744  call    __security_check_cookie
0x180145749  lea     r11, [rsp+0B0h+var_s0]
0x180145751  mov     rbx, [r11+18h]
0x180145755  mov     rdi, [r11+20h]
0x180145759  mov     rsp, r11
0x18014575c  pop     rbp
0x18014575d  retn
```
