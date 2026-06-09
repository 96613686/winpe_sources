# CProvisioningCommandsNode::GetValue(tagVARIANT *)

- ea: `0x1800089c0`
- end: `0x180008caf`
- name: `?GetValue@CProvisioningCommandsNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000108c`
- `0x180004da4`
- `0x1800071d8`
- `0x1800089c0`
- `0x180009b50`
- `0x18000a050`
- `0x18000c600`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008c65`
- `OLEAUT32!__imp_SysAllocString` at `0x180008c65`
- `OLEAUT32!__imp_VariantInit` at `0x180008a6d`
- `OLEAUT32!__imp_VariantInit` at `0x180008a6d`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetValue(CProvisioningCommandsNode *this, struct tagVARIANT *a2)
{
  int v5; // r14d
  __int64 v6; // rdx
  int Command; // eax
  int Value; // eax
  unsigned int v9; // ebx
  LONG v10; // eax
  const OLECHAR *v11; // rcx
  int v12; // [rsp+20h] [rbp-F8h]
  int v13; // [rsp+30h] [rbp-E8h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-E0h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-D8h] BYREF
  unsigned __int16 *v16; // [rsp+48h] [rbp-D0h] BYREF
  void *v17[4]; // [rsp+50h] [rbp-C8h] BYREF
  OLECHAR *psz[3]; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int64 v19; // [rsp+88h] [rbp-90h]
  __int16 v20; // [rsp+90h] [rbp-88h]
  __int64 v21; // [rsp+A0h] [rbp-78h]
  __int64 v22; // [rsp+A8h] [rbp-70h]
  LONG v23; // [rsp+B0h] [rbp-68h]
  int v24; // [rsp+B4h] [rbp-64h]
  LONG v25; // [rsp+B8h] [rbp-60h]
  LONG v26; // [rsp+BCh] [rbp-5Ch]
  int *v27; // [rsp+E0h] [rbp-38h]
  __int64 v28; // [rsp+E8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( (unsigned int)dword_180014230 > 4 )
  {
    v13 = *((_DWORD *)this + 11);
    v27 = &v13;
    v28 = 4;
    v12 = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_180014230, &word_180010966, 0, 0);
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"admin\\prov\\launch\\csp\\getvalue.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
  VariantInit(a2);
  v16 = 0;
  v15 = 0;
  String1 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         1,
         &v16);
  if ( v5 < 0 )
  {
    v6 = 20;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"admin\\prov\\launch\\csp\\getvalue.cpp",
      (const char *)(unsigned int)v5,
      v12);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         2,
         &v15);
  if ( v5 < 0 )
  {
    v6 = 21;
    goto LABEL_7;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         3,
         &String1);
  if ( v5 < 0 )
  {
    v6 = 22;
    goto LABEL_7;
  }
  v17[3] = (void *)7;
  v17[2] = 0;
  LOWORD(v17[0]) = 0;
  v19 = 7;
  psz[2] = 0;
  LOWORD(psz[0]) = 0;
  v22 = 7;
  v21 = 0;
  v20 = 0;
  v23 = 0;
  v24 = 1;
  Command = CProvisioningCommandsNode::FindCommand(v16, v15, String1, (struct Command *)v17);
  v5 = Command;
  if ( Command < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"admin\\prov\\launch\\csp\\getvalue.cpp",
      (const char *)(unsigned int)Command,
      v12);
    Command::~Command(v17);
    return (unsigned int)v5;
  }
  a2->vt = 19;
  switch ( *((_DWORD *)this + 11) )
  {
    case 4:
    case 8:
      a2->vt = 8;
      v11 = (const OLECHAR *)psz;
      if ( v19 >= 8 )
        v11 = psz[0];
      a2->llVal = (LONGLONG)SysAllocString(v11);
      goto LABEL_31;
    case 9:
      v10 = v25;
      goto LABEL_27;
    case 0xA:
      v10 = v26;
      goto LABEL_27;
    case 0xB:
      v10 = v23;
      goto LABEL_27;
    case 0xC:
      v10 = v24;
LABEL_27:
      a2->lVal = v10;
      goto LABEL_31;
  }
  Value = CCSPNodeImpl::GetValue(this, a2);
  v9 = Value;
  if ( Value < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"admin\\prov\\launch\\csp\\getvalue.cpp",
      (const char *)(unsigned int)Value,
      v12);
    Command::~Command(v17);
    return v9;
  }
LABEL_31:
  Command::~Command(v17);
  return 0;
}

```

## disassembly

