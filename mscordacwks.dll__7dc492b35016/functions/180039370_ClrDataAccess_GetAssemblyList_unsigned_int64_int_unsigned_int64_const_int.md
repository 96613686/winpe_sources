# ClrDataAccess::GetAssemblyList(unsigned __int64,int,unsigned __int64 * const,int *)

- ea: `0x180039370`
- end: `0x1800399d1`
- name: `?GetAssemblyList@ClrDataAccess@@UEAAJ_KHQEA_KPEAH@Z`
- size: `1633`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, int, unsigned __int64 *const, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000bd18`
- `0x18000c170`
- `0x18000c4fc`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180039370`
- `0x180074af0`
- `0x18009752c`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800393b3`
- `KERNEL32!EnterCriticalSection` at `0x1800393b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800399ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800399ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ClrDataAccess::GetAssemblyList(
        ClrDataAccess *this,
        unsigned __int64 a2,
        int a3,
        unsigned __int64 *const a4,
        int *a5)
{
  unsigned int v9; // ebx
  ClrDataAccess *v11; // r13
  __int64 *v12; // rdi
  int v13; // r12d
  __int64 v14; // rdx
  unsigned __int64 *v15; // rax
  int v16; // ecx
  int v17; // esi
  __int64 *v18; // rax
  __int64 *v19; // rdi
  int v20; // eax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  unsigned int v23; // eax
  __int64 *v24; // rax
  __int64 *v25; // rax
  int IsIntrospectionOnly; // eax
  _QWORD *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rax
  __int64 *v30; // rdi
  int v31; // eax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  unsigned int v34; // eax
  __int64 *v35; // rax
  __int64 *v36; // rax
  int v37; // eax
  _QWORD *v38; // rax
  struct Exception *v39; // rbx
  BOOL v40; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v42; // rcx
  __int64 *TargetAddrForHostAddr; // [rsp+38h] [rbp-B0h] BYREF
  __int64 *v44; // [rsp+40h] [rbp-A8h]
  __int128 v45; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-90h]
  int v47; // [rsp+60h] [rbp-88h]
  __int128 v48; // [rsp+68h] [rbp-80h] BYREF
  __int64 v49; // [rsp+78h] [rbp-70h]
  __int64 v50; // [rsp+80h] [rbp-68h]
  ClrDataAccess *v51; // [rsp+88h] [rbp-60h]
  ClrDataAccess *v52; // [rsp+90h] [rbp-58h]
  void *v53; // [rsp+98h] [rbp-50h]
  int v54; // [rsp+A0h] [rbp-48h]
  struct Exception *v55; // [rsp+B0h] [rbp-38h]
  struct Exception *v56; // [rsp+B8h] [rbp-30h] BYREF
  unsigned int v58; // [rsp+F8h] [rbp+10h] BYREF

  v9 = 0;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v11 = g_dacImpl;
  v51 = g_dacImpl;
  v52 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v58 = 0;
  v55 = 0;
  try
  {
    try
    {
      TargetAddrForHostAddr = (__int64 *)a2;
      v12 = DacInstantiateClassByVTable(a2, 1360, 1);
      v13 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64 *))(*v12 + 16))(v12) )
      {
        SharedDomain::SharedAssemblyIterator::SharedAssemblyIterator((SharedDomain::SharedAssemblyIterator *)&v48);
        if ( a4 )
        {
          while ( (unsigned int)SharedDomain::SharedAssemblyIterator::Next((SharedDomain::SharedAssemblyIterator *)&v48)
               && v13 < a3 )
          {
            LOBYTE(v14) = 1;
            a4[v13++] = DacGetTargetAddrForHostAddr(v50, v14);
          }
        }
        else
        {
          while ( (unsigned int)SharedDomain::SharedAssemblyIterator::Next((SharedDomain::SharedAssemblyIterator *)&v48) )
            ++v13;
        }
        if ( a5 )
          *a5 = v13;
        goto LABEL_106;
      }
      if ( (*(unsigned int (__fastcall **)(__int64 *))(*v12 + 8))(v12) )
      {
        v15 = (unsigned __int64 *)(*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v12 + 32))(
                                    v12,
                                    &TargetAddrForHostAddr);
        v44 = DacInstantiateClassByVTable(*v15, 4144, 1);
        v16 = *((_DWORD *)v44 + 340);
        *(_QWORD *)&v48 = v44 + 171;
        DWORD2(v48) = -1;
        HIDWORD(v48) = v16;
        LODWORD(v49) = 0;
        v45 = v48;
        v46 = v49;
        v47 = 7;
        v17 = 0;
        if ( a4 )
        {
LABEL_15:
          TargetAddrForHostAddr = v44 + 56;
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                do
                {
                  if ( !(unsigned int)ArrayListBase::Iterator::Next((ArrayListBase::Iterator *)&v45) )
                  {
                    if ( v17 )
                      v17 = 0;
                    v19 = 0;
                    v20 = 0;
LABEL_46:
                    if ( v20 && v13 < a3 )
                    {
                      if ( *((int *)v19 + 10) >= 11 )
                      {
                        v53 = DacInstantiateTypeByAddressHelper(v19[15], 0x118u, 1, 1);
                        v54 = 0;
                        LOBYTE(v28) = 1;
                        a4[v13++] = DacGetTargetAddrForHostAddr(v53, v28);
                      }
                      goto LABEL_15;
                    }
LABEL_84:
                    if ( a5 )
                      *a5 = v13;
                    v11 = v51;
                    goto LABEL_106;
                  }
                  TargetAddrForHostAddr = *(__int64 **)(v45 + 8LL * DWORD2(v45) + 16);
                  v18 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 240, 1);
                  v19 = v18;
                }
                while ( !v18 );
                if ( !v18[7] )
                  break;
                if ( (v47 & 0x10) != 0 )
                  goto LABEL_20;
              }
              if ( (v18[8] & 1) != 0 && (v47 & 0x20) != 0 )
                goto LABEL_28;
              if ( *((int *)v18 + 10) < 11 )
                break;
              if ( (v47 & 1) != 0 )
                goto LABEL_28;
            }
            if ( (v47 & 2) != 0 )
            {
LABEL_28:
              v22 = DacInstantiateClassByVTable(v18[2], 200, 1);
              v23 = *((_DWORD *)v22 + 28);
              if ( (v23 & 4) != 0 )
              {
                LOBYTE(v21) = 1;
                TargetAddrForHostAddr = (__int64 *)DacGetTargetAddrForHostAddr(v22, v21);
                v24 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 216, 1);
                v25 = DacInstantiateClassByVTable(v24[25], 280, 1);
                IsIntrospectionOnly = PEFile::IsIntrospectionOnly((PEFile *)v25);
              }
              else
              {
                IsIntrospectionOnly = (v23 >> 10) & 1;
              }
              if ( IsIntrospectionOnly )
              {
                if ( (v47 & 8) != 0 )
                {
LABEL_35:
                  if ( !*((_DWORD *)v19 + 58) )
                  {
LABEL_20:
                    v17 = 1;
LABEL_21:
                    v20 = 1;
                    goto LABEL_46;
                  }
                  if ( (v47 & 0x40) == 0 )
                  {
                    v27 = DacInstantiateTypeByAddressHelper(v19[15], 0x118u, 1, 1);
                    if ( (DacInstantiateClassByVTable(v27[11], 1576, 1)[4] & 1) != 0 )
                    {
                      if ( *((_DWORD *)DomainFile::GetLoaderAllocator((DomainFile *)v19) + 192) )
                      {
                        v17 = 1;
                        DomainFile::GetLoaderAllocator((DomainFile *)v19);
                        goto LABEL_21;
                      }
                      if ( (v47 & 0x80u) != 0 )
                      {
                        if ( v17 )
                          v17 = 0;
                        goto LABEL_21;
                      }
                    }
                  }
                }
              }
              else if ( (v47 & 4) != 0 )
              {
                goto LABEL_35;
              }
            }
          }
        }
