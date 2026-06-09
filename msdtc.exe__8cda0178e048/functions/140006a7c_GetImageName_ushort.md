# GetImageName(ushort * *)

- ea: `0x140006a7c`
- end: `0x140006b5f`
- name: `?GetImageName@@YAJPEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b68`

## callees

- `0x1400027a4`
- `0x140002ed4`
- `0x140006844`
- `0x140006a7c`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b32`

## pseudocode

```c
__int64 __fastcall GetImageName(unsigned __int16 **a1)
{
  int ExeNameAndAppId; // eax
  unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  LPVOID pv; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-228h] BYREF

  pv = 0;
  v8 = 0;
  ExeNameAndAppId = GetExeNameAndAppId((unsigned __int16 **)&pv, &v8);
  v3 = v8;
  v4 = ExeNameAndAppId;
  if ( ExeNameAndAppId >= 0 )
  {
    v5 = v8 ? StringCbPrintfW(v9, 0x20Au, L"%s-%s", pv, v8) : StringCbPrintfW(v9, 0x20Au, L"%s", pv);
    v4 = v5;
    if ( v5 >= 0 )
      v4 = DuplicateString(v9, a1);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v3 )
    CoTaskMemFree(v3);
  return v4;
}

```

## disassembly

```asm
0x140006a7c  mov     [rsp+arg_8], rbx
0x140006a81  mov     [rsp+arg_10], rbp
0x140006a86  push    rdi
0x140006a87  sub     rsp, 260h
0x140006a8e  mov     rax, cs:__security_cookie
0x140006a95  xor     rax, rsp
0x140006a98  mov     [rsp+268h+var_18], rax
0x140006aa0  mov     rbp, rcx
0x140006aa3  mov     [rsp+268h+pv], 0
0x140006aac  lea     rcx, [rsp+268h+pv]; unsigned __int16 **
0x140006ab1  mov     [rsp+268h+var_230], 0
0x140006aba  lea     rdx, [rsp+268h+var_230]; unsigned __int16 **
0x140006abf  call    ?GetExeNameAndAppId@@YAJPEAPEAG0@Z; GetExeNameAndAppId(ushort * *,ushort * *)
0x140006ac4  mov     rdi, [rsp+268h+var_230]
0x140006ac9  mov     ebx, eax
0x140006acb  test    eax, eax
0x140006acd  js      short loc_140006B17
0x140006acf  mov     r9, [rsp+268h+pv]
0x140006ad4  mov     edx, 20Ah; unsigned __int64
0x140006ad9  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x140006ade  test    rdi, rdi
0x140006ae1  jz      short loc_140006AF6
0x140006ae3  lea     r8, aSS; "%s-%s"
0x140006aea  mov     [rsp+268h+var_248], rdi
0x140006aef  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006af4  jmp     short loc_140006B02
0x140006af6  lea     r8, aS; "%s"
0x140006afd  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006b02  mov     ebx, eax
0x140006b04  test    eax, eax
0x140006b06  js      short loc_140006B17
0x140006b08  mov     rdx, rbp; unsigned __int16 **
0x140006b0b  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x140006b10  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x140006b15  mov     ebx, eax
0x140006b17  cmp     [rsp+268h+pv], 0
0x140006b1d  jz      short loc_140006B2A
0x140006b1f  mov     rcx, [rsp+268h+pv]; pv
0x140006b24  call    cs:__imp_CoTaskMemFree
0x140006b2a  test    rdi, rdi
0x140006b2d  jz      short loc_140006B38
0x140006b2f  mov     rcx, rdi; pv
0x140006b32  call    cs:__imp_CoTaskMemFree
0x140006b38  mov     eax, ebx
0x140006b3a  mov     rcx, [rsp+268h+var_18]
0x140006b42  xor     rcx, rsp; StackCookie
0x140006b45  call    __security_check_cookie
0x140006b4a  lea     r11, [rsp+268h+var_8]
0x140006b52  mov     rbx, [r11+18h]
0x140006b56  mov     rbp, [r11+20h]
0x140006b5a  mov     rsp, r11
0x140006b5d  pop     rdi
0x140006b5e  retn
```
