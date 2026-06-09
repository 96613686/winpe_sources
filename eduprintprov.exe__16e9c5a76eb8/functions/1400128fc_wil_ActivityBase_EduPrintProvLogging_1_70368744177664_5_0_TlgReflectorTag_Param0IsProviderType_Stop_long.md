# wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1400128fc`
- end: `0x140012ad2`
- name: `?Stop@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14001199c`
- `0x140011bb0`

## callees

- `0x1400016dc`
- `0x140002600`
- `0x140003168`
- `0x14000ace0`
- `0x14000cfac`
- `0x140012014`
- `0x1400128fc`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012961`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400129b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400129b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012a3f`

## string_xrefs

- `0x140012a5a`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 result; // rax
  __int64 v6; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // rbx
  __int64 *v9; // rcx
  const struct wil::FailureInfo *v10; // rdx
  int v11; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v13; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v15; // [rsp+70h] [rbp-39h]
  __int64 v16; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v18; // [rsp+88h] [rbp-21h]
  int *v19; // [rsp+90h] [rbp-19h]
  __int64 v20; // [rsp+98h] [rbp-11h]
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v10);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    result = (__int64)EduPrintProvLogging::Provider();
    v6 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        v19 = &v11;
        v20 = 4;
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(
                   v6,
                   byte_140017F99,
                   *(_QWORD *)(a1 + 272) + 8LL,
                   0,
                   5,
                   v14,
                   CurrentThreadId,
                   0,
                   0x1000000);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v8 = a1 + 288;
    if ( *(_DWORD *)(v8 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v8 + 24) = 0;
    v9 = *(__int64 **)v8;
    while ( 1 )
    {
      result = *v9;
      if ( !*v9 )
        break;
      if ( result == v8 )
      {
        result = *(_QWORD *)(v8 + 16);
        *v9 = result;
        break;
      }
      v9 = (__int64 *)(result + 16);
      *(_QWORD *)v8 = result + 16;
    }
    *(_QWORD *)v8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400128fc  mov     [rsp-8+arg_8], rbx
0x140012901  mov     [rsp-8+arg_10], rdi
0x140012906  push    rbp
0x140012907  lea     rbp, [rsp-57h]
0x14001290c  sub     rsp, 100h
0x140012913  mov     rax, cs:__security_cookie
0x14001291a  xor     rax, rsp
0x14001291d  mov     [rbp+57h+var_10], rax
0x140012921  mov     rbx, rcx
0x140012924  lea     rdx, [rbp+57h+SRWLock]
0x140012928  call    ?LockExclusive@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001292d  mov     rax, [rbx+110h]
0x140012934  mov     edi, [rax+0F8h]
0x14001293a  cmp     edi, 1
0x14001293d  jl      loc_140012AB7
0x140012943  cmp     dword ptr [rax+48h], 0
0x140012947  jl      short loc_140012950
0x140012949  mov     dword ptr [rax+48h], 0
0x140012950  dec     edi
0x140012952  mov     [rax+0F8h], edi
0x140012958  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14001295c  test    rcx, rcx
0x14001295f  jz      short loc_140012967
0x140012961  call    cs:__imp_ReleaseSRWLockExclusive
0x140012967  test    edi, edi
0x140012969  jnz     short loc_14001297F
0x14001296b  mov     rax, [rbx]
0x14001296e  mov     rcx, rbx
0x140012971  mov     rax, [rax+8]
0x140012975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001297a  jmp     loc_140012A2F
0x14001297f  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x140012984  mov     rdi, rax
0x140012987  mov     ecx, [rax]
0x140012989  cmp     ecx, 5
0x14001298c  jbe     loc_140012A2F
0x140012992  mov     rax, [rax+18h]
0x140012996  mov     rcx, [rdi+10h]
0x14001299a  mov     rdx, 400000000000h
0x1400129a4  test    rdx, rcx
0x1400129a7  jz      loc_140012A2F
0x1400129ad  mov     rcx, rax
0x1400129b0  and     rcx, rdx
0x1400129b3  cmp     rcx, rax
0x1400129b6  jnz     short loc_140012A2F
0x1400129b8  call    cs:__imp_GetCurrentThreadId
0x1400129be  mov     [rbp+57h+var_D0], eax
0x1400129c1  mov     dword ptr [rbp+57h+SRWLock], 0
0x1400129c8  mov     [rbp+57h+var_C0], 1000000h
0x1400129d0  lea     rax, [rbp+57h+var_D0]
0x1400129d4  mov     [rbp+57h+var_70], rax
0x1400129d8  mov     [rbp+57h+var_68], 4
0x1400129e0  lea     rax, [rbp+57h+SRWLock]
0x1400129e4  mov     [rbp+57h+var_80], rax
0x1400129e8  mov     [rbp+57h+var_78], 4
0x1400129f0  lea     rax, [rbp+57h+var_C0]
0x1400129f4  mov     [rbp+57h+var_90], rax
0x1400129f8  mov     [rbp+57h+var_88], 8
0x140012a00  mov     r8, [rbx+110h]
0x140012a07  add     r8, 8
0x140012a0b  lea     rax, [rbp+57h+var_B0]
0x140012a0f  mov     [rsp+100h+var_D8], rax
0x140012a14  mov     [rsp+100h+var_E0], 5
0x140012a1c  xor     r9d, r9d
0x140012a1f  lea     rdx, byte_140017F99
0x140012a26  mov     rcx, rdi
0x140012a29  call    _tlgWriteTransfer_EventWriteTransfer
0x140012a2e  nop
0x140012a2f  cmp     dword ptr [rbx+138h], 0
0x140012a36  jz      short loc_140012A96
0x140012a38  add     rbx, 120h
0x140012a3f  call    cs:__imp_GetCurrentThreadId
0x140012a45  cmp     [rbx+18h], eax
0x140012a48  jz      short loc_140012A66
0x140012a4a  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140012a51  test    rax, rax
0x140012a54  jz      short loc_140012A66
0x140012a56  mov     rdx, [rbp+5Fh]
0x140012a5a  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140012a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a66  mov     dword ptr [rbx+18h], 0
0x140012a6d  mov     rcx, [rbx]
0x140012a70  jmp     short loc_140012A7E
0x140012a72  cmp     rax, rbx
0x140012a75  jz      short loc_140012A88
0x140012a77  lea     rcx, [rax+10h]
0x140012a7b  mov     [rbx], rcx
0x140012a7e  mov     rax, [rcx]
0x140012a81  test    rax, rax
0x140012a84  jnz     short loc_140012A72
0x140012a86  jmp     short loc_140012A8F
0x140012a88  mov     rax, [rbx+10h]
0x140012a8c  mov     [rcx], rax
0x140012a8f  mov     qword ptr [rbx], 0
0x140012a96  mov     rcx, [rbp+57h+var_10]
0x140012a9a  xor     rcx, rsp; StackCookie
0x140012a9d  call    __security_check_cookie
0x140012aa2  lea     r11, [rsp+100h+var_s0]
0x140012aaa  mov     rbx, [r11+18h]
0x140012aae  mov     rdi, [r11+20h]
0x140012ab2  mov     rsp, r11
0x140012ab5  pop     rbp
0x140012ab6  retn
0x140012ab7  xor     edx, edx; Val
0x140012ab9  mov     r8d, 98h; Size
0x140012abf  lea     rcx, [rbp+57h+var_B0]; void *
0x140012ac3  call    memset_0
0x140012ac8  lea     rcx, [rbp+57h+var_B0]; this
0x140012acc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
