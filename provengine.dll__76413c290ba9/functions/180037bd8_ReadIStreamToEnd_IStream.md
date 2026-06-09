# ReadIStreamToEnd(IStream *)

- ea: `0x180037bd8`
- end: `0x180037d8b`
- name: `?ReadIStreamToEnd@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@@Z`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003795c`

## callees

- `0x1800071a4`
- `0x180021cf4`
- `0x180037bd8`
- `0x180037e3c`
- `0x180047010`

## string_xrefs

- `0x180037cf2`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037d15`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037d2e`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037d47`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037d60`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037d79`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ReadIStreamToEnd(_QWORD *a1, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  unsigned int v10; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int v13; // [rsp+78h] [rbp+30h] BYREF
  __int64 v14; // [rsp+80h] [rbp+38h] BYREF
  __int64 v15; // [rsp+88h] [rbp+40h] BYREF

  v14 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)a2 + 40LL))(
         a2,
         qword_18005AD60,
         1,
         &v14);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v4,
      v11);
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)a2 + 40LL))(
         a2,
         qword_18005AD60,
         2,
         &v15);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v5,
      v11);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, v14, 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v6,
      v11);
  if ( HIDWORD(v15) || HIDWORD(v14) )
  {
    v10 = wil::verify_hresult<long>(0x8000FFFF);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)v10,
      v11);
  }
  v7 = v15 - v14;
  std::vector<unsigned char>::resize(a1, (unsigned int)(v15 - v14));
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)a2 + 24LL))(a2, *a1, v7, &v13);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v8,
      v11);
  if ( v7 != v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)0x8000FFFFLL,
      v11);
  return a1;
}

```

## disassembly

```asm
0x180037bd8  mov     [rsp-20h+arg_0], rcx
0x180037bdd  push    rbp
0x180037bde  push    rbx
0x180037bdf  push    rsi
0x180037be0  push    rdi
0x180037be1  mov     rbp, rsp
0x180037be4  sub     rsp, 48h
0x180037be8  mov     rbx, rdx
0x180037beb  mov     rdi, rcx
0x180037bee  mov     [rbp+var_18], 0
0x180037bf5  mov     [rbp+arg_10], 0
0x180037bfd  mov     qword ptr [rcx], 0
0x180037c04  mov     qword ptr [rcx+8], 0
0x180037c0c  mov     qword ptr [rcx+10h], 0
0x180037c14  mov     r8d, 1
0x180037c1a  mov     [rbp+var_18], r8d
0x180037c1e  mov     rax, [rdx]
0x180037c21  lea     r9, [rbp+arg_10]
0x180037c25  mov     rdx, cs:qword_18005AD60
0x180037c2c  mov     rcx, rbx
0x180037c2f  mov     rax, [rax+28h]
0x180037c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c38  test    eax, eax
0x180037c3a  js      loc_180037D27
0x180037c40  mov     [rbp+arg_18], 0
0x180037c48  mov     rax, [rbx]
0x180037c4b  lea     r9, [rbp+arg_18]
0x180037c4f  mov     r8d, 2
0x180037c55  mov     rdx, cs:qword_18005AD60
0x180037c5c  mov     rcx, rbx
0x180037c5f  mov     rax, [rax+28h]
0x180037c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c68  test    eax, eax
0x180037c6a  js      loc_180037D40
0x180037c70  mov     rax, [rbx]
0x180037c73  xor     r9d, r9d
0x180037c76  xor     r8d, r8d
0x180037c79  mov     rdx, [rbp+arg_10]
0x180037c7d  mov     rcx, rbx
0x180037c80  mov     rax, [rax+28h]
0x180037c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c89  test    eax, eax
0x180037c8b  js      loc_180037D59
0x180037c91  cmp     dword ptr [rbp+arg_18+4], 0
0x180037c95  jnz     short loc_180037D04
0x180037c97  cmp     dword ptr [rbp+arg_10+4], 0
0x180037c9b  jnz     short loc_180037D04
0x180037c9d  mov     eax, dword ptr [rbp+arg_18]
0x180037ca0  sub     eax, dword ptr [rbp+arg_10]
0x180037ca3  mov     esi, eax
0x180037ca5  mov     edx, eax
0x180037ca7  mov     rcx, rdi
0x180037caa  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180037caf  mov     [rbp+arg_8], 0
0x180037cb6  mov     rax, [rbx]
0x180037cb9  lea     r9, [rbp+arg_8]
0x180037cbd  mov     r8d, esi
0x180037cc0  mov     rdx, [rdi]
0x180037cc3  mov     rcx, rbx
0x180037cc6  mov     rax, [rax+18h]
0x180037cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ccf  test    eax, eax
0x180037cd1  js      loc_180037D72
0x180037cd7  cmp     esi, [rbp+arg_8]
0x180037cda  jnz     short loc_180037CE8
0x180037cdc  mov     rax, rdi
0x180037cdf  add     rsp, 48h
0x180037ce3  pop     rdi
0x180037ce4  pop     rsi
0x180037ce5  pop     rbx
0x180037ce6  pop     rbp
0x180037ce7  retn
0x180037ce8  mov     rcx, [rbp+20h]; this
0x180037cec  mov     r9d, 8000FFFFh; char *
0x180037cf2  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037cf9  mov     edx, 30h ; '0'; void *
0x180037cfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037d04  mov     ecx, 8000FFFFh
0x180037d09  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180037d0e  mov     r9d, eax; char *
0x180037d11  mov     rcx, [rbp+20h]; this
0x180037d15  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037d1c  mov     edx, 28h ; '('; void *
0x180037d21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037d27  mov     rcx, [rbp+20h]; this
0x180037d2b  mov     r9d, eax; char *
0x180037d2e  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037d35  mov     edx, 20h ; ' '; void *
0x180037d3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037d40  mov     rcx, [rbp+20h]; this
0x180037d44  mov     r9d, eax; char *
0x180037d47  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037d4e  mov     edx, 23h ; '#'; void *
0x180037d53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037d59  mov     rcx, [rbp+20h]; this
0x180037d5d  mov     r9d, eax; char *
0x180037d60  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037d67  mov     edx, 24h ; '$'; void *
0x180037d6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037d72  mov     rcx, [rbp+20h]; this
0x180037d76  mov     r9d, eax; char *
0x180037d79  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037d80  mov     edx, 2Fh ; '/'; void *
0x180037d85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
