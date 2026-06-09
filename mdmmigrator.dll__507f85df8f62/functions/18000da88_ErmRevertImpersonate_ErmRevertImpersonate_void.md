# ErmRevertImpersonate::~ErmRevertImpersonate(void)

- ea: `0x18000da88`
- end: `0x18000dbb3`
- name: `??1ErmRevertImpersonate@@QEAA@XZ`
- size: `299`
- prototype: `void __fastcall(ErmRevertImpersonate *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180010170`
- `0x180010610`
- `0x180010864`
- `0x18001f9f3`
- `0x18001fa29`
- `0x18001fa5f`

## callees

- `0x1800013c8`
- `0x1800022e0`
- `0x180007720`
- `0x18000da88`

## import_xrefs

- `DMCmnUtils!DmImpersonate` at `0x18000daba`
- `DMCmnUtils!DmImpersonate` at `0x18000daba`

## string_xrefs

- `0x18000db42`: `ErmRevertImpersonate::~ErmRevertImpersonate`

## pseudocode

```c
void __fastcall ErmRevertImpersonate::~ErmRevertImpersonate(ErmRevertImpersonate *this)
{
  char **v1; // rbx
  int v2; // edi
  int v3; // [rsp+30h] [rbp-29h] BYREF
  int v4; // [rsp+34h] [rbp-25h] BYREF
  char v5[32]; // [rsp+40h] [rbp-19h] BYREF
  const wchar_t *v6; // [rsp+60h] [rbp+7h]
  __int64 v7; // [rsp+68h] [rbp+Fh]
  int *v8; // [rsp+70h] [rbp+17h]
  __int64 v9; // [rsp+78h] [rbp+1Fh]
  const char *v10; // [rsp+80h] [rbp+27h]
  __int64 v11; // [rsp+88h] [rbp+2Fh]
  int *v12; // [rsp+90h] [rbp+37h]
  __int64 v13; // [rsp+98h] [rbp+3Fh]

  v1 = (char **)this;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(ErmRevertImpersonate **)this;
  v2 = DmImpersonate((const unsigned __int16 *)this);
  if ( v2 < 0
    && (unsigned int)dword_18002B0C0 > 5
    && (qword_18002B0D0 & 0x400000000000LL) != 0
    && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
  {
    v3 = v2;
    v4 = 32;
    v12 = &v3;
    v13 = 4;
    v10 = "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
    v11 = 81;
    v8 = &v4;
    v9 = 4;
    v6 = L"ErmRevertImpersonate::~ErmRevertImpersonate";
    v7 = 88;
    tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, &dword_180025D8C, 0, 0, 6, v5);
  }
  byte_18002B7D8 = v2 != 1;
  std::wstring::~wstring(v1);
}

```

## disassembly

```asm
0x18000da88  mov     [rsp-8+arg_8], rbx
0x18000da8d  mov     [rsp-8+arg_10], rdi
0x18000da92  push    rbp
0x18000da93  lea     rbp, [rsp-57h]
0x18000da98  sub     rsp, 0B0h
0x18000da9f  mov     rax, cs:__security_cookie
0x18000daa6  xor     rax, rsp
0x18000daa9  mov     [rbp+57h+var_10], rax
0x18000daad  mov     rbx, rcx
0x18000dab0  cmp     qword ptr [rcx+18h], 7
0x18000dab5  jbe     short loc_18000DABA
0x18000dab7  mov     rcx, [rcx]
0x18000daba  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18000dac0  mov     edi, eax
0x18000dac2  test    eax, eax
0x18000dac4  jns     loc_18000DB7F
0x18000daca  mov     ecx, cs:dword_18002B0C0
0x18000dad0  cmp     ecx, 5
0x18000dad3  jbe     loc_18000DB7F
0x18000dad9  mov     rdx, cs:qword_18002B0D8
0x18000dae0  mov     rcx, cs:qword_18002B0D0
0x18000dae7  mov     r9, 400000000000h
0x18000daf1  test    r9, rcx
0x18000daf4  jz      loc_18000DB7F
0x18000dafa  mov     rax, rdx
0x18000dafd  and     rax, r9
0x18000db00  cmp     rax, rdx
0x18000db03  jnz     short loc_18000DB7F
0x18000db05  mov     [rbp+57h+var_80], edi
0x18000db08  mov     [rbp+57h+var_7C], 20h ; ' '
0x18000db0f  lea     rax, [rbp+57h+var_80]
0x18000db13  mov     [rbp+57h+var_20], rax
0x18000db17  mov     [rbp+57h+var_18], 4
0x18000db1f  lea     rax, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000db26  mov     [rbp+57h+var_30], rax
0x18000db2a  mov     [rbp+57h+var_28], 51h ; 'Q'
0x18000db32  lea     rax, [rbp+57h+var_7C]
0x18000db36  mov     [rbp+57h+var_40], rax
0x18000db3a  mov     [rbp+57h+var_38], 4
0x18000db42  lea     rax, aErmrevertimper; "ErmRevertImpersonate::~ErmRevertImperso"...
0x18000db49  mov     [rbp+57h+var_50], rax
0x18000db4d  mov     [rbp+57h+var_48], 58h ; 'X'
0x18000db55  lea     rax, [rbp+57h+var_70]
0x18000db59  mov     [rsp+0B0h+var_88], rax
0x18000db5e  mov     [rsp+0B0h+var_90], 6
0x18000db66  xor     r9d, r9d
0x18000db69  xor     r8d, r8d
0x18000db6c  lea     rdx, dword_180025D8C
0x18000db73  lea     rcx, dword_18002B0C0
0x18000db7a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000db7f  cmp     edi, 1
0x18000db82  setnz   cs:byte_18002B7D8
0x18000db89  mov     rcx, rbx; void *
0x18000db8c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000db91  nop
0x18000db92  mov     rcx, [rbp+57h+var_10]
0x18000db96  xor     rcx, rsp; StackCookie
0x18000db99  call    __security_check_cookie
0x18000db9e  lea     r11, [rsp+0B0h+var_s0]
0x18000dba6  mov     rbx, [r11+18h]
0x18000dbaa  mov     rdi, [r11+20h]
0x18000dbae  mov     rsp, r11
0x18000dbb1  pop     rbp
0x18000dbb2  retn
```
