# DacDbiInterfaceImpl::Hijack(VMPTR_Base<Thread,__VPtr<Thread>>,uint,_EXCEPTION_RECORD const *,_CONTEXT *,uint,EHijackReason::EHijackReason,void *,unsigned __int64 *)

- ea: `0x180016490`
- end: `0x18001694c`
- name: `?Hijack@DacDbiInterfaceImpl@@UEAAXV?$VMPTR_Base@VThread@@V?$__VPtr@VThread@@@@@@IPEBU_EXCEPTION_RECORD@@PEAU_CONTEXT@@IW4EHijackReason@5@PEAXPEA_K@Z`
- size: `1212`
- prototype: `__int64 __fastcall(int, int, int, int, void *, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180016490`
- `0x18001c458`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180076604`
- `0x1800f0d20`
- `0x1800f21d0`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800164fe`
- `KERNEL32!EnterCriticalSection` at `0x1800164fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800168d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800168d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DacDbiInterfaceImpl::Hijack(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        void *a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned __int64 *a9)
{
  ClrDataAccess *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 *v17; // r15
  __int64 v18; // rax
  unsigned __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rax
  unsigned __int64 *v24; // rax
  __int64 *v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  unsigned __int64 v28; // rsi
  unsigned __int64 v29; // r14
  __int64 TargetAddrForHostAddr; // rax
  unsigned __int64 *v31; // rbx
  __int64 v32; // rdx
  unsigned __int64 v33; // rdi
  __int64 v34; // rax
  unsigned __int64 *v35; // rbx
  unsigned __int64 v36; // rbx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v43; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v44; // [rsp+40h] [rbp-C0h]
  __int64 v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h]
  ClrDataAccess *v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  ClrDataAccess *v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  _BYTE Src[68]; // [rsp+80h] [rbp-80h] BYREF
  int v52; // [rsp+C4h] [rbp-3Ch]
  unsigned __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v55; // [rsp+118h] [rbp+18h]
  __int64 v56; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v57[130]; // [rsp+140h] [rbp+40h] BYREF

  v43 = a3;
  v45 = a8;
  v44 = a9;
  v13 = (ClrDataAccess *)(a1 - 352);
  EnterCriticalSection(&g_dacCritSec);
  v47 = g_dacImpl;
  v49 = g_dacImpl;
  v48 = g_pAllocator;
  v50 = g_pAllocator;
  g_dacImpl = v13;
  g_pAllocator = *((_QWORD *)v13 + 45);
  v17 = 0;
  if ( a2 )
    v17 = DacInstantiateClassByVTable(a2, 1992, 1);
  v18 = DacGlobalBase(v15, v14, v16);
  v19 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v18 + (unsigned int)*g_pDebugger[0], 8u, 1, 1);
  if ( !DacInstantiateClassByVTable(*v19, 224, 1)
    || (v23 = DacGlobalBase(v21, v20, v22),
        v24 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned int)*g_pDebugger[0] + v23, 8u, 1, 1),
        v25 = DacInstantiateClassByVTable(*v24, 224, 1),
        (v46 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v25[21], 0x10u, 1, 1)) == 0) )
  {
    ThrowHR(-2146231280);
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _BYTE *))(**(_QWORD **)(a1 - 312) + 40LL))(
          *(_QWORD *)(a1 - 312),
          a3,
          1048587,
          1232,
          Src);
  if ( v26 < 0 )
    ThrowHR(v26);
  if ( a5 )
  {
    if ( a6 != 1232 )
      ThrowHR(-2147024809);
    memmove(a5, Src, 0x4D0u);
  }
  v52 &= ~0x100u;
  v28 = 0;
  v29 = v55;
  if ( !v17 || !v17[77] )
    goto LABEL_23;
  LOBYTE(v27) = 1;
  TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v17, v27);
  v31 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr + 616, 0x1C0u, 1, 1);
  v33 = DacInstantiateTypeByAddressHelper(*v31, 0x198u, 1, 1)
      ? *((_QWORD *)DacInstantiateTypeByAddressHelper(*v31, 0x198u, 1, 1) + 8)
      : 0LL;
  LOBYTE(v32) = 1;
  v34 = DacGetTargetAddrForHostAddr(v17, v32);
  v35 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v34 + 616, 0x1C0u, 1, 1);
  v36 = DacInstantiateTypeByAddressHelper(*v35, 0x198u, 1, 1)
      ? *((_QWORD *)DacInstantiateTypeByAddressHelper(*v35, 0x198u, 1, 1) + 7)
      : 0LL;
  if ( v33 >= v29 )
    goto LABEL_23;
  v37 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _BYTE *, __int64))(**(_QWORD **)(a1 - 304) + 48LL))(
          *(_QWORD *)(a1 - 304),
          v33,
          Src,
          1232);
  if ( v37 < 0 )
    ThrowHR(v37);
  v38 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, _QWORD))(**(_QWORD **)(a1 - 304) + 48LL))(
          *(_QWORD *)(a1 - 304),
          v36,
          a4,
          (unsigned int)(8 * *(_DWORD *)(a4 + 24) + 32));
  if ( v38 < 0 )
    ThrowHR(v38);
  v28 = v36;
  v29 = v36;
  if ( v33 < v36 )
    v29 = v33;
  v42 = v29;
  if ( !v33 )
  {
LABEL_23:
    v33 = ((v29 & 0xFFFFFFFFFFFFFFF0uLL) - 1217) & 0xFFFFFFFFFFFFFFF0uLL;
    v42 = v33;
    v39 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _BYTE *, __int64))(**(_QWORD **)(a1 - 304) + 48LL))(
            *(_QWORD *)(a1 - 304),
            v33,
            Src,
            1232);
    if ( v39 < 0 )
      ThrowHR(v39);
    if ( a4 )
    {
      v28 = ((((v29 & 0xFFFFFFFFFFFFFFF0uLL) - 1217) & 0xFFFFFFFFFFFFFFF0uLL) - 145) & 0xFFFFFFFFFFFFFFF0uLL;
      v42 = v28;
      v40 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, __int64))(**(_QWORD **)(a1 - 304) + 48LL))(
              *(_QWORD *)(a1 - 304),
              v28,
              a4,
              152);
      if ( v40 < 0 )
        ThrowHR(v40);
    }
  }
  if ( v44 )
    *v44 = v33;
  v53 = v33;
  v54 = v28;
  v56 = a7;
  v57[0] = v45;
  DacDbiInterfaceImpl::PushHelper<unsigned __int64>(a1 - 352, &v42, v57);
  DacDbiInterfaceImpl::PushHelper<unsigned __int64>(a1 - 352, &v42, &v56);
  DacDbiInterfaceImpl::PushHelper<unsigned __int64>(a1 - 352, &v42, &v54);
  DacDbiInterfaceImpl::PushHelper<unsigned __int64>(a1 - 352, &v42, &v53);
  v55 = v42;
  v57[7] = v46;
  v41 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *))(**(_QWORD **)(a1 - 304) + 56LL))(
          *(_QWORD *)(a1 - 304),
          v43,
          1232,
          Src);
  if ( v41 < 0 )
    ThrowHR(v41);
  g_dacImpl = v47;
  g_pAllocator = v48;
  LeaveCriticalSection(&g_dacCritSec);
}

```

