# getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000f690`
- end: `0x18000f748`
- name: `?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `184`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c1e0`
- `0x18000c780`
- `0x18000deb0`
- `0x18000f750`
- `0x18005ea34`
- `0x18005ee0c`
- `0x18005f078`
- `0x18005f628`
- `0x18005f864`
- `0x18005fb70`
- `0x18005ff50`
- `0x1800604e4`

## callees

- `0x18000f350`
- `0x18000f690`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f6b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f6b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f6f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f6f3`

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
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a2);
      v6 = -2147024809;
    }
    SysFreeString(v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f690  mov     [rsp+arg_0], rbx
0x18000f695  mov     [rsp+arg_10], rbp
0x18000f69a  push    rsi
0x18000f69b  push    rdi
0x18000f69c  push    r14
0x18000f69e  sub     rsp, 20h
0x18000f6a2  mov     rbp, r8
0x18000f6a5  mov     rsi, rdx
0x18000f6a8  mov     r14, rcx
0x18000f6ab  mov     edi, 80070057h
0x18000f6b0  test    rdx, rdx
0x18000f6b3  jz      short loc_18000F6F9
0x18000f6b5  mov     rcx, rdx; psz
0x18000f6b8  call    cs:__imp_SysAllocString
0x18000f6be  mov     rbx, rax
0x18000f6c1  mov     [rsp+38h+arg_8], rax
0x18000f6c6  test    rax, rax
0x18000f6c9  jz      short loc_18000F742
0x18000f6cb  mov     rax, [r14]
0x18000f6ce  mov     r8, rbp
0x18000f6d1  mov     rdx, rbx
0x18000f6d4  mov     rcx, r14
0x18000f6d7  mov     rax, [rax+128h]
0x18000f6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6e3  mov     edi, eax
0x18000f6e5  test    eax, eax
0x18000f6e7  jnz     short loc_18000F70E
0x18000f6e9  cmp     qword ptr [rbp+0], 0
0x18000f6ee  jz      short loc_18000F70E
0x18000f6f0  mov     rcx, rbx; bstrString
0x18000f6f3  call    cs:__imp_SysFreeString
0x18000f6f9  mov     eax, edi
0x18000f6fb  mov     rbx, [rsp+38h+arg_0]
0x18000f700  mov     rbp, [rsp+38h+arg_10]
0x18000f705  add     rsp, 20h
0x18000f709  pop     r14
0x18000f70b  pop     rdi
0x18000f70c  pop     rsi
0x18000f70d  retn
0x18000f70e  lea     rax, WPP_GLOBAL_Control
0x18000f715  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f71c  cmp     rcx, rax
0x18000f71f  jnz     short loc_18000F728
0x18000f721  mov     edi, 80070057h
0x18000f726  jmp     short loc_18000F6F0
0x18000f728  mov     edx, 0FCh
0x18000f72d  mov     r9, rsi
0x18000f730  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f737  mov     rcx, [rcx+10h]
0x18000f73b  call    WPP_SF_S
0x18000f740  jmp     short loc_18000F721
0x18000f742  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
