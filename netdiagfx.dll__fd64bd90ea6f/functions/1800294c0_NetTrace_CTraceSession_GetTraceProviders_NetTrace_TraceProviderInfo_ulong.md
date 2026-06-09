# NetTrace::CTraceSession::GetTraceProviders(NetTrace::TraceProviderInfo * *,ulong *)

- ea: `0x1800294c0`
- end: `0x18002957e`
- name: `?GetTraceProviders@CTraceSession@NetTrace@@UEAAJPEAPEAUTraceProviderInfo@2@PEAK@Z`
- size: `190`
- prototype: `__int64 __fastcall(NetTrace::CTraceSession *__hidden this, struct NetTrace::TraceProviderInfo **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015d64`
- `0x1800293bc`
- `0x1800294c0`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800294ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800294ec`

## pseudocode

```c
__int64 __fastcall NetTrace::CTraceSession::GetTraceProviders(
        NetTrace::CTraceSession *this,
        struct NetTrace::TraceProviderInfo **a2,
        unsigned int *a3)
{
  unsigned int v3; // ebx
  struct NetTrace::TraceProviderInfo *v7; // rax
  struct NetTrace::TraceProviderInfo *v8; // rdi
  unsigned int v9; // ebp
  __int64 v10; // rsi
  _OWORD *NextValue; // rax
  __int64 v12; // rdx
  __int64 i; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 18);
  v7 = (struct NetTrace::TraceProviderInfo *)CoTaskMemAlloc(48 * v3);
  v8 = v7;
  v9 = -2147024882;
  if ( v7 )
  {
    memset_0(v7, 0, 48 * v3);
    v9 = 0;
    v10 = 0;
    for ( i = ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::GetStartPosition((char *)this + 64);
          i;
          *(_OWORD *)((char *)v8 + 8 * v12 + 32) = NextValue[2] )
    {
      if ( (unsigned int)v10 >= v3 )
        break;
      NextValue = (_OWORD *)ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::GetNextValue(
                              (char *)this + 64,
                              &i);
      v12 = 3 * v10;
      v10 = (unsigned int)(v10 + 1);
      v12 *= 2;
      *(_OWORD *)((char *)v8 + 8 * v12) = *NextValue;
      *(_OWORD *)((char *)v8 + 8 * v12 + 16) = NextValue[1];
    }
    *a2 = v8;
    *a3 = v3;
  }
  return v9;
}

```

## disassembly

```asm
0x1800294c0  mov     [rsp+arg_0], rbx
0x1800294c5  mov     [rsp+arg_8], rbp
0x1800294ca  push    rsi
0x1800294cb  push    rdi
0x1800294cc  push    r12
0x1800294ce  push    r14
0x1800294d0  push    r15
0x1800294d2  sub     rsp, 20h
0x1800294d6  mov     ebx, [rcx+48h]
0x1800294d9  mov     r14, rcx
0x1800294dc  mov     r15, r8
0x1800294df  mov     r12, rdx
0x1800294e2  lea     eax, [rbx+rbx*2]
0x1800294e5  shl     eax, 4
0x1800294e8  mov     ecx, eax; cb
0x1800294ea  mov     esi, eax
0x1800294ec  call    cs:__imp_CoTaskMemAlloc
0x1800294f2  mov     rdi, rax
0x1800294f5  mov     ebp, 8007000Eh
0x1800294fa  test    rax, rax
0x1800294fd  jz      short loc_180029565
0x1800294ff  mov     r8d, esi; Size
0x180029502  xor     edx, edx; Val
0x180029504  mov     rcx, rax; void *
0x180029507  call    memset_0
0x18002950c  lea     rcx, [r14+40h]
0x180029510  xor     ebp, ebp
0x180029512  xor     esi, esi
0x180029514  call    ?GetStartPosition@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::GetStartPosition(void)
0x180029519  mov     [rsp+48h+arg_18], rax
0x18002951e  test    rax, rax
0x180029521  jz      short loc_18002955E
0x180029523  cmp     esi, ebx
0x180029525  jnb     short loc_18002955E
0x180029527  lea     rdx, [rsp+48h+arg_18]
0x18002952c  lea     rcx, [r14+40h]
0x180029530  call    ?GetNextValue@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAAAEAUTraceProviderInfo@NetTrace@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::GetNextValue(__POSITION * &)
0x180029535  lea     rdx, [rsi+rsi*2]
0x180029539  inc     esi
0x18002953b  add     rdx, rdx
0x18002953e  movups  xmm0, xmmword ptr [rax]
0x180029541  movups  xmmword ptr [rdi+rdx*8], xmm0
0x180029545  movups  xmm1, xmmword ptr [rax+10h]
0x180029549  movups  xmmword ptr [rdi+rdx*8+10h], xmm1
0x18002954e  movups  xmm0, xmmword ptr [rax+20h]
0x180029552  movups  xmmword ptr [rdi+rdx*8+20h], xmm0
0x180029557  cmp     [rsp+48h+arg_18], rbp
0x18002955c  jnz     short loc_180029523
0x18002955e  mov     [r12], rdi
0x180029562  mov     [r15], ebx
0x180029565  mov     rbx, [rsp+48h+arg_0]
0x18002956a  mov     eax, ebp
0x18002956c  mov     rbp, [rsp+48h+arg_8]
0x180029571  add     rsp, 20h
0x180029575  pop     r15
0x180029577  pop     r14
0x180029579  pop     r12
0x18002957b  pop     rdi
0x18002957c  pop     rsi
0x18002957d  retn
```
