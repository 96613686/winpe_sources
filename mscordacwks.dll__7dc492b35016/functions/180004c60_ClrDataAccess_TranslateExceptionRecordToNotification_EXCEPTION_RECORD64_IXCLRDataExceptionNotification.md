# ClrDataAccess::TranslateExceptionRecordToNotification(_EXCEPTION_RECORD64 *,IXCLRDataExceptionNotification *)

- ea: `0x180004c60`
- end: `0x1800051c8`
- name: `?TranslateExceptionRecordToNotification@ClrDataAccess@@UEAAJPEAU_EXCEPTION_RECORD64@@PEAUIXCLRDataExceptionNotification@@@Z`
- size: `1384`
- prototype: `__int64 __fastcall(ClrDataAccess *__hidden this, struct _EXCEPTION_RECORD64 *, struct IXCLRDataExceptionNotification *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180004c60`
- `0x18000ceac`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x18002c9e4`
- `0x180030148`
- `0x180031c34`
- `0x18007262c`
- `0x18008a06c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004cd8`
- `KERNEL32!EnterCriticalSection` at `0x180004cd8`
- `KERNEL32!LeaveCriticalSection` at `0x180004fd8`
- `KERNEL32!LeaveCriticalSection` at `0x180004fd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataAccess::TranslateExceptionRecordToNotification(
        ClrDataAccess *this,
        struct _EXCEPTION_RECORD64 *a2,
        struct IXCLRDataExceptionNotification *a3)
{
  struct IXCLRDataExceptionNotification *v3; // r13
  unsigned int v5; // ebx
  ClrDataModule *v6; // r12
  ClrDataMethodInstance *v7; // r14
  struct _EXCEPTION_RECORD64 *v8; // r8
  unsigned int v9; // edx
  int v10; // esi
  MethodDesc *v11; // r14
  struct BaseDomain *Domain; // rbx
  __int64 v13; // rdx
  const struct NoThrow *v14; // rdx
  __int64 *v15; // rbx
  ClrDataMethodInstance *v16; // rax
  ClrDataMethodInstance *v17; // rax
  int v18; // r15d
  __int64 *v19; // rax
  bool v20; // zf
  __int64 *v21; // rbx
  const struct NoThrow *v22; // rdx
  ClrDataModule *v23; // rax
  ClrDataAccess *v24; // rcx
  int v25; // eax
  struct ClrDataAccess *v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  ClrDataAccess *v30; // rcx
  int v31; // esi
  int v32; // esi
  int v33; // esi
  int v34; // esi
  int v35; // esi
  struct ClrDataExceptionState *v36; // rsi
  struct Exception *v38; // rbx
  BOOL v39; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v41; // rcx
  __int64 v42; // [rsp+20h] [rbp-198h] BYREF
  struct ClrDataExceptionState *v43; // [rsp+28h] [rbp-190h] BYREF
  struct ClrDataAccess *v44; // [rsp+30h] [rbp-188h] BYREF
  char *TargetAddrForHostAddr; // [rsp+38h] [rbp-180h]
  BOOL v46; // [rsp+40h] [rbp-178h]
  int v47; // [rsp+48h] [rbp-170h]
  unsigned int v48; // [rsp+4Ch] [rbp-16Ch]
  ClrDataAccess *v49; // [rsp+50h] [rbp-168h] BYREF
  struct _EXCEPTION_RECORD64 *v50; // [rsp+58h] [rbp-160h]
  unsigned int v51; // [rsp+60h] [rbp-158h]
  ClrDataModule *v52; // [rsp+68h] [rbp-150h]
  ClrDataMethodInstance *v53; // [rsp+70h] [rbp-148h]
  struct ClrDataAccess *v54; // [rsp+78h] [rbp-140h]
  ClrDataAccess *v55; // [rsp+80h] [rbp-138h]
  struct IXCLRDataExceptionNotification *v56; // [rsp+88h] [rbp-130h]
  char v57; // [rsp+90h] [rbp-128h] BYREF
  unsigned __int64 v58; // [rsp+98h] [rbp-120h]
  _QWORD v59[4]; // [rsp+A0h] [rbp-118h] BYREF
  int v60; // [rsp+C0h] [rbp-F8h]
  unsigned __int64 v61; // [rsp+C8h] [rbp-F0h] BYREF
  _BYTE v62[24]; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 *v63; // [rsp+E8h] [rbp-D0h]
  int v64; // [rsp+F0h] [rbp-C8h]
  __int64 v65; // [rsp+100h] [rbp-B8h]
  unsigned __int64 v66; // [rsp+108h] [rbp-B0h]
  unsigned int v67; // [rsp+110h] [rbp-A8h]

