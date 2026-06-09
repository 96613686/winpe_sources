# CProvisioningCommandsNode::GetValue(tagVARIANT *)

- ea: `0x180008dd0`
- end: `0x1800090cc`
- name: `?GetValue@CProvisioningCommandsNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `764`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001090`
- `0x180004ee4`
- `0x18000751c`
- `0x180008dd0`
- `0x180009ff0`
- `0x18000a554`
- `0x18000ccc0`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000907b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000907b`
- `OLEAUT32!__imp_VariantInit` at `0x180008e7d`
- `OLEAUT32!__imp_VariantInit` at `0x180008e7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  _WORD v17[8]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-B8h]
  __int64 v19; // [rsp+68h] [rbp-B0h]
  OLECHAR *psz[3]; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int64 v21; // [rsp+88h] [rbp-90h]
  __int16 v22; // [rsp+90h] [rbp-88h]
  __int64 v23; // [rsp+A0h] [rbp-78h]
  __int64 v24; // [rsp+A8h] [rbp-70h]
  LONG v25; // [rsp+B0h] [rbp-68h]
  int v26; // [rsp+B4h] [rbp-64h]
  LONG v27; // [rsp+B8h] [rbp-60h]
  LONG v28; // [rsp+BCh] [rbp-5Ch]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+C0h] [rbp-58h] BYREF
  int *v30; // [rsp+E0h] [rbp-38h]
  __int64 v31; // [rsp+E8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( (unsigned int)dword_180014230 > 4 )
  {
    v13 = *((_DWORD *)this + 11);
    v30 = &v13;
    v31 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, (unsigned __int8 *)&word_180010966, 0, 0, 3u, &v29);
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
  v19 = 7;
  v18 = 0;
  v17[0] = 0;
  v21 = 7;
  psz[2] = 0;
  LOWORD(psz[0]) = 0;
  v24 = 7;
  v23 = 0;
  v22 = 0;
  v25 = 0;
  v26 = 1;
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
    Command::~Command((Command *)v17);
    return (unsigned int)v5;
  }
  a2->vt = 19;
  switch ( *((_DWORD *)this + 11) )
  {
    case 4:
    case 8:
      a2->vt = 8;
      v11 = (const OLECHAR *)psz;
      if ( v21 >= 8 )
        v11 = psz[0];
      a2->llVal = (LONGLONG)SysAllocString(v11);
      goto LABEL_31;
    case 9:
      v10 = v27;
      goto LABEL_27;
    case 0xA:
      v10 = v28;
      goto LABEL_27;
    case 0xB:
      v10 = v25;
      goto LABEL_27;
    case 0xC:
      v10 = v26;
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
    Command::~Command((Command *)v17);
    return v9;
  }
LABEL_31:
  Command::~Command((Command *)v17);
  return 0;
}

