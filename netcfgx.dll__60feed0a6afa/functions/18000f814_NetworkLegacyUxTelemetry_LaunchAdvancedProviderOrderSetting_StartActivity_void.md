# NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StartActivity(void)

- ea: `0x18000f814`
- end: `0x18000f9b5`
- name: `?StartActivity@LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000da34`

## callees

- `0x1800018dc`
- `0x180001f90`
- `0x18000d570`
- `0x18000df94`
- `0x18000e970`
- `0x18000f814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f89c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f89c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f98a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f98a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f87e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f87e`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StartActivity(
        NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = NetworkLegacyUxLogging::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = NetworkLegacyUxLogging::Provider();
  v6 = v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x400000000000LL) != 0 )
    {
      v7 = v8 & 0x400000000000LL;
      if ( (v8 & 0x400000000000LL) == v8 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v14 = 0;
        v9 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v9 + 4)
          || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
          && !*(_DWORD *)(v9 + 28)
          && !*(_DWORD *)(v9 + 32)
          && !*(_DWORD *)(v9 + 36) )
        {
          v10 = 0;
        }
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        tlgWriteTransfer_EventWriteTransfer(v6, byte_18001616B, v9 + 8, v10, 4, v15);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          v5);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *((_QWORD *)v11 + 2) = *Local;
        *Local = v11;
        *((_DWORD *)v11 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000f814  push    rbp
0x18000f816  push    rbx
0x18000f817  push    rdi
0x18000f818  push    r14
0x18000f81a  lea     rbp, [rsp-3Fh]
0x18000f81f  sub     rsp, 98h
0x18000f826  mov     rax, cs:__security_cookie
0x18000f82d  xor     rax, rsp
0x18000f830  mov     [rbp+57h+var_30], rax
0x18000f834  mov     rbx, rcx
0x18000f837  lea     rdx, [rbp+57h+SRWLock]
0x18000f83b  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f840  mov     rdi, [rbx+110h]
0x18000f847  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000f84c  mov     edx, [rax]
0x18000f84e  mov     r14, 400000000000h
0x18000f858  cmp     edx, 5
0x18000f85b  jbe     short loc_18000F886
0x18000f85d  mov     rcx, [rax+18h]
0x18000f861  mov     rax, [rax+10h]
0x18000f865  test    r14, rax
0x18000f868  jz      short loc_18000F886
0x18000f86a  mov     rax, rcx
0x18000f86d  and     rax, r14
0x18000f870  cmp     rax, rcx
0x18000f873  jnz     short loc_18000F886
0x18000f875  lea     rdx, [rdi+8]; ActivityId
0x18000f879  mov     ecx, 3; ControlCode
0x18000f87e  call    cs:__imp_EventActivityIdControl
0x18000f884  jmp     short loc_18000F88D
0x18000f886  xorps   xmm0, xmm0
0x18000f889  movups  xmmword ptr [rdi+8], xmm0
0x18000f88d  mov     dword ptr [rdi], 1
0x18000f893  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000f897  test    rcx, rcx
0x18000f89a  jz      short loc_18000F8A2
0x18000f89c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f8a2  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000f8a7  mov     rdi, rax
0x18000f8aa  mov     ecx, [rax]
0x18000f8ac  cmp     ecx, 5
0x18000f8af  jbe     loc_18000F957
0x18000f8b5  mov     rax, [rax+18h]
0x18000f8b9  mov     rcx, [rdi+10h]
0x18000f8bd  test    r14, rcx
0x18000f8c0  jz      loc_18000F957
0x18000f8c6  mov     rcx, rax
0x18000f8c9  and     rcx, r14
0x18000f8cc  cmp     rcx, rax
0x18000f8cf  jnz     loc_18000F957
0x18000f8d5  call    cs:__imp_GetCurrentThreadId
0x18000f8db  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000f8de  mov     [rbp+57h+var_78], 0
0x18000f8e6  mov     r8, [rbx+110h]
0x18000f8ed  cmp     byte ptr [r8+4], 0
0x18000f8f2  jz      short loc_18000F913
0x18000f8f4  lea     r9, [r8+18h]
0x18000f8f8  cmp     dword ptr [r9], 0
0x18000f8fc  jnz     short loc_18000F916
0x18000f8fe  cmp     dword ptr [r9+4], 0
0x18000f903  jnz     short loc_18000F916
0x18000f905  cmp     dword ptr [r9+8], 0
0x18000f90a  jnz     short loc_18000F916
0x18000f90c  cmp     dword ptr [r9+0Ch], 0
0x18000f911  jnz     short loc_18000F916
0x18000f913  xor     r9d, r9d
0x18000f916  lea     rax, [rbp+57h+SRWLock]
0x18000f91a  mov     [rbp+57h+var_40], rax
0x18000f91e  mov     ecx, 4
0x18000f923  mov     [rbp+57h+var_38], rcx
0x18000f927  lea     rax, [rbp+57h+var_78]
0x18000f92b  mov     [rbp+57h+var_50], rax
0x18000f92f  mov     [rbp+57h+var_48], 8
0x18000f937  add     r8, 8
0x18000f93b  lea     rax, [rbp+57h+var_70]
0x18000f93f  mov     [rsp+0B0h+var_88], rax
0x18000f944  mov     [rsp+0B0h+var_90], ecx
0x18000f948  lea     rdx, byte_18001616B
0x18000f94f  mov     rcx, rdi
0x18000f952  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f957  cmp     dword ptr [rbx+138h], 0
0x18000f95e  jnz     short loc_18000F99C
0x18000f960  add     rbx, 120h
0x18000f967  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f96f  jz      short loc_18000F995
0x18000f971  mov     dl, 1
0x18000f973  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000f978  mov     [rbx], rax
0x18000f97b  test    rax, rax
0x18000f97e  jz      short loc_18000F99C
0x18000f980  mov     rcx, [rax]
0x18000f983  mov     [rbx+10h], rcx
0x18000f987  mov     [rax], rbx
0x18000f98a  call    cs:__imp_GetCurrentThreadId
0x18000f990  mov     [rbx+18h], eax
0x18000f993  jmp     short loc_18000F99C
0x18000f995  mov     qword ptr [rbx], 0
0x18000f99c  mov     rcx, [rbp+57h+var_30]
0x18000f9a0  xor     rcx, rsp; StackCookie
0x18000f9a3  call    __security_check_cookie
0x18000f9a8  add     rsp, 98h
0x18000f9af  pop     r14
0x18000f9b1  pop     rdi
0x18000f9b2  pop     rbx
0x18000f9b3  pop     rbp
0x18000f9b4  retn
```
