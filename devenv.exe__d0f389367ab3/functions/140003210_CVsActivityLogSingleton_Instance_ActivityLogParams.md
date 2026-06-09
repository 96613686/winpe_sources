# CVsActivityLogSingleton::Instance(ActivityLogParams *)

- ea: `0x140003210`
- end: `0x1400033e6`
- name: `?Instance@CVsActivityLogSingleton@@SAPEAV1@PEAUActivityLogParams@@@Z`
- size: `470`
- prototype: `struct CVsActivityLogSingleton *__fastcall(struct ActivityLogParams *)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x140003f60`
- `0x140003fd0`
- `0x140005020`
- `0x140007b08`
- `0x140007d78`
- `0x140008488`
- `0x14000a720`
- `0x14002cc50`
- `0x140031800`
- `0x140064190`
- `0x140064220`
- `0x1400642e0`

## callees

- `0x140001040`
- `0x140002160`
- `0x140002c10`
- `0x140003210`
- `0x140015d30`
- `0x14002ce80`
- `0x140033ab0`
- `0x140064d80`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x140003299`
- `KERNEL32!SetEnvironmentVariableW` at `0x140003299`
- `KERNEL32!EnterCriticalSection` at `0x140003231`
- `KERNEL32!EnterCriticalSection` at `0x140003231`
- `KERNEL32!LeaveCriticalSection` at `0x1400033c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400033c2`
- `ole32!CoCreateGuid` at `0x140003278`
- `ole32!CoCreateGuid` at `0x140003278`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct CVsActivityLogSingleton *__fastcall CVsActivityLogSingleton::Instance(struct ActivityLogParams *a1)
{
  CVsActivityLogSingletonImpl *v2; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  CVsActivityLogBufferedSingletonImpl *v4; // rax
  CVsActivityLogBufferedSingletonImpl *v5; // rbx
  _QWORD *v6; // rdx
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF
  CVsActivityLogBufferedSingletonImpl *v9; // [rsp+50h] [rbp+18h]

  EnterCriticalSection(&CVsActivityLogSingleton::ms_SyncObject);
  if ( !CVsActivityLogSingleton::ms_pActivityLogParams )
  {
    if ( !a1 )
      goto LABEL_20;
    CVsActivityLogSingleton::ms_pActivityLogParams = a1;
  }
  if ( !CVsActivityLogSingleton::ms_pInstance && !CVsActivityLogSingleton::ms_bTerminated )
  {
    CoCreateGuid(&CVsActivityLogSingleton::ms_guidLogId);
    if ( *((_DWORD *)CVsActivityLogSingleton::ms_pActivityLogParams + 2) )
    {
      SetEnvironmentVariableW(L"VSLogActivity", L"1");
      v2 = (CVsActivityLogSingletonImpl *)operator new(0x38u);
      v8 = (__int64)v2;
      if ( v2 )
      {
        *(_OWORD *)v2 = 0;
        *((_OWORD *)v2 + 1) = 0;
        *((_OWORD *)v2 + 2) = 0;
        *((_QWORD *)v2 + 6) = 0;
        v2 = CVsActivityLogSingletonImpl::CVsActivityLogSingletonImpl(
               v2,
               CVsActivityLogSingleton::ms_pActivityLogParams);
      }
      CVsActivityLogSingleton::ms_pInstance = v2;
    }
    else
    {
      v8 = 0;
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v8 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
      if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableA(
                           &v8,
                           L"VSLogActivity") )
      {
        v4 = (CVsActivityLogBufferedSingletonImpl *)operator new(0x38u);
        v9 = v4;
        if ( v4 )
        {
          *(_OWORD *)v4 = 0;
          *((_OWORD *)v4 + 1) = 0;
          *((_OWORD *)v4 + 2) = 0;
          *((_QWORD *)v4 + 6) = 0;
          v4 = CVsActivityLogSingletonImpl::CVsActivityLogSingletonImpl(
                 v4,
                 CVsActivityLogSingleton::ms_pActivityLogParams);
        }
      }
      else
      {
        v4 = (CVsActivityLogBufferedSingletonImpl *)operator new(0xE0u);
        v5 = v4;
        v9 = v4;
        if ( v4 )
        {
          memset_0(v4, 0, 0xE0u);
          v4 = CVsActivityLogBufferedSingletonImpl::CVsActivityLogBufferedSingletonImpl(
                 v5,
                 CVsActivityLogSingleton::ms_pActivityLogParams);
        }
      }
      CVsActivityLogSingleton::ms_pInstance = v4;
      v6 = (_QWORD *)(v8 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 - 24 + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
      }
    }
  }
  a1 = CVsActivityLogSingleton::ms_pInstance;
LABEL_20:
  LeaveCriticalSection(&CVsActivityLogSingleton::ms_SyncObject);
  return a1;
}

```

