# VIDMM_GLOBAL::LockCommon(VIDMM_ALLOC *,bool,ulong,void * *,bool *)

- ea: `0x140117aa8`
- end: `0x140117e3e`
- name: `?LockCommon@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z`
- size: `918`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_ALLOC *@<rdx>, bool@<r8b>, unsigned int@<r9d>, void **, bool *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140117708`
- `0x1401179cc`

## callees

- `0x140004268`
- `0x14002b730`
- `0x14002b830`
- `0x14002d810`
- `0x14002d86c`
- `0x14002eba4`
- `0x1400305ac`
- `0x140039d78`
- `0x14003a734`
- `0x140059030`
- `0x140059380`
- `0x140097b0c`
- `0x1400a5598`
- `0x1400ea904`
- `0x140117aa8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140117bba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140117bba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140117bc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140117bc6`
- `watchdog!WdLogSingleEntry0` at `0x140117c56`
- `watchdog!WdLogSingleEntry0` at `0x140117d09`
- `watchdog!WdLogSingleEntry0` at `0x140117d3d`
- `watchdog!WdLogSingleEntry0` at `0x140117d96`
- `watchdog!WdLogSingleEntry0` at `0x140117c56`
- `watchdog!WdLogSingleEntry0` at `0x140117d09`
- `watchdog!WdLogSingleEntry0` at `0x140117d3d`
- `watchdog!WdLogSingleEntry0` at `0x140117d96`

## string_xrefs

- `0x140117c67`: `Cached CPUVisible allocations must have an aperture segment in their supported segment set to be locked.\n`
- `0x140117da7`: `CPUVisible allocations in !CPUVisible local memory segments must support an aperture segment while resident.\n`

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
    WdLogGlobalForLineNumber = 25918;
    goto LABEL_25;
  }
  if ( !*((_DWORD *)v12 + 17) )
  {
    v18 = *((_DWORD *)v13 + 6);
    v19 = *(_DWORD *)v13[49];
    if ( (v18 & 0x8000000) != 0 )
    {
      v20 = v18 & 1;
      if ( (v19 & 4) != 0 )
      {
        if ( v20 || (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 8) != 0 )
          goto LABEL_4;
        WdLogSingleEntry0(1);
        v22 = 25942;
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
        v22 = 25951;
        v23 = L"CPUVisible allocations in !CPUVisible local memory segments must support an aperture segment while resident.\n";
      }
    }
    else
    {
      if ( (v19 & 0x40000) == 0 || (v18 & 2) != 0 )
        goto LABEL_4;
      WdLogSingleEntry0(1);
      v22 = 25963;
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
0x140117aa8  mov     [rsp-8+arg_18], r9d
0x140117aad  push    rbp
0x140117aae  push    rbx
0x140117aaf  push    rsi
0x140117ab0  push    rdi
0x140117ab1  push    r12
0x140117ab3  push    r13
0x140117ab5  push    r14
0x140117ab7  push    r15
0x140117ab9  lea     rbp, [rsp-0Fh]
0x140117abe  sub     rsp, 0E8h
0x140117ac5  mov     rax, [rbp+47h+arg_20]
0x140117ac9  mov     r14, rdx
0x140117acc  movzx   r13d, r8b
0x140117ad0  mov     rsi, rcx
0x140117ad3  mov     qword ptr [rax], 0
0x140117ada  call    ValidateCommonLockParameters
0x140117adf  mov     edi, eax
0x140117ae1  test    eax, eax
0x140117ae3  js      loc_140117BEC
0x140117ae9  mov     r15, [r14]
0x140117aec  lea     rcx, [rbp+47h+var_C0]; this
0x140117af0  mov     rbx, [r15]
0x140117af3  mov     r12, [rbx]
0x140117af6  lea     rdx, [rbx+140h]; struct DXGPUSHLOCKFAST *
0x140117afd  mov     [rsp+120h+var_C8], r12
0x140117b02  mov     [rsp+120h+var_D0], 0
0x140117b07  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x140117b0c  mov     eax, [rbx+0B8h]
0x140117b12  test    eax, eax
0x140117b14  jnz     loc_140117CF3
0x140117b1a  mov     eax, [r15+44h]
0x140117b1e  test    eax, eax
0x140117b20  jz      loc_140117C10
0x140117b26  mov     ecx, [r12+3Ch]
0x140117b2b  lea     rdx, [rbx+88h]; struct DXGFASTMUTEX *
0x140117b32  mov     rax, [rsi+8E80h]
0x140117b39  xor     r8d, r8d; unsigned __int8
0x140117b3c  shr     rcx, 2
0x140117b40  and     ecx, 3Fh
0x140117b43  mov     r12, [rax+rcx*8]
0x140117b47  lea     rcx, [rbp+47h+var_B0]; this
0x140117b4b  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x140117b50  lea     rcx, [rbp+47h+var_B0]; this
0x140117b54  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x140117b59  mov     rcx, [rbx+0E8h]
0x140117b60  mov     rdx, [rbx+0F0h]
0x140117b67  mov     rax, [rcx]
0x140117b6a  mov     rax, [rax+68h]
0x140117b6e  call    _guard_dispatch_icall
0x140117b73  mov     rax, [rsp+120h+var_C8]
0x140117b78  mov     eax, [rax+40h]
0x140117b7b  test    al, 10h
0x140117b7d  jnz     loc_140117DB3
0x140117b83  cmp     [rbp+47h+var_A8], 0
0x140117b87  jz      short loc_140117B92
0x140117b89  lea     rcx, [rbp+47h+var_B0]; this
0x140117b8d  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x140117b92  cmp     [rsp+120h+var_D0], 0
0x140117b97  mov     r15, [rbp+47h+arg_20]
0x140117b9b  jz      loc_140117CA7
0x140117ba1  mov     r12, [rsp+120h+var_C8]
0x140117ba6  cmp     [rbp+47h+var_B8], 0
0x140117baa  jz      short loc_140117BD2
0x140117bac  mov     rcx, [rbp+47h+var_C0]
0x140117bb0  xor     edx, edx
0x140117bb2  mov     qword ptr [rcx+8], 0
0x140117bba  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140117bc1  nop     dword ptr [rax+rax+00h]
0x140117bc6  call    cs:__imp_KeLeaveCriticalRegion
0x140117bcd  nop     dword ptr [rax+rax+00h]
0x140117bd2  cmp     [rsp+120h+var_D0], 0
0x140117bd7  jnz     loc_140117DD2
0x140117bdd  test    edi, edi
0x140117bdf  js      short loc_140117BEA
0x140117be1  cmp     byte ptr [rsi+916Dh], 0
0x140117be8  jz      short loc_140117C01
0x140117bea  mov     eax, edi
0x140117bec  add     rsp, 0E8h
0x140117bf3  pop     r15
0x140117bf5  pop     r14
0x140117bf7  pop     r13
0x140117bf9  pop     r12
0x140117bfb  pop     rdi
0x140117bfc  pop     rsi
0x140117bfd  pop     rbx
0x140117bfe  pop     rbp
0x140117bff  retn
0x140117c01  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x140117c04  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x140117c06  mov     rcx, rsi; this
0x140117c09  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x140117c0e  jmp     short loc_140117BEA
0x140117c10  mov     rax, [rbx+188h]
0x140117c17  mov     r9d, [rbx+18h]
0x140117c1b  mov     ecx, [rax]
0x140117c1d  bt      r9d, 1Bh
0x140117c22  jnb     loc_140117D24
0x140117c28  and     r9b, 1
0x140117c2c  test    cl, 4
0x140117c2f  jz      loc_140117D5A
0x140117c35  test    r9b, r9b
0x140117c38  jnz     loc_140117B26
0x140117c3e  mov     rax, [rsi+18h]
0x140117c42  mov     edx, [rax+1BCh]
0x140117c48  test    dl, 8
0x140117c4b  jnz     loc_140117B26
0x140117c51  mov     ecx, 1
0x140117c56  call    cs:__imp_WdLogSingleEntry0
0x140117c5d  nop     dword ptr [rax+rax+00h]
0x140117c62  mov     eax, 6556h
0x140117c67  lea     r9, aCachedCpuvisib; "Cached CPUVisible allocations must have"...
0x140117c6e  xor     ecx, ecx
0x140117c70  mov     cs:WdLogGlobalForLineNumber, eax
0x140117c76  mov     [rsp+120h+var_E8], rcx
0x140117c7b  mov     edx, 40000h
0x140117c80  mov     [rsp+120h+var_F0], rcx
0x140117c85  mov     [rsp+120h+var_F8], rcx
0x140117c8a  mov     [rsp+120h+var_100], rax
0x140117c8f  call    DxgkLogInternalTriageEvent
0x140117c94  lea     rcx, [rbp+47h+var_C0]; this
0x140117c98  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x140117c9d  mov     eax, 0C000000Dh
0x140117ca2  jmp     loc_140117BEC
0x140117ca7  lea     rax, [rsp+120h+var_D0]
0x140117cac  mov     r9b, r13b; bool
0x140117caf  mov     [rsp+120h+var_F0], rax; bool *
0x140117cb4  mov     r8, r14; struct VIDMM_ALLOC *
0x140117cb7  mov     eax, [rbp+47h+arg_18]
0x140117cba  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x140117cbc  mov     [rsp+120h+var_F8], r15; void **
0x140117cc1  mov     rcx, rsi; this
0x140117cc4  mov     dword ptr [rsp+120h+var_100], eax; unsigned int
0x140117cc8  call    ?LockInternal@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z; VIDMM_GLOBAL::LockInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,ulong,void * *,bool *)
0x140117ccd  mov     r12, [rsp+120h+var_C8]
0x140117cd2  mov     edi, eax
0x140117cd4  test    eax, eax
0x140117cd6  jns     loc_140117BA6
0x140117cdc  mov     eax, [r12+40h]
0x140117ce1  test    al, 10h
0x140117ce3  jz      loc_140117BA6
0x140117ce9  mov     [rsp+120h+var_D0], 1
0x140117cee  jmp     loc_140117BA6
0x140117cf3  xor     ecx, ecx
0x140117cf5  cmp     [rbx+28h], cl
0x140117cf8  setnz   cl
0x140117cfb  cmp     r13d, ecx
0x140117cfe  jz      loc_140117B1A
0x140117d04  mov     ecx, 2
0x140117d09  call    cs:__imp_WdLogSingleEntry0
0x140117d10  nop     dword ptr [rax+rax+00h]
0x140117d15  mov     cs:WdLogGlobalForLineNumber, 653Eh
0x140117d1f  jmp     loc_140117C94
0x140117d24  bt      ecx, 12h
0x140117d28  jnb     loc_140117B26
0x140117d2e  test    r9b, 2
0x140117d32  jnz     loc_140117B26
0x140117d38  mov     ecx, 1
0x140117d3d  call    cs:__imp_WdLogSingleEntry0
0x140117d44  nop     dword ptr [rax+rax+00h]
0x140117d49  mov     eax, 656Bh
0x140117d4e  lea     r9, aCpuvisibleonde_2; "CpuVisibleOnDemand allocations must be "...
0x140117d55  jmp     loc_140117C6E
0x140117d5a  mov     rcx, r14; this
0x140117d5d  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x140117d62  test    al, al
0x140117d64  jz      loc_140117B26
0x140117d6a  mov     rdx, rbx
0x140117d6d  mov     rcx, rsi
0x140117d70  call    NeedsApertureForLock
0x140117d75  test    al, al
0x140117d77  jz      loc_140117B26
0x140117d7d  test    r9b, r9b
0x140117d80  jnz     loc_140117B26
0x140117d86  mov     eax, [rbx+18h]
0x140117d89  test    al, 4
0x140117d8b  jnz     loc_140117B26
0x140117d91  mov     ecx, 1
0x140117d96  call    cs:__imp_WdLogSingleEntry0
0x140117d9d  nop     dword ptr [rax+rax+00h]
0x140117da2  mov     eax, 655Fh
0x140117da7  lea     r9, aCpuvisibleAllo; "CPUVisible allocations in !CPUVisible l"...
0x140117dae  jmp     loc_140117C6E
0x140117db3  mov     rax, [r12]
0x140117db7  mov     rdx, r15
0x140117dba  mov     rcx, r12
0x140117dbd  mov     rax, [rax+108h]
0x140117dc4  call    _guard_dispatch_icall
0x140117dc9  mov     [rsp+120h+var_D0], al
0x140117dcd  jmp     loc_140117B83
0x140117dd2  xor     edx, edx; Val
0x140117dd4  lea     rcx, [rbp+47h+var_A0]; void *
0x140117dd8  lea     r8d, [rdx+58h]; Size
0x140117ddc  call    memset
0x140117de1  mov     eax, [rbp+47h+arg_18]
0x140117de4  lea     r8, [rbp+47h+var_A0]; struct _VIDMM_DEFERRED_COMMAND *
0x140117de8  mov     ecx, [r12+3Ch]
0x140117ded  mov     r9b, 1; bool
0x140117df0  shr     rcx, 2
0x140117df4  and     ecx, 3Fh
0x140117df7  mov     [rbp+47h+var_78], eax
0x140117dfa  mov     rax, [r14+8]
0x140117dfe  shl     rcx, 5
0x140117e02  mov     [rbp+47h+var_A0], 0D0h
0x140117e09  mov     [rbp+47h+var_90], r14
0x140117e0d  mov     rdx, [rax+48h]
0x140117e11  mov     [rbp+47h+var_80], r15
0x140117e15  mov     [rbp+47h+var_74], r13b
0x140117e19  mov     [rsp+120h+var_100], 0; unsigned __int64 *
0x140117e22  mov     rdx, [rcx+rdx]; struct VIDMM_PAGING_QUEUE *
0x140117e26  mov     rcx, rsi; this
0x140117e29  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x140117e2e  mov     rcx, [rbp+47h+arg_28]
0x140117e32  mov     edi, eax
0x140117e34  mov     al, [rbp+47h+var_73]
0x140117e37  mov     [rcx], al
0x140117e39  jmp     loc_140117BDD
```
