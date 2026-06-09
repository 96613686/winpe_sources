# XmlParseDocument(basic_xstr_t<wchar_t> const &,XmlNode * *,INamespaceToId const *)

- ea: `0x18001edc0`
- end: `0x18001eeab`
- name: `?XmlParseDocument@@YAPEB_WAEBV?$basic_xstr_t@_W@@PEAPEAVXmlNode@@PEBVINamespaceToId@@@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d3e4`

## callees

- `0x1800022d6`
- `0x18000a33c`
- `0x18001ec80`
- `0x18001edc0`
- `0x18001f0cc`
- `0x18001f6d4`
- `0x18001fcc0`
- `0x180020130`
- `0x180020240`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XmlParseDocument(int *a1)
{
  __int64 v1; // rdi
  const wchar_t *v2; // rbx
  wchar_t *v3; // rbx
  const struct INamespaceToId *v4; // rdx
  __int64 v5; // rbx
  __int64 v7[4]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-28h] BYREF

  v1 = *((_QWORD *)a1 + 1) + 2LL * *a1;
  v2 = (const wchar_t *)skip_misc(*((_QWORD *)a1 + 1), v1);
  if ( (unsigned __int8)is_start_sub_str(L"<!DOCTYPE", L"", v2, v1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_0d715812294c36d66968236745223d1f_Traceguids);
    bad_document::bad_document((bad_document *)pExceptionObject, v2);
    throw (bad_document *)pExceptionObject;
  }
  v3 = (wchar_t *)skip_misc(v2, v1);
  CNameSpaceInfo::CNameSpaceInfo((CNameSpaceInfo *)v7, v4);
  v5 = parse_element(v3, (__int64)v7);
  CNameSpaceInfo::~CNameSpaceInfo((CNameSpaceInfo *)v7);
  return v5;
}

```

## disassembly

```asm
0x18001edc0  mov     [rsp+arg_0], rbx
0x18001edc5  mov     [rsp+arg_8], rsi
0x18001edca  push    rdi
0x18001edcb  sub     rsp, 70h
0x18001edcf  mov     rsi, rdx
0x18001edd2  mov     r8, [rcx+8]
0x18001edd6  movsxd  rax, dword ptr [rcx]
0x18001edd9  lea     rdi, [r8+rax*2]
0x18001eddd  mov     rdx, rdi
0x18001ede0  mov     rcx, r8
0x18001ede3  call    skip_misc
0x18001ede8  mov     rbx, rax
0x18001edeb  mov     r9, rdi
0x18001edee  mov     r8, rax
0x18001edf1  lea     rdx, aDoctype+12h; ""
0x18001edf8  lea     rcx, aDoctype; "<!DOCTYPE"
0x18001edff  call    is_start_sub_str
0x18001ee04  test    al, al
0x18001ee06  jz      short loc_18001EE55
0x18001ee08  lea     rax, WPP_GLOBAL_Control
0x18001ee0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee16  cmp     rcx, rax
0x18001ee19  jz      short loc_18001EE36
0x18001ee1b  test    byte ptr [rcx+1Ch], 1
0x18001ee1f  jz      short loc_18001EE36
0x18001ee21  mov     edx, 0Dh
0x18001ee26  lea     r8, WPP_0d715812294c36d66968236745223d1f_Traceguids
0x18001ee2d  mov     rcx, [rcx+10h]
0x18001ee31  call    WPP_SF_
0x18001ee36  mov     rdx, rbx; wchar_t *
0x18001ee39  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001ee3e  call    ??0bad_document@@QEAA@PEB_W@Z; bad_document::bad_document(wchar_t const *)
0x18001ee43  lea     rdx, _TI2?AVbad_document@@; pThrowInfo
0x18001ee4a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001ee4f  call    _CxxThrowException_0
0x18001ee55  mov     rdx, rdi
0x18001ee58  mov     rcx, rbx
0x18001ee5b  call    skip_misc
0x18001ee60  mov     rbx, rax
0x18001ee63  lea     rcx, [rsp+78h+var_48]; this
0x18001ee68  call    ??0CNameSpaceInfo@@QEAA@PEBVINamespaceToId@@@Z; CNameSpaceInfo::CNameSpaceInfo(INamespaceToId const *)
0x18001ee6d  nop
0x18001ee6e  lea     rax, [rsp+78h+var_48]
0x18001ee73  mov     [rsp+78h+var_58], rax; __int64
0x18001ee78  mov     r9, rsi
0x18001ee7b  xor     r8d, r8d
0x18001ee7e  mov     rdx, rdi
0x18001ee81  mov     rcx, rbx; wchar_t *
0x18001ee84  call    parse_element
0x18001ee89  mov     rbx, rax
0x18001ee8c  lea     rcx, [rsp+78h+var_48]; this
0x18001ee91  call    ??1CNameSpaceInfo@@QEAA@XZ; CNameSpaceInfo::~CNameSpaceInfo(void)
0x18001ee96  mov     rax, rbx
0x18001ee99  lea     r11, [rsp+78h+var_8]
0x18001ee9e  mov     rbx, [r11+10h]
0x18001eea2  mov     rsi, [r11+18h]
0x18001eea6  mov     rsp, r11
0x18001eea9  pop     rdi
0x18001eeaa  retn
```