## disassembly

```asm
0x140003210  mov     [rsp+arg_0], rbx
0x140003215  push    rsi
0x140003216  sub     rsp, 30h
0x14000321a  mov     rbx, rcx
0x14000321d  lea     rsi, ?ms_SyncObject@CVsActivityLogSingleton@@1VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection CVsActivityLogSingleton::ms_SyncObject
0x140003224  mov     [rsp+38h+var_18], rsi
0x140003229  mov     [rsp+38h+var_10], 0
0x14000322e  mov     rcx, rsi; lpCriticalSection
0x140003231  call    cs:__imp_EnterCriticalSection
0x140003237  mov     [rsp+38h+var_10], 1
0x14000323c  cmp     cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA, 0; ActivityLogParams * CVsActivityLogSingleton::ms_pActivityLogParams
0x140003244  jnz     short loc_140003256
0x140003246  test    rbx, rbx
0x140003249  jz      loc_1400033BF
0x14000324f  mov     cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA, rbx; ActivityLogParams * CVsActivityLogSingleton::ms_pActivityLogParams
0x140003256  cmp     cs:?ms_pInstance@CVsActivityLogSingleton@@0PEAV1@EA, 0; CVsActivityLogSingleton * CVsActivityLogSingleton::ms_pInstance
0x14000325e  jnz     loc_1400033B8
0x140003264  cmp     cs:?ms_bTerminated@CVsActivityLogSingleton@@0_NA, 0; bool CVsActivityLogSingleton::ms_bTerminated
0x14000326b  jnz     loc_1400033B8
0x140003271  lea     rcx, ?ms_guidLogId@CVsActivityLogSingleton@@0U_GUID@@A; pguid
0x140003278  call    cs:__imp_CoCreateGuid
0x14000327e  mov     rax, cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA; ActivityLogParams * CVsActivityLogSingleton::ms_pActivityLogParams
0x140003285  cmp     dword ptr [rax+8], 0
0x140003289  jz      short loc_1400032E3
0x14000328b  lea     rdx, Value; "1"
0x140003292  lea     rcx, Name; "VSLogActivity"
0x140003299  call    cs:__imp_SetEnvironmentVariableW
0x14000329f  mov     ecx, 38h ; '8'; Size
0x1400032a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400032a9  mov     [rsp+38h+arg_8], rax
0x1400032ae  test    rax, rax
0x1400032b1  jz      short loc_1400032D7
0x1400032b3  xorps   xmm0, xmm0
0x1400032b6  xor     ecx, ecx
0x1400032b8  movups  xmmword ptr [rax], xmm0
0x1400032bb  movups  xmmword ptr [rax+10h], xmm0
0x1400032bf  movups  xmmword ptr [rax+20h], xmm0
0x1400032c3  mov     [rax+30h], rcx
0x1400032c7  mov     rdx, cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA; struct ActivityLogParams *
0x1400032ce  mov     rcx, rax; this
0x1400032d1  call    ??0CVsActivityLogSingletonImpl@@IEAA@PEAUActivityLogParams@@@Z; CVsActivityLogSingletonImpl::CVsActivityLogSingletonImpl(ActivityLogParams *)
0x1400032d6  nop
0x1400032d7  mov     cs:?ms_pInstance@CVsActivityLogSingleton@@0PEAV1@EA, rax; CVsActivityLogSingleton * CVsActivityLogSingleton::ms_pInstance
0x1400032de  jmp     loc_1400033B8
0x1400032e3  and     [rsp+38h+arg_8], 0
0x1400032e9  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400032ee  mov     rcx, rax
0x1400032f1  test    rax, rax
0x1400032f4  jz      loc_1400033DB
0x1400032fa  mov     rax, [rax]
0x1400032fd  call    qword ptr [rax+18h]
0x140003300  add     rax, 18h
0x140003304  mov     [rsp+38h+arg_8], rax
0x140003309  lea     rdx, Name; "VSLogActivity"
0x140003310  lea     rcx, [rsp+38h+arg_8]
0x140003315  call    ?GetEnvironmentVariableA@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableA(ushort const *)
0x14000331a  test    eax, eax
0x14000331c  jz      short loc_140003358
0x14000331e  mov     ecx, 38h ; '8'; Size
0x140003323  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003328  mov     [rsp+38h+arg_10], rax
0x14000332d  test    rax, rax
0x140003330  jz      short loc_140003356
0x140003332  xorps   xmm0, xmm0
0x140003335  xor     ecx, ecx
0x140003337  movups  xmmword ptr [rax], xmm0
0x14000333a  movups  xmmword ptr [rax+10h], xmm0
0x14000333e  movups  xmmword ptr [rax+20h], xmm0
0x140003342  mov     [rax+30h], rcx
0x140003346  mov     rdx, cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA; struct ActivityLogParams *
0x14000334d  mov     rcx, rax; this
0x140003350  call    ??0CVsActivityLogSingletonImpl@@IEAA@PEAUActivityLogParams@@@Z; CVsActivityLogSingletonImpl::CVsActivityLogSingletonImpl(ActivityLogParams *)
0x140003355  nop
0x140003356  jmp     short loc_14000338F
0x140003358  mov     ecx, 0E0h; Size
0x14000335d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003362  mov     rbx, rax
0x140003365  mov     [rsp+38h+arg_10], rax
0x14000336a  test    rax, rax
0x14000336d  jz      short loc_14000338F
0x14000336f  xor     edx, edx; Val
0x140003371  mov     r8d, 0E0h; Size
0x140003377  mov     rcx, rax; void *
0x14000337a  call    memset_0
0x14000337f  mov     rdx, cs:?ms_pActivityLogParams@CVsActivityLogSingleton@@0PEAUActivityLogParams@@EA; struct ActivityLogParams *
0x140003386  mov     rcx, rbx; this
0x140003389  call    ??0CVsActivityLogBufferedSingletonImpl@@IEAA@PEAUActivityLogParams@@@Z; CVsActivityLogBufferedSingletonImpl::CVsActivityLogBufferedSingletonImpl(ActivityLogParams *)
0x14000338e  nop
0x14000338f  mov     cs:?ms_pInstance@CVsActivityLogSingleton@@0PEAV1@EA, rax; CVsActivityLogSingleton * CVsActivityLogSingleton::ms_pInstance
0x140003396  mov     rdx, [rsp+38h+arg_8]
0x14000339b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000339f  or      eax, 0FFFFFFFFh
0x1400033a2  lock xadd [rdx+10h], eax
0x1400033a7  sub     eax, 1
0x1400033aa  jg      short loc_1400033B8
0x1400033ac  lfence
0x1400033af  mov     rcx, [rdx]
0x1400033b2  mov     rax, [rcx]
0x1400033b5  call    qword ptr [rax+8]
0x1400033b8  mov     rbx, cs:?ms_pInstance@CVsActivityLogSingleton@@0PEAV1@EA; CVsActivityLogSingleton * CVsActivityLogSingleton::ms_pInstance
0x1400033bf  mov     rcx, rsi; lpCriticalSection
0x1400033c2  call    cs:__imp_LeaveCriticalSection
0x1400033c8  mov     [rsp+38h+var_10], 0
0x1400033cd  mov     rax, rbx
0x1400033d0  mov     rbx, [rsp+38h+arg_0]
0x1400033d5  add     rsp, 30h
0x1400033d9  pop     rsi
0x1400033da  retn
0x1400033db  mov     ecx, 80004005h; int
0x1400033e0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
