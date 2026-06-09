# ClrDataAccess::GetMethodTableFieldData(unsigned __int64,DacpMethodTableFieldData *)

- ea: `0x1800375c0`
- end: `0x1800378da`
- name: `?GetMethodTableFieldData@ClrDataAccess@@UEAAJ_KPEAUDacpMethodTableFieldData@@@Z`
- size: `794`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, struct DacpMethodTableFieldData *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18001dcec`
- `0x18001dda4`
- `0x1800210f0`
- `0x180022068`
- `0x1800328f0`
- `0x1800375c0`
- `0x180040c60`
- `0x18007d5c8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800375f8`
- `KERNEL32!EnterCriticalSection` at `0x1800375f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800378bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800378bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataAccess::GetMethodTableFieldData(
        ClrDataAccess *this,
        unsigned __int64 a2,
        struct DacpMethodTableFieldData *a3)
{
  unsigned int v6; // ebx
  ClrDataAccess *v7; // r12
  struct MethodTable *v8; // rax
  MethodTable *v9; // r14
  unsigned __int64 v10; // rcx
  void *v11; // rax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rax
  int v18; // edi
  unsigned __int64 *ContextStaticsBucketPtr; // rax
  __int16 v20; // cx
  unsigned __int64 *v21; // rax
  __int16 v22; // ax
  struct Exception *v24; // rbx
  BOOL v25; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v27; // rcx
  ClrDataAccess *v28; // [rsp+28h] [rbp-80h]
  _QWORD v29[2]; // [rsp+40h] [rbp-68h] BYREF
  struct Exception *v30; // [rsp+50h] [rbp-58h]
  _QWORD v31[10]; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v33; // [rsp+B8h] [rbp+10h] BYREF
  unsigned __int64 v34; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v7 = g_dacImpl;
  v28 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v33 = 0;
  v30 = 0;
  try
  {
    try
    {
      v34 = a2;
      v8 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(a2, 0x40u, 1, 1);
      v9 = v8;
      LODWORD(v34) = 0;
      if ( !v8 || !(unsigned int)DacValidateMethodTable(v8, (int *)&v34) )
      {
        v6 = -2147024809;
        v33 = -2147024809;
        goto LABEL_51;
      }
      *(_WORD *)a3 = MethodTable::GetNumInstanceFields(v9);
      *((_WORD *)a3 + 1) = MethodTable::GetNumStaticFields(v9);
      v10 = *((_QWORD *)v9 + 5);
      if ( (v10 & 2) != 0 )
      {
        if ( (v10 & 1) != 0 )
        {
          v34 = v10 - 3;
          v34 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v10 - 3, 8u, 1, 1);
          v10 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v34, 0x40u, 1, 1) + 5);
        }
        else
        {
          v34 = v10 - 2;
          v10 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v10 - 2, 0x40u, 1, 1) + 5);
        }
        v34 = v10;
      }
      else
      {
        v34 = *((_QWORD *)v9 + 5);
      }
      v11 = DacInstantiateTypeByAddressHelper(v10, 0x48u, 1, 1);
      *((_WORD *)a3 + 2) = EEClass::GetPackableField(v11, 6);
      v12 = *((_QWORD *)v9 + 5);
      if ( (v12 & 2) != 0 )
      {
        if ( (v12 & 1) == 0 )
        {
          v34 = v12 - 2;
          v12 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v12 - 2, 0x40u, 1, 1) + 5);
          v34 = v12;
          goto LABEL_17;
        }
        v34 = v12 - 3;
        v34 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v12 - 3, 8u, 1, 1);
        v12 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v34, 0x40u, 1, 1) + 5);
      }
      v34 = v12;
