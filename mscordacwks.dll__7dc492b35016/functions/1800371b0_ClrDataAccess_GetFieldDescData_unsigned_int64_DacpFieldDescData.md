# ClrDataAccess::GetFieldDescData(unsigned __int64,DacpFieldDescData *)

- ea: `0x1800371b0`
- end: `0x1800375b3`
- name: `?GetFieldDescData@ClrDataAccess@@UEAAJ_KPEAUDacpFieldDescData@@@Z`
- size: `1027`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, struct DacpFieldDescData *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c968`
- `0x18001d6b8`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x1800371b0`
- `0x180040d24`
- `0x180040dd4`
- `0x180081de0`
- `0x180083a38`
- `0x180091c08`
- `0x180091d08`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800371ee`
- `KERNEL32!EnterCriticalSection` at `0x1800371ee`
- `KERNEL32!LeaveCriticalSection` at `0x180037593`
- `KERNEL32!LeaveCriticalSection` at `0x180037593`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ClrDataAccess::GetFieldDescData(
        ClrDataAccess *this,
        unsigned __int64 a2,
        struct DacpFieldDescData *a3)
{
  struct DacpFieldDescData *v3; // rdi
  int v6; // ecx
  unsigned __int64 v7; // rcx
  void *v8; // rax
  bool v9; // r8
  unsigned __int64 v10; // rcx
  void *v11; // rax
  void *v12; // rax
  __int64 v13; // rdx
  _DWORD *v14; // r15
  unsigned int v15; // ecx
  char *v16; // r14
  __int64 v17; // rdx
  int ElemTypeSlow; // esi
  unsigned int *v19; // r12
  void *v20; // rax
  unsigned __int64 *Module; // rax
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  void *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  void *v30; // rax
  __int64 v31; // rdx
  void **v33; // rbx
  int v34; // edi
  struct Exception *v35; // rbx
  BOOL v36; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v38; // rcx
  __int64 v39; // [rsp+0h] [rbp-188h] BYREF
  _QWORD *v40; // [rsp+20h] [rbp-168h] BYREF
  unsigned int v41; // [rsp+28h] [rbp-160h] BYREF
  unsigned int v42[2]; // [rsp+30h] [rbp-158h] BYREF
  struct Exception *v43; // [rsp+38h] [rbp-150h] BYREF
  void **v44; // [rsp+40h] [rbp-148h]
  char *v45; // [rsp+48h] [rbp-140h] BYREF
  unsigned int v46; // [rsp+50h] [rbp-138h]
  void **v47; // [rsp+58h] [rbp-130h] BYREF
  __int64 v48; // [rsp+60h] [rbp-128h]
  __int64 v49; // [rsp+68h] [rbp-120h]
  _DWORD *v50; // [rsp+70h] [rbp-118h] BYREF
  unsigned __int64 v51; // [rsp+78h] [rbp-110h] BYREF
  unsigned __int64 v52; // [rsp+80h] [rbp-108h] BYREF
  ClrDataAccess *v53; // [rsp+88h] [rbp-100h]
  struct Exception *v54; // [rsp+98h] [rbp-F0h]
  _QWORD v55[3]; // [rsp+A0h] [rbp-E8h] BYREF
  void **v56; // [rsp+B8h] [rbp-D0h] BYREF
  struct Exception *v57; // [rsp+C0h] [rbp-C8h] BYREF
  _BYTE v58[72]; // [rsp+D0h] [rbp-B8h] BYREF
  char *v59; // [rsp+118h] [rbp-70h]
  __int64 v60; // [rsp+120h] [rbp-68h]
  int v62; // [rsp+198h] [rbp+10h] BYREF
  struct DacpFieldDescData *v63; // [rsp+1A0h] [rbp+18h]
  unsigned __int64 v64; // [rsp+1A8h] [rbp+20h] BYREF

  v63 = a3;
  v3 = a3;
  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v53 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v54 = 0;
  try
  {
    try
    {
      v64 = a2;
      v14 = DacInstantiateTypeByAddressHelper(a2, 0x10u, 1, 1);
      v50 = v14;
      v6 = v14[3] >> 27;
      *(_DWORD *)v3 = v6;
      *((_DWORD *)v3 + 1) = v6;
      LODWORD(v43) = 0;
      v44 = 0;
      try
      {
        try
        {
          v40 = &v43;
          FieldDesc::LookupFieldTypeHandle(v14, &v51, 6);
          v7 = v51;
          if ( (v51 & 2) != 0 )
          {
            v40 = (_QWORD *)(v51 - 2);
            v8 = DacInstantiateTypeByAddressHelper(v51 - 2, 4u, 1, 1);
            TypeDesc::GetMethodTable(v8, v42);
            v7 = *(_QWORD *)v42;
          }
          else
          {
            *(_QWORD *)v42 = v51;
          }
          if ( DacInstantiateTypeByAddressHelper(v7, 0x40u, 1, 1) )
          {
            v10 = v51;
            if ( (v51 & 2) != 0 )
            {
              v40 = (_QWORD *)(v51 - 2);
              v11 = DacInstantiateTypeByAddressHelper(v51 - 2, 4u, 1, 1);
              TypeDesc::GetMethodTable(v11, &v40);
              v10 = (unsigned __int64)v40;
            }
            else
            {
              v40 = (_QWORD *)v51;
            }
            v12 = DacInstantiateTypeByAddressHelper(v10, 0x40u, 1, 1);
            LOBYTE(v13) = 1;
            *((_QWORD *)v3 + 1) = DacGetTargetAddrForHostAddr(v12, v13);
          }
          else
          {
            *((_QWORD *)v3 + 1) = 0;
          }
        }
        catch ( Exception *v56 )
        {
          Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v43);
          v44 = v56;
          throw;
        }
      }
      catch ( ... )
      {
        v55[1] = 0;
        v55[0] = &DelegatingException::`vftable';
        v55[2] = -1;
        v33 = v44;
        v47 = v44;
        v34 = 0;
        LODWORD(v48) = 0;
        if ( v44 )
        {
          v34 = 1;
          LODWORD(v48) = 1;
        }
        Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v43, (int)&v39, v9);
        *((_QWORD *)v63 + 1) = 0;
        if ( v34 )
        {
          if ( v33 )
          {
            if ( !(*((unsigned int (__fastcall **)(void **))*v33 + 10))(v33) )
              (*(void (__fastcall **)(void **, __int64))*v33)(v33, 5);
          }
          LODWORD(v48) = 0;
        }
        DelegatingException::~DelegatingException((DelegatingException *)v55);
        v3 = v63;
        v14 = v50;
      }
      v40 = 0;
      MetaSig::MetaSig(v58, v14, 0);
      MetaSig::NextArg(v58);
      v45 = v59;
      v46 = v60;
      if ( (_DWORD)v60 && (v15 = (unsigned __int8)*v59, v15 < 0x1F) )
      {
        LODWORD(v64) = (unsigned __int8)*v59;
        v16 = v59 + 1;
        v45 = v59 + 1;
        v17 = (unsigned int)(v60 - 1);
        v46 = v60 - 1;
        ElemTypeSlow = 0;
        v62 = 0;
      }
      else
      {
        ElemTypeSlow = SigParser::GetElemTypeSlow((SigParser *)&v45, (enum CorElementType *)&v64);
        v62 = ElemTypeSlow;
        if ( ElemTypeSlow < 0 )
        {
LABEL_29:
          LOBYTE(v17) = 1;
          v40 = (_QWORD *)(DacGetTargetAddrForHostAddr(v14, v17) + *(_QWORD *)v14);
          v20 = DacInstantiateTypeByAddressHelper((unsigned __int64)v40, 0x40u, 1, 1);
          Module = (unsigned __int64 *)MethodTable::GetModule(v20, &v52);
          v22 = DacInstantiateClassByVTable(*Module, 1576, 1);
          LOBYTE(v23) = 1;
          *((_QWORD *)v3 + 2) = DacGetTargetAddrForHostAddr(v22, v23);
          v25 = v14[2];
          if ( v25 < 0 )
            v26 = v25 & 0xFFFFFF;
          else
            v26 = v25 & 0x1FFFF;
          *((_DWORD *)v3 + 7) = v26 | 0x4000000;
          LOBYTE(v24) = 1;
          v52 = DacGetTargetAddrForHostAddr(v14, v24) + *(_QWORD *)v14;
          v27 = DacInstantiateTypeByAddressHelper(v52, 0x40u, 1, 1);
          LOBYTE(v28) = 1;
          *((_QWORD *)v3 + 4) = DacGetTargetAddrForHostAddr(v27, v28);
          *((_DWORD *)v3 + 10) = FieldDesc::GetOffset((FieldDesc *)v14);
          *((_DWORD *)v3 + 11) = (v14[2] >> 25) & 1;
          *((_DWORD *)v3 + 12) = (v14[2] >> 26) & 1;
          *((_DWORD *)v3 + 13) = *((_BYTE *)v14 + 11) & 1;
          LOBYTE(v29) = 1;
          v52 = DacGetTargetAddrForHostAddr(v14, v29) + 16;
          v30 = DacInstantiateTypeByAddressHelper(v52, 0x10u, 1, 1);
          LOBYTE(v31) = 1;
          *((_QWORD *)v3 + 7) = DacGetTargetAddrForHostAddr(v30, v31);
          goto LABEL_63;
        }
        v17 = v46;
        v16 = v45;
        v15 = v64;
      }
      if ( v15 - 17 <= 1 )
      {
        v19 = (unsigned int *)&v50;
        if ( v3 != (struct DacpFieldDescData *)-24LL )
          v19 = (unsigned int *)((char *)v3 + 24);
        ElemTypeSlow = CorSigUncompressData(v16, v17, &v41, v42);
        if ( ElemTypeSlow < 0 )
        {
          *v19 = 0;
        }
        else
        {
          v41 = *((_DWORD *)&g_tkCorEncodeToken + (v41 & 3)) | (v41 >> 2);
          *v19 = v41;
        }
        if ( ElemTypeSlow >= 0 )
        {
          v45 = &v16[v42[0]];
          v17 = (unsigned int)(v17 - v42[0]);
          v46 = v17;
        }
        v62 = ElemTypeSlow;
      }
      else
      {
        *((_DWORD *)v3 + 6) = 0x2000000;
        if ( !*((_QWORD *)v3 + 1) )
          *((_DWORD *)v3 + 1) = v15;
      }
      goto LABEL_29;
    }
    catch ( Exception *v57 )
    {
      v54 = v57;
      throw;
    }
  }
  catch ( ... )
  {
    v48 = 0;
    v47 = &DelegatingException::`vftable';
    v49 = -1;
    v35 = v54;
    v43 = v54;
    v36 = v54 != 0;
    LODWORD(v44) = v36;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v38 = (struct Exception *)&v47;
    if ( v35 )
      v38 = v35;
    if ( !DacExceptionFilter(v38, (ClrDataAccess *)((char *)this - 16), &v62) )
    {
      LODWORD(v44) = 0;
      throw;
    }
    if ( v36 )
    {
      if ( v35 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v35 + 80LL))(v35) )
        (**(void (__fastcall ***)(struct Exception *, __int64))v35)(v35, 5);
      LODWORD(v44) = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v47);
    ElemTypeSlow = v62;
  }
LABEL_63:
  g_dacImpl = v53;
  LeaveCriticalSection(&g_dacCritSec);
  return (unsigned int)ElemTypeSlow;
}

```

## disassembly

```asm
0x1800371b0  mov     [rsp+arg_10], r8
0x1800371b5  mov     [rsp+arg_0], rcx
0x1800371ba  push    rbx
0x1800371bb  push    rsi
0x1800371bc  push    rdi
0x1800371bd  push    r12
0x1800371bf  push    r14
0x1800371c1  push    r15
0x1800371c3  sub     rsp, 158h
0x1800371ca  mov     rdi, r8
0x1800371cd  mov     rsi, rdx
0x1800371d0  mov     r14, rcx
0x1800371d3  xor     ebx, ebx
0x1800371d5  test    rdx, rdx
0x1800371d8  jz      loc_18003759D
0x1800371de  test    r8, r8
0x1800371e1  jz      loc_18003759D
0x1800371e7  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800371ee  call    cs:__imp_EnterCriticalSection
0x1800371f4  mov     rax, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800371fb  mov     [rsp+188h+var_100], rax
0x180037203  lea     rax, [r14-10h]
0x180037207  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x18003720e  mov     [rsp+188h+arg_8], ebx
0x180037215  mov     [rsp+188h+var_F0], rbx
0x18003721d  lea     rax, [rsp+188h+var_F8]
0x180037225  mov     [rsp+188h+arg_18], rax
0x18003722d  mov     [rsp+188h+arg_18], rsi
0x180037235  mov     r9b, 1; bool
0x180037238  mov     r8b, r9b; bool
0x18003723b  lea     edx, [rbx+10h]; unsigned int
0x18003723e  mov     rcx, rsi; unsigned __int64
0x180037241  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037246  mov     r15, rax
0x180037249  mov     [rsp+188h+var_118], rax
0x18003724e  mov     ecx, [rax+0Ch]
0x180037251  shr     ecx, 1Bh
0x180037254  mov     [rdi], ecx
0x180037256  mov     [rdi+4], ecx
0x180037259  mov     dword ptr [rsp+188h+var_150], ebx
0x18003725d  mov     [rsp+188h+var_148], rbx
0x180037262  lea     rax, [rsp+188h+var_150]
0x180037267  mov     [rsp+188h+var_168], rax
0x18003726c  xor     r9d, r9d
0x18003726f  lea     r8d, [rbx+6]
0x180037273  lea     rdx, [rsp+188h+var_110]
0x180037278  mov     rcx, r15
0x18003727b  call    ?LookupFieldTypeHandle@FieldDesc@@QEAA?AVTypeHandle@@W4ClassLoadLevel@@H@Z; FieldDesc::LookupFieldTypeHandle(ClassLoadLevel,int)
0x180037280  mov     rcx, [rsp+188h+var_110]; unsigned __int64
0x180037285  test    cl, 2
0x180037288  jz      short loc_1800372B5
0x18003728a  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x18003728e  mov     [rsp+188h+var_168], rcx
0x180037293  mov     r9b, 1; bool
0x180037296  mov     r8b, r9b; bool
0x180037299  lea     edx, [rbx+4]; unsigned int
0x18003729c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800372a1  mov     rcx, rax
0x1800372a4  lea     rdx, [rsp+188h+var_158]
0x1800372a9  call    ?GetMethodTable@TypeDesc@@QEAA?AV?$__DPtr@VMethodTable@@@@XZ; TypeDesc::GetMethodTable(void)
0x1800372ae  mov     rcx, qword ptr [rsp+188h+var_158]
0x1800372b3  jmp     short loc_1800372BA
0x1800372b5  mov     qword ptr [rsp+188h+var_158], rcx
0x1800372ba  mov     r9b, 1; bool
0x1800372bd  mov     r8b, r9b; bool
0x1800372c0  mov     edx, 40h ; '@'; unsigned int
0x1800372c5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800372ca  test    rax, rax
0x1800372cd  jz      short loc_18003732B
0x1800372cf  mov     rcx, [rsp+188h+var_110]; unsigned __int64
0x1800372d4  test    cl, 2
0x1800372d7  jz      short loc_180037306
0x1800372d9  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x1800372dd  mov     [rsp+188h+var_168], rcx
0x1800372e2  mov     r9b, 1; bool
0x1800372e5  mov     r8b, r9b; bool
0x1800372e8  mov     edx, 4; unsigned int
0x1800372ed  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800372f2  mov     rcx, rax
0x1800372f5  lea     rdx, [rsp+188h+var_168]
0x1800372fa  call    ?GetMethodTable@TypeDesc@@QEAA?AV?$__DPtr@VMethodTable@@@@XZ; TypeDesc::GetMethodTable(void)
0x1800372ff  mov     rcx, [rsp+188h+var_168]
0x180037304  jmp     short loc_18003730B
0x180037306  mov     [rsp+188h+var_168], rcx
0x18003730b  mov     r9b, 1; bool
0x18003730e  mov     r8b, r9b; bool
0x180037311  mov     edx, 40h ; '@'; unsigned int
0x180037316  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003731b  mov     dl, 1
0x18003731d  mov     rcx, rax
0x180037320  call    DacGetTargetAddrForHostAddr
0x180037325  mov     [rdi+8], rax
0x180037329  jmp     short loc_18003732F
0x18003732b  mov     [rdi+8], rbx
0x18003732f  jmp     short loc_180037340
0x180037331  xor     ebx, ebx
0x180037333  mov     rdi, [rsp+188h+arg_10]
0x18003733b  mov     r15, [rsp+188h+var_118]
0x180037340  mov     [rsp+188h+var_168], rbx
0x180037345  mov     r8, rbx
0x180037348  mov     rdx, r15
0x18003734b  lea     rcx, [rsp+188h+var_B8]
0x180037353  call    ??0MetaSig@@QEAA@PEAVFieldDesc@@VTypeHandle@@@Z; MetaSig::MetaSig(FieldDesc *,TypeHandle)
0x180037358  lea     rcx, [rsp+188h+var_B8]
0x180037360  call    ?NextArg@MetaSig@@QEAA?AW4CorElementType@@XZ; MetaSig::NextArg(void)
0x180037365  mov     r14, [rsp+188h+var_70]
0x18003736d  mov     [rsp+188h+var_140], r14
0x180037372  mov     rax, [rsp+188h+var_68]
0x18003737a  mov     [rsp+188h+var_138], eax
0x18003737e  test    eax, eax
0x180037380  jz      short loc_1800373AC
0x180037382  movzx   ecx, byte ptr [r14]
0x180037386  cmp     ecx, 1Fh
0x180037389  jnb     short loc_1800373AC
0x18003738b  mov     dword ptr [rsp+188h+arg_18], ecx
0x180037392  inc     r14
0x180037395  mov     [rsp+188h+var_140], r14
0x18003739a  lea     edx, [rax-1]
0x18003739d  mov     [rsp+188h+var_138], edx
0x1800373a1  mov     esi, ebx
0x1800373a3  mov     [rsp+188h+arg_8], ebx
0x1800373aa  jmp     short loc_1800373DF
0x1800373ac  lea     rdx, [rsp+188h+arg_18]; enum CorElementType *
0x1800373b4  lea     rcx, [rsp+188h+var_140]; this
0x1800373b9  call    ?GetElemTypeSlow@SigParser@@QEAAJPEAW4CorElementType@@@Z; SigParser::GetElemTypeSlow(CorElementType *)
0x1800373be  mov     esi, eax
0x1800373c0  mov     [rsp+188h+arg_8], eax
0x1800373c7  test    eax, eax
0x1800373c9  js      loc_180037465
0x1800373cf  mov     edx, [rsp+188h+var_138]; unsigned int
0x1800373d3  mov     r14, [rsp+188h+var_140]
0x1800373d8  mov     ecx, dword ptr [rsp+188h+arg_18]
0x1800373df  lea     eax, [rcx-11h]
0x1800373e2  cmp     eax, 1
0x1800373e5  jbe     short loc_1800373F9
0x1800373e7  mov     dword ptr [rdi+18h], 2000000h
0x1800373ee  cmp     [rdi+8], rbx
0x1800373f2  jnz     short loc_180037465
0x1800373f4  mov     [rdi+4], ecx
0x1800373f7  jmp     short loc_180037465
0x1800373f9  lea     rax, [rdi+18h]
0x1800373fd  lea     r12, [rsp+188h+var_118]
0x180037402  test    rax, rax
0x180037405  cmovnz  r12, rax
0x180037409  lea     r9, [rsp+188h+var_158]; unsigned int *
0x18003740e  lea     r8, [rsp+188h+var_160]; unsigned int *
0x180037413  mov     rcx, r14; unsigned __int8 *
0x180037416  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x18003741b  mov     esi, eax
0x18003741d  test    eax, eax
0x18003741f  js      short loc_180037442
0x180037421  mov     ecx, [rsp+188h+var_160]
0x180037425  mov     eax, ecx
0x180037427  and     eax, 3
0x18003742a  lea     r8, ?g_tkCorEncodeToken@@3QBIB; uint const near * const g_tkCorEncodeToken
0x180037431  shr     ecx, 2
0x180037434  or      ecx, [r8+rax*4]
0x180037438  mov     [rsp+188h+var_160], ecx
0x18003743c  mov     [r12], ecx
0x180037440  jmp     short loc_180037446
0x180037442  mov     [r12], ebx
0x180037446  test    esi, esi
0x180037448  js      short loc_18003745E
0x18003744a  mov     eax, [rsp+188h+var_158]
0x18003744e  add     r14, rax
0x180037451  mov     [rsp+188h+var_140], r14
0x180037456  sub     edx, [rsp+188h+var_158]
0x18003745a  mov     [rsp+188h+var_138], edx
0x18003745e  mov     [rsp+188h+arg_8], esi
0x180037465  mov     dl, 1
0x180037467  mov     rcx, r15
0x18003746a  call    DacGetTargetAddrForHostAddr
0x18003746f  mov     rcx, [r15]
0x180037472  add     rcx, rax; unsigned __int64
0x180037475  mov     [rsp+188h+var_168], rcx
0x18003747a  mov     r9b, 1; bool
0x18003747d  mov     r8b, r9b; bool
0x180037480  mov     edx, 40h ; '@'; unsigned int
0x180037485  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003748a  lea     rdx, [rsp+188h+var_108]
0x180037492  mov     rcx, rax
0x180037495  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x18003749a  mov     r8b, 1
0x18003749d  mov     edx, 628h
0x1800374a2  mov     rcx, [rax]; unsigned __int64
0x1800374a5  call    DacInstantiateClassByVTable
0x1800374aa  mov     dl, 1
0x1800374ac  mov     rcx, rax
0x1800374af  call    DacGetTargetAddrForHostAddr
0x1800374b4  mov     [rdi+10h], rax
0x1800374b8  mov     eax, [r15+8]
0x1800374bc  test    eax, eax
0x1800374be  js      short loc_1800374CB
0x1800374c0  and     eax, 1FFFFh
0x1800374c5  bts     eax, 1Ah
0x1800374c9  jmp     short loc_1800374D4
0x1800374cb  and     eax, 0FFFFFFh
0x1800374d0  bts     eax, 1Ah
0x1800374d4  mov     [rdi+1Ch], eax
0x1800374d7  mov     dl, 1
0x1800374d9  mov     rcx, r15
0x1800374dc  call    DacGetTargetAddrForHostAddr
0x1800374e1  mov     rcx, [r15]
0x1800374e4  add     rcx, rax; unsigned __int64
0x1800374e7  mov     [rsp+188h+var_108], rcx
0x1800374ef  mov     r9b, 1; bool
0x1800374f2  mov     r8b, r9b; bool
0x1800374f5  mov     edx, 40h ; '@'; unsigned int
0x1800374fa  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800374ff  mov     dl, 1
0x180037501  mov     rcx, rax
0x180037504  call    DacGetTargetAddrForHostAddr
0x180037509  mov     [rdi+20h], rax
0x18003750d  mov     rcx, r15; this
0x180037510  call    ?GetOffset@FieldDesc@@QEAAKXZ; FieldDesc::GetOffset(void)
0x180037515  mov     [rdi+28h], eax
0x180037518  mov     eax, [r15+8]
0x18003751c  shr     eax, 19h
0x18003751f  and     eax, 1
0x180037522  mov     [rdi+2Ch], eax
0x180037525  mov     eax, [r15+8]
0x180037529  shr     eax, 1Ah
0x18003752c  and     eax, 1
0x18003752f  mov     [rdi+30h], eax
0x180037532  movzx   eax, byte ptr [r15+0Bh]
0x180037537  and     eax, 1
0x18003753a  mov     [rdi+34h], eax
0x18003753d  mov     dl, 1
0x18003753f  mov     rcx, r15
0x180037542  call    DacGetTargetAddrForHostAddr
0x180037547  add     rax, 10h
0x18003754b  mov     [rsp+188h+var_108], rax
0x180037553  mov     r9b, 1; bool
0x180037556  mov     r8b, r9b; bool
0x180037559  mov     edx, 10h; unsigned int
0x18003755e  mov     rcx, rax; unsigned __int64
0x180037561  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037566  mov     dl, 1
0x180037568  mov     rcx, rax
0x18003756b  call    DacGetTargetAddrForHostAddr
0x180037570  mov     [rdi+38h], rax
0x180037574  jmp     short loc_18003757D
0x180037576  mov     esi, [rsp+188h+arg_8]
0x18003757d  mov     rdx, [rsp+188h+var_100]
0x180037585  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rdx; ClrDataAccess * g_dacImpl
0x18003758c  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180037593  call    cs:__imp_LeaveCriticalSection
0x180037599  mov     eax, esi
0x18003759b  jmp     short loc_1800375A2
0x18003759d  mov     eax, 80070057h
0x1800375a2  add     rsp, 158h
0x1800375a9  pop     r15
0x1800375ab  pop     r14
0x1800375ad  pop     r12
0x1800375af  pop     rdi
0x1800375b0  pop     rsi
0x1800375b1  pop     rbx
0x1800375b2  retn
```
