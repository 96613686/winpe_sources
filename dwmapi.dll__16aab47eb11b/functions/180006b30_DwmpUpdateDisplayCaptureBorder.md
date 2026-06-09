# DwmpUpdateDisplayCaptureBorder

- ea: `0x180006b30`
- end: `0x180006bcf`
- name: `DwmpUpdateDisplayCaptureBorder`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x180006b30`
- `0x18000af44`
- `0x18000bab0`

## string_xrefs

- `0x180006bb5`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUpdateDisplayCaptureBorder(CApiPortClient *a1, int a2)
{
  int v2; // ebx
  __int64 v4; // rdx
  int v5; // [rsp+20h] [rbp-58h]
  unsigned int v6; // [rsp+40h] [rbp-38h] BYREF
  CApiPortClient *v7; // [rsp+44h] [rbp-34h]
  int v8; // [rsp+4Ch] [rbp-2Ch]
  void **v9; // [rsp+50h] [rbp-28h] BYREF
  __int128 v10; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v12; // [rsp+88h] [rbp+10h] BYREF

  v6 = 1073741961;
  v9 = &CStandardData::`vftable';
  v7 = a1;
  v8 = a2;
  v12 = 0;
  v10 = 0;
  v2 = CApiPortClient::SendRequest(a1, &v6, 16, (const struct CAlpcView **)&v9, &v12, 0, 0);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v10 + 8);
  if ( v2 < 0 )
  {
    v4 = 412;
  }
  else
  {
    v2 = v12;
    if ( v12 >= 0 )
      return 0;
    v4 = 413;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006b30  mov     r11, rsp
0x180006b33  push    rbx
0x180006b34  sub     rsp, 70h
0x180006b38  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180006b3f  mov     [rsp+78h+var_38], 40000089h
0x180006b47  mov     [r11-28h], rax
0x180006b4b  lea     r9, [r11-28h]; struct CStandardData *
0x180006b4f  xor     eax, eax
0x180006b51  mov     [r11-34h], rcx
0x180006b55  mov     [rsp+78h+var_48], ax; __int16
0x180006b5a  xorps   xmm0, xmm0
0x180006b5d  mov     [r11-50h], rax
0x180006b61  mov     [rsp+78h+var_2C], edx
0x180006b65  lea     rdx, [r11-38h]; void *
0x180006b69  lea     r8d, [rax+10h]; __int16
0x180006b6d  mov     dword ptr [r11+10h], 0
0x180006b75  lea     rax, [r11+10h]
0x180006b79  mov     [r11-58h], rax
0x180006b7d  movdqu  [rsp+78h+var_20], xmm0
0x180006b83  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x180006b88  lea     rcx, [rsp+78h+var_20+8]
0x180006b8d  mov     ebx, eax
0x180006b8f  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180006b94  test    ebx, ebx
0x180006b96  js      short loc_180006BAB
0x180006b98  mov     ebx, [rsp+78h+arg_8]
0x180006b9f  test    ebx, ebx
0x180006ba1  js      short loc_180006BC8
0x180006ba3  xor     eax, eax
0x180006ba5  add     rsp, 70h
0x180006ba9  pop     rbx
0x180006baa  retn
0x180006bab  mov     edx, 19Ch; void *
0x180006bb0  mov     rcx, [rsp+78h]; this
0x180006bb5  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180006bbc  mov     r9d, ebx; char *
0x180006bbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bc4  mov     eax, ebx
0x180006bc6  jmp     short loc_180006BA5
0x180006bc8  mov     edx, 19Dh
0x180006bcd  jmp     short loc_180006BB0
```
