# LogTokenRedemtionStats

- ea: `0x18000e020`
- end: `0x18000e0c5`
- name: `LogTokenRedemtionStats`
- size: `165`
- prototype: `__int64 __fastcall(SqmHelper *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000da68`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000e020`
- `0x18001182c`
- `0x180019720`
- `0x1800198a0`

## string_xrefs

- `0x18000e0a6`: `LogTokenRedemtionStats`

## pseudocode

```c
void __fastcall LogTokenRedemtionStats(SqmHelper *this, __int64 a2)
{
  __int64 v4; // rcx
  int CurrentTimeAsFileTime; // ebx
  const struct _FILETIME *v6; // r8
  unsigned __int64 v7; // rdx
  int *v8; // rax
  int v9; // [rsp+20h] [rbp-18h]
  struct _FILETIME v10; // [rsp+50h] [rbp+18h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  CurrentTimeAsFileTime = DSUtils::GetCurrentTimeAsFileTime(&v10, (struct _FILETIME *)a2);
  if ( CurrentTimeAsFileTime < 0 )
  {
    v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
    v9 = CurrentTimeAsFileTime;
    DSLogger::LogError((DSLogger *)v8, L"LogTokenRedemtionStats", 60, L"Failed to log. hr=0x%x", v9);
  }
  else
  {
    v11 = *(_QWORD *)(a2 + 88);
    v7 = (__int64)((unsigned __int128)(DSUtils::GetFileTimeSpanInMilliSeconds((DSUtils *)&v11, &v10, v6)
                                     * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 7;
    SqmHelper::LogSqmTokenLifetime(this, (const unsigned __int16 *)*(unsigned int *)(a2 + 84), v7 + (v7 >> 63));
  }
}

```

## disassembly

```asm
0x18000e020  mov     rax, rsp
0x18000e023  mov     [rax+8], rbx
0x18000e027  mov     [rax+10h], rsi
0x18000e02b  push    rdi
0x18000e02c  sub     rsp, 30h
0x18000e030  mov     rsi, rcx
0x18000e033  mov     qword ptr [rax+18h], 0
0x18000e03b  lea     rcx, [rax+18h]; lpFileTime
0x18000e03f  mov     rdi, rdx
0x18000e042  call    ?GetCurrentTimeAsFileTime@DSUtils@@YAJPEAU_FILETIME@@@Z; DSUtils::GetCurrentTimeAsFileTime(_FILETIME *)
0x18000e047  mov     ebx, eax
0x18000e049  test    eax, eax
0x18000e04b  js      short loc_18000E090
0x18000e04d  mov     rax, [rdi+58h]
0x18000e051  lea     rdx, [rsp+38h+arg_10]; struct _FILETIME *
0x18000e056  lea     rcx, [rsp+38h+arg_18]; this
0x18000e05b  mov     [rsp+38h+arg_18], rax
0x18000e060  call    ?GetFileTimeSpanInMilliSeconds@DSUtils@@YA_JAEBU_FILETIME@@0@Z; DSUtils::GetFileTimeSpanInMilliSeconds(_FILETIME const &,_FILETIME const &)
0x18000e065  mov     r8, rax
0x18000e068  mov     rcx, rsi; this
0x18000e06b  mov     rax, 20C49BA5E353F7CFh
0x18000e075  imul    r8
0x18000e078  sar     rdx, 7
0x18000e07c  mov     r8, rdx
0x18000e07f  shr     r8, 3Fh
0x18000e083  add     r8, rdx; unsigned int
0x18000e086  mov     edx, [rdi+54h]; unsigned __int16 *
0x18000e089  call    ?LogSqmTokenLifetime@SqmHelper@@YAXPEBGKK@Z; SqmHelper::LogSqmTokenLifetime(ushort const *,ulong,ulong)
0x18000e08e  jmp     short loc_18000E0B5
0x18000e090  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000e095  lea     r9, aFailedToLogHr0; "Failed to log. hr=0x%x"
0x18000e09c  mov     [rsp+38h+var_18], ebx
0x18000e0a0  mov     r8d, 3Ch ; '<'; unsigned int
0x18000e0a6  lea     rdx, aLogtokenredemt; "LogTokenRedemtionStats"
0x18000e0ad  mov     rcx, rax; this
0x18000e0b0  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000e0b5  mov     rbx, [rsp+38h+arg_0]
0x18000e0ba  mov     rsi, [rsp+38h+arg_8]
0x18000e0bf  add     rsp, 30h
0x18000e0c3  pop     rdi
0x18000e0c4  retn
```
