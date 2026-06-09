# CXMLValue::ScReadFromBSTR(ushort * const)

- ea: `0x18002024c`
- end: `0x180020500`
- name: `?ScReadFromBSTR@CXMLValue@@QEAA?AVSC@mmcerror@@QEAG@Z`
- size: `692`
- prototype: `mmcerror::SC *__fastcall(__int64, mmcerror::SC *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f080`
- `0x18001f9e0`
- `0x180020508`
- `0x1800234d0`

## callees

- `0x1800063c0`
- `0x1800139a4`
- `0x180014ea8`
- `0x18002024c`
- `0x18002c490`
- `0x180057074`
- `0x18013f010`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800204a1`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800204a1`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180020267`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180020267`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020395`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020437`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020470`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020395`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020437`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020470`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800204e3`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800204e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800203c1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18002040a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800203c1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18002040a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180020279`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180020279`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800203d6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18002047a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800203d6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18002047a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800203cc`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180020415`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800204ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800203cc`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180020415`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800204ee`
- `msvcrt!wcstoul` at `0x18002031b`
- `msvcrt!wcstoul` at `0x18002031b`
- `msvcrt!wcstol` at `0x18002032c`
- `msvcrt!wcstol` at `0x180020344`
- `msvcrt!wcstol` at `0x1800204d0`
- `msvcrt!wcstol` at `0x18002032c`
- `msvcrt!wcstol` at `0x180020344`
- `msvcrt!wcstol` at `0x1800204d0`
- `msvcrt!_wcsicmp` at `0x1800202d6`
- `msvcrt!_wcsicmp` at `0x1800202fd`
- `msvcrt!_wcsicmp` at `0x1800202d6`
- `msvcrt!_wcsicmp` at `0x1800202fd`
- `ole32!CLSIDFromString` at `0x18002042b`
- `ole32!CLSIDFromString` at `0x18002042b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800203e5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800203e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002041f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002041f`

## string_xrefs

- `0x18002026e`: `CXMLValue::ScReadFromBSTR`

## pseudocode

