# Document::getParser(IXMLParser3 * *)

- ea: `0x180011004`
- end: `0x18001143f`
- name: `?getParser@Document@@QEAAXPEAPEAUIXMLParser3@@@Z`
- size: `1083`
- prototype: `void __fastcall(Document *__hidden this, struct IXMLParser3 **)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001da98`
- `0x180043800`
- `0x180089960`
- `0x1800f3374`

## callees

- `0x180011004`
- `0x180012000`
- `0x18001226c`
- `0x180012e70`
- `0x18001c310`
- `0x180038db0`
- `0x180041918`
- `0x18004a8fc`
- `0x18004b488`
- `0x18005356c`
- `0x18005e9e8`
- `0x180064034`
- `0x1800f8dc0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180011385`
- `msvcrt!_resetstkoflw` at `0x180011385`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011058`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011058`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011373`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011373`

## pseudocode

```c
void __fastcall Document::getParser(Document *this, struct IXMLParser3 **a2)
{
  BOOL v4; // edi
  LPVOID v5; // rax
  __int64 v6; // rdi
  int v7; // esi
  struct DocumentVtbl *lpVtbl; // rdx
  const unsigned __int16 **v9; // rdi
  struct DocumentVtbl *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int128 v13; // [rsp+28h] [rbp-50h]
  __int128 v14; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-28h]
  XMLParser *v16; // [rsp+80h] [rbp+8h] BYREF

  v16 = 0;
  v4 = ((__int64)this[1].lpVtbl & 4LL) == 0;
  if ( g_fUseMpHeap )
    v5 = MpHeapAlloc(this, 8u, 0x158u);
  else
    v5 = HeapAlloc(g_hProcessHeap, 8u, 0x158u);
  if ( v5 )
  {
    v6 = XMLParser::XMLParser(v5, v4);
  }
  else
  {
    failure_tracing::record();
    v6 = 0;
  }
  if ( v6 )
  {
    v7 = X_CRITICAL_SECTION::Initialize((X_CRITICAL_SECTION *)(v6 + 232));
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      goto LABEL_22;
    }
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, XMLParser **))v6)(v6, &IID_IXMLParser3, &v16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    v7 = -2147024882;
  }
  if ( v7 < 0 )
LABEL_22:
    Exception::throwHR(v7);
  if ( LODWORD(this[8].lpVtbl) )
  {
    if ( !this[7].lpVtbl )
      COMSafeControlRoot::getSecureBaseURL((COMSafeControlRoot *)&this[3]);
    lpVtbl = this[7].lpVtbl;
    if ( lpVtbl || (lpVtbl = this[6].lpVtbl) != 0 )
      (*(void (__fastcall **)(XMLParser *, HRESULT (__stdcall *)(Document *, UINT *)))(*(_QWORD *)v16 + 232LL))(
        v16,
        lpVtbl->GetTypeInfoCount);
  }
  *((_DWORD *)v16 + 80) = this[8].lpVtbl;
  v9 = (const unsigned __int16 **)this[6].lpVtbl;
  if ( v9 )
  {
    (*((void (__fastcall **)(struct DocumentVtbl *))*v9 + 1))(this[6].lpVtbl);
    XMLParser::SetBaseURL(v16, v9[3]);
    (*((void (__fastcall **)(const unsigned __int16 **))*v9 + 2))(v9);
  }
  (*(void (__fastcall **)(XMLParser *, struct DocumentVtbl *))(*(_QWORD *)v16 + 176LL))(v16, this[34].lpVtbl);
  if ( !this[36].lpVtbl || (BYTE4(this[25].lpVtbl) & 0x20) != 0 )
    Document::initDefaultFactory(this, 0, 0);
  v10 = this[31].lpVtbl;
  if ( v10 )
    NamespaceMgr::reset((NamespaceMgr *)v10);
  (*(void (__fastcall **)(XMLParser *, struct DocumentVtbl *))(*(_QWORD *)v16 + 24LL))(v16, this[36].lpVtbl);
  (*(void (__fastcall **)(XMLParser *))(*(_QWORD *)v16 + 224LL))(v16);
  (*(void (__fastcall **)(XMLParser *, _QWORD))(*(_QWORD *)v16 + 248LL))(
    v16,
    (unsigned int)(HIDWORD(this[52].lpVtbl) << 10));
  v13 = 0;
  LOWORD(v13) = 19;
  DWORD2(v13) = this[53].lpVtbl;
  v11 = *(_QWORD *)v16;
  v14 = v13;
  v15 = 0;
  v12 = (*(__int64 (__fastcall **)(XMLParser *, const wchar_t *, __int128 *))(v11 + 264))(v16, L"MaxElementDepth", &v14);
  if ( v12 < 0 )
    Exception::throwHR(v12);
  assign((struct IUnknown **)&this[37], v16);
  *a2 = v16;
}

```

