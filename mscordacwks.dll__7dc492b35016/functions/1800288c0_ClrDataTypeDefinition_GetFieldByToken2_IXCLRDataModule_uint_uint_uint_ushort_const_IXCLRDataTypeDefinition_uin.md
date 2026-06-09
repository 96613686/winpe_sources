# ClrDataTypeDefinition::GetFieldByToken2(IXCLRDataModule *,uint,uint,uint *,ushort * const,IXCLRDataTypeDefinition * *,uint *)

- ea: `0x1800288c0`
- end: `0x180028c15`
- name: `?GetFieldByToken2@ClrDataTypeDefinition@@UEAAJPEAUIXCLRDataModule@@IIPEAIQEAGPEAPEAUIXCLRDataTypeDefinition@@1@Z`
- size: `853`
- prototype: `__int64 __fastcall(ClrDataTypeDefinition *__hidden this, struct IXCLRDataModule *, unsigned int, unsigned int, unsigned int *, unsigned __int16 *const, struct IXCLRDataTypeDefinition **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1800011dc`
- `0x18000c968`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180024d4c`
- `0x180024e98`
- `0x1800279ac`
- `0x1800288c0`
- `0x18002b160`
- `0x18007262c`
- `0x18007d378`
- `0x18007d834`
- `0x180081de0`
- `0x180082c58`
- `0x180083a38`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800288f5`
- `KERNEL32!EnterCriticalSection` at `0x1800288f5`
- `KERNEL32!LeaveCriticalSection` at `0x180028913`
- `KERNEL32!LeaveCriticalSection` at `0x180028bfa`
- `KERNEL32!LeaveCriticalSection` at `0x180028913`
- `KERNEL32!LeaveCriticalSection` at `0x180028bfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataTypeDefinition::GetFieldByToken2(
        ClrDataTypeDefinition *this,
        struct IXCLRDataModule *a2,
        int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned __int16 *const a6,
        struct IXCLRDataTypeDefinition **a7,
        unsigned int *a8)
{
  int v8; // r15d
  struct IXCLRDataModule *v9; // rbx
  __int64 v11; // r8
  ClrDataAccess *v12; // r10
  ClrDataAccess *v14; // r12
  struct IXCLRDataTypeDefinition *v15; // rdi
  signed int inited; // esi
  struct FieldDesc *v17; // rax
  __int64 v18; // rdx
  FieldDesc *v19; // r14
  void *v20; // rax
  unsigned __int64 *Module; // rax
  __int64 *v22; // r15
  __int64 v23; // rdx
  __int64 TargetAddrForHostAddr; // rbx
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  const CHAR *Name; // rax
  const struct NoThrow *v30; // rdx
  void *v31; // rsi
  unsigned __int64 v32; // rcx
  void *v33; // rax
  MethodTable *v34; // rax
  unsigned int v35; // ebx
  unsigned __int64 *v36; // rax
  __int64 *v37; // rax
  struct Exception *v38; // rbx
  BOOL v39; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v41; // rcx
  int v42; // [rsp+30h] [rbp-158h] BYREF
  __int64 v43; // [rsp+38h] [rbp-150h] BYREF
  unsigned __int64 v44; // [rsp+40h] [rbp-148h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-140h] BYREF
  BOOL v46; // [rsp+50h] [rbp-138h]
  ClrDataAccess *v47; // [rsp+58h] [rbp-130h]
  unsigned __int64 v48; // [rsp+68h] [rbp-120h]
  _QWORD v49[3]; // [rsp+70h] [rbp-118h] BYREF
  char v50[8]; // [rsp+88h] [rbp-100h] BYREF
  unsigned __int64 v51; // [rsp+90h] [rbp-F8h] BYREF
  int v52; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-E0h]
  int v54; // [rsp+B0h] [rbp-D8h]
  int v55; // [rsp+B4h] [rbp-D4h]
  int v56; // [rsp+B8h] [rbp-D0h]
  int v57; // [rsp+BCh] [rbp-CCh]
  int v58; // [rsp+140h] [rbp-48h]
  char v59; // [rsp+144h] [rbp-44h]

  v8 = a3;
  v9 = a2;
  EnterCriticalSection(&g_dacCritSec);
  v12 = (ClrDataAccess *)*((_QWORD *)this + 2);
  if ( *((_DWORD *)v12 + 46) == *((_DWORD *)this + 6) )
  {
    v14 = g_dacImpl;
    v47 = g_dacImpl;
    g_dacImpl = v12;
    v15 = 0;
    v48 = 0;
    try
    {
      try
      {
        v52 = 0;
        v43 = 0;
        v53 = 0;
        v54 = -1;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        if ( *((_QWORD *)this + 6) )
        {
          LOBYTE(v11) = 1;
          inited = InitFieldIter(&v52, *((_QWORD *)this + 6), v11, 3839, 0);
          v42 = inited;
          if ( !inited )
          {
            inited = -2147024809;
            v42 = -2147024809;
            while ( 1 )
            {
              v17 = DeepFieldDescIterator::Next((DeepFieldDescIterator *)&v52);
              v19 = v17;
              if ( !v17 )
                break;
              if ( !v9 )
                goto LABEL_15;
              LOBYTE(v18) = 1;
              v43 = DacGetTargetAddrForHostAddr(v17, v18) + *(_QWORD *)v17;
              v20 = DacInstantiateTypeByAddressHelper(v43, 0x40u, 1, 1);
              Module = (unsigned __int64 *)MethodTable::GetModule(v20, &v45);
              v22 = DacInstantiateClassByVTable(*Module, 1576, 1);
              LOBYTE(v23) = 1;
              TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(*((_QWORD *)v9 + 5), v23);
              LOBYTE(v25) = 1;
              v26 = DacGetTargetAddrForHostAddr(v22, v25);
              v8 = a3;
              if ( TargetAddrForHostAddr == v26 )
              {
LABEL_15:
                v27 = *((_DWORD *)v19 + 2);
                v28 = v27 < 0 ? v27 & 0xFFFFFF : v27 & 0x1FFFF;
                if ( (v28 | 0x4000000) == v8 )
                {
                  if ( a8 )
                    *a8 = GetTypeFieldValueFlags(*((_QWORD *)this + 6), v19, v59 != 0 ? 0x80 : 0, 0);
                  Name = FieldDesc::GetName(v19);
                  inited = ConvertUtf8(Name, a4, a5, a6);
                  v42 = inited;
                  if ( inited >= 0 && a7 )
                  {
                    FieldDesc::LookupFieldTypeHandle(v19, &v44, 6);
                    v31 = operator new(0x38u, v30);
                    if ( v31 )
                    {
                      v32 = v44;
                      if ( (v44 & 2) != 0 )
                      {
                        v45 = v44 - 2;
                        v33 = DacInstantiateTypeByAddressHelper(v44 - 2, 4u, 1, 1);
                        TypeDesc::GetMethodTable(v33, &v43);
                        v32 = v43;
                      }
                      else
                      {
                        v43 = v44;
                      }
                      v34 = (MethodTable *)DacInstantiateTypeByAddressHelper(v32, 0x40u, 1, 1);
                      v35 = MethodTable::GetTypeDefRid_NoLogging(v34) | 0x2000000;
                      v36 = (unsigned __int64 *)TypeHandle::GetModule(&v44, v50);
                      v37 = DacInstantiateClassByVTable(*v36, 1576, 1);
                      v15 = (struct IXCLRDataTypeDefinition *)ClrDataTypeDefinition::ClrDataTypeDefinition(
                                                                v31,
                                                                *((_QWORD *)this + 2),
                                                                v37,
                                                                v35,
                                                                v44);
                    }
                    *a7 = v15;
                    inited = v15 == 0 ? 0x8007000E : 0;
                    goto LABEL_6;
                  }
                  goto LABEL_43;
                }
              }
              v9 = a2;
            }
          }
        }
        else
        {
          inited = -2147467263;
LABEL_6:
          v42 = inited;
        }
      }
      catch ( Exception *v51 )
      {
        v48 = v51;
        throw;
      }
LABEL_43:
      ;
    }
    catch ( ... )
    {
      v49[1] = 0;
      v49[0] = &DelegatingException::`vftable';
      v49[2] = -1;
      v38 = (struct Exception *)v48;
      v45 = v48;
      v39 = v48 != 0;
      v46 = v39;
      if ( !(__int64)__ClrFlsGetBlock() )
      {
        ExecutionEngine = GetExecutionEngine();
        (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
          ExecutionEngine,
          18);
      }
      v41 = (struct Exception *)v49;
      if ( v38 )
        v41 = v38;
      if ( !DacExceptionFilter(v41, *((struct ClrDataAccess **)this + 2), &v42) )
      {
        v46 = 0;
        throw;
      }
      if ( v39 )
      {
        if ( v38 )
        {
          if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v38 + 80LL))(v38) )
            (**(void (__fastcall ***)(struct Exception *, __int64))v38)(v38, 5);
        }
        v46 = 0;
      }
      DelegatingException::~DelegatingException((DelegatingException *)v49);
      v14 = v47;
      inited = v42;
    }
    g_dacImpl = v14;
    LeaveCriticalSection(&g_dacCritSec);
    return (unsigned int)inited;
  }
  else
  {
    LeaveCriticalSection(&g_dacCritSec);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800288c0  mov     rax, rsp
0x1800288c3  mov     [rax+20h], r9d
0x1800288c7  mov     [rax+18h], r8d
0x1800288cb  mov     [rax+10h], rdx
0x1800288cf  mov     [rax+8], rcx
0x1800288d3  push    rbx
0x1800288d4  push    rsi
0x1800288d5  push    rdi
0x1800288d6  push    r12
0x1800288d8  push    r13
0x1800288da  push    r14
0x1800288dc  push    r15
0x1800288de  sub     rsp, 150h
0x1800288e5  mov     r15d, r8d
0x1800288e8  mov     rbx, rdx
0x1800288eb  mov     r13, rcx
0x1800288ee  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800288f5  call    cs:__imp_EnterCriticalSection
0x1800288fb  mov     r10, [r13+10h]
0x1800288ff  mov     eax, [r13+18h]
0x180028903  cmp     [r10+0B8h], eax
0x18002890a  jz      short loc_180028923
0x18002890c  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028913  call    cs:__imp_LeaveCriticalSection
0x180028919  mov     eax, 80070057h
0x18002891e  jmp     loc_180028C02
0x180028923  mov     r12, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18002892a  mov     [rsp+188h+var_130], r12
0x18002892f  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r10; ClrDataAccess * g_dacImpl
0x180028936  xor     edi, edi
0x180028938  mov     [rsp+188h+var_120], rdi
0x18002893d  lea     rax, [rsp+188h+var_128]
0x180028942  mov     [rsp+188h+var_150], rax
0x180028947  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002894b  mov     [rsp+188h+var_E0], rax
0x180028953  mov     [rsp+188h+var_E8], edi
0x18002895a  mov     [rsp+188h+var_150], rdi
0x18002895f  mov     [rsp+188h+var_E0], rdi
0x180028967  mov     [rsp+188h+var_D8], eax
0x18002896e  mov     [rsp+188h+var_D4], edi
0x180028975  mov     [rsp+188h+var_D0], edi
0x18002897c  mov     [rsp+188h+var_CC], edi
0x180028983  mov     [rsp+188h+var_48], edi
0x18002898a  mov     [rsp+188h+var_44], dil
0x180028992  cmp     [r13+30h], rdi
0x180028996  jnz     short loc_1800289A6
0x180028998  mov     esi, 80004001h
0x18002899d  mov     [rsp+188h+var_158], esi
0x1800289a1  jmp     loc_180028BEC
0x1800289a6  mov     [rsp+188h+var_168], rdi
0x1800289ab  mov     r9d, 0EFFh
0x1800289b1  mov     r8b, 1
0x1800289b4  mov     rdx, [r13+30h]
0x1800289b8  lea     rcx, [rsp+188h+var_E8]
0x1800289c0  call    ?InitFieldIter@@YAJPEAVDeepFieldDescIterator@@VTypeHandle@@_NIPEAUIXCLRDataTypeInstance@@@Z; InitFieldIter(DeepFieldDescIterator *,TypeHandle,bool,uint,IXCLRDataTypeInstance *)
0x1800289c5  mov     esi, eax
0x1800289c7  mov     [rsp+188h+var_158], eax
0x1800289cb  test    eax, eax
0x1800289cd  jnz     short loc_1800289A1
0x1800289cf  mov     esi, 80070057h
0x1800289d4  mov     [rsp+188h+var_158], esi
0x1800289d8  lea     rcx, [rsp+188h+var_E8]; this
0x1800289e0  call    ?Next@DeepFieldDescIterator@@QEAAPEAVFieldDesc@@XZ; DeepFieldDescIterator::Next(void)
0x1800289e5  mov     r14, rax
0x1800289e8  test    rax, rax
0x1800289eb  jz      short loc_1800289A1
0x1800289ed  test    rbx, rbx
0x1800289f0  jz      short loc_180028A60
0x1800289f2  mov     dl, 1
0x1800289f4  mov     rcx, rax
0x1800289f7  call    DacGetTargetAddrForHostAddr
0x1800289fc  mov     rcx, [r14]
0x1800289ff  add     rcx, rax; unsigned __int64
0x180028a02  mov     [rsp+188h+var_150], rcx
0x180028a07  mov     r9b, 1; bool
0x180028a0a  mov     r8b, r9b; bool
0x180028a0d  mov     edx, 40h ; '@'; unsigned int
0x180028a12  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180028a17  lea     rdx, [rsp+188h+var_140]
0x180028a1c  mov     rcx, rax
0x180028a1f  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x180028a24  mov     r8b, 1
0x180028a27  mov     edx, 628h
0x180028a2c  mov     rcx, [rax]; unsigned __int64
0x180028a2f  call    DacInstantiateClassByVTable
0x180028a34  mov     r15, rax
0x180028a37  mov     dl, 1
0x180028a39  mov     rcx, [rbx+28h]
0x180028a3d  call    DacGetTargetAddrForHostAddr
0x180028a42  mov     rbx, rax
0x180028a45  mov     dl, 1
0x180028a47  mov     rcx, r15
0x180028a4a  call    DacGetTargetAddrForHostAddr
0x180028a4f  mov     r15d, [rsp+188h+arg_10]
0x180028a57  cmp     rbx, rax
0x180028a5a  jnz     loc_180028BD6
0x180028a60  mov     eax, [r14+8]
0x180028a64  test    eax, eax
0x180028a66  js      short loc_180028A73
0x180028a68  and     eax, 1FFFFh
0x180028a6d  bts     eax, 1Ah
0x180028a71  jmp     short loc_180028A7C
0x180028a73  and     eax, 0FFFFFFh
0x180028a78  bts     eax, 1Ah
0x180028a7c  cmp     eax, r15d
0x180028a7f  jnz     loc_180028BD6
0x180028a85  mov     rbx, [rsp+188h+arg_38]
0x180028a8d  test    rbx, rbx
0x180028a90  jz      short loc_180028AB6
0x180028a92  mov     al, [rsp+188h+var_44]
0x180028a99  neg     al
0x180028a9b  sbb     r8d, r8d
0x180028a9e  and     r8d, 80h
0x180028aa5  xor     r9d, r9d
0x180028aa8  mov     rdx, r14
0x180028aab  mov     rcx, [r13+30h]
0x180028aaf  call    ?GetTypeFieldValueFlags@@YAIVTypeHandle@@PEAVFieldDesc@@I_N@Z; GetTypeFieldValueFlags(TypeHandle,FieldDesc *,uint,bool)
0x180028ab4  mov     [rbx], eax
0x180028ab6  mov     rcx, r14; this
0x180028ab9  call    ?GetName@FieldDesc@@QEAAPEBDXZ; FieldDesc::GetName(void)
0x180028abe  mov     rcx, rax; lpMultiByteStr
0x180028ac1  mov     r9, [rsp+188h+arg_28]; unsigned __int16 *
0x180028ac9  mov     r8, [rsp+188h+arg_20]; unsigned int *
0x180028ad1  mov     edx, [rsp+188h+cchWideChar]; cchWideChar
0x180028ad8  call    ?ConvertUtf8@@YAJPEBDIPEAIPEAG@Z; ConvertUtf8(char const *,uint,uint *,ushort *)
0x180028add  mov     esi, eax
0x180028adf  mov     [rsp+188h+var_158], eax
0x180028ae3  test    eax, eax
0x180028ae5  js      loc_1800289A1
0x180028aeb  mov     r15, [rsp+188h+arg_30]
0x180028af3  test    r15, r15
0x180028af6  jz      loc_1800289A1
0x180028afc  xor     r9d, r9d
0x180028aff  lea     r8d, [r9+6]
0x180028b03  lea     rdx, [rsp+188h+var_148]
0x180028b08  mov     rcx, r14
0x180028b0b  call    ?LookupFieldTypeHandle@FieldDesc@@QEAA?AVTypeHandle@@W4ClassLoadLevel@@H@Z; FieldDesc::LookupFieldTypeHandle(ClassLoadLevel,int)
0x180028b10  mov     ecx, 38h ; '8'; dwBytes
0x180028b15  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180028b1a  mov     rsi, rax
0x180028b1d  test    rax, rax
0x180028b20  jz      loc_180028BC1
0x180028b26  mov     rcx, [rsp+188h+var_148]; unsigned __int64
0x180028b2b  test    cl, 2
0x180028b2e  jz      short loc_180028B5D
0x180028b30  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180028b34  mov     [rsp+188h+var_140], rcx
0x180028b39  mov     r9b, 1; bool
0x180028b3c  mov     r8b, r9b; bool
0x180028b3f  mov     edx, 4; unsigned int
0x180028b44  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180028b49  mov     rcx, rax
0x180028b4c  lea     rdx, [rsp+188h+var_150]
0x180028b51  call    ?GetMethodTable@TypeDesc@@QEAA?AV?$__DPtr@VMethodTable@@@@XZ; TypeDesc::GetMethodTable(void)
0x180028b56  mov     rcx, [rsp+188h+var_150]
0x180028b5b  jmp     short loc_180028B62
0x180028b5d  mov     [rsp+188h+var_150], rcx
0x180028b62  mov     r9b, 1; bool
0x180028b65  mov     r8b, r9b; bool
0x180028b68  mov     edx, 40h ; '@'; unsigned int
0x180028b6d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180028b72  mov     rcx, rax; this
0x180028b75  call    ?GetTypeDefRid_NoLogging@MethodTable@@QEAAIXZ; MethodTable::GetTypeDefRid_NoLogging(void)
0x180028b7a  mov     ebx, eax
0x180028b7c  bts     ebx, 19h
0x180028b80  lea     rdx, [rsp+188h+var_100]
0x180028b88  lea     rcx, [rsp+188h+var_148]
0x180028b8d  call    ?GetModule@TypeHandle@@QEBA?AV?$__VPtr@VModule@@@@XZ; TypeHandle::GetModule(void)
0x180028b92  mov     r8b, 1
0x180028b95  mov     edx, 628h
0x180028b9a  mov     rcx, [rax]; unsigned __int64
0x180028b9d  call    DacInstantiateClassByVTable
0x180028ba2  mov     rcx, [rsp+188h+var_148]
0x180028ba7  mov     [rsp+188h+var_168], rcx
0x180028bac  mov     r9d, ebx
0x180028baf  mov     r8, rax
0x180028bb2  mov     rdx, [r13+10h]
0x180028bb6  mov     rcx, rsi
0x180028bb9  call    ??0ClrDataTypeDefinition@@QEAA@PEAVClrDataAccess@@PEAVModule@@IVTypeHandle@@@Z; ClrDataTypeDefinition::ClrDataTypeDefinition(ClrDataAccess *,Module *,uint,TypeHandle)
0x180028bbe  mov     rdi, rax
0x180028bc1  mov     [r15], rdi
0x180028bc4  neg     rdi
0x180028bc7  sbb     esi, esi
0x180028bc9  not     esi
0x180028bcb  and     esi, 8007000Eh
0x180028bd1  jmp     loc_18002899D
0x180028bd6  mov     rbx, [rsp+188h+arg_8]
0x180028bde  jmp     loc_1800289D8
0x180028be3  mov     r12, [rsp+188h+var_130]
0x180028be8  mov     esi, [rsp+188h+var_158]
0x180028bec  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r12; ClrDataAccess * g_dacImpl
0x180028bf3  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028bfa  call    cs:__imp_LeaveCriticalSection
0x180028c00  mov     eax, esi
0x180028c02  add     rsp, 150h
0x180028c09  pop     r15
0x180028c0b  pop     r14
0x180028c0d  pop     r13
0x180028c0f  pop     r12
0x180028c11  pop     rdi
0x180028c12  pop     rsi
0x180028c13  pop     rbx
0x180028c14  retn
```