```asm
0x1800089c0  mov     r11, rsp
0x1800089c3  mov     [r11+18h], rbx
0x1800089c7  push    rsi
0x1800089c8  push    rdi
0x1800089c9  push    r14
0x1800089cb  sub     rsp, 100h
0x1800089d2  mov     rax, cs:__security_cookie
0x1800089d9  xor     rax, rsp
0x1800089dc  mov     [rsp+118h+var_28], rax
0x1800089e4  mov     rbx, rdx
0x1800089e7  mov     rsi, rcx
0x1800089ea  mov     eax, cs:dword_180014230
0x1800089f0  cmp     eax, 4
0x1800089f3  jbe     short loc_180008A3B
0x1800089f5  mov     eax, [rcx+2Ch]
0x1800089f8  mov     [rsp+118h+var_E8], eax
0x1800089fc  lea     rax, [rsp+118h+var_E8]
0x180008a01  mov     [r11-38h], rax
0x180008a05  mov     qword ptr [r11-30h], 4
0x180008a0d  xor     edi, edi
0x180008a0f  lea     rax, [r11-58h]
0x180008a13  mov     [rsp+118h+var_F0], rax
0x180008a18  mov     [rsp+118h+var_F8], 3
0x180008a20  xor     r9d, r9d
0x180008a23  xor     r8d, r8d
0x180008a26  lea     rdx, word_180010966
0x180008a2d  lea     rcx, dword_180014230
0x180008a34  call    _tlgWriteTransfer_EventWriteTransfer
0x180008a39  jmp     short loc_180008A3D
0x180008a3b  xor     edi, edi
0x180008a3d  test    rbx, rbx
0x180008a40  jnz     short loc_180008A6A
0x180008a42  mov     rcx, [rsp+118h]; this
0x180008a4a  mov     ebx, 80070057h
0x180008a4f  mov     r9d, ebx; char *
0x180008a52  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008a59  mov     edx, 0Ch; void *
0x180008a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a63  mov     eax, ebx
0x180008a65  jmp     loc_180008C8B
0x180008a6a  mov     rcx, rbx; pvarg
0x180008a6d  call    cs:__imp_VariantInit
0x180008a73  mov     [rsp+118h+var_D0], rdi
0x180008a78  mov     [rsp+118h+var_D8], rdi
0x180008a7d  mov     [rsp+118h+String1], rdi
0x180008a82  mov     rcx, [rsi+18h]
0x180008a86  mov     rax, [rcx]
0x180008a89  lea     r8, [rsp+118h+var_D0]
0x180008a8e  mov     edx, 1
0x180008a93  mov     rax, [rax+58h]
0x180008a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a9c  mov     r14d, eax
0x180008a9f  test    eax, eax
0x180008aa1  jns     short loc_180008AC7
0x180008aa3  mov     edx, 14h; void *
0x180008aa8  mov     rcx, [rsp+118h]; this
0x180008ab0  mov     r9d, r14d; char *
0x180008ab3  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008abf  mov     eax, r14d
0x180008ac2  jmp     loc_180008C8B
0x180008ac7  mov     rcx, [rsi+18h]
0x180008acb  mov     rax, [rcx]
0x180008ace  lea     r8, [rsp+118h+var_D8]
0x180008ad3  mov     edx, 2
0x180008ad8  mov     rax, [rax+58h]
0x180008adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae1  mov     r14d, eax
0x180008ae4  test    eax, eax
0x180008ae6  jns     short loc_180008AEF
0x180008ae8  mov     edx, 15h
0x180008aed  jmp     short loc_180008AA8
0x180008aef  mov     rcx, [rsi+18h]
0x180008af3  mov     rax, [rcx]
0x180008af6  lea     r8, [rsp+118h+String1]
0x180008afb  mov     edx, 3
0x180008b00  mov     rax, [rax+58h]
0x180008b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b09  mov     r14d, eax
0x180008b0c  test    eax, eax
0x180008b0e  jns     short loc_180008B17
0x180008b10  mov     edx, 16h
0x180008b15  jmp     short loc_180008AA8
0x180008b17  mov     eax, 7
0x180008b1c  mov     [rsp+118h+var_B0], rax
0x180008b21  mov     [rsp+118h+var_B8], rdi
0x180008b26  mov     [rsp+118h+var_C8], di
0x180008b2b  mov     [rsp+118h+var_90], rax
0x180008b33  mov     [rsp+118h+var_98], rdi
0x180008b3b  mov     word ptr [rsp+118h+psz], di
0x180008b40  mov     [rsp+118h+var_70], rax
0x180008b48  mov     [rsp+118h+var_78], rdi
0x180008b50  mov     [rsp+118h+var_88], di
0x180008b58  mov     [rsp+118h+var_68], edi
0x180008b5f  mov     [rsp+118h+var_64], 1
0x180008b6a  lea     r9, [rsp+118h+var_C8]; struct Command *
0x180008b6f  mov     r8, [rsp+118h+String1]; String1
0x180008b74  mov     rdx, [rsp+118h+var_D8]; unsigned __int16 *
0x180008b79  mov     rcx, [rsp+118h+var_D0]; unsigned __int16 *
0x180008b7e  call    ?FindCommand@CProvisioningCommandsNode@@CAJPEBG00PEAUCommand@@@Z; CProvisioningCommandsNode::FindCommand(ushort const *,ushort const *,ushort const *,Command *)
0x180008b83  mov     r14d, eax
0x180008b86  test    eax, eax
0x180008b88  jns     short loc_180008BB6
0x180008b8a  mov     rcx, [rsp+118h]; this
0x180008b92  mov     r9d, eax; char *
0x180008b95  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008b9c  mov     edx, 19h; void *
0x180008ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ba6  nop
0x180008ba7  lea     rcx, [rsp+118h+var_C8]; this
0x180008bac  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008bb1  jmp     loc_180008ABF
0x180008bb6  mov     word ptr [rbx], 13h
0x180008bbb  mov     r8d, [rsi+2Ch]
0x180008bbf  sub     r8d, 4
0x180008bc3  jz      loc_180008C4A
0x180008bc9  sub     r8d, 4
0x180008bcd  jz      short loc_180008C4A
0x180008bcf  sub     r8d, 1
0x180008bd3  jz      short loc_180008C3E
0x180008bd5  sub     r8d, 1
0x180008bd9  jz      short loc_180008C35
0x180008bdb  sub     r8d, 1
0x180008bdf  jz      short loc_180008C2C
0x180008be1  cmp     r8d, 1
0x180008be5  jz      short loc_180008C23
0x180008be7  mov     rdx, rbx; struct tagVARIANT *
0x180008bea  mov     rcx, rsi; this
0x180008bed  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x180008bf2  mov     ebx, eax
0x180008bf4  test    eax, eax
0x180008bf6  jns     short loc_180008C6F
0x180008bf8  mov     rcx, [rsp+118h]; this
0x180008c00  mov     r9d, eax; char *
0x180008c03  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008c0a  mov     edx, 3Fh ; '?'; void *
0x180008c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c14  nop
0x180008c15  lea     rcx, [rsp+118h+var_C8]; this
0x180008c1a  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008c1f  mov     eax, ebx
0x180008c21  jmp     short loc_180008C8B
0x180008c23  mov     eax, [rsp+118h+var_64]
0x180008c2a  jmp     short loc_180008C45
0x180008c2c  mov     eax, [rsp+118h+var_68]
0x180008c33  jmp     short loc_180008C45
0x180008c35  mov     eax, [rsp+118h+var_5C]
0x180008c3c  jmp     short loc_180008C45
0x180008c3e  mov     eax, [rsp+118h+var_60]
0x180008c45  mov     [rbx+8], eax
0x180008c48  jmp     short loc_180008C6F
0x180008c4a  mov     eax, 8
0x180008c4f  mov     [rbx], ax
0x180008c52  lea     rcx, [rsp+118h+psz]
0x180008c57  cmp     [rsp+118h+var_90], rax
0x180008c5f  cmovnb  rcx, [rsp+118h+psz]; psz
0x180008c65  call    cs:__imp_SysAllocString
0x180008c6b  mov     [rbx+8], rax
0x180008c6f  lea     rcx, [rsp+118h+var_C8]; this
0x180008c74  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008c79  xor     eax, eax
0x180008c7b  jmp     short loc_180008C8B
0x180008c7d  lea     rcx, [rsp+118h+var_C8]; this
0x180008c82  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008c87  mov     eax, [rsp+118h+var_E8]
0x180008c8b  mov     rcx, [rsp+118h+var_28]
0x180008c93  xor     rcx, rsp; StackCookie
0x180008c96  call    __security_check_cookie
0x180008c9b  mov     rbx, [rsp+118h+arg_10]
0x180008ca3  add     rsp, 100h
0x180008caa  pop     r14
0x180008cac  pop     rdi
0x180008cad  pop     rsi
0x180008cae  retn
```
