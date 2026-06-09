# CWrapperOutputPin::SetCompressionParamUsingIPropBag(ushort const *,long)

- ea: `0x18001a434`
- end: `0x18001a4f0`
- name: `?SetCompressionParamUsingIPropBag@CWrapperOutputPin@@IEAAJPEBGJ@Z`
- size: `188`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001add0`
- `0x18001aed0`

## callees

- `0x180001460`
- `0x18001a434`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::SetCompressionParamUsingIPropBag(
        CWrapperOutputPin *this,
        const unsigned __int16 *a2,
        int a3)
{
  unsigned int v5; // ebx
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+28h] [rbp-40h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h]

  v5 = -2147467263;
  v6 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 10) + 160LL);
  v8 = 0;
  if ( v6 )
  {
    (**v6)(v6, &IID_IPropertyBag, &v8);
    if ( v8 )
    {
      v10 = 0;
      v9 = 0;
      DWORD2(v9) = a3;
      LOWORD(v9) = 3;
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *))(*(_QWORD *)v8 + 32LL))(
             v8,
             a2,
             &v9);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001a434  push    rbx
0x18001a436  push    rsi
0x18001a437  push    rdi
0x18001a438  sub     rsp, 50h
0x18001a43c  mov     rax, cs:__security_cookie
0x18001a443  xor     rax, rsp
0x18001a446  mov     [rsp+68h+var_28], rax
0x18001a44b  mov     rax, [rcx+50h]
0x18001a44f  mov     esi, r8d
0x18001a452  mov     rdi, rdx
0x18001a455  mov     ebx, 80004001h
0x18001a45a  mov     rcx, [rax+0A0h]
0x18001a461  mov     [rsp+68h+var_48], 0
0x18001a46a  test    rcx, rcx
0x18001a46d  jz      short loc_18001A4D9
0x18001a46f  mov     rax, [rcx]
0x18001a472  lea     r8, [rsp+68h+var_48]
0x18001a477  lea     rdx, IID_IPropertyBag
0x18001a47e  mov     rax, [rax]
0x18001a481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a486  mov     rcx, [rsp+68h+var_48]
0x18001a48b  test    rcx, rcx
0x18001a48e  jz      short loc_18001A4D9
0x18001a490  xor     eax, eax
0x18001a492  lea     r8, [rsp+68h+var_40]
0x18001a497  mov     [rsp+68h+var_30], rax
0x18001a49c  xorps   xmm0, xmm0
0x18001a49f  movups  [rsp+68h+var_40], xmm0
0x18001a4a4  mov     eax, 3
0x18001a4a9  mov     dword ptr [rsp+68h+var_40+8], esi
0x18001a4ad  mov     word ptr [rsp+68h+var_40], ax
0x18001a4b2  mov     rdx, rdi
0x18001a4b5  mov     rax, [rcx]
0x18001a4b8  mov     rax, [rax+20h]
0x18001a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c1  mov     rcx, [rsp+68h+var_48]
0x18001a4c6  mov     ebx, eax
0x18001a4c8  test    rcx, rcx
0x18001a4cb  jz      short loc_18001A4D9
0x18001a4cd  mov     rdx, [rcx]
0x18001a4d0  mov     rax, [rdx+10h]
0x18001a4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4d9  mov     eax, ebx
0x18001a4db  mov     rcx, [rsp+68h+var_28]
0x18001a4e0  xor     rcx, rsp; StackCookie
0x18001a4e3  call    __security_check_cookie
0x18001a4e8  add     rsp, 50h
0x18001a4ec  pop     rdi
0x18001a4ed  pop     rsi
0x18001a4ee  pop     rbx
0x18001a4ef  retn
```
