# DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StartActivity(void)

- ea: `0x14000d358`
- end: `0x14000d4f9`
- name: `?StartActivity@DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000e174`

## callees

- `0x140001bac`
- `0x1400022a0`
- `0x1400096cc`
- `0x140009e44`
- `0x14000a9b4`
- `0x14000d358`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d3c2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d3c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d3e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d3e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d4ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d4ce`

## pseudocode

```c
void __fastcall DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StartActivity(
        DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+7h]
  __int64 v16; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v18; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = DXGIAdapterCacheLogging::Provider();
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
  v4 = DXGIAdapterCacheLogging::Provider();
  v5 = v4;
  v6 = *(unsigned int *)v4;
  if ( (unsigned int)v6 > 5 )
  {
    v7 = *((_QWORD *)v4 + 3);
    v6 = *((_QWORD *)v5 + 2);
    if ( (v6 & 0x400000000000LL) != 0 )
    {
      v6 = v7 & 0x400000000000LL;
      if ( (v7 & 0x400000000000LL) == v7 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v13 = 0x1000000;
        v8 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v8 + 4)
          || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
          && !*(_DWORD *)(v8 + 28)
          && !*(_DWORD *)(v8 + 32)
          && !*(_DWORD *)(v8 + 36) )
        {
          v9 = 0;
        }
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v5, byte_1400156DD, v8 + 8, v9, 4, v14);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          1);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *((_QWORD *)v10 + 2) = *Local;
        *Local = v10;
        *((_DWORD *)v10 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
}

```

## disassembly

```asm
0x14000d358  push    rbp
0x14000d35a  push    rbx
0x14000d35b  push    rdi
0x14000d35c  push    r14
0x14000d35e  lea     rbp, [rsp-3Fh]
0x14000d363  sub     rsp, 98h
0x14000d36a  mov     rax, cs:__security_cookie
0x14000d371  xor     rax, rsp
0x14000d374  mov     [rbp+57h+var_30], rax
0x14000d378  mov     rbx, rcx
0x14000d37b  lea     rdx, [rbp+57h+SRWLock]
0x14000d37f  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000d384  mov     rdi, [rbx+110h]
0x14000d38b  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000d390  mov     edx, [rax]
0x14000d392  mov     r14, 400000000000h
0x14000d39c  cmp     edx, 5
0x14000d39f  jbe     short loc_14000D3CA
0x14000d3a1  mov     rcx, [rax+18h]
0x14000d3a5  mov     rax, [rax+10h]
0x14000d3a9  test    r14, rax
0x14000d3ac  jz      short loc_14000D3CA
0x14000d3ae  mov     rax, rcx
0x14000d3b1  and     rax, r14
0x14000d3b4  cmp     rax, rcx
0x14000d3b7  jnz     short loc_14000D3CA
0x14000d3b9  lea     rdx, [rdi+8]; ActivityId
0x14000d3bd  mov     ecx, 3; ControlCode
0x14000d3c2  call    cs:__imp_EventActivityIdControl
0x14000d3c8  jmp     short loc_14000D3D1
0x14000d3ca  xorps   xmm0, xmm0
0x14000d3cd  movups  xmmword ptr [rdi+8], xmm0
0x14000d3d1  mov     dword ptr [rdi], 1
0x14000d3d7  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000d3db  test    rcx, rcx
0x14000d3de  jz      short loc_14000D3E6
0x14000d3e0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d3e6  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000d3eb  mov     rdi, rax
0x14000d3ee  mov     ecx, [rax]
0x14000d3f0  cmp     ecx, 5
0x14000d3f3  jbe     loc_14000D49B
0x14000d3f9  mov     rax, [rax+18h]
0x14000d3fd  mov     rcx, [rdi+10h]
0x14000d401  test    r14, rcx
0x14000d404  jz      loc_14000D49B
0x14000d40a  mov     rcx, rax
0x14000d40d  and     rcx, r14
0x14000d410  cmp     rcx, rax
0x14000d413  jnz     loc_14000D49B
0x14000d419  call    cs:__imp_GetCurrentThreadId
0x14000d41f  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000d422  mov     [rbp+57h+var_78], 1000000h
0x14000d42a  mov     r8, [rbx+110h]
0x14000d431  cmp     byte ptr [r8+4], 0
0x14000d436  jz      short loc_14000D457
0x14000d438  lea     r9, [r8+18h]
0x14000d43c  cmp     dword ptr [r9], 0
0x14000d440  jnz     short loc_14000D45A
0x14000d442  cmp     dword ptr [r9+4], 0
0x14000d447  jnz     short loc_14000D45A
0x14000d449  cmp     dword ptr [r9+8], 0
0x14000d44e  jnz     short loc_14000D45A
0x14000d450  cmp     dword ptr [r9+0Ch], 0
0x14000d455  jnz     short loc_14000D45A
0x14000d457  xor     r9d, r9d
0x14000d45a  lea     rax, [rbp+57h+SRWLock]
0x14000d45e  mov     [rbp+57h+var_40], rax
0x14000d462  mov     ecx, 4
0x14000d467  mov     [rbp+57h+var_38], rcx
0x14000d46b  lea     rax, [rbp+57h+var_78]
0x14000d46f  mov     [rbp+57h+var_50], rax
0x14000d473  mov     [rbp+57h+var_48], 8
0x14000d47b  add     r8, 8
0x14000d47f  lea     rax, [rbp+57h+var_70]
0x14000d483  mov     [rsp+0B0h+var_88], rax
0x14000d488  mov     [rsp+0B0h+var_90], ecx
0x14000d48c  lea     rdx, byte_1400156DD
0x14000d493  mov     rcx, rdi
0x14000d496  call    _tlgWriteTransfer_EventWriteTransfer
0x14000d49b  cmp     dword ptr [rbx+138h], 0
0x14000d4a2  jnz     short loc_14000D4E0
0x14000d4a4  add     rbx, 120h
0x14000d4ab  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000d4b3  jz      short loc_14000D4D9
0x14000d4b5  mov     dl, 1
0x14000d4b7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000d4bc  mov     [rbx], rax
0x14000d4bf  test    rax, rax
0x14000d4c2  jz      short loc_14000D4E0
0x14000d4c4  mov     rcx, [rax]
0x14000d4c7  mov     [rbx+10h], rcx
0x14000d4cb  mov     [rax], rbx
0x14000d4ce  call    cs:__imp_GetCurrentThreadId
0x14000d4d4  mov     [rbx+18h], eax
0x14000d4d7  jmp     short loc_14000D4E0
0x14000d4d9  mov     qword ptr [rbx], 0
0x14000d4e0  mov     rcx, [rbp+57h+var_30]
0x14000d4e4  xor     rcx, rsp; StackCookie
0x14000d4e7  call    __security_check_cookie
0x14000d4ec  add     rsp, 98h
0x14000d4f3  pop     r14
0x14000d4f5  pop     rdi
0x14000d4f6  pop     rbx
0x14000d4f7  pop     rbp
0x14000d4f8  retn
```
