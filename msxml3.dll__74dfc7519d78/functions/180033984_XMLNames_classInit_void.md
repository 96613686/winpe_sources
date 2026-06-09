# XMLNames::classInit(void)

- ea: `0x180033984`
- end: `0x180033eea`
- name: `?classInit@XMLNames@@SAXXZ`
- size: `1382`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180013d60`
- `0x1800d5bc0`

## callees

- `0x180012000`
- `0x18001434c`
- `0x180015c8c`
- `0x180016334`
- `0x180033984`
- `0x180034240`
- `0x18003d92c`
- `0x18004a800`
- `0x18004aa34`
- `0x180051c50`
- `0x18005e9e8`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180033e52`
- `msvcrt!_resetstkoflw` at `0x180033e52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ea5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ea5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800339d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180033e40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800339d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180033e40`

## pseudocode

```c
void XMLNames::classInit(void)
{
  struct Mutex *v0; // rbx
  _DWORD *Value; // r15
  int v2; // r13d
  struct IUnknown *v3; // rax
  struct IUnknown *v4; // rax
  struct IUnknown *v5; // rax
  struct IUnknown *v6; // rax
  struct IUnknown *v7; // rax
  struct IUnknown *v8; // rax
  struct IUnknown *v9; // rax
  struct IUnknown *v10; // rax
  struct IUnknown *v11; // rax
  struct IUnknown *v12; // rax
  struct IUnknown *v13; // rax
  struct IUnknown *v14; // rax
  struct IUnknown *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  _DWORD *v18; // r14
  int i; // esi
  struct IUnknown *v20; // rax
  struct Name *v21; // rax
  struct Atom *v22; // rdi
  struct IUnknown *v23; // rax
  struct Name *v24; // rax
  struct Name *v25; // rax
  struct Name *v26; // rax
  struct Name *v27; // rax
  struct Name *v28; // rax
  struct Name *v29; // rax

  if ( !XMLNames::names )
  {
    v0 = g_pMutex;
    if ( g_pMutex )
    {
      (*(void (__fastcall **)(struct Mutex *))(*(_QWORD *)g_pMutex + 8LL))(g_pMutex);
      (*(void (__fastcall **)(struct Mutex *))(*(_QWORD *)v0 + 24LL))(v0);
    }
    Value = TlsGetValue(g_dwTlsIndex);
    v2 = Value[19];
    Value[19] = 1;
    if ( !XMLNames::names )
    {
      v3 = Atom::create((struct String *)&String::s_cstrEmpty, 0, 0);
      _globalreference::assign((_globalreference *)XMLNames::atomEmpty, v3);
      v4 = Atom::create((struct String *)&XMLNames::s_cstrXML, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomXML, v4);
      v5 = Atom::create((struct String *)&XMLNames::s_cstrXMLNS, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomXMLNS, v5);
      v6 = Atom::create((struct String *)&XMLNames::s_cstrURNXML, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomURNXML, v6);
      v7 = Atom::create((struct String *)&XMLNames::s_cstrURNXMLNS, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomURNXMLNS, v7);
      v8 = Atom::create((struct String *)&XMLNames::s_cstrDTTYPENS, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomDTTYPENS, v8);
      v9 = Atom::create((struct String *)&XMLNames::s_cstrDTTYPENSAlias, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomDTTYPENSAlias, v9);
      v10 = Atom::create((struct String *)&XMLNames::s_cstrDTTYPENS2, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomDTTYPENSOld, v10);
      v11 = Atom::create((struct String *)&XMLNames::s_cstrSCHEMA, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomSCHEMA, v11);
      v12 = Atom::create((struct String *)&XMLNames::s_cstrSCHEMAAlias, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomSCHEMAAlias, v12);
      v13 = Atom::create((struct String *)&XMLNames::s_cstrSCHEMA2, 0, 0);
      _globalreference::assign((_globalreference *)XMLNames::atomSCHEMA2, v13);
      v14 = Atom::create((struct String *)&XMLNames::s_cstrXSDSCHEMA, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomXSDSCHEMA, v14);
      v15 = Atom::create((struct String *)&XMLNames::s_cstrXSI, 0, 0);
      _globalreference::assign((_globalreference *)&XMLNames::atomXSI, v15);
      v17 = _array<_reference<TemplateAction>>::operator new(v16, 38);
      if ( v17 )
        v18 = (_DWORD *)_array<_reference<BitSet>>::_array<_reference<BitSet>>(v17);
      else
        v18 = 0;
      for ( i = 0; i < 16; ++i )
      {
        v20 = Atom::create((struct String *)(&XMLNames::cstrings)[i], 0, 0);
        v21 = Name::create((struct Atom *)v20, 0);
        if ( i < 0 || i >= v18[4] )
LABEL_37:
          Exception::throw_E_INVALIDARG();
        assign((struct IUnknown **)&v18[2 * i + 6], v21);
      }
      while ( i < 31 )
      {
        v22 = (struct Atom *)XMLNames::atomURNXML;
        v23 = Atom::create((struct String *)(&XMLNames::cstrings)[i], 0, 0);
        v24 = Name::create((struct Atom *)v23, v22);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v24);
      }
      while ( i < 32 )
      {
        v25 = Name::create((struct String *)(&XMLNames::cstrings)[i], 0, 0, XMLNames::atomURNXMLNS);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v25);
      }
      while ( i < 34 )
      {
        v26 = Name::create((struct String *)(&XMLNames::cstrings)[i], 0, 0, XMLNames::atomDTTYPENS);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v26);
      }
      while ( i < 35 )
      {
        v27 = Name::create((struct String *)(&XMLNames::cstrings)[i], 0, 0, XMLNames::atomDTTYPENSAlias);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v27);
      }
      while ( i < 36 )
      {
        v28 = Name::create((struct String *)(&XMLNames::cstrings)[i], 0, 0, XMLNames::atomDTTYPENSOld);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v28);
      }
      while ( i < 38 )
      {
        v29 = Name::create((struct String *)(&XMLNames::cstrings)[i], 0, 0, XMLNames::atomXSI);
        if ( i < 0 || i >= v18[4] )
          goto LABEL_37;
        assign((struct IUnknown **)&v18[2 * i++ + 6], v29);
      }
      _globalreference::assign((_globalreference *)&XMLNames::names, v18);
    }
    if ( Value )
      Value[19] = v2;
    if ( v0 )
    {
      (*(void (__fastcall **)(struct Mutex *))(*(_QWORD *)v0 + 32LL))(v0);
      (*(void (__fastcall **)(struct Mutex *))(*(_QWORD *)v0 + 16LL))(v0);
    }
  }
}

```

