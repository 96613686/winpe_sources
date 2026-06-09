# ClrDataAccess::GetAppDomainData(unsigned __int64,DacpAppDomainData *)

- ea: `0x180038a50`
- end: `0x180038fe7`
- name: `?GetAppDomainData@ClrDataAccess@@UEAAJ_KPEAUDacpAppDomainData@@@Z`
- size: `1431`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, struct DacpAppDomainData *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bd18`
- `0x18000c170`
- `0x18000c4fc`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180038a50`
- `0x180074af0`
- `0x18009752c`
- `0x1800f3020`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180038a79`
- `KERNEL32!EnterCriticalSection` at `0x180038a79`
- `KERNEL32!LeaveCriticalSection` at `0x180038fc2`
- `KERNEL32!LeaveCriticalSection` at `0x180038fc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ClrDataAccess::GetAppDomainData(
        ClrDataAccess *this,
        unsigned __int64 a2,
        struct DacpAppDomainData *a3)
{
  __int64 *v6; // rax
  void *v7; // rax
  __int64 v8; // rdx
  void *v9; // rax
  __int64 v10; // rdx
  void *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  unsigned __int64 *v16; // rax
  __int64 *v17; // r14
  int v18; // ecx
  int v19; // edi
  __int64 *v20; // rax
  __int64 *v21; // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  unsigned int v25; // eax
  __int64 *v26; // rax
  __int64 *v27; // rax
  int IsIntrospectionOnly; // eax
  _QWORD *v29; // rax
  int v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // rdx
  bool v33; // r8
  _QWORD *v35; // rbx
  int v36; // edi
  _QWORD *v37; // rcx
  int v38; // eax
  struct Exception *v39; // rbx
  BOOL v40; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v42; // rcx
  __int64 v43; // [rsp+0h] [rbp-148h] BYREF
  int *TargetAddrForHostAddr; // [rsp+20h] [rbp-128h] BYREF
  __int64 *v45; // [rsp+28h] [rbp-120h]
  int v46; // [rsp+30h] [rbp-118h]
  unsigned __int64 v47; // [rsp+38h] [rbp-110h] BYREF
  struct Exception *v48; // [rsp+40h] [rbp-108h]
  int v49; // [rsp+48h] [rbp-100h]
  __int128 v50; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-E8h]
  int v52; // [rsp+68h] [rbp-E0h] BYREF
  _QWORD *v53; // [rsp+70h] [rbp-D8h]
  __int64 *v54; // [rsp+78h] [rbp-D0h]
  __int128 v55; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v56; // [rsp+90h] [rbp-B8h]
  int v57; // [rsp+98h] [rbp-B0h]
  ClrDataAccess *v58; // [rsp+A0h] [rbp-A8h]
  char v59; // [rsp+A8h] [rbp-A0h] BYREF
  struct Exception *v60; // [rsp+B0h] [rbp-98h]
  __int128 v61; // [rsp+B8h] [rbp-90h]
  __int64 v62; // [rsp+C8h] [rbp-80h]
  _QWORD v63[3]; // [rsp+D0h] [rbp-78h] BYREF
  __int128 v64; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v65; // [rsp+F8h] [rbp-50h]
  _QWORD *v66; // [rsp+108h] [rbp-40h] BYREF
  struct Exception *v67; // [rsp+110h] [rbp-38h] BYREF
  unsigned int v69; // [rsp+168h] [rbp+20h] BYREF

  EnterCriticalSection(&g_dacCritSec);
  v58 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v69 = 0;
  v60 = 0;
  try
  {
    try
    {
      v47 = (unsigned __int64)&v59;
      if ( !a2 )
      {
        v69 = -2147024809;
        goto LABEL_88;
      }
      v47 = a2;
      memset(a3, 0, 0x48u);
      *(_QWORD *)a3 = a2;
      v6 = DacInstantiateClassByVTable(a2, 1360, 1);
      (*(void (__fastcall **)(__int64 *, unsigned __int64 *))(*v6 + 24))(v6, &v47);
      TargetAddrForHostAddr = (int *)DacInstantiateClassByVTable(v47, 816, 1)[67];
      v7 = DacInstantiateTypeByAddressHelper((unsigned __int64)TargetAddrForHostAddr, 0x90u, 1, 1);
      LOBYTE(v8) = 1;
      *((_QWORD *)a3 + 3) = DacGetTargetAddrForHostAddr(v7, v8);
      TargetAddrForHostAddr = (int *)DacInstantiateClassByVTable(v47, 816, 1)[66];
      v9 = DacInstantiateTypeByAddressHelper((unsigned __int64)TargetAddrForHostAddr, 0x90u, 1, 1);
      LOBYTE(v10) = 1;
      *((_QWORD *)a3 + 2) = DacGetTargetAddrForHostAddr(v9, v10);
      TargetAddrForHostAddr = (int *)DacInstantiateClassByVTable(v47, 816, 1)[68];
      v11 = DacInstantiateTypeByAddressHelper((unsigned __int64)TargetAddrForHostAddr, 0x90u, 1, 1);
      LOBYTE(v12) = 1;
      *((_QWORD *)a3 + 4) = DacGetTargetAddrForHostAddr(v11, v12);
      *((_DWORD *)a3 + 17) = 3;
      v13 = DacInstantiateClassByVTable(a2, 1360, 1);
      if ( (*(unsigned int (__fastcall **)(__int64 *))(*v13 + 16))(v13) )
      {
        SharedDomain::SharedAssemblyIterator::SharedAssemblyIterator((SharedDomain::SharedAssemblyIterator *)&v64);
        while ( (unsigned int)SharedDomain::SharedAssemblyIterator::Next((SharedDomain::SharedAssemblyIterator *)&v64) )
          ++*((_DWORD *)a3 + 15);
        goto LABEL_88;
      }
      v14 = DacInstantiateClassByVTable(a2, 1360, 1);
      if ( !(*(unsigned int (__fastcall **)(__int64 *))(*v14 + 8))(v14) )
        goto LABEL_88;
      v15 = DacInstantiateClassByVTable(a2, 1360, 1);
      v16 = (unsigned __int64 *)(*(__int64 (__fastcall **)(__int64 *, int **))(*v15 + 32))(v15, &TargetAddrForHostAddr);
      v17 = DacInstantiateClassByVTable(*v16, 4144, 1);
      *((_QWORD *)a3 + 5) = *(_QWORD *)a3 + 16LL;
      *((_QWORD *)a3 + 6) = v17[3];
      *((_DWORD *)a3 + 14) = *((_DWORD *)v17 + 2);
      *((_DWORD *)a3 + 17) = *((_DWORD *)v17 + 808);
      if ( (unsigned int)(*((_DWORD *)v17 + 808) - 2) > 9 )
        goto LABEL_55;
      v54 = v17;
      v18 = *((_DWORD *)v17 + 340);
      *(_QWORD *)&v61 = v17 + 171;
      DWORD2(v61) = -1;
      HIDWORD(v61) = v18;
      LODWORD(v62) = 0;
      v55 = v61;
      v56 = v62;
      v57 = 7;
      v45 = 0;
      v19 = 0;
      v46 = 0;
LABEL_11:
      TargetAddrForHostAddr = (int *)(v54 + 56);
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            do
            {
              if ( !(unsigned int)ArrayListBase::Iterator::Next((ArrayListBase::Iterator *)&v55) )
              {
                if ( v19 )
                {
                  v19 = 0;
                  v46 = 0;
                }
                v21 = 0;
                v45 = 0;
                v22 = 0;
LABEL_47:
                if ( v22 )
                {
                  if ( *((int *)v21 + 10) >= 11 )
                    ++*((_DWORD *)a3 + 15);
                  goto LABEL_11;
                }
                v30 = *((_DWORD *)v17 + 830);
                *(_QWORD *)&v50 = v17 + 416;
                DWORD2(v50) = -1;
                HIDWORD(v50) = v30;
                LODWORD(v51) = 0;
                v64 = v50;
                v65 = v51;
                while ( (unsigned int)ArrayListBase::Iterator::Next((ArrayListBase::Iterator *)&v64) )
                  ++*((_DWORD *)a3 + 16);
                if ( v19 )
                  v46 = 0;
LABEL_55:
                v52 = 0;
                v53 = 0;
                try
                {
                  try
                  {
                    TargetAddrForHostAddr = &v52;
                    v31 = DacInstantiateClassByVTable(v17[364], 8, 1);
                    LOBYTE(v32) = 1;
                    *((_QWORD *)a3 + 1) = DacGetTargetAddrForHostAddr(v31, v32);
                  }
                  catch ( Exception *v66 )
                  {
                    Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v52);
                    v53 = v66;
                    throw;
                  }
                }
                catch ( ... )
                {
                  v63[1] = 0;
                  v63[0] = &DelegatingException::`vftable';
                  v63[2] = -1;
                  v35 = v53;
                  v48 = (struct Exception *)v53;
                  v36 = 0;
                  v49 = 0;
                  if ( v53 )
                  {
                    v36 = 1;
                    v49 = 1;
                  }
                  Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v52, (int)&v43, v33);
                  v37 = v63;
                  if ( v35 )
                    v37 = v35;
                  v38 = (*(__int64 (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
                  if ( v38 != -2147024866 && v38 != -2146231223 )
                  {
                    v49 = 0;
                    throw;
                  }
                  if ( v36 )
                  {
                    if ( v35 && !(*(unsigned int (__fastcall **)(_QWORD *))(*v35 + 80LL))(v35) )
                      (*(void (__fastcall **)(_QWORD *, __int64))*v35)(v35, 5);
                    v49 = 0;
                  }
                  DelegatingException::~DelegatingException((DelegatingException *)v63);
                  goto LABEL_88;
                }
                goto LABEL_88;
              }
              TargetAddrForHostAddr = *(int **)(v55 + 8LL * DWORD2(v55) + 16);
              v20 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 240, 1);
              v21 = v20;
            }
            while ( !v20 );
            if ( !v20[7] )
              break;
            if ( (v57 & 0x10) != 0 )
              goto LABEL_16;
          }
          if ( (v20[8] & 1) != 0 && (v57 & 0x20) != 0 )
            goto LABEL_26;
          if ( *((int *)v20 + 10) < 11 )
            break;
          if ( (v57 & 1) != 0 )
            goto LABEL_26;
        }
        if ( (v57 & 2) != 0 )
        {
LABEL_26:
          v24 = DacInstantiateClassByVTable(v20[2], 200, 1);
          v25 = *((_DWORD *)v24 + 28);
          if ( (v25 & 4) != 0 )
          {
            LOBYTE(v23) = 1;
            TargetAddrForHostAddr = (int *)DacGetTargetAddrForHostAddr(v24, v23);
            v26 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 216, 1);
            v27 = DacInstantiateClassByVTable(v26[25], 280, 1);
            IsIntrospectionOnly = PEFile::IsIntrospectionOnly((PEFile *)v27);
          }
          else
          {
            IsIntrospectionOnly = (v25 >> 10) & 1;
          }
          if ( IsIntrospectionOnly )
          {
            if ( (v57 & 8) != 0 )
            {
LABEL_33:
              if ( !*((_DWORD *)v21 + 58) )
              {
LABEL_16:
                if ( v19 )
                  v46 = 0;
                v45 = v21;
                v19 = 1;
                v46 = 1;
LABEL_19:
                v22 = 1;
                goto LABEL_47;
              }
              if ( (v57 & 0x40) == 0 )
              {
                v29 = DacInstantiateTypeByAddressHelper(v21[15], 0x118u, 1, 1);
                if ( (DacInstantiateClassByVTable(v29[11], 1576, 1)[4] & 1) != 0 )
                {
                  if ( *((_DWORD *)DomainFile::GetLoaderAllocator((DomainFile *)v21) + 192) )
                  {
                    if ( v19 )
                      v46 = 0;
                    v45 = v21;
                    v19 = 1;
                    v46 = 1;
                    DomainFile::GetLoaderAllocator((DomainFile *)v21);
                    goto LABEL_19;
                  }
                  if ( (v57 & 0x80u) != 0 )
                  {
                    if ( v19 )
                    {
                      v19 = 0;
                      v46 = 0;
                    }
                    v45 = v21;
                    goto LABEL_19;
                  }
                }
              }
            }
          }
          else if ( (v57 & 4) != 0 )
          {
            goto LABEL_33;
          }
        }
      }
    }
    catch ( Exception *v67 )
    {
      v60 = v67;
      throw;
    }
  }
  catch ( ... )
  {
    *((_QWORD *)&v50 + 1) = 0;
    *(_QWORD *)&v50 = &DelegatingException::`vftable';
    v51 = -1;
    v39 = v60;
    v48 = v60;
    v40 = v60 != 0;
    v49 = v40;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v42 = (struct Exception *)&v50;
    if ( v39 )
      v42 = v39;
    if ( !DacExceptionFilter(v42, (ClrDataAccess *)((char *)this - 16), (int *)&v69) )
    {
      v49 = 0;
      throw;
    }
    if ( v40 )
    {
      if ( v39 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v39 + 80LL))(v39) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v39)(v39, 5);
      }
      v49 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v50);
  }