LABEL_50:
        TargetAddrForHostAddr = v44 + 56;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              do
              {
                if ( !(unsigned int)ArrayListBase::Iterator::Next((ArrayListBase::Iterator *)&v45) )
                {
                  if ( v17 )
                    v17 = 0;
                  v30 = 0;
                  v31 = 0;
                  goto LABEL_81;
                }
                TargetAddrForHostAddr = *(__int64 **)(v45 + 8LL * DWORD2(v45) + 16);
                v29 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 240, 1);
                v30 = v29;
              }
              while ( !v29 );
              if ( !v29[7] )
                break;
              if ( (v47 & 0x10) != 0 )
                goto LABEL_55;
            }
            if ( (v29[8] & 1) != 0 && (v47 & 0x20) != 0 )
              goto LABEL_63;
            if ( *((int *)v29 + 10) < 11 )
              break;
            if ( (v47 & 1) != 0 )
              goto LABEL_63;
          }
          if ( (v47 & 2) != 0 )
          {
LABEL_63:
            v33 = DacInstantiateClassByVTable(v29[2], 200, 1);
            v34 = *((_DWORD *)v33 + 28);
            if ( (v34 & 4) != 0 )
            {
              LOBYTE(v32) = 1;
              TargetAddrForHostAddr = (__int64 *)DacGetTargetAddrForHostAddr(v33, v32);
              v35 = DacInstantiateClassByVTable((unsigned __int64)TargetAddrForHostAddr, 216, 1);
              v36 = DacInstantiateClassByVTable(v35[25], 280, 1);
              v37 = PEFile::IsIntrospectionOnly((PEFile *)v36);
            }
            else
            {
              v37 = (v34 >> 10) & 1;
            }
            if ( v37 )
            {
              if ( (v47 & 8) != 0 )
              {
LABEL_70:
                if ( !*((_DWORD *)v30 + 58) )
                {
LABEL_55:
                  v17 = 1;
                  goto LABEL_56;
                }
                if ( (v47 & 0x40) == 0 )
                {
                  v38 = DacInstantiateTypeByAddressHelper(v30[15], 0x118u, 1, 1);
                  if ( (DacInstantiateClassByVTable(v38[11], 1576, 1)[4] & 1) != 0 )
                  {
                    if ( *((_DWORD *)DomainFile::GetLoaderAllocator((DomainFile *)v30) + 192) )
                    {
                      v17 = 1;
                      DomainFile::GetLoaderAllocator((DomainFile *)v30);
                      goto LABEL_56;
                    }
                    if ( (v47 & 0x80u) != 0 )
                    {
                      if ( v17 )
                        v17 = 0;
LABEL_56:
                      v31 = 1;
LABEL_81:
                      if ( !v31 )
                        goto LABEL_84;
                      if ( *((int *)v30 + 10) >= 11 )
                        ++v13;
                      goto LABEL_50;
                    }
                  }
                }
              }
            }
            else if ( (v47 & 4) != 0 )
            {
              goto LABEL_70;
            }
          }
        }
      }
      v9 = -2147024809;
      v58 = -2147024809;
    }
    catch ( Exception *v56 )
    {
      v55 = v56;
      throw;
    }
  }
  catch ( ... )
  {
    *((_QWORD *)&v48 + 1) = 0;
    *(_QWORD *)&v48 = &DelegatingException::`vftable';
    v49 = -1;
    v39 = v55;
    v40 = v55 != 0;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v42 = (struct Exception *)&v48;
    if ( v39 )
      v42 = v39;
    if ( !DacExceptionFilter(v42, (ClrDataAccess *)((char *)this - 16), (int *)&v58) )
      throw;
    if ( v40 && v39 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v39 + 80LL))(v39) )
      (**(void (__fastcall ***)(struct Exception *, __int64))v39)(v39, 5);
    DelegatingException::~DelegatingException((DelegatingException *)&v48);
    v11 = v52;
    v9 = v58;
  }
LABEL_106:
  g_dacImpl = v11;
  LeaveCriticalSection(&g_dacCritSec);
  return v9;
}

```

## disassembly

```asm
0x180039370  mov     [rsp+arg_10], rbx
0x180039375  mov     [rsp+arg_18], rsi
0x18003937a  mov     [rsp+arg_0], rcx
0x18003937f  push    rdi
0x180039380  push    r12
0x180039382  push    r13
0x180039384  push    r14
0x180039386  push    r15
0x180039388  sub     rsp, 0C0h
0x18003938f  mov     r14, r9
0x180039392  mov     r15d, r8d
0x180039395  mov     rdi, rdx
0x180039398  mov     rsi, rcx
0x18003939b  xor     ebx, ebx
0x18003939d  test    rdx, rdx
0x1800393a0  jnz     short loc_1800393AC
0x1800393a2  mov     eax, 80070057h
0x1800393a7  jmp     loc_1800399B4
0x1800393ac  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800393b3  call    cs:__imp_EnterCriticalSection
0x1800393b9  mov     r13, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800393c0  mov     [rsp+0E8h+var_60], r13
0x1800393c8  mov     [rsp+0E8h+var_58], r13
0x1800393d0  lea     rax, [rsi-10h]
0x1800393d4  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x1800393db  mov     [rsp+0E8h+arg_8], ebx
0x1800393e2  mov     [rsp+0E8h+var_38], rbx
0x1800393ea  lea     rax, [rsp+0E8h+var_40]
0x1800393f2  mov     [rsp+0E8h+var_B0], rax
0x1800393f7  mov     [rsp+0E8h+var_B0], rdi
0x1800393fc  mov     esi, 1
0x180039401  mov     r8b, sil
0x180039404  mov     edx, 550h
0x180039409  mov     rcx, rdi; unsigned __int64
0x18003940c  call    DacInstantiateClassByVTable
0x180039411  mov     rdi, rax
0x180039414  mov     r12d, ebx
0x180039417  mov     [rsp+0E8h+var_B8], ebx
0x18003941b  mov     rax, [rax]
0x18003941e  mov     rcx, rdi
0x180039421  mov     rax, [rax+10h]
0x180039425  call    cs:__guard_dispatch_icall_fptr
0x18003942b  test    eax, eax
0x18003942d  jz      short loc_1800394A6
0x18003942f  lea     rcx, [rsp+0E8h+var_80]; this
0x180039434  call    ??0SharedAssemblyIterator@SharedDomain@@QEAA@XZ; SharedDomain::SharedAssemblyIterator::SharedAssemblyIterator(void)
0x180039439  test    r14, r14
0x18003943c  jz      short loc_180039475
0x18003943e  lea     rcx, [rsp+0E8h+var_80]; this
0x180039443  call    ?Next@SharedAssemblyIterator@SharedDomain@@QEAAHXZ; SharedDomain::SharedAssemblyIterator::Next(void)
0x180039448  test    eax, eax
0x18003944a  jz      short loc_18003948D
0x18003944c  cmp     r12d, r15d
0x18003944f  jge     short loc_18003948D
0x180039451  mov     dl, sil
0x180039454  mov     rcx, [rsp+0E8h+var_68]
0x18003945c  call    DacGetTargetAddrForHostAddr
0x180039461  mov     rcx, rax
0x180039464  movsxd  rax, r12d
0x180039467  mov     [r14+rax*8], rcx
0x18003946b  add     r12d, esi
0x18003946e  mov     [rsp+0E8h+var_B8], r12d
0x180039473  jmp     short loc_18003943E
0x180039475  lea     rcx, [rsp+0E8h+var_80]; this
0x18003947a  call    ?Next@SharedAssemblyIterator@SharedDomain@@QEAAHXZ; SharedDomain::SharedAssemblyIterator::Next(void)
0x18003947f  test    eax, eax
0x180039481  jz      short loc_18003948D
0x180039483  add     r12d, esi
0x180039486  mov     [rsp+0E8h+var_B8], r12d
0x18003948b  jmp     short loc_180039475
0x18003948d  mov     rax, [rsp+0E8h+arg_20]
0x180039495  test    rax, rax
0x180039498  jz      loc_18003998D
0x18003949e  mov     [rax], r12d
0x1800394a1  jmp     loc_18003998D
0x1800394a6  mov     rax, [rdi]
0x1800394a9  mov     rcx, rdi
0x1800394ac  mov     rax, [rax+8]
0x1800394b0  call    cs:__guard_dispatch_icall_fptr
0x1800394b6  test    eax, eax
0x1800394b8  jz      loc_180039981
0x1800394be  mov     rax, [rdi]
0x1800394c1  lea     rdx, [rsp+0E8h+var_B0]
0x1800394c6  mov     rcx, rdi
0x1800394c9  mov     rax, [rax+20h]
0x1800394cd  call    cs:__guard_dispatch_icall_fptr
0x1800394d3  mov     r8b, sil
0x1800394d6  mov     edx, 1030h
0x1800394db  mov     rcx, [rax]; unsigned __int64
0x1800394de  call    DacInstantiateClassByVTable
0x1800394e3  mov     [rsp+0E8h+var_A8], rax
0x1800394e8  mov     ecx, [rax+550h]
0x1800394ee  add     rax, 558h
0x1800394f4  mov     qword ptr [rsp+0E8h+var_80], rax
0x1800394f9  or      dword ptr [rsp+0E8h+var_80+8], 0FFFFFFFFh
0x1800394fe  mov     dword ptr [rsp+0E8h+var_80+0Ch], ecx
0x180039502  mov     dword ptr [rsp+0E8h+var_70], ebx
0x180039506  movups  xmm0, [rsp+0E8h+var_80]
0x18003950b  movups  [rsp+0E8h+var_A0], xmm0
0x180039510  movsd   xmm1, [rsp+0E8h+var_70]
0x180039516  movsd   [rsp+0E8h+var_90], xmm1
0x18003951c  mov     [rsp+0E8h+var_88], 7
0x180039524  mov     [rsp+0E8h+var_C8], rbx
0x180039529  mov     esi, ebx
0x18003952b  mov     [rsp+0E8h+var_C0], ebx
0x18003952f  mov     r13d, 118h
0x180039535  test    r14, r14
0x180039538  jz      loc_18003978E
0x18003953e  mov     rax, [rsp+0E8h+var_A8]
0x180039543  add     rax, 1C0h
0x180039549  mov     [rsp+0E8h+var_B0], rax
0x18003954e  lea     rcx, [rsp+0E8h+var_A0]; this
0x180039553  call    ?Next@Iterator@ArrayListBase@@QEAAHXZ; ArrayListBase::Iterator::Next(void)
0x180039558  test    eax, eax
0x18003955a  jz      loc_180039700
0x180039560  mov     eax, dword ptr [rsp+0E8h+var_A0+8]
0x180039564  mov     rcx, qword ptr [rsp+0E8h+var_A0]
0x180039569  mov     rcx, [rcx+rax*8+10h]; unsigned __int64
0x18003956e  mov     [rsp+0E8h+var_B0], rcx
0x180039573  mov     r8b, 1
0x180039576  mov     edx, 0F0h
0x18003957b  call    DacInstantiateClassByVTable
0x180039580  mov     rdi, rax
0x180039583  test    rax, rax
0x180039586  jnz     short loc_18003958A
0x180039588  jmp     short loc_18003954E
0x18003958a  cmp     [rax+38h], rbx
0x18003958e  jz      short loc_1800395B6
0x180039590  test    byte ptr [rsp+0E8h+var_88], 10h
0x180039595  jz      short loc_180039588
0x180039597  test    esi, esi
0x180039599  jz      short loc_18003959F
0x18003959b  mov     [rsp+0E8h+var_C0], ebx
0x18003959f  mov     [rsp+0E8h+var_C8], rdi
0x1800395a4  mov     ecx, 1
0x1800395a9  mov     esi, ecx
0x1800395ab  mov     [rsp+0E8h+var_C0], ecx
0x1800395af  mov     eax, ecx
0x1800395b1  jmp     loc_180039719
0x1800395b6  mov     ecx, 1
0x1800395bb  test    [rax+40h], cl
0x1800395be  mov     eax, [rsp+0E8h+var_88]
0x1800395c2  jz      short loc_1800395C8
0x1800395c4  test    al, 20h
0x1800395c6  jnz     short loc_1800395D2
0x1800395c8  cmp     dword ptr [rdi+28h], 0Bh
0x1800395cc  jl      short loc_1800395D4
0x1800395ce  test    cl, al
0x1800395d0  jz      short loc_180039588
0x1800395d2  jmp     short loc_1800395D8
0x1800395d4  test    al, 2
0x1800395d6  jz      short loc_180039588
0x1800395d8  mov     r8b, cl
0x1800395db  mov     edx, 0C8h
0x1800395e0  mov     rcx, [rdi+10h]; unsigned __int64
0x1800395e4  call    DacInstantiateClassByVTable
0x1800395e9  mov     rcx, rax
0x1800395ec  mov     eax, [rax+70h]
0x1800395ef  test    al, 4
0x1800395f1  jz      short loc_180039630
0x1800395f3  mov     dl, 1
0x1800395f5  call    DacGetTargetAddrForHostAddr
0x1800395fa  mov     [rsp+0E8h+var_B0], rax
0x1800395ff  mov     r8b, 1
0x180039602  mov     edx, 0D8h
0x180039607  mov     rcx, rax; unsigned __int64
0x18003960a  call    DacInstantiateClassByVTable
0x18003960f  mov     r8b, 1
0x180039612  mov     edx, r13d
0x180039615  mov     rcx, [rax+0C8h]; unsigned __int64
0x18003961c  call    DacInstantiateClassByVTable
0x180039621  mov     rcx, rax; this
0x180039624  call    ?IsIntrospectionOnly@PEFile@@QEBAHXZ; PEFile::IsIntrospectionOnly(void)
0x180039629  mov     ecx, 1
0x18003962e  jmp     short loc_18003963A
0x180039630  shr     eax, 0Ah
0x180039633  mov     ecx, 1
0x180039638  and     eax, ecx
0x18003963a  test    eax, eax
0x18003963c  mov     eax, [rsp+0E8h+var_88]
0x180039640  jz      short loc_18003964C
0x180039642  test    al, 8
0x180039644  jz      loc_180039588
0x18003964a  jmp     short loc_180039654
0x18003964c  test    al, 4
0x18003964e  jz      loc_180039588
0x180039654  cmp     [rdi+0E8h], ebx
0x18003965a  jz      loc_1800396EE
0x180039660  test    al, 40h
0x180039662  jnz     loc_180039588
0x180039668  mov     r9b, cl; bool
0x18003966b  mov     r8b, cl; bool
0x18003966e  mov     edx, r13d; unsigned int
0x180039671  mov     rcx, [rdi+78h]; unsigned __int64
0x180039675  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003967a  mov     r8b, 1
0x18003967d  mov     edx, 628h
0x180039682  mov     rcx, [rax+58h]; unsigned __int64
0x180039686  call    DacInstantiateClassByVTable
0x18003968b  test    byte ptr [rax+20h], 1
0x18003968f  jz      loc_180039588
0x180039695  mov     rcx, rdi; this
0x180039698  call    ?GetLoaderAllocator@DomainFile@@QEAAPEAVLoaderAllocator@@XZ; DomainFile::GetLoaderAllocator(void)
0x18003969d  cmp     [rax+300h], ebx
0x1800396a3  jz      short loc_1800396CA
0x1800396a5  test    esi, esi
0x1800396a7  jz      short loc_1800396AD
0x1800396a9  mov     [rsp+0E8h+var_C0], ebx
0x1800396ad  mov     [rsp+0E8h+var_C8], rdi
0x1800396b2  mov     esi, 1
0x1800396b7  mov     [rsp+0E8h+var_C0], esi
0x1800396bb  mov     rcx, rdi; this
0x1800396be  call    ?GetLoaderAllocator@DomainFile@@QEAAPEAVLoaderAllocator@@XZ; DomainFile::GetLoaderAllocator(void)
0x1800396c3  mov     ecx, esi
0x1800396c5  jmp     loc_1800395AF
0x1800396ca  test    byte ptr [rsp+0E8h+var_88], 80h
0x1800396cf  jz      loc_180039588
0x1800396d5  test    esi, esi
0x1800396d7  jz      short loc_1800396DF
0x1800396d9  mov     esi, ebx
0x1800396db  mov     [rsp+0E8h+var_C0], ebx
0x1800396df  mov     [rsp+0E8h+var_C8], rdi
0x1800396e4  mov     ecx, 1
0x1800396e9  jmp     loc_1800395AF
0x1800396ee  test    esi, esi
0x1800396f0  jz      short loc_1800396F6
0x1800396f2  mov     [rsp+0E8h+var_C0], ebx
0x1800396f6  mov     [rsp+0E8h+var_C8], rdi
0x1800396fb  jmp     loc_1800395A9
0x180039700  test    esi, esi
0x180039702  jz      short loc_18003970A
0x180039704  mov     esi, ebx
0x180039706  mov     [rsp+0E8h+var_C0], ebx
0x18003970a  mov     rdi, rbx
0x18003970d  mov     [rsp+0E8h+var_C8], rbx
0x180039712  mov     eax, ebx
0x180039714  mov     ecx, 1
0x180039719  test    eax, eax
0x18003971b  jz      loc_18003995F
0x180039721  cmp     r12d, r15d
0x180039724  jge     loc_18003995F
0x18003972a  cmp     dword ptr [rdi+28h], 0Bh
0x18003972e  jl      short loc_180039789
0x180039730  mov     r9b, cl; bool
0x180039733  mov     r8b, cl; bool
0x180039736  mov     edx, r13d; unsigned int
0x180039739  mov     rcx, [rdi+78h]; unsigned __int64
0x18003973d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180039742  mov     rcx, rax
0x180039745  mov     [rsp+0E8h+var_50], rax
0x18003974d  mov     [rsp+0E8h+var_48], ebx
0x180039754  mov     eax, ebx
0x180039756  test    rcx, rcx
0x180039759  mov     edi, 1
0x18003975e  cmovnz  eax, edi
0x180039761  mov     [rsp+0E8h+var_48], eax
0x180039768  mov     [rsp+0E8h+var_48], ebx
0x18003976f  mov     dl, dil
0x180039772  call    DacGetTargetAddrForHostAddr
0x180039777  mov     rcx, rax
0x18003977a  movsxd  rax, r12d
0x18003977d  mov     [r14+rax*8], rcx
0x180039781  add     r12d, edi
0x180039784  mov     [rsp+0E8h+var_B8], r12d
0x180039789  jmp     loc_18003953E
0x18003978e  mov     rax, [rsp+0E8h+var_A8]
0x180039793  add     rax, 1C0h
0x180039799  mov     [rsp+0E8h+var_B0], rax
0x18003979e  mov     r14d, 1
0x1800397a4  lea     rcx, [rsp+0E8h+var_A0]; this
0x1800397a9  call    ?Next@Iterator@ArrayListBase@@QEAAHXZ; ArrayListBase::Iterator::Next(void)
0x1800397ae  test    eax, eax
0x1800397b0  jz      loc_180039934
0x1800397b6  mov     eax, dword ptr [rsp+0E8h+var_A0+8]
0x1800397ba  mov     rcx, qword ptr [rsp+0E8h+var_A0]
0x1800397bf  mov     rcx, [rcx+rax*8+10h]; unsigned __int64
0x1800397c4  mov     [rsp+0E8h+var_B0], rcx
0x1800397c9  mov     r8b, r14b
0x1800397cc  mov     edx, 0F0h
0x1800397d1  call    DacInstantiateClassByVTable
0x1800397d6  mov     rdi, rax
0x1800397d9  test    rax, rax
0x1800397dc  jnz     short loc_1800397E0
0x1800397de  jmp     short loc_1800397A4
0x1800397e0  cmp     [rax+38h], rbx
0x1800397e4  jz      short loc_18003980A
0x1800397e6  test    byte ptr [rsp+0E8h+var_88], 10h
0x1800397eb  jz      short loc_1800397DE
0x1800397ed  test    esi, esi
0x1800397ef  jz      short loc_1800397F5
0x1800397f1  mov     [rsp+0E8h+var_C0], ebx
0x1800397f5  mov     [rsp+0E8h+var_C8], rdi
0x1800397fa  mov     esi, r14d
0x1800397fd  mov     [rsp+0E8h+var_C0], r14d
0x180039802  mov     eax, r14d
0x180039805  jmp     loc_180039948
0x18003980a  test    [rax+40h], r14b
0x18003980e  mov     eax, [rsp+0E8h+var_88]
0x180039812  jz      short loc_180039818
0x180039814  test    al, 20h
  ... truncated ...
```
