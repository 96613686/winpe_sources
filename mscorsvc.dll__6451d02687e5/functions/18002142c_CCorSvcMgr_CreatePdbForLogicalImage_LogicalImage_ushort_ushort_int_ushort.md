# CCorSvcMgr::CreatePdbForLogicalImage(LogicalImage *,ushort *,ushort *,int,ushort *)

- ea: `0x18002142c`
- end: `0x18002180e`
- name: `?CreatePdbForLogicalImage@CCorSvcMgr@@AEAAJPEAVLogicalImage@@PEAG1H1@Z`
- size: `994`
- prototype: `__int64 __fastcall(CCorSvcMgr *this, struct Configuration **, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180020480`

## callees

- `0x1800093d8`
- `0x180020df0`
- `0x18002142c`
- `0x180021810`
- `0x18002225c`
- `0x180022344`
- `0x180025110`
- `0x1800289bc`
- `0x18002c5a0`
- `0x18002d3c0`
- `0x18002d624`
- `0x180030d84`
- `0x180034fd4`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180021601`
- `KERNEL32!EnterCriticalSection` at `0x18002174e`
- `KERNEL32!EnterCriticalSection` at `0x180021601`
- `KERNEL32!EnterCriticalSection` at `0x18002174e`
- `KERNEL32!LeaveCriticalSection` at `0x1800216ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800217a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800216ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800217a5`
- `OLEAUT32!__imp_SysAllocString` at `0x180021653`
- `OLEAUT32!__imp_SysAllocString` at `0x180021690`
- `OLEAUT32!__imp_SysAllocString` at `0x180021653`
- `OLEAUT32!__imp_SysAllocString` at `0x180021690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800215ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18002175d`
- `OLEAUT32!__imp_SysFreeString` at `0x180021774`
- `OLEAUT32!__imp_SysFreeString` at `0x1800215ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18002175d`
- `OLEAUT32!__imp_SysFreeString` at `0x180021774`

## pseudocode

```c
__int64 __fastcall CCorSvcMgr::CreatePdbForLogicalImage(
        CCorSvcMgr *this,
        struct Configuration **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        unsigned __int16 *a6)
{
  int v9; // r12d
  BSTR v10; // rsi
  int RuntimeVersionFromNativeHeader; // eax
  int v12; // eax
  __int64 v13; // r8
  CCorSvcMgr *v14; // rcx
  int v15; // eax
  struct CCorSvcMgr::WorkerPoolItem *SvcWorkerForConfiguration; // rsi
  BOOL v17; // r14d
  int v18; // eax
  int v19; // r12d
  const OLECHAR *RootPath; // rax
  SString *v21; // rax
  const OLECHAR *v22; // rcx
  __int64 v23; // r9
  OLECHAR *v24; // r15
  OLECHAR *v25; // rdi
  int v26; // eax
  BSTR bstrString; // [rsp+60h] [rbp-61h] BYREF
  int v29; // [rsp+68h] [rbp-59h]
  SString *v30; // [rsp+70h] [rbp-51h]
  __int64 v31; // [rsp+78h] [rbp-49h] BYREF
  BSTR v32; // [rsp+80h] [rbp-41h]
  int v33; // [rsp+88h] [rbp-39h]
  BSTR v34; // [rsp+90h] [rbp-31h]
  int v35; // [rsp+98h] [rbp-29h]
  struct CCorSvcMgr::WorkerPoolItem *v36; // [rsp+A0h] [rbp-21h]
  BOOL v37; // [rsp+A8h] [rbp-19h]
  __int128 v38; // [rsp+B8h] [rbp-9h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp+7h]
  BSTR *p_bstrString; // [rsp+120h] [rbp+5Fh] BYREF
  unsigned __int16 *v41; // [rsp+128h] [rbp+67h]
  unsigned __int16 *v42; // [rsp+130h] [rbp+6Fh]

