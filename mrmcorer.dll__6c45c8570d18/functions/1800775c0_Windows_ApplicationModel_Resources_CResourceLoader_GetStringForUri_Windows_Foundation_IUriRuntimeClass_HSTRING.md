# Windows::ApplicationModel::Resources::CResourceLoader::GetStringForUri(Windows::Foundation::IUriRuntimeClass *,HSTRING__ * *)

- ea: `0x1800775c0`
- end: `0x1800776af`
- name: `?GetStringForUri@CResourceLoader@Resources@ApplicationModel@Windows@@UEAAJPEAUIUriRuntimeClass@Foundation@4@PEAPEAUHSTRING__@@@Z`
- size: `239`
- prototype: `int(Windows::ApplicationModel::Resources::CResourceLoader *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18002c8d0`
- `0x1800775c0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800776a7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800776a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007762b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007762b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077697`

## string_xrefs

- `0x18007764c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x18007767b`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::CResourceLoader::GetStringForUri(
        Windows::ApplicationModel::Resources::CResourceLoader *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        HSTRING *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v6 = -2147024809;
    RoOriginateError(2147942487LL);
    return v6;
  }
  string = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 48LL))(
         a2,
         &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)(unsigned int)v5,
      v9);
    if ( string )
      WindowsDeleteString(string);
    return v6;
  }
  v7 = (*(__int64 (__fastcall **)(char *, HSTRING, HSTRING *))(*((_QWORD *)this - 2) + 48LL))(
         (char *)this - 16,
         string,
         a3);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)(unsigned int)v7,
      v9);
    if ( string )
      WindowsDeleteString(string);
    return v6;
  }
  if ( string )
    WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800775c0  mov     r11, rsp
0x1800775c3  mov     [r11+8], rbx
0x1800775c7  mov     [r11+18h], rsi
0x1800775cb  push    rdi; int
0x1800775cc  sub     rsp, 20h
0x1800775d0  mov     rdi, r8
0x1800775d3  mov     r9, rdx
0x1800775d6  mov     rsi, rcx
0x1800775d9  test    rdx, rdx
0x1800775dc  jz      loc_1800776A0
0x1800775e2  mov     qword ptr [r11+10h], 0
0x1800775ea  mov     rax, [rdx]
0x1800775ed  lea     rdx, [r11+10h]
0x1800775f1  mov     rcx, r9
0x1800775f4  mov     rax, [rax+30h]
0x1800775f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775fd  mov     ebx, eax
0x1800775ff  test    eax, eax
0x180077601  js      short loc_180077644
0x180077603  lea     rcx, [rsi-10h]
0x180077607  mov     rax, [rcx]
0x18007760a  mov     r8, rdi
0x18007760d  mov     rdx, [rsp+28h+string]
0x180077612  mov     rax, [rax+30h]
0x180077616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007761b  mov     ebx, eax
0x18007761d  test    eax, eax
0x18007761f  js      short loc_180077673
0x180077621  mov     rcx, [rsp+28h+string]; string
0x180077626  test    rcx, rcx
0x180077629  jz      short loc_180077632
0x18007762b  call    cs:__imp_WindowsDeleteString
0x180077631  nop
0x180077632  xor     eax, eax
0x180077634  mov     rbx, [rsp+28h+arg_0]
0x180077639  mov     rsi, [rsp+28h+arg_10]
0x18007763e  add     rsp, 20h
0x180077642  pop     rdi
0x180077643  retn
0x180077644  mov     rcx, [rsp+28h]; this
0x180077649  mov     r9d, ebx; char *
0x18007764c  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180077653  mov     edx, 0BAh; void *
0x180077658  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007765d  nop
0x18007765e  mov     rcx, [rsp+28h+string]; string
0x180077663  test    rcx, rcx
0x180077666  jz      short loc_18007766F
0x180077668  call    cs:__imp_WindowsDeleteString
0x18007766e  nop
0x18007766f  mov     eax, ebx
0x180077671  jmp     short loc_180077634
0x180077673  mov     rcx, [rsp+28h]; this
0x180077678  mov     r9d, ebx; char *
0x18007767b  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180077682  mov     edx, 0BBh; void *
0x180077687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007768c  nop
0x18007768d  mov     rcx, [rsp+28h+string]; string
0x180077692  test    rcx, rcx
0x180077695  jz      short loc_18007769E
0x180077697  call    cs:__imp_WindowsDeleteString
0x18007769d  nop
0x18007769e  jmp     short loc_18007766F
0x1800776a0  mov     ebx, 80070057h
0x1800776a5  mov     ecx, ebx
0x1800776a7  call    cs:__imp_RoOriginateError
0x1800776ad  jmp     short loc_18007766F
```