```c
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
0x18002024c  push    rbp
0x18002024e  push    rbx
0x18002024f  push    rsi
0x180020250  push    rdi
0x180020251  mov     rbp, rsp
0x180020254  sub     rsp, 68h
0x180020258  mov     rdi, r8
0x18002025b  mov     rsi, rdx
0x18002025e  mov     rbx, rcx
0x180020261  xor     edx, edx
0x180020263  lea     rcx, [rbp+var_40]
0x180020267  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18002026d  nop
0x18002026e  lea     rdx, aCxmlvalueScrea; "CXMLValue::ScReadFromBSTR"
0x180020275  lea     rcx, [rbp+var_40]
0x180020279  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18002027f  lea     rcx, WindowName
0x180020286  test    rdi, rdi
0x180020289  cmovnz  rcx, rdi; String
0x18002028d  mov     edx, [rbx]
0x18002028f  cmp     edx, 7
0x180020292  jg      loc_180020355
0x180020298  jz      short loc_180020315
0x18002029a  test    edx, edx
0x18002029c  jz      loc_1800204C8
0x1800202a2  sub     edx, 1
0x1800202a5  jz      short loc_180020315
0x1800202a7  sub     edx, 1
0x1800202aa  jz      loc_18002033E
0x1800202b0  sub     edx, 1
0x1800202b3  jz      short loc_180020326
0x1800202b5  sub     edx, 1
0x1800202b8  jz      short loc_180020315
0x1800202ba  sub     edx, 1
0x1800202bd  jz      short loc_1800202EC
0x1800202bf  cmp     edx, 1
0x1800202c2  jnz     loc_18002038C
0x1800202c8  mov     rax, [rbx+8]
0x1800202cc  mov     byte ptr [rax], 0
0x1800202cf  lea     rdx, aTrue; "true"
0x1800202d6  call    cs:__imp__wcsicmp
0x1800202dc  test    eax, eax
0x1800202de  setz    cl
0x1800202e1  mov     rax, [rbx+8]
0x1800202e5  mov     [rax], cl
0x1800202e7  jmp     loc_1800204DC
0x1800202ec  mov     rax, [rbx+8]
0x1800202f0  mov     dword ptr [rax], 0
0x1800202f6  lea     rdx, aTrue; "true"
0x1800202fd  call    cs:__imp__wcsicmp
0x180020303  xor     ecx, ecx
0x180020305  test    eax, eax
0x180020307  setz    cl
0x18002030a  mov     rax, [rbx+8]
0x18002030e  mov     [rax], ecx
0x180020310  jmp     loc_1800204DC
0x180020315  xor     edx, edx; EndPtr
0x180020317  lea     r8d, [rdx+0Ah]; Radix
0x18002031b  call    cs:__imp_wcstoul
0x180020321  jmp     loc_1800204D6
0x180020326  xor     edx, edx; EndPtr
0x180020328  lea     r8d, [rdx+0Ah]; Radix
0x18002032c  call    cs:__imp_wcstol
0x180020332  mov     rcx, [rbx+8]
0x180020336  mov     [rcx], ax
0x180020339  jmp     loc_1800204DC
0x18002033e  xor     edx, edx; EndPtr
0x180020340  lea     r8d, [rdx+0Ah]; Radix
0x180020344  call    cs:__imp_wcstol
0x18002034a  mov     rcx, [rbx+8]
0x18002034e  mov     [rcx], al
0x180020350  jmp     loc_1800204DC
0x180020355  sub     edx, 8
0x180020358  jz      loc_1800204C8
0x18002035e  sub     edx, 1
0x180020361  jz      loc_18002045E
0x180020367  sub     edx, 1
0x18002036a  jz      loc_180020450
0x180020370  sub     edx, 1
0x180020373  jz      loc_18002043F
0x180020379  sub     edx, 1
0x18002037c  jz      loc_180020427
0x180020382  sub     edx, 1
0x180020385  jz      short loc_1800203E1
0x180020387  cmp     edx, 1
0x18002038a  jz      short loc_1800203A3
0x18002038c  mov     edx, 80004001h
0x180020391  lea     rcx, [rbp+var_40]
0x180020395  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18002039b  mov     rdx, rax
0x18002039e  jmp     loc_1800204E0
0x1800203a3  mov     rcx, [rbx+8]
0x1800203a7  mov     rax, [rcx]
0x1800203aa  mov     r8, rdi
0x1800203ad  lea     rdx, [rbp+var_28]
0x1800203b1  mov     rax, [rax]
0x1800203b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203b9  nop
0x1800203ba  mov     rdx, rax
0x1800203bd  lea     rcx, [rbp+var_40]
0x1800203c1  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1800203c7  nop
0x1800203c8  lea     rcx, [rbp+var_28]
0x1800203cc  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800203d2  lea     rcx, [rbp+var_40]
0x1800203d6  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800203dc  jmp     loc_1800204DC
0x1800203e1  mov     rdi, [rbx+8]
0x1800203e5  call    cs:__imp_SysAllocString
0x1800203eb  mov     rbx, rax
0x1800203ee  mov     [rbp+arg_0], rax
0x1800203f2  mov     r8, rdi
0x1800203f5  lea     rdx, [rbp+arg_0]
0x1800203f9  lea     rcx, [rbp+var_28]
0x1800203fd  call    ScDecodeBinary
0x180020402  nop
0x180020403  mov     rdx, rax
0x180020406  lea     rcx, [rbp+var_40]
0x18002040a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180020410  nop
0x180020411  lea     rcx, [rbp+var_28]
0x180020415  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18002041b  nop
0x18002041c  mov     rcx, rbx; bstrString
0x18002041f  call    cs:__imp_SysFreeString
0x180020425  jmp     short loc_1800203D2
0x180020427  mov     rdx, [rbx+8]; pclsid
0x18002042b  call    cs:__imp_CLSIDFromString
0x180020431  mov     edx, eax
0x180020433  lea     rcx, [rbp+var_40]
0x180020437  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18002043d  jmp     short loc_1800203D2
0x18002043f  mov     rdx, rcx
0x180020442  mov     rcx, [rbx+8]
0x180020446  call    ??4tstring@@QEAAAEAV0@PEBG@Z; tstring::operator=(ushort const *)
0x18002044b  jmp     loc_1800204DC
0x180020450  mov     rdx, rcx
0x180020453  mov     rcx, [rbx+8]
0x180020457  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002045c  jmp     short loc_1800204DC
0x18002045e  mov     rdx, rcx; unsigned __int16 *
0x180020461  mov     rcx, [rbx+8]; this
0x180020465  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x18002046a  mov     edx, eax
0x18002046c  lea     rcx, [rbp+var_40]
0x180020470  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180020476  lea     rcx, [rbp+var_40]
0x18002047a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180020480  test    al, al
0x180020482  jz      short loc_1800204DC
0x180020484  lea     rcx, WPP_GLOBAL_Control
0x18002048b  mov     rax, cs:WPP_GLOBAL_Control
0x180020492  cmp     rax, rcx
0x180020495  jz      short loc_1800204DC
0x180020497  cmp     byte ptr [rax+19h], 2
0x18002049b  jb      short loc_1800204DC
0x18002049d  lea     rcx, [rbp+var_40]
0x1800204a1  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1800204a7  mov     edx, 0Eh
0x1800204ac  mov     r9d, eax
0x1800204af  lea     r8, WPP_646a9a0b7a2a331061ddf5a41ff5190c_Traceguids
0x1800204b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204bd  mov     rcx, [rcx+10h]
0x1800204c1  call    WPP_SF_d
0x1800204c6  jmp     short loc_1800204DC
0x1800204c8  mov     r8d, 0Ah; Radix
0x1800204ce  xor     edx, edx; EndPtr
0x1800204d0  call    cs:__imp_wcstol
0x1800204d6  mov     rcx, [rbx+8]
0x1800204da  mov     [rcx], eax
0x1800204dc  lea     rdx, [rbp+var_40]
0x1800204e0  mov     rcx, rsi
0x1800204e3  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800204e9  nop
0x1800204ea  lea     rcx, [rbp+var_40]
0x1800204ee  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800204f4  mov     rax, rsi
0x1800204f7  add     rsp, 68h
0x1800204fb  pop     rdi
0x1800204fc  pop     rsi
0x1800204fd  pop     rbx
0x1800204fe  pop     rbp
0x1800204ff  retn
```
