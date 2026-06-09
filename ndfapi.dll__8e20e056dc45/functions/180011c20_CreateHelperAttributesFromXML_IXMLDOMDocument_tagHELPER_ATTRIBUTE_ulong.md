# CreateHelperAttributesFromXML(IXMLDOMDocument *,tagHELPER_ATTRIBUTE * *,ulong *)

- ea: `0x180011c20`
- end: `0x180011e0d`
- name: `?CreateHelperAttributesFromXML@@YAJPEAUIXMLDOMDocument@@PEAPEAUtagHELPER_ATTRIBUTE@@PEAK@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, struct tagHELPER_ATTRIBUTE **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180011e20`

## callees

- `0x180008a60`
- `0x180011934`
- `0x180011c20`
- `0x1800159d0`
- `0x18001f652`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180011cf7`
- `ole32!CoTaskMemAlloc` at `0x180011cf7`

## pseudocode

```c
__int64 __fastcall CreateHelperAttributesFromXML(
        struct IXMLDOMDocument *a1,
        struct tagHELPER_ATTRIBUTE **a2,
        unsigned int *a3)
{
  unsigned int *v3; // r15
  struct tagHELPER_ATTRIBUTE *v4; // r14
  unsigned int v5; // r12d
  int v6; // r13d
  int NextNode; // edi
  struct tagHELPER_ATTRIBUTE *v8; // rbx
  __int64 v9; // rsi
  struct IXMLDOMNodeList *v10; // rbx
  struct tagHELPER_ATTRIBUTE *v11; // rax
  struct tagHELPER_ATTRIBUTE *v12; // r15
  __int64 v13; // r15
  struct tagHELPER_ATTRIBUTE *v14; // r14
  struct IXMLDOMNode *v15; // rbx
  struct IXMLDOMNodeList *v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF
  struct tagHELPER_ATTRIBUTE *v19; // [rsp+30h] [rbp-18h]
  __int64 v20; // [rsp+38h] [rbp-10h]
  struct IXMLDOMNode *i; // [rsp+90h] [rbp+48h] BYREF
  struct tagHELPER_ATTRIBUTE **v22; // [rsp+98h] [rbp+50h]
  unsigned int *v23; // [rsp+A0h] [rbp+58h]
  struct tagHELPER_ATTRIBUTE *v24; // [rsp+A8h] [rbp+60h]

  v23 = a3;
  v22 = a2;
  v3 = a3;
  v4 = 0;
  v19 = 0;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  v18 = 0;
  NextNode = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))a1->lpVtbl->get_documentElement)(a1, &v18);
  if ( NextNode >= 0 )
  {
    v8 = 0;
    v9 = 0;
    v17 = 0;
    NextNode = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNodeList **))(*(_QWORD *)v18 + 96LL))(v18, &v17);
    if ( NextNode >= 0 )
    {
      v10 = v17;
      for ( i = 0; ; i = 0 )
      {
        XmlUtilGetNextNode(v10, &i);
        if ( !i )
          break;
        v9 = (unsigned int)(v9 + 1);
        ((void (*)(void))i->lpVtbl->Release)();
      }
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v10->lpVtbl->reset)(v10);
      NextNode = 0;
      if ( (_DWORD)v9 )
      {
        v11 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v9);
        v12 = v11;
        v24 = v11;
        if ( v11 )
        {
          memset_0(v11, 0, 144 * v9);
          v19 = v12;
          v5 = v9;
          v20 = (unsigned int)v9 | 0x100000000LL;
          v6 = 1;
        }
        else
        {
          NextNode = -2147024882;
        }
        v13 = 0;
        v14 = v24;
        do
        {
          if ( NextNode < 0 )
            break;
          i = 0;
          NextNode = XmlUtilGetNextNode(v17, &i);
          v15 = i;
          if ( NextNode >= 0 )
            NextNode = CreateHelperAttributeFromXML(i, &v14[v13]);
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < (unsigned int)v9 );
        v4 = v19;
        v8 = v24;
        v3 = v23;
      }
      else
      {
        v8 = 0;
      }
    }
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v17->lpVtbl->Release)(v17);
    if ( NextNode >= 0 )
    {
      *v22 = v8;
      *v3 = v9;
      v4 = 0;
      v19 = 0;
      v5 = 0;
      v20 = 0;
      v6 = 0;
    }
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v4 )
    FreeHelperAttributes(v4, v5, v6);
  return (unsigned int)NextNode;
}

