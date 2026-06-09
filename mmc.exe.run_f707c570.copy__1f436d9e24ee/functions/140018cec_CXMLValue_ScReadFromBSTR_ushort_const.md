# CXMLValue::ScReadFromBSTR(ushort * const)

- ea: `0x140018cec`
- end: `0x140018fa0`
- name: `?ScReadFromBSTR@CXMLValue@@QEAA?AVSC@mmcerror@@QEAG@Z`
- size: `692`
- prototype: `mmcerror::SC *__fastcall(__int64, mmcerror::SC *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018064`
- `0x140018350`
- `0x140018958`
- `0x14001a078`

## callees

- `0x140005da0`
- `0x14000d1f0`
- `0x14000d38c`
- `0x140018cec`
- `0x14001c4f0`
- `0x1400598b4`
- `0x1400f3010`

## import_xrefs

- `msvcrt!wcstoul` at `0x140018dbb`
- `msvcrt!wcstoul` at `0x140018dbb`
- `msvcrt!_wcsicmp` at `0x140018d76`
- `msvcrt!_wcsicmp` at `0x140018d9d`
- `msvcrt!_wcsicmp` at `0x140018d76`
- `msvcrt!_wcsicmp` at `0x140018d9d`
- `msvcrt!wcstol` at `0x140018dcc`
- `msvcrt!wcstol` at `0x140018de4`
- `msvcrt!wcstol` at `0x140018f70`
- `msvcrt!wcstol` at `0x140018dcc`
- `msvcrt!wcstol` at `0x140018de4`
- `msvcrt!wcstol` at `0x140018f70`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018e6c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018eb5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018f8e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018e6c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018eb5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140018f8e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140018e76`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140018f1a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140018e76`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140018f1a`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140018d07`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140018d07`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140018f41`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140018f41`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018e35`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018ed7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018f10`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018e35`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018ed7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140018f10`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x140018f83`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x140018f83`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140018e61`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140018eaa`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140018e61`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140018eaa`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140018d19`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140018d19`
- `ole32!CLSIDFromString` at `0x140018ecb`
- `ole32!CLSIDFromString` at `0x140018ecb`
- `OLEAUT32!__imp_SysAllocString` at `0x140018e85`
- `OLEAUT32!__imp_SysAllocString` at `0x140018e85`
- `OLEAUT32!__imp_SysFreeString` at `0x140018ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x140018ebf`

## string_xrefs

- `0x140018d0e`: `CXMLValue::ScReadFromBSTR`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CXMLValue::ScReadFromBSTR(__int64 a1, mmcerror::SC *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v6; // rcx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  const struct mmcerror::SC *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdi
  OLECHAR *v23; // rbx
  mmcerror::SC *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  _BYTE v29[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v30[40]; // [rsp+40h] [rbp-28h] BYREF
  BSTR v31; // [rsp+90h] [rbp+28h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v29, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v29, L"CXMLValue::ScReadFromBSTR");
  v6 = &WindowName;
  if ( a3 )
    v6 = a3;
  v7 = *(_DWORD *)a1;
  if ( *(int *)a1 > 7 )
  {
    v14 = v7 - 8;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 )
      {
        v26 = CStr::Assign(*(CStr **)(a1 + 8), v6);
        mmcerror::SC::operator=(v29, v26);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v29)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v27 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_646a9a0b7a2a331061ddf5a41ff5190c_Traceguids, v27);
        }
        goto LABEL_37;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        std::wstring::assign(*(_QWORD *)(a1 + 8), v6);
        goto LABEL_37;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        tstring::operator=(*(_QWORD *)(a1 + 8), v6);
        goto LABEL_37;
      }
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 != 1 )
            goto LABEL_24;
          v21 = (***(__int64 (__fastcall ****)(_QWORD, _BYTE *, const unsigned __int16 *))(a1 + 8))(
                  *(_QWORD *)(a1 + 8),
                  v30,
                  a3);
          mmcerror::SC::operator=(v29, v21);
          mmcerror::SC::~SC((mmcerror::SC *)v30);
        }
        else
        {
          v22 = *(_QWORD *)(a1 + 8);
          v23 = SysAllocString(v6);
          v31 = v23;
          v24 = ScDecodeBinary((mmcerror::SC *)v30, &v31, v22);
          mmcerror::SC::operator=(v29, v24);
          mmcerror::SC::~SC((mmcerror::SC *)v30);
          SysFreeString(v23);
        }
      }
      else
      {
        v25 = CLSIDFromString(v6, *(LPCLSID *)(a1 + 8));
        mmcerror::SC::operator=(v29, v25);
      }
      mmcerror::SC::operator bool(v29);
      goto LABEL_37;
    }
    goto LABEL_35;
  }
  if ( v7 == 7 )
  {
LABEL_14:
    v13 = wcstoul(v6, 0, 10);
LABEL_36:
    **(_DWORD **)(a1 + 8) = v13;
    goto LABEL_37;
  }
  if ( !v7 )
  {
LABEL_35:
    v13 = wcstol(v6, 0, 10);
    goto LABEL_36;
  }
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_14;
  v9 = v8 - 1;
  if ( !v9 )
  {
    **(_BYTE **)(a1 + 8) = wcstol(v6, 0, 10);
    goto LABEL_37;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    **(_WORD **)(a1 + 8) = wcstol(v6, 0, 10);
    goto LABEL_37;
  }
  v11 = v10 - 1;
  if ( !v11 )
    goto LABEL_14;
  v12 = v11 - 1;
  if ( !v12 )
  {
    **(_DWORD **)(a1 + 8) = 0;
    **(_DWORD **)(a1 + 8) = _wcsicmp(v6, L"true") == 0;
    goto LABEL_37;
  }
  if ( v12 == 1 )
  {
    **(_BYTE **)(a1 + 8) = 0;
    **(_BYTE **)(a1 + 8) = _wcsicmp(v6, L"true") == 0;
LABEL_37:
    v20 = (const struct mmcerror::SC *)v29;
    goto LABEL_38;
  }
LABEL_24:
  v20 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v29, 2147500033LL);
LABEL_38:
  mmcerror::SC::SC(a2, v20);
  mmcerror::SC::~SC((mmcerror::SC *)v29);
  return a2;
}

```

