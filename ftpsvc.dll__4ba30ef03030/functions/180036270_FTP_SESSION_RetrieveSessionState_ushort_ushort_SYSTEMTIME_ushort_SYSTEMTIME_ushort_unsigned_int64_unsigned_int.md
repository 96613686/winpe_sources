# FTP_SESSION::RetrieveSessionState(ushort * *,ushort * *,_SYSTEMTIME *,ushort * *,_SYSTEMTIME *,ushort * *,unsigned __int64 *,unsigned __int64 *,long *)

- ea: `0x180036270`
- end: `0x1800365c5`
- name: `?RetrieveSessionState@FTP_SESSION@@UEAAJPEAPEAG0PEAU_SYSTEMTIME@@010PEA_K2PEAJ@Z`
- size: `853`
- prototype: `__int64 __fastcall(FTP_SESSION *__hidden this, unsigned __int16 **, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, unsigned __int64 *, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x18000aba4`
- `0x180036270`
- `0x180047050`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180036355`
- `ole32!CoTaskMemAlloc` at `0x18003639a`
- `ole32!CoTaskMemAlloc` at `0x180036416`
- `ole32!CoTaskMemAlloc` at `0x180036482`
- `ole32!CoTaskMemAlloc` at `0x180036355`
- `ole32!CoTaskMemAlloc` at `0x18003639a`
- `ole32!CoTaskMemAlloc` at `0x180036416`
- `ole32!CoTaskMemAlloc` at `0x180036482`
- `ole32!CoTaskMemFree` at `0x18003655c`
- `ole32!CoTaskMemFree` at `0x18003656a`
- `ole32!CoTaskMemFree` at `0x180036578`
- `ole32!CoTaskMemFree` at `0x180036586`
- `ole32!CoTaskMemFree` at `0x18003655c`
- `ole32!CoTaskMemFree` at `0x18003656a`
- `ole32!CoTaskMemFree` at `0x180036578`
- `ole32!CoTaskMemFree` at `0x180036586`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800363fb`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180036467`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800363fb`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180036467`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180036329`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180036329`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003633a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800363ef`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003633a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800363ef`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003631b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003631b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800362f7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800362f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180036591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003659d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180036591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003659d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SESSION::RetrieveSessionState(
        FTP_SESSION *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        struct _SYSTEMTIME *a4,
        unsigned __int16 **a5,
        struct _SYSTEMTIME *a6,
        unsigned __int16 **a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9,
        int *a10)
{
  unsigned __int16 *v12; // r15
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // r12
  int v15; // ebx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rdi
  __int64 v19; // rbx
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rax
  unsigned int v25; // ebx
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rdx
  _BYTE v31[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C8h] [rbp-38h]
  _OWORD v37[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  STRU::STRU(v31);
  memset(v37, 0, sizeof(v37));
  v38 = 0;
  STRU::STRU((STRU *)v34, (unsigned __int16 *)v37, 0x14u);
  CSpinLock::WriteLock((FTP_SESSION *)((char *)this + 5616));
  v15 = STRU::Copy((STRU *)v34, *((const unsigned __int16 **)this + 728));
  if ( v15 < 0 )
  {
    v18 = 0;
  }
  else
  {
    v16 = (unsigned int)(v36 + 1);
    v17 = (unsigned __int16 *)CoTaskMemAlloc(2 * v16);
    v18 = v17;
    if ( !v17 )
    {
LABEL_3:
      v15 = -2147024882;
      goto LABEL_18;
    }
    v15 = StringCchCopyNW(v17, v16, v35, v16);
    if ( v15 >= 0 )
    {
      v12 = v18;
      v19 = (unsigned int)(*((_DWORD *)this + 184) + 1);
      v20 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
      v18 = v20;
      if ( !v20 )
        goto LABEL_3;
      v15 = StringCchCopyNW(v20, (unsigned int)v19, *((const unsigned __int16 **)this + 90), (unsigned int)v19);
      if ( v15 >= 0 )
      {
        v13 = v18;
        v18 = 0;
        v21 = *((_QWORD *)this + 701);
        *v32 = 0;
        v33 = 0;
        v22 = v21 ? STRU::CopyA((STRU *)v31, *(const char **)(v21 + 48)) : STRU::Copy((STRU *)v31, &WideCharStr);
        v15 = v22;
        if ( v22 >= 0 )
        {
          v23 = v33 + 1;
          v24 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v33 + 1));
          v18 = v24;
          if ( !v24 )
            goto LABEL_3;
          v15 = StringCchCopyNW(v24, v23, v32, v23);
          if ( v15 >= 0 )
          {
            v14 = v18;
            v18 = 0;
            *v32 = 0;
            *v32 = 0;
            v33 = 0;
            v15 = STRU::CopyA((STRU *)v31, *((const char **)this + 593));
            if ( v15 >= 0 )
            {
              v25 = v33 + 1;
              v26 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v33 + 1));
              v18 = v26;
              if ( !v26 )
                goto LABEL_3;
              v15 = StringCchCopyNW(v26, v25, v32, v25);
              if ( v15 >= 0 )
              {
                v27 = v18;
                v18 = 0;
                *v32 = 0;
                v33 = 0;
                *a2 = v12;
                *a3 = v13;
                *a4 = *(struct _SYSTEMTIME *)((char *)this + 4676);
                *a5 = v14;
                *a6 = *(struct _SYSTEMTIME *)((char *)this + 4692);
                *a7 = v27;
                *a8 = *((_QWORD *)this + 8) + *((_QWORD *)this + 10);
                *a9 = *((_QWORD *)this + 9) + *((_QWORD *)this + 11);
                *a10 = *((_DWORD *)this + 1192);
                v12 = 0;
                v13 = 0;
                v14 = 0;
                v15 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  _InterlockedExchange(
    (volatile __int32 *)this + 1404,
    ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v18 )
    CoTaskMemFree(v18);
  STRU::~STRU(v34);
  STRU::~STRU(v31);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180036270  push    rbp
0x180036272  push    rbx
0x180036273  push    rsi
0x180036274  push    rdi
0x180036275  push    r12
0x180036277  push    r13
0x180036279  push    r14
0x18003627b  push    r15
0x18003627d  lea     rbp, [rsp-8]
0x180036282  sub     rsp, 108h
0x180036289  mov     rax, cs:__security_cookie
0x180036290  xor     rax, rsp
0x180036293  mov     [rbp+40h+var_48], rax
0x180036297  mov     [rsp+140h+var_118], r9
0x18003629c  mov     [rsp+140h+var_120], r8
0x1800362a1  mov     r13, rdx
0x1800362a4  mov     rsi, rcx
0x1800362a7  mov     rax, [rbp+40h+arg_20]
0x1800362ab  mov     [rsp+140h+var_110], rax
0x1800362b0  mov     rax, [rbp+40h+arg_28]
0x1800362b4  mov     [rsp+140h+var_108], rax
0x1800362b9  mov     rax, [rbp+40h+arg_30]
0x1800362c0  mov     [rsp+140h+var_100], rax
0x1800362c5  mov     rax, [rbp+40h+arg_38]
0x1800362cc  mov     [rsp+140h+var_F8], rax
0x1800362d1  mov     rax, [rbp+40h+arg_40]
0x1800362d8  mov     [rsp+140h+var_F0], rax
0x1800362dd  mov     rax, [rbp+40h+arg_48]
0x1800362e4  mov     [rsp+140h+var_E8], rax
0x1800362e9  xor     r15d, r15d
0x1800362ec  xor     r14d, r14d
0x1800362ef  xor     r12d, r12d
0x1800362f2  lea     rcx, [rsp+140h+var_E0]
0x1800362f7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800362fd  nop
0x1800362fe  xorps   xmm0, xmm0
0x180036301  xor     eax, eax
0x180036303  movups  [rbp+40h+var_70], xmm0
0x180036307  movups  [rbp+40h+var_60], xmm0
0x18003630b  mov     [rbp+40h+var_50], rax
0x18003630f  lea     r8d, [r15+14h]
0x180036313  lea     rdx, [rbp+40h+var_70]
0x180036317  lea     rcx, [rbp+40h+var_A8]
0x18003631b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180036321  nop
0x180036322  lea     rcx, [rsi+15F0h]
0x180036329  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x18003632f  mov     rdx, [rsi+16C0h]
0x180036336  lea     rcx, [rbp+40h+var_A8]
0x18003633a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180036340  mov     ebx, eax
0x180036342  test    eax, eax
0x180036344  js      loc_180036536
0x18003634a  mov     eax, [rbp+40h+var_78]
0x18003634d  inc     eax
0x18003634f  mov     ebx, eax
0x180036351  lea     rcx, [rax+rax]; cb
0x180036355  call    cs:__imp_CoTaskMemAlloc
0x18003635b  mov     rdi, rax
0x18003635e  test    rax, rax
0x180036361  jnz     short loc_18003636D
0x180036363  mov     ebx, 8007000Eh
0x180036368  jmp     loc_180036538
0x18003636d  mov     r9, rbx; unsigned __int64
0x180036370  mov     r8, [rbp+40h+var_88]; unsigned __int16 *
0x180036374  mov     rdx, rbx; unsigned __int64
0x180036377  mov     rcx, rdi; unsigned __int16 *
0x18003637a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003637f  mov     ebx, eax
0x180036381  test    eax, eax
0x180036383  js      loc_180036538
0x180036389  mov     r15, rdi
0x18003638c  mov     eax, [rsi+2E0h]
0x180036392  inc     eax
0x180036394  mov     ebx, eax
0x180036396  lea     rcx, [rax+rax]; cb
0x18003639a  call    cs:__imp_CoTaskMemAlloc
0x1800363a0  mov     rdi, rax
0x1800363a3  test    rax, rax
0x1800363a6  jz      short loc_180036363
0x1800363a8  mov     r9d, ebx; unsigned __int64
0x1800363ab  mov     r8, [rsi+2D0h]; unsigned __int16 *
0x1800363b2  mov     edx, ebx; unsigned __int64
0x1800363b4  mov     rcx, rax; unsigned __int16 *
0x1800363b7  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800363bc  mov     ebx, eax
0x1800363be  test    eax, eax
0x1800363c0  js      loc_180036538
0x1800363c6  mov     r14, rdi
0x1800363c9  xor     edi, edi
0x1800363cb  mov     rdx, [rsi+15E8h]
0x1800363d2  xor     ecx, ecx
0x1800363d4  mov     rax, [rbp+40h+var_C0]
0x1800363d8  mov     [rax], cx
0x1800363db  mov     [rbp+40h+var_B0], ecx
0x1800363de  lea     rcx, [rsp+140h+var_E0]
0x1800363e3  test    rdx, rdx
0x1800363e6  jnz     short loc_1800363F7
0x1800363e8  lea     rdx, WideCharStr
0x1800363ef  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800363f5  jmp     short loc_180036401
0x1800363f7  mov     rdx, [rdx+30h]
0x1800363fb  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180036401  test    eax, eax
0x180036403  mov     ebx, eax
0x180036405  js      loc_180036538
0x18003640b  mov     eax, [rbp+40h+var_B0]
0x18003640e  inc     eax
0x180036410  mov     ebx, eax
0x180036412  lea     rcx, [rax+rax]; cb
0x180036416  call    cs:__imp_CoTaskMemAlloc
0x18003641c  mov     rdi, rax
0x18003641f  test    rax, rax
0x180036422  jz      loc_180036363
0x180036428  mov     r9d, ebx; unsigned __int64
0x18003642b  mov     r8, [rbp+40h+var_C0]; unsigned __int16 *
0x18003642f  mov     edx, ebx; unsigned __int64
0x180036431  mov     rcx, rax; unsigned __int16 *
0x180036434  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180036439  mov     ebx, eax
0x18003643b  test    eax, eax
0x18003643d  js      loc_180036538
0x180036443  mov     r12, rdi
0x180036446  xor     edi, edi
0x180036448  xor     ecx, ecx
0x18003644a  mov     rax, [rbp+40h+var_C0]
0x18003644e  mov     [rax], cx
0x180036451  mov     rax, [rbp+40h+var_C0]
0x180036455  mov     [rax], cx
0x180036458  mov     [rbp+40h+var_B0], ecx
0x18003645b  mov     rdx, [rsi+1288h]
0x180036462  lea     rcx, [rsp+140h+var_E0]
0x180036467  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18003646d  mov     ebx, eax
0x18003646f  test    eax, eax
0x180036471  js      loc_180036538
0x180036477  mov     eax, [rbp+40h+var_B0]
0x18003647a  inc     eax
0x18003647c  mov     ebx, eax
0x18003647e  lea     rcx, [rax+rax]; cb
0x180036482  call    cs:__imp_CoTaskMemAlloc
0x180036488  mov     rdi, rax
0x18003648b  test    rax, rax
0x18003648e  jz      loc_180036363
0x180036494  mov     r9d, ebx; unsigned __int64
0x180036497  mov     r8, [rbp+40h+var_C0]; unsigned __int16 *
0x18003649b  mov     edx, ebx; unsigned __int64
0x18003649d  mov     rcx, rax; unsigned __int16 *
0x1800364a0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800364a5  mov     ebx, eax
0x1800364a7  test    eax, eax
0x1800364a9  js      loc_180036538
0x1800364af  mov     rdx, rdi
0x1800364b2  xor     edi, edi
0x1800364b4  xor     ecx, ecx
0x1800364b6  mov     rax, [rbp+40h+var_C0]
0x1800364ba  mov     [rax], cx
0x1800364bd  mov     [rbp+40h+var_B0], ecx
0x1800364c0  mov     [r13+0], r15
0x1800364c4  mov     rax, [rsp+140h+var_120]
0x1800364c9  mov     [rax], r14
0x1800364cc  movups  xmm0, xmmword ptr [rsi+1244h]
0x1800364d3  mov     rax, [rsp+140h+var_118]
0x1800364d8  movdqu  xmmword ptr [rax], xmm0
0x1800364dc  mov     rax, [rsp+140h+var_110]
0x1800364e1  mov     [rax], r12
0x1800364e4  movups  xmm1, xmmword ptr [rsi+1254h]
0x1800364eb  mov     rax, [rsp+140h+var_108]
0x1800364f0  movdqu  xmmword ptr [rax], xmm1
0x1800364f4  mov     rax, [rsp+140h+var_100]
0x1800364f9  mov     [rax], rdx
0x1800364fc  mov     rax, [rsi+50h]
0x180036500  add     rax, [rsi+40h]
0x180036504  mov     rcx, [rsp+140h+var_F8]
0x180036509  mov     [rcx], rax
0x18003650c  mov     rax, [rsi+58h]
0x180036510  add     rax, [rsi+48h]
0x180036514  mov     rcx, [rsp+140h+var_F0]
0x180036519  mov     [rcx], rax
0x18003651c  mov     eax, [rsi+12A0h]
0x180036522  mov     rcx, [rsp+140h+var_E8]
0x180036527  mov     [rcx], eax
0x180036529  xor     r15d, r15d
0x18003652c  xor     r14d, r14d
0x18003652f  xor     r12d, r12d
0x180036532  xor     ebx, ebx
0x180036534  jmp     short loc_180036538
0x180036536  xor     edi, edi
0x180036538  mov     r8d, [rsi+15F0h]
0x18003653f  dec     r8d
0x180036542  mov     eax, r8d
0x180036545  and     al, 3
0x180036547  neg     al
0x180036549  sbb     edx, edx
0x18003654b  and     edx, r8d
0x18003654e  xchg    edx, [rsi+15F0h]
0x180036554  test    r12, r12
0x180036557  jz      short loc_180036562
0x180036559  mov     rcx, r12; pv
0x18003655c  call    cs:__imp_CoTaskMemFree
0x180036562  test    r14, r14
0x180036565  jz      short loc_180036570
0x180036567  mov     rcx, r14; pv
0x18003656a  call    cs:__imp_CoTaskMemFree
0x180036570  test    r15, r15
0x180036573  jz      short loc_18003657E
0x180036575  mov     rcx, r15; pv
0x180036578  call    cs:__imp_CoTaskMemFree
0x18003657e  test    rdi, rdi
0x180036581  jz      short loc_18003658D
0x180036583  mov     rcx, rdi; pv
0x180036586  call    cs:__imp_CoTaskMemFree
0x18003658c  nop
0x18003658d  lea     rcx, [rbp+40h+var_A8]
0x180036591  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180036597  nop
0x180036598  lea     rcx, [rsp+140h+var_E0]
0x18003659d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800365a3  mov     eax, ebx
0x1800365a5  mov     rcx, [rbp+40h+var_48]
0x1800365a9  xor     rcx, rsp; StackCookie
0x1800365ac  call    __security_check_cookie
0x1800365b1  add     rsp, 108h
0x1800365b8  pop     r15
0x1800365ba  pop     r14
0x1800365bc  pop     r13
0x1800365be  pop     r12
0x1800365c0  pop     rdi
0x1800365c1  pop     rsi
0x1800365c2  pop     rbx
0x1800365c3  pop     rbp
0x1800365c4  retn
```
