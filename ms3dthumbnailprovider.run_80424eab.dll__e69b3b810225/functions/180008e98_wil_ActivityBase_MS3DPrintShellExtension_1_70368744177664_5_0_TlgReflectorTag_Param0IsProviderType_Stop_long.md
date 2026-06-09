# wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180008e98`
- end: `0x180009066`
- name: `?Stop@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800079a0`

## callees

- `0x1800018dc`
- `0x180001ef0`
- `0x180002954`
- `0x18000705c`
- `0x180007c04`
- `0x180008e98`
- `0x180009820`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008f4e`
- `KERNEL32!GetCurrentThreadId` at `0x180008fda`
- `KERNEL32!GetCurrentThreadId` at `0x180008f4e`
- `KERNEL32!GetCurrentThreadId` at `0x180008fda`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008ef7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008ef7`

## string_xrefs

- `0x180008ff5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 *v10; // rcx
  const struct wil::FailureInfo *v11; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  void *retaddr; // [rsp+128h] [rbp+28h]

  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v15, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v15, v11);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    result = (__int64)MS3DPrintShellExtension::Provider();
    v8 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = a2;
        v14 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v21 = 4;
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v8, byte_18000DEDB, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v15);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v9 = a1 + 288;
    if ( *(_DWORD *)(v9 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v9 + 24) = 0;
    v10 = *(__int64 **)v9;
    while ( 1 )
    {
      result = *v10;
      if ( !*v10 )
        break;
      if ( result == v9 )
      {
        result = *(_QWORD *)(v9 + 16);
        *v10 = result;
        break;
      }
      v10 = (__int64 *)(result + 16);
      *(_QWORD *)v9 = result + 16;
    }
    *(_QWORD *)v9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008e98  push    rbp
0x180008e9a  push    rbx
0x180008e9b  push    rsi
0x180008e9c  push    rdi
0x180008e9d  lea     rbp, [rsp-8]
0x180008ea2  sub     rsp, 108h
0x180008ea9  mov     rax, cs:__security_cookie
0x180008eb0  xor     rax, rsp
0x180008eb3  mov     [rbp+20h+var_30], rax
0x180008eb7  mov     esi, edx
0x180008eb9  mov     rbx, rcx
0x180008ebc  lea     rdx, [rsp+120h+SRWLock]
0x180008ec1  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008ec6  mov     rax, [rbx+110h]
0x180008ecd  mov     edi, [rax+0F8h]
0x180008ed3  cmp     edi, 1
0x180008ed6  jl      loc_180009049
0x180008edc  cmp     dword ptr [rax+48h], 0
0x180008ee0  jl      short loc_180008EE5
0x180008ee2  mov     [rax+48h], esi
0x180008ee5  dec     edi
0x180008ee7  mov     [rax+0F8h], edi
0x180008eed  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x180008ef2  test    rcx, rcx
0x180008ef5  jz      short loc_180008EFD
0x180008ef7  call    cs:__imp_ReleaseSRWLockExclusive
0x180008efd  test    edi, edi
0x180008eff  jnz     short loc_180008F15
0x180008f01  mov     rax, [rbx]
0x180008f04  mov     rcx, rbx
0x180008f07  mov     rax, [rax+8]
0x180008f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f10  jmp     loc_180008FCA
0x180008f15  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x180008f1a  mov     rdi, rax
0x180008f1d  mov     ecx, [rax]
0x180008f1f  cmp     ecx, 5
0x180008f22  jbe     loc_180008FCA
0x180008f28  mov     rax, [rax+18h]
0x180008f2c  mov     rcx, [rdi+10h]
0x180008f30  mov     rdx, 400000000000h
0x180008f3a  test    rdx, rcx
0x180008f3d  jz      loc_180008FCA
0x180008f43  mov     rcx, rax
0x180008f46  and     rcx, rdx
0x180008f49  cmp     rcx, rax
0x180008f4c  jnz     short loc_180008FCA
0x180008f4e  call    cs:__imp_GetCurrentThreadId
0x180008f54  mov     [rsp+120h+var_F0], eax
0x180008f58  mov     dword ptr [rsp+120h+SRWLock], esi
0x180008f5c  mov     [rsp+120h+var_E0], 1000000h
0x180008f65  lea     rax, [rsp+120h+var_F0]
0x180008f6a  mov     [rbp+20h+var_90], rax
0x180008f6e  mov     [rbp+20h+var_88], 4
0x180008f76  lea     rax, [rsp+120h+SRWLock]
0x180008f7b  mov     [rbp+20h+var_A0], rax
0x180008f7f  mov     [rbp+20h+var_98], 4
0x180008f87  lea     rax, [rsp+120h+var_E0]
0x180008f8c  mov     [rsp+120h+var_B0], rax
0x180008f91  mov     [rsp+120h+var_A8], 8
0x180008f9a  mov     r8, [rbx+110h]
0x180008fa1  add     r8, 8
0x180008fa5  lea     rax, [rsp+120h+var_D0]
0x180008faa  mov     [rsp+120h+var_F8], rax
0x180008faf  mov     [rsp+120h+var_100], 5
0x180008fb7  xor     r9d, r9d
0x180008fba  lea     rdx, byte_18000DEDB
0x180008fc1  mov     rcx, rdi
0x180008fc4  call    _tlgWriteTransfer_EventWriteTransfer
0x180008fc9  nop
0x180008fca  cmp     dword ptr [rbx+138h], 0
0x180008fd1  jz      short loc_180009031
0x180008fd3  add     rbx, 120h
0x180008fda  call    cs:__imp_GetCurrentThreadId
0x180008fe0  cmp     [rbx+18h], eax
0x180008fe3  jz      short loc_180009001
0x180008fe5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180008fec  test    rax, rax
0x180008fef  jz      short loc_180009001
0x180008ff1  mov     rdx, [rbp+28h]
0x180008ff5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180008ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009001  mov     dword ptr [rbx+18h], 0
0x180009008  mov     rcx, [rbx]
0x18000900b  jmp     short loc_180009019
0x18000900d  cmp     rax, rbx
0x180009010  jz      short loc_180009023
0x180009012  lea     rcx, [rax+10h]
0x180009016  mov     [rbx], rcx
0x180009019  mov     rax, [rcx]
0x18000901c  test    rax, rax
0x18000901f  jnz     short loc_18000900D
0x180009021  jmp     short loc_18000902A
0x180009023  mov     rax, [rbx+10h]
0x180009027  mov     [rcx], rax
0x18000902a  mov     qword ptr [rbx], 0
0x180009031  mov     rcx, [rbp+20h+var_30]
0x180009035  xor     rcx, rsp; StackCookie
0x180009038  call    __security_check_cookie
0x18000903d  add     rsp, 108h
0x180009044  pop     rdi
0x180009045  pop     rsi
0x180009046  pop     rbx
0x180009047  pop     rbp
0x180009048  retn
0x180009049  xor     edx, edx; Val
0x18000904b  mov     r8d, 98h; Size
0x180009051  lea     rcx, [rsp+120h+var_D0]; void *
0x180009056  call    memset_0
0x18000905b  lea     rcx, [rsp+120h+var_D0]; this
0x180009060  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
