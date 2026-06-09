# CUniversalRefresher::CNonHiPerf::CEnumRequest::Refresh(CUniversalRefresher::CNonHiPerf *)

- ea: `0x180068f50`
- end: `0x1800692f9`
- name: `?Refresh@CEnumRequest@CNonHiPerf@CUniversalRefresher@@UEAAJPEAV23@@Z`
- size: `937`
- prototype: `__int64 __fastcall(CUniversalRefresher::CNonHiPerf::CEnumRequest *__hidden this, struct CUniversalRefresher::CNonHiPerf *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180039d04`
- `0x180068f50`
- `0x180071ed4`
- `0x180091972`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180069064`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180069064`
- `wbemcomn!GetMemLogObject` at `0x180068fbd`
- `wbemcomn!GetMemLogObject` at `0x18006907a`
- `wbemcomn!GetMemLogObject` at `0x180069120`
- `wbemcomn!GetMemLogObject` at `0x180068fbd`
- `wbemcomn!GetMemLogObject` at `0x18006907a`
- `wbemcomn!GetMemLogObject` at `0x180069120`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068fc8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069085`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006912b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068fc8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069085`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006912b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::CNonHiPerf::CEnumRequest::Refresh(
        CUniversalRefresher::CNonHiPerf::CEnumRequest *this,
        struct CUniversalRefresher::CNonHiPerf *a2)
{
  int v4; // ebx
  CMemoryLog *v5; // rax
  HRESULT ProxyBlanket; // eax
  unsigned int v8; // edi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // eax
  CMemoryLog *v13; // rax
  int v14; // r14d
  int v15; // r12d
  int v16; // eax
  int v17; // esi
  unsigned int v18; // edi
  unsigned int v19; // r15d
  int v20; // eax
  __int64 i; // r15
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v23; // [rsp+58h] [rbp-A8h]
  DWORD pwAuthnSvc[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pAuthnLevel[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD pCapabilites[2]; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v27; // [rsp+88h] [rbp-78h]
  int v28[100]; // [rsp+90h] [rbp-70h] BYREF
  struct IWbemObjectAccess *v29[100]; // [rsp+220h] [rbp+120h] BYREF
  struct IWbemObjectAccess *v30[100]; // [rsp+540h] [rbp+440h] BYREF

  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)a2 + 1) + 144LL))(
         *((_QWORD *)a2 + 1),
         *((_QWORD *)this + 4),
         48);
  if ( v4 >= 0 )
  {
    v27 = v23;
    *(_OWORD *)pwAuthnSvc = 0;
    *(_OWORD *)pAuthnLevel = 0;
    *(_QWORD *)pCapabilites = 0;
    ProxyBlanket = CoQueryProxyBlanket(
                     *((IUnknown **)a2 + 1),
                     pwAuthnSvc,
                     &pwAuthnSvc[1],
                     (LPOLESTR *)&pwAuthnSvc[2],
                     pAuthnLevel,
                     &pAuthnLevel[1],
                     (RPC_AUTH_IDENTITY_HANDLE *)&pAuthnLevel[2],
                     pCapabilites);
    v8 = 0;
    if ( ProxyBlanket != -2147467262 )
      v8 = ProxyBlanket;
    if ( (v8 & 0x80000000) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v8;
      }
      v11 = 130;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, v8);
      return v8;
    }
    v12 = WbemSetProxyBlanket(
            v23,
            pwAuthnSvc[0],
            pwAuthnSvc[1],
            (unsigned __int16 *)0xFFFFFFFFFFFFFFFFLL,
            pAuthnLevel[0],
            pAuthnLevel[1],
            *(struct _COAUTHIDENTITY **)&pAuthnLevel[2],
            pCapabilites[0],
            0);
    v8 = 0;
    if ( v12 != -2147467262 )
      v8 = v12;
    if ( (v8 & 0x80000000) != 0 )
    {
      v13 = GetMemLogObject();
      CMemoryLog::Write(v13, v8);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v8;
      }
      v11 = 131;
      goto LABEL_14;
    }
    memset_0(v29, 0, sizeof(v29));
    v14 = 0;
    v15 = 1;
    if ( v8 )
    {
      v17 = v8;
LABEL_37:
      v8 = 0;
      if ( v17 < 0 )
        return (unsigned int)v17;
      return v8;
    }
    while ( 1 )
    {
      v22 = 0;
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, struct IWbemObjectAccess **, int *))v23->lpVtbl[1].AddRef)(
              v23,
              1000,
              100,
              v29,
              &v22);
      v17 = v16;
      if ( v16 >= 0 )
      {
        v18 = v22;
        if ( v22 )
          break;
      }
      if ( v16 != 262148 )
      {
LABEL_34:
        if ( v17 )
          goto LABEL_37;
      }
    }
    memset_0(v30, 0, sizeof(v30));
    v19 = 0;
    while ( v19 < v18 )
    {
      v20 = v14++;
      v28[v19] = v20;
      v17 = ((__int64 (__fastcall *)(struct IWbemObjectAccess *, GUID *, struct IWbemObjectAccess **))v29[v19]->lpVtbl->QueryInterface)(
              v29[v19],
              &IID_IWbemObjectAccess,
              &v30[v19]);
      ++v19;
      if ( v17 < 0 )
        goto LABEL_32;
      v18 = v22;
    }
    v17 = CClientLoadableHiPerfEnum::Replace(*((CClientLoadableHiPerfEnum **)this + 6), v15, v18, v28, v30);
    for ( i = 0; (unsigned int)i < v22; i = (unsigned int)(i + 1) )
    {
      ((void (__fastcall *)(struct IWbemObjectAccess *))v29[i]->lpVtbl->Release)(v29[i]);
      ((void (__fastcall *)(struct IWbemObjectAccess *))v30[i]->lpVtbl->Release)(v30[i]);
    }