## disassembly

```asm
0x140018cec  push    rbp
0x140018cee  push    rbx
0x140018cef  push    rsi
0x140018cf0  push    rdi
0x140018cf1  mov     rbp, rsp
0x140018cf4  sub     rsp, 68h
0x140018cf8  mov     rdi, r8
0x140018cfb  mov     rsi, rdx
0x140018cfe  mov     rbx, rcx
0x140018d01  xor     edx, edx
0x140018d03  lea     rcx, [rbp+var_40]
0x140018d07  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140018d0d  nop
0x140018d0e  lea     rdx, aCxmlvalueScrea; "CXMLValue::ScReadFromBSTR"
0x140018d15  lea     rcx, [rbp+var_40]
0x140018d19  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140018d1f  lea     rcx, WindowName
0x140018d26  test    rdi, rdi
0x140018d29  cmovnz  rcx, rdi; String
0x140018d2d  mov     edx, [rbx]
0x140018d2f  cmp     edx, 7
0x140018d32  jg      loc_140018DF5
0x140018d38  jz      short loc_140018DB5
0x140018d3a  test    edx, edx
0x140018d3c  jz      loc_140018F68
0x140018d42  sub     edx, 1
0x140018d45  jz      short loc_140018DB5
0x140018d47  sub     edx, 1
0x140018d4a  jz      loc_140018DDE
0x140018d50  sub     edx, 1
0x140018d53  jz      short loc_140018DC6
0x140018d55  sub     edx, 1
0x140018d58  jz      short loc_140018DB5
0x140018d5a  sub     edx, 1
0x140018d5d  jz      short loc_140018D8C
0x140018d5f  cmp     edx, 1
0x140018d62  jnz     loc_140018E2C
0x140018d68  mov     rax, [rbx+8]
0x140018d6c  mov     byte ptr [rax], 0
0x140018d6f  lea     rdx, aTrue; "true"
0x140018d76  call    cs:__imp__wcsicmp
0x140018d7c  test    eax, eax
0x140018d7e  setz    cl
0x140018d81  mov     rax, [rbx+8]
0x140018d85  mov     [rax], cl
0x140018d87  jmp     loc_140018F7C
0x140018d8c  mov     rax, [rbx+8]
0x140018d90  mov     dword ptr [rax], 0
0x140018d96  lea     rdx, aTrue; "true"
0x140018d9d  call    cs:__imp__wcsicmp
0x140018da3  xor     ecx, ecx
0x140018da5  test    eax, eax
0x140018da7  setz    cl
0x140018daa  mov     rax, [rbx+8]
0x140018dae  mov     [rax], ecx
0x140018db0  jmp     loc_140018F7C
0x140018db5  xor     edx, edx; EndPtr
0x140018db7  lea     r8d, [rdx+0Ah]; Radix
0x140018dbb  call    cs:__imp_wcstoul
0x140018dc1  jmp     loc_140018F76
0x140018dc6  xor     edx, edx; EndPtr
0x140018dc8  lea     r8d, [rdx+0Ah]; Radix
0x140018dcc  call    cs:__imp_wcstol
0x140018dd2  mov     rcx, [rbx+8]
0x140018dd6  mov     [rcx], ax
0x140018dd9  jmp     loc_140018F7C
0x140018dde  xor     edx, edx; EndPtr
0x140018de0  lea     r8d, [rdx+0Ah]; Radix
0x140018de4  call    cs:__imp_wcstol
0x140018dea  mov     rcx, [rbx+8]
0x140018dee  mov     [rcx], al
0x140018df0  jmp     loc_140018F7C
0x140018df5  sub     edx, 8
0x140018df8  jz      loc_140018F68
0x140018dfe  sub     edx, 1
0x140018e01  jz      loc_140018EFE
0x140018e07  sub     edx, 1
0x140018e0a  jz      loc_140018EF0
0x140018e10  sub     edx, 1
0x140018e13  jz      loc_140018EDF
0x140018e19  sub     edx, 1
0x140018e1c  jz      loc_140018EC7
0x140018e22  sub     edx, 1
0x140018e25  jz      short loc_140018E81
0x140018e27  cmp     edx, 1
0x140018e2a  jz      short loc_140018E43
0x140018e2c  mov     edx, 80004001h
0x140018e31  lea     rcx, [rbp+var_40]
0x140018e35  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140018e3b  mov     rdx, rax
0x140018e3e  jmp     loc_140018F80
0x140018e43  mov     rcx, [rbx+8]
0x140018e47  mov     rax, [rcx]
0x140018e4a  mov     r8, rdi
0x140018e4d  lea     rdx, [rbp+var_28]
0x140018e51  mov     rax, [rax]
0x140018e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e59  nop
0x140018e5a  mov     rdx, rax
0x140018e5d  lea     rcx, [rbp+var_40]
0x140018e61  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140018e67  nop
0x140018e68  lea     rcx, [rbp+var_28]
0x140018e6c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140018e72  lea     rcx, [rbp+var_40]
0x140018e76  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140018e7c  jmp     loc_140018F7C
0x140018e81  mov     rdi, [rbx+8]
0x140018e85  call    cs:__imp_SysAllocString
0x140018e8b  mov     rbx, rax
0x140018e8e  mov     [rbp+arg_0], rax
0x140018e92  mov     r8, rdi
0x140018e95  lea     rdx, [rbp+arg_0]
0x140018e99  lea     rcx, [rbp+var_28]
0x140018e9d  call    ScDecodeBinary
0x140018ea2  nop
0x140018ea3  mov     rdx, rax
0x140018ea6  lea     rcx, [rbp+var_40]
0x140018eaa  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140018eb0  nop
0x140018eb1  lea     rcx, [rbp+var_28]
0x140018eb5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140018ebb  nop
0x140018ebc  mov     rcx, rbx; bstrString
0x140018ebf  call    cs:__imp_SysFreeString
0x140018ec5  jmp     short loc_140018E72
0x140018ec7  mov     rdx, [rbx+8]; pclsid
0x140018ecb  call    cs:__imp_CLSIDFromString
0x140018ed1  mov     edx, eax
0x140018ed3  lea     rcx, [rbp+var_40]
0x140018ed7  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140018edd  jmp     short loc_140018E72
0x140018edf  mov     rdx, rcx
0x140018ee2  mov     rcx, [rbx+8]
0x140018ee6  call    ??4tstring@@QEAAAEAV0@PEBG@Z; tstring::operator=(ushort const *)
0x140018eeb  jmp     loc_140018F7C
0x140018ef0  mov     rdx, rcx
0x140018ef3  mov     rcx, [rbx+8]
0x140018ef7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140018efc  jmp     short loc_140018F7C
0x140018efe  mov     rdx, rcx; unsigned __int16 *
0x140018f01  mov     rcx, [rbx+8]; this
0x140018f05  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x140018f0a  mov     edx, eax
0x140018f0c  lea     rcx, [rbp+var_40]
0x140018f10  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140018f16  lea     rcx, [rbp+var_40]
0x140018f1a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140018f20  test    al, al
0x140018f22  jz      short loc_140018F7C
0x140018f24  lea     rcx, WPP_GLOBAL_Control
0x140018f2b  mov     rax, cs:WPP_GLOBAL_Control
0x140018f32  cmp     rax, rcx
0x140018f35  jz      short loc_140018F7C
0x140018f37  cmp     byte ptr [rax+19h], 2
0x140018f3b  jb      short loc_140018F7C
0x140018f3d  lea     rcx, [rbp+var_40]
0x140018f41  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140018f47  mov     edx, 0Eh
0x140018f4c  mov     r9d, eax
0x140018f4f  lea     r8, WPP_646a9a0b7a2a331061ddf5a41ff5190c_Traceguids
0x140018f56  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f5d  mov     rcx, [rcx+10h]
0x140018f61  call    WPP_SF_d
0x140018f66  jmp     short loc_140018F7C
0x140018f68  mov     r8d, 0Ah; Radix
0x140018f6e  xor     edx, edx; EndPtr
0x140018f70  call    cs:__imp_wcstol
0x140018f76  mov     rcx, [rbx+8]
0x140018f7a  mov     [rcx], eax
0x140018f7c  lea     rdx, [rbp+var_40]
0x140018f80  mov     rcx, rsi
0x140018f83  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x140018f89  nop
0x140018f8a  lea     rcx, [rbp+var_40]
0x140018f8e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140018f94  mov     rax, rsi
0x140018f97  add     rsp, 68h
0x140018f9b  pop     rdi
0x140018f9c  pop     rsi
0x140018f9d  pop     rbx
0x140018f9e  pop     rbp
0x140018f9f  retn
```
