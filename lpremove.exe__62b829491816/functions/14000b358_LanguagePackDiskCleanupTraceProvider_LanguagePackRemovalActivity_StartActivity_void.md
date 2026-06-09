# LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::StartActivity(void)

- ea: `0x14000b358`
- end: `0x14000b4fe`
- name: `?StartActivity@LanguagePackRemovalActivity@LanguagePackDiskCleanupTraceProvider@@QEAAXXZ`
- size: `422`
- prototype: `void __fastcall(LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000d8b8`

## callees

- `0x140001b9c`
- `0x140002190`
- `0x140007760`
- `0x140007eac`
- `0x1400084b8`
- `0x14000b358`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14000b3c6`
- `ADVAPI32!EventActivityIdControl` at `0x14000b3c6`
- `KERNEL32!GetCurrentThreadId` at `0x14000b41e`
- `KERNEL32!GetCurrentThreadId` at `0x14000b4d3`
- `KERNEL32!GetCurrentThreadId` at `0x14000b41e`
- `KERNEL32!GetCurrentThreadId` at `0x14000b4d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b3e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b3e4`

## pseudocode

```c
void __fastcall LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::StartActivity(
        LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v3 > 5u
    && (*(_QWORD *)(v3 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v3 + 24) & 0x200000000000LL) == *(_QWORD *)(v3 + 24) )
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
  v5 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u )
  {
    v4 = *(_QWORD *)(v5 + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0 && (v4 & 0x200000000000LL) == v4 )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v11 = 0;
      v6 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v6 + 4)
        || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
        && !*(_DWORD *)(v6 + 28)
        && !*(_DWORD *)(v6 + 32)
        && !*(_DWORD *)(v6 + 36) )
      {
        v7 = 0;
      }
      p_SRWLock = &SRWLock;
      v16 = 4;
      v13 = &v11;
      v14 = 8;
      tlgWriteTransfer_EventWriteTransfer(v5, &word_140014576, v6 + 8, v7, 4, v12);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x14000b358  push    rbp
0x14000b35a  push    rbx
0x14000b35b  push    rdi
0x14000b35c  push    r14
0x14000b35e  lea     rbp, [rsp-3Fh]
0x14000b363  sub     rsp, 98h
0x14000b36a  mov     rax, cs:__security_cookie
0x14000b371  xor     rax, rsp
0x14000b374  mov     [rbp+57h+var_30], rax
0x14000b378  mov     rbx, rcx
0x14000b37b  lea     rdx, [rbp+57h+SRWLock]
0x14000b37f  call    ?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b384  mov     rdi, [rbx+110h]
0x14000b38b  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000b390  mov     rdx, [rax+8]
0x14000b394  mov     eax, [rdx]
0x14000b396  mov     r14, 200000000000h
0x14000b3a0  cmp     eax, 5
0x14000b3a3  jbe     short loc_14000B3CE
0x14000b3a5  mov     rcx, [rdx+18h]
0x14000b3a9  mov     rax, [rdx+10h]
0x14000b3ad  test    r14, rax
0x14000b3b0  jz      short loc_14000B3CE
0x14000b3b2  mov     rax, rcx
0x14000b3b5  and     rax, r14
0x14000b3b8  cmp     rax, rcx
0x14000b3bb  jnz     short loc_14000B3CE
0x14000b3bd  lea     rdx, [rdi+8]; ActivityId
0x14000b3c1  mov     ecx, 3; ControlCode
0x14000b3c6  call    cs:__imp_EventActivityIdControl
0x14000b3cc  jmp     short loc_14000B3D5
0x14000b3ce  xorps   xmm0, xmm0
0x14000b3d1  movups  xmmword ptr [rdi+8], xmm0
0x14000b3d5  mov     dword ptr [rdi], 1
0x14000b3db  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000b3df  test    rcx, rcx
0x14000b3e2  jz      short loc_14000B3EA
0x14000b3e4  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b3ea  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000b3ef  mov     rdi, [rax+8]
0x14000b3f3  mov     eax, [rdi]
0x14000b3f5  cmp     eax, 5
0x14000b3f8  jbe     loc_14000B4A0
0x14000b3fe  mov     rcx, [rdi+18h]
0x14000b402  mov     rax, [rdi+10h]
0x14000b406  test    r14, rax
0x14000b409  jz      loc_14000B4A0
0x14000b40f  mov     rax, rcx
0x14000b412  and     rax, r14
0x14000b415  cmp     rax, rcx
0x14000b418  jnz     loc_14000B4A0
0x14000b41e  call    cs:__imp_GetCurrentThreadId
0x14000b424  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000b427  mov     [rbp+57h+var_78], 0
0x14000b42f  mov     r8, [rbx+110h]
0x14000b436  cmp     byte ptr [r8+4], 0
0x14000b43b  jz      short loc_14000B45C
0x14000b43d  lea     r9, [r8+18h]
0x14000b441  cmp     dword ptr [r9], 0
0x14000b445  jnz     short loc_14000B45F
0x14000b447  cmp     dword ptr [r9+4], 0
0x14000b44c  jnz     short loc_14000B45F
0x14000b44e  cmp     dword ptr [r9+8], 0
0x14000b453  jnz     short loc_14000B45F
0x14000b455  cmp     dword ptr [r9+0Ch], 0
0x14000b45a  jnz     short loc_14000B45F
0x14000b45c  xor     r9d, r9d
0x14000b45f  lea     rax, [rbp+57h+SRWLock]
0x14000b463  mov     [rbp+57h+var_40], rax
0x14000b467  mov     ecx, 4
0x14000b46c  mov     [rbp+57h+var_38], rcx
0x14000b470  lea     rax, [rbp+57h+var_78]
0x14000b474  mov     [rbp+57h+var_50], rax
0x14000b478  mov     [rbp+57h+var_48], 8
0x14000b480  add     r8, 8
0x14000b484  lea     rax, [rbp+57h+var_70]
0x14000b488  mov     [rsp+0B0h+var_88], rax
0x14000b48d  mov     [rsp+0B0h+var_90], ecx
0x14000b491  lea     rdx, word_140014576
0x14000b498  mov     rcx, rdi
0x14000b49b  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b4a0  cmp     dword ptr [rbx+138h], 0
0x14000b4a7  jnz     short loc_14000B4E5
0x14000b4a9  add     rbx, 120h
0x14000b4b0  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000b4b8  jz      short loc_14000B4DE
0x14000b4ba  mov     dl, 1
0x14000b4bc  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000b4c1  mov     [rbx], rax
0x14000b4c4  test    rax, rax
0x14000b4c7  jz      short loc_14000B4E5
0x14000b4c9  mov     rcx, [rax]
0x14000b4cc  mov     [rbx+10h], rcx
0x14000b4d0  mov     [rax], rbx
0x14000b4d3  call    cs:__imp_GetCurrentThreadId
0x14000b4d9  mov     [rbx+18h], eax
0x14000b4dc  jmp     short loc_14000B4E5
0x14000b4de  mov     qword ptr [rbx], 0
0x14000b4e5  mov     rcx, [rbp+57h+var_30]
0x14000b4e9  xor     rcx, rsp; StackCookie
0x14000b4ec  call    __security_check_cookie
0x14000b4f1  add     rsp, 98h
0x14000b4f8  pop     r14
0x14000b4fa  pop     rdi
0x14000b4fb  pop     rbx
0x14000b4fc  pop     rbp
0x14000b4fd  retn
```