## disassembly

```asm
0x180016490  mov     [rsp-8+arg_8], rbx
0x180016495  push    rbp
0x180016496  push    rsi
0x180016497  push    rdi
0x180016498  push    r12
0x18001649a  push    r13
0x18001649c  push    r14
0x18001649e  push    r15
0x1800164a0  lea     rbp, [rsp-460h]
0x1800164a8  sub     rsp, 560h
0x1800164af  mov     rax, cs:__security_cookie
0x1800164b6  xor     rax, rsp
0x1800164b9  mov     [rbp+490h+var_40], rax
0x1800164c0  mov     r12, r9
0x1800164c3  mov     r14d, r8d
0x1800164c6  mov     [rsp+590h+var_558], r8d
0x1800164cb  mov     rbx, rdx
0x1800164ce  mov     r13, rcx
0x1800164d1  mov     rdi, [rbp+490h+arg_20]
0x1800164d8  mov     rax, [rbp+490h+arg_38]
0x1800164df  mov     [rsp+590h+var_548], rax
0x1800164e4  mov     rax, [rbp+490h+arg_40]
0x1800164eb  mov     [rsp+590h+var_550], rax
0x1800164f0  lea     rsi, [rcx-160h]
0x1800164f7  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800164fe  call    cs:__imp_EnterCriticalSection
0x180016504  mov     rax, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18001650b  mov     [rsp+590h+var_538], rax
0x180016510  mov     [rsp+590h+var_528], rax
0x180016515  mov     rax, cs:g_pAllocator
0x18001651c  mov     [rsp+590h+var_530], rax
0x180016521  mov     [rsp+590h+var_520], rax
0x180016526  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rsi; ClrDataAccess * g_dacImpl
0x18001652d  mov     rax, [rsi+168h]
0x180016534  mov     cs:g_pAllocator, rax
0x18001653b  xor     r15d, r15d
0x18001653e  test    rbx, rbx
0x180016541  jz      short loc_180016556
0x180016543  mov     r8b, 1
0x180016546  mov     edx, 7C8h
0x18001654b  mov     rcx, rbx; unsigned __int64
0x18001654e  call    DacInstantiateClassByVTable
0x180016553  mov     r15, rax
0x180016556  call    DacGlobalBase
0x18001655b  mov     rdx, cs:?g_pDebugger@@3V?$__GlobalPtr@PEAVDebugger@@V?$__VPtr@VDebugger@@@@@@A; __GlobalPtr<Debugger *,__VPtr<Debugger>> g_pDebugger
0x180016562  mov     ecx, [rdx]
0x180016564  add     rcx, rax; unsigned __int64
0x180016567  mov     r9b, 1; bool
0x18001656a  mov     r8b, r9b; bool
0x18001656d  mov     ebx, 8
0x180016572  mov     edx, ebx; unsigned int
0x180016574  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180016579  mov     r8b, 1
0x18001657c  mov     esi, 0E0h
0x180016581  mov     edx, esi
0x180016583  mov     rcx, [rax]; unsigned __int64
0x180016586  call    DacInstantiateClassByVTable
0x18001658b  test    rax, rax
0x18001658e  jz      loc_18001690E
0x180016594  call    DacGlobalBase
0x180016599  mov     rcx, rax
0x18001659c  mov     rax, cs:?g_pDebugger@@3V?$__GlobalPtr@PEAVDebugger@@V?$__VPtr@VDebugger@@@@@@A; __GlobalPtr<Debugger *,__VPtr<Debugger>> g_pDebugger
0x1800165a3  mov     r8d, [rax]
0x1800165a6  add     rcx, r8; unsigned __int64
0x1800165a9  mov     r9b, 1; bool
0x1800165ac  mov     r8b, r9b; bool
0x1800165af  mov     edx, ebx; unsigned int
0x1800165b1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800165b6  mov     r8b, 1
0x1800165b9  mov     edx, esi
0x1800165bb  mov     rcx, [rax]; unsigned __int64
0x1800165be  call    DacInstantiateClassByVTable
0x1800165c3  mov     r9b, 1; bool
0x1800165c6  mov     r8b, r9b; bool
0x1800165c9  lea     edx, [rbx+8]; unsigned int
0x1800165cc  mov     rcx, [rax+0A8h]; unsigned __int64
0x1800165d3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800165d8  mov     rax, [rax]
0x1800165db  mov     [rsp+590h+var_540], rax
0x1800165e0  test    rax, rax
0x1800165e3  jz      loc_18001690E
0x1800165e9  mov     rcx, [r13-138h]
0x1800165f0  mov     rax, [rcx]
0x1800165f3  lea     rdx, [rbp+490h+Src]
0x1800165f7  mov     [rsp+590h+var_570], rdx
0x1800165fc  mov     esi, 4D0h
0x180016601  mov     r9d, esi
0x180016604  mov     r8d, 10000Bh
0x18001660a  mov     edx, r14d
0x18001660d  mov     rax, [rax+28h]
0x180016611  call    cs:__guard_dispatch_icall_fptr
0x180016617  test    eax, eax
0x180016619  js      loc_180016919
0x18001661f  test    rdi, rdi
0x180016622  jz      short loc_18001663F
0x180016624  cmp     [rbp+490h+arg_28], esi
0x18001662a  jnz     loc_180016921
0x180016630  mov     r8d, esi; Size
0x180016633  lea     rdx, [rbp+490h+Src]; Src
0x180016637  mov     rcx, rdi; void *
0x18001663a  call    memmove
0x18001663f  btr     [rbp+490h+var_4CC], 8
0x180016644  xor     esi, esi
0x180016646  mov     r14, [rbp+490h+var_478]
0x18001664a  test    r15, r15
0x18001664d  jz      loc_180016787
0x180016653  cmp     [r15+268h], rsi
0x18001665a  jz      loc_180016787
0x180016660  mov     dl, 1
0x180016662  mov     rcx, r15
0x180016665  call    DacGetTargetAddrForHostAddr
0x18001666a  lea     rcx, [rax+268h]; unsigned __int64
0x180016671  mov     r9b, 1; bool
0x180016674  mov     r8b, r9b; bool
0x180016677  mov     edx, 1C0h; unsigned int
0x18001667c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180016681  mov     rbx, rax
0x180016684  mov     r9b, 1; bool
0x180016687  mov     r8b, r9b; bool
0x18001668a  mov     edi, 198h
0x18001668f  mov     edx, edi; unsigned int
0x180016691  mov     rcx, [rax]; unsigned __int64
0x180016694  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180016699  test    rax, rax
0x18001669c  jz      short loc_1800166B4
0x18001669e  mov     r9b, 1; bool
0x1800166a1  mov     r8b, r9b; bool
0x1800166a4  mov     edx, edi; unsigned int
0x1800166a6  mov     rcx, [rbx]; unsigned __int64
0x1800166a9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800166ae  mov     rdi, [rax+40h]
0x1800166b2  jmp     short loc_1800166B6
0x1800166b4  xor     edi, edi
0x1800166b6  mov     dl, 1
0x1800166b8  mov     rcx, r15
0x1800166bb  call    DacGetTargetAddrForHostAddr
0x1800166c0  lea     rcx, [rax+268h]; unsigned __int64
0x1800166c7  mov     r9b, 1; bool
0x1800166ca  mov     r8b, r9b; bool
0x1800166cd  mov     edx, 1C0h; unsigned int
0x1800166d2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800166d7  mov     rbx, rax
0x1800166da  mov     r9b, 1; bool
0x1800166dd  mov     r8b, r9b; bool
0x1800166e0  mov     r15d, 198h
0x1800166e6  mov     edx, r15d; unsigned int
0x1800166e9  mov     rcx, [rax]; unsigned __int64
0x1800166ec  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800166f1  test    rax, rax
0x1800166f4  jz      short loc_18001670D
0x1800166f6  mov     r9b, 1; bool
0x1800166f9  mov     r8b, r9b; bool
0x1800166fc  mov     edx, r15d; unsigned int
0x1800166ff  mov     rcx, [rbx]; unsigned __int64
0x180016702  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180016707  mov     rbx, [rax+38h]
0x18001670b  jmp     short loc_18001670F
0x18001670d  xor     ebx, ebx
0x18001670f  cmp     rdi, r14
0x180016712  jnb     short loc_180016787
0x180016714  mov     rcx, [r13-130h]
0x18001671b  mov     rax, [rcx]
0x18001671e  mov     r9d, 4D0h
0x180016724  lea     r8, [rbp+490h+Src]
0x180016728  mov     rdx, rdi
0x18001672b  mov     rax, [rax+30h]
0x18001672f  call    cs:__guard_dispatch_icall_fptr
0x180016735  test    eax, eax
0x180016737  js      loc_18001692C
0x18001673d  mov     eax, [r12+18h]
0x180016742  lea     r9d, ds:20h[rax*8]
0x18001674a  mov     rcx, [r13-130h]
0x180016751  mov     rax, [rcx]
0x180016754  mov     r8, r12
0x180016757  mov     rdx, rbx
0x18001675a  mov     rax, [rax+30h]
0x18001675e  call    cs:__guard_dispatch_icall_fptr
0x180016764  test    eax, eax
0x180016766  js      loc_180016934
0x18001676c  mov     rsi, rbx
0x18001676f  mov     r14, rbx
0x180016772  cmp     rdi, rbx
0x180016775  cmovb   r14, rdi
0x180016779  mov     [rsp+590h+var_560], r14
0x18001677e  test    rdi, rdi
0x180016781  jnz     loc_18001680B
0x180016787  mov     rdi, r14
0x18001678a  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18001678e  sub     rdi, 4C1h
0x180016795  and     rdi, 0FFFFFFFFFFFFFFF0h
0x180016799  mov     [rsp+590h+var_560], rdi
0x18001679e  mov     rcx, [r13-130h]
0x1800167a5  mov     rax, [rcx]
0x1800167a8  mov     r9d, 4D0h
0x1800167ae  lea     r8, [rbp+490h+Src]
0x1800167b2  mov     rdx, rdi
0x1800167b5  mov     rax, [rax+30h]
0x1800167b9  call    cs:__guard_dispatch_icall_fptr
0x1800167bf  test    eax, eax
0x1800167c1  js      loc_18001693C
0x1800167c7  test    r12, r12
0x1800167ca  jz      short loc_18001680B
0x1800167cc  mov     rsi, rdi
0x1800167cf  and     rsi, 0FFFFFFFFFFFFFFF0h
0x1800167d3  sub     rsi, 91h
0x1800167da  and     rsi, 0FFFFFFFFFFFFFFF0h
0x1800167de  mov     [rsp+590h+var_560], rsi
0x1800167e3  mov     rcx, [r13-130h]
0x1800167ea  mov     rax, [rcx]
0x1800167ed  mov     r9d, 98h
0x1800167f3  mov     r8, r12
0x1800167f6  mov     rdx, rsi
0x1800167f9  mov     rax, [rax+30h]
0x1800167fd  call    cs:__guard_dispatch_icall_fptr
0x180016803  test    eax, eax
0x180016805  js      loc_180016944
0x18001680b  mov     rax, [rsp+590h+var_550]
0x180016810  test    rax, rax
0x180016813  jz      short loc_180016818
0x180016815  mov     [rax], rdi
0x180016818  mov     [rbp+490h+var_490], rdi
0x18001681c  mov     [rbp+490h+var_488], rsi
0x180016820  movsxd  rax, [rbp+490h+arg_30]
0x180016827  mov     [rbp+490h+var_458], rax
0x18001682b  mov     rax, [rsp+590h+var_548]
0x180016830  mov     [rbp+490h+var_450], rax
0x180016834  lea     r8, [rbp+490h+var_450]
0x180016838  lea     rdx, [rsp+590h+var_560]
0x18001683d  lea     rbx, [r13-160h]
0x180016844  mov     rcx, rbx
0x180016847  call    ??$PushHelper@_K@DacDbiInterfaceImpl@@IEAA_KPEA_KPEB_KH@Z; DacDbiInterfaceImpl::PushHelper<unsigned __int64>(unsigned __int64 *,unsigned __int64 const *,int)
0x18001684c  lea     r8, [rbp+490h+var_458]
0x180016850  lea     rdx, [rsp+590h+var_560]
0x180016855  mov     rcx, rbx
0x180016858  call    ??$PushHelper@_K@DacDbiInterfaceImpl@@IEAA_KPEA_KPEB_KH@Z; DacDbiInterfaceImpl::PushHelper<unsigned __int64>(unsigned __int64 *,unsigned __int64 const *,int)
0x18001685d  lea     r8, [rbp+490h+var_488]
0x180016861  lea     rdx, [rsp+590h+var_560]
0x180016866  mov     rcx, rbx
0x180016869  call    ??$PushHelper@_K@DacDbiInterfaceImpl@@IEAA_KPEA_KPEB_KH@Z; DacDbiInterfaceImpl::PushHelper<unsigned __int64>(unsigned __int64 *,unsigned __int64 const *,int)
0x18001686e  lea     r8, [rbp+490h+var_490]
0x180016872  lea     rdx, [rsp+590h+var_560]
0x180016877  mov     rcx, rbx
0x18001687a  call    ??$PushHelper@_K@DacDbiInterfaceImpl@@IEAA_KPEA_KPEB_KH@Z; DacDbiInterfaceImpl::PushHelper<unsigned __int64>(unsigned __int64 *,unsigned __int64 const *,int)
0x18001687f  mov     rax, [rsp+590h+var_560]
0x180016884  mov     [rbp+490h+var_478], rax
0x180016888  mov     rax, [rsp+590h+var_540]
0x18001688d  mov     [rbp+490h+var_418], rax
0x180016891  mov     rcx, [r13-130h]
0x180016898  mov     rax, [rcx]
0x18001689b  lea     r9, [rbp+490h+Src]
0x18001689f  mov     r8d, 4D0h
0x1800168a5  mov     edx, [rsp+590h+var_558]
0x1800168a9  mov     rax, [rax+38h]
0x1800168ad  call    cs:__guard_dispatch_icall_fptr
0x1800168b3  test    eax, eax
0x1800168b5  js      short loc_180016906
0x1800168b7  mov     rax, [rsp+590h+var_538]
0x1800168bc  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x1800168c3  mov     rax, [rsp+590h+var_530]
0x1800168c8  mov     cs:g_pAllocator, rax
0x1800168cf  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800168d6  call    cs:__imp_LeaveCriticalSection
0x1800168dc  mov     rcx, [rbp+490h+var_40]
0x1800168e3  xor     rcx, rsp; StackCookie
0x1800168e6  call    __security_check_cookie
0x1800168eb  mov     rbx, [rsp+590h+arg_8]
0x1800168f3  add     rsp, 560h
0x1800168fa  pop     r15
0x1800168fc  pop     r14
0x1800168fe  pop     r13
0x180016900  pop     r12
0x180016902  pop     rdi
0x180016903  pop     rsi
0x180016904  pop     rbp
0x180016905  retn
0x180016906  mov     ecx, eax; int
0x180016908  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001690e  mov     ecx, 80131C10h; int
0x180016913  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016919  mov     ecx, eax; int
0x18001691b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016921  mov     ecx, 80070057h; int
0x180016926  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001692c  mov     ecx, eax; int
0x18001692e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016934  mov     ecx, eax; int
0x180016936  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001693c  mov     ecx, eax; int
0x18001693e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016944  mov     ecx, eax; int
0x180016946  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