  v3 = a3;
  v50 = a2;
  v44 = this;
  v54 = this;
  v56 = a3;
  v5 = -2147467259;
  LODWORD(v42) = -2147467259;
  v6 = 0;
  v52 = 0;
  v7 = 0;
  v53 = 0;
  v43 = 0;
  v47 = 0;
  v48 = 0;
  EnterCriticalSection(&g_dacCritSec);
  v49 = g_dacImpl;
  v55 = g_dacImpl;
  g_dacImpl = this;
  v58 = 0;
  try
  {
    try
    {
      TargetAddrForHostAddr = &v57;
      v9 = 0;
      v51 = 0;
      v18 = 1;
      v8 = v50;
      while ( v9 < 0xF )
      {
        *(&v65 + v9) = v8->ExceptionInformation[v9];
        v51 = ++v9;
      }
      v10 = v65;
      v47 = v65;
      switch ( (_DWORD)v65 )
      {
        case 1:
          v20 = v65 == 1;
          break;
        case 2:
          v20 = v65 == 2;
          break;
        case 3:
          if ( v65 != 3 )
            goto LABEL_95;
          TargetAddrForHostAddr = (char *)v66;
          v11 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v66, 8u, 1, 1);
          Domain = MethodDesc::GetDomain(v11);
          if ( !(*(unsigned int (__fastcall **)(struct BaseDomain *))(*(_QWORD *)Domain + 8LL))(Domain) )
          {
            v64 = 0;
            UnsafeAppDomainIterator::Init((UnsafeAppDomainIterator *)v62);
            v15 = v63;
            goto LABEL_15;
          }
          goto LABEL_13;
        case 5:
          if ( v65 == 5 )
          {
            TargetAddrForHostAddr = (char *)v66;
            v19 = DacInstantiateClassByVTable(v66, 1992, 1);
            v5 = ClrDataExceptionState::NewFromThread(v44, (struct Thread *)v19, &v43, 0);
            LODWORD(v42) = v5;
          }
          goto LABEL_95;
        case 6:
          if ( v65 == 6 )
          {
            LODWORD(v50) = v66;
            if ( (_DWORD)v66 == 1 )
              HIDWORD(v50) = v67;
            else
              v18 = 0;
            if ( v18 )
            {
              v5 = 0;
              goto LABEL_39;
            }
          }
          goto LABEL_95;
        case 7:
          if ( v65 != 7 )
            goto LABEL_95;
          v48 = v67;
          TargetAddrForHostAddr = (char *)v66;
          v11 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v66, 8u, 1, 1);
          Domain = MethodDesc::GetDomain(v11);
          if ( !(*(unsigned int (__fastcall **)(struct BaseDomain *))(*(_QWORD *)Domain + 8LL))(Domain) )
          {
            v60 = 0;
            UnsafeAppDomainIterator::Init((UnsafeAppDomainIterator *)v59);
            v15 = (__int64 *)v59[3];
            goto LABEL_15;
          }
LABEL_13:
          LOBYTE(v13) = 1;
          TargetAddrForHostAddr = (char *)DacGetTargetAddrForHostAddr(Domain, v13);
          v15 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 4144, 1);
LABEL_15:
          v16 = (ClrDataMethodInstance *)operator new(0x30u, v14);
          if ( v16 )
            v7 = ClrDataMethodInstance::ClrDataMethodInstance(v16, v44, (struct AppDomain *)v15, v11);
          else
            v7 = 0;
          v53 = v7;
          v17 = v7;
LABEL_38:
          v5 = v17 == 0 ? 0x8007000E : 0;
          goto LABEL_39;
        default:
          v5 = -2147024809;
LABEL_39:
          LODWORD(v42) = v5;
          goto LABEL_95;
      }
      if ( v20 )
      {
        TargetAddrForHostAddr = (char *)v66;
        v21 = DacInstantiateClassByVTable(v66, 1576, 1);
        v23 = (ClrDataModule *)operator new(0x68u, v22);
        if ( v23 )
          v6 = ClrDataModule::ClrDataModule(v23, v44, (struct Module *)v21);
        else
          v6 = 0;
        v17 = v6;
        v52 = v6;
        goto LABEL_38;
      }
    }
    catch ( Exception *v61 )
    {
      v58 = v61;
      throw;
    }
  }
  catch ( ... )
  {
    v59[1] = 0;
    v59[0] = &DelegatingException::`vftable';
    v59[2] = -1;
    v38 = (struct Exception *)v58;
    TargetAddrForHostAddr = (char *)v58;
    v39 = v58 != 0;
    v46 = v39;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v41 = (struct Exception *)v59;
    if ( v38 )
      v41 = v38;
    if ( !DacExceptionFilter(v41, v54, (int *)&v42) )
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
    DelegatingException::~DelegatingException((DelegatingException *)v59);
    v5 = v42;
    v6 = v52;
    v7 = v53;
    v10 = v47;
    v24 = v55;
    v3 = v56;
    goto LABEL_41;
  }
LABEL_95:
  v24 = v49;
LABEL_41:
  g_dacImpl = v24;
  LeaveCriticalSection(&g_dacCritSec);
  if ( v5 )
  {
    v36 = v43;
    goto LABEL_70;
  }
  v25 = (**(__int64 (__fastcall ***)(struct IXCLRDataExceptionNotification *, GUID *, struct ClrDataAccess **))v3)(
          v3,
          &GUID_31201a94_4337_49b7_aef7_0c755054091f,
          &v44);
  v26 = v44;
  if ( v25 )
    v26 = 0;
  v44 = v26;
  v27 = (**(__int64 (__fastcall ***)(struct IXCLRDataExceptionNotification *, GUID *, __int64 *))v3)(
          v3,
          &GUID_31201a94_4337_49b7_aef7_0c7550540920,
          &v42);
  v28 = v42;
  if ( v27 )
    v28 = 0;
  v42 = v28;
  v29 = (**(__int64 (__fastcall ***)(struct IXCLRDataExceptionNotification *, GUID *, ClrDataAccess **))v3)(
          v3,
          &GUID_c25e926e_5f09_4aa2_bbad_b7fc7f10cfd7,
          &v49);
  v30 = v49;
  if ( v29 )
    v30 = 0;
  v49 = v30;
  v31 = v10 - 1;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( v33 )
      {
        v34 = v33 - 2;
        if ( !v34 )
        {
          v36 = v43;
          if ( v44 )
            (*(void (__fastcall **)(struct ClrDataAccess *, struct ClrDataExceptionState *))(*(_QWORD *)v44 + 104LL))(
              v44,
              v43);
          else
            v5 = -2147024809;
          goto LABEL_65;
        }
        v35 = v34 - 1;
        if ( v35 )
        {
          if ( v35 == 1 && v30 )
            (*(void (__fastcall **)(ClrDataAccess *, ClrDataMethodInstance *, _QWORD))(*(_QWORD *)v30 + 120LL))(
              v30,
              v7,
              v48);
        }
        else if ( v42 )
        {
          (*(void (__fastcall **)(__int64, struct _EXCEPTION_RECORD64 *))(*(_QWORD *)v42 + 112LL))(v42, v50);
        }
      }
      else
      {
        (*(void (__fastcall **)(struct IXCLRDataExceptionNotification *, ClrDataMethodInstance *))(*(_QWORD *)v3 + 24LL))(
          v3,
          v7);
      }
    }
    else
    {
      (*(void (__fastcall **)(struct IXCLRDataExceptionNotification *, ClrDataModule *))(*(_QWORD *)v3 + 64LL))(v3, v6);
    }
  }
  else
  {
    (*(void (__fastcall **)(struct IXCLRDataExceptionNotification *, ClrDataModule *))(*(_QWORD *)v3 + 56LL))(v3, v6);
  }
  v36 = v43;
LABEL_65:
  if ( v44 )
    (*(void (__fastcall **)(struct ClrDataAccess *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_70:
  if ( v6 )
    (*(void (__fastcall **)(ClrDataModule *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(ClrDataMethodInstance *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v36 )
    (*(void (__fastcall **)(struct ClrDataExceptionState *))(*(_QWORD *)v36 + 16LL))(v36);
  return v5;
}

```

## disassembly

```asm
0x180004c60  mov     [rsp+arg_8], rbx
0x180004c65  mov     [rsp+arg_18], rsi
0x180004c6a  push    rdi
0x180004c6b  push    r12
0x180004c6d  push    r13
0x180004c6f  push    r14
0x180004c71  push    r15
0x180004c73  sub     rsp, 190h
0x180004c7a  mov     rax, cs:__security_cookie
0x180004c81  xor     rax, rsp
0x180004c84  mov     [rsp+1B8h+var_38], rax
0x180004c8c  mov     r13, r8
0x180004c8f  mov     [rsp+1B8h+var_160], rdx
0x180004c94  mov     rsi, rcx
0x180004c97  mov     [rsp+1B8h+var_188], rcx
0x180004c9c  mov     [rsp+1B8h+var_140], rcx
0x180004ca1  mov     [rsp+1B8h+var_130], r8
0x180004ca9  mov     ebx, 80004005h
0x180004cae  mov     dword ptr [rsp+1B8h+var_198], ebx
0x180004cb2  xor     edi, edi
0x180004cb4  mov     r12d, edi
0x180004cb7  mov     [rsp+1B8h+var_150], rdi
0x180004cbc  mov     r14d, edi
0x180004cbf  mov     [rsp+1B8h+var_148], rdi
0x180004cc4  mov     [rsp+1B8h+var_190], rdi
0x180004cc9  mov     [rsp+1B8h+var_170], edi
0x180004ccd  mov     [rsp+1B8h+var_16C], edi
0x180004cd1  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004cd8  call    cs:__imp_EnterCriticalSection
0x180004cde  mov     rcx, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180004ce5  mov     [rsp+1B8h+var_168], rcx
0x180004cea  mov     [rsp+1B8h+var_138], rcx
0x180004cf2  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rsi; ClrDataAccess * g_dacImpl
0x180004cf9  mov     [rsp+1B8h+var_120], rdi
0x180004d01  lea     rax, [rsp+1B8h+var_128]
0x180004d09  mov     [rsp+1B8h+var_180], rax
0x180004d0e  mov     edx, edi
0x180004d10  mov     [rsp+1B8h+var_158], edx
0x180004d14  lea     r15d, [rdi+1]
0x180004d18  mov     r8, [rsp+1B8h+var_160]
0x180004d1d  cmp     edx, 0Fh
0x180004d20  jnb     short loc_180004D3A
0x180004d22  mov     ecx, edx
0x180004d24  mov     rax, [r8+rcx*8+20h]
0x180004d29  mov     [rsp+rcx*8+1B8h+var_B8], rax
0x180004d31  add     edx, r15d
0x180004d34  mov     [rsp+1B8h+var_158], edx
0x180004d38  jmp     short loc_180004D1D
0x180004d3a  mov     rsi, [rsp+1B8h+var_B8]
0x180004d42  mov     [rsp+1B8h+var_170], esi
0x180004d46  mov     eax, esi
0x180004d48  sub     eax, r15d
0x180004d4b  jz      loc_180004F3B
0x180004d51  sub     eax, r15d
0x180004d54  jz      loc_180004F35
0x180004d5a  sub     eax, r15d
0x180004d5d  jz      loc_180004ECD
0x180004d63  sub     eax, 2
0x180004d66  jz      loc_180004E89
0x180004d6c  sub     eax, r15d
0x180004d6f  jz      loc_180004E4E
0x180004d75  cmp     eax, r15d
0x180004d78  jz      short loc_180004D84
0x180004d7a  mov     ebx, 80070057h
0x180004d7f  jmp     loc_180004F9B
0x180004d84  cmp     rsi, 7
0x180004d88  jnz     loc_180004F40
0x180004d8e  mov     eax, [rsp+1B8h+var_A8]
0x180004d95  mov     [rsp+1B8h+var_16C], eax
0x180004d99  mov     rcx, [rsp+1B8h+var_B0]; unsigned __int64
0x180004da1  mov     [rsp+1B8h+var_180], rcx
0x180004da6  mov     r9b, r15b; bool
0x180004da9  mov     r8b, r15b; bool
0x180004dac  lea     edx, [rsi+1]; unsigned int
0x180004daf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180004db4  mov     r14, rax
0x180004db7  mov     rcx, rax; this
0x180004dba  call    ?GetDomain@MethodDesc@@QEAAPEAVBaseDomain@@XZ; MethodDesc::GetDomain(void)
0x180004dbf  mov     rbx, rax
0x180004dc2  mov     rax, [rax]
0x180004dc5  mov     rcx, rbx
0x180004dc8  mov     rax, [rax+8]
0x180004dcc  call    cs:__guard_dispatch_icall_fptr
0x180004dd2  test    eax, eax
0x180004dd4  jz      short loc_180004DFB
0x180004dd6  mov     dl, r15b
0x180004dd9  mov     rcx, rbx
0x180004ddc  call    DacGetTargetAddrForHostAddr
0x180004de1  mov     [rsp+1B8h+var_180], rax
0x180004de6  mov     r8b, r15b
0x180004de9  mov     edx, 1030h
0x180004dee  mov     rcx, rax; unsigned __int64
0x180004df1  call    DacInstantiateClassByVTable
0x180004df6  mov     rbx, rax
0x180004df9  jmp     short loc_180004E17
0x180004dfb  mov     [rsp+1B8h+var_F8], edi
0x180004e02  lea     rcx, [rsp+1B8h+var_118]; this
0x180004e0a  call    ?Init@UnsafeAppDomainIterator@@QEAAXXZ; UnsafeAppDomainIterator::Init(void)
0x180004e0f  mov     rbx, [rsp+1B8h+var_100]
0x180004e17  mov     ecx, 30h ; '0'; dwBytes
0x180004e1c  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180004e21  test    rax, rax
0x180004e24  jz      short loc_180004E3E
0x180004e26  mov     r9, r14; struct MethodDesc *
0x180004e29  mov     r8, rbx; struct AppDomain *
0x180004e2c  mov     rdx, [rsp+1B8h+var_188]; struct ClrDataAccess *
0x180004e31  mov     rcx, rax; this
0x180004e34  call    ??0ClrDataMethodInstance@@QEAA@PEAVClrDataAccess@@PEAVAppDomain@@PEAVMethodDesc@@@Z; ClrDataMethodInstance::ClrDataMethodInstance(ClrDataAccess *,AppDomain *,MethodDesc *)
0x180004e39  mov     r14, rax
0x180004e3c  jmp     short loc_180004E41
0x180004e3e  mov     r14, rdi
0x180004e41  mov     [rsp+1B8h+var_148], r14
0x180004e46  mov     rax, r14
0x180004e49  jmp     loc_180004F8E
0x180004e4e  cmp     rsi, 6
0x180004e52  jnz     loc_180004F40
0x180004e58  mov     rcx, [rsp+1B8h+var_B0]
0x180004e60  mov     dword ptr [rsp+1B8h+var_160], ecx
0x180004e64  cmp     ecx, r15d
0x180004e67  jz      short loc_180004E6E
0x180004e69  mov     r15d, edi
0x180004e6c  jmp     short loc_180004E79
0x180004e6e  mov     eax, [rsp+1B8h+var_A8]
0x180004e75  mov     dword ptr [rsp+1B8h+var_160+4], eax
0x180004e79  test    r15d, r15d
0x180004e7c  jz      loc_180004F9F
0x180004e82  mov     ebx, edi
0x180004e84  jmp     loc_180004F9B
0x180004e89  cmp     rsi, 5
0x180004e8d  jnz     loc_180004F40
0x180004e93  mov     rcx, [rsp+1B8h+var_B0]; unsigned __int64
0x180004e9b  mov     [rsp+1B8h+var_180], rcx
0x180004ea0  mov     r8b, r15b
0x180004ea3  mov     edx, 7C8h
0x180004ea8  call    DacInstantiateClassByVTable
0x180004ead  xor     r9d, r9d; struct IXCLRDataExceptionState **
0x180004eb0  lea     r8, [rsp+1B8h+var_190]; struct ClrDataExceptionState **
0x180004eb5  mov     rdx, rax; struct Thread *
0x180004eb8  mov     rcx, [rsp+1B8h+var_188]; struct ClrDataAccess *
0x180004ebd  call    ?NewFromThread@ClrDataExceptionState@@SAJPEAVClrDataAccess@@PEAVThread@@PEAPEAV1@PEAPEAUIXCLRDataExceptionState@@@Z; ClrDataExceptionState::NewFromThread(ClrDataAccess *,Thread *,ClrDataExceptionState * *,IXCLRDataExceptionState * *)
0x180004ec2  mov     ebx, eax
0x180004ec4  mov     dword ptr [rsp+1B8h+var_198], eax
0x180004ec8  jmp     loc_180004F9F
0x180004ecd  cmp     rsi, 3
0x180004ed1  jnz     short loc_180004F40
0x180004ed3  mov     rcx, [rsp+1B8h+var_B0]; unsigned __int64
0x180004edb  mov     [rsp+1B8h+var_180], rcx
0x180004ee0  mov     r9b, r15b; bool
0x180004ee3  mov     r8b, r15b; bool
0x180004ee6  lea     edx, [rsi+5]; unsigned int
0x180004ee9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180004eee  mov     r14, rax
0x180004ef1  mov     rcx, rax; this
0x180004ef4  call    ?GetDomain@MethodDesc@@QEAAPEAVBaseDomain@@XZ; MethodDesc::GetDomain(void)
0x180004ef9  mov     rbx, rax
0x180004efc  mov     rcx, [rax]
0x180004eff  mov     rax, [rcx+8]
0x180004f03  mov     rcx, rbx
0x180004f06  call    cs:__guard_dispatch_icall_fptr
0x180004f0c  test    eax, eax
0x180004f0e  jnz     loc_180004DD6
0x180004f14  mov     [rsp+1B8h+var_C8], edi
0x180004f1b  lea     rcx, [rsp+1B8h+var_E8]; this
0x180004f23  call    ?Init@UnsafeAppDomainIterator@@QEAAXXZ; UnsafeAppDomainIterator::Init(void)
0x180004f28  mov     rbx, [rsp+1B8h+var_D0]
0x180004f30  jmp     loc_180004E17
0x180004f35  cmp     rsi, 2
0x180004f39  jmp     short loc_180004F3E
0x180004f3b  cmp     rsi, r15
0x180004f3e  jz      short loc_180004F42
0x180004f40  jmp     short loc_180004F9F
0x180004f42  mov     rcx, [rsp+1B8h+var_B0]; unsigned __int64
0x180004f4a  mov     [rsp+1B8h+var_180], rcx
0x180004f4f  mov     r8b, r15b
0x180004f52  mov     edx, 628h
0x180004f57  call    DacInstantiateClassByVTable
0x180004f5c  mov     rbx, rax
0x180004f5f  mov     ecx, 68h ; 'h'; dwBytes
0x180004f64  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180004f69  test    rax, rax
0x180004f6c  jz      short loc_180004F83
0x180004f6e  mov     r8, rbx; struct Module *
0x180004f71  mov     rdx, [rsp+1B8h+var_188]; struct ClrDataAccess *
0x180004f76  mov     rcx, rax; this
0x180004f79  call    ??0ClrDataModule@@QEAA@PEAVClrDataAccess@@PEAVModule@@@Z; ClrDataModule::ClrDataModule(ClrDataAccess *,Module *)
0x180004f7e  mov     r12, rax
0x180004f81  jmp     short loc_180004F86
0x180004f83  mov     r12, rdi
0x180004f86  mov     rax, r12
0x180004f89  mov     [rsp+1B8h+var_150], r12
0x180004f8e  neg     rax
0x180004f91  sbb     ebx, ebx
0x180004f93  not     ebx
0x180004f95  and     ebx, 8007000Eh
0x180004f9b  mov     dword ptr [rsp+1B8h+var_198], ebx
0x180004f9f  mov     rcx, [rsp+1B8h+var_168]
0x180004fa4  jmp     short loc_180004FCA
0x180004fa6  xor     edi, edi
0x180004fa8  mov     ebx, dword ptr [rsp+1B8h+var_198]
0x180004fac  mov     r12, [rsp+1B8h+var_150]
0x180004fb1  mov     r14, [rsp+1B8h+var_148]
0x180004fb6  mov     esi, [rsp+1B8h+var_170]
0x180004fba  mov     rcx, [rsp+1B8h+var_138]
0x180004fc2  mov     r13, [rsp+1B8h+var_130]
0x180004fca  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rcx; ClrDataAccess * g_dacImpl
0x180004fd1  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004fd8  call    cs:__imp_LeaveCriticalSection
0x180004fde  test    ebx, ebx
0x180004fe0  jnz     loc_180005154
0x180004fe6  mov     rax, [r13+0]
0x180004fea  lea     r8, [rsp+1B8h+var_188]
0x180004fef  lea     rdx, _GUID_31201a94_4337_49b7_aef7_0c755054091f
0x180004ff6  mov     rcx, r13
0x180004ff9  mov     rax, [rax]
0x180004ffc  call    cs:__guard_dispatch_icall_fptr
0x180005002  mov     rcx, [rsp+1B8h+var_188]
0x180005007  test    eax, eax
0x180005009  cmovnz  rcx, rdi
0x18000500d  mov     [rsp+1B8h+var_188], rcx
0x180005012  mov     rax, [r13+0]
0x180005016  lea     r8, [rsp+1B8h+var_198]
0x18000501b  lea     rdx, _GUID_31201a94_4337_49b7_aef7_0c7550540920
0x180005022  mov     rcx, r13
0x180005025  mov     rax, [rax]
0x180005028  call    cs:__guard_dispatch_icall_fptr
0x18000502e  mov     rcx, [rsp+1B8h+var_198]
0x180005033  test    eax, eax
0x180005035  cmovnz  rcx, rdi
0x180005039  mov     [rsp+1B8h+var_198], rcx
0x18000503e  mov     rax, [r13+0]
0x180005042  lea     r8, [rsp+1B8h+var_168]
0x180005047  lea     rdx, _GUID_c25e926e_5f09_4aa2_bbad_b7fc7f10cfd7
0x18000504e  mov     rcx, r13
0x180005051  mov     rax, [rax]
0x180005054  call    cs:__guard_dispatch_icall_fptr
0x18000505a  mov     rcx, [rsp+1B8h+var_168]
0x18000505f  test    eax, eax
0x180005061  cmovnz  rcx, rdi
0x180005065  mov     [rsp+1B8h+var_168], rcx
0x18000506a  sub     esi, 1
0x18000506d  jz      loc_18000510B
0x180005073  sub     esi, 1
0x180005076  jz      loc_180005101
0x18000507c  sub     esi, 1
0x18000507f  jz      short loc_1800050F4
0x180005081  sub     esi, 2
0x180005084  jz      short loc_1800050CC
0x180005086  sub     esi, 1
0x180005089  jz      short loc_1800050B4
0x18000508b  cmp     esi, 1
0x18000508e  jnz     loc_18000511F
0x180005094  test    rcx, rcx
0x180005097  jz      loc_18000511F
0x18000509d  mov     rax, [rcx]
0x1800050a0  mov     r8d, [rsp+1B8h+var_16C]
0x1800050a5  mov     rdx, r14
0x1800050a8  mov     rax, [rax+78h]
0x1800050ac  call    cs:__guard_dispatch_icall_fptr
0x1800050b2  jmp     short loc_18000511F
0x1800050b4  mov     rcx, [rsp+1B8h+var_198]
0x1800050b9  test    rcx, rcx
0x1800050bc  jz      short loc_18000511F
0x1800050be  mov     rax, [rcx]
0x1800050c1  mov     rdx, [rsp+1B8h+var_160]
0x1800050c6  mov     rax, [rax+70h]
0x1800050ca  jmp     short loc_180005119
0x1800050cc  mov     rcx, [rsp+1B8h+var_188]
0x1800050d1  mov     rsi, [rsp+1B8h+var_190]
0x1800050d6  test    rcx, rcx
0x1800050d9  jz      short loc_1800050ED
0x1800050db  mov     rax, [rcx]
0x1800050de  mov     rdx, rsi
0x1800050e1  mov     rax, [rax+68h]
0x1800050e5  call    cs:__guard_dispatch_icall_fptr
0x1800050eb  jmp     short loc_180005124
0x1800050ed  mov     ebx, 80070057h
0x1800050f2  jmp     short loc_180005124
0x1800050f4  mov     rax, [r13+0]
0x1800050f8  mov     rdx, r14
0x1800050fb  mov     rax, [rax+18h]
0x1800050ff  jmp     short loc_180005116
0x180005101  mov     rax, [r13+0]
0x180005105  mov     rax, [rax+40h]
0x180005109  jmp     short loc_180005113
0x18000510b  mov     rax, [r13+0]
0x18000510f  mov     rax, [rax+38h]
0x180005113  mov     rdx, r12
0x180005116  mov     rcx, r13
0x180005119  call    cs:__guard_dispatch_icall_fptr
0x18000511f  mov     rsi, [rsp+1B8h+var_190]
0x180005124  mov     rcx, [rsp+1B8h+var_188]
0x180005129  test    rcx, rcx
0x18000512c  jz      short loc_18000513B
0x18000512e  mov     rax, [rcx]
0x180005131  mov     rax, [rax+10h]
0x180005135  call    cs:__guard_dispatch_icall_fptr
0x18000513b  mov     rcx, [rsp+1B8h+var_198]
0x180005140  test    rcx, rcx
0x180005143  jz      short loc_180005159
0x180005145  mov     rax, [rcx]
  ... truncated ...
```
