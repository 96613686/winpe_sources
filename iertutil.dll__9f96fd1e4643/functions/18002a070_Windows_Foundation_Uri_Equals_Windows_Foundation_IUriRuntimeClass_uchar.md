# Windows::Foundation::Uri::Equals(Windows::Foundation::IUriRuntimeClass *,uchar *)

- ea: `0x18002a070`
- end: `0x18002a1c5`
- name: `?Equals@Uri@Foundation@Windows@@UEAAJPEAUIUriRuntimeClass@23@PEAE@Z`
- size: `341`
- prototype: `__int64 __fastcall(Windows::Foundation::Uri *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180022cd8`
- `0x18002a070`
- `0x18002a420`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a11d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a11d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002a18e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002a18e`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::Equals(
        Windows::Foundation::Uri *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        bool *a3)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  int v7; // edi
  unsigned __int16 *StringRawBuffer; // rax
  int UriPriv; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  HSTRING string; // [rsp+68h] [rbp+28h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    OriginateErrorString(-2147467261, 0x1B58u, 0);
    return (unsigned int)v7;
  }
  v5 = *(_QWORD *)a2;
  v6 = 0;
  string = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(v5 + 128))(a2, &string);
  if ( v7 >= 0 )
  {
    v14 = 0;
    StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
    UriPriv = CreateUriPriv(StringRawBuffer, 0, 0x2014B84u, 0, 0, 0, 0, (struct IUri **)&v14);
    v7 = UriPriv;
    if ( UriPriv < 0 )
    {
      OriginateErrorString(UriPriv, 0x1B5Au, string);
      v10 = v14;
    }
    else
    {
      v6 = v14;
      v10 = 0;
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  WindowsDeleteString(string);
  if ( v7 >= 0 )
  {
    v11 = *((_QWORD *)this + 11);
    LODWORD(string) = 0;
    if ( v11 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v11 + 216LL))(v11, v6, &string);
      if ( v7 >= 0 )
      {
        *a3 = (_DWORD)string == 1;
        goto LABEL_11;
      }
    }
    else
    {
      v7 = -2147418113;
    }
    RoOriginateError((unsigned int)v7, 0);
  }
LABEL_11:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a070  mov     [rsp-18h+arg_0], rbx
0x18002a075  mov     [rsp-18h+arg_18], rsi
0x18002a07a  push    rbp
0x18002a07b  push    rdi
0x18002a07c  push    r14
0x18002a07e  mov     rbp, rsp
0x18002a081  sub     rsp, 40h
0x18002a085  mov     byte ptr [r8], 0
0x18002a089  mov     rsi, r8
0x18002a08c  mov     r9, rdx
0x18002a08f  mov     r14, rcx
0x18002a092  test    rdx, rdx
0x18002a095  jz      loc_18002A196
0x18002a09b  mov     rax, [rdx]
0x18002a09e  xor     ebx, ebx
0x18002a0a0  lea     rdx, [rbp+string]
0x18002a0a4  mov     [rbp+string], rbx
0x18002a0a8  mov     rcx, r9
0x18002a0ab  mov     rax, [rax+80h]
0x18002a0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0b7  mov     edi, eax
0x18002a0b9  test    eax, eax
0x18002a0bb  js      short loc_18002A119
0x18002a0bd  mov     rcx, [rbp+string]; string
0x18002a0c1  xor     edx, edx; length
0x18002a0c3  mov     [rbp+arg_10], rbx
0x18002a0c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a0cd  lea     rcx, [rbp+arg_10]
0x18002a0d1  xor     r9d, r9d
0x18002a0d4  mov     [rsp+40h+var_8], rcx; __int64
0x18002a0d9  xor     edx, edx
0x18002a0db  mov     qword ptr [rsp+40h+var_10], rbx; int
0x18002a0e0  mov     r8d, 2014B84h
0x18002a0e6  mov     qword ptr [rsp+40h+var_18], rbx; int
0x18002a0eb  mov     rcx, rax; unsigned __int16 *
0x18002a0ee  mov     [rsp+40h+var_20], rbx; __int64
0x18002a0f3  call    CreateUriPriv
0x18002a0f8  mov     edi, eax
0x18002a0fa  test    eax, eax
0x18002a0fc  js      loc_18002A1AC
0x18002a102  mov     rbx, [rbp+arg_10]
0x18002a106  xor     ecx, ecx
0x18002a108  test    rcx, rcx
0x18002a10b  jz      short loc_18002A119
0x18002a10d  mov     rax, [rcx]
0x18002a110  mov     rax, [rax+10h]
0x18002a114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a119  mov     rcx, [rbp+string]; string
0x18002a11d  call    cs:__imp_WindowsDeleteString
0x18002a123  test    edi, edi
0x18002a125  js      short loc_18002A15C
0x18002a127  mov     rcx, [r14+58h]
0x18002a12b  mov     dword ptr [rbp+string], 0
0x18002a132  test    rcx, rcx
0x18002a135  jz      short loc_18002A185
0x18002a137  mov     rax, [rcx]
0x18002a13a  lea     r8, [rbp+string]
0x18002a13e  mov     rdx, rbx
0x18002a141  mov     rax, [rax+0D8h]
0x18002a148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a14d  mov     edi, eax
0x18002a14f  test    eax, eax
0x18002a151  js      short loc_18002A18A
0x18002a153  cmp     dword ptr [rbp+string], 1
0x18002a157  setz    al
0x18002a15a  mov     [rsi], al
0x18002a15c  test    rbx, rbx
0x18002a15f  jz      short loc_18002A170
0x18002a161  mov     rcx, [rbx]
0x18002a164  mov     rax, [rcx+10h]
0x18002a168  mov     rcx, rbx
0x18002a16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a170  mov     rbx, [rsp+40h+arg_0]
0x18002a175  mov     eax, edi
0x18002a177  mov     rsi, [rsp+40h+arg_18]
0x18002a17c  add     rsp, 40h
0x18002a180  pop     r14
0x18002a182  pop     rdi
0x18002a183  pop     rbp
0x18002a184  retn
0x18002a185  mov     edi, 8000FFFFh
0x18002a18a  xor     edx, edx
0x18002a18c  mov     ecx, edi
0x18002a18e  call    cs:__imp_RoOriginateError
0x18002a194  jmp     short loc_18002A15C
0x18002a196  mov     edi, 80004003h
0x18002a19b  xor     r8d, r8d; HSTRING
0x18002a19e  mov     ecx, edi; int
0x18002a1a0  mov     edx, 1B58h; unsigned int
0x18002a1a5  call    ?OriginateErrorString@@YAXJIPEAUHSTRING__@@@Z; OriginateErrorString(long,uint,HSTRING__ *)
0x18002a1aa  jmp     short loc_18002A170
0x18002a1ac  mov     r8, [rbp+string]; HSTRING
0x18002a1b0  mov     edx, 1B5Ah; unsigned int
0x18002a1b5  mov     ecx, eax; int
0x18002a1b7  call    ?OriginateErrorString@@YAXJIPEAUHSTRING__@@@Z; OriginateErrorString(long,uint,HSTRING__ *)
0x18002a1bc  mov     rcx, [rbp+arg_10]
0x18002a1c0  jmp     loc_18002A108
```