```

## disassembly

```asm
0x180011c20  mov     [rsp-40h+arg_10], r8
0x180011c25  mov     [rsp-40h+arg_8], rdx
0x180011c2a  push    rbp
0x180011c2b  push    rbx
0x180011c2c  push    rsi
0x180011c2d  push    rdi
0x180011c2e  push    r12
0x180011c30  push    r13
0x180011c32  push    r14
0x180011c34  push    r15
0x180011c36  mov     rbp, rsp
0x180011c39  sub     rsp, 48h
0x180011c3d  mov     r15, r8
0x180011c40  xor     r14d, r14d
0x180011c43  mov     [rbp+var_18], r14
0x180011c47  xor     r12d, r12d
0x180011c4a  mov     [rbp+var_10], r12
0x180011c4e  xor     r13d, r13d
0x180011c51  mov     [rbp+var_20], r13
0x180011c55  mov     rax, [rcx]
0x180011c58  lea     rdx, [rbp+var_20]
0x180011c5c  mov     rax, [rax+168h]
0x180011c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c68  mov     edi, eax
0x180011c6a  test    eax, eax
0x180011c6c  js      loc_180011DD1
0x180011c72  xor     ebx, ebx
0x180011c74  xor     esi, esi
0x180011c76  mov     [rbp+var_28], rbx
0x180011c7a  mov     rcx, [rbp+var_20]
0x180011c7e  mov     rax, [rcx]
0x180011c81  lea     rdx, [rbp+var_28]
0x180011c85  mov     rax, [rax+60h]
0x180011c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c8e  mov     edi, eax
0x180011c90  test    eax, eax
0x180011c92  js      loc_180011D9C
0x180011c98  mov     rbx, [rbp+var_28]
0x180011c9c  mov     [rbp+arg_0], rsi
0x180011ca0  jmp     short loc_180011CBE
0x180011ca2  inc     esi
0x180011ca4  test    rcx, rcx
0x180011ca7  jz      short loc_180011CB6
0x180011ca9  mov     rax, [rcx]
0x180011cac  mov     rax, [rax+10h]
0x180011cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb5  nop
0x180011cb6  mov     [rbp+arg_0], 0
0x180011cbe  lea     rdx, [rbp+arg_0]; struct IXMLDOMNode **
0x180011cc2  mov     rcx, rbx; struct IXMLDOMNodeList *
0x180011cc5  call    ?XmlUtilGetNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; XmlUtilGetNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180011cca  mov     rcx, [rbp+arg_0]
0x180011cce  test    rcx, rcx
0x180011cd1  jnz     short loc_180011CA2
0x180011cd3  mov     rax, [rbx]
0x180011cd6  mov     rcx, rbx
0x180011cd9  mov     rax, [rax+50h]
0x180011cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce2  xor     edi, edi
0x180011ce4  test    esi, esi
0x180011ce6  jz      loc_180011D99
0x180011cec  lea     rbx, [rsi+rsi*8]
0x180011cf0  shl     rbx, 4
0x180011cf4  mov     rcx, rbx; cb
0x180011cf7  call    cs:__imp_CoTaskMemAlloc
0x180011cfd  mov     r15, rax
0x180011d00  mov     [rbp+arg_18], rax
0x180011d04  test    rax, rax
0x180011d07  jz      short loc_180011D2A
0x180011d09  mov     r8, rbx; Size
0x180011d0c  xor     edx, edx; Val
0x180011d0e  mov     rcx, rax; void *
0x180011d11  call    memset_0
0x180011d16  mov     [rbp+var_18], r15
0x180011d1a  mov     r12d, esi
0x180011d1d  mov     dword ptr [rbp+var_10], esi
0x180011d20  lea     r13d, [rdi+1]
0x180011d24  mov     dword ptr [rbp+var_10+4], r13d
0x180011d28  jmp     short loc_180011D2F
0x180011d2a  mov     edi, 8007000Eh
0x180011d2f  xor     r15d, r15d
0x180011d32  mov     r14, [rbp+arg_18]
0x180011d36  test    edi, edi
0x180011d38  js      short loc_180011D8B
0x180011d3a  mov     [rbp+arg_0], 0
0x180011d42  lea     rdx, [rbp+arg_0]; struct IXMLDOMNode **
0x180011d46  mov     rcx, [rbp+var_28]; struct IXMLDOMNodeList *
0x180011d4a  call    ?XmlUtilGetNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; XmlUtilGetNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180011d4f  mov     edi, eax
0x180011d51  mov     rbx, [rbp+arg_0]
0x180011d55  test    eax, eax
0x180011d57  js      short loc_180011D6E
0x180011d59  lea     rdx, [r15+r15*8]
0x180011d5d  shl     rdx, 4
0x180011d61  add     rdx, r14; struct tagHELPER_ATTRIBUTE *
0x180011d64  mov     rcx, rbx; struct IXMLDOMNode *
0x180011d67  call    ?CreateHelperAttributeFromXML@@YAJPEAUIXMLDOMNode@@PEAUtagHELPER_ATTRIBUTE@@@Z; CreateHelperAttributeFromXML(IXMLDOMNode *,tagHELPER_ATTRIBUTE *)
0x180011d6c  mov     edi, eax
0x180011d6e  test    rbx, rbx
0x180011d71  jz      short loc_180011D83
0x180011d73  mov     rax, [rbx]
0x180011d76  mov     rcx, rbx
0x180011d79  mov     rax, [rax+10h]
0x180011d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d82  nop
0x180011d83  inc     r15d
0x180011d86  cmp     r15d, esi
0x180011d89  jb      short loc_180011D36
0x180011d8b  mov     r14, [rbp+var_18]
0x180011d8f  mov     rbx, [rbp+arg_18]
0x180011d93  mov     r15, [rbp+arg_10]
0x180011d97  jmp     short loc_180011D9C
0x180011d99  mov     rbx, rdi
0x180011d9c  mov     rcx, [rbp+var_28]
0x180011da0  test    rcx, rcx
0x180011da3  jz      short loc_180011DB2
0x180011da5  mov     rax, [rcx]
0x180011da8  mov     rax, [rax+10h]
0x180011dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db1  nop
0x180011db2  test    edi, edi
0x180011db4  js      short loc_180011DD1
0x180011db6  mov     rax, [rbp+arg_8]
0x180011dba  mov     [rax], rbx
0x180011dbd  mov     [r15], esi
0x180011dc0  xor     r14d, r14d
0x180011dc3  mov     [rbp+var_18], r14
0x180011dc7  xor     r12d, r12d
0x180011dca  mov     [rbp+var_10], r12
0x180011dce  xor     r13d, r13d
0x180011dd1  mov     rcx, [rbp+var_20]
0x180011dd5  test    rcx, rcx
0x180011dd8  jz      short loc_180011DE7
0x180011dda  mov     rax, [rcx]
0x180011ddd  mov     rax, [rax+10h]
0x180011de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011de6  nop
0x180011de7  test    r14, r14
0x180011dea  jz      short loc_180011DFA
0x180011dec  mov     r8d, r13d; int
0x180011def  mov     edx, r12d; unsigned int
0x180011df2  mov     rcx, r14; pv
0x180011df5  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180011dfa  mov     eax, edi
0x180011dfc  add     rsp, 48h
0x180011e00  pop     r15
0x180011e02  pop     r14
0x180011e04  pop     r13
0x180011e06  pop     r12
0x180011e08  pop     rdi
0x180011e09  pop     rsi
0x180011e0a  pop     rbx
0x180011e0b  pop     rbp
0x180011e0c  retn
```
