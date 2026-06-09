# DwmpStopDisplayCapture

- ea: `0x180005bc0`
- end: `0x180005c5b`
- name: `DwmpStopDisplayCapture`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x180005bc0`
- `0x18000af44`
- `0x18000bab0`

## string_xrefs

- `0x180005c2e`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpStopDisplayCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-58h]
  unsigned int v5; // [rsp+40h] [rbp-38h] BYREF
  CApiPortClient *v6; // [rsp+44h] [rbp-34h]
  void **v7; // [rsp+50h] [rbp-28h] BYREF
  __int128 v8; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v10; // [rsp+80h] [rbp+8h] BYREF

  v5 = 1073741958;
  v7 = &CStandardData::`vftable';
  v6 = a1;
  v10 = 0;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, (const struct CAlpcView **)&v7, &v10, 0, 0);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((_QWORD *)&v8 + 1);
  if ( v1 < 0 )
  {
    v2 = 361;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v1,
      v4);
    return (unsigned int)v1;
  }
  v1 = v10;
  if ( v10 < 0 )
  {
    v2 = 362;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180005bc0  mov     r11, rsp
0x180005bc3  push    rbx
0x180005bc4  sub     rsp, 70h
0x180005bc8  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180005bcf  mov     [rsp+78h+var_38], 40000086h
0x180005bd7  mov     [r11-28h], rax
0x180005bdb  lea     r9, [r11-28h]; struct CStandardData *
0x180005bdf  xor     eax, eax
0x180005be1  mov     [r11-34h], rcx
0x180005be5  mov     [rsp+78h+var_48], ax; __int16
0x180005bea  lea     rdx, [r11-38h]; void *
0x180005bee  mov     [r11-50h], rax
0x180005bf2  xorps   xmm0, xmm0
0x180005bf5  mov     dword ptr [r11+8], 0
0x180005bfd  lea     r8d, [rax+0Ch]; __int16
0x180005c01  lea     rax, [r11+8]
0x180005c05  mov     [r11-58h], rax
0x180005c09  movdqu  [rsp+78h+var_20], xmm0
0x180005c0f  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x180005c14  lea     rcx, [rsp+78h+var_20+8]
0x180005c19  mov     ebx, eax
0x180005c1b  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180005c20  test    ebx, ebx
0x180005c22  jns     short loc_180005C45
0x180005c24  mov     edx, 169h; void *
0x180005c29  mov     rcx, [rsp+78h]; this
0x180005c2e  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180005c35  mov     r9d, ebx; char *
0x180005c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c3d  mov     eax, ebx
0x180005c3f  add     rsp, 70h
0x180005c43  pop     rbx
0x180005c44  retn
0x180005c45  mov     ebx, [rsp+78h+arg_0]
0x180005c4c  test    ebx, ebx
0x180005c4e  jns     short loc_180005C57
0x180005c50  mov     edx, 16Ah
0x180005c55  jmp     short loc_180005C29
0x180005c57  xor     eax, eax
0x180005c59  jmp     short loc_180005C3F
```