## disassembly

```asm
0x180011004  mov     rax, rsp
0x180011007  mov     [rax+10h], rbx
0x18001100b  mov     [rax+18h], rsi
0x18001100f  push    rdi
0x180011010  push    r14
0x180011012  push    r15
0x180011014  sub     rsp, 60h
0x180011018  mov     r15, rdx
0x18001101b  mov     rbx, rcx
0x18001101e  mov     qword ptr [rax+8], 0
0x180011026  mov     edi, [rcx+8]
0x180011029  shr     rdi, 2
0x18001102d  not     edi
0x18001102f  and     edi, 1
0x180011032  mov     r8d, 158h; dwBytes
0x180011038  mov     r14d, 8
0x18001103e  mov     edx, r14d; dwFlags
0x180011041  cmp     cs:g_fUseMpHeap, 0
0x180011048  jz      short loc_180011051
0x18001104a  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x18001104f  jmp     short loc_18001105E
0x180011051  mov     rcx, cs:g_hProcessHeap; hHeap
0x180011058  call    cs:__imp_HeapAlloc
0x18001105e  mov     rsi, rax
0x180011061  test    rax, rax
0x180011064  jnz     short loc_180011070
0x180011066  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18001106b  test    rsi, rsi
0x18001106e  jz      short loc_18001107F
0x180011070  mov     edx, edi
0x180011072  mov     rcx, rsi
0x180011075  call    ??0XMLParser@@IEAA@W4RentalEnum@@@Z; XMLParser::XMLParser(RentalEnum)
0x18001107a  mov     rdi, rax
0x18001107d  jmp     short loc_180011081
0x18001107f  xor     edi, edi
0x180011081  test    rdi, rdi
0x180011084  jnz     short loc_18001108D
0x180011086  mov     esi, 8007000Eh
0x18001108b  jmp     short loc_1800110E6
0x18001108d  lea     rcx, [rdi+0E8h]; this
0x180011094  call    ?Initialize@X_CRITICAL_SECTION@@QEAAJXZ; X_CRITICAL_SECTION::Initialize(void)
0x180011099  mov     esi, eax
0x18001109b  test    eax, eax
0x18001109d  jns     short loc_1800110B0
0x18001109f  mov     rax, [rdi]
0x1800110a2  mov     rcx, rdi
0x1800110a5  mov     rax, [rax+10h]
0x1800110a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ae  xor     edi, edi
0x1800110b0  test    esi, esi
0x1800110b2  js      loc_18001117E
0x1800110b8  mov     rax, [rdi]
0x1800110bb  lea     r8, [rsp+78h+arg_0]
0x1800110c3  lea     rdx, IID_IXMLParser3
0x1800110ca  mov     rcx, rdi
0x1800110cd  mov     rax, [rax]
0x1800110d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d5  mov     esi, eax
0x1800110d7  mov     rcx, [rdi]
0x1800110da  mov     rax, [rcx+10h]
0x1800110de  mov     rcx, rdi
0x1800110e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e6  test    esi, esi
0x1800110e8  js      loc_18001117E
0x1800110ee  cmp     dword ptr [rbx+40h], 0
0x1800110f2  jz      short loc_180011131
0x1800110f4  cmp     qword ptr [rbx+38h], 0
0x1800110f9  jnz     short loc_180011104
0x1800110fb  lea     rcx, [rbx+18h]; this
0x1800110ff  call    ?getSecureBaseURL@COMSafeControlRoot@@IEAAXXZ; COMSafeControlRoot::getSecureBaseURL(void)
0x180011104  mov     rdx, [rbx+38h]
0x180011108  test    rdx, rdx
0x18001110b  jnz     short loc_180011116
0x18001110d  mov     rdx, [rbx+30h]
0x180011111  test    rdx, rdx
0x180011114  jz      short loc_180011131
0x180011116  mov     rcx, [rsp+78h+arg_0]
0x18001111e  mov     rax, [rcx]
0x180011121  mov     rdx, [rdx+18h]
0x180011125  mov     rax, [rax+0E8h]
0x18001112c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011131  mov     ecx, [rbx+40h]
0x180011134  mov     rax, [rsp+78h+arg_0]
0x18001113c  mov     [rax+140h], ecx
0x180011142  mov     rdi, [rbx+30h]
0x180011146  test    rdi, rdi
0x180011149  jz      short loc_18001117A
0x18001114b  mov     rax, [rdi]
0x18001114e  mov     rcx, rdi
0x180011151  mov     rax, [rax+8]
0x180011155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001115a  mov     rdx, [rdi+18h]; unsigned __int16 *
0x18001115e  mov     rcx, [rsp+78h+arg_0]; this
0x180011166  call    ?SetBaseURL@XMLParser@@QEAAJPEBG@Z; XMLParser::SetBaseURL(ushort const *)
0x18001116b  mov     rax, [rdi]
0x18001116e  mov     rcx, rdi
0x180011171  mov     rax, [rax+10h]
0x180011175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001117a  test    esi, esi
0x18001117c  jns     short loc_180011186
0x18001117e  mov     ecx, esi; int
0x180011180  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180011186  mov     rcx, [rsp+78h+arg_0]
0x18001118e  mov     rax, [rcx]
0x180011191  mov     rdx, [rbx+110h]
0x180011198  mov     rax, [rax+0B0h]
0x18001119f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a4  cmp     qword ptr [rbx+120h], 0
0x1800111ac  jz      short loc_1800111B7
0x1800111ae  test    byte ptr [rbx+0CCh], 20h
0x1800111b5  jz      short loc_1800111C4
0x1800111b7  xor     r8d, r8d; struct Atom *
0x1800111ba  xor     edx, edx; Document *
0x1800111bc  mov     rcx, rbx; this
0x1800111bf  call    ?initDefaultFactory@Document@@QEAAXPEAV1@PEAVAtom@@@Z; Document::initDefaultFactory(Document *,Atom *)
0x1800111c4  mov     rcx, [rbx+0F8h]; this
0x1800111cb  test    rcx, rcx
0x1800111ce  jz      short loc_1800111D5
0x1800111d0  call    ?reset@NamespaceMgr@@QEAAXXZ; NamespaceMgr::reset(void)
0x1800111d5  mov     rcx, [rsp+78h+arg_0]
0x1800111dd  mov     rax, [rcx]
0x1800111e0  mov     rdx, [rbx+120h]
0x1800111e7  mov     rax, [rax+18h]
0x1800111eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f0  xor     edx, edx
0x1800111f2  mov     [rsp+78h+var_58], edx
0x1800111f6  mov     eax, [rbx+0C8h]
0x1800111fc  test    al, 10h
0x1800111fe  cmovz   edx, r14d
0x180011202  mov     [rsp+78h+var_58], edx
0x180011206  test    al, 2
0x180011208  jz      short loc_180011211
0x18001120a  or      edx, 4
0x18001120d  mov     [rsp+78h+var_58], edx
0x180011211  test    r14b, al
0x180011214  jz      short loc_18001121D
0x180011216  or      edx, 10h
0x180011219  mov     [rsp+78h+var_58], edx
0x18001121d  test    al, 20h
0x18001121f  jz      short loc_180011228
0x180011221  or      edx, 2
0x180011224  mov     [rsp+78h+var_58], edx
0x180011228  test    al, 4
0x18001122a  jnz     short loc_180011236
0x18001122c  cmp     qword ptr [rbx+190h], 0
0x180011234  jz      short loc_18001123D
0x180011236  or      edx, 40h
0x180011239  mov     [rsp+78h+var_58], edx
0x18001123d  test    al, 40h
0x18001123f  jz      short loc_18001124B
0x180011241  or      edx, 0FFh
0x180011247  mov     [rsp+78h+var_58], edx
0x18001124b  mov     r8d, 1000h
0x180011251  test    r8d, eax
0x180011254  jz      short loc_18001125E
0x180011256  bts     edx, 8
0x18001125a  mov     [rsp+78h+var_58], edx
0x18001125e  bt      eax, 0Dh
0x180011262  jnb     short loc_18001126C
0x180011264  bts     edx, 10h
0x180011268  mov     [rsp+78h+var_58], edx
0x18001126c  test    al, al
0x18001126e  jns     short loc_18001127A
0x180011270  or      edx, 0F0100h
0x180011276  mov     [rsp+78h+var_58], edx
0x18001127a  mov     ecx, 200h
0x18001127f  test    [rbx+0CCh], ecx
0x180011285  jz      short loc_18001128F
0x180011287  bts     edx, 0Bh
0x18001128b  mov     [rsp+78h+var_58], edx
0x18001128f  test    ecx, eax
0x180011291  jz      short loc_18001129A
0x180011293  or      edx, r8d
0x180011296  mov     [rsp+78h+var_58], edx
0x18001129a  mov     ecx, 4000h
0x18001129f  test    ecx, eax
0x1800112a1  jnz     short loc_1800112A9
0x1800112a3  or      edx, ecx
0x1800112a5  mov     [rsp+78h+var_58], edx
0x1800112a9  mov     ecx, 8000h
0x1800112ae  test    ecx, eax
0x1800112b0  jz      short loc_1800112B8
0x1800112b2  or      edx, ecx
0x1800112b4  mov     [rsp+78h+var_58], edx
0x1800112b8  mov     rcx, [rsp+78h+arg_0]
0x1800112c0  mov     rax, [rcx]
0x1800112c3  mov     rax, [rax+0E0h]
0x1800112ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112cf  mov     rcx, [rsp+78h+arg_0]
0x1800112d7  mov     rax, [rcx]
0x1800112da  mov     edx, [rbx+1A4h]
0x1800112e0  shl     edx, 0Ah
0x1800112e3  mov     rax, [rax+0F8h]
0x1800112ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ef  xorps   xmm0, xmm0
0x1800112f2  xor     edx, edx
0x1800112f4  movups  [rsp+78h+var_50], xmm0
0x1800112f9  lea     eax, [rdx+13h]
0x1800112fc  mov     word ptr [rsp+78h+var_50], ax
0x180011301  mov     eax, [rbx+1A8h]
0x180011307  mov     dword ptr [rsp+78h+var_50+8], eax
0x18001130b  mov     rcx, [rsp+78h+arg_0]
0x180011313  mov     rax, [rcx]
0x180011316  movups  xmm0, [rsp+78h+var_50]
0x18001131b  movaps  [rsp+78h+var_38], xmm0
0x180011320  mov     [rsp+78h+var_28], rdx
0x180011325  lea     r8, [rsp+78h+var_38]
0x18001132a  lea     rdx, ?s_MaxElementDepth_pwz@XMLParser@@2QBGB; "MaxElementDepth"
0x180011331  mov     rax, [rax+108h]
0x180011338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001133d  test    eax, eax
0x18001133f  jns     short loc_180011349
0x180011341  mov     ecx, eax; int
0x180011343  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180011349  lea     rcx, [rbx+128h]; struct IUnknown **
0x180011350  mov     rdx, [rsp+78h+arg_0]; void *
0x180011358  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18001135d  mov     rax, [rsp+78h+arg_0]
0x180011365  mov     [r15], rax
0x180011368  jmp     loc_180011429
0x18001136d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180011373  call    cs:__imp_TlsGetValue
0x180011379  mov     rbx, rax
0x18001137c  cmp     dword ptr [rax+54h], 0C00000FDh
0x180011383  jnz     short loc_1800113FE
0x180011385  call    cs:__imp__resetstkoflw
0x18001138b  test    eax, eax
0x18001138d  jnz     short loc_1800113E0
0x18001138f  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180011396  test    rcx, rcx
0x180011399  jz      short loc_1800113AD
0x18001139b  cmp     [rcx+50h], rbx
0x18001139f  jnz     short loc_1800113AD
0x1800113a1  mov     rax, [rcx]
0x1800113a4  mov     rax, [rax+20h]
0x1800113a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ad  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800113b4  test    rcx, rcx
0x1800113b7  jz      short loc_1800113CB
0x1800113b9  cmp     [rcx+50h], rbx
0x1800113bd  jnz     short loc_1800113CB
0x1800113bf  mov     rax, [rcx]
0x1800113c2  mov     rax, [rax+20h]
0x1800113c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113cb  xor     r9d, r9d; lpArguments
0x1800113ce  xor     r8d, r8d; nNumberOfArguments
0x1800113d1  xor     edx, edx; dwExceptionFlags
0x1800113d3  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800113d8  call    cs:__imp_RaiseException
0x1800113de  jmp     short loc_1800113FE
0x1800113e0  mov     rax, [rbx+60h]
0x1800113e4  mov     [rbx+68h], rax
0x1800113e8  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800113ef  mov     [rbx+60h], rax
0x1800113f3  mov     dword ptr [rbx+54h], 800703E9h
0x1800113fa  mov     byte ptr [rbx+78h], 0
0x1800113fe  mov     rcx, [rsp+78h+arg_0]
0x180011406  test    rcx, rcx
0x180011409  jz      short loc_180011423
0x18001140b  mov     rax, [rcx]
0x18001140e  mov     rax, [rax+10h]
0x180011412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011417  mov     [rsp+78h+arg_0], 0
0x180011423  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180011429  lea     r11, [rsp+78h+var_18]
0x18001142e  mov     rbx, [r11+28h]
0x180011432  mov     rsi, [r11+30h]
0x180011436  mov     rsp, r11
0x180011439  pop     r15
0x18001143b  pop     r14
0x18001143d  pop     rdi
0x18001143e  retn
0x180102f4a  push    rbp
0x180102f4c  sub     rsp, 20h
0x180102f50  mov     rbp, rdx
0x180102f53  xor     edx, edx; bool
0x180102f55  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180102f5a  nop
0x180102f5b  add     rsp, 20h
0x180102f5f  pop     rbp
0x180102f60  retn
```
