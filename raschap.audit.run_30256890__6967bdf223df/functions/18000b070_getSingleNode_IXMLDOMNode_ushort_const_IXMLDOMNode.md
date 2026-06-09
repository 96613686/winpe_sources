# getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000b070`
- end: `0x18000b126`
- name: `?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `182`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001cbe4`
- `0x18001d330`

## callees

- `0x18000b070`
- `0x180017e80`
- `0x18001cbbc`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b098`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b098`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall getSingleNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct IXMLDOMNode **a3)
{
  unsigned int v6; // edi
  BSTR v7; // rax
  int v8; // ecx
  OLECHAR *v9; // rbx

  v6 = -2147024809;
  if ( a2 )
  {
    v7 = SysAllocString(a2);
    v9 = v7;
    if ( !v7 )
      ATL::AtlThrowImpl(v8);
    v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
           a1,
           v7,
           a3);
    if ( v6 || !*a3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a2);
      v6 = -2147024809;
    }
    SysFreeString(v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18000b070  mov     [rsp+arg_0], rbx
0x18000b075  mov     [rsp+arg_10], rbp
0x18000b07a  push    rsi
0x18000b07b  push    rdi
0x18000b07c  push    r14
0x18000b07e  sub     rsp, 20h
0x18000b082  mov     rsi, r8
0x18000b085  mov     rbp, rdx
0x18000b088  mov     r14, rcx
0x18000b08b  mov     edi, 80070057h
0x18000b090  test    rdx, rdx
0x18000b093  jz      short loc_18000B0D8
0x18000b095  mov     rcx, rdx; psz
0x18000b098  call    cs:__imp_SysAllocString
0x18000b09e  mov     rbx, rax
0x18000b0a1  mov     [rsp+38h+arg_8], rax
0x18000b0a6  test    rax, rax
0x18000b0a9  jz      short loc_18000B0ED
0x18000b0ab  mov     rax, [r14]
0x18000b0ae  mov     r8, rsi
0x18000b0b1  mov     rdx, rbx
0x18000b0b4  mov     rcx, r14
0x18000b0b7  mov     rax, [rax+128h]
0x18000b0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0c3  mov     edi, eax
0x18000b0c5  test    eax, eax
0x18000b0c7  jnz     short loc_18000B0F3
0x18000b0c9  cmp     qword ptr [rsi], 0
0x18000b0cd  jz      short loc_18000B0F3
0x18000b0cf  mov     rcx, rbx; bstrString
0x18000b0d2  call    cs:__imp_SysFreeString
0x18000b0d8  mov     eax, edi
0x18000b0da  mov     rbx, [rsp+38h+arg_0]
0x18000b0df  mov     rbp, [rsp+38h+arg_10]
0x18000b0e4  add     rsp, 20h
0x18000b0e8  pop     r14
0x18000b0ea  pop     rdi
0x18000b0eb  pop     rsi
0x18000b0ec  retn
0x18000b0ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b0f3  lea     rax, WPP_GLOBAL_Control
0x18000b0fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b101  cmp     rcx, rax
0x18000b104  jz      short loc_18000B11E
0x18000b106  mov     edx, 3Ch ; '<'
0x18000b10b  mov     r9, rbp
0x18000b10e  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18000b115  mov     rcx, [rcx+10h]
0x18000b119  call    WPP_SF_S
0x18000b11e  mov     edi, 80070057h
0x18000b123  jmp     short loc_18000B0CF
```