  v42 = a4;
  v41 = a3;
  v36 = 0;
  v37 = 0;
  v9 = 0;
  if ( a2 )
  {
    SvcWorkerForConfiguration = CCorSvcMgr::GetSvcWorkerForConfiguration(this, a2[1], 0, 0, 0);
    v36 = SvcWorkerForConfiguration;
    v17 = SvcWorkerForConfiguration != 0;
    v37 = v17;
  }
  else
  {
    v10 = (BSTR)*((_QWORD *)this + 37);
    bstrString = 0;
    v29 = 0;
    if ( !*((_QWORD *)this + 37) )
    {
      p_bstrString = &bstrString;
      bstrString = 0;
      RuntimeVersionFromNativeHeader = CCorSvcMgr::GetRuntimeVersionFromNativeHeader(this, a3, &bstrString);
      if ( RuntimeVersionFromNativeHeader < 0 )
        ThrowHR(RuntimeVersionFromNativeHeader);
      v12 = v29;
      v10 = bstrString;
      if ( bstrString )
        v12 = 1;
      v29 = v12;
    }
    v13 = *((_QWORD *)this + 39);
    if ( v13 && *((_QWORD *)this + 41) )
    {
      Logger::Printf(
        (CCorSvcMgr *)((char *)this + 208),
        L"Using explicitly specified package '%s' for NI '%s'.\n",
        v13,
        a3);
    }
    else
    {
      v15 = CCorSvcMgr::InferPackageInformation(this, a3);
      if ( v15 >= 0 )
        v9 = 1;
      else
        Logger::Printf(
          (CCorSvcMgr *)((char *)this + 208),
          L"Encountered failure '0x%x' while looking for package matching NI '%s'.  Proceeding without using a package.\n",
          (unsigned int)v15,
          a3);
    }
    if ( *((_QWORD *)this + 39) || *((_QWORD *)this + 41) )
    {
      if ( v9 )
      {
        LODWORD(p_bstrString) = 0;
        if ( (int)CCorSvcMgr::IsRunningAtHigherThanMediumIL(v14, (int *)&p_bstrString) >= 0 )
        {
          if ( (_DWORD)p_bstrString )
            CCorSvcMgr::RelaunchNgenPdbAsMediumILAndExitProcess(this);
        }
      }
    }
    v38 = *((_OWORD *)this + 17);
    SvcWorkerForConfiguration = (struct CCorSvcMgr::WorkerPoolItem *)CCorSvcMgr::GetPooledSvcWorker(
                                                                       this,
                                                                       *((_QWORD *)this + 162),
                                                                       (char *)this + 24,
                                                                       &v38,
                                                                       v10,
                                                                       0);
    v36 = SvcWorkerForConfiguration;
    v17 = SvcWorkerForConfiguration != 0;
    v37 = v17;
    if ( v29 )
    {
      SysFreeString(bstrString);
      v29 = 0;
    }
  }
  v39 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)SvcWorkerForConfiguration + 3);
  *(_QWORD *)&v38 = (char *)this + 152;
  BYTE8(v38) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  BYTE8(v38) = 1;
  v18 = *((_DWORD *)this + 316);
  if ( v18 < 0 && (!*((_DWORD *)this + 317) || v18 == -2147024784) )
    goto LABEL_48;
  v34 = 0;
  LODWORD(p_bstrString) = 0;
  v35 = 0;
  v32 = 0;
  v19 = 0;
  v33 = 0;
  if ( a2 )
  {
    RootPath = Configuration::GetRootPath(a2[1]);
    v34 = SysAllocString(RootPath);
    LODWORD(p_bstrString) = v34 != 0;
    v35 = (int)p_bstrString;
    v21 = a2[11];
    v30 = v21;
    if ( v21 )
    {
      SString::ConvertToUnicode(v21);
      v22 = (const OLECHAR *)*((_QWORD *)v30 + 2);
    }
    else
    {
      v22 = 0;
    }
    v32 = SysAllocString(v22);
    if ( v32 )
      v19 = 1;
    v33 = v19;
  }
  bstrString = (BSTR)((char *)this + 152);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v31 = 0;
  LODWORD(v30) = (**v39)(v39, &IID_ICorSvcWorker3, &v31);
  if ( (int)v30 < 0 )
  {
    v25 = v32;
    v24 = v34;
  }
  else
  {
    if ( a2 )
      v23 = *((unsigned int *)a2[1] + 6);
    else
      v23 = 0;
    v24 = v34;
    v25 = v32;
    LODWORD(v30) = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, __int64, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *))(*(_QWORD *)v31 + 80LL))(
                     v31,
                     v32,
                     v34,
                     v23,
                     v41,
                     v42,
                     a5,
                     a6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( v19 )
  {
    SysFreeString(v25);
    v33 = 0;
  }
  if ( (_DWORD)p_bstrString )
  {
    SysFreeString(v24);
    v35 = 0;
  }
  if ( (unsigned int)CCorSvcMgr::IsInterruptRequested(this) )
    ThrowHR(-2146230784);
  if ( (v26 = *((_DWORD *)this + 316), v26 < 0) && !*((_DWORD *)this + 317) || v26 == -2147024784 )
LABEL_48:
    ThrowHR(-2147467260);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( v17 )
  {
    CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(SvcWorkerForConfiguration);
    operator delete(SvcWorkerForConfiguration);
    v37 = 0;
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18002142c  mov     rax, rsp
0x18002142f  mov     [rax+8], rbx
0x180021433  mov     [rax+20h], r9
0x180021437  mov     [rax+18h], r8
0x18002143b  push    rbp
0x18002143c  push    rsi
0x18002143d  push    rdi
0x18002143e  push    r12
0x180021440  push    r13
0x180021442  push    r14
0x180021444  push    r15
0x180021446  lea     rbp, [rax-4Fh]
0x18002144a  sub     rsp, 0D0h
0x180021451  mov     r14, r8
0x180021454  mov     r15, rdx
0x180021457  mov     rbx, rcx
0x18002145a  xor     r13d, r13d
0x18002145d  mov     [rbp+47h+var_B0], r13d
0x180021461  mov     [rbp+47h+var_68], r13
0x180021465  mov     [rbp+47h+var_60], r13d
0x180021469  mov     r12d, r13d
0x18002146c  test    rdx, rdx
0x18002146f  jnz     loc_1800215B9
0x180021475  mov     rsi, [rcx+128h]
0x18002147c  mov     [rbp+47h+bstrString], r13
0x180021480  mov     [rbp+47h+var_A0], r13d
0x180021484  lea     edi, [rdx+1]
0x180021487  cmp     [rcx+128h], r13
0x18002148e  jnz     short loc_1800214CB
0x180021490  lea     rax, [rbp+47h+bstrString]
0x180021494  mov     [rbp+47h+arg_8], rax
0x180021498  mov     [rbp+47h+bstrString], r13
0x18002149c  mov     [rbp+47h+var_B0], edi
0x18002149f  lea     r8, [rbp+47h+bstrString]; unsigned __int16 **
0x1800214a3  mov     rdx, r14; unsigned __int16 *
0x1800214a6  call    ?GetRuntimeVersionFromNativeHeader@CCorSvcMgr@@AEAAJPEBGPEAPEAG@Z; CCorSvcMgr::GetRuntimeVersionFromNativeHeader(ushort const *,ushort * *)
0x1800214ab  test    eax, eax
0x1800214ad  js      loc_1800217F2
0x1800214b3  mov     eax, edi
0x1800214b5  and     eax, 0FFFFFFFEh
0x1800214b8  mov     [rbp+47h+var_B0], eax
0x1800214bb  mov     eax, [rbp+47h+var_A0]
0x1800214be  mov     rsi, [rbp+47h+bstrString]
0x1800214c2  test    rsi, rsi
0x1800214c5  cmovnz  eax, edi
0x1800214c8  mov     [rbp+47h+var_A0], eax
0x1800214cb  mov     r8, [rbx+138h]
0x1800214d2  test    r8, r8
0x1800214d5  jz      short loc_1800214F8
0x1800214d7  cmp     [rbx+148h], r13
0x1800214de  jz      short loc_1800214F8
0x1800214e0  lea     rcx, [rbx+0D0h]; this
0x1800214e7  mov     r9, r14
0x1800214ea  lea     rdx, aUsingExplicitl; "Using explicitly specified package '%s'"...
0x1800214f1  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x1800214f6  jmp     short loc_180021525
0x1800214f8  mov     rdx, r14; unsigned __int16 *
0x1800214fb  mov     rcx, rbx; this
0x1800214fe  call    ?InferPackageInformation@CCorSvcMgr@@AEAAJPEBG@Z; CCorSvcMgr::InferPackageInformation(ushort const *)
0x180021503  test    eax, eax
0x180021505  jns     short loc_180021522
0x180021507  lea     rcx, [rbx+0D0h]; this
0x18002150e  mov     r9, r14
0x180021511  mov     r8d, eax
0x180021514  lea     rdx, aEncounteredFai; "Encountered failure '0x%x' while lookin"...
0x18002151b  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x180021520  jmp     short loc_180021525
0x180021522  mov     r12d, edi
0x180021525  cmp     [rbx+138h], r13
0x18002152c  jnz     short loc_180021537
0x18002152e  cmp     [rbx+148h], r13
0x180021535  jz      short loc_180021557
0x180021537  test    r12d, r12d
0x18002153a  jz      short loc_180021557
0x18002153c  mov     dword ptr [rbp+47h+arg_8], r13d
0x180021540  lea     rdx, [rbp+47h+arg_8]; int *
0x180021544  call    ?IsRunningAtHigherThanMediumIL@CCorSvcMgr@@AEAAJPEAH@Z; CCorSvcMgr::IsRunningAtHigherThanMediumIL(int *)
0x180021549  test    eax, eax
0x18002154b  js      short loc_180021557
0x18002154d  cmp     dword ptr [rbp+47h+arg_8], r13d
0x180021551  jnz     loc_1800217FA
0x180021557  movups  xmm0, xmmword ptr [rbx+110h]
0x18002155e  movdqu  [rbp+47h+var_50], xmm0
0x180021563  lea     r8, [rbx+18h]
0x180021567  mov     [rsp+48h], r13
0x18002156c  mov     [rsp+38h], r13
0x180021571  mov     qword ptr [rsp+100h+var_D8], r13
0x180021576  mov     [rsp+100h+var_E0], rsi
0x18002157b  lea     r9, [rbp+47h+var_50]
0x18002157f  mov     rdx, [rbx+510h]
0x180021586  mov     rcx, rbx
0x180021589  call    ?GetPooledSvcWorker@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAXPEAUICorSvcLogger@@U_NGenPrivateAttributes@@PEBG3HPEAGW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@PEAVLogicalImage@@@Z; CCorSvcMgr::GetPooledSvcWorker(void *,ICorSvcLogger *,_NGenPrivateAttributes,ushort const *,ushort const *,int,ushort *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001,LogicalImage *)
0x18002158e  mov     rsi, rax
0x180021591  mov     [rbp+47h+var_68], rax
0x180021595  mov     r14d, r13d
0x180021598  test    rax, rax
0x18002159b  cmovnz  r14d, edi
0x18002159f  mov     [rbp+47h+var_60], r14d
0x1800215a3  cmp     [rbp+47h+var_A0], r13d
0x1800215a7  jz      short loc_1800215E7
0x1800215a9  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800215ad  call    cs:__imp_SysFreeString
0x1800215b3  mov     [rbp+47h+var_A0], r13d
0x1800215b7  jmp     short loc_1800215E7
0x1800215b9  mov     [rsp+100h+var_E0], r13; struct ICorSvcLogger *
0x1800215be  xor     r9d, r9d; struct LogicalImage *
0x1800215c1  xor     r8d, r8d; unsigned __int16 *
0x1800215c4  mov     rdx, [rdx+8]; struct Configuration *
0x1800215c8  call    ?GetSvcWorkerForConfiguration@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAVConfiguration@@PEBGPEAVLogicalImage@@PEAUICorSvcLogger@@@Z; CCorSvcMgr::GetSvcWorkerForConfiguration(Configuration *,ushort const *,LogicalImage *,ICorSvcLogger *)
0x1800215cd  mov     rsi, rax
0x1800215d0  mov     [rbp+47h+var_68], rax
0x1800215d4  mov     r14d, r13d
0x1800215d7  mov     edi, 1
0x1800215dc  test    rax, rax
0x1800215df  cmovnz  r14d, edi
0x1800215e3  mov     [rbp+47h+var_60], r14d
0x1800215e7  mov     rax, [rsi+18h]
0x1800215eb  mov     [rbp+47h+var_40], rax
0x1800215ef  lea     r13, [rbx+98h]
0x1800215f6  mov     qword ptr [rbp+47h+var_50], r13
0x1800215fa  mov     byte ptr [rbp+47h+var_50+8], 0
0x1800215fe  mov     rcx, r13; lpCriticalSection
0x180021601  call    cs:__imp_EnterCriticalSection
0x180021607  mov     byte ptr [rbp+47h+var_50+8], dil
0x18002160b  mov     eax, [rbx+4F0h]
0x180021611  xor     ecx, ecx
0x180021613  test    eax, eax
0x180021615  jns     short loc_18002162E
0x180021617  cmp     [rbx+4F4h], ecx
0x18002161d  jz      loc_1800217E7
0x180021623  cmp     eax, 80070070h
0x180021628  jz      loc_1800217E7
0x18002162e  mov     [rbp+47h+var_78], rcx
0x180021632  mov     dword ptr [rbp+47h+arg_8], ecx
0x180021635  mov     [rbp+47h+var_70], ecx
0x180021638  mov     [rbp+47h+var_88], rcx
0x18002163c  mov     r12d, ecx
0x18002163f  mov     [rbp+47h+var_80], ecx
0x180021642  test    r15, r15
0x180021645  jz      short loc_1800216A5
0x180021647  mov     rcx, [r15+8]; this
0x18002164b  call    ?GetRootPath@Configuration@@QEAAPEBGXZ; Configuration::GetRootPath(void)
0x180021650  mov     rcx, rax; psz
0x180021653  call    cs:__imp_SysAllocString
0x180021659  mov     rcx, rax
0x18002165c  mov     [rbp+47h+var_78], rax
0x180021660  mov     eax, r12d
0x180021663  test    rcx, rcx
0x180021666  cmovnz  eax, edi
0x180021669  mov     dword ptr [rbp+47h+arg_8], eax
0x18002166c  mov     [rbp+47h+var_70], eax
0x18002166f  mov     rax, [r15+58h]
0x180021673  mov     [rbp+47h+var_98], rax
0x180021677  test    rax, rax
0x18002167a  jnz     short loc_180021680
0x18002167c  xor     ecx, ecx
0x18002167e  jmp     short loc_180021690
0x180021680  mov     rcx, rax; this
0x180021683  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180021688  mov     rax, [rbp+47h+var_98]
0x18002168c  mov     rcx, [rax+10h]; psz
0x180021690  call    cs:__imp_SysAllocString
0x180021696  mov     [rbp+47h+var_88], rax
0x18002169a  test    rax, rax
0x18002169d  cmovnz  r12d, edi
0x1800216a1  mov     [rbp+47h+var_80], r12d
0x1800216a5  mov     [rbp+47h+bstrString], r13
0x1800216a9  mov     rcx, r13; lpCriticalSection
0x1800216ac  call    cs:__imp_LeaveCriticalSection
0x1800216b2  nop
0x1800216b3  and     [rbp+47h+var_90], 0
0x1800216b8  mov     rcx, [rbp+47h+var_40]
0x1800216bc  mov     rax, [rcx]
0x1800216bf  lea     r8, [rbp+47h+var_90]
0x1800216c3  lea     rdx, IID_ICorSvcWorker3
0x1800216ca  mov     rax, [rax]
0x1800216cd  call    cs:__guard_dispatch_icall_fptr
0x1800216d3  mov     dword ptr [rbp+47h+var_98], eax
0x1800216d6  test    eax, eax
0x1800216d8  js      short loc_180021743
0x1800216da  test    r15, r15
0x1800216dd  jnz     short loc_1800216E4
0x1800216df  xor     r9d, r9d
0x1800216e2  jmp     short loc_1800216EC
0x1800216e4  mov     rax, [r15+8]
0x1800216e8  mov     r9d, [rax+18h]
0x1800216ec  mov     rcx, [rbp+47h+var_90]
0x1800216f0  mov     rax, [rcx]
0x1800216f3  mov     rdx, [rbp+47h+arg_28]
0x1800216f7  mov     [rsp+38h], rdx
0x1800216fc  mov     edx, [rbp+47h+arg_20]
0x1800216ff  mov     dword ptr [rsp+100h+var_D0], edx
0x180021703  mov     rdx, [rbp+47h+arg_18]
0x180021707  mov     qword ptr [rsp+100h+var_D8], rdx
0x18002170c  mov     rdx, [rbp+47h+arg_10]
0x180021710  mov     [rsp+100h+var_E0], rdx
0x180021715  mov     r15, [rbp+47h+var_78]
0x180021719  mov     r8, r15
0x18002171c  mov     rdi, [rbp+47h+var_88]
0x180021720  mov     rdx, rdi
0x180021723  mov     rax, [rax+50h]
0x180021727  call    cs:__guard_dispatch_icall_fptr
0x18002172d  mov     dword ptr [rbp+47h+var_98], eax
0x180021730  mov     rcx, [rbp+47h+var_90]
0x180021734  mov     rax, [rcx]
0x180021737  mov     rax, [rax+10h]
0x18002173b  call    cs:__guard_dispatch_icall_fptr
0x180021741  jmp     short loc_18002174B
0x180021743  mov     rdi, [rbp+47h+var_88]
0x180021747  mov     r15, [rbp+47h+var_78]
0x18002174b  mov     rcx, r13; lpCriticalSection
0x18002174e  call    cs:__imp_EnterCriticalSection
0x180021754  nop
0x180021755  test    r12d, r12d
0x180021758  jz      short loc_18002176A
0x18002175a  mov     rcx, rdi; bstrString
0x18002175d  call    cs:__imp_SysFreeString
0x180021763  xor     edi, edi
0x180021765  mov     [rbp+47h+var_80], edi
0x180021768  jmp     short loc_18002176C
0x18002176a  xor     edi, edi
0x18002176c  cmp     dword ptr [rbp+47h+arg_8], edi
0x18002176f  jz      short loc_18002177D
0x180021771  mov     rcx, r15; bstrString
0x180021774  call    cs:__imp_SysFreeString
0x18002177a  mov     [rbp+47h+var_70], edi
0x18002177d  mov     rcx, rbx; this
0x180021780  call    ?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ; CCorSvcMgr::IsInterruptRequested(void)
0x180021785  test    eax, eax
0x180021787  jnz     short loc_180021803
0x180021789  mov     eax, [rbx+4F0h]
0x18002178f  test    eax, eax
0x180021791  jns     short loc_18002179B
0x180021793  cmp     [rbx+4F4h], edi
0x180021799  jz      short loc_1800217E7
0x18002179b  cmp     eax, 80070070h
0x1800217a0  jz      short loc_1800217E7
0x1800217a2  mov     rcx, r13; lpCriticalSection
0x1800217a5  call    cs:__imp_LeaveCriticalSection
0x1800217ab  nop
0x1800217ac  test    r14d, r14d
0x1800217af  jz      short loc_1800217C9
0x1800217b1  mov     rcx, rsi; this
0x1800217b4  call    ??1WorkerPoolItem@CCorSvcMgr@@QEAA@XZ; CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(void)
0x1800217b9  mov     edx, 40h ; '@'; unsigned __int64
0x1800217be  mov     rcx, rsi; void *
0x1800217c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800217c6  mov     [rbp+47h+var_60], edi
0x1800217c9  mov     eax, dword ptr [rbp+47h+var_98]
0x1800217cc  mov     rbx, [rsp+100h+arg_0]
0x1800217d4  add     rsp, 0D0h
0x1800217db  pop     r15
0x1800217dd  pop     r14
0x1800217df  pop     r13
0x1800217e1  pop     r12
0x1800217e3  pop     rdi
0x1800217e4  pop     rsi
0x1800217e5  pop     rbp
0x1800217e6  retn
0x1800217e7  mov     ecx, 80004004h; int
0x1800217ec  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800217f2  mov     ecx, eax; int
0x1800217f4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800217fa  mov     rcx, rbx; this
0x1800217fd  call    ?RelaunchNgenPdbAsMediumILAndExitProcess@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::RelaunchNgenPdbAsMediumILAndExitProcess(void)
0x180021803  mov     ecx, 80131E00h; int
0x180021808  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
