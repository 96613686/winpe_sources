# CJob::ValidateFileLimit(ulong)

- ea: `0x1800942a0`
- end: `0x1800944b9`
- name: `?ValidateFileLimit@CJob@@IEAAXK@Z`
- size: `537`
- prototype: `void __fastcall(CJob *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008abdc`

## callees

- `0x180016d60`
- `0x1800302e8`
- `0x180066e6c`
- `0x1800942a0`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800b13b4`
- `0x1800b674c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800943df`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800943df`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800942ff`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009431a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180094335`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800942ff`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009431a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180094335`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CJob::ValidateFileLimit(CJob *this, int a2)
{
  PSID *v4; // rdi
  bool v5; // di
  unsigned int v6; // edi
  unsigned int v7; // esi
  __int64 v8; // [rsp+38h] [rbp-C8h] BYREF
  volatile signed __int32 *v9; // [rsp+40h] [rbp-C0h]
  _BYTE v10[24]; // [rsp+48h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+7Ch] [rbp-84h]
  int v15; // [rsp+80h] [rbp-80h]
  OLECHAR sz[256]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = (PSID *)(*(__int64 (__fastcall **)(CJob *, _BYTE *))(*(_QWORD *)this + 16LL))(this, v10);
  v5 = 0;
  if ( !EqualSid(*v4, *((PSID *)g_GlobalInfo + 11))
    && !EqualSid(*v4, *((PSID *)g_GlobalInfo + 17))
    && !EqualSid(*v4, *((PSID *)g_GlobalInfo + 19)) )
  {
    v8 = *((_QWORD *)g_GlobalInfo + 7);
    v9 = (volatile signed __int32 *)*((_QWORD *)g_GlobalInfo + 8);
    _InterlockedIncrement(v9);
    if ( (unsigned int)CheckClientGroupMembership(&v8) )
    {
      if ( *((_BYTE *)g_Manager + 1496) )
        v5 = 1;
    }
  }
  SidHandle::~SidHandle((SidHandle *)v10);
  if ( v5 )
  {
    v6 = *((_DWORD *)g_Manager + 377);
    v7 = ((__int64)(*((_QWORD *)this + 107) - *((_QWORD *)this + 106)) >> 3) + a2;
    if ( v6 < v7 )
    {
      memset_0(sz, 0, 0x1FEu);
      if ( !StringFromGUID2((const GUID *const)((char *)this + 676), sz, 39) )
        StringCchCopyW(sz, 0xFFu, (const unsigned __int16 *)(*((_QWORD *)this + 87) + 12LL));
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)&WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          (unsigned int)sz,
          v7,
          v6);
      EVENT_LOG::ReportObjectLimitExceededFailure(g_EventLogger, &EVT_EXCEEDED_FILELIMIT_PER_JOB, sz, v7, v6);
      v12 = 0;
      pExceptionObject = &ComError::`vftable';
      v13 = -2145386415;
      v14 = 1320;
      v15 = 1;
      throw (ComError *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800942a0  mov     [rsp-8+arg_10], rbx
0x1800942a5  push    rbp
0x1800942a6  push    rsi
0x1800942a7  push    rdi
0x1800942a8  lea     rbp, [rsp-1D0h]
0x1800942b0  sub     rsp, 2D0h
0x1800942b7  mov     rax, cs:__security_cookie
0x1800942be  xor     rax, rsp
0x1800942c1  mov     [rbp+1E0h+var_20], rax
0x1800942c8  mov     esi, edx
0x1800942ca  mov     rbx, rcx
0x1800942cd  mov     [rsp+2E0h+var_2B0], 0
0x1800942d5  mov     rax, [rcx]
0x1800942d8  lea     rdx, [rsp+2E0h+var_298]
0x1800942dd  mov     rax, [rax+10h]
0x1800942e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942e6  mov     rdi, rax
0x1800942e9  mov     [rsp+2E0h+var_2B0], 1
0x1800942f1  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x1800942f8  mov     rdx, [rdx+58h]; pSid2
0x1800942fc  mov     rcx, [rax]; pSid1
0x1800942ff  call    cs:__imp_EqualSid
0x180094305  test    eax, eax
0x180094307  jnz     short loc_18009437E
0x180094309  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180094310  mov     rdx, [rdx+88h]; pSid2
0x180094317  mov     rcx, [rdi]; pSid1
0x18009431a  call    cs:__imp_EqualSid
0x180094320  test    eax, eax
0x180094322  jnz     short loc_18009437E
0x180094324  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18009432b  mov     rdx, [rdx+98h]; pSid2
0x180094332  mov     rcx, [rdi]; pSid1
0x180094335  call    cs:__imp_EqualSid
0x18009433b  test    eax, eax
0x18009433d  jnz     short loc_18009437E
0x18009433f  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180094346  mov     rax, [rcx+38h]
0x18009434a  mov     [rsp+2E0h+var_2A8], rax
0x18009434f  mov     rax, [rcx+40h]
0x180094353  mov     [rsp+2E0h+var_2A0], rax
0x180094358  lock inc dword ptr [rax]
0x18009435b  lea     rcx, [rsp+2E0h+var_2A8]
0x180094360  call    ?CheckClientGroupMembership@@YAJVSidHandle@@@Z; CheckClientGroupMembership(SidHandle)
0x180094365  test    eax, eax
0x180094367  jz      short loc_18009437E
0x180094369  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180094370  cmp     byte ptr [rax+5D8h], 0
0x180094377  jz      short loc_18009437E
0x180094379  mov     dil, 1
0x18009437c  jmp     short loc_180094381
0x18009437e  xor     dil, dil
0x180094381  lea     rcx, [rsp+2E0h+var_298]; this
0x180094386  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18009438b  test    dil, dil
0x18009438e  jz      loc_180094497
0x180094394  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18009439b  mov     edi, [rax+5E4h]
0x1800943a1  mov     rax, [rbx+358h]
0x1800943a8  sub     rax, [rbx+350h]
0x1800943af  sar     rax, 3
0x1800943b3  add     esi, eax
0x1800943b5  cmp     edi, esi
0x1800943b7  jnb     loc_180094497
0x1800943bd  xor     edx, edx; Val
0x1800943bf  mov     r8d, 1FEh; Size
0x1800943c5  lea     rcx, [rbp+1E0h+sz]; void *
0x1800943c9  call    memset_0
0x1800943ce  lea     rcx, [rbx+2A4h]; rguid
0x1800943d5  mov     r8d, 27h ; '''; cchMax
0x1800943db  lea     rdx, [rbp+1E0h+sz]; lpsz
0x1800943df  call    cs:__imp_StringFromGUID2
0x1800943e5  test    eax, eax
0x1800943e7  jnz     short loc_180094402
0x1800943e9  mov     r8, [rbx+2B8h]
0x1800943f0  add     r8, 0Ch; unsigned __int16 *
0x1800943f4  mov     edx, 0FFh; unsigned __int64
0x1800943f9  lea     rcx, [rbp+1E0h+sz]; unsigned __int16 *
0x1800943fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180094402  lea     rax, WPP_GLOBAL_Control
0x180094409  mov     rcx, cs:WPP_GLOBAL_Control
0x180094410  cmp     rcx, rax
0x180094413  jz      short loc_18009443C
0x180094415  test    byte ptr [rcx+1Ch], 4
0x180094419  jz      short loc_18009443C
0x18009441b  mov     edx, 42h ; 'B'
0x180094420  mov     [rsp+2E0h+var_2B8], edi
0x180094424  mov     [rsp+2E0h+var_2C0], esi
0x180094428  lea     r9, [rbp+1E0h+sz]
0x18009442c  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180094433  mov     rcx, [rcx+10h]
0x180094437  call    WPP_SF_Sdd
0x18009443c  mov     [rsp+2E0h+var_2C0], edi; unsigned int
0x180094440  mov     r9d, esi; unsigned int
0x180094443  lea     r8, [rbp+1E0h+sz]; unsigned __int16 *
0x180094447  lea     rdx, EVT_EXCEEDED_FILELIMIT_PER_JOB; struct _EVENT_DESCRIPTOR *
0x18009444e  mov     rcx, cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA; this
0x180094455  call    ?ReportObjectLimitExceededFailure@EVENT_LOG@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKK@Z; EVENT_LOG::ReportObjectLimitExceededFailure(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong)
0x18009445a  xorps   xmm0, xmm0
0x18009445d  movups  [rsp+2E0h+var_278], xmm0
0x180094462  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180094469  mov     [rsp+2E0h+pExceptionObject], rax
0x18009446e  mov     [rsp+2E0h+var_268], 80200051h
0x180094476  mov     [rsp+2E0h+var_264], 528h
0x18009447e  mov     [rbp+1E0h+var_260], 1
0x180094485  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18009448c  lea     rcx, [rsp+2E0h+pExceptionObject]; pExceptionObject
0x180094491  call    _CxxThrowException_0
0x180094497  mov     rcx, [rbp+1E0h+var_20]
0x18009449e  xor     rcx, rsp; StackCookie
0x1800944a1  call    __security_check_cookie
0x1800944a6  mov     rbx, [rsp+2E0h+arg_10]
0x1800944ae  add     rsp, 2D0h
0x1800944b5  pop     rdi
0x1800944b6  pop     rsi
0x1800944b7  pop     rbp
0x1800944b8  retn
```
