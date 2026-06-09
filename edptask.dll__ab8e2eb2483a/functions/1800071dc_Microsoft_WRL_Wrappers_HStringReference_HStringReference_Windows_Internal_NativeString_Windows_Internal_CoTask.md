# Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800071dc`
- end: `0x18000724c`
- name: `??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *hstringHeader, const WCHAR **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x1800071dc`
- `0x18000f250`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007216`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const WCHAR **a2,
        unsigned int a3)
{
  HSTRING *v3; // r9
  const WCHAR *v5; // rcx
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d

  v3 = (HSTRING *)&hstringHeader[1];
  hstringHeader[1].Reserved.Reserved1 = 0;
  v5 = *a2;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    JUMPOUT(0x18000724BLL);
  }
  StringReference = WindowsCreateStringReference(v5, v6, hstringHeader, v3);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
    __debugbreak();
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x1800071dc  mov     [rsp+arg_0], rbx
0x1800071e1  push    rdi
0x1800071e2  sub     rsp, 20h
0x1800071e6  lea     r9, [rcx+18h]; string
0x1800071ea  xor     edi, edi
0x1800071ec  mov     [r9], rdi
0x1800071ef  mov     rbx, rcx
0x1800071f2  mov     rcx, [rdx]; sourceString
0x1800071f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800071f9  inc     rdx; int
0x1800071fc  cmp     [rcx+rdx*2], di
0x180007200  jnz     short loc_1800071F9
0x180007202  mov     eax, 0FFFFFFFFh
0x180007207  cmp     rdx, rax
0x18000720a  ja      short loc_180007236
0x18000720c  lea     eax, [rdx+1]
0x18000720f  cmp     eax, edx
0x180007211  jb      short loc_180007241
0x180007213  mov     r8, rbx; hstringHeader
0x180007216  call    cs:__imp_WindowsCreateStringReference
0x18000721c  test    eax, eax
0x18000721e  js      short loc_18000722E
0x180007220  mov     rax, rbx
0x180007223  mov     rbx, [rsp+28h+arg_0]
0x180007228  add     rsp, 20h
0x18000722c  pop     rdi
0x18000722d  retn
0x18000722e  mov     ecx, eax; this
0x180007230  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180007235  int     3; Trap to Debugger
0x180007236  mov     ecx, 80070216h; this
0x18000723b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180007240  int     3; Trap to Debugger
0x180007241  mov     ecx, 80070216h; this
0x180007246  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
