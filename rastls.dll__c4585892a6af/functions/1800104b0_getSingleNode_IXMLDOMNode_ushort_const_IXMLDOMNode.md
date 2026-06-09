# getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x1800104b0`
- end: `0x180010575`
- name: `?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `197`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cbc4`
- `0x18000d1e0`
- `0x18000eb10`
- `0x180010580`
- `0x180062228`
- `0x180062614`
- `0x180062884`
- `0x180062e58`
- `0x18006309c`
- `0x1800633e0`
- `0x1800637fc`
- `0x180063df0`

## callees

- `0x180010140`
- `0x1800104b0`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800104d8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800104d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180010519`
- `OLEAUT32!__imp_SysFreeString` at `0x180010519`

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
0x1800104b0  mov     [rsp+arg_0], rbx
0x1800104b5  mov     [rsp+arg_10], rbp
0x1800104ba  push    rsi
0x1800104bb  push    rdi
0x1800104bc  push    r14
0x1800104be  sub     rsp, 20h
0x1800104c2  mov     rbp, r8
0x1800104c5  mov     rsi, rdx
0x1800104c8  mov     r14, rcx
0x1800104cb  mov     edi, 80070057h
0x1800104d0  test    rdx, rdx
0x1800104d3  jz      short loc_180010525
0x1800104d5  mov     rcx, rdx; psz
0x1800104d8  call    cs:__imp_SysAllocString
0x1800104df  nop     dword ptr [rax+rax+00h]
0x1800104e4  mov     rbx, rax
0x1800104e7  mov     [rsp+38h+arg_8], rax
0x1800104ec  test    rax, rax
0x1800104ef  jz      short loc_18001056F
0x1800104f1  mov     rax, [r14]
0x1800104f4  mov     r8, rbp
0x1800104f7  mov     rdx, rbx
0x1800104fa  mov     rcx, r14
0x1800104fd  mov     rax, [rax+128h]
0x180010504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010509  mov     edi, eax
0x18001050b  test    eax, eax
0x18001050d  jnz     short loc_18001053B
0x18001050f  cmp     qword ptr [rbp+0], 0
0x180010514  jz      short loc_18001053B
0x180010516  mov     rcx, rbx; bstrString
0x180010519  call    cs:__imp_SysFreeString
0x180010520  nop     dword ptr [rax+rax+00h]
0x180010525  mov     eax, edi
0x180010527  mov     rbx, [rsp+38h+arg_0]
0x18001052c  mov     rbp, [rsp+38h+arg_10]
0x180010531  add     rsp, 20h
0x180010535  pop     r14
0x180010537  pop     rdi
0x180010538  pop     rsi
0x180010539  retn
0x18001053b  lea     rax, WPP_GLOBAL_Control
0x180010542  mov     rcx, cs:WPP_GLOBAL_Control
0x180010549  cmp     rcx, rax
0x18001054c  jnz     short loc_180010555
0x18001054e  mov     edi, 80070057h
0x180010553  jmp     short loc_180010516
0x180010555  mov     edx, 0FCh
0x18001055a  mov     r9, rsi
0x18001055d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010564  mov     rcx, [rcx+10h]
0x180010568  call    WPP_SF_S
0x18001056d  jmp     short loc_18001054E
0x18001056f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
