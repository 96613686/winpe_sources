# VIDMM_GLOBAL::LockCommon(VIDMM_ALLOC *,bool,ulong,void * *,bool *)

- ea: `0x140114068`
- end: `0x1401143fe`
- name: `?LockCommon@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z`
- size: `918`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_ALLOC *@<rdx>, bool@<r8b>, unsigned int@<r9d>, void **, bool *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140113cc8`
- `0x140113f8c`

## callees

- `0x1400045ec`
- `0x14002e850`
- `0x14002e950`
- `0x14002faf0`
- `0x14002fb4c`
- `0x140030fc4`
- `0x1400327ec`
- `0x14003b068`
- `0x14003ba24`
- `0x140058760`
- `0x140058ac0`
- `0x14009d45c`
- `0x1400a52b8`
- `0x1400e2504`
- `0x140114068`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011417a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011417a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140114186`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140114186`
- `watchdog!WdLogSingleEntry0` at `0x140114216`
- `watchdog!WdLogSingleEntry0` at `0x1401142c9`
- `watchdog!WdLogSingleEntry0` at `0x1401142fd`
- `watchdog!WdLogSingleEntry0` at `0x140114356`
- `watchdog!WdLogSingleEntry0` at `0x140114216`
- `watchdog!WdLogSingleEntry0` at `0x1401142c9`
- `watchdog!WdLogSingleEntry0` at `0x1401142fd`
- `watchdog!WdLogSingleEntry0` at `0x140114356`

## string_xrefs

- `0x140114227`: `Cached CPUVisible allocations must have an aperture segment in their supported segment set to be locked.\n`
- `0x140114367`: `CPUVisible allocations in !CPUVisible local memory segments must support an aperture segment while resident.\n`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::LockCommon(
        VIDMM_GLOBAL *this,
        __int64 ***a2,
        unsigned __int8 a3,
        unsigned int a4,
        void **a5,
        bool *a6)
{
  int v7; // r13d
  __int64 result; // rax
  bool v10; // r8
  int v11; // edi
  __int64 **v12; // r15
  __int64 *v13; // rbx
  __int64 v14; // r12
  __int64 v15; // r12
  __int64 v16; // r12
  __int64 v17; // rcx
  int v18; // r9d
  int v19; // ecx
  char v20; // r9
  int v21; // r8d
  __int64 v22; // rax
  const wchar_t *v23; // r9
  int v24; // eax
  char v25; // r9
  __int64 v26; // rcx
  __int64 **v27; // rax
  __int64 *v28; // rdx
  bool v29; // [rsp+50h] [rbp-89h] BYREF
  __int64 v30; // [rsp+58h] [rbp-81h]
  __int64 v31; // [rsp+60h] [rbp-79h] BYREF
  char v32; // [rsp+68h] [rbp-71h]
  _BYTE v33[16]; // [rsp+70h] [rbp-69h] BYREF
  _QWORD v34[20]; // [rsp+80h] [rbp-59h] BYREF

  v7 = a3;
  *a5 = 0;
  result = ValidateCommonLockParameters();
  v11 = result;
  if ( (int)result < 0 )
    return result;
  v12 = *a2;
  v13 = **a2;
  v14 = *v13;
  v30 = *v13;
  v29 = 0;
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
    (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&v31,
    (struct DXGPUSHLOCKFAST *)(v13 + 40),
    v10);
  if ( *((_DWORD *)v13 + 46) && v7 != (*((_BYTE *)v13 + 40) != 0) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 25679;
    goto LABEL_25;
  }
  if ( !*((_DWORD *)v12 + 17) )
  {
    v18 = *((_DWORD *)v13 + 6);
    v19 = *(_DWORD *)v13[48];
    if ( (v18 & 0x8000000) != 0 )
    {
      v20 = v18 & 1;
      if ( (v19 & 4) != 0 )
      {
        if ( v20 || (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 8) != 0 )
          goto LABEL_4;
        WdLogSingleEntry0(1);
        v22 = 25703;
        v23 = L"Cached CPUVisible allocations must have an aperture segment in their supported segment set to be locked.\n";
      }
      else
      {
        if ( !VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)a2)
          || !(unsigned __int8)NeedsApertureForLock(this, v13)
          || v25
          || (v13[3] & 4) != 0 )
        {
          goto LABEL_4;
        }
        WdLogSingleEntry0(1);
        v22 = 25712;
        v23 = L"CPUVisible allocations in !CPUVisible local memory segments must support an aperture segment while resident.\n";
      }
    }
    else
    {
      if ( (v19 & 0x40000) == 0 || (v18 & 2) != 0 )
        goto LABEL_4;
      WdLogSingleEntry0(1);
      v22 = 25724;
      v23 = L"CpuVisibleOnDemand allocations must be aperture only to lock.\n";
    }
    WdLogGlobalForLineNumber = v22;
    DxgkLogInternalTriageEvent(0, 0x40000, v21, (_DWORD)v23, v22, 0, 0, 0);
LABEL_25:
    DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&v31);
    return 3221225485LL;
  }
LABEL_4:
  v15 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v14 + 60) >> 2) & 0x3F));
  DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v33, (struct DXGFASTMUTEX *const)(v13 + 17), 0);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v33);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13[29] + 104LL))(v13[29], v13[30]);
  if ( (*(_DWORD *)(v30 + 64) & 0x10) != 0 )
    v29 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v15 + 264LL))(v15, v12);
  if ( v33[8] )
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v33);
  if ( v29 )
  {
    v16 = v30;
  }
  else
  {
    v24 = VIDMM_GLOBAL::LockInternal(this, 0, (struct VIDMM_ALLOC *)a2, v7, a4, a5, &v29);
    v16 = v30;
    v11 = v24;
    if ( v24 < 0 && (*(_DWORD *)(v30 + 64) & 0x10) != 0 )
      v29 = 1;
  }
  if ( v32 )
  {
    v17 = v31;
    *(_QWORD *)(v31 + 8) = 0;
    ExReleasePushLockExclusiveEx(v17, 0);
    KeLeaveCriticalRegion();
  }
  if ( v29 )
  {
    memset(v34, 0, 0x58u);
    v26 = (*(_DWORD *)(v16 + 60) >> 2) & 0x3F;
    LODWORD(v34[5]) = a4;
    v27 = a2[1];
    LODWORD(v34[0]) = 208;
    v34[2] = a2;
    v28 = v27[9];
    v34[4] = a5;
    BYTE4(v34[5]) = v7;
    v11 = VIDMM_GLOBAL::QueueDeferredCommand(
            this,
            (struct VIDMM_PAGING_QUEUE *)v28[4 * v26],
            (struct _VIDMM_DEFERRED_COMMAND *)v34,
            1,
            0);
    *a6 = BYTE5(v34[5]);
  }
  if ( v11 >= 0 && !*((_BYTE *)this + 37229) )
    VIDMM_GLOBAL::WaitForAllPagingEngines(this, 0, (struct VIDMM_GLOBAL_ALLOC *)v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140114068  mov     [rsp-8+arg_18], r9d
0x14011406d  push    rbp
0x14011406e  push    rbx
0x14011406f  push    rsi
0x140114070  push    rdi
0x140114071  push    r12
0x140114073  push    r13
0x140114075  push    r14
0x140114077  push    r15
0x140114079  lea     rbp, [rsp-0Fh]
0x14011407e  sub     rsp, 0E8h
0x140114085  mov     rax, [rbp+47h+arg_20]
0x140114089  mov     r14, rdx
0x14011408c  movzx   r13d, r8b
0x140114090  mov     rsi, rcx
0x140114093  mov     qword ptr [rax], 0
0x14011409a  call    ValidateCommonLockParameters
0x14011409f  mov     edi, eax
0x1401140a1  test    eax, eax
0x1401140a3  js      loc_1401141AC
0x1401140a9  mov     r15, [r14]
0x1401140ac  lea     rcx, [rbp+47h+var_C0]; this
0x1401140b0  mov     rbx, [r15]
0x1401140b3  mov     r12, [rbx]
0x1401140b6  lea     rdx, [rbx+140h]; struct DXGPUSHLOCKFAST *
0x1401140bd  mov     [rsp+120h+var_C8], r12
0x1401140c2  mov     [rsp+120h+var_D0], 0
0x1401140c7  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x1401140cc  mov     eax, [rbx+0B8h]
0x1401140d2  test    eax, eax
0x1401140d4  jnz     loc_1401142B3
0x1401140da  mov     eax, [r15+44h]
0x1401140de  test    eax, eax
0x1401140e0  jz      loc_1401141D0
0x1401140e6  mov     ecx, [r12+3Ch]
0x1401140eb  lea     rdx, [rbx+88h]; struct DXGFASTMUTEX *
0x1401140f2  mov     rax, [rsi+8E80h]
0x1401140f9  xor     r8d, r8d; unsigned __int8
0x1401140fc  shr     rcx, 2
0x140114100  and     ecx, 3Fh
0x140114103  mov     r12, [rax+rcx*8]
0x140114107  lea     rcx, [rbp+47h+var_B0]; this
0x14011410b  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x140114110  lea     rcx, [rbp+47h+var_B0]; this
0x140114114  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x140114119  mov     rcx, [rbx+0E8h]
0x140114120  mov     rdx, [rbx+0F0h]
0x140114127  mov     rax, [rcx]
0x14011412a  mov     rax, [rax+68h]
0x14011412e  call    _guard_dispatch_icall
0x140114133  mov     rax, [rsp+120h+var_C8]
0x140114138  mov     eax, [rax+40h]
0x14011413b  test    al, 10h
0x14011413d  jnz     loc_140114373
0x140114143  cmp     [rbp+47h+var_A8], 0
0x140114147  jz      short loc_140114152
0x140114149  lea     rcx, [rbp+47h+var_B0]; this
0x14011414d  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x140114152  cmp     [rsp+120h+var_D0], 0
0x140114157  mov     r15, [rbp+47h+arg_20]
0x14011415b  jz      loc_140114267
0x140114161  mov     r12, [rsp+120h+var_C8]
0x140114166  cmp     [rbp+47h+var_B8], 0
0x14011416a  jz      short loc_140114192
0x14011416c  mov     rcx, [rbp+47h+var_C0]
0x140114170  xor     edx, edx
0x140114172  mov     qword ptr [rcx+8], 0
0x14011417a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140114181  nop     dword ptr [rax+rax+00h]
0x140114186  call    cs:__imp_KeLeaveCriticalRegion
0x14011418d  nop     dword ptr [rax+rax+00h]
0x140114192  cmp     [rsp+120h+var_D0], 0
0x140114197  jnz     loc_140114392
0x14011419d  test    edi, edi
0x14011419f  js      short loc_1401141AA
0x1401141a1  cmp     byte ptr [rsi+916Dh], 0
0x1401141a8  jz      short loc_1401141C1
0x1401141aa  mov     eax, edi
0x1401141ac  add     rsp, 0E8h
0x1401141b3  pop     r15
0x1401141b5  pop     r14
0x1401141b7  pop     r13
0x1401141b9  pop     r12
0x1401141bb  pop     rdi
0x1401141bc  pop     rsi
0x1401141bd  pop     rbx
0x1401141be  pop     rbp
0x1401141bf  retn
0x1401141c1  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1401141c4  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1401141c6  mov     rcx, rsi; this
0x1401141c9  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1401141ce  jmp     short loc_1401141AA
0x1401141d0  mov     rax, [rbx+180h]
0x1401141d7  mov     r9d, [rbx+18h]
0x1401141db  mov     ecx, [rax]
0x1401141dd  bt      r9d, 1Bh
0x1401141e2  jnb     loc_1401142E4
0x1401141e8  and     r9b, 1
0x1401141ec  test    cl, 4
0x1401141ef  jz      loc_14011431A
0x1401141f5  test    r9b, r9b
0x1401141f8  jnz     loc_1401140E6
0x1401141fe  mov     rax, [rsi+18h]
0x140114202  mov     edx, [rax+1BCh]
0x140114208  test    dl, 8
0x14011420b  jnz     loc_1401140E6
0x140114211  mov     ecx, 1
0x140114216  call    cs:__imp_WdLogSingleEntry0
0x14011421d  nop     dword ptr [rax+rax+00h]
0x140114222  mov     eax, 6467h
0x140114227  lea     r9, aCachedCpuvisib; "Cached CPUVisible allocations must have"...
0x14011422e  xor     ecx, ecx
0x140114230  mov     cs:WdLogGlobalForLineNumber, eax
0x140114236  mov     [rsp+120h+var_E8], rcx
0x14011423b  mov     edx, 40000h
0x140114240  mov     [rsp+120h+var_F0], rcx
0x140114245  mov     [rsp+120h+var_F8], rcx
0x14011424a  mov     [rsp+120h+var_100], rax
0x14011424f  call    DxgkLogInternalTriageEvent
0x140114254  lea     rcx, [rbp+47h+var_C0]; this
0x140114258  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x14011425d  mov     eax, 0C000000Dh
0x140114262  jmp     loc_1401141AC
0x140114267  lea     rax, [rsp+120h+var_D0]
0x14011426c  mov     r9b, r13b; bool
0x14011426f  mov     [rsp+120h+var_F0], rax; bool *
0x140114274  mov     r8, r14; struct VIDMM_ALLOC *
0x140114277  mov     eax, [rbp+47h+arg_18]
0x14011427a  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14011427c  mov     [rsp+120h+var_F8], r15; void **
0x140114281  mov     rcx, rsi; this
0x140114284  mov     dword ptr [rsp+120h+var_100], eax; unsigned int
0x140114288  call    ?LockInternal@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z; VIDMM_GLOBAL::LockInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,ulong,void * *,bool *)
0x14011428d  mov     r12, [rsp+120h+var_C8]
0x140114292  mov     edi, eax
0x140114294  test    eax, eax
0x140114296  jns     loc_140114166
0x14011429c  mov     eax, [r12+40h]
0x1401142a1  test    al, 10h
0x1401142a3  jz      loc_140114166
0x1401142a9  mov     [rsp+120h+var_D0], 1
0x1401142ae  jmp     loc_140114166
0x1401142b3  xor     ecx, ecx
0x1401142b5  cmp     [rbx+28h], cl
0x1401142b8  setnz   cl
0x1401142bb  cmp     r13d, ecx
0x1401142be  jz      loc_1401140DA
0x1401142c4  mov     ecx, 2
0x1401142c9  call    cs:__imp_WdLogSingleEntry0
0x1401142d0  nop     dword ptr [rax+rax+00h]
0x1401142d5  mov     cs:WdLogGlobalForLineNumber, 644Fh
0x1401142df  jmp     loc_140114254
0x1401142e4  bt      ecx, 12h
0x1401142e8  jnb     loc_1401140E6
0x1401142ee  test    r9b, 2
0x1401142f2  jnz     loc_1401140E6
0x1401142f8  mov     ecx, 1
0x1401142fd  call    cs:__imp_WdLogSingleEntry0
0x140114304  nop     dword ptr [rax+rax+00h]
0x140114309  mov     eax, 647Ch
0x14011430e  lea     r9, aCpuvisibleonde_2; "CpuVisibleOnDemand allocations must be "...
0x140114315  jmp     loc_14011422E
0x14011431a  mov     rcx, r14; this
0x14011431d  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x140114322  test    al, al
0x140114324  jz      loc_1401140E6
0x14011432a  mov     rdx, rbx
0x14011432d  mov     rcx, rsi
0x140114330  call    NeedsApertureForLock
0x140114335  test    al, al
0x140114337  jz      loc_1401140E6
0x14011433d  test    r9b, r9b
0x140114340  jnz     loc_1401140E6
0x140114346  mov     eax, [rbx+18h]
0x140114349  test    al, 4
0x14011434b  jnz     loc_1401140E6
0x140114351  mov     ecx, 1
0x140114356  call    cs:__imp_WdLogSingleEntry0
0x14011435d  nop     dword ptr [rax+rax+00h]
0x140114362  mov     eax, 6470h
0x140114367  lea     r9, aCpuvisibleAllo; "CPUVisible allocations in !CPUVisible l"...
0x14011436e  jmp     loc_14011422E
0x140114373  mov     rax, [r12]
0x140114377  mov     rdx, r15
0x14011437a  mov     rcx, r12
0x14011437d  mov     rax, [rax+108h]
0x140114384  call    _guard_dispatch_icall
0x140114389  mov     [rsp+120h+var_D0], al
0x14011438d  jmp     loc_140114143
0x140114392  xor     edx, edx; Val
0x140114394  lea     rcx, [rbp+47h+var_A0]; void *
0x140114398  lea     r8d, [rdx+58h]; Size
0x14011439c  call    memset
0x1401143a1  mov     eax, [rbp+47h+arg_18]
0x1401143a4  lea     r8, [rbp+47h+var_A0]; struct _VIDMM_DEFERRED_COMMAND *
0x1401143a8  mov     ecx, [r12+3Ch]
0x1401143ad  mov     r9b, 1; bool
0x1401143b0  shr     rcx, 2
0x1401143b4  and     ecx, 3Fh
0x1401143b7  mov     [rbp+47h+var_78], eax
0x1401143ba  mov     rax, [r14+8]
0x1401143be  shl     rcx, 5
0x1401143c2  mov     [rbp+47h+var_A0], 0D0h
0x1401143c9  mov     [rbp+47h+var_90], r14
0x1401143cd  mov     rdx, [rax+48h]
0x1401143d1  mov     [rbp+47h+var_80], r15
0x1401143d5  mov     [rbp+47h+var_74], r13b
0x1401143d9  mov     [rsp+120h+var_100], 0; unsigned __int64 *
0x1401143e2  mov     rdx, [rcx+rdx]; struct VIDMM_PAGING_QUEUE *
0x1401143e6  mov     rcx, rsi; this
0x1401143e9  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x1401143ee  mov     rcx, [rbp+47h+arg_28]
0x1401143f2  mov     edi, eax
0x1401143f4  mov     al, [rbp+47h+var_73]
0x1401143f7  mov     [rcx], al
0x1401143f9  jmp     loc_14011419D
```