## disassembly

```asm
0x180033984  push    rbx
0x180033986  push    rsi
0x180033987  push    rdi
0x180033988  push    r12
0x18003398a  push    r13
0x18003398c  push    r14
0x18003398e  push    r15
0x180033990  sub     rsp, 30h
0x180033994  cmp     cs:?names@XMLNames@@2V?$_staticreference@V?$_array@V?$_reference@VName@@@@@@@@A, 0; _staticreference<_array<_reference<Name>>> XMLNames::names
0x18003399c  jnz     loc_180033E2A
0x1800339a2  mov     rbx, cs:?g_pMutex@@3PEAVCSMutex@@EA; CSMutex * g_pMutex
0x1800339a9  mov     [rsp+68h+arg_8], rbx
0x1800339ae  test    rbx, rbx
0x1800339b1  jz      short loc_1800339D1
0x1800339b3  mov     rax, [rbx]
0x1800339b6  mov     rcx, rbx
0x1800339b9  mov     rax, [rax+8]
0x1800339bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339c2  mov     rax, [rbx]
0x1800339c5  mov     rcx, rbx
0x1800339c8  mov     rax, [rax+18h]
0x1800339cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339d1  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800339d7  call    cs:__imp_TlsGetValue
0x1800339dd  mov     r15, rax
0x1800339e0  mov     [rsp+68h+arg_10], rax
0x1800339e8  mov     r13d, [rax+4Ch]
0x1800339ec  mov     [rsp+68h+arg_0], r13d
0x1800339f1  mov     dword ptr [rax+4Ch], 1
0x1800339f8  cmp     cs:?names@XMLNames@@2V?$_staticreference@V?$_array@V?$_reference@VName@@@@@@@@A, 0; _staticreference<_array<_reference<Name>>> XMLNames::names
0x180033a00  jnz     loc_180033DFE
0x180033a06  xor     r8d, r8d; int
0x180033a09  xor     edx, edx; Src
0x180033a0b  lea     rcx, ?s_cstrEmpty@String@@2V_CodebaseString@@B; struct String *
0x180033a12  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033a17  mov     rdx, rax; void *
0x180033a1a  lea     rcx, ?atomEmpty@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033a21  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033a26  xor     r8d, r8d; int
0x180033a29  xor     edx, edx; Src
0x180033a2b  lea     rcx, ?s_cstrXML@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033a32  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033a37  mov     rdx, rax; void *
0x180033a3a  lea     rcx, ?atomXML@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033a41  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033a46  xor     r8d, r8d; int
0x180033a49  xor     edx, edx; Src
0x180033a4b  lea     rcx, ?s_cstrXMLNS@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033a52  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033a57  mov     rdx, rax; void *
0x180033a5a  lea     rcx, ?atomXMLNS@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033a61  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033a66  xor     r8d, r8d; int
0x180033a69  xor     edx, edx; Src
0x180033a6b  lea     rcx, ?s_cstrURNXML@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033a72  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033a77  mov     rdx, rax; void *
0x180033a7a  lea     rcx, ?atomURNXML@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033a81  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033a86  xor     r8d, r8d; int
0x180033a89  xor     edx, edx; Src
0x180033a8b  lea     rcx, ?s_cstrURNXMLNS@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033a92  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033a97  mov     rdx, rax; void *
0x180033a9a  lea     rcx, ?atomURNXMLNS@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033aa1  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033aa6  xor     r8d, r8d; int
0x180033aa9  xor     edx, edx; Src
0x180033aab  lea     rcx, ?s_cstrDTTYPENS@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033ab2  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033ab7  mov     rdx, rax; void *
0x180033aba  lea     rcx, ?atomDTTYPENS@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033ac1  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033ac6  xor     r8d, r8d; int
0x180033ac9  xor     edx, edx; Src
0x180033acb  lea     rcx, ?s_cstrDTTYPENSAlias@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033ad2  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033ad7  mov     rdx, rax; void *
0x180033ada  lea     rcx, ?atomDTTYPENSAlias@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033ae1  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033ae6  xor     r8d, r8d; int
0x180033ae9  xor     edx, edx; Src
0x180033aeb  lea     rcx, ?s_cstrDTTYPENS2@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033af2  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033af7  mov     rdx, rax; void *
0x180033afa  lea     rcx, ?atomDTTYPENSOld@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033b01  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033b06  xor     r8d, r8d; int
0x180033b09  xor     edx, edx; Src
0x180033b0b  lea     rcx, ?s_cstrSCHEMA@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033b12  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033b17  mov     rdx, rax; void *
0x180033b1a  lea     rcx, ?atomSCHEMA@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033b21  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033b26  xor     r8d, r8d; int
0x180033b29  xor     edx, edx; Src
0x180033b2b  lea     rcx, ?s_cstrSCHEMAAlias@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033b32  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033b37  mov     rdx, rax; void *
0x180033b3a  lea     rcx, ?atomSCHEMAAlias@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033b41  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033b46  xor     r8d, r8d; int
0x180033b49  xor     edx, edx; Src
0x180033b4b  lea     rcx, ?s_cstrSCHEMA2@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033b52  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033b57  mov     rdx, rax; void *
0x180033b5a  lea     rcx, ?atomSCHEMA2@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033b61  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033b66  xor     r8d, r8d; int
0x180033b69  xor     edx, edx; Src
0x180033b6b  lea     rcx, ?s_cstrXSDSCHEMA@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033b72  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033b77  mov     rdx, rax; void *
0x180033b7a  lea     rcx, ?atomXSDSCHEMA@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033b81  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033b86  xor     r8d, r8d; int
0x180033b89  xor     edx, edx; Src
0x180033b8b  lea     rcx, ?s_cstrXSI@XMLNames@@2V_CodebaseString@@B; struct String *
0x180033b92  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033b97  mov     rdx, rax; void *
0x180033b9a  lea     rcx, ?atomXSI@XMLNames@@2V?$_staticreference@VAtom@@@@A; this
0x180033ba1  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033ba6  mov     edx, 26h ; '&'
0x180033bab  call    ??2?$_array@V?$_reference@VTemplateAction@@@@@@SAPEAX_KH@Z; _array<_reference<TemplateAction>>::operator new(unsigned __int64,int)
0x180033bb0  test    rax, rax
0x180033bb3  jz      short loc_180033BC2
0x180033bb5  mov     rcx, rax
0x180033bb8  call    ??0?$_array@V?$_reference@VBitSet@@@@@@QEAA@XZ; _array<_reference<BitSet>>::_array<_reference<BitSet>>(void)
0x180033bbd  mov     r14, rax
0x180033bc0  jmp     short loc_180033BC5
0x180033bc2  xor     r14d, r14d
0x180033bc5  xor     esi, esi
0x180033bc7  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033bce  mov     [rsp+68h+var_48], esi
0x180033bd2  cmp     esi, 10h
0x180033bd5  jge     short loc_180033C18
0x180033bd7  movsxd  rdi, esi
0x180033bda  xor     r8d, r8d; int
0x180033bdd  xor     edx, edx; Src
0x180033bdf  mov     rcx, [rax+rdi*8]; struct String *
0x180033be3  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033be8  xor     edx, edx; struct Atom *
0x180033bea  mov     rcx, rax; struct Atom *
0x180033bed  call    ?create@Name@@SAPEAV1@PEAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x180033bf2  test    esi, esi
0x180033bf4  js      loc_180033DE8
0x180033bfa  cmp     esi, [r14+10h]
0x180033bfe  jge     loc_180033DE8
0x180033c04  lea     rcx, [rdi+3]
0x180033c08  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033c0c  mov     rdx, rax; void *
0x180033c0f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033c14  inc     esi
0x180033c16  jmp     short loc_180033BC7
0x180033c18  cmp     esi, 1Fh
0x180033c1b  jge     short loc_180033C72
0x180033c1d  mov     rdi, cs:?atomURNXML@XMLNames@@2V?$_staticreference@VAtom@@@@A; _staticreference<Atom> XMLNames::atomURNXML
0x180033c24  movsxd  r12, esi
0x180033c27  xor     r8d, r8d; int
0x180033c2a  xor     edx, edx; Src
0x180033c2c  mov     rcx, [rax+r12*8]; struct String *
0x180033c30  call    ?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z; Atom::create(String *,ushort const *,int)
0x180033c35  mov     rdx, rdi; struct Atom *
0x180033c38  mov     rcx, rax; struct Atom *
0x180033c3b  call    ?create@Name@@SAPEAV1@PEAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x180033c40  test    esi, esi
0x180033c42  js      loc_180033DE8
0x180033c48  cmp     esi, [r14+10h]
0x180033c4c  jge     loc_180033DE8
0x180033c52  lea     rcx, [r12+3]
0x180033c57  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033c5b  mov     rdx, rax; void *
0x180033c5e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033c63  inc     esi
0x180033c65  mov     [rsp+68h+var_48], esi
0x180033c69  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033c70  jmp     short loc_180033C18
0x180033c72  cmp     esi, 20h ; ' '
0x180033c75  jge     short loc_180033CC0
0x180033c77  movsxd  rdi, esi
0x180033c7a  mov     r9, cs:?atomURNXMLNS@XMLNames@@2V?$_staticreference@VAtom@@@@A; struct Atom *
0x180033c81  xor     r8d, r8d; int
0x180033c84  xor     edx, edx; unsigned __int16 *
0x180033c86  mov     rcx, [rax+rdi*8]; struct String *
0x180033c8a  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x180033c8f  test    esi, esi
0x180033c91  js      loc_180033DE8
0x180033c97  cmp     esi, [r14+10h]
0x180033c9b  jge     loc_180033DE8
0x180033ca1  lea     rcx, [rdi+3]
0x180033ca5  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033ca9  mov     rdx, rax; void *
0x180033cac  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033cb1  inc     esi
0x180033cb3  mov     [rsp+68h+var_48], esi
0x180033cb7  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033cbe  jmp     short loc_180033C72
0x180033cc0  cmp     esi, 22h ; '"'
0x180033cc3  jge     short loc_180033D0E
0x180033cc5  movsxd  rdi, esi
0x180033cc8  mov     r9, cs:?atomDTTYPENS@XMLNames@@2V?$_staticreference@VAtom@@@@A; struct Atom *
0x180033ccf  xor     r8d, r8d; int
0x180033cd2  xor     edx, edx; unsigned __int16 *
0x180033cd4  mov     rcx, [rax+rdi*8]; struct String *
0x180033cd8  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x180033cdd  test    esi, esi
0x180033cdf  js      loc_180033DE8
0x180033ce5  cmp     esi, [r14+10h]
0x180033ce9  jge     loc_180033DE8
0x180033cef  lea     rcx, [rdi+3]
0x180033cf3  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033cf7  mov     rdx, rax; void *
0x180033cfa  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033cff  inc     esi
0x180033d01  mov     [rsp+68h+var_48], esi
0x180033d05  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033d0c  jmp     short loc_180033CC0
0x180033d0e  cmp     esi, 23h ; '#'
0x180033d11  jge     short loc_180033D5C
0x180033d13  movsxd  rdi, esi
0x180033d16  mov     r9, cs:?atomDTTYPENSAlias@XMLNames@@2V?$_staticreference@VAtom@@@@A; struct Atom *
0x180033d1d  xor     r8d, r8d; int
0x180033d20  xor     edx, edx; unsigned __int16 *
0x180033d22  mov     rcx, [rax+rdi*8]; struct String *
0x180033d26  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x180033d2b  test    esi, esi
0x180033d2d  js      loc_180033DE8
0x180033d33  cmp     esi, [r14+10h]
0x180033d37  jge     loc_180033DE8
0x180033d3d  lea     rcx, [rdi+3]
0x180033d41  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033d45  mov     rdx, rax; void *
0x180033d48  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033d4d  inc     esi
0x180033d4f  mov     [rsp+68h+var_48], esi
0x180033d53  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033d5a  jmp     short loc_180033D0E
0x180033d5c  cmp     esi, 24h ; '$'
0x180033d5f  jge     short loc_180033DA2
0x180033d61  movsxd  rdi, esi
0x180033d64  mov     r9, cs:?atomDTTYPENSOld@XMLNames@@2V?$_staticreference@VAtom@@@@A; struct Atom *
0x180033d6b  xor     r8d, r8d; int
0x180033d6e  xor     edx, edx; unsigned __int16 *
0x180033d70  mov     rcx, [rax+rdi*8]; struct String *
0x180033d74  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x180033d79  test    esi, esi
0x180033d7b  js      short loc_180033DE8
0x180033d7d  cmp     esi, [r14+10h]
0x180033d81  jge     short loc_180033DE8
0x180033d83  lea     rcx, [rdi+3]
0x180033d87  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033d8b  mov     rdx, rax; void *
0x180033d8e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033d93  inc     esi
0x180033d95  mov     [rsp+68h+var_48], esi
0x180033d99  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033da0  jmp     short loc_180033D5C
0x180033da2  cmp     esi, 26h ; '&'
0x180033da5  jge     short loc_180033DEE
0x180033da7  movsxd  rdi, esi
0x180033daa  mov     r9, cs:?atomXSI@XMLNames@@2V?$_staticreference@VAtom@@@@A; struct Atom *
0x180033db1  xor     r8d, r8d; int
0x180033db4  xor     edx, edx; unsigned __int16 *
0x180033db6  mov     rcx, [rax+rdi*8]; struct String *
0x180033dba  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x180033dbf  test    esi, esi
0x180033dc1  js      short loc_180033DE8
0x180033dc3  cmp     esi, [r14+10h]
0x180033dc7  jge     short loc_180033DE8
0x180033dc9  lea     rcx, [rdi+3]
0x180033dcd  lea     rcx, [r14+rcx*8]; struct IUnknown **
0x180033dd1  mov     rdx, rax; void *
0x180033dd4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180033dd9  inc     esi
0x180033ddb  mov     [rsp+68h+var_48], esi
0x180033ddf  lea     rax, ?cstrings@XMLNames@@2QBQEBVString@@B; String const * const near * const XMLNames::cstrings
0x180033de6  jmp     short loc_180033DA2
0x180033de8  call    ?throw_E_INVALIDARG@Exception@@SAXXZ; Exception::throw_E_INVALIDARG(void)
0x180033dee  mov     rdx, r14; void *
0x180033df1  lea     rcx, ?names@XMLNames@@2V?$_staticreference@V?$_array@V?$_reference@VName@@@@@@@@A; this
0x180033df8  call    ?assign@_globalreference@@QEAAXPEAX@Z; _globalreference::assign(void *)
0x180033dfd  nop
0x180033dfe  test    r15, r15
0x180033e01  jz      short loc_180033E07
0x180033e03  mov     [r15+4Ch], r13d
0x180033e07  test    rbx, rbx
0x180033e0a  jz      short loc_180033E2A
0x180033e0c  mov     rax, [rbx]
0x180033e0f  mov     rcx, rbx
0x180033e12  mov     rax, [rax+20h]
0x180033e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e1b  mov     rax, [rbx]
0x180033e1e  mov     rcx, rbx
0x180033e21  mov     rax, [rax+10h]
0x180033e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e2a  add     rsp, 30h
0x180033e2e  pop     r15
0x180033e30  pop     r14
0x180033e32  pop     r13
0x180033e34  pop     r12
  ... truncated ...
```