LABEL_17:
      v13 = DacInstantiateTypeByAddressHelper(v12, 0x48u, 1, 1);
      LOBYTE(v14) = 1;
      v15 = DacGetTargetAddrForHostAddr(v13, v14) + 24;
      v16 = v13[3];
      if ( v16 )
      {
        v17 = v16 + v15;
        v34 = v17;
      }
      else
      {
        v17 = 0;
        v34 = 0;
      }
      *((_QWORD *)a3 + 1) = v17;
      if ( *(int *)v9 >= 0 )
        v18 = *(_DWORD *)v9 & 0x40;
      else
        v18 = 0;
      if ( v18 )
      {
        ContextStaticsBucketPtr = (unsigned __int64 *)MethodTable::GetContextStaticsBucketPtr(v9);
        v34 = *(_QWORD *)DacInstantiateTypeByAddressHelper(*ContextStaticsBucketPtr, 8u, 1, 1);
        v20 = *((_WORD *)DacInstantiateTypeByAddressHelper(v34, 8u, 1, 1) + 2);
      }
      else
      {
        v20 = 0;
      }
      *((_WORD *)a3 + 9) = v20;
      if ( v18 )
      {
        v21 = (unsigned __int64 *)MethodTable::GetContextStaticsBucketPtr(v9);
        v34 = *(_QWORD *)DacInstantiateTypeByAddressHelper(*v21, 8u, 1, 1);
        v22 = *(_DWORD *)DacInstantiateTypeByAddressHelper(v34, 8u, 1, 1);
      }
      else
      {
        v22 = 0;
      }
      *((_WORD *)a3 + 8) = v22;
    }
    catch ( Exception *v29 )
    {
      v30 = (struct Exception *)v29[0];
      throw;
    }
  }
  catch ( ... )
  {
    v31[1] = 0;
    v31[0] = &DelegatingException::`vftable';
    v31[2] = -1;
    v24 = v30;
    v29[1] = v30;
    v25 = v30 != 0;
    LODWORD(v30) = v25;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v27 = (struct Exception *)v31;
    if ( v24 )
      v27 = v24;
    if ( !DacExceptionFilter(v27, (ClrDataAccess *)((char *)this - 16), (int *)&v33) )
    {
      LODWORD(v30) = 0;
      throw;
    }
    if ( v25 )
    {
      if ( v24 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v24 + 80LL))(v24) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v24)(v24, 5);
      }
      LODWORD(v30) = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v31);
    v7 = v28;
    v6 = v33;
  }
LABEL_51:
  g_dacImpl = v7;
  LeaveCriticalSection(&g_dacCritSec);
  return v6;
}

```

## disassembly

```asm
0x1800375c0  mov     [rsp+arg_0], rcx
0x1800375c5  push    rbx
0x1800375c6  push    rsi
0x1800375c7  push    rdi
0x1800375c8  push    r12
0x1800375ca  push    r13
0x1800375cc  push    r14
0x1800375ce  push    r15
0x1800375d0  sub     rsp, 70h
0x1800375d4  mov     r15, r8
0x1800375d7  mov     rdi, rdx
0x1800375da  mov     rsi, rcx
0x1800375dd  xor     ebx, ebx
0x1800375df  test    rdx, rdx
0x1800375e2  jz      loc_1800378C5
0x1800375e8  test    r8, r8
0x1800375eb  jz      loc_1800378C5
0x1800375f1  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800375f8  call    cs:__imp_EnterCriticalSection
0x1800375fe  mov     r12, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180037605  mov     [rsp+0A8h+var_80], r12
0x18003760a  lea     rax, [rsi-10h]
0x18003760e  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180037615  mov     [rsp+0A8h+arg_8], ebx
0x18003761c  mov     [rsp+0A8h+var_58], rbx
0x180037621  lea     rax, [rsp+0A8h+var_60]
0x180037626  mov     [rsp+0A8h+arg_18], rax
0x18003762e  mov     [rsp+0A8h+arg_18], rdi
0x180037636  mov     r9b, 1; bool
0x180037639  mov     r8b, r9b; bool
0x18003763c  lea     r13d, [rbx+40h]
0x180037640  mov     edx, r13d; unsigned int
0x180037643  mov     rcx, rdi; unsigned __int64
0x180037646  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003764b  mov     r14, rax
0x18003764e  mov     dword ptr [rsp+0A8h+arg_18], ebx
0x180037655  test    rax, rax
0x180037658  jz      loc_180037893
0x18003765e  lea     rdx, [rsp+0A8h+arg_18]; int *
0x180037666  mov     rcx, rax; struct MethodTable *
0x180037669  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x18003766e  test    eax, eax
0x180037670  jz      loc_180037893
0x180037676  mov     rcx, r14; this
0x180037679  call    ?GetNumInstanceFields@MethodTable@@QEAAGXZ; MethodTable::GetNumInstanceFields(void)
0x18003767e  mov     [r15], ax
0x180037682  mov     rcx, r14; this
0x180037685  call    ?GetNumStaticFields@MethodTable@@QEAAGXZ; MethodTable::GetNumStaticFields(void)
0x18003768a  mov     [r15+2], ax
0x18003768f  mov     rcx, [r14+28h]
0x180037693  test    cl, 2
0x180037696  jnz     short loc_1800376A2
0x180037698  mov     [rsp+0A8h+arg_18], rcx
0x1800376a0  jmp     short loc_180037712
0x1800376a2  test    cl, 1
0x1800376a5  jz      short loc_1800376EC
0x1800376a7  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x1800376ab  mov     [rsp+0A8h+arg_18], rcx
0x1800376b3  mov     r9b, 1; bool
0x1800376b6  mov     r8b, r9b; bool
0x1800376b9  mov     esi, 8
0x1800376be  mov     edx, esi; unsigned int
0x1800376c0  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800376c5  mov     rcx, [rax]; unsigned __int64
0x1800376c8  mov     [rsp+0A8h+arg_18], rcx
0x1800376d0  mov     r9b, 1; bool
0x1800376d3  mov     r8b, r9b; bool
0x1800376d6  mov     edx, r13d; unsigned int
0x1800376d9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800376de  mov     rcx, [rax+28h]
0x1800376e2  mov     [rsp+0A8h+arg_18], rcx
0x1800376ea  jmp     short loc_180037717
0x1800376ec  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x1800376f0  mov     [rsp+0A8h+arg_18], rcx
0x1800376f8  mov     r9b, 1; bool
0x1800376fb  mov     r8b, r9b; bool
0x1800376fe  mov     edx, r13d; unsigned int
0x180037701  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037706  mov     rcx, [rax+28h]; unsigned __int64
0x18003770a  mov     [rsp+0A8h+arg_18], rcx
0x180037712  mov     esi, 8
0x180037717  mov     r9b, 1; bool
0x18003771a  mov     r8b, r9b; bool
0x18003771d  mov     edi, 48h ; 'H'
0x180037722  mov     edx, edi; unsigned int
0x180037724  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037729  lea     edx, [rdi-42h]
0x18003772c  mov     rcx, rax
0x18003772f  call    ?GetPackableField@EEClass@@AEAAKW4EEClassFieldId@@@Z; EEClass::GetPackableField(EEClassFieldId)
0x180037734  mov     [r15+4], ax
0x180037739  mov     rcx, [r14+28h]
0x18003773d  test    cl, 2
0x180037740  jnz     short loc_18003774C
0x180037742  mov     [rsp+0A8h+arg_18], rcx
0x18003774a  jmp     short loc_1800377AF
0x18003774c  test    cl, 1
0x18003774f  jz      short loc_180037789
0x180037751  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180037755  mov     [rsp+0A8h+arg_18], rcx
0x18003775d  mov     r9b, 1; bool
0x180037760  mov     r8b, r9b; bool
0x180037763  mov     edx, esi; unsigned int
0x180037765  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003776a  mov     rcx, [rax]; unsigned __int64
0x18003776d  mov     [rsp+0A8h+arg_18], rcx
0x180037775  mov     r9b, 1; bool
0x180037778  mov     r8b, r9b; bool
0x18003777b  mov     edx, r13d; unsigned int
0x18003777e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037783  mov     rcx, [rax+28h]
0x180037787  jmp     short loc_180037742
0x180037789  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x18003778d  mov     [rsp+0A8h+arg_18], rcx
0x180037795  mov     r9b, 1; bool
0x180037798  mov     r8b, r9b; bool
0x18003779b  mov     edx, r13d; unsigned int
0x18003779e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800377a3  mov     rcx, [rax+28h]; unsigned __int64
0x1800377a7  mov     [rsp+0A8h+arg_18], rcx
0x1800377af  mov     r9b, 1; bool
0x1800377b2  mov     r8b, r9b; bool
0x1800377b5  mov     edx, edi; unsigned int
0x1800377b7  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800377bc  mov     rdi, rax
0x1800377bf  mov     dl, 1
0x1800377c1  mov     rcx, rax
0x1800377c4  call    DacGetTargetAddrForHostAddr
0x1800377c9  add     rax, 18h
0x1800377cd  mov     rcx, [rdi+18h]
0x1800377d1  test    rcx, rcx
0x1800377d4  jnz     short loc_1800377E3
0x1800377d6  mov     rax, rbx
0x1800377d9  mov     [rsp+0A8h+arg_18], rbx
0x1800377e1  jmp     short loc_1800377EE
0x1800377e3  add     rax, rcx
0x1800377e6  mov     [rsp+0A8h+arg_18], rax
0x1800377ee  mov     [r15+8], rax
0x1800377f2  mov     edi, [r14]
0x1800377f5  test    edi, edi
0x1800377f7  jns     short loc_1800377FD
0x1800377f9  mov     edi, ebx
0x1800377fb  jmp     short loc_180037800
0x1800377fd  and     edi, r13d
0x180037800  test    edi, edi
0x180037802  jz      short loc_18003783F
0x180037804  lea     rdx, [rsp+0A8h+var_78]
0x180037809  mov     rcx, r14; this
0x18003780c  call    ?GetContextStaticsBucketPtr@MethodTable@@QEAA?AV?$__DPtr@V?$__DPtr@UContextStaticsBucket@@@@@@XZ; MethodTable::GetContextStaticsBucketPtr(void)
0x180037811  mov     r9b, 1; bool
0x180037814  mov     r8b, r9b; bool
0x180037817  mov     edx, esi; unsigned int
0x180037819  mov     rcx, [rax]; unsigned __int64
0x18003781c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037821  mov     rcx, [rax]; unsigned __int64
0x180037824  mov     [rsp+0A8h+arg_18], rcx
0x18003782c  mov     r9b, 1; bool
0x18003782f  mov     r8b, r9b; bool
0x180037832  mov     edx, esi; unsigned int
0x180037834  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037839  movzx   ecx, word ptr [rax+4]
0x18003783d  jmp     short loc_180037841
0x18003783f  mov     ecx, ebx
0x180037841  mov     [r15+12h], cx
0x180037846  test    edi, edi
0x180037848  jz      short loc_18003788A
0x18003784a  lea     rdx, [rsp+0A8h+var_70]
0x18003784f  mov     rcx, r14; this
0x180037852  call    ?GetContextStaticsBucketPtr@MethodTable@@QEAA?AV?$__DPtr@V?$__DPtr@UContextStaticsBucket@@@@@@XZ; MethodTable::GetContextStaticsBucketPtr(void)
0x180037857  mov     r9b, 1; bool
0x18003785a  mov     r8b, r9b; bool
0x18003785d  mov     edx, esi; unsigned int
0x18003785f  mov     rcx, [rax]; unsigned __int64
0x180037862  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037867  mov     rcx, [rax]; unsigned __int64
0x18003786a  mov     [rsp+0A8h+arg_18], rcx
0x180037872  mov     r9b, 1; bool
0x180037875  mov     r8b, r9b; bool
0x180037878  mov     edx, esi; unsigned int
0x18003787a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003787f  mov     ecx, [rax]
0x180037881  mov     [rsp+0A8h+var_88], ecx
0x180037885  movzx   eax, cx
0x180037888  jmp     short loc_18003788C
0x18003788a  mov     eax, ebx
0x18003788c  mov     [r15+10h], ax
0x180037891  jmp     short loc_18003789F
0x180037893  mov     ebx, 80070057h
0x180037898  mov     [rsp+0A8h+arg_8], ebx
0x18003789f  jmp     short loc_1800378AD
0x1800378a1  mov     r12, [rsp+0A8h+var_80]
0x1800378a6  mov     ebx, [rsp+0A8h+arg_8]
0x1800378ad  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r12; ClrDataAccess * g_dacImpl
0x1800378b4  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800378bb  call    cs:__imp_LeaveCriticalSection
0x1800378c1  mov     eax, ebx
0x1800378c3  jmp     short loc_1800378CA
0x1800378c5  mov     eax, 80070057h
0x1800378ca  add     rsp, 70h
0x1800378ce  pop     r15
0x1800378d0  pop     r14
0x1800378d2  pop     r13
0x1800378d4  pop     r12
0x1800378d6  pop     rdi
0x1800378d7  pop     rsi
0x1800378d8  pop     rbx
0x1800378d9  retn
```
