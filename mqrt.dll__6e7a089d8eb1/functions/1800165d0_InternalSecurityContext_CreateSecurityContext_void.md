# InternalSecurityContext::CreateSecurityContext(void)

- ea: `0x1800165d0`
- end: `0x1800166d4`
- name: `?CreateSecurityContext@InternalSecurityContext@@SAPEAV1@XZ`
- size: `260`
- prototype: `struct InternalSecurityContext *(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000dc48`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x18000a4f4`
- `0x180013c74`
- `0x1800165d0`
- `0x18001753c`
- `0x180021010`
- `0x180023c5a`
- `0x180026010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct InternalSecurityContext *InternalSecurityContext::CreateSecurityContext(void)
{
  _DWORD *v0; // rax
  RTSecurityContextBase *v1; // rdi
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  RTSecurityContextBase *v7; // [rsp+50h] [rbp+8h] BYREF

  v0 = MmAllocate(0x48u);
  v1 = (RTSecurityContextBase *)v0;
  v7 = (RTSecurityContextBase *)v0;
  if ( v0 )
  {
    memset_0(v0 + 2, 0, 0x40u);
    *((_DWORD *)v1 + 8) = 1;
    *((_DWORD *)v1 + 15) = 1;
    *((_DWORD *)v1 + 16) = 2;
    *(_QWORD *)v1 = &InternalSecurityContext::`vftable';
  }
  else
  {
    v1 = 0;
  }
  v7 = v1;
  v2 = RTSecurityContextBase::InitializeUserInfo(v1);
  v3 = v2;
  if ( v2 < 0 )
  {
    LogMsgHR(v2, (wchar_t *)L"rt/rtsecctx", 0xFAu);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v3);
    throw (bad_hresult *)pExceptionObject;
  }
  v4 = (**(__int64 (__fastcall ***)(RTSecurityContextBase *, _QWORD))v1)(v1, 0);
  if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 32),
      11,
      WPP_4429bf9cee813cde9fee94052f370384_Traceguids,
      (unsigned int)v4);
  v7 = 0;
  P<InternalSecurityContext>::~P<InternalSecurityContext>(&v7);
  return v1;
}

```

## disassembly

```asm
0x1800165d0  mov     [rsp+arg_8], rbx
0x1800165d5  push    rdi
0x1800165d6  sub     rsp, 40h
0x1800165da  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800165df  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800165e4  mov     rdi, rax
0x1800165e7  mov     [rsp+48h+arg_0], rax
0x1800165ec  test    rax, rax
0x1800165ef  jz      short loc_180016621
0x1800165f1  xor     edx, edx; Val
0x1800165f3  lea     r8d, [rdx+40h]; Size
0x1800165f7  lea     rcx, [rax+8]; void *
0x1800165fb  call    memset_0
0x180016600  mov     dword ptr [rdi+20h], 1
0x180016607  mov     dword ptr [rdi+3Ch], 1
0x18001660e  mov     dword ptr [rdi+40h], 2
0x180016615  lea     rax, ??_7InternalSecurityContext@@6B@; const InternalSecurityContext::`vftable'
0x18001661c  mov     [rdi], rax
0x18001661f  jmp     short loc_180016623
0x180016621  xor     edi, edi
0x180016623  mov     [rsp+48h+arg_0], rdi
0x180016628  mov     rcx, rdi; this
0x18001662b  call    ?InitializeUserInfo@RTSecurityContextBase@@QEAAJXZ; RTSecurityContextBase::InitializeUserInfo(void)
0x180016630  mov     ebx, eax
0x180016632  test    eax, eax
0x180016634  jns     short loc_180016668
0x180016636  mov     r8d, 0FAh; unsigned __int16
0x18001663c  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016643  mov     ecx, eax; int
0x180016645  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001664a  mov     edx, ebx; unsigned int
0x18001664c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180016651  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180016656  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x18001665d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016662  call    _CxxThrowException_0
0x180016668  mov     rax, [rdi]
0x18001666b  xor     edx, edx
0x18001666d  mov     rcx, rdi
0x180016670  mov     rax, [rax]
0x180016673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016678  test    eax, eax
0x18001667a  jns     short loc_1800166B3
0x18001667c  lea     rdx, WPP_GLOBAL_Control
0x180016683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001668a  cmp     rcx, rdx
0x18001668d  jz      short loc_1800166B3
0x18001668f  test    byte ptr [rcx+10Ch], 1
0x180016696  jz      short loc_1800166B3
0x180016698  mov     edx, 0Bh
0x18001669d  mov     r9d, eax
0x1800166a0  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x1800166a7  mov     rcx, [rcx+100h]
0x1800166ae  call    WPP_SF_d
0x1800166b3  mov     [rsp+48h+arg_0], 0
0x1800166bc  lea     rcx, [rsp+48h+arg_0]
0x1800166c1  call    ??1?$P@VInternalSecurityContext@@@@QEAA@XZ; P<InternalSecurityContext>::~P<InternalSecurityContext>(void)
0x1800166c6  mov     rax, rdi
0x1800166c9  mov     rbx, [rsp+48h+arg_8]
0x1800166ce  add     rsp, 40h
0x1800166d2  pop     rdi
0x1800166d3  retn
```
