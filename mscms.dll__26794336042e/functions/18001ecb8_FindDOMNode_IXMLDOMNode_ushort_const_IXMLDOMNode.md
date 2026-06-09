# FindDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x18001ecb8`
- end: `0x18001ed68`
- name: `?FindDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `176`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e9d4`
- `0x18001ebc4`
- `0x18002b98c`
- `0x180058904`
- `0x180059604`
- `0x1800599a4`
- `0x18005a174`
- `0x18005a1dc`
- `0x18005a930`
- `0x18005b17c`
- `0x18005b7ac`

## callees

- `0x18001ecb8`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ecd9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ecd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed15`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed15`

## pseudocode

```c
__int64 __fastcall FindDOMNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct IXMLDOMNode **a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  unsigned int v7; // ebx
  struct IXMLDOMNode *v8; // rcx
  struct IXMLDOMNode *v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  v5 = SysAllocString(a2);
  v6 = v5;
  if ( !v5 )
  {
    v7 = -2147024882;
LABEL_3:
    v8 = v10;
    *a3 = 0;
    goto LABEL_4;
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
         a1,
         v5,
         &v10);
  if ( v7 )
    goto LABEL_3;
  ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->AddRef)(v10);
  v8 = v10;
  *a3 = v10;
LABEL_4:
  if ( v8 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
    v10 = 0;
  }
  SysFreeString(v6);
  return v7;
}

```

## disassembly

```asm
0x18001ecb8  mov     [rsp+arg_0], rbx
0x18001ecbd  mov     [rsp+arg_8], rsi
0x18001ecc2  push    rdi
0x18001ecc3  sub     rsp, 20h
0x18001ecc7  mov     rbx, rcx
0x18001ecca  mov     [rsp+28h+arg_18], 0
0x18001ecd3  mov     rcx, rdx; psz
0x18001ecd6  mov     rsi, r8
0x18001ecd9  call    cs:__imp_SysAllocString
0x18001ecdf  mov     rdi, rax
0x18001ece2  test    rax, rax
0x18001ece5  jnz     short loc_18001ED2D
0x18001ece7  mov     ebx, 8007000Eh
0x18001ecec  mov     rcx, [rsp+28h+arg_18]
0x18001ecf1  mov     qword ptr [rsi], 0
0x18001ecf8  test    rcx, rcx
0x18001ecfb  jz      short loc_18001ED12
0x18001ecfd  mov     rax, [rcx]
0x18001ed00  mov     rax, [rax+10h]
0x18001ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed09  mov     [rsp+28h+arg_18], 0
0x18001ed12  mov     rcx, rdi; bstrString
0x18001ed15  call    cs:__imp_SysFreeString
0x18001ed1b  mov     rsi, [rsp+28h+arg_8]
0x18001ed20  mov     eax, ebx
0x18001ed22  mov     rbx, [rsp+28h+arg_0]
0x18001ed27  add     rsp, 20h
0x18001ed2b  pop     rdi
0x18001ed2c  retn
0x18001ed2d  mov     rax, [rbx]
0x18001ed30  lea     r8, [rsp+28h+arg_18]
0x18001ed35  mov     rdx, rdi
0x18001ed38  mov     rcx, rbx
0x18001ed3b  mov     rax, [rax+128h]
0x18001ed42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed47  mov     ebx, eax
0x18001ed49  test    eax, eax
0x18001ed4b  jnz     short loc_18001ECEC
0x18001ed4d  mov     rcx, [rsp+28h+arg_18]
0x18001ed52  mov     rdx, [rcx]
0x18001ed55  mov     rax, [rdx+8]
0x18001ed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed5e  mov     rcx, [rsp+28h+arg_18]
0x18001ed63  mov     [rsi], rcx
0x18001ed66  jmp     short loc_18001ECF8
```
