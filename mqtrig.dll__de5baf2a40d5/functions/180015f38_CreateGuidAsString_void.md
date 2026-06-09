# CreateGuidAsString(void)

- ea: `0x180015f38`
- end: `0x18001601c`
- name: `?CreateGuidAsString@@YA?AV_bstr_t@@XZ`
- size: `228`
- prototype: `_bstr_t *__fastcall(_bstr_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a300`
- `0x180010590`

## callees

- `0x18000544c`
- `0x180012c84`
- `0x18001e380`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180015f72`
- `ole32!CoCreateGuid` at `0x180015f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_bstr_t *__fastcall CreateGuidAsString(_bstr_t *a1)
{
  int Data2; // [rsp+20h] [rbp-89h]
  int Data3; // [rsp+28h] [rbp-81h]
  int v5; // [rsp+30h] [rbp-79h]
  int v6; // [rsp+38h] [rbp-71h]
  int v7; // [rsp+40h] [rbp-69h]
  int v8; // [rsp+48h] [rbp-61h]
  int v9; // [rsp+50h] [rbp-59h]
  int v10; // [rsp+58h] [rbp-51h]
  int v11; // [rsp+60h] [rbp-49h]
  int v12; // [rsp+68h] [rbp-41h]
  GUID pguid; // [rsp+78h] [rbp-31h] BYREF
  wchar_t v14[40]; // [rsp+90h] [rbp-19h] BYREF

  pguid = 0;
  CoCreateGuid(&pguid);
  v12 = pguid.Data4[7];
  v11 = pguid.Data4[6];
  v10 = pguid.Data4[5];
  v9 = pguid.Data4[4];
  v8 = pguid.Data4[3];
  v7 = pguid.Data4[2];
  v6 = pguid.Data4[1];
  v5 = pguid.Data4[0];
  Data3 = pguid.Data3;
  Data2 = pguid.Data2;
  StringCchPrintfW(
    v14,
    0x25u,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    pguid.Data1,
    Data2,
    Data3,
    v5,
    v6,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12);
  _bstr_t::_bstr_t(a1, v14);
  return a1;
}

```

## disassembly

```asm
0x180015f38  mov     [rsp-8+arg_8], rbx
0x180015f3d  mov     [rsp-8+arg_10], rsi
0x180015f42  push    rbp
0x180015f43  push    rdi
0x180015f44  push    r14
0x180015f46  lea     rbp, [rsp-47h]
0x180015f4b  sub     rsp, 0F0h
0x180015f52  mov     rax, cs:__security_cookie
0x180015f59  xor     rax, rsp
0x180015f5c  mov     [rbp+57h+var_20], rax
0x180015f60  mov     qword ptr [rbp+57h+pguid.Data1], rcx
0x180015f64  mov     r14, rcx
0x180015f67  xorps   xmm0, xmm0
0x180015f6a  lea     rcx, [rbp+57h+pguid]; pguid
0x180015f6e  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180015f72  call    cs:__imp_CoCreateGuid
0x180015f78  movzx   ecx, [rbp+57h+pguid.Data4+6]
0x180015f7c  movzx   edx, [rbp+57h+pguid.Data4+5]
0x180015f80  movzx   r8d, [rbp+57h+pguid.Data4+4]
0x180015f85  movzx   r9d, [rbp+57h+pguid.Data4+3]
0x180015f8a  movzx   eax, [rbp+57h+pguid.Data4+7]
0x180015f8e  movzx   r10d, [rbp+57h+pguid.Data4+2]
0x180015f93  movzx   r11d, [rbp+57h+pguid.Data4+1]
0x180015f98  movzx   ebx, [rbp+57h+pguid.Data4]
0x180015f9c  movzx   edi, [rbp+57h+pguid.Data3]
0x180015fa0  movzx   esi, [rbp+57h+pguid.Data2]
0x180015fa4  mov     [rsp+100h+var_98], eax
0x180015fa8  mov     [rsp+100h+var_A0], ecx
0x180015fac  lea     rcx, [rbp+57h+var_70]; wchar_t *
0x180015fb0  mov     [rsp+100h+var_A8], edx
0x180015fb4  mov     edx, 25h ; '%'; unsigned __int64
0x180015fb9  mov     [rsp+100h+var_B0], r8d
0x180015fbe  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180015fc5  mov     [rsp+100h+var_B8], r9d
0x180015fca  mov     r9d, [rbp+57h+pguid.Data1]
0x180015fce  mov     [rsp+100h+var_C0], r10d
0x180015fd3  mov     [rsp+100h+var_C8], r11d
0x180015fd8  mov     [rsp+100h+var_D0], ebx
0x180015fdc  mov     [rsp+100h+var_D8], edi
0x180015fe0  mov     [rsp+100h+var_E0], esi
0x180015fe4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180015fe9  lea     rdx, [rbp+57h+var_70]; wchar_t *
0x180015fed  mov     rcx, r14; this
0x180015ff0  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180015ff5  mov     rax, r14
0x180015ff8  mov     rcx, [rbp+57h+var_20]
0x180015ffc  xor     rcx, rsp; StackCookie
0x180015fff  call    __security_check_cookie
0x180016004  lea     r11, [rsp+100h+var_10]
0x18001600c  mov     rbx, [r11+28h]
0x180016010  mov     rsi, [r11+30h]
0x180016014  mov     rsp, r11
0x180016017  pop     r14
0x180016019  pop     rdi
0x18001601a  pop     rbp
0x18001601b  retn
```