LABEL_88:
  g_dacImpl = v58;
  LeaveCriticalSection(&g_dacCritSec);
  return v69;
}

```

## disassembly

```asm
0x180038a50  mov     [rsp+arg_8], rbx
0x180038a55  mov     [rsp+arg_0], rcx
0x180038a5a  push    rsi
0x180038a5b  push    rdi
0x180038a5c  push    r12
0x180038a5e  push    r14
0x180038a60  push    r15
0x180038a62  sub     rsp, 120h
0x180038a69  mov     rsi, r8
0x180038a6c  mov     rdi, rdx
0x180038a6f  mov     rbx, rcx
0x180038a72  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038a79  call    cs:__imp_EnterCriticalSection
0x180038a7f  mov     rax, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180038a86  mov     [rsp+148h+var_A8], rax
0x180038a8e  lea     rax, [rbx-10h]
0x180038a92  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180038a99  xor     r15d, r15d
0x180038a9c  mov     [rsp+148h+arg_18], r15d
0x180038aa4  mov     [rsp+148h+var_98], r15
0x180038aac  lea     rax, [rsp+148h+var_A0]
0x180038ab4  mov     [rsp+148h+var_110], rax
0x180038ab9  test    rdi, rdi
0x180038abc  jnz     short loc_180038ACE
0x180038abe  mov     [rsp+148h+arg_18], 80070057h
0x180038ac9  jmp     loc_180038FAC
0x180038ace  mov     [rsp+148h+var_110], rdi
0x180038ad3  xor     edx, edx; Val
0x180038ad5  lea     r8d, [rdx+48h]; Size
0x180038ad9  mov     rcx, rsi; void *
0x180038adc  call    memset
0x180038ae1  mov     [rsi], rdi
0x180038ae4  mov     r12d, 1
0x180038aea  mov     r8b, r12b
0x180038aed  mov     edx, 550h
0x180038af2  mov     rcx, rdi; unsigned __int64
0x180038af5  call    DacInstantiateClassByVTable
0x180038afa  mov     r8, rax
0x180038afd  mov     rcx, [rax]
0x180038b00  mov     rax, [rcx+18h]
0x180038b04  lea     rdx, [rsp+148h+var_110]
0x180038b09  mov     rcx, r8
0x180038b0c  call    cs:__guard_dispatch_icall_fptr
0x180038b12  mov     r8b, r12b
0x180038b15  mov     r14d, 330h
0x180038b1b  mov     edx, r14d
0x180038b1e  mov     rcx, [rsp+148h+var_110]; unsigned __int64
0x180038b23  call    DacInstantiateClassByVTable
0x180038b28  mov     rcx, [rax+218h]; unsigned __int64
0x180038b2f  mov     [rsp+148h+var_128], rcx
0x180038b34  mov     r9b, r12b; bool
0x180038b37  mov     r8b, r12b; bool
0x180038b3a  mov     ebx, 90h
0x180038b3f  mov     edx, ebx; unsigned int
0x180038b41  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038b46  mov     dl, r12b
0x180038b49  mov     rcx, rax
0x180038b4c  call    DacGetTargetAddrForHostAddr
0x180038b51  mov     [rsi+18h], rax
0x180038b55  mov     r8b, r12b
0x180038b58  mov     edx, r14d
0x180038b5b  mov     rcx, [rsp+148h+var_110]; unsigned __int64
0x180038b60  call    DacInstantiateClassByVTable
0x180038b65  mov     rcx, [rax+210h]; unsigned __int64
0x180038b6c  mov     [rsp+148h+var_128], rcx
0x180038b71  mov     r9b, r12b; bool
0x180038b74  mov     r8b, r12b; bool
0x180038b77  mov     edx, ebx; unsigned int
0x180038b79  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038b7e  mov     dl, r12b
0x180038b81  mov     rcx, rax
0x180038b84  call    DacGetTargetAddrForHostAddr
0x180038b89  mov     [rsi+10h], rax
0x180038b8d  mov     r8b, r12b
0x180038b90  mov     edx, r14d
0x180038b93  mov     rcx, [rsp+148h+var_110]; unsigned __int64
0x180038b98  call    DacInstantiateClassByVTable
0x180038b9d  mov     rcx, [rax+220h]; unsigned __int64
0x180038ba4  mov     [rsp+148h+var_128], rcx
0x180038ba9  mov     r9b, r12b; bool
0x180038bac  mov     r8b, r12b; bool
0x180038baf  mov     edx, ebx; unsigned int
0x180038bb1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038bb6  mov     dl, r12b
0x180038bb9  mov     rcx, rax
0x180038bbc  call    DacGetTargetAddrForHostAddr
0x180038bc1  mov     [rsi+20h], rax
0x180038bc5  mov     dword ptr [rsi+44h], 3
0x180038bcc  mov     r8b, r12b
0x180038bcf  mov     edx, 550h
0x180038bd4  mov     rcx, rdi; unsigned __int64
0x180038bd7  call    DacInstantiateClassByVTable
0x180038bdc  mov     rdx, rax
0x180038bdf  mov     rcx, [rax]
0x180038be2  mov     rax, [rcx+10h]
0x180038be6  mov     rcx, rdx
0x180038be9  call    cs:__guard_dispatch_icall_fptr
0x180038bef  test    eax, eax
0x180038bf1  jz      short loc_180038C1B
0x180038bf3  lea     rcx, [rsp+148h+var_60]; this
0x180038bfb  call    ??0SharedAssemblyIterator@SharedDomain@@QEAA@XZ; SharedDomain::SharedAssemblyIterator::SharedAssemblyIterator(void)
0x180038c00  lea     rcx, [rsp+148h+var_60]; this
0x180038c08  call    ?Next@SharedAssemblyIterator@SharedDomain@@QEAAHXZ; SharedDomain::SharedAssemblyIterator::Next(void)
0x180038c0d  test    eax, eax
0x180038c0f  jz      loc_180038FAC
0x180038c15  add     [rsi+3Ch], r12d
0x180038c19  jmp     short loc_180038C00
0x180038c1b  mov     r8b, r12b
0x180038c1e  mov     edx, 550h
0x180038c23  mov     rcx, rdi; unsigned __int64
0x180038c26  call    DacInstantiateClassByVTable
0x180038c2b  mov     r8, rax
0x180038c2e  mov     rcx, [rax]
0x180038c31  mov     rax, [rcx+8]
0x180038c35  mov     rcx, r8
0x180038c38  call    cs:__guard_dispatch_icall_fptr
0x180038c3e  test    eax, eax
0x180038c40  jz      loc_180038FAC
0x180038c46  mov     r8b, r12b
0x180038c49  mov     edx, 550h
0x180038c4e  mov     rcx, rdi; unsigned __int64
0x180038c51  call    DacInstantiateClassByVTable
0x180038c56  mov     r8, rax
0x180038c59  mov     rcx, [rax]
0x180038c5c  mov     rax, [rcx+20h]
0x180038c60  lea     rdx, [rsp+148h+var_128]
0x180038c65  mov     rcx, r8
0x180038c68  call    cs:__guard_dispatch_icall_fptr
0x180038c6e  mov     r8b, r12b
0x180038c71  mov     edx, 1030h
0x180038c76  mov     rcx, [rax]; unsigned __int64
0x180038c79  call    DacInstantiateClassByVTable
0x180038c7e  mov     r14, rax
0x180038c81  mov     rcx, [rsi]
0x180038c84  add     rcx, 10h
0x180038c88  mov     [rsi+28h], rcx
0x180038c8c  mov     rcx, [rax+18h]
0x180038c90  mov     [rsi+30h], rcx
0x180038c94  mov     ecx, [rax+8]
0x180038c97  mov     [rsi+38h], ecx
0x180038c9a  mov     ecx, [rax+0CA0h]
0x180038ca0  mov     [rsi+44h], ecx
0x180038ca3  mov     ecx, [rax+0CA0h]
0x180038ca9  sub     ecx, 2
0x180038cac  cmp     ecx, 9
0x180038caf  ja      short loc_180038CB6
0x180038cb1  mov     eax, r12d
0x180038cb4  jmp     short loc_180038CB9
0x180038cb6  mov     eax, r15d
0x180038cb9  test    eax, eax
0x180038cbb  jz      loc_180038F73
0x180038cc1  mov     [rsp+148h+var_D0], r14
0x180038cc6  mov     ecx, [r14+550h]
0x180038ccd  lea     rax, [r14+558h]
0x180038cd4  mov     qword ptr [rsp+148h+var_90], rax
0x180038cdc  or      dword ptr [rsp+148h+var_90+8], 0FFFFFFFFh
0x180038ce4  mov     dword ptr [rsp+148h+var_90+0Ch], ecx
0x180038ceb  mov     dword ptr [rsp+148h+var_80], r15d
0x180038cf3  movups  xmm0, [rsp+148h+var_90]
0x180038cfb  movups  [rsp+148h+var_C8], xmm0
0x180038d03  movsd   xmm1, [rsp+148h+var_80]
0x180038d0c  movsd   [rsp+148h+var_B8], xmm1
0x180038d15  mov     [rsp+148h+var_B0], 7
0x180038d20  mov     [rsp+148h+var_120], r15
0x180038d25  mov     edi, r15d
0x180038d28  mov     [rsp+148h+var_118], r15d
0x180038d2d  mov     rax, [rsp+148h+var_D0]
0x180038d32  add     rax, 1C0h
0x180038d38  mov     [rsp+148h+var_128], rax
0x180038d3d  lea     rcx, [rsp+148h+var_C8]; this
0x180038d45  call    ?Next@Iterator@ArrayListBase@@QEAAHXZ; ArrayListBase::Iterator::Next(void)
0x180038d4a  test    eax, eax
0x180038d4c  jz      loc_180038EEC
0x180038d52  mov     eax, dword ptr [rsp+148h+var_C8+8]
0x180038d59  mov     rcx, qword ptr [rsp+148h+var_C8]
0x180038d61  mov     rcx, [rcx+rax*8+10h]; unsigned __int64
0x180038d66  mov     [rsp+148h+var_128], rcx
0x180038d6b  mov     r8b, r12b
0x180038d6e  mov     edx, 0F0h
0x180038d73  call    DacInstantiateClassByVTable
0x180038d78  mov     rbx, rax
0x180038d7b  test    rax, rax
0x180038d7e  jnz     short loc_180038D82
0x180038d80  jmp     short loc_180038D3D
0x180038d82  cmp     [rax+38h], r15
0x180038d86  jz      short loc_180038DB0
0x180038d88  test    byte ptr [rsp+148h+var_B0], 10h
0x180038d90  jz      short loc_180038D80
0x180038d92  test    edi, edi
0x180038d94  jz      short loc_180038D9B
0x180038d96  mov     [rsp+148h+var_118], r15d
0x180038d9b  mov     [rsp+148h+var_120], rbx
0x180038da0  mov     edi, r12d
0x180038da3  mov     [rsp+148h+var_118], r12d
0x180038da8  mov     eax, r12d
0x180038dab  jmp     loc_180038F03
0x180038db0  test    [rax+40h], r12b
0x180038db4  mov     eax, [rsp+148h+var_B0]
0x180038dbb  jz      short loc_180038DC1
0x180038dbd  test    al, 20h
0x180038dbf  jnz     short loc_180038DCC
0x180038dc1  cmp     dword ptr [rbx+28h], 0Bh
0x180038dc5  jl      short loc_180038DCE
0x180038dc7  test    r12b, al
0x180038dca  jz      short loc_180038D80
0x180038dcc  jmp     short loc_180038DD2
0x180038dce  test    al, 2
0x180038dd0  jz      short loc_180038D80
0x180038dd2  mov     r8b, r12b
0x180038dd5  mov     edx, 0C8h
0x180038dda  mov     rcx, [rbx+10h]; unsigned __int64
0x180038dde  call    DacInstantiateClassByVTable
0x180038de3  mov     rcx, rax
0x180038de6  mov     eax, [rax+70h]
0x180038de9  test    al, 4
0x180038deb  jz      short loc_180038E28
0x180038ded  mov     dl, r12b
0x180038df0  call    DacGetTargetAddrForHostAddr
0x180038df5  mov     [rsp+148h+var_128], rax
0x180038dfa  mov     r8b, r12b
0x180038dfd  mov     edx, 0D8h
0x180038e02  mov     rcx, rax; unsigned __int64
0x180038e05  call    DacInstantiateClassByVTable
0x180038e0a  mov     r8b, r12b
0x180038e0d  mov     edx, 118h
0x180038e12  mov     rcx, [rax+0C8h]; unsigned __int64
0x180038e19  call    DacInstantiateClassByVTable
0x180038e1e  mov     rcx, rax; this
0x180038e21  call    ?IsIntrospectionOnly@PEFile@@QEBAHXZ; PEFile::IsIntrospectionOnly(void)
0x180038e26  jmp     short loc_180038E2E
0x180038e28  shr     eax, 0Ah
0x180038e2b  and     eax, r12d
0x180038e2e  test    eax, eax
0x180038e30  mov     eax, [rsp+148h+var_B0]
0x180038e37  jz      short loc_180038E43
0x180038e39  test    al, 8
0x180038e3b  jz      loc_180038D80
0x180038e41  jmp     short loc_180038E4B
0x180038e43  test    al, 4
0x180038e45  jz      loc_180038D80
0x180038e4b  cmp     [rbx+0E8h], r15d
0x180038e52  jz      loc_180038EE7
0x180038e58  test    al, 40h
0x180038e5a  jnz     loc_180038D80
0x180038e60  mov     r9b, r12b; bool
0x180038e63  mov     r8b, r12b; bool
0x180038e66  mov     edx, 118h; unsigned int
0x180038e6b  mov     rcx, [rbx+78h]; unsigned __int64
0x180038e6f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180038e74  mov     r8b, r12b
0x180038e77  mov     edx, 628h
0x180038e7c  mov     rcx, [rax+58h]; unsigned __int64
0x180038e80  call    DacInstantiateClassByVTable
0x180038e85  test    [rax+20h], r12b
0x180038e89  jz      loc_180038D80
0x180038e8f  mov     rcx, rbx; this
0x180038e92  call    ?GetLoaderAllocator@DomainFile@@QEAAPEAVLoaderAllocator@@XZ; DomainFile::GetLoaderAllocator(void)
0x180038e97  cmp     [rax+300h], r15d
0x180038e9e  jz      short loc_180038EC3
0x180038ea0  test    edi, edi
0x180038ea2  jz      short loc_180038EA9
0x180038ea4  mov     [rsp+148h+var_118], r15d
0x180038ea9  mov     [rsp+148h+var_120], rbx
0x180038eae  mov     edi, r12d
0x180038eb1  mov     [rsp+148h+var_118], r12d
0x180038eb6  mov     rcx, rbx; this
0x180038eb9  call    ?GetLoaderAllocator@DomainFile@@QEAAPEAVLoaderAllocator@@XZ; DomainFile::GetLoaderAllocator(void)
0x180038ebe  jmp     loc_180038DA8
0x180038ec3  test    byte ptr [rsp+148h+var_B0], 80h
0x180038ecb  jz      loc_180038D80
0x180038ed1  test    edi, edi
0x180038ed3  jz      short loc_180038EDD
0x180038ed5  mov     edi, r15d
0x180038ed8  mov     [rsp+148h+var_118], r15d
0x180038edd  mov     [rsp+148h+var_120], rbx
0x180038ee2  jmp     loc_180038DA8
0x180038ee7  jmp     loc_180038D92
0x180038eec  test    edi, edi
0x180038eee  jz      short loc_180038EF8
0x180038ef0  mov     edi, r15d
0x180038ef3  mov     [rsp+148h+var_118], r15d
0x180038ef8  mov     rbx, r15
0x180038efb  mov     [rsp+148h+var_120], rbx
0x180038f00  mov     eax, r15d
0x180038f03  test    eax, eax
0x180038f05  jz      short loc_180038F16
0x180038f07  cmp     dword ptr [rbx+28h], 0Bh
0x180038f0b  jl      short loc_180038F11
0x180038f0d  add     [rsi+3Ch], r12d
0x180038f11  jmp     loc_180038D2D
0x180038f16  mov     ecx, [r14+0CF8h]
0x180038f1d  lea     rax, [r14+0D00h]
0x180038f24  mov     qword ptr [rsp+148h+var_F8], rax
0x180038f29  or      dword ptr [rsp+148h+var_F8+8], 0FFFFFFFFh
0x180038f2e  mov     dword ptr [rsp+148h+var_F8+0Ch], ecx
0x180038f32  mov     dword ptr [rsp+148h+var_E8], r15d
0x180038f37  movups  xmm0, [rsp+148h+var_F8]
0x180038f3c  movups  [rsp+148h+var_60], xmm0
0x180038f44  movsd   xmm1, [rsp+148h+var_E8]
0x180038f4a  movsd   [rsp+148h+var_50], xmm1
  ... truncated ...
```
