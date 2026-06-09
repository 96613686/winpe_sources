# ClrDataAccess::GetObjectData(unsigned __int64,DacpObjectData *)

- ea: `0x1800381e0`
- end: `0x18003879c`
- name: `?GetObjectData@ClrDataAccess@@UEAAJ_KPEAUDacpObjectData@@@Z`
- size: `1468`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, struct DacpObjectData *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callees

- `0x18001d580`
- `0x180020f50`
- `0x1800210f0`
- `0x180022068`
- `0x18002b268`
- `0x18002b2f8`
- `0x180032724`
- `0x18003277c`
- `0x1800328f0`
- `0x1800381e0`
- `0x1800f3020`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180038220`
- `KERNEL32!EnterCriticalSection` at `0x180038220`
- `KERNEL32!LeaveCriticalSection` at `0x180038779`
- `KERNEL32!LeaveCriticalSection` at `0x180038779`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ClrDataAccess::GetObjectData(ClrDataAccess *this, unsigned __int64 a2, struct DacpObjectData *a3)
{
  unsigned __int64 v4; // rbx
  ClrDataAccess *v5; // r12
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rax
  int v8; // r15d
  unsigned __int64 *v9; // r14
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 *v16; // rax
  void *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 *v19; // rax
  void *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // r12
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rcx
  struct MethodTable *v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // rax
  void *v29; // rax
  __int64 v30; // rdx
  unsigned __int64 *LowerBoundsPtr; // rax
  void *v32; // rax
  __int64 v33; // rdx
  bool v34; // r8
  unsigned __int64 v35; // rbx
  _QWORD *v36; // rax
  void *v37; // rax
  __int64 v38; // rdx
  _QWORD *v40; // rbx
  int v41; // edi
  _QWORD *v42; // rcx
  _QWORD *v43; // rcx
  struct Exception *v44; // rbx
  BOOL v45; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v47; // rcx
  __int64 v48; // [rsp+0h] [rbp-118h] BYREF
  char *v49; // [rsp+30h] [rbp-E8h]
  int v50; // [rsp+38h] [rbp-E0h] BYREF
  int v51; // [rsp+3Ch] [rbp-DCh] BYREF
  unsigned int v52; // [rsp+40h] [rbp-D8h] BYREF
  struct Exception *v53; // [rsp+48h] [rbp-D0h]
  int v54; // [rsp+50h] [rbp-C8h]
  void **v55; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD *v56; // [rsp+60h] [rbp-B8h]
  __int64 v57; // [rsp+68h] [rbp-B0h]
  unsigned __int64 v58; // [rsp+70h] [rbp-A8h]
  _QWORD v59[3]; // [rsp+78h] [rbp-A0h] BYREF
  unsigned __int64 *v60; // [rsp+90h] [rbp-88h]
  unsigned __int64 v61; // [rsp+98h] [rbp-80h]
  ClrDataAccess *v62; // [rsp+A0h] [rbp-78h]
  unsigned __int64 v63; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-68h]
  char v65; // [rsp+B8h] [rbp-60h] BYREF
  struct Exception *v66; // [rsp+C0h] [rbp-58h]
  char v67[8]; // [rsp+C8h] [rbp-50h] BYREF
  _QWORD *v68; // [rsp+D0h] [rbp-48h] BYREF
  struct Exception *v69; // [rsp+D8h] [rbp-40h] BYREF
  unsigned __int64 v71; // [rsp+128h] [rbp+10h] BYREF
  int v72; // [rsp+138h] [rbp+20h] BYREF

  v71 = a2;
  v4 = a2;
  v5 = this;
  v6 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v62 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)v5 - 16);
  v72 = 0;
  v66 = 0;
  try
  {
    try
    {
      v49 = &v65;
      memset(a3, 0, 0x60u);
      v7 = DACGetMethodTableFromObjectPointer(v4, *((struct ICorDebugDataTarget **)v5 + 3));
      v8 = 0;
      if ( !v7 )
        v8 = -2147024809;
      v72 = v8;
      v50 = 0;
      v60 = 0;
      if ( v8 < 0 )
        goto LABEL_89;
      v49 = (char *)v7;
      v9 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v7, 0x40u, 1, 1);
      v60 = v9;
      if ( !(unsigned int)DacValidateMethodTable((struct MethodTable *)v9, &v50) )
        v8 = -2147024809;
      v72 = v8;
      if ( v8 < 0 )
        goto LABEL_89;
      LOBYTE(v10) = 1;
      *(_QWORD *)a3 = DacGetTargetAddrForHostAddr(v9, v10);
      *((_QWORD *)a3 + 2) = *((unsigned int *)v9 + 1);
      if ( *(int *)v9 >= 0 )
        v11 = 0;
      else
        v11 = *(unsigned __int16 *)v9;
      if ( v11 )
      {
        v12 = *((_QWORD *)v5 + 3);
        v51 = 0;
        v52 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, unsigned __int64, unsigned int *, __int64, int *))(*(_QWORD *)v12 + 32LL))(
               v12,
               v4 + 8,
               &v52,
               4,
               &v51)
          || v51 != 4 )
        {
          v13 = 0;
        }
        else
        {
          v13 = v52;
        }
        if ( *(int *)v9 >= 0 )
          v14 = 0;
        else
          v14 = *(unsigned __int16 *)v9;
        *((_QWORD *)a3 + 2) += v14 * v13;
        if ( *(int *)v9 >= 0 )
          v15 = 0;
        else
          v15 = *(unsigned __int16 *)v9;
        *((_QWORD *)a3 + 6) = v15;
      }
      if ( v50 )
      {
        *((_DWORD *)a3 + 2) = 1;
        goto LABEL_47;
      }
      v49 = (char *)((unsigned int)*g_pStringClass[0] + DacGlobalBase());
      v16 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v49, 8u, 1, 1);
      v17 = DacInstantiateTypeByAddressHelper(*v16, 0x40u, 1, 1);
      LOBYTE(v18) = 1;
      if ( *(_QWORD *)a3 == DacGetTargetAddrForHostAddr(v17, v18) )
      {
        *((_DWORD *)a3 + 2) = 0;
        goto LABEL_47;
      }
      v49 = (char *)((unsigned int)*g_pObjectClass[0] + DacGlobalBase());
      v19 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v49, 8u, 1, 1);
      v20 = DacInstantiateTypeByAddressHelper(*v19, 0x40u, 1, 1);
      LOBYTE(v21) = 1;
      if ( *(_QWORD *)a3 == DacGetTargetAddrForHostAddr(v20, v21) )
      {
        *((_DWORD *)a3 + 2) = 2;
        goto LABEL_47;
      }
      if ( (*(_DWORD *)v9 & 0xC0000) != 0x80000 )
      {
        *((_DWORD *)a3 + 2) = 4;
LABEL_47:
        LODWORD(v55) = 0;
        v56 = 0;
        try
        {
          try
          {
            v71 = (unsigned __int64)&v55;
            DACGetSyncBlockFromObjectPointer(&v71, v4, *((_QWORD *)v5 + 3));
            if ( v71 )
            {
              v35 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v71, 0x50u, 1, 1) + 5);
              v71 = v35;
              if ( v35 )
              {
                *((_QWORD *)a3 + 10) = *((_QWORD *)DacInstantiateTypeByAddressHelper(v35, 0x20u, 1, 1) + 3)
                                     & 0xFFFFFFFFFFFFFFFEuLL;
                v36 = DacInstantiateTypeByAddressHelper(v35, 0x20u, 1, 1);
                v64 = 1;
                if ( v36[1] == 1 )
                {
                  v71 = 0;
                }
                else
                {
                  v6 = v36[1];
                  v71 = v6;
                }
                v37 = DacInstantiateTypeByAddressHelper(v6, 0x40u, 1, 1);
                LOBYTE(v38) = 1;
                *((_QWORD *)a3 + 11) = DacGetTargetAddrForHostAddr(v37, v38);
              }
            }
          }
          catch ( Exception *v68 )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v55);
            v56 = v68;
            throw;
          }
        }
        catch ( ... )
        {
          v59[1] = 0;
          v59[0] = &DelegatingException::`vftable';
          v59[2] = -1;
          v40 = v56;
          v53 = (struct Exception *)v56;
          v41 = 0;
          v54 = 0;
          if ( v56 )
          {
            v41 = 1;
            v54 = 1;
          }
          Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v55, (int)&v48, v34);
          v42 = v59;
          if ( v40 )
            v42 = v40;
          if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42) != -2147024597 )
          {
            v43 = v59;
            if ( v40 )
              v43 = v40;
            if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43) != -2146231223 )
            {
              v54 = 0;
              throw;
            }
          }
          if ( v41 )
          {
            if ( v40 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD *))(*v40 + 80LL))(v40) )
                (*(void (__fastcall **)(_QWORD *, __int64))*v40)(v40, 5);
            }
            v54 = 0;
          }
          DelegatingException::~DelegatingException((DelegatingException *)v59);
          v8 = v72;
          goto LABEL_89;
        }
        goto LABEL_89;
      }
      *((_DWORD *)a3 + 2) = 3;
      v49 = (char *)v4;
      v22 = (__int64 *)DacInstantiateTypeByAddressHelper(v4, 0x10u, 1, 1);
      v23 = v9[5];
      if ( (v23 & 2) != 0 )
      {
        if ( (v23 & 1) == 0 )
        {
          v49 = (char *)(v23 - 2);
          v23 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v23 - 2, 0x40u, 1, 1) + 5);
          v58 = v23;
