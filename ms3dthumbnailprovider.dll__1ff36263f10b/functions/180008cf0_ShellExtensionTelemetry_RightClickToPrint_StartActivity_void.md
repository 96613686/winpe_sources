# ShellExtensionTelemetry::RightClickToPrint::StartActivity(void)

- ea: `0x180008cf0`
- end: `0x180008e91`
- name: `?StartActivity@RightClickToPrint@ShellExtensionTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(ShellExtensionTelemetry::RightClickToPrint *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800079a0`

## callees

- `0x1800018dc`
- `0x180001ef0`
- `0x180006970`
- `0x18000705c`
- `0x180007c04`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008db1`
- `KERNEL32!GetCurrentThreadId` at `0x180008e66`
- `KERNEL32!GetCurrentThreadId` at `0x180008db1`
- `KERNEL32!GetCurrentThreadId` at `0x180008e66`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008d78`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008d78`
- `ADVAPI32!EventActivityIdControl` at `0x180008d5a`
- `ADVAPI32!EventActivityIdControl` at `0x180008d5a`

## pseudocode

```c
void __fastcall ShellExtensionTelemetry::RightClickToPrint::StartActivity(
        ShellExtensionTelemetry::RightClickToPrint *this)
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

  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = MS3DPrintShellExtension::Provider();
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
  v4 = MS3DPrintShellExtension::Provider();
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
        tlgWriteTransfer_EventWriteTransfer(v6, word_18000DE92, v9 + 8, v10, 4, v15);
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
0x180008cf0  push    rbp
0x180008cf2  push    rbx
0x180008cf3  push    rdi
0x180008cf4  push    r14
0x180008cf6  lea     rbp, [rsp-3Fh]
0x180008cfb  sub     rsp, 98h
0x180008d02  mov     rax, cs:__security_cookie
0x180008d09  xor     rax, rsp
0x180008d0c  mov     [rbp+57h+var_30], rax
0x180008d10  mov     rbx, rcx
0x180008d13  lea     rdx, [rbp+57h+SRWLock]
0x180008d17  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008d1c  mov     rdi, [rbx+110h]
0x180008d23  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x180008d28  mov     edx, [rax]
0x180008d2a  mov     r14, 400000000000h
0x180008d34  cmp     edx, 5
0x180008d37  jbe     short loc_180008D62
0x180008d39  mov     rcx, [rax+18h]
0x180008d3d  mov     rax, [rax+10h]
0x180008d41  test    r14, rax
0x180008d44  jz      short loc_180008D62
0x180008d46  mov     rax, rcx
0x180008d49  and     rax, r14
0x180008d4c  cmp     rax, rcx
0x180008d4f  jnz     short loc_180008D62
0x180008d51  lea     rdx, [rdi+8]; ActivityId
0x180008d55  mov     ecx, 3; ControlCode
0x180008d5a  call    cs:__imp_EventActivityIdControl
0x180008d60  jmp     short loc_180008D69
0x180008d62  xorps   xmm0, xmm0
0x180008d65  movups  xmmword ptr [rdi+8], xmm0
0x180008d69  mov     dword ptr [rdi], 1
0x180008d6f  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180008d73  test    rcx, rcx
0x180008d76  jz      short loc_180008D7E
0x180008d78  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d7e  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x180008d83  mov     rdi, rax
0x180008d86  mov     ecx, [rax]
0x180008d88  cmp     ecx, 5
0x180008d8b  jbe     loc_180008E33
0x180008d91  mov     rax, [rax+18h]
0x180008d95  mov     rcx, [rdi+10h]
0x180008d99  test    r14, rcx
0x180008d9c  jz      loc_180008E33
0x180008da2  mov     rcx, rax
0x180008da5  and     rcx, r14
0x180008da8  cmp     rcx, rax
0x180008dab  jnz     loc_180008E33
0x180008db1  call    cs:__imp_GetCurrentThreadId
0x180008db7  mov     dword ptr [rbp+57h+SRWLock], eax
0x180008dba  mov     [rbp+57h+var_78], 0
0x180008dc2  mov     r8, [rbx+110h]
0x180008dc9  cmp     byte ptr [r8+4], 0
0x180008dce  jz      short loc_180008DEF
0x180008dd0  lea     r9, [r8+18h]
0x180008dd4  cmp     dword ptr [r9], 0
0x180008dd8  jnz     short loc_180008DF2
0x180008dda  cmp     dword ptr [r9+4], 0
0x180008ddf  jnz     short loc_180008DF2
0x180008de1  cmp     dword ptr [r9+8], 0
0x180008de6  jnz     short loc_180008DF2
0x180008de8  cmp     dword ptr [r9+0Ch], 0
0x180008ded  jnz     short loc_180008DF2
0x180008def  xor     r9d, r9d
0x180008df2  lea     rax, [rbp+57h+SRWLock]
0x180008df6  mov     [rbp+57h+var_40], rax
0x180008dfa  mov     ecx, 4
0x180008dff  mov     [rbp+57h+var_38], rcx
0x180008e03  lea     rax, [rbp+57h+var_78]
0x180008e07  mov     [rbp+57h+var_50], rax
0x180008e0b  mov     [rbp+57h+var_48], 8
0x180008e13  add     r8, 8
0x180008e17  lea     rax, [rbp+57h+var_70]
0x180008e1b  mov     [rsp+0B0h+var_88], rax
0x180008e20  mov     [rsp+0B0h+var_90], ecx
0x180008e24  lea     rdx, word_18000DE92
0x180008e2b  mov     rcx, rdi
0x180008e2e  call    _tlgWriteTransfer_EventWriteTransfer
0x180008e33  cmp     dword ptr [rbx+138h], 0
0x180008e3a  jnz     short loc_180008E78
0x180008e3c  add     rbx, 120h
0x180008e43  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008e4b  jz      short loc_180008E71
0x180008e4d  mov     dl, 1
0x180008e4f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008e54  mov     [rbx], rax
0x180008e57  test    rax, rax
0x180008e5a  jz      short loc_180008E78
0x180008e5c  mov     rcx, [rax]
0x180008e5f  mov     [rbx+10h], rcx
0x180008e63  mov     [rax], rbx
0x180008e66  call    cs:__imp_GetCurrentThreadId
0x180008e6c  mov     [rbx+18h], eax
0x180008e6f  jmp     short loc_180008E78
0x180008e71  mov     qword ptr [rbx], 0
0x180008e78  mov     rcx, [rbp+57h+var_30]
0x180008e7c  xor     rcx, rsp; StackCookie
0x180008e7f  call    __security_check_cookie
0x180008e84  add     rsp, 98h
0x180008e8b  pop     r14
0x180008e8d  pop     rdi
0x180008e8e  pop     rbx
0x180008e8f  pop     rbp
0x180008e90  retn
```
