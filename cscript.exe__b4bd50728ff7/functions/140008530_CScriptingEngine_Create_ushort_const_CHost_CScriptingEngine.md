# CScriptingEngine::Create(ushort const *,CHost *,CScriptingEngine * *)

- ea: `0x140008530`
- end: `0x140008792`
- name: `?Create@CScriptingEngine@@SAJPEBGPEAVCHost@@PEAPEAV1@@Z`
- size: `610`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, struct CHost *, struct CScriptingEngine **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001950`

## callees

- `0x1400074ec`
- `0x140008530`
- `0x140009c70`
- `0x14000fc0c`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1400085b8`
- `ole32!CLSIDFromString` at `0x1400085b8`
- `ole32!CoCreateInstance` at `0x1400085e4`
- `ole32!CoCreateInstance` at `0x1400085e4`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::Create(LPCOLESTR lpsz, struct CHost *a2, struct CScriptingEngine **a3)
{
  int v4; // ebp
  CScriptingEngine *v7; // rax
  struct IUnknown *v8; // rdx
  CScriptingEngine *v9; // rax
  CScriptingEngine *v10; // rbx
  HRESULT v11; // edi
  _QWORD *v12; // rsi
  char v13; // al
  unsigned int v14; // eax
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  pclsid = 0;
  ppv = 0;
  v7 = (CScriptingEngine *)operator new(0xB8u);
  if ( !v7 )
  {
    v10 = 0;
    goto LABEL_17;
  }
  v9 = CScriptingEngine::CScriptingEngine(v7, v8);
  v10 = v9;
  if ( !v9 )
  {
LABEL_17:
    v11 = -2147024882;
    goto LABEL_18;
  }
  v11 = CCharSink::Init((CScriptingEngine *)((char *)v9 + 120), 0x1000u);
  if ( v11 >= 0 )
  {
    *((_QWORD *)v10 + 14) = a2;
    v11 = CLSIDFromString(lpsz, &pclsid);
    if ( v11 >= 0 )
    {
      v11 = CoCreateInstance(&pclsid, 0, 0x17u, &IID_IUnknown, &ppv);
      if ( v11 >= 0 )
      {
        v12 = (_QWORD *)((char *)v10 + 96);
        v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(ppv, &IID_IActiveScript, (__int64)v10 + 96);
        if ( v11 >= 0 )
        {
          v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                  ppv,
                  &IID_IActiveScriptParse64,
                  (__int64)v10 + 104);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, CScriptingEngine *))(*(_QWORD *)*v12 + 24LL))(*v12, v10);
            if ( v11 >= 0 )
            {
              v4 = 1;
              v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 13) + 24LL))(*((_QWORD *)v10 + 13));
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)*v12 + 64LL))(
                        *v12,
                        L"WScript",
                        2);
                if ( v11 >= 0 )
                {
                  v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)*v12 + 64LL))(
                          *v12,
                          L"WSH",
                          2);
                  if ( v11 >= 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v12 + 40LL))(*v12, 5);
                    if ( v11 >= 0 )
                    {
                      v13 = *((_BYTE *)a2 + 71);
                      *((_BYTE *)v10 + 176) = v13;
                      if ( !v13
                        || (v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v12)(
                                    *v12,
                                    &IID_IActiveScriptDebug64,
                                    (__int64)v10 + 168),
                            v11 >= 0) )
                      {
                        v14 = CScriptingEngine::m_contextCount + 1;
                        *((_DWORD *)v10 + 22) = CScriptingEngine::m_contextCount + 1;
                        *a3 = v10;
                        v10 = 0;
                        v11 = 0;
                        CScriptingEngine::m_contextCount = v14;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v10 )
  {
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 12) + 56LL))(*((_QWORD *)v10 + 12));
    (*(void (__fastcall **)(CScriptingEngine *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140008530  mov     [rsp+arg_8], rbx
0x140008535  mov     [rsp+arg_18], rbp
0x14000853a  push    rsi
0x14000853b  push    rdi
0x14000853c  push    r12
0x14000853e  push    r14
0x140008540  push    r15
0x140008542  sub     rsp, 50h
0x140008546  mov     rax, cs:__security_cookie
0x14000854d  xor     rax, rsp
0x140008550  mov     [rsp+78h+var_30], rax
0x140008555  mov     rsi, rcx
0x140008558  xorps   xmm0, xmm0
0x14000855b  xor     ebp, ebp
0x14000855d  mov     ecx, 0B8h; Size
0x140008562  movups  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x140008567  mov     [rsp+78h+var_48], rbp
0x14000856c  mov     r12, r8
0x14000856f  mov     r14, rdx
0x140008572  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008577  test    rax, rax
0x14000857a  jz      loc_140008725
0x140008580  mov     rcx, rax; this
0x140008583  call    ??0CScriptingEngine@@AEAA@PEAUIUnknown@@@Z; CScriptingEngine::CScriptingEngine(IUnknown *)
0x140008588  mov     rbx, rax
0x14000858b  test    rax, rax
0x14000858e  jz      loc_140008727
0x140008594  lea     rcx, [rax+78h]; this
0x140008598  mov     edx, 1000h; unsigned int
0x14000859d  call    ?Init@CCharSink@@QEAAJK@Z; CCharSink::Init(ulong)
0x1400085a2  mov     edi, eax
0x1400085a4  test    eax, eax
0x1400085a6  js      loc_14000872C
0x1400085ac  lea     rdx, [rsp+78h+pclsid]; pclsid
0x1400085b1  mov     [rbx+70h], r14
0x1400085b5  mov     rcx, rsi; lpsz
0x1400085b8  call    cs:__imp_CLSIDFromString
0x1400085be  mov     edi, eax
0x1400085c0  test    eax, eax
0x1400085c2  js      loc_14000872C
0x1400085c8  lea     rax, [rsp+78h+var_48]
0x1400085cd  xor     edx, edx; pUnkOuter
0x1400085cf  lea     r9, IID_IUnknown; riid
0x1400085d6  mov     [rsp+78h+ppv], rax; ppv
0x1400085db  lea     r8d, [rbp+17h]; dwClsContext
0x1400085df  lea     rcx, [rsp+78h+pclsid]; rclsid
0x1400085e4  call    cs:__imp_CoCreateInstance
0x1400085ea  mov     edi, eax
0x1400085ec  test    eax, eax
0x1400085ee  js      loc_14000872C
0x1400085f4  mov     rcx, [rsp+78h+var_48]
0x1400085f9  lea     rsi, [rbx+60h]
0x1400085fd  mov     r8, rsi
0x140008600  lea     rdx, IID_IActiveScript
0x140008607  mov     rax, [rcx]
0x14000860a  mov     rax, [rax]
0x14000860d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008612  mov     edi, eax
0x140008614  test    eax, eax
0x140008616  js      loc_14000872C
0x14000861c  mov     rcx, [rsp+78h+var_48]
0x140008621  lea     r8, [rbx+68h]
0x140008625  lea     rdx, IID_IActiveScriptParse64
0x14000862c  mov     rax, [rcx]
0x14000862f  mov     rax, [rax]
0x140008632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008637  mov     edi, eax
0x140008639  test    eax, eax
0x14000863b  js      loc_14000872C
0x140008641  mov     rcx, [rsi]
0x140008644  mov     rdx, rbx
0x140008647  mov     rax, [rcx]
0x14000864a  mov     rax, [rax+18h]
0x14000864e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008653  mov     edi, eax
0x140008655  test    eax, eax
0x140008657  js      loc_14000872C
0x14000865d  mov     rcx, [rbx+68h]
0x140008661  mov     ebp, 1
0x140008666  mov     rax, [rcx]
0x140008669  mov     rax, [rax+18h]
0x14000866d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008672  mov     edi, eax
0x140008674  test    eax, eax
0x140008676  js      loc_14000872C
0x14000867c  mov     rcx, [rsi]
0x14000867f  lea     r15d, [rbp+1]
0x140008683  mov     r8d, r15d
0x140008686  lea     rdx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x14000868d  mov     rax, [rcx]
0x140008690  mov     rax, [rax+40h]
0x140008694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008699  mov     edi, eax
0x14000869b  test    eax, eax
0x14000869d  js      loc_14000872C
0x1400086a3  mov     rcx, [rsi]
0x1400086a6  lea     rdx, ?GWSZ_WSH@@3QBGB; "WSH"
0x1400086ad  mov     r8d, r15d
0x1400086b0  mov     rax, [rcx]
0x1400086b3  mov     rax, [rax+40h]
0x1400086b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086bc  mov     edi, eax
0x1400086be  test    eax, eax
0x1400086c0  js      short loc_14000872C
0x1400086c2  mov     rcx, [rsi]
0x1400086c5  lea     edx, [rbp+4]
0x1400086c8  mov     rax, [rcx]
0x1400086cb  mov     rax, [rax+28h]
0x1400086cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086d4  mov     edi, eax
0x1400086d6  test    eax, eax
0x1400086d8  js      short loc_14000872C
0x1400086da  mov     al, [r14+47h]
0x1400086de  mov     [rbx+0B0h], al
0x1400086e4  test    al, al
0x1400086e6  jz      short loc_14000870A
0x1400086e8  mov     rcx, [rsi]
0x1400086eb  lea     r8, [rbx+0A8h]
0x1400086f2  lea     rdx, IID_IActiveScriptDebug64
0x1400086f9  mov     rax, [rcx]
0x1400086fc  mov     rax, [rax]
0x1400086ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008704  mov     edi, eax
0x140008706  test    eax, eax
0x140008708  js      short loc_14000872C
0x14000870a  mov     eax, cs:?m_contextCount@CScriptingEngine@@0KA; ulong CScriptingEngine::m_contextCount
0x140008710  add     eax, ebp
0x140008712  mov     [rbx+58h], eax
0x140008715  mov     [r12], rbx
0x140008719  xor     ebx, ebx
0x14000871b  xor     edi, edi
0x14000871d  mov     cs:?m_contextCount@CScriptingEngine@@0KA, eax; ulong CScriptingEngine::m_contextCount
0x140008723  jmp     short loc_14000872C
0x140008725  xor     ebx, ebx
0x140008727  mov     edi, 8007000Eh
0x14000872c  mov     rcx, [rsp+78h+var_48]
0x140008731  test    rcx, rcx
0x140008734  jz      short loc_140008742
0x140008736  mov     rax, [rcx]
0x140008739  mov     rax, [rax+10h]
0x14000873d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008742  test    rbx, rbx
0x140008745  jz      short loc_14000876A
0x140008747  test    ebp, ebp
0x140008749  jz      short loc_14000875B
0x14000874b  mov     rcx, [rbx+60h]
0x14000874f  mov     rax, [rcx]
0x140008752  mov     rax, [rax+38h]
0x140008756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000875b  mov     rax, [rbx]
0x14000875e  mov     rcx, rbx
0x140008761  mov     rax, [rax+10h]
0x140008765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000876a  mov     eax, edi
0x14000876c  mov     rcx, [rsp+78h+var_30]
0x140008771  xor     rcx, rsp; StackCookie
0x140008774  call    __security_check_cookie
0x140008779  lea     r11, [rsp+78h+var_28]
0x14000877e  mov     rbx, [r11+38h]
0x140008782  mov     rbp, [r11+48h]
0x140008786  mov     rsp, r11
0x140008789  pop     r15
0x14000878b  pop     r14
0x14000878d  pop     r12
0x14000878f  pop     rdi
0x140008790  pop     rsi
0x140008791  retn
```