LABEL_37:
          v49 = (char *)v23;
          *((_DWORD *)a3 + 8) = *((_DWORD *)DacInstantiateTypeByAddressHelper(v23, 0x50u, 1, 1) + 19);
          v24 = v9[6];
          v49 = (char *)v24;
          v25 = v24;
          v61 = v24;
          while ( (v25 & 2) != 0 )
          {
            v49 = (char *)(v25 - 2);
            v25 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v25 - 2, 0x28u, 1, 1) + 2);
            v61 = v25;
          }
          v49 = (char *)v25;
          v26 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(v25, 0x40u, 1, 1);
          if ( (unsigned int)DacValidateMethodTable(v26, &v50) )
          {
            *((_QWORD *)a3 + 3) = v24;
            *((_DWORD *)a3 + 9) = MethodTable::GetRank((MethodTable *)v9);
            *((_QWORD *)a3 + 5) = *((unsigned int *)v22 + 2);
            *((_QWORD *)a3 + 7) = *(_QWORD *)ArrayBase::GetDataPtr(v22, &v63, 1);
            v64 = *v22;
            v63 = v64 & 0xFFFFFFFFFFFFFFFEuLL;
            if ( (~(*(_DWORD *)DacInstantiateTypeByAddressHelper(v64 & 0xFFFFFFFFFFFFFFFEuLL, 0x40u, 1, 1) >> 17) & 1) != 0 )
            {
              LOBYTE(v27) = 1;
              v28 = DacGetTargetAddrForHostAddr(v22, v27) + 16;
            }
            else
            {
              LOBYTE(v27) = 1;
              v28 = DacGetTargetAddrForHostAddr(v22, v27) + 8;
            }
            v49 = (char *)v28;
            v29 = DacInstantiateTypeByAddressHelper(v28, 4u, 1, 1);
            LOBYTE(v30) = 1;
            *((_QWORD *)a3 + 8) = DacGetTargetAddrForHostAddr(v29, v30);
            LowerBoundsPtr = (unsigned __int64 *)ArrayBase::GetLowerBoundsPtr(v22, v67);
            v32 = DacInstantiateTypeByAddressHelper(*LowerBoundsPtr, 4u, 1, 1);
            LOBYTE(v33) = 1;
            *((_QWORD *)a3 + 9) = DacGetTargetAddrForHostAddr(v32, v33);
            v4 = v71;
            v5 = this;
            goto LABEL_47;
          }
          v8 = -2147024809;
          v72 = -2147024809;
          goto LABEL_89;
        }
        v49 = (char *)(v23 - 3);
        v49 = *(char **)DacInstantiateTypeByAddressHelper(v23 - 3, 8u, 1, 1);
        v23 = *((_QWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)v49, 0x40u, 1, 1) + 5);
      }
      v58 = v23;
      goto LABEL_37;
    }
    catch ( Exception *v69 )
    {
      v66 = v69;
      throw;
    }
  }
  catch ( ... )
  {
    v56 = 0;
    v55 = &DelegatingException::`vftable';
    v57 = -1;
    v44 = v66;
    v53 = v66;
    v45 = v66 != 0;
    v54 = v45;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v47 = (struct Exception *)&v55;
    if ( v44 )
      v47 = v44;
    if ( !DacExceptionFilter(v47, (ClrDataAccess *)((char *)this - 16), &v72) )
    {
      v54 = 0;
      throw;
    }
    if ( v45 )
    {
      if ( v44 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v44 + 80LL))(v44) )
        (**(void (__fastcall ***)(struct Exception *, __int64))v44)(v44, 5);
      v54 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v55);
    v8 = v72;
  }
LABEL_89:
  g_dacImpl = v62;
  LeaveCriticalSection(&g_dacCritSec);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800381e0  mov     [rsp+arg_8], rdx
0x1800381e5  mov     [rsp+arg_0], rcx
0x1800381ea  push    rbx
0x1800381eb  push    rsi
0x1800381ec  push    rdi
0x1800381ed  push    r12
0x1800381ef  push    r13
0x1800381f1  push    r14
0x1800381f3  push    r15
0x1800381f5  sub     rsp, 0E0h
0x1800381fc  mov     rsi, r8
0x1800381ff  mov     rbx, rdx
0x180038202  mov     r12, rcx
0x180038205  xor     edi, edi
0x180038207  test    rdx, rdx
0x18003820a  jz      loc_180038784
0x180038210  test    r8, r8
0x180038213  jz      loc_180038784
0x180038219  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038220  call    cs:__imp_EnterCriticalSection
0x180038226  mov     rax, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18003822d  mov     [rsp+118h+var_78], rax
0x180038235  lea     rax, [r12-10h]
0x18003823a  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180038241  mov     [rsp+118h+arg_18], edi
0x180038248  mov     [rsp+118h+var_58], rdi
0x180038250  lea     rax, [rsp+118h+var_60]
0x180038258  mov     [rsp+118h+var_E8], rax
0x18003825d  xor     edx, edx; Val
0x18003825f  lea     r8d, [rdi+60h]; Size
0x180038263  mov     rcx, rsi; void *
0x180038266  call    memset
0x18003826b  mov     rdx, [r12+18h]; struct ICorDebugDataTarget *
0x180038270  mov     rcx, rbx; unsigned __int64
0x180038273  call    ?DACGetMethodTableFromObjectPointer@@YA_K_KPEAUICorDebugDataTarget@@@Z; DACGetMethodTableFromObjectPointer(unsigned __int64,ICorDebugDataTarget *)
0x180038278  mov     r15d, edi
0x18003827b  mov     r13d, 80070057h
0x180038281  test    rax, rax
0x180038284  cmovz   r15d, r13d
0x180038288  mov     [rsp+118h+arg_18], r15d
0x180038290  mov     [rsp+118h+var_E0], edi
0x180038294  mov     [rsp+118h+var_88], rdi
0x18003829c  test    r15d, r15d
0x18003829f  js      loc_180038759
0x1800382a5  mov     [rsp+118h+var_E8], rax
0x1800382aa  mov     r9b, 1; bool
0x1800382ad  mov     r8b, r9b; bool
0x1800382b0  lea     edx, [rdi+40h]; unsigned int
0x1800382b3  mov     rcx, rax; unsigned __int64
0x1800382b6  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800382bb  mov     r14, rax
0x1800382be  mov     [rsp+118h+var_88], rax
0x1800382c6  lea     rdx, [rsp+118h+var_E0]; int *
0x1800382cb  mov     rcx, rax; struct MethodTable *
0x1800382ce  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x1800382d3  test    eax, eax
0x1800382d5  cmovz   r15d, r13d
0x1800382d9  mov     [rsp+118h+arg_18], r15d
0x1800382e1  test    r15d, r15d
0x1800382e4  js      loc_180038759
0x1800382ea  mov     dl, 1
0x1800382ec  mov     rcx, r14
0x1800382ef  call    DacGetTargetAddrForHostAddr
0x1800382f4  mov     [rsi], rax
0x1800382f7  mov     eax, [r14+4]
0x1800382fb  mov     [rsi+10h], rax
0x1800382ff  cmp     [r14], edi
0x180038302  jge     short loc_18003830A
0x180038304  movzx   eax, word ptr [r14]
0x180038308  jmp     short loc_18003830C
0x18003830a  mov     eax, edi
0x18003830c  test    eax, eax
0x18003830e  jz      short loc_18003837E
0x180038310  mov     rcx, [r12+18h]
0x180038315  lea     rdx, [rbx+8]
0x180038319  mov     [rsp+118h+var_DC], edi
0x18003831d  mov     [rsp+118h+var_D8], edi
0x180038321  mov     rax, [rcx]
0x180038324  lea     r8, [rsp+118h+var_DC]
0x180038329  mov     [rsp+118h+var_F8], r8
0x18003832e  mov     r9d, 4
0x180038334  lea     r8, [rsp+118h+var_D8]
0x180038339  mov     rax, [rax+20h]
0x18003833d  call    cs:__guard_dispatch_icall_fptr
0x180038343  test    eax, eax
0x180038345  jnz     short loc_180038354
0x180038347  cmp     [rsp+118h+var_DC], 4
0x18003834c  jnz     short loc_180038354
0x18003834e  mov     eax, [rsp+118h+var_D8]
0x180038352  jmp     short loc_180038356
0x180038354  mov     eax, edi
0x180038356  cmp     [r14], edi
0x180038359  jge     short loc_180038361
0x18003835b  movzx   ecx, word ptr [r14]
0x18003835f  jmp     short loc_180038364
0x180038361  mov     rcx, rdi
0x180038364  imul    rax, rcx
0x180038368  add     [rsi+10h], rax
0x18003836c  cmp     [r14], edi
0x18003836f  jge     short loc_180038377
0x180038371  movzx   eax, word ptr [r14]
0x180038375  jmp     short loc_18003837A
0x180038377  mov     rax, rdi
0x18003837a  mov     [rsi+30h], rax
0x18003837e  cmp     [rsp+118h+var_E0], edi
0x180038382  jz      short loc_180038390
0x180038384  mov     dword ptr [rsi+8], 1
0x18003838b  jmp     loc_18003866B
0x180038390  call    DacGlobalBase
0x180038395  mov     r10, rax
0x180038398  mov     rax, cs:?g_pStringClass@@3V?$__GlobalPtr@PEAVMethodTable@@V?$__DPtr@VMethodTable@@@@@@A; __GlobalPtr<MethodTable *,__DPtr<MethodTable>> g_pStringClass
0x18003839f  mov     ecx, [rax]
0x1800383a1  add     r10, rcx
0x1800383a4  mov     [rsp+118h+var_E8], r10
0x1800383a9  mov     r9b, 1; bool
0x1800383ac  mov     r8b, r9b; bool
0x1800383af  mov     edx, 8; unsigned int
0x1800383b4  mov     rcx, r10; unsigned __int64
0x1800383b7  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800383bc  mov     r9b, 1; bool
0x1800383bf  mov     r8b, r9b; bool
0x1800383c2  mov     edx, 40h ; '@'; unsigned int
0x1800383c7  mov     rcx, [rax]; unsigned __int64
0x1800383ca  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800383cf  mov     dl, 1
0x1800383d1  mov     rcx, rax
0x1800383d4  call    DacGetTargetAddrForHostAddr
0x1800383d9  cmp     [rsi], rax
0x1800383dc  jnz     short loc_1800383E6
0x1800383de  mov     [rsi+8], edi
0x1800383e1  jmp     loc_18003866B
0x1800383e6  call    DacGlobalBase
0x1800383eb  mov     rcx, rax
0x1800383ee  mov     rax, cs:?g_pObjectClass@@3V?$__GlobalPtr@PEAVMethodTable@@V?$__DPtr@VMethodTable@@@@@@A; __GlobalPtr<MethodTable *,__DPtr<MethodTable>> g_pObjectClass
0x1800383f5  mov     edx, [rax]
0x1800383f7  add     rcx, rdx; unsigned __int64
0x1800383fa  mov     [rsp+118h+var_E8], rcx
0x1800383ff  mov     r9b, 1; bool
0x180038402  mov     r8b, r9b; bool
0x180038405  mov     edx, 8; unsigned int
0x18003840a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003840f  mov     r9b, 1; bool
0x180038412  mov     r8b, r9b; bool
0x180038415  mov     edx, 40h ; '@'; unsigned int
0x18003841a  mov     rcx, [rax]; unsigned __int64
0x18003841d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038422  mov     dl, 1
0x180038424  mov     rcx, rax
0x180038427  call    DacGetTargetAddrForHostAddr
0x18003842c  cmp     [rsi], rax
0x18003842f  jnz     short loc_18003843D
0x180038431  mov     dword ptr [rsi+8], 2
0x180038438  jmp     loc_18003866B
0x18003843d  mov     eax, [r14]
0x180038440  and     eax, 0C0000h
0x180038445  cmp     eax, 80000h
0x18003844a  jnz     loc_180038664
0x180038450  mov     dword ptr [rsi+8], 3
0x180038457  mov     [rsp+118h+var_E8], rbx
0x18003845c  mov     r9b, 1; bool
0x18003845f  mov     r8b, r9b; bool
0x180038462  mov     edx, 10h; unsigned int
0x180038467  mov     rcx, rbx; unsigned __int64
0x18003846a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003846f  mov     r12, rax
0x180038472  mov     rcx, [r14+28h]
0x180038476  test    cl, 2
0x180038479  jnz     short loc_180038482
0x18003847b  mov     [rsp+118h+var_A8], rcx
0x180038480  jmp     short loc_1800384E0
0x180038482  test    cl, 1
0x180038485  jz      short loc_1800384BE
0x180038487  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x18003848b  mov     [rsp+118h+var_E8], rcx
0x180038490  mov     r9b, 1; bool
0x180038493  mov     r8b, r9b; bool
0x180038496  mov     edx, 8; unsigned int
0x18003849b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800384a0  mov     rcx, [rax]; unsigned __int64
0x1800384a3  mov     [rsp+118h+var_E8], rcx
0x1800384a8  mov     r9b, 1; bool
0x1800384ab  mov     r8b, r9b; bool
0x1800384ae  mov     edx, 40h ; '@'; unsigned int
0x1800384b3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800384b8  mov     rcx, [rax+28h]
0x1800384bc  jmp     short loc_18003847B
0x1800384be  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x1800384c2  mov     [rsp+118h+var_E8], rcx
0x1800384c7  mov     r9b, 1; bool
0x1800384ca  mov     r8b, r9b; bool
0x1800384cd  mov     edx, 40h ; '@'; unsigned int
0x1800384d2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800384d7  mov     rcx, [rax+28h]; unsigned __int64
0x1800384db  mov     [rsp+118h+var_A8], rcx
0x1800384e0  mov     [rsp+118h+var_E8], rcx
0x1800384e5  mov     r9b, 1; bool
0x1800384e8  mov     r8b, r9b; bool
0x1800384eb  mov     edx, 50h ; 'P'; unsigned int
0x1800384f0  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800384f5  mov     eax, [rax+4Ch]
0x1800384f8  mov     [rsi+20h], eax
0x1800384fb  mov     rbx, [r14+30h]
0x1800384ff  mov     [rsp+118h+var_E8], rbx
0x180038504  mov     rcx, rbx; unsigned __int64
0x180038507  mov     [rsp+118h+var_80], rbx
0x18003850f  test    cl, 2
0x180038512  jz      short loc_18003853B
0x180038514  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180038518  mov     [rsp+118h+var_E8], rcx
0x18003851d  mov     r9b, 1; bool
0x180038520  mov     r8b, r9b; bool
0x180038523  mov     edx, 28h ; '('; unsigned int
0x180038528  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003852d  mov     rcx, [rax+10h]
0x180038531  mov     [rsp+118h+var_80], rcx
0x180038539  jmp     short loc_18003850F
0x18003853b  mov     [rsp+118h+var_E8], rcx
0x180038540  mov     r9b, 1; bool
0x180038543  mov     r8b, r9b; bool
0x180038546  mov     edx, 40h ; '@'; unsigned int
0x18003854b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038550  lea     rdx, [rsp+118h+var_E0]; int *
0x180038555  mov     rcx, rax; struct MethodTable *
0x180038558  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x18003855d  test    eax, eax
0x18003855f  jnz     short loc_180038571
0x180038561  mov     r15d, r13d
0x180038564  mov     [rsp+118h+arg_18], r13d
0x18003856c  jmp     loc_180038759
0x180038571  mov     [rsi+18h], rbx
0x180038575  mov     rcx, r14; this
0x180038578  call    ?GetRank@MethodTable@@QEAAKXZ; MethodTable::GetRank(void)
0x18003857d  mov     [rsi+24h], eax
0x180038580  mov     eax, [r12+8]
0x180038585  mov     [rsi+28h], rax
0x180038589  mov     r8d, 1
0x18003858f  lea     rdx, [rsp+118h+var_70]
0x180038597  mov     rcx, r12
0x18003859a  call    ?GetDataPtr@ArrayBase@@QEBA?AV?$__ArrayDPtr@E@@H@Z; ArrayBase::GetDataPtr(int)
0x18003859f  mov     rcx, [rax]
0x1800385a2  mov     [rsi+38h], rcx
0x1800385a6  mov     rcx, [r12]
0x1800385aa  mov     [rsp+118h+var_68], rcx
0x1800385b2  and     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x1800385b6  mov     [rsp+118h+var_70], rcx
0x1800385be  mov     r9b, 1; bool
0x1800385c1  mov     r8b, r9b; bool
0x1800385c4  mov     edx, 40h ; '@'; unsigned int
0x1800385c9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800385ce  mov     eax, [rax]
0x1800385d0  shr     eax, 11h
0x1800385d3  not     eax
0x1800385d5  test    al, 1
0x1800385d7  jz      short loc_1800385EE
0x1800385d9  mov     dl, 1
0x1800385db  mov     rcx, r12
0x1800385de  call    DacGetTargetAddrForHostAddr
0x1800385e3  add     rax, 10h
0x1800385e7  mov     [rsp+118h+var_E8], rax
0x1800385ec  jmp     short loc_180038601
0x1800385ee  mov     dl, 1
0x1800385f0  mov     rcx, r12
0x1800385f3  call    DacGetTargetAddrForHostAddr
0x1800385f8  add     rax, 8
0x1800385fc  mov     [rsp+118h+var_E8], rax
0x180038601  mov     r9b, 1; bool
0x180038604  mov     r8b, r9b; bool
0x180038607  mov     ebx, 4
0x18003860c  mov     edx, ebx; unsigned int
0x18003860e  mov     rcx, rax; unsigned __int64
0x180038611  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038616  mov     dl, 1
0x180038618  mov     rcx, rax
0x18003861b  call    DacGetTargetAddrForHostAddr
0x180038620  mov     [rsi+40h], rax
0x180038624  lea     rdx, [rsp+118h+var_50]
0x18003862c  mov     rcx, r12
0x18003862f  call    ?GetLowerBoundsPtr@ArrayBase@@QEBA?AV?$__DPtr@H@@XZ; ArrayBase::GetLowerBoundsPtr(void)
0x180038634  mov     r9b, 1; bool
0x180038637  mov     r8b, r9b; bool
0x18003863a  mov     edx, ebx; unsigned int
0x18003863c  mov     rcx, [rax]; unsigned __int64
0x18003863f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038644  mov     dl, 1
0x180038646  mov     rcx, rax
0x180038649  call    DacGetTargetAddrForHostAddr
0x18003864e  mov     [rsi+48h], rax
0x180038652  mov     rbx, [rsp+118h+arg_8]
0x18003865a  mov     r12, [rsp+118h+arg_0]
0x180038662  jmp     short loc_18003866B
0x180038664  mov     dword ptr [rsi+8], 4
0x18003866b  test    r15d, r15d
0x18003866e  js      loc_180038759
0x180038674  mov     dword ptr [rsp+118h+var_C0], edi
0x180038678  mov     [rsp+118h+var_B8], rdi
0x18003867d  lea     rax, [rsp+118h+var_C0]
0x180038682  mov     [rsp+118h+arg_8], rax
0x18003868a  mov     r8, [r12+18h]
0x18003868f  mov     rdx, rbx
0x180038692  lea     rcx, [rsp+118h+arg_8]
  ... truncated ...
```
