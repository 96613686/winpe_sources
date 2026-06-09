# CLogState::_DoWrapAround(void)

- ea: `0x180009934`
- end: `0x180009af7`
- name: `?_DoWrapAround@CLogState@@AEAAXXZ`
- size: `451`
- prototype: `void __fastcall(CLogState *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009298`
- `0x180009600`
- `0x180009754`

## callees

- `0x180009934`
- `0x18000d998`
- `0x18001266c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000999c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000999c`

## string_xrefs

- `0x180009a42`: `com\complus\dtc\dtc\log\logmgr\src\logstate.cpp`
- `0x180009ab2`: `com\complus\dtc\dtc\log\logmgr\src\logstate.cpp`

## pseudocode

```c
void __fastcall CLogState::_DoWrapAround(CLogState *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // edx
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  ulong pExceptionObject; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+10h] BYREF

  if ( *((_DWORD *)this + 8) > *((_DWORD *)this + 6) )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 19) + 24LL);
    if ( v8 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, 4097, 4);
      if ( v9 < 0 )
        TraceFile(
          v9,
          "failed in m_pCLogMgr->m_pIDtcTrace->Trace",
          "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstate.cpp",
          0x42Eu);
    }
    pExceptionObject = -1073737670;
    throw &pExceptionObject;
  }
  v2 = *(unsigned int *)this;
  if ( *((_DWORD *)this + 12) == v2 + 32 )
  {
    pExceptionObject = -1073737699;
    throw &pExceptionObject;
  }
  v3 = *((_DWORD *)this + 32);
  v4 = ++*((_DWORD *)this + 7);
  *((_DWORD *)this + 31) = v3;
  v5 = *((_QWORD *)this + 19);
  *((_DWORD *)this + 30) = v2;
  *((_DWORD *)this + 3) = 0;
  *((_DWORD *)this + 32) = 0;
  **(_DWORD **)(v5 + 392) = v4;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 19) + 392LL) + 16LL) = (*(_QWORD *)&SystemTimeAsFileTime
                                                                   - *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 19)
                                                                                           + 392LL)
                                                                               + 8LL))
                                                                  / 0x2710uLL;
  *(struct _FILETIME *)(*(_QWORD *)(*((_QWORD *)this + 19) + 392LL) + 8LL) = SystemTimeAsFileTime;
  *((_DWORD *)this + 6) = *((_DWORD *)this + 30) + 32;
  v6 = *(_QWORD *)(*((_QWORD *)this + 19) + 24LL);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 24LL))(v6, 4100, 4);
    if ( v7 < 0 )
      TraceFile(
        v7,
        "failed in m_pCLogMgr->m_pIDtcTrace->Trace",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstate.cpp",
        0x440u);
  }
}

```

## disassembly

```asm
0x180009934  push    rbx
0x180009936  sub     rsp, 50h
0x18000993a  mov     eax, [rcx+18h]
0x18000993d  mov     rbx, rcx
0x180009940  cmp     [rcx+20h], eax
0x180009943  ja      loc_180009A5D
0x180009949  mov     ecx, [rcx]
0x18000994b  mov     eax, [rbx+30h]
0x18000994e  lea     rdx, [rcx+20h]
0x180009952  cmp     rax, rdx
0x180009955  jz      loc_180009ADD
0x18000995b  mov     eax, [rbx+80h]
0x180009961  inc     dword ptr [rbx+1Ch]
0x180009964  mov     edx, [rbx+1Ch]
0x180009967  mov     [rbx+7Ch], eax
0x18000996a  mov     rax, [rbx+98h]
0x180009971  mov     [rbx+78h], ecx
0x180009974  mov     dword ptr [rbx+0Ch], 0
0x18000997b  mov     dword ptr [rbx+80h], 0
0x180009985  mov     rcx, [rax+188h]
0x18000998c  mov     [rcx], edx
0x18000998e  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009993  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000999c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800099a2  mov     rax, [rbx+98h]
0x1800099a9  mov     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800099ae  mov     r8, [rax+188h]
0x1800099b5  mov     rax, 346DC5D63886594Bh
0x1800099bf  sub     rcx, [r8+8]
0x1800099c3  mul     rcx
0x1800099c6  shr     rdx, 0Bh
0x1800099ca  mov     [r8+10h], rdx
0x1800099ce  mov     rax, [rbx+98h]
0x1800099d5  mov     rcx, [rax+188h]
0x1800099dc  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800099e1  mov     [rcx+8], rax
0x1800099e5  mov     eax, [rbx+78h]
0x1800099e8  add     eax, 20h ; ' '
0x1800099eb  mov     [rbx+18h], eax
0x1800099ee  mov     rax, [rbx+98h]
0x1800099f5  mov     rcx, [rax+18h]
0x1800099f9  test    rcx, rcx
0x1800099fc  jz      short loc_180009A57
0x1800099fe  mov     rax, [rcx]
0x180009a01  xor     r9d, r9d
0x180009a04  mov     [rsp+58h+var_20], 0
0x180009a0d  mov     edx, 1004h
0x180009a12  mov     [rsp+58h+var_28], 0
0x180009a1b  mov     [rsp+58h+var_30], 0
0x180009a23  mov     rax, [rax+18h]
0x180009a27  lea     r8d, [r9+4]
0x180009a2b  mov     [rsp+58h+var_38], 8000101Fh
0x180009a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a38  test    eax, eax
0x180009a3a  jns     short loc_180009A57
0x180009a3c  mov     r9d, 440h; unsigned int
0x180009a42  lea     r8, aComComplusDtcD_2; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180009a49  lea     rdx, aFailedInMPclog; "failed in m_pCLogMgr->m_pIDtcTrace->Tra"...
0x180009a50  mov     ecx, eax; int
0x180009a52  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180009a57  add     rsp, 50h
0x180009a5b  pop     rbx
0x180009a5c  retn
0x180009a5d  mov     rax, [rcx+98h]
0x180009a64  mov     ebx, 0C000103Ah
0x180009a69  mov     rcx, [rax+18h]
0x180009a6d  test    rcx, rcx
0x180009a70  jz      short loc_180009AC7
0x180009a72  mov     rax, [rcx]
0x180009a75  xor     r9d, r9d
0x180009a78  mov     [rsp+58h+var_20], 0
0x180009a81  mov     edx, 1001h
0x180009a86  mov     [rsp+58h+var_28], 0
0x180009a8f  mov     [rsp+58h+var_30], 0
0x180009a97  mov     rax, [rax+18h]
0x180009a9b  lea     r8d, [r9+4]
0x180009a9f  mov     [rsp+58h+var_38], ebx
0x180009aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa8  test    eax, eax
0x180009aaa  jns     short loc_180009AC7
0x180009aac  mov     r9d, 42Eh; unsigned int
0x180009ab2  lea     r8, aComComplusDtcD_2; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180009ab9  lea     rdx, aFailedInMPclog; "failed in m_pCLogMgr->m_pIDtcTrace->Tra"...
0x180009ac0  mov     ecx, eax; int
0x180009ac2  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180009ac7  lea     rdx, _TI1K; pThrowInfo
0x180009ace  mov     [rsp+58h+pExceptionObject], ebx
0x180009ad2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009ad7  call    _CxxThrowException_0
0x180009add  lea     rdx, _TI1K; pThrowInfo
0x180009ae4  mov     [rsp+58h+pExceptionObject], 0C000101Dh
0x180009aec  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009af1  call    _CxxThrowException_0
```