```

## disassembly

```asm
0x180008dd0  mov     r11, rsp
0x180008dd3  mov     [r11+18h], rbx
0x180008dd7  push    rsi
0x180008dd8  push    rdi
0x180008dd9  push    r14
0x180008ddb  sub     rsp, 100h
0x180008de2  mov     rax, cs:__security_cookie
0x180008de9  xor     rax, rsp
0x180008dec  mov     [rsp+118h+var_28], rax
0x180008df4  mov     rbx, rdx
0x180008df7  mov     rsi, rcx
0x180008dfa  mov     eax, cs:dword_180014230
0x180008e00  cmp     eax, 4
0x180008e03  jbe     short loc_180008E4B
0x180008e05  mov     eax, [rcx+2Ch]
0x180008e08  mov     [rsp+118h+var_E8], eax
0x180008e0c  lea     rax, [rsp+118h+var_E8]
0x180008e11  mov     [r11-38h], rax
0x180008e15  mov     qword ptr [r11-30h], 4
0x180008e1d  xor     edi, edi
0x180008e1f  lea     rax, [r11-58h]
0x180008e23  mov     [rsp+118h+var_F0], rax
0x180008e28  mov     [rsp+118h+var_F8], 3
0x180008e30  xor     r9d, r9d
0x180008e33  xor     r8d, r8d
0x180008e36  lea     rdx, word_180010966
0x180008e3d  lea     rcx, dword_180014230
0x180008e44  call    _tlgWriteTransfer_EventWriteTransfer
0x180008e49  jmp     short loc_180008E4D
0x180008e4b  xor     edi, edi
0x180008e4d  test    rbx, rbx
0x180008e50  jnz     short loc_180008E7A
0x180008e52  mov     rcx, [rsp+118h]; this
0x180008e5a  mov     ebx, 80070057h
0x180008e5f  mov     r9d, ebx; char *
0x180008e62  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008e69  mov     edx, 0Ch; void *
0x180008e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e73  mov     eax, ebx
0x180008e75  jmp     loc_1800090A7
0x180008e7a  mov     rcx, rbx; pvarg
0x180008e7d  call    cs:__imp_VariantInit
0x180008e84  nop     dword ptr [rax+rax+00h]
0x180008e89  mov     [rsp+118h+var_D0], rdi
0x180008e8e  mov     [rsp+118h+var_D8], rdi
0x180008e93  mov     [rsp+118h+String1], rdi
0x180008e98  mov     rcx, [rsi+18h]
0x180008e9c  mov     rax, [rcx]
0x180008e9f  lea     r8, [rsp+118h+var_D0]
0x180008ea4  mov     edx, 1
0x180008ea9  mov     rax, [rax+58h]
0x180008ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb2  mov     r14d, eax
0x180008eb5  test    eax, eax
0x180008eb7  jns     short loc_180008EDD
0x180008eb9  mov     edx, 14h; void *
0x180008ebe  mov     rcx, [rsp+118h]; this
0x180008ec6  mov     r9d, r14d; char *
0x180008ec9  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ed5  mov     eax, r14d
0x180008ed8  jmp     loc_1800090A7
0x180008edd  mov     rcx, [rsi+18h]
0x180008ee1  mov     rax, [rcx]
0x180008ee4  lea     r8, [rsp+118h+var_D8]
0x180008ee9  mov     edx, 2
0x180008eee  mov     rax, [rax+58h]
0x180008ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef7  mov     r14d, eax
0x180008efa  test    eax, eax
0x180008efc  jns     short loc_180008F05
0x180008efe  mov     edx, 15h
0x180008f03  jmp     short loc_180008EBE
0x180008f05  mov     rcx, [rsi+18h]
0x180008f09  mov     rax, [rcx]
0x180008f0c  lea     r8, [rsp+118h+String1]
0x180008f11  mov     edx, 3
0x180008f16  mov     rax, [rax+58h]
0x180008f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f1f  mov     r14d, eax
0x180008f22  test    eax, eax
0x180008f24  jns     short loc_180008F2D
0x180008f26  mov     edx, 16h
0x180008f2b  jmp     short loc_180008EBE
0x180008f2d  mov     eax, 7
0x180008f32  mov     [rsp+118h+var_B0], rax
0x180008f37  mov     [rsp+118h+var_B8], rdi
0x180008f3c  mov     [rsp+118h+var_C8], di
0x180008f41  mov     [rsp+118h+var_90], rax
0x180008f49  mov     [rsp+118h+var_98], rdi
0x180008f51  mov     word ptr [rsp+118h+psz], di
0x180008f56  mov     [rsp+118h+var_70], rax
0x180008f5e  mov     [rsp+118h+var_78], rdi
0x180008f66  mov     [rsp+118h+var_88], di
0x180008f6e  mov     [rsp+118h+var_68], edi
0x180008f75  mov     [rsp+118h+var_64], 1
0x180008f80  lea     r9, [rsp+118h+var_C8]; struct Command *
0x180008f85  mov     r8, [rsp+118h+String1]; String1
0x180008f8a  mov     rdx, [rsp+118h+var_D8]; unsigned __int16 *
0x180008f8f  mov     rcx, [rsp+118h+var_D0]; unsigned __int16 *
0x180008f94  call    ?FindCommand@CProvisioningCommandsNode@@CAJPEBG00PEAUCommand@@@Z; CProvisioningCommandsNode::FindCommand(ushort const *,ushort const *,ushort const *,Command *)
0x180008f99  mov     r14d, eax
0x180008f9c  test    eax, eax
0x180008f9e  jns     short loc_180008FCC
0x180008fa0  mov     rcx, [rsp+118h]; this
0x180008fa8  mov     r9d, eax; char *
0x180008fab  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180008fb2  mov     edx, 19h; void *
0x180008fb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fbc  nop
0x180008fbd  lea     rcx, [rsp+118h+var_C8]; this
0x180008fc2  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008fc7  jmp     loc_180008ED5
0x180008fcc  mov     word ptr [rbx], 13h
0x180008fd1  mov     r8d, [rsi+2Ch]
0x180008fd5  sub     r8d, 4
0x180008fd9  jz      loc_180009060
0x180008fdf  sub     r8d, 4
0x180008fe3  jz      short loc_180009060
0x180008fe5  sub     r8d, 1
0x180008fe9  jz      short loc_180009054
0x180008feb  sub     r8d, 1
0x180008fef  jz      short loc_18000904B
0x180008ff1  sub     r8d, 1
0x180008ff5  jz      short loc_180009042
0x180008ff7  cmp     r8d, 1
0x180008ffb  jz      short loc_180009039
0x180008ffd  mov     rdx, rbx; struct tagVARIANT *
0x180009000  mov     rcx, rsi; this
0x180009003  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x180009008  mov     ebx, eax
0x18000900a  test    eax, eax
0x18000900c  jns     short loc_18000908B
0x18000900e  mov     rcx, [rsp+118h]; this
0x180009016  mov     r9d, eax; char *
0x180009019  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x180009020  mov     edx, 3Fh ; '?'; void *
0x180009025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000902a  nop
0x18000902b  lea     rcx, [rsp+118h+var_C8]; this
0x180009030  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180009035  mov     eax, ebx
0x180009037  jmp     short loc_1800090A7
0x180009039  mov     eax, [rsp+118h+var_64]
0x180009040  jmp     short loc_18000905B
0x180009042  mov     eax, [rsp+118h+var_68]
0x180009049  jmp     short loc_18000905B
0x18000904b  mov     eax, [rsp+118h+var_5C]
0x180009052  jmp     short loc_18000905B
0x180009054  mov     eax, [rsp+118h+var_60]
0x18000905b  mov     [rbx+8], eax
0x18000905e  jmp     short loc_18000908B
0x180009060  mov     eax, 8
0x180009065  mov     [rbx], ax
0x180009068  lea     rcx, [rsp+118h+psz]
0x18000906d  cmp     [rsp+118h+var_90], rax
0x180009075  cmovnb  rcx, [rsp+118h+psz]; psz
0x18000907b  call    cs:__imp_SysAllocString
0x180009082  nop     dword ptr [rax+rax+00h]
0x180009087  mov     [rbx+8], rax
0x18000908b  lea     rcx, [rsp+118h+var_C8]; this
0x180009090  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180009095  xor     eax, eax
0x180009097  jmp     short loc_1800090A7
0x180009099  lea     rcx, [rsp+118h+var_C8]; this
0x18000909e  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x1800090a3  mov     eax, [rsp+118h+var_E8]
0x1800090a7  mov     rcx, [rsp+118h+var_28]
0x1800090af  xor     rcx, rsp; StackCookie
0x1800090b2  call    __security_check_cookie
0x1800090b7  mov     rbx, [rsp+118h+arg_10]
0x1800090bf  add     rsp, 100h
0x1800090c6  pop     r14
0x1800090c8  pop     rdi
0x1800090c9  pop     rsi
0x1800090ca  retn
```
