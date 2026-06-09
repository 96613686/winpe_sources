# CXMLScriptEngine::ParseScriptText(ushort const *,ushort const *,IUnknown *,ushort const *,unsigned __int64,ulong,ulong,tagVARIANT *,tagEXCEPINFO *)

- ea: `0x180094070`
- end: `0x1800943fe`
- name: `?ParseScriptText@CXMLScriptEngine@@UEAAJPEBG0PEAUIUnknown@@0_KKKPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z`
- size: `910`
- prototype: `int(CXMLScriptEngine *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, struct tagVARIANT *, struct tagEXCEPINFO *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180026c28`
- `0x180026de4`
- `0x18002d8d0`
- `0x180036da8`
- `0x1800384a8`
- `0x18005068c`
- `0x18005f9b8`
- `0x180064034`
- `0x180068c30`
- `0x18009363c`
- `0x180093a3c`
- `0x180093fd4`
- `0x180094070`
- `0x180094510`
- `0x180094610`
- `0x180094d0c`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18009431a`
- `msvcrt!_resetstkoflw` at `0x18009431a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009436d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009436d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180094308`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180094399`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180094308`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180094399`

## pseudocode

```c
__int64 __fastcall CXMLScriptEngine::ParseScriptText(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4,
        const unsigned __int16 *a5,
        unsigned __int64 a6,
        unsigned int a7)
{
  __int64 v9; // rbx
  int v11; // esi
  struct IHTMLElement *MyScriptElement; // rdi
  const unsigned __int16 *v13; // rdx
  struct IUnknown *v14; // rcx
  int v15; // eax
  struct Object *ObjectFromIUnk; // rdi
  int v17; // edi
  const unsigned __int16 **v18; // rdi
  int v19; // r8d
  __int16 v20; // [rsp+24h] [rbp-A4h] BYREF
  struct IUnknown *v21; // [rsp+28h] [rbp-A0h] BYREF
  int v22; // [rsp+30h] [rbp-98h] BYREF
  __int64 v23; // [rsp+38h] [rbp-90h] BYREF
  XMLParser *v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+48h] [rbp-80h] BYREF
  void *v26; // [rsp+50h] [rbp-78h] BYREF
  __int64 v27; // [rsp+58h] [rbp-70h] BYREF
  int v28; // [rsp+60h] [rbp-68h]
  int v29; // [rsp+64h] [rbp-64h]
  unsigned __int16 *v30; // [rsp+68h] [rbp-60h] BYREF
  struct tagVARIANT v31; // [rsp+70h] [rbp-58h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&v25);
  v9 = v25;
  if ( v25 )
  {
    v11 = -2147467259;
    v26 = 0;
    v21 = 0;
    if ( *((_DWORD *)this + 10) == 1 )
    {
      MyScriptElement = (struct IHTMLElement *)CXMLScriptEngine::GetMyScriptElement((CXMLScriptEngine *)(this - 1));
      v26 = MyScriptElement;
      if ( MyScriptElement )
      {
        memset(&v31, 0, sizeof(v31));
        v11 = CXMLScriptEngine::AttachToXMLParser((CXMLScriptEngine *)(this - 1), (struct IXMLDOMDocument **)&v21);
        v27 = v9;
        v28 = *(_DWORD *)(v9 + 76);
        v29 = 0;
        *(_DWORD *)(v9 + 76) = 0;
        v31.vt = 9;
        v14 = 0;
        if ( v11 >= 0 )
          v14 = v21;
        v31.llVal = (LONGLONG)v14;
        v15 = SetExpandoProperty(MyScriptElement, v13, &v31);
        if ( v11 >= 0 && v21 )
        {
          if ( v15 >= 0 )
          {
            if ( (unsigned int)CXMLScriptEngine::IsSecure((CXMLScriptEngine *)(this - 1), MyScriptElement) )
            {
              ObjectFromIUnk = Object::getObjectFromIUnk(v21, &IID_Document);
              if ( ObjectFromIUnk )
              {
                v30 = a2;
                v22 = xstrlenw(a2, 0x7FFFFFFFu);
                xstrTrim((const unsigned __int16 **)&v30, &v22);
                if ( v22 > 0 )
                {
                  v23 = 0;
                  if ( (**(int (__fastcall ***)(struct Object *, GUID *, __int64 *))ObjectFromIUnk)(
                         ObjectFromIUnk,
                         &IID_IXMLParser,
                         &v23) >= 0 )
                  {
                    v24 = 0;
                    v17 = (**(__int64 (__fastcall ***)(__int64, __int64 *, XMLParser **))v23)(
                            v23,
                            qword_180130D78,
                            &v24);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                    if ( v17 >= 0 )
                    {
                      v20 = 0;
                      XMLParser::SetCurrentURL(v24, this[7]);
                      (*(void (__fastcall **)(XMLParser *))(*(_QWORD *)v24 + 16LL))(v24);
                      ((void (__fastcall *)(struct IUnknown *, unsigned __int16 *, __int16 *))v21->lpVtbl[21].Release)(
                        v21,
                        a2,
                        &v20);
                    }
                  }
                }
                v11 = 0;
              }
            }
            else
            {
              v18 = (const unsigned __int16 **)Resources::FormatSystemMessage(0x80070005);
              (*((void (__fastcall **)(const unsigned __int16 **))*v18 + 1))(v18);
              v11 = CXMLScriptEngine::RaiseScriptError((CXMLScriptEngine *)(this - 1), a7, v19, v18[3]);
              (*((void (__fastcall **)(const unsigned __int16 **))*v18 + 2))(v18);
            }
            Model::~Model((Model *)&v27);
          }
          else
          {
            v11 = v15;
            Model::~Model((Model *)&v27);
          }
        }
        else
        {
          Model::~Model((Model *)&v27);
        }
      }
    }
    ReleaseInterface((void **)&v21);
    ReleaseInterface(&v26);
    ((void (__fastcall *)(__int64))g_pfnExit)(v9);
    return (unsigned int)v11;
  }
  else
  {
    ((void (__fastcall *)(_QWORD))g_pfnExit)(0);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180094070  push    rbx
0x180094072  push    rsi
0x180094073  push    rdi
0x180094074  push    r13
0x180094076  push    r14
0x180094078  push    r15
0x18009407a  sub     rsp, 98h
0x180094081  mov     r15, rdx
0x180094084  mov     r13, rcx
0x180094087  lea     rcx, [rsp+0C8h+var_80]; this
0x18009408c  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180094091  mov     rbx, [rsp+0C8h+var_80]
0x180094096  test    rbx, rbx
0x180094099  jnz     short loc_1800940B3
0x18009409b  xor     ecx, ecx
0x18009409d  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800940a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940a9  mov     eax, 80004005h
0x1800940ae  jmp     loc_1800943ED
0x1800940b3  mov     esi, 80004005h
0x1800940b8  mov     [rsp+0C8h+var_78], 0
0x1800940c1  mov     [rsp+0C8h+var_A0], 0
0x1800940ca  lea     r14, [r13-8]
0x1800940ce  cmp     dword ptr [r14+30h], 1
0x1800940d3  jnz     loc_1800942FD
0x1800940d9  mov     rcx, r14; this
0x1800940dc  call    ?GetMyScriptElement@CXMLScriptEngine@@AEAAPEAUIHTMLElement@@XZ; CXMLScriptEngine::GetMyScriptElement(void)
0x1800940e1  mov     rdi, rax
0x1800940e4  mov     [rsp+0C8h+var_78], rax
0x1800940e9  test    rax, rax
0x1800940ec  jz      loc_1800942FD
0x1800940f2  xorps   xmm0, xmm0
0x1800940f5  xor     eax, eax
0x1800940f7  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x1800940fc  mov     qword ptr [rsp+0C8h+var_58+10h], rax
0x180094104  lea     rdx, [rsp+0C8h+var_A0]; struct IXMLDOMDocument **
0x180094109  mov     rcx, r14; this
0x18009410c  call    ?AttachToXMLParser@CXMLScriptEngine@@AEAAJPEAPEAUIXMLDOMDocument@@@Z; CXMLScriptEngine::AttachToXMLParser(IXMLDOMDocument * *)
0x180094111  mov     esi, eax
0x180094113  mov     [rsp+0C8h+var_A8], eax
0x180094117  mov     [rsp+0C8h+var_70], rbx
0x18009411c  mov     ecx, [rbx+4Ch]
0x18009411f  mov     [rsp+0C8h+var_68], ecx
0x180094123  mov     [rsp+0C8h+var_64], 0
0x18009412b  mov     dword ptr [rbx+4Ch], 0
0x180094132  mov     eax, 9
0x180094137  mov     word ptr [rsp+0C8h+var_58], ax
0x18009413c  xor     ecx, ecx
0x18009413e  test    esi, esi
0x180094140  cmovns  rcx, [rsp+0C8h+var_A0]
0x180094146  mov     qword ptr [rsp+0C8h+var_58+8], rcx
0x18009414b  lea     r8, [rsp+0C8h+var_58]; struct tagVARIANT *
0x180094150  mov     rcx, rdi; struct IHTMLElement *
0x180094153  call    ?SetExpandoProperty@@YAJPEAUIHTMLElement@@PEBGPEAUtagVARIANT@@@Z; SetExpandoProperty(IHTMLElement *,ushort const *,tagVARIANT *)
0x180094158  test    esi, esi
0x18009415a  js      loc_1800942EE
0x180094160  cmp     [rsp+0C8h+var_A0], 0
0x180094166  jz      loc_1800942EE
0x18009416c  test    eax, eax
0x18009416e  jns     short loc_180094185
0x180094170  mov     esi, eax
0x180094172  mov     [rsp+0C8h+var_A8], eax
0x180094176  lea     rcx, [rsp+0C8h+var_70]; this
0x18009417b  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x180094180  jmp     loc_1800943C8
0x180094185  mov     rdx, rdi; struct IHTMLElement *
0x180094188  mov     rcx, r14; this
0x18009418b  call    ?IsSecure@CXMLScriptEngine@@AEAAHPEAUIHTMLElement@@@Z; CXMLScriptEngine::IsSecure(IHTMLElement *)
0x180094190  test    eax, eax
0x180094192  jz      loc_18009429E
0x180094198  lea     rdx, ?IID_Document@@3U_GUID@@B; struct _GUID *
0x18009419f  mov     rcx, [rsp+0C8h+var_A0]; struct IUnknown *
0x1800941a4  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &)
0x1800941a9  mov     rdi, rax
0x1800941ac  test    rax, rax
0x1800941af  jz      loc_1800942E2
0x1800941b5  mov     [rsp+0C8h+var_60], r15
0x1800941ba  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800941bf  mov     rcx, r15; unsigned __int16 *
0x1800941c2  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800941c7  mov     [rsp+0C8h+var_98], eax
0x1800941cb  lea     rdx, [rsp+0C8h+var_98]; int *
0x1800941d0  lea     rcx, [rsp+0C8h+var_60]; unsigned __int16 **
0x1800941d5  call    ?xstrTrim@@YAXPEAPEBGPEAH@Z; xstrTrim(ushort const * *,int *)
0x1800941da  cmp     [rsp+0C8h+var_98], 0
0x1800941df  jle     loc_180094296
0x1800941e5  mov     [rsp+0C8h+var_90], 0
0x1800941ee  mov     rax, [rdi]
0x1800941f1  lea     r8, [rsp+0C8h+var_90]
0x1800941f6  lea     rdx, IID_IXMLParser
0x1800941fd  mov     rcx, rdi
0x180094200  mov     rax, [rax]
0x180094203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094208  mov     [rsp+0C8h+var_A8], eax
0x18009420c  test    eax, eax
0x18009420e  js      loc_180094296
0x180094214  mov     [rsp+0C8h+var_88], 0
0x18009421d  mov     rcx, [rsp+0C8h+var_90]
0x180094222  mov     rax, [rcx]
0x180094225  lea     r8, [rsp+0C8h+var_88]
0x18009422a  lea     rdx, qword_180130D78
0x180094231  mov     rax, [rax]
0x180094234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094239  mov     edi, eax
0x18009423b  mov     [rsp+0C8h+var_A8], eax
0x18009423f  mov     rcx, [rsp+0C8h+var_90]
0x180094244  mov     rdx, [rcx]
0x180094247  mov     rax, [rdx+10h]
0x18009424b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094250  test    edi, edi
0x180094252  js      short loc_180094296
0x180094254  xor     eax, eax
0x180094256  mov     [rsp+0C8h+var_A4], ax
0x18009425b  mov     rdx, [r13+38h]; unsigned __int16 *
0x18009425f  mov     rcx, [rsp+0C8h+var_88]; this
0x180094264  call    ?SetCurrentURL@XMLParser@@QEAAJPEBG@Z; XMLParser::SetCurrentURL(ushort const *)
0x180094269  mov     rcx, [rsp+0C8h+var_88]
0x18009426e  mov     rax, [rcx]
0x180094271  mov     rax, [rax+10h]
0x180094275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009427a  mov     rcx, [rsp+0C8h+var_A0]
0x18009427f  mov     rax, [rcx]
0x180094282  lea     r8, [rsp+0C8h+var_A4]
0x180094287  mov     rdx, r15
0x18009428a  mov     rax, [rax+208h]
0x180094291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094296  xor     esi, esi
0x180094298  mov     [rsp+0C8h+var_A8], esi
0x18009429c  jmp     short loc_1800942E2
0x18009429e  mov     ecx, 80070005h; dwMessageId
0x1800942a3  call    ?FormatSystemMessage@Resources@@SAPEAVString@@J@Z; Resources::FormatSystemMessage(long)
0x1800942a8  mov     rdi, rax
0x1800942ab  mov     rdx, [rax]
0x1800942ae  mov     rcx, rax
0x1800942b1  mov     rax, [rdx+8]
0x1800942b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942ba  mov     r9, [rdi+18h]; unsigned __int16 *
0x1800942be  mov     edx, [rsp+0C8h+arg_30]; unsigned int
0x1800942c5  mov     rcx, r14; this
0x1800942c8  call    ?RaiseScriptError@CXMLScriptEngine@@AEAAJKJPEBG@Z; CXMLScriptEngine::RaiseScriptError(ulong,long,ushort const *)
0x1800942cd  mov     esi, eax
0x1800942cf  mov     [rsp+0C8h+var_A8], eax
0x1800942d3  mov     rcx, [rdi]
0x1800942d6  mov     rax, [rcx+10h]
0x1800942da  mov     rcx, rdi
0x1800942dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942e2  lea     rcx, [rsp+0C8h+var_70]; this
0x1800942e7  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x1800942ec  jmp     short loc_1800942FD
0x1800942ee  lea     rcx, [rsp+0C8h+var_70]; this
0x1800942f3  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x1800942f8  jmp     loc_1800943C8
0x1800942fd  jmp     loc_1800943C8
0x180094302  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180094308  call    cs:__imp_TlsGetValue
0x18009430e  mov     rbx, rax
0x180094311  cmp     dword ptr [rax+54h], 0C00000FDh
0x180094318  jnz     short loc_180094393
0x18009431a  call    cs:__imp__resetstkoflw
0x180094320  test    eax, eax
0x180094322  jnz     short loc_180094375
0x180094324  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18009432b  test    rcx, rcx
0x18009432e  jz      short loc_180094342
0x180094330  cmp     [rcx+50h], rbx
0x180094334  jnz     short loc_180094342
0x180094336  mov     rax, [rcx]
0x180094339  mov     rax, [rax+20h]
0x18009433d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094342  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180094349  test    rcx, rcx
0x18009434c  jz      short loc_180094360
0x18009434e  cmp     [rcx+50h], rbx
0x180094352  jnz     short loc_180094360
0x180094354  mov     rax, [rcx]
0x180094357  mov     rax, [rax+20h]
0x18009435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094360  xor     r9d, r9d; lpArguments
0x180094363  xor     r8d, r8d; nNumberOfArguments
0x180094366  xor     edx, edx; dwExceptionFlags
0x180094368  mov     ecx, 0C00000FDh; dwExceptionCode
0x18009436d  call    cs:__imp_RaiseException
0x180094373  jmp     short loc_180094393
0x180094375  mov     rax, [rbx+60h]
0x180094379  mov     [rbx+68h], rax
0x18009437d  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180094384  mov     [rbx+60h], rax
0x180094388  mov     dword ptr [rbx+54h], 800703E9h
0x18009438f  mov     byte ptr [rbx+78h], 0
0x180094393  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180094399  call    cs:__imp_TlsGetValue
0x18009439f  mov     rcx, [rax+60h]; struct Exception *
0x1800943a3  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800943a8  mov     rdx, rax
0x1800943ab  mov     rcx, [rax]
0x1800943ae  mov     rax, [rcx+80h]
0x1800943b5  mov     rcx, rdx
0x1800943b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800943bd  mov     esi, eax
0x1800943bf  mov     [rsp+0C8h+var_A8], eax
0x1800943c3  mov     rbx, [rsp+0C8h+var_80]
0x1800943c8  lea     rcx, [rsp+0C8h+var_A0]; void **
0x1800943cd  call    ?ReleaseInterface@@YAKPEAPEAX@Z; ReleaseInterface(void * *)
0x1800943d2  lea     rcx, [rsp+0C8h+var_78]; void **
0x1800943d7  call    ?ReleaseInterface@@YAKPEAPEAX@Z; ReleaseInterface(void * *)
0x1800943dc  mov     rcx, rbx
0x1800943df  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800943e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800943eb  mov     eax, esi
0x1800943ed  add     rsp, 98h
0x1800943f4  pop     r15
0x1800943f6  pop     r14
0x1800943f8  pop     r13
0x1800943fa  pop     rdi
0x1800943fb  pop     rsi
0x1800943fc  pop     rbx
0x1800943fd  retn
0x180103b64  push    rbp
0x180103b66  sub     rsp, 20h
0x180103b6a  mov     rbp, rdx
0x180103b6d  xor     edx, edx; bool
0x180103b6f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103b74  nop
0x180103b75  add     rsp, 20h
0x180103b79  pop     rbp
0x180103b7a  retn
```