LABEL_32:
    v15 = 0;
    goto LABEL_34;
  }
  v5 = GetMemLogObject();
  CMemoryLog::Write(v5, v4);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180068f50  mov     [rsp-8+arg_10], rbx
0x180068f55  push    rbp
0x180068f56  push    rsi
0x180068f57  push    rdi
0x180068f58  push    r12
0x180068f5a  push    r13
0x180068f5c  push    r14
0x180068f5e  push    r15
0x180068f60  lea     rbp, [rsp-770h]
0x180068f68  sub     rsp, 870h
0x180068f6f  mov     rax, cs:__security_cookie
0x180068f76  xor     rax, rsp
0x180068f79  mov     [rbp+7A0h+var_40], rax
0x180068f80  mov     rdi, rdx
0x180068f83  mov     r13, rcx
0x180068f86  mov     [rsp+8A0h+var_848], 0
0x180068f8f  mov     rcx, [rdx+8]
0x180068f93  mov     rax, [rcx]
0x180068f96  lea     rdx, [rsp+8A0h+var_848]
0x180068f9b  mov     [rsp+8A0h+pAuthnLevel], rdx
0x180068fa0  xor     r9d, r9d
0x180068fa3  lea     r8d, [r9+30h]
0x180068fa7  mov     rdx, [r13+20h]
0x180068fab  mov     rax, [rax+90h]
0x180068fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fb7  mov     ebx, eax
0x180068fb9  test    eax, eax
0x180068fbb  jns     short loc_18006900E
0x180068fbd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180068fc3  mov     edx, ebx
0x180068fc5  mov     rcx, rax
0x180068fc8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180068fce  lea     rcx, WPP_GLOBAL_Control
0x180068fd5  mov     r10, cs:WPP_GLOBAL_Control
0x180068fdc  cmp     r10, rcx
0x180068fdf  jz      short loc_180069007
0x180068fe1  test    byte ptr [r10+1Ch], 1
0x180068fe6  jz      short loc_180069007
0x180068fe8  cmp     byte ptr [r10+19h], 2
0x180068fed  jb      short loc_180069007
0x180068fef  mov     edx, 81h
0x180068ff4  mov     r9d, ebx
0x180068ff7  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180068ffe  mov     rcx, [r10+10h]
0x180069002  call    WPP_SF_d
0x180069007  mov     eax, ebx
0x180069009  jmp     loc_1800692CF
0x18006900e  mov     rbx, [rsp+8A0h+var_848]
0x180069013  mov     [rbp+7A0h+var_818], rbx
0x180069017  xorps   xmm0, xmm0
0x18006901a  xor     eax, eax
0x18006901c  movups  xmmword ptr [rsp+8A0h+pwAuthnSvc], xmm0
0x180069021  movups  xmmword ptr [rsp+8A0h+var_830], xmm0
0x180069026  mov     qword ptr [rbp+7A0h+var_820], rax
0x18006902a  lea     rax, [rbp+7A0h+var_820]
0x18006902e  mov     [rsp+8A0h+pCapabilites], rax; pCapabilites
0x180069033  lea     rax, [rsp+8A0h+var_830+8]
0x180069038  mov     [rsp+8A0h+pAuthInfo], rax; pAuthInfo
0x18006903d  lea     rax, [rsp+8A0h+var_830+4]
0x180069042  mov     [rsp+8A0h+pImpLevel], rax; pImpLevel
0x180069047  lea     rax, [rsp+8A0h+var_830]
0x18006904c  mov     [rsp+8A0h+pAuthnLevel], rax; pAuthnLevel
0x180069051  lea     r9, [rsp+8A0h+pwAuthnSvc+8]; pServerPrincName
0x180069056  lea     r8, [rsp+8A0h+pwAuthnSvc+4]; pAuthzSvc
0x18006905b  lea     rdx, [rsp+8A0h+pwAuthnSvc]; pwAuthnSvc
0x180069060  mov     rcx, [rdi+8]; pProxy
0x180069064  call    cs:__imp_CoQueryProxyBlanket
0x18006906a  xor     edi, edi
0x18006906c  mov     esi, 80004002h
0x180069071  cmp     eax, esi
0x180069073  cmovnz  edi, eax
0x180069076  test    edi, edi
0x180069078  jns     short loc_1800690D8
0x18006907a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180069080  mov     edx, edi
0x180069082  mov     rcx, rax
0x180069085  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006908b  lea     rcx, WPP_GLOBAL_Control
0x180069092  mov     rax, cs:WPP_GLOBAL_Control
0x180069099  cmp     rax, rcx
0x18006909c  jz      short loc_1800690C3
0x18006909e  test    byte ptr [rax+1Ch], 1
0x1800690a2  jz      short loc_1800690C3
0x1800690a4  cmp     byte ptr [rax+19h], 2
0x1800690a8  jb      short loc_1800690C3
0x1800690aa  mov     edx, 82h
0x1800690af  mov     r9d, edi
0x1800690b2  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800690b9  mov     rcx, [rax+10h]
0x1800690bd  call    WPP_SF_d
0x1800690c2  nop
0x1800690c3  test    rbx, rbx
0x1800690c6  jz      loc_1800692C5
0x1800690cc  mov     rax, [rbx]
0x1800690cf  mov     rax, [rax+10h]
0x1800690d3  jmp     loc_1800692BD
0x1800690d8  mov     [rsp+8A0h+var_860], 0; bool
0x1800690dd  mov     eax, [rbp+7A0h+var_820]
0x1800690e0  mov     dword ptr [rsp+8A0h+pCapabilites], eax; unsigned int
0x1800690e4  mov     rax, qword ptr [rsp+8A0h+var_830+8]
0x1800690e9  mov     [rsp+8A0h+pAuthInfo], rax; struct _COAUTHIDENTITY *
0x1800690ee  mov     eax, [rsp+8A0h+var_830+4]
0x1800690f2  mov     dword ptr [rsp+8A0h+pImpLevel], eax; unsigned int
0x1800690f6  mov     eax, [rsp+8A0h+var_830]
0x1800690fa  mov     dword ptr [rsp+8A0h+pAuthnLevel], eax; unsigned int
0x1800690fe  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int16 *
0x180069102  mov     r8d, [rsp+8A0h+pwAuthnSvc+4]; unsigned int
0x180069107  mov     edx, [rsp+8A0h+pwAuthnSvc]; unsigned int
0x18006910b  mov     rcx, [rsp+8A0h+var_848]; struct IUnknown *
0x180069110  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x180069115  xor     edi, edi
0x180069117  cmp     eax, esi
0x180069119  cmovnz  edi, eax
0x18006911c  test    edi, edi
0x18006911e  jns     short loc_180069166
0x180069120  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180069126  mov     edx, edi
0x180069128  mov     rcx, rax
0x18006912b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180069131  lea     rcx, WPP_GLOBAL_Control
0x180069138  mov     rax, cs:WPP_GLOBAL_Control
0x18006913f  cmp     rax, rcx
0x180069142  jz      loc_1800690C3
0x180069148  test    byte ptr [rax+1Ch], 1
0x18006914c  jz      loc_1800690C3
0x180069152  cmp     byte ptr [rax+19h], 2
0x180069156  jb      loc_1800690C3
0x18006915c  mov     edx, 83h
0x180069161  jmp     loc_1800690AF
0x180069166  xor     edx, edx; Val
0x180069168  mov     r8d, 320h; Size
0x18006916e  lea     rcx, [rbp+7A0h+var_680]; void *
0x180069175  call    memset_0
0x18006917a  xor     r14d, r14d
0x18006917d  lea     r12d, [r14+1]
0x180069181  test    edi, edi
0x180069183  jnz     loc_1800692A8
0x180069189  mov     [rsp+8A0h+var_850], 0
0x180069191  mov     rcx, [rsp+8A0h+var_848]
0x180069196  mov     rax, [rcx]
0x180069199  lea     rdx, [rsp+8A0h+var_850]
0x18006919e  mov     [rsp+8A0h+pAuthnLevel], rdx
0x1800691a3  lea     r9, [rbp+7A0h+var_680]
0x1800691aa  mov     edx, 3E8h
0x1800691af  mov     r8d, 64h ; 'd'
0x1800691b5  mov     rax, [rax+20h]
0x1800691b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691be  mov     esi, eax
0x1800691c0  test    eax, eax
0x1800691c2  js      loc_180069293
0x1800691c8  mov     edi, [rsp+8A0h+var_850]
0x1800691cc  test    edi, edi
0x1800691ce  jz      loc_180069293
0x1800691d4  xor     edx, edx; Val
0x1800691d6  mov     r8d, 320h; Size
0x1800691dc  lea     rcx, [rbp+7A0h+var_360]; void *
0x1800691e3  call    memset_0
0x1800691e8  xor     r15d, r15d
0x1800691eb  cmp     r15d, edi
0x1800691ee  jnb     short loc_180069231
0x1800691f0  mov     eax, r14d
0x1800691f3  inc     r14d
0x1800691f6  movsxd  rdx, r15d
0x1800691f9  mov     [rbp+rdx*4+7A0h+var_810], eax
0x1800691fd  mov     rcx, [rbp+rdx*8+7A0h+var_680]
0x180069205  mov     rax, [rcx]
0x180069208  lea     r8, [rbp+7A0h+var_360]
0x18006920f  lea     r8, [r8+rdx*8]
0x180069213  lea     rdx, IID_IWbemObjectAccess
0x18006921a  mov     rax, [rax]
0x18006921d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069222  mov     esi, eax
0x180069224  inc     r15d
0x180069227  test    eax, eax
0x180069229  js      short loc_18006928E
0x18006922b  mov     edi, [rsp+8A0h+var_850]
0x18006922f  jmp     short loc_1800691EB
0x180069231  lea     rax, [rbp+7A0h+var_360]
0x180069238  mov     [rsp+8A0h+pAuthnLevel], rax; struct IWbemObjectAccess **
0x18006923d  lea     r9, [rbp+7A0h+var_810]; int *
0x180069241  mov     r8d, edi; int
0x180069244  mov     edx, r12d; int
0x180069247  mov     rcx, [r13+30h]; this
0x18006924b  call    ?Replace@CClientLoadableHiPerfEnum@@QEAAJHJPEAJPEAPEAUIWbemObjectAccess@@@Z; CClientLoadableHiPerfEnum::Replace(int,long,long *,IWbemObjectAccess * *)
0x180069250  mov     esi, eax
0x180069252  xor     r15d, r15d
0x180069255  cmp     [rsp+8A0h+var_850], r15d
0x18006925a  jbe     short loc_18006928E
0x18006925c  mov     rcx, [rbp+r15*8+7A0h+var_680]
0x180069264  mov     rax, [rcx]
0x180069267  mov     rax, [rax+10h]
0x18006926b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069270  mov     rcx, [rbp+r15*8+7A0h+var_360]
0x180069278  mov     rax, [rcx]
0x18006927b  mov     rax, [rax+10h]
0x18006927f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069284  inc     r15d
0x180069287  cmp     r15d, [rsp+8A0h+var_850]
0x18006928c  jb      short loc_18006925C
0x18006928e  xor     r12d, r12d
0x180069291  jmp     short loc_18006929E
0x180069293  cmp     eax, 40004h
0x180069298  jz      loc_180069189
0x18006929e  test    esi, esi
0x1800692a0  jz      loc_180069189
0x1800692a6  jmp     short loc_1800692AA
0x1800692a8  mov     esi, edi
0x1800692aa  xor     edi, edi
0x1800692ac  test    esi, esi
0x1800692ae  cmovs   edi, esi
0x1800692b1  test    rbx, rbx
0x1800692b4  jz      short loc_1800692C5
0x1800692b6  mov     rcx, [rbx]
0x1800692b9  mov     rax, [rcx+10h]
0x1800692bd  mov     rcx, rbx
0x1800692c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692c5  mov     [rbp+7A0h+var_818], 0
0x1800692cd  mov     eax, edi
0x1800692cf  mov     rcx, [rbp+7A0h+var_40]
0x1800692d6  xor     rcx, rsp; StackCookie
0x1800692d9  call    __security_check_cookie
0x1800692de  mov     rbx, [rsp+8A0h+arg_10]
0x1800692e6  add     rsp, 870h
0x1800692ed  pop     r15
0x1800692ef  pop     r14
0x1800692f1  pop     r13
0x1800692f3  pop     r12
0x1800692f5  pop     rdi
0x1800692f6  pop     rsi
0x1800692f7  pop     rbp
0x1800692f8  retn
```
