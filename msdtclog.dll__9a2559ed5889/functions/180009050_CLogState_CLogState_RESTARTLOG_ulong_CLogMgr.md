# CLogState::CLogState(_RESTARTLOG &,ulong,CLogMgr *)

- ea: `0x180009050`
- end: `0x180009170`
- name: `??0CLogState@@QEAA@AEAU_RESTARTLOG@@KPEAVCLogMgr@@@Z`
- size: `288`
- prototype: `CLogState *__fastcall(CLogState *__hidden this, struct _RESTARTLOG *, unsigned int, struct CLogMgr *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800065c8`

## callees

- `0x180009050`
- `0x180009848`
- `0x18000d998`
- `0x18001266c`
- `0x18001280a`
- `0x180015010`

## string_xrefs

- `0x180009143`: `com\complus\dtc\dtc\log\logmgr\src\logstate.cpp`

## pseudocode

```c
CLogState *__fastcall CLogState::CLogState(
        CLogState *this,
        struct _RESTARTLOG *a2,
        unsigned int a3,
        struct CLogMgr *a4)
{
  int v5; // ecx
  int v6; // eax
  int v7; // edx
  __int64 v9; // rcx
  int v10; // eax
  ulong pExceptionObject; // [rsp+60h] [rbp+8h] BYREF

  *((_QWORD *)this + 19) = a4;
  if ( *((_DWORD *)a2 + 15) != 65537 )
  {
    v9 = *((_QWORD *)a4 + 3);
    if ( v9 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 24LL))(
              v9,
              4097,
              4,
              0,
              -1073737662,
              0,
              0,
              0);
      if ( v10 < 0 )
        TraceFile(
          v10,
          "m_pCLogMgr->m_pIDtcTrace->Trace",
          "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstate.cpp",
          0x3Du);
    }
    pExceptionObject = -1073737662;
    throw &pExceptionObject;
  }
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 40) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 56) = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 72) = *((_OWORD *)a2 + 3);
  *(_OWORD *)((char *)this + 88) = *((_OWORD *)a2 + 4);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 20);
  v5 = 4 * *((_DWORD *)this + 20);
  *((_DWORD *)this + 1) = *((_DWORD *)this + 14) / a3;
  *((_DWORD *)this + 35) = *((_DWORD *)this + 9);
  v6 = *((_DWORD *)this + 8);
  *(_DWORD *)this = v5;
  *((_DWORD *)this + 33) = v5;
  *((_DWORD *)this + 36) = v6;
  *((_DWORD *)this + 34) = 1;
  memset_0((char *)this + 160, 0, 0x94u);
  CLogState::_ComputeState(this, v7);
  return this;
}

```

## disassembly

```asm
0x180009050  push    rbx
0x180009052  sub     rsp, 50h
0x180009056  mov     r10d, 1
0x18000905c  mov     [rcx+98h], r9
0x180009063  mov     rbx, rcx
0x180009066  cmp     [rdx+3Ch], r10w
0x18000906b  jnz     loc_180009100
0x180009071  cmp     [rdx+3Eh], r10w
0x180009076  jnz     loc_180009100
0x18000907c  movaps  xmm0, xmmword ptr [rdx]
0x18000907f  movups  xmmword ptr [rcx+18h], xmm0
0x180009083  movaps  xmm1, xmmword ptr [rdx+10h]
0x180009087  movups  xmmword ptr [rcx+28h], xmm1
0x18000908b  movaps  xmm0, xmmword ptr [rdx+20h]
0x18000908f  movups  xmmword ptr [rcx+38h], xmm0
0x180009093  movaps  xmm1, xmmword ptr [rdx+30h]
0x180009097  movups  xmmword ptr [rcx+48h], xmm1
0x18000909b  movaps  xmm0, xmmword ptr [rdx+40h]
0x18000909f  movups  xmmword ptr [rcx+58h], xmm0
0x1800090a3  mov     eax, [rdx+50h]
0x1800090a6  xor     edx, edx
0x1800090a8  mov     [rcx+68h], eax
0x1800090ab  mov     eax, [rbx+38h]
0x1800090ae  mov     ecx, [rcx+50h]
0x1800090b1  div     r8d
0x1800090b4  shl     ecx, 2
0x1800090b7  xor     edx, edx; Val
0x1800090b9  mov     [rbx+4], eax
0x1800090bc  mov     r8d, 94h; Size
0x1800090c2  mov     eax, [rbx+24h]
0x1800090c5  mov     [rbx+8Ch], eax
0x1800090cb  mov     eax, [rbx+20h]
0x1800090ce  mov     [rbx], ecx
0x1800090d0  mov     [rbx+84h], ecx
0x1800090d6  lea     rcx, [rbx+0A0h]; void *
0x1800090dd  mov     [rbx+90h], eax
0x1800090e3  mov     [rbx+88h], r10d
0x1800090ea  call    memset_0
0x1800090ef  mov     rcx, rbx; this
0x1800090f2  call    ?_ComputeState@CLogState@@AEAAXH@Z; CLogState::_ComputeState(int)
0x1800090f7  mov     rax, rbx
0x1800090fa  add     rsp, 50h
0x1800090fe  pop     rbx
0x1800090ff  retn
0x180009100  mov     rcx, [r9+18h]
0x180009104  xor     ebx, ebx
0x180009106  test    rcx, rcx
0x180009109  jz      short loc_180009156
0x18000910b  mov     rax, [rcx]
0x18000910e  lea     r8d, [rbx+4]
0x180009112  mov     [rsp+58h+var_20], rbx
0x180009117  xor     r9d, r9d
0x18000911a  mov     [rsp+58h+var_28], rbx
0x18000911f  mov     edx, 1001h
0x180009124  mov     [rsp+58h+var_30], ebx
0x180009128  mov     rax, [rax+18h]
0x18000912c  mov     [rsp+58h+var_38], 0C0001042h
0x180009134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009139  test    eax, eax
0x18000913b  jns     short loc_180009156
0x18000913d  lea     r9d, [rbx+3Dh]; unsigned int
0x180009141  mov     ecx, eax; int
0x180009143  lea     r8, aComComplusDtcD_2; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000914a  lea     rdx, aMPclogmgrMPidt; "m_pCLogMgr->m_pIDtcTrace->Trace"
0x180009151  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180009156  lea     rdx, _TI1K; pThrowInfo
0x18000915d  mov     [rsp+58h+pExceptionObject], 0C0001042h
0x180009165  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000916a  call    _CxxThrowException_0
```
