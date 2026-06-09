# CNfsXmlSharePermission::NfsXmlReadPermissionEntryAttributes(IXMLDOMNode *)

- ea: `0x180027fa0`
- end: `0x180028141`
- name: `?NfsXmlReadPermissionEntryAttributes@CNfsXmlSharePermission@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(CNfsXmlSharePermission *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180027d18`

## callees

- `0x18000ec88`
- `0x18000efc8`
- `0x180027fa0`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002808e`
- `msvcrt!_wcsicmp` at `0x1800280a6`
- `msvcrt!_wcsicmp` at `0x1800280ba`
- `msvcrt!_wcsicmp` at `0x1800280e1`
- `msvcrt!_wcsicmp` at `0x18002808e`
- `msvcrt!_wcsicmp` at `0x1800280a6`
- `msvcrt!_wcsicmp` at `0x1800280ba`
- `msvcrt!_wcsicmp` at `0x1800280e1`
- `OLEAUT32!__imp_VariantInit` at `0x180027fe4`
- `OLEAUT32!__imp_VariantInit` at `0x180027fe4`

## string_xrefs

- `0x180028087`: `RootAccess`

## pseudocode

```c
__int64 __fastcall CNfsXmlSharePermission::NfsXmlReadPermissionEntryAttributes(
        CNfsXmlSharePermission *this,
        struct IXMLDOMNode *a2)
{
  int i; // ebx
  unsigned int v5; // edi
  const wchar_t *bstrVal; // r14
  bool v7; // al
  __int64 v8; // rax
  wchar_t *String1; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+38h] BYREF
  __int64 v13; // [rsp+80h] [rbp+40h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  v14 = 0;
  v12 = 0;
  v13 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  String1 = 0;
  VariantInit(&pvarg);
  i = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_attributes)(a2, &v14);
  if ( i >= 0 )
  {
    v5 = 0;
    for ( i = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 88LL))(v14, &v12); i >= 0; v13 = 0 )
    {
      if ( v5 >= v12 )
        break;
      i = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 80LL))(v14, v5, &v13);
      if ( i >= 0 )
      {
        i = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v13 + 56LL))(v13, &String1);
        if ( i >= 0 )
          i = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v13 + 64LL))(v13, &pvarg);
        if ( _wcsicmp(String1, L"RootAccess") )
        {
          if ( _wcsicmp(String1, L"Type") )
          {
            i = -2147024809;
          }
          else
          {
            v8 = std::char_traits<unsigned short>::length(pvarg.llVal);
            std::wstring::assign((char *)this + 32, pvarg.llVal, v8);
            *((_BYTE *)this + 137) = 1;
          }
        }
        else
        {
          bstrVal = pvarg.bstrVal;
          v7 = _wcsicmp(pvarg.bstrVal, L"false") && _wcsicmp(bstrVal, L"0");
          *((_BYTE *)this + 96) = v7;
          *((_BYTE *)this + 139) = 1;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      ++v5;
    }
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180027fa0  push    rbp
0x180027fa2  push    rbx
0x180027fa3  push    rsi
0x180027fa4  push    rdi
0x180027fa5  push    r14
0x180027fa7  mov     rbp, rsp
0x180027faa  sub     rsp, 40h
0x180027fae  mov     rsi, rcx
0x180027fb1  mov     [rbp+arg_18], 0
0x180027fb9  xorps   xmm0, xmm0
0x180027fbc  mov     [rbp+arg_8], 0
0x180027fc3  xor     eax, eax
0x180027fc5  mov     [rbp+arg_10], 0
0x180027fcd  lea     rcx, [rbp+pvarg]; pvarg
0x180027fd1  mov     qword ptr [rbp+pvarg+10h], rax
0x180027fd5  movups  xmmword ptr [rbp+pvarg], xmm0
0x180027fd9  mov     rbx, rdx
0x180027fdc  mov     [rbp+String1], 0
0x180027fe4  call    cs:__imp_VariantInit
0x180027fea  mov     rax, [rbx]
0x180027fed  lea     rdx, [rbp+arg_18]
0x180027ff1  mov     rcx, rbx
0x180027ff4  mov     rax, [rax+88h]
0x180027ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028000  mov     ebx, eax
0x180028002  test    eax, eax
0x180028004  js      loc_180028134
0x18002800a  mov     rcx, [rbp+arg_18]
0x18002800e  lea     rdx, [rbp+arg_8]
0x180028012  mov     rax, [rcx]
0x180028015  mov     rax, [rax+58h]
0x180028019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002801e  xor     edi, edi
0x180028020  mov     ebx, eax
0x180028022  test    eax, eax
0x180028024  js      loc_180028134
0x18002802a  cmp     edi, [rbp+arg_8]
0x18002802d  jnb     loc_180028134
0x180028033  mov     rcx, [rbp+arg_18]
0x180028037  lea     r8, [rbp+arg_10]
0x18002803b  mov     edx, edi
0x18002803d  mov     rax, [rcx]
0x180028040  mov     rax, [rax+50h]
0x180028044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028049  mov     ebx, eax
0x18002804b  test    eax, eax
0x18002804d  js      loc_180028122
0x180028053  mov     rcx, [rbp+arg_10]
0x180028057  lea     rdx, [rbp+String1]
0x18002805b  mov     rax, [rcx]
0x18002805e  mov     rax, [rax+38h]
0x180028062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028067  mov     ebx, eax
0x180028069  test    eax, eax
0x18002806b  js      short loc_180028083
0x18002806d  mov     rcx, [rbp+arg_10]
0x180028071  lea     rdx, [rbp+pvarg]
0x180028075  mov     rax, [rcx]
0x180028078  mov     rax, [rax+40h]
0x18002807c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028081  mov     ebx, eax
0x180028083  mov     rcx, [rbp+String1]; String1
0x180028087  lea     rdx, aRootaccess; "RootAccess"
0x18002808e  call    cs:__imp__wcsicmp
0x180028094  test    eax, eax
0x180028096  jnz     short loc_1800280D6
0x180028098  mov     r14, qword ptr [rbp+pvarg+8]
0x18002809c  lea     rdx, aFalse; "false"
0x1800280a3  mov     rcx, r14; String1
0x1800280a6  call    cs:__imp__wcsicmp
0x1800280ac  test    eax, eax
0x1800280ae  jz      short loc_1800280C8
0x1800280b0  lea     rdx, a0; "0"
0x1800280b7  mov     rcx, r14; String1
0x1800280ba  call    cs:__imp__wcsicmp
0x1800280c0  test    eax, eax
0x1800280c2  jz      short loc_1800280C8
0x1800280c4  mov     al, 1
0x1800280c6  jmp     short loc_1800280CA
0x1800280c8  xor     al, al
0x1800280ca  mov     [rsi+60h], al
0x1800280cd  mov     byte ptr [rsi+8Bh], 1
0x1800280d4  jmp     short loc_180028112
0x1800280d6  mov     rcx, [rbp+String1]; String1
0x1800280da  lea     rdx, aType; "Type"
0x1800280e1  call    cs:__imp__wcsicmp
0x1800280e7  test    eax, eax
0x1800280e9  jnz     short loc_18002810D
0x1800280eb  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800280ef  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800280f4  mov     rdx, qword ptr [rbp+pvarg+8]
0x1800280f8  lea     rcx, [rsi+20h]
0x1800280fc  mov     r8, rax
0x1800280ff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180028104  mov     byte ptr [rsi+89h], 1
0x18002810b  jmp     short loc_180028112
0x18002810d  mov     ebx, 80070057h
0x180028112  mov     rcx, [rbp+arg_10]
0x180028116  mov     rax, [rcx]
0x180028119  mov     rax, [rax+10h]
0x18002811d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028122  inc     edi
0x180028124  mov     [rbp+arg_10], 0
0x18002812c  test    ebx, ebx
0x18002812e  jns     loc_18002802A
0x180028134  mov     eax, ebx
0x180028136  add     rsp, 40h
0x18002813a  pop     r14
0x18002813c  pop     rdi
0x18002813d  pop     rsi
0x18002813e  pop     rbx
0x18002813f  pop     rbp
0x180028140  retn
```
