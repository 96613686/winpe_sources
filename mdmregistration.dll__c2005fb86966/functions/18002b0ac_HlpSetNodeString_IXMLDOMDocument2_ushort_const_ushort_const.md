# HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)

- ea: `0x18002b0ac`
- end: `0x18002b225`
- name: `?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z`
- size: `377`
- prototype: `int(struct IXMLDOMDocument2 **, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800226a4`
- `0x180022948`
- `0x180022e74`
- `0x18002c37c`
- `0x18002c5cc`
- `0x18002c758`

## callees

- `0x18002b0ac`
- `0x18004e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b0dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b0f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b0dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b0f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b180`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b190`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1de`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b180`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b190`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b1de`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall HlpSetNodeString(
        struct IXMLDOMDocument2 **a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  OLECHAR *v5; // rdi
  BSTR v6; // rax
  OLECHAR *v7; // rbx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, OLECHAR *, __int64 *); // rbp
  __int64 v10; // rcx
  int v11; // esi
  __int64 v12; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  OLECHAR *v16; // [rsp+68h] [rbp+20h]

  v15 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = SysAllocString(a2);
  v16 = v5;
  v6 = SysAllocString(a3);
  v7 = v6;
  if ( v5 && v6 )
  {
    v8 = (__int64)*a1;
    v9 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v8 + 296LL);
    v10 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v9(v8, v5, &v15);
    if ( v11 >= 0 && v15 )
      v11 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v15 + 216LL))(v15, v7);
    SysFreeString(v5);
    SysFreeString(v7);
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return (unsigned int)v11;
  }
  else
  {
    if ( v5 )
      SysFreeString(v5);
    if ( v7 )
      SysFreeString(v7);
    v14 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002b0ac  mov     [rsp+arg_0], rbx
0x18002b0b1  push    rbp
0x18002b0b2  push    rsi
0x18002b0b3  push    rdi
0x18002b0b4  sub     rsp, 30h
0x18002b0b8  mov     rbx, r8
0x18002b0bb  mov     rsi, rcx
0x18002b0be  mov     [rsp+48h+arg_8], 0
0x18002b0c7  test    rdx, rdx
0x18002b0ca  jz      loc_18002B212
0x18002b0d0  test    rbx, rbx
0x18002b0d3  jz      loc_18002B212
0x18002b0d9  mov     rcx, rdx; psz
0x18002b0dc  call    cs:__imp_SysAllocString
0x18002b0e3  nop     dword ptr [rax+rax+00h]
0x18002b0e8  mov     rdi, rax
0x18002b0eb  mov     [rsp+48h+arg_18], rax
0x18002b0f0  mov     rcx, rbx; psz
0x18002b0f3  call    cs:__imp_SysAllocString
0x18002b0fa  nop     dword ptr [rax+rax+00h]
0x18002b0ff  mov     rbx, rax
0x18002b102  mov     [rsp+48h+var_28], rax
0x18002b107  test    rdi, rdi
0x18002b10a  jz      loc_18002B1C1
0x18002b110  test    rax, rax
0x18002b113  jz      loc_18002B1C1
0x18002b119  mov     rsi, [rsi]
0x18002b11c  mov     rax, [rsi]
0x18002b11f  mov     rbp, [rax+128h]
0x18002b126  mov     rcx, [rsp+48h+arg_8]
0x18002b12b  test    rcx, rcx
0x18002b12e  jz      short loc_18002B146
0x18002b130  mov     [rsp+48h+arg_8], 0
0x18002b139  mov     rax, [rcx]
0x18002b13c  mov     rax, [rax+10h]
0x18002b140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b145  nop
0x18002b146  lea     r8, [rsp+48h+arg_8]
0x18002b14b  mov     rdx, rdi
0x18002b14e  mov     rcx, rsi
0x18002b151  mov     rax, rbp
0x18002b154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b159  mov     esi, eax
0x18002b15b  test    eax, eax
0x18002b15d  js      short loc_18002B17D
0x18002b15f  mov     rcx, [rsp+48h+arg_8]
0x18002b164  test    rcx, rcx
0x18002b167  jz      short loc_18002B17D
0x18002b169  mov     rax, [rcx]
0x18002b16c  mov     rdx, rbx
0x18002b16f  mov     rax, [rax+0D8h]
0x18002b176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b17b  mov     esi, eax
0x18002b17d  mov     rcx, rdi; bstrString
0x18002b180  call    cs:__imp_SysFreeString
0x18002b187  nop     dword ptr [rax+rax+00h]
0x18002b18c  nop
0x18002b18d  mov     rcx, rbx; bstrString
0x18002b190  call    cs:__imp_SysFreeString
0x18002b197  nop     dword ptr [rax+rax+00h]
0x18002b19c  nop
0x18002b19d  mov     rcx, [rsp+48h+arg_8]
0x18002b1a2  test    rcx, rcx
0x18002b1a5  jz      short loc_18002B1BD
0x18002b1a7  mov     [rsp+48h+arg_8], 0
0x18002b1b0  mov     rax, [rcx]
0x18002b1b3  mov     rax, [rax+10h]
0x18002b1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1bc  nop
0x18002b1bd  mov     eax, esi
0x18002b1bf  jmp     short loc_18002B217
0x18002b1c1  test    rdi, rdi
0x18002b1c4  jz      short loc_18002B1D6
0x18002b1c6  mov     rcx, rdi; bstrString
0x18002b1c9  call    cs:__imp_SysFreeString
0x18002b1d0  nop     dword ptr [rax+rax+00h]
0x18002b1d5  nop
0x18002b1d6  test    rbx, rbx
0x18002b1d9  jz      short loc_18002B1EB
0x18002b1db  mov     rcx, rbx; bstrString
0x18002b1de  call    cs:__imp_SysFreeString
0x18002b1e5  nop     dword ptr [rax+rax+00h]
0x18002b1ea  nop
0x18002b1eb  mov     rcx, [rsp+48h+arg_8]
0x18002b1f0  test    rcx, rcx
0x18002b1f3  jz      short loc_18002B20B
0x18002b1f5  mov     [rsp+48h+arg_8], 0
0x18002b1fe  mov     rax, [rcx]
0x18002b201  mov     rax, [rax+10h]
0x18002b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b20a  nop
0x18002b20b  mov     eax, 8007000Eh
0x18002b210  jmp     short loc_18002B217
0x18002b212  mov     eax, 80070057h
0x18002b217  mov     rbx, [rsp+48h+arg_0]
0x18002b21c  add     rsp, 30h
0x18002b220  pop     rdi
0x18002b221  pop     rsi
0x18002b222  pop     rbp
0x18002b223  retn
```
