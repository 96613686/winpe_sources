# ClrDataAccess::TraverseModuleMap(ModuleMapType,unsigned __int64,void (*)(uint,unsigned __int64,void *),void *)

- ea: `0x180036180`
- end: `0x1800365a1`
- name: `?TraverseModuleMap@ClrDataAccess@@UEAAJW4ModuleMapType@@_KP6AXI1PEAX@Z2@Z`
- size: `1057`
- prototype: `int __high(enum ModuleMapType, unsigned __int64, void (__high *)(unsigned int, unsigned __int64, void *), void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000c968`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180036180`
- `0x18004067c`
- `0x180040768`
- `0x18004082c`
- `0x18007f8fc`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800361bc`
- `KERNEL32!EnterCriticalSection` at `0x1800361bc`
- `KERNEL32!LeaveCriticalSection` at `0x180036581`
- `KERNEL32!LeaveCriticalSection` at `0x180036581`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataAccess::TraverseModuleMap(
        __int64 a1,
        int a2,
        unsigned __int64 a3,
        void (__fastcall *a4)(_QWORD, __int64, __int64),
        __int64 a5)
{
  unsigned int v9; // ebx
  ClrDataAccess *v11; // r15
  __int64 *v12; // rax
  __int64 *v13; // rcx
  int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // edi
  __int64 *v17; // rax
  unsigned __int64 *Element; // rax
  unsigned __int64 v19; // rcx
  void *v20; // rax
  void *v21; // rax
  __int64 v22; // rdx
  __int64 TargetAddrForHostAddr; // rax
  __int64 v24; // rax
  unsigned int v25; // edi
  unsigned __int64 *v26; // rax
  unsigned __int64 *v27; // rax
  void *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  struct Exception *v31; // rbx
  BOOL v32; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v34; // rcx
  unsigned __int64 v35; // [rsp+20h] [rbp-158h] BYREF
  int v36; // [rsp+28h] [rbp-150h]
  int v37; // [rsp+2Ch] [rbp-14Ch]
  __int64 *v38; // [rsp+30h] [rbp-148h] BYREF
  int v39; // [rsp+38h] [rbp-140h]
  int NextCompressedEntry; // [rsp+3Ch] [rbp-13Ch]
  unsigned __int64 v41; // [rsp+40h] [rbp-138h] BYREF
  int v42; // [rsp+48h] [rbp-130h]
  unsigned __int64 v43; // [rsp+50h] [rbp-128h]
  int v44; // [rsp+58h] [rbp-120h]
  unsigned __int64 v45; // [rsp+60h] [rbp-118h]
  struct Exception *v46; // [rsp+68h] [rbp-110h] BYREF
  BOOL v47; // [rsp+70h] [rbp-108h]
  void **v48; // [rsp+78h] [rbp-100h] BYREF
  __int64 v49; // [rsp+80h] [rbp-F8h]
  unsigned __int64 v50; // [rsp+88h] [rbp-F0h]
  int v51; // [rsp+90h] [rbp-E8h]
  ClrDataAccess *v52; // [rsp+98h] [rbp-E0h]
  __int64 v53; // [rsp+A0h] [rbp-D8h]
  unsigned __int64 v54; // [rsp+A8h] [rbp-D0h]
  __int64 v55; // [rsp+B0h] [rbp-C8h]
  unsigned __int64 v56; // [rsp+B8h] [rbp-C0h]
  struct Exception *v57; // [rsp+C8h] [rbp-B0h]
  __int64 *v58; // [rsp+D0h] [rbp-A8h] BYREF
  int v59; // [rsp+D8h] [rbp-A0h]
  int v60; // [rsp+DCh] [rbp-9Ch]
  unsigned __int64 v61; // [rsp+E0h] [rbp-98h]
  int v62; // [rsp+E8h] [rbp-90h]
  unsigned __int64 v63; // [rsp+F0h] [rbp-88h]
  int v64; // [rsp+F8h] [rbp-80h]
  unsigned __int64 v65; // [rsp+100h] [rbp-78h]
  int v66; // [rsp+108h] [rbp-70h]
  unsigned __int64 v67; // [rsp+110h] [rbp-68h]
  int v68; // [rsp+118h] [rbp-60h]
  unsigned __int64 v69; // [rsp+120h] [rbp-58h]
  char v70[8]; // [rsp+128h] [rbp-50h] BYREF
  char v71[8]; // [rsp+130h] [rbp-48h] BYREF
  char v72[8]; // [rsp+138h] [rbp-40h] BYREF
  struct Exception *v73; // [rsp+140h] [rbp-38h] BYREF
  unsigned int v75; // [rsp+190h] [rbp+18h] BYREF

  v9 = 0;
  if ( !a3 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v11 = g_dacImpl;
  v52 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)(a1 - 16);
  v75 = 0;
  v57 = 0;
  try
  {
    try
    {
      v35 = a3;
      v12 = DacInstantiateClassByVTable(a3, 1576, 1);
      if ( a2 )
      {
        if ( a2 == 1 )
        {
          v13 = v12 + 56;
          v41 = -1;
          v43 = -1;
          v38 = v12 + 56;
          v14 = -1;
          v39 = -1;
          NextCompressedEntry = 0;
          v15 = v12[57];
          if ( v15 )
          {
            v53 = v13[1];
            v45 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
            v48 = (void **)(v15 & 0xFFFFFFFFFFFFFFF8uLL);
            v50 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
            LODWORD(v49) = 8 * (v15 & 7);
            v51 = v49;
            v41 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
            v42 = v49;
            v43 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
            v44 = v49;
          }
          v16 = 0;
          v36 = 0;
          while ( v13 && v13[1] )
          {
            v39 = v14 + 1;
            if ( v14 + 1 == *((_DWORD *)v13 + 4) )
            {
              v69 = *v13;
              v45 = v69;
              v17 = (__int64 *)DacInstantiateTypeByAddressHelper(v69, 0x48u, 1, 1);
              v13 = v17;
              v38 = v17;
              if ( !v17 || !v17[1] )
                goto LABEL_47;
              v39 = 0;
            }
            if ( v13[6] )
              NextCompressedEntry = LookupMapBase::GetNextCompressedEntry(
                                      (LookupMapBase *)v13,
                                      (struct BitStreamReader *)&v41,
                                      NextCompressedEntry);
            Element = (unsigned __int64 *)LookupMap<__VPtr<Module>>::Iterator::GetElement(&v38, v70);
            if ( DacInstantiateTypeByAddressHelper(*Element, 1u, 1, 1) )
            {
              v19 = *(_QWORD *)LookupMap<__VPtr<Module>>::Iterator::GetElement(&v38, v71);
              v54 = v19;
              if ( (v19 & 2) != 0 )
              {
                v54 = v19 - 2;
                v20 = DacInstantiateTypeByAddressHelper(v19 - 2, 4u, 1, 1);
                TypeDesc::GetMethodTable(v20, &v35);
                v19 = v35;
              }
              else
              {
                v35 = v19;
              }
              v21 = DacInstantiateTypeByAddressHelper(v19, 0x40u, 1, 1);
              LOBYTE(v22) = 1;
              TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v21, v22);
              a4(v16, TargetAddrForHostAddr, a5);
            }
            v36 = ++v16;
            v14 = v39;
            v13 = v38;
          }
        }
        else
        {
          v9 = -2147024809;
          v75 = -2147024809;
        }
      }
      else
      {
        v61 = -1;
        v63 = -1;
        v58 = v12 + 47;
        v59 = -1;
        v60 = 0;
        v24 = v12[48];
        if ( v24 )
        {
          v55 = v24;
          v56 = v24 & 0xFFFFFFFFFFFFFFF8uLL;
          v65 = v24 & 0xFFFFFFFFFFFFFFF8uLL;
          v67 = v24 & 0xFFFFFFFFFFFFFFF8uLL;
          v66 = 8 * (v24 & 7);
          v68 = v66;
          v61 = v24 & 0xFFFFFFFFFFFFFFF8uLL;
          v62 = v66;
          v63 = v24 & 0xFFFFFFFFFFFFFFF8uLL;
          v64 = v66;
        }
        v25 = 0;
        v37 = 0;
        while ( (unsigned int)LookupMap<__DPtr<MethodTable>>::Iterator::Next(&v58) )
        {
          v26 = (unsigned __int64 *)LookupMap<__DPtr<MethodDesc>>::Iterator::GetElement(&v58, v72);
          if ( DacInstantiateTypeByAddressHelper(*v26, 0x40u, 1, 1) )
          {
            v27 = (unsigned __int64 *)LookupMap<__DPtr<MethodDesc>>::Iterator::GetElement(&v58, &v46);
            v28 = DacInstantiateTypeByAddressHelper(*v27, 0x40u, 1, 1);
            LOBYTE(v29) = 1;
            v30 = DacGetTargetAddrForHostAddr(v28, v29);
            a4(v25, v30, a5);
          }
          v37 = ++v25;
        }
      }
    }
    catch ( Exception *v73 )
    {
      v57 = v73;
      throw;
    }
LABEL_47:
    ;
  }
  catch ( ... )
  {
    v49 = 0;
    v48 = &DelegatingException::`vftable';
    v50 = -1;
    v31 = v57;
    v46 = v57;
    v32 = v57 != 0;
    v47 = v32;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v34 = (struct Exception *)&v48;
    if ( v31 )
      v34 = v31;
    if ( !DacExceptionFilter(v34, (struct ClrDataAccess *)(a1 - 16), (int *)&v75) )
    {
      v47 = 0;
      throw;
    }
    if ( v32 )
    {
      if ( v31 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v31 + 80LL))(v31) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v31)(v31, 5);
      }
      v47 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v48);
    v11 = v52;
    v9 = v75;
  }
  g_dacImpl = v11;
  LeaveCriticalSection(&g_dacCritSec);
  return v9;
}

```

## disassembly

```asm
0x180036180  mov     [rsp+arg_8], rbx
0x180036185  mov     [rsp+arg_0], rcx
0x18003618a  push    rsi
0x18003618b  push    rdi
0x18003618c  push    r12
0x18003618e  push    r14
0x180036190  push    r15
0x180036192  sub     rsp, 150h
0x180036199  mov     r12, r9
0x18003619c  mov     rsi, r8
0x18003619f  mov     edi, edx
0x1800361a1  mov     r14, rcx
0x1800361a4  xor     ebx, ebx
0x1800361a6  test    r8, r8
0x1800361a9  jnz     short loc_1800361B5
0x1800361ab  mov     eax, 80070057h
0x1800361b0  jmp     loc_180036589
0x1800361b5  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800361bc  call    cs:__imp_EnterCriticalSection
0x1800361c2  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800361c9  mov     [rsp+178h+var_E0], r15
0x1800361d1  lea     rax, [r14-10h]
0x1800361d5  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x1800361dc  mov     [rsp+178h+arg_10], ebx
0x1800361e3  mov     [rsp+178h+var_B0], rbx
0x1800361eb  lea     rax, [rsp+178h+var_B8]
0x1800361f3  mov     [rsp+178h+var_158], rax
0x1800361f8  mov     [rsp+178h+var_158], rsi
0x1800361fd  mov     r14d, 1
0x180036203  mov     r8b, r14b
0x180036206  mov     edx, 628h
0x18003620b  mov     rcx, rsi; unsigned __int64
0x18003620e  call    DacInstantiateClassByVTable
0x180036213  mov     rcx, rax
0x180036216  test    edi, edi
0x180036218  jz      loc_180036413
0x18003621e  cmp     edi, r14d
0x180036221  jz      short loc_180036234
0x180036223  mov     ebx, 80070057h
0x180036228  mov     [rsp+178h+arg_10], ebx
0x18003622f  jmp     loc_180036573
0x180036234  add     rcx, 1C0h
0x18003623b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003623f  mov     [rsp+178h+var_138], rdx
0x180036244  mov     [rsp+178h+var_128], rdx
0x180036249  mov     [rsp+178h+var_148], rcx
0x18003624e  or      r8d, 0FFFFFFFFh
0x180036252  mov     [rsp+178h+var_140], r8d
0x180036257  mov     [rsp+178h+var_13C], ebx
0x18003625b  mov     rax, [rcx+8]
0x18003625f  test    rax, rax
0x180036262  jz      short loc_1800362C5
0x180036264  mov     [rsp+178h+var_D8], rax
0x18003626c  mov     [rsp+178h+var_D8], rax
0x180036274  mov     [rsp+178h+var_118], rax
0x180036279  mov     [rsp+178h+var_100], rdx
0x18003627e  mov     [rsp+178h+var_F0], rdx
0x180036286  mov     rdx, rax
0x180036289  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18003628d  mov     [rsp+178h+var_118], rdx
0x180036292  mov     [rsp+178h+var_100], rdx
0x180036297  mov     [rsp+178h+var_F0], rdx
0x18003629f  and     eax, 7
0x1800362a2  shl     eax, 3
0x1800362a5  mov     dword ptr [rsp+178h+var_F8], eax
0x1800362ac  mov     [rsp+178h+var_E8], eax
0x1800362b3  mov     [rsp+178h+var_138], rdx
0x1800362b8  mov     [rsp+178h+var_130], eax
0x1800362bc  mov     [rsp+178h+var_128], rdx
0x1800362c1  mov     [rsp+178h+var_120], eax
0x1800362c5  mov     edi, ebx
0x1800362c7  mov     [rsp+178h+var_150], ebx
0x1800362cb  test    rcx, rcx
0x1800362ce  jz      loc_18003640E
0x1800362d4  cmp     [rcx+8], rbx
0x1800362d8  jz      loc_18003640E
0x1800362de  add     r8d, r14d
0x1800362e1  mov     [rsp+178h+var_140], r8d
0x1800362e6  cmp     r8d, [rcx+10h]
0x1800362ea  jnz     short loc_18003632B
0x1800362ec  mov     rcx, [rcx]; unsigned __int64
0x1800362ef  mov     [rsp+178h+var_58], rcx
0x1800362f7  mov     [rsp+178h+var_118], rcx
0x1800362fc  mov     r9b, r14b; bool
0x1800362ff  mov     r8b, r14b; bool
0x180036302  mov     edx, 48h ; 'H'; unsigned int
0x180036307  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003630c  mov     rcx, rax; this
0x18003630f  mov     [rsp+178h+var_148], rax
0x180036314  test    rax, rax
0x180036317  jz      loc_18003640E
0x18003631d  cmp     [rax+8], rbx
0x180036321  jz      loc_18003640E
0x180036327  mov     [rsp+178h+var_140], ebx
0x18003632b  cmp     [rcx+30h], rbx
0x18003632f  jz      short loc_180036344
0x180036331  mov     r8d, [rsp+178h+var_13C]; int
0x180036336  lea     rdx, [rsp+178h+var_138]; struct BitStreamReader *
0x18003633b  call    ?GetNextCompressedEntry@LookupMapBase@@IEAAHPEAVBitStreamReader@@H@Z; LookupMapBase::GetNextCompressedEntry(BitStreamReader *,int)
0x180036340  mov     [rsp+178h+var_13C], eax
0x180036344  lea     rdx, [rsp+178h+var_50]
0x18003634c  lea     rcx, [rsp+178h+var_148]
0x180036351  call    ?GetElement@Iterator@?$LookupMap@V?$__VPtr@VModule@@@@@@QEAA?AV?$__VPtr@VModule@@@@XZ; LookupMap<__VPtr<Module>>::Iterator::GetElement(void)
0x180036356  mov     r9b, r14b; bool
0x180036359  mov     r8b, r14b; bool
0x18003635c  mov     edx, r14d; unsigned int
0x18003635f  mov     rcx, [rax]; unsigned __int64
0x180036362  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036367  test    rax, rax
0x18003636a  jz      loc_1800363F8
0x180036370  lea     rdx, [rsp+178h+var_48]
0x180036378  lea     rcx, [rsp+178h+var_148]
0x18003637d  call    ?GetElement@Iterator@?$LookupMap@V?$__VPtr@VModule@@@@@@QEAA?AV?$__VPtr@VModule@@@@XZ; LookupMap<__VPtr<Module>>::Iterator::GetElement(void)
0x180036382  mov     rcx, [rax]; unsigned __int64
0x180036385  mov     [rsp+178h+var_D0], rcx
0x18003638d  test    cl, 2
0x180036390  jz      short loc_1800363C2
0x180036392  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180036396  mov     [rsp+178h+var_D0], rcx
0x18003639e  mov     r9b, r14b; bool
0x1800363a1  mov     r8b, r14b; bool
0x1800363a4  mov     edx, 4; unsigned int
0x1800363a9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800363ae  mov     rcx, rax
0x1800363b1  lea     rdx, [rsp+178h+var_158]
0x1800363b6  call    ?GetMethodTable@TypeDesc@@QEAA?AV?$__DPtr@VMethodTable@@@@XZ; TypeDesc::GetMethodTable(void)
0x1800363bb  mov     rcx, [rsp+178h+var_158]
0x1800363c0  jmp     short loc_1800363C7
0x1800363c2  mov     [rsp+178h+var_158], rcx
0x1800363c7  mov     r9b, r14b; bool
0x1800363ca  mov     r8b, r14b; bool
0x1800363cd  mov     edx, 40h ; '@'; unsigned int
0x1800363d2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800363d7  mov     dl, r14b
0x1800363da  mov     rcx, rax
0x1800363dd  call    DacGetTargetAddrForHostAddr
0x1800363e2  mov     rdx, rax
0x1800363e5  mov     r8, [rsp+178h+arg_20]
0x1800363ed  mov     ecx, edi
0x1800363ef  mov     rax, r12
0x1800363f2  call    cs:__guard_dispatch_icall_fptr
0x1800363f8  add     edi, r14d
0x1800363fb  mov     [rsp+178h+var_150], edi
0x1800363ff  mov     r8d, [rsp+178h+var_140]
0x180036404  mov     rcx, [rsp+178h+var_148]
0x180036409  jmp     loc_1800362CB
0x18003640e  jmp     loc_18003622F
0x180036413  add     rax, 178h
0x180036419  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003641d  mov     [rsp+178h+var_98], rdx
0x180036425  mov     [rsp+178h+var_88], rdx
0x18003642d  mov     [rsp+178h+var_A8], rax
0x180036435  or      r8d, 0FFFFFFFFh
0x180036439  mov     [rsp+178h+var_A0], r8d
0x180036441  mov     [rsp+178h+var_9C], ebx
0x180036448  mov     rax, [rax+8]
0x18003644c  test    rax, rax
0x18003644f  jz      short loc_1800364CA
0x180036451  mov     [rsp+178h+var_C8], rax
0x180036459  mov     [rsp+178h+var_C8], rax
0x180036461  mov     [rsp+178h+var_C0], rax
0x180036469  mov     [rsp+178h+var_78], rdx
0x180036471  mov     [rsp+178h+var_68], rdx
0x180036479  mov     rcx, rax
0x18003647c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180036480  mov     [rsp+178h+var_C0], rcx
0x180036488  mov     [rsp+178h+var_78], rcx
0x180036490  mov     [rsp+178h+var_68], rcx
0x180036498  and     eax, 7
0x18003649b  shl     eax, 3
0x18003649e  mov     [rsp+178h+var_70], eax
0x1800364a5  mov     [rsp+178h+var_60], eax
0x1800364ac  mov     [rsp+178h+var_98], rcx
0x1800364b4  mov     [rsp+178h+var_90], eax
0x1800364bb  mov     [rsp+178h+var_88], rcx
0x1800364c3  mov     [rsp+178h+var_80], eax
0x1800364ca  mov     edi, ebx
0x1800364cc  mov     [rsp+178h+var_14C], ebx
0x1800364d0  lea     rcx, [rsp+178h+var_A8]
0x1800364d8  call    ?Next@Iterator@?$LookupMap@V?$__DPtr@VMethodTable@@@@@@QEAAHXZ; LookupMap<__DPtr<MethodTable>>::Iterator::Next(void)
0x1800364dd  test    eax, eax
0x1800364df  jz      loc_18003622F
0x1800364e5  lea     rdx, [rsp+178h+var_40]
0x1800364ed  lea     rcx, [rsp+178h+var_A8]
0x1800364f5  call    ?GetElement@Iterator@?$LookupMap@V?$__DPtr@VMethodDesc@@@@@@QEAA?AV?$__DPtr@VMethodDesc@@@@XZ; LookupMap<__DPtr<MethodDesc>>::Iterator::GetElement(void)
0x1800364fa  mov     r9b, r14b; bool
0x1800364fd  mov     r8b, r14b; bool
0x180036500  mov     edx, 40h ; '@'; unsigned int
0x180036505  mov     rcx, [rax]; unsigned __int64
0x180036508  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003650d  test    rax, rax
0x180036510  jz      short loc_180036558
0x180036512  lea     rdx, [rsp+178h+var_110]
0x180036517  lea     rcx, [rsp+178h+var_A8]
0x18003651f  call    ?GetElement@Iterator@?$LookupMap@V?$__DPtr@VMethodDesc@@@@@@QEAA?AV?$__DPtr@VMethodDesc@@@@XZ; LookupMap<__DPtr<MethodDesc>>::Iterator::GetElement(void)
0x180036524  mov     r9b, r14b; bool
0x180036527  mov     r8b, r14b; bool
0x18003652a  mov     edx, 40h ; '@'; unsigned int
0x18003652f  mov     rcx, [rax]; unsigned __int64
0x180036532  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036537  mov     dl, r14b
0x18003653a  mov     rcx, rax
0x18003653d  call    DacGetTargetAddrForHostAddr
0x180036542  mov     rdx, rax
0x180036545  mov     r8, [rsp+178h+arg_20]
0x18003654d  mov     ecx, edi
0x18003654f  mov     rax, r12
0x180036552  call    cs:__guard_dispatch_icall_fptr
0x180036558  add     edi, r14d
0x18003655b  mov     [rsp+178h+var_14C], edi
0x18003655f  jmp     loc_1800364D0
0x180036564  mov     r15, [rsp+178h+var_E0]
0x18003656c  mov     ebx, [rsp+178h+arg_10]
0x180036573  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x18003657a  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036581  call    cs:__imp_LeaveCriticalSection
0x180036587  mov     eax, ebx
0x180036589  mov     rbx, [rsp+178h+arg_8]
0x180036591  add     rsp, 150h
0x180036598  pop     r15
0x18003659a  pop     r14
0x18003659c  pop     r12
0x18003659e  pop     rdi
0x18003659f  pop     rsi
0x1800365a0  retn
```
