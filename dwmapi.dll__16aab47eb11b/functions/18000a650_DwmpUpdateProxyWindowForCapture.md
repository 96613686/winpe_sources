# DwmpUpdateProxyWindowForCapture

- ea: `0x18000a650`
- end: `0x18000a724`
- name: `DwmpUpdateProxyWindowForCapture`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000a650`
- `0x18000ad58`
- `0x18000b990`
- `0x18000bab0`
- `0x18000d0a0`

## string_xrefs

- `0x18000a6e3`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUpdateProxyWindowForCapture(CApiPortClient *a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-50h]
  int v6; // [rsp+30h] [rbp-40h] BYREF
  void **v7; // [rsp+38h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-30h] BYREF
  int v9; // [rsp+50h] [rbp-20h] BYREF
  CApiPortClient *v10; // [rsp+54h] [rbp-1Ch]
  __int64 v11; // [rsp+5Ch] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v11 = a2;
  v9 = 1073741959;
  v7 = &CStandardData::`vftable';
  v10 = a1;
  v6 = 0;
  v8 = 0;
  v2 = CApiPortClient::SendRequestValidate(a1, &v9, 0x14u, (const struct CExtraData *)&v7, &v6);
  v7 = &CStandardData::`vftable';
  if ( (_QWORD)v8 )
    CApiPortClient::UnlockExtraDataPointer((CApiPortClient *)v8);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v8 + 8);
  if ( v2 < 0 )
  {
    v3 = 378;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v2 = v6;
  if ( v6 < 0 )
  {
    v3 = 379;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a650  mov     [rsp-8+arg_10], rbx
0x18000a655  mov     [rsp-8+arg_18], rdi
0x18000a65a  push    rbp
0x18000a65b  mov     rbp, rsp
0x18000a65e  sub     rsp, 70h
0x18000a662  mov     rax, cs:__security_cookie
0x18000a669  xor     rax, rsp
0x18000a66c  mov     [rbp+var_8], rax
0x18000a670  mov     [rbp+var_14], rdx
0x18000a674  lea     rax, [rbp+var_40]
0x18000a678  xorps   xmm0, xmm0
0x18000a67b  mov     qword ptr [rsp+70h+var_50], rax; int
0x18000a680  lea     rdi, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x18000a687  mov     [rbp+var_20], 40000087h
0x18000a68e  lea     rdx, [rbp+var_20]; void *
0x18000a692  mov     [rbp+var_38], rdi
0x18000a696  lea     r9, [rbp+var_38]; struct CExtraData *
0x18000a69a  mov     [rbp+var_1C], rcx
0x18000a69e  mov     r8d, 14h; unsigned __int64
0x18000a6a4  mov     [rbp+var_40], 0
0x18000a6ab  movdqu  [rbp+var_30], xmm0
0x18000a6b0  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KAEBVCExtraData@@PEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,CExtraData const &,long *)
0x18000a6b5  mov     rcx, qword ptr [rbp+var_30]
0x18000a6b9  mov     ebx, eax
0x18000a6bb  mov     [rbp+var_38], rdi
0x18000a6bf  test    rcx, rcx
0x18000a6c2  jz      short loc_18000A6CD
0x18000a6c4  lea     rdx, [rbp+var_30+8]
0x18000a6c8  call    ?UnlockExtraDataPointer@CApiPortClient@@QEAAX$$QEAV?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@@Z; CApiPortClient::UnlockExtraDataPointer(std::unique_ptr<CAlpcView> &&)
0x18000a6cd  lea     rcx, [rbp+var_30+8]
0x18000a6d1  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x18000a6d6  test    ebx, ebx
0x18000a6d8  jns     short loc_18000A6F6
0x18000a6da  mov     edx, 17Ah; void *
0x18000a6df  mov     rcx, [rbp+8]; this
0x18000a6e3  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18000a6ea  mov     r9d, ebx; char *
0x18000a6ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6f2  mov     eax, ebx
0x18000a6f4  jmp     short loc_18000A706
0x18000a6f6  mov     ebx, [rbp+var_40]
0x18000a6f9  test    ebx, ebx
0x18000a6fb  jns     short loc_18000A704
0x18000a6fd  mov     edx, 17Bh
0x18000a702  jmp     short loc_18000A6DF
0x18000a704  xor     eax, eax
0x18000a706  mov     rcx, [rbp+var_8]
0x18000a70a  xor     rcx, rsp; StackCookie
0x18000a70d  call    __security_check_cookie
0x18000a712  lea     r11, [rsp+70h+var_s0]
0x18000a717  mov     rbx, [r11+20h]
0x18000a71b  mov     rdi, [r11+28h]
0x18000a71f  mov     rsp, r11
0x18000a722  pop     rbp
0x18000a723  retn
```
