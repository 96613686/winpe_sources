# ClrDataAccess::GetMethodTableSlot(unsigned __int64,uint,unsigned __int64 *)

- ea: `0x180033750`
- end: `0x180033a21`
- name: `?GetMethodTableSlot@ClrDataAccess@@UEAAJ_KIPEA_K@Z`
- size: `721`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800210f0`
- `0x180022068`
- `0x1800328f0`
- `0x180033750`
- `0x180041044`
- `0x180082d30`
- `0x180083374`
- `0x180089fd4`
- `0x18008a3fc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180033794`
- `KERNEL32!EnterCriticalSection` at `0x180033794`
- `KERNEL32!LeaveCriticalSection` at `0x1800339f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800339f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataAccess::GetMethodTableSlot(
        ClrDataAccess *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  ClrDataAccess *v8; // r14
  int v9; // edi
  struct MethodTable *v10; // rbx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  struct MethodDescChunk *v17; // rax
  __int64 v18; // rdx
  MethodDesc *i; // rbx
  unsigned __int16 v20; // ax
  __int64 TargetAddrForHostAddr; // rsi
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  MethodDesc **v28; // rbx
  BOOL v29; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  MethodDesc **v31; // rcx
  int v32[2]; // [rsp+20h] [rbp-78h] BYREF
  BOOL v33; // [rsp+28h] [rbp-70h]
  ClrDataAccess *v34; // [rsp+30h] [rbp-68h]
  MethodDesc **v35; // [rsp+38h] [rbp-60h] BYREF
  MethodDesc **v36; // [rsp+48h] [rbp-50h]
  MethodDesc *v37; // [rsp+50h] [rbp-48h] BYREF
  __int64 v38; // [rsp+58h] [rbp-40h]
  unsigned __int64 v39; // [rsp+60h] [rbp-38h]
  int v41; // [rsp+A8h] [rbp+10h] BYREF

  if ( !a2 || !a4 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v8 = g_dacImpl;
  v34 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v9 = 0;
  v41 = 0;
  v36 = 0;
  try
  {
    try
    {
      v32[1] = HIDWORD(a2);
      v10 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(a2, 0x40u, 1, 1);
      v32[0] = 0;
      if ( !(unsigned int)DacValidateMethodTable(v10, v32) )
      {
        v9 = -2147024809;
        v41 = -2147024809;
        goto LABEL_49;
      }
      if ( a3 < MethodTable::GetNumVtableSlots(v10) )
      {
        *a4 = MethodTable::GetRestoredSlot(v10, a3);
        goto LABEL_49;
      }
      v9 = -2147024809;
      v41 = -2147024809;
      v11 = *((_QWORD *)v10 + 5);
      if ( (v11 & 2) != 0 )
      {
        if ( (v11 & 1) == 0 )
        {
          *(_QWORD *)v32 = v11 - 2;
          v11 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v11 - 2, 0x40u, 1, 1) + 5);
          *(_QWORD *)v32 = v11;
LABEL_13:
          v12 = DacInstantiateTypeByAddressHelper(v11, 0x48u, 1, 1);
          LOBYTE(v13) = 1;
          v14 = DacGetTargetAddrForHostAddr(v12, v13) + 32;
          v15 = v12[4];
          if ( v15 )
          {
            v16 = v14 + v15;
            *(_QWORD *)v32 = v16;
          }
          else
          {
            v16 = 0;
            *(_QWORD *)v32 = 0;
          }
LABEL_16:
          v17 = (struct MethodDescChunk *)DacInstantiateTypeByAddressHelper(v16, 0x18u, 1, 1);
          MethodTable::IntroducedMethodIterator::SetChunk((MethodTable::IntroducedMethodIterator *)&v37, v17);
          for ( i = v37; i && v9 < 0; v37 = i )
          {
            v20 = *((_WORD *)i + 2);
            if ( *((__int16 *)i + 3) >= 0 )
              v20 &= 0x3FFu;
            if ( v20 == a3 )
            {
              *a4 = MethodDesc::GetMethodEntryPoint(i);
              v9 = 0;
              v41 = 0;
            }
            LOBYTE(v18) = 1;
            TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(i, v18);
            v22 = TargetAddrForHostAddr + MethodDesc::SizeOf(i);
            if ( v22 >= v39 )
            {
              LOBYTE(v23) = 1;
              v24 = v38;
              v25 = DacGetTargetAddrForHostAddr(v38, v23) + 8;
              v26 = *(_QWORD *)(v24 + 8);
              if ( v26 )
              {
                v16 = v25 + v26;
                *(_QWORD *)v32 = v16;
              }
              else
              {
                v16 = 0;
                *(_QWORD *)v32 = 0;
              }
              goto LABEL_16;
            }
            *(_QWORD *)v32 = v22;
            i = (MethodDesc *)DacInstantiateTypeByAddressHelper(v22, 8u, 1, 1);
          }
          goto LABEL_49;
        }
        *(_QWORD *)v32 = v11 - 3;
        *(_QWORD *)v32 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v11 - 3, 8u, 1, 1);
        v11 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*(unsigned __int64 *)v32, 0x40u, 1, 1) + 5);
      }
      *(_QWORD *)v32 = v11;
      goto LABEL_13;
    }
    catch ( Exception *v35 )
    {
      v36 = v35;
      throw;
    }
  }
  catch ( ... )
  {
    v38 = 0;
    v37 = (MethodDesc *)&DelegatingException::`vftable';
    v39 = -1;
    v28 = v36;
    *(_QWORD *)v32 = v36;
    v29 = v36 != 0;
    v33 = v29;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v31 = &v37;
    if ( v28 )
      v31 = v28;
    if ( !DacExceptionFilter((struct Exception *)v31, (ClrDataAccess *)((char *)this - 16), &v41) )
    {
      v33 = 0;
      throw;
    }
    if ( v29 )
    {
      if ( v28 )
      {
        if ( !(*((unsigned int (__fastcall **)(MethodDesc **))*v28 + 10))(v28) )
          (*(void (__fastcall **)(MethodDesc **, __int64))*v28)(v28, 5);
      }
      v33 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v37);
    v8 = v34;
    v9 = v41;
  }
LABEL_49:
  g_dacImpl = v8;
  LeaveCriticalSection(&g_dacCritSec);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180033750  mov     [rsp+arg_10], rbx
0x180033755  mov     [rsp+arg_18], rsi
0x18003375a  mov     [rsp+arg_0], rcx
0x18003375f  push    rdi
0x180033760  push    r12
0x180033762  push    r13
0x180033764  push    r14
0x180033766  push    r15
0x180033768  sub     rsp, 70h
0x18003376c  mov     r15, r9
0x18003376f  mov     r12d, r8d
0x180033772  mov     rsi, rdx
0x180033775  mov     rbx, rcx
0x180033778  xor     r13d, r13d
0x18003377b  test    rdx, rdx
0x18003377e  jz      loc_180033A02
0x180033784  test    r9, r9
0x180033787  jz      loc_180033A02
0x18003378d  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033794  call    cs:__imp_EnterCriticalSection
0x18003379a  mov     r14, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800337a1  mov     [rsp+98h+var_68], r14
0x1800337a6  lea     rax, [rbx-10h]
0x1800337aa  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x1800337b1  mov     edi, r13d
0x1800337b4  mov     [rsp+98h+arg_8], r13d
0x1800337bc  mov     [rsp+98h+var_50], r13
0x1800337c1  lea     rax, [rsp+98h+var_58]
0x1800337c6  mov     qword ptr [rsp+98h+var_78], rax
0x1800337cb  mov     qword ptr [rsp+98h+var_78], rsi
0x1800337d0  mov     r9b, 1; bool
0x1800337d3  mov     r8b, r9b; bool
0x1800337d6  lea     edx, [r13+40h]; unsigned int
0x1800337da  mov     rcx, rsi; unsigned __int64
0x1800337dd  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800337e2  mov     rbx, rax
0x1800337e5  mov     [rsp+98h+var_78], r13d
0x1800337ea  lea     rdx, [rsp+98h+var_78]; int *
0x1800337ef  mov     rcx, rax; struct MethodTable *
0x1800337f2  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x1800337f7  test    eax, eax
0x1800337f9  jnz     short loc_18003380C
0x1800337fb  mov     edi, 80070057h
0x180033800  mov     [rsp+98h+arg_8], edi
0x180033807  jmp     loc_1800339EA
0x18003380c  mov     rcx, rbx; this
0x18003380f  call    ?GetNumVtableSlots@MethodTable@@QEAAGXZ; MethodTable::GetNumVtableSlots(void)
0x180033814  movzx   eax, ax
0x180033817  cmp     r12d, eax
0x18003381a  jnb     short loc_18003382C
0x18003381c  mov     edx, r12d; unsigned int
0x18003381f  mov     rcx, rbx; this
0x180033822  call    ?GetRestoredSlot@MethodTable@@QEAA_KK@Z; MethodTable::GetRestoredSlot(ulong)
0x180033827  mov     [r15], rax
0x18003382a  jmp     short loc_180033807
0x18003382c  mov     edi, 80070057h
0x180033831  mov     [rsp+98h+arg_8], edi
0x180033838  mov     rcx, [rbx+28h]
0x18003383c  test    cl, 2
0x18003383f  jnz     short loc_180033848
0x180033841  mov     qword ptr [rsp+98h+var_78], rcx
0x180033846  jmp     short loc_1800338A6
0x180033848  test    cl, 1
0x18003384b  jz      short loc_180033884
0x18003384d  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180033851  mov     qword ptr [rsp+98h+var_78], rcx
0x180033856  mov     r9b, 1; bool
0x180033859  mov     r8b, r9b; bool
0x18003385c  mov     edx, 8; unsigned int
0x180033861  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180033866  mov     rcx, [rax]; unsigned __int64
0x180033869  mov     qword ptr [rsp+98h+var_78], rcx
0x18003386e  mov     r9b, 1; bool
0x180033871  mov     r8b, r9b; bool
0x180033874  mov     edx, 40h ; '@'; unsigned int
0x180033879  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003387e  mov     rcx, [rax+28h]
0x180033882  jmp     short loc_180033841
0x180033884  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180033888  mov     qword ptr [rsp+98h+var_78], rcx
0x18003388d  mov     r9b, 1; bool
0x180033890  mov     r8b, r9b; bool
0x180033893  mov     edx, 40h ; '@'; unsigned int
0x180033898  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003389d  mov     rcx, [rax+28h]; unsigned __int64
0x1800338a1  mov     qword ptr [rsp+98h+var_78], rcx
0x1800338a6  mov     r9b, 1; bool
0x1800338a9  mov     r8b, r9b; bool
0x1800338ac  mov     edx, 48h ; 'H'; unsigned int
0x1800338b1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800338b6  mov     rbx, rax
0x1800338b9  mov     dl, 1
0x1800338bb  mov     rcx, rax
0x1800338be  call    DacGetTargetAddrForHostAddr
0x1800338c3  add     rax, 20h ; ' '
0x1800338c7  mov     rcx, [rbx+20h]
0x1800338cb  test    rcx, rcx
0x1800338ce  jnz     short loc_1800338DA
0x1800338d0  mov     rcx, r13
0x1800338d3  mov     qword ptr [rsp+98h+var_78], rcx
0x1800338d8  jmp     short loc_1800338E2
0x1800338da  add     rcx, rax; unsigned __int64
0x1800338dd  mov     qword ptr [rsp+98h+var_78], rcx
0x1800338e2  mov     r9b, 1; bool
0x1800338e5  mov     r8b, r9b; bool
0x1800338e8  mov     edx, 18h; unsigned int
0x1800338ed  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800338f2  mov     rdx, rax; struct MethodDescChunk *
0x1800338f5  lea     rcx, [rsp+98h+var_48]; this
0x1800338fa  call    ?SetChunk@IntroducedMethodIterator@MethodTable@@IEAAXPEAVMethodDescChunk@@@Z; MethodTable::IntroducedMethodIterator::SetChunk(MethodDescChunk *)
0x1800338ff  mov     rbx, [rsp+98h+var_48]
0x180033904  test    rbx, rbx
0x180033907  jz      loc_180033807
0x18003390d  test    edi, edi
0x18003390f  jns     loc_180033807
0x180033915  movzx   eax, word ptr [rbx+4]
0x180033919  cmp     [rbx+6], r13w
0x18003391e  jl      short loc_18003392A
0x180033920  mov     ecx, 3FFh
0x180033925  and     ax, cx
0x180033928  jmp     short $+2
0x18003392a  movzx   eax, ax
0x18003392d  cmp     eax, r12d
0x180033930  jnz     short loc_180033948
0x180033932  mov     rcx, rbx; this
0x180033935  call    ?GetMethodEntryPoint@MethodDesc@@QEAA_KXZ; MethodDesc::GetMethodEntryPoint(void)
0x18003393a  mov     [r15], rax
0x18003393d  mov     edi, r13d
0x180033940  mov     [rsp+98h+arg_8], r13d
0x180033948  mov     dl, 1
0x18003394a  mov     rcx, rbx
0x18003394d  call    DacGetTargetAddrForHostAddr
0x180033952  mov     rsi, rax
0x180033955  mov     rcx, rbx; this
0x180033958  call    ?SizeOf@MethodDesc@@QEAA_KXZ; MethodDesc::SizeOf(void)
0x18003395d  add     rax, rsi
0x180033960  cmp     rax, [rsp+98h+var_38]
0x180033965  jnb     short loc_180033989
0x180033967  mov     qword ptr [rsp+98h+var_78], rax
0x18003396c  mov     r9b, 1; bool
0x18003396f  mov     r8b, r9b; bool
0x180033972  mov     edx, 8; unsigned int
0x180033977  mov     rcx, rax; unsigned __int64
0x18003397a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003397f  mov     rbx, rax
0x180033982  mov     [rsp+98h+var_48], rax
0x180033987  jmp     short loc_1800339D9
0x180033989  mov     dl, 1
0x18003398b  mov     rbx, [rsp+98h+var_40]
0x180033990  mov     rcx, rbx
0x180033993  call    DacGetTargetAddrForHostAddr
0x180033998  add     rax, 8
0x18003399c  mov     rcx, [rbx+8]
0x1800339a0  test    rcx, rcx
0x1800339a3  jnz     short loc_1800339AF
0x1800339a5  mov     rcx, r13
0x1800339a8  mov     qword ptr [rsp+98h+var_78], rcx
0x1800339ad  jmp     short loc_1800339B7
0x1800339af  add     rcx, rax; unsigned __int64
0x1800339b2  mov     qword ptr [rsp+98h+var_78], rcx
0x1800339b7  mov     r9b, 1; bool
0x1800339ba  mov     r8b, r9b; bool
0x1800339bd  mov     edx, 18h; unsigned int
0x1800339c2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800339c7  mov     rdx, rax; struct MethodDescChunk *
0x1800339ca  lea     rcx, [rsp+98h+var_48]; this
0x1800339cf  call    ?SetChunk@IntroducedMethodIterator@MethodTable@@IEAAXPEAVMethodDescChunk@@@Z; MethodTable::IntroducedMethodIterator::SetChunk(MethodDescChunk *)
0x1800339d4  mov     rbx, [rsp+98h+var_48]
0x1800339d9  jmp     loc_180033904
0x1800339de  mov     r14, [rsp+98h+var_68]
0x1800339e3  mov     edi, [rsp+98h+arg_8]
0x1800339ea  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r14; ClrDataAccess * g_dacImpl
0x1800339f1  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800339f8  call    cs:__imp_LeaveCriticalSection
0x1800339fe  mov     eax, edi
0x180033a00  jmp     short loc_180033A07
0x180033a02  mov     eax, 80070057h
0x180033a07  lea     r11, [rsp+98h+var_28]
0x180033a0c  mov     rbx, [r11+40h]
0x180033a10  mov     rsi, [r11+48h]
0x180033a14  mov     rsp, r11
0x180033a17  pop     r15
0x180033a19  pop     r14
0x180033a1b  pop     r13
0x180033a1d  pop     r12
0x180033a1f  pop     rdi
0x180033a20  retn
```
