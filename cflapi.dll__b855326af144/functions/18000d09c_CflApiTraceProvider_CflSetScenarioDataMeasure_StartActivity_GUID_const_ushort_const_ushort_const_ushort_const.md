# CflApiTraceProvider::CflSetScenarioDataMeasure::StartActivity(_GUID const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000d09c`
- end: `0x18000d315`
- name: `?StartActivity@CflSetScenarioDataMeasure@CflApiTraceProvider@@QEAAXPEBU_GUID@@PEBG11@Z`
- size: `633`
- prototype: `void __fastcall(CflApiTraceProvider::CflSetScenarioDataMeasure *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800081e8`

## callees

- `0x180001d7c`
- `0x180002490`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000d09c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d153`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d18d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d18d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2df`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d134`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d134`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflSetScenarioDataMeasure::StartActivity(
        CflApiTraceProvider::CflSetScenarioDataMeasure *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  __int64 v8; // rbx
  __int64 v9; // rcx
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r10
  int *v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  __int64 v19; // rdx
  int v20; // edx
  __int64 v21; // rcx
  int v22; // ecx
  _QWORD *v23; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-81h] BYREF
  __int64 v26; // [rsp+38h] [rbp-79h] BYREF
  __int128 v27; // [rsp+40h] [rbp-71h] BYREF
  __int64 *v28; // [rsp+70h] [rbp-41h]
  __int64 v29; // [rsp+78h] [rbp-39h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-31h]
  __int64 v31; // [rsp+88h] [rbp-29h]
  __int128 *v32; // [rsp+90h] [rbp-21h]
  __int64 v33; // [rsp+98h] [rbp-19h]
  const unsigned __int16 *v34; // [rsp+A0h] [rbp-11h]
  int v35; // [rsp+A8h] [rbp-9h]
  int v36; // [rsp+ACh] [rbp-5h]
  const unsigned __int16 *v37; // [rsp+B0h] [rbp-1h]
  int v38; // [rsp+B8h] [rbp+7h]
  int v39; // [rsp+BCh] [rbp+Bh]
  int *v40; // [rsp+C0h] [rbp+Fh]
  int v41; // [rsp+C8h] [rbp+17h]
  int v42; // [rsp+CCh] [rbp+1Bh]

  v27 = 0;
  if ( a2 )
    v27 = (__int128)*a2;
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v8 = *((_QWORD *)this + 34);
  v9 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v9 > 5u
    && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  }
  else
  {
    *(_OWORD *)(v8 + 8) = 0;
  }
  v10 = SRWLock;
  *(_DWORD *)v8 = 1;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v13 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v13 > 5u )
  {
    v12 = *(_QWORD *)(v13 + 24);
    if ( (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = 0;
      v16 = (int *)a5;
      v17 = -1;
      v18 = 2;
      if ( a5 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a5[v19] );
        v20 = 2 * v19 + 2;
      }
      else
      {
        v16 = &dword_1800328FC;
        v20 = 2;
      }
      v40 = v16;
      v41 = v20;
      v42 = 0;
      if ( a4 )
      {
        v21 = -1;
        do
          ++v21;
        while ( a4[v21] );
        v22 = 2 * v21 + 2;
      }
      else
      {
        a4 = (const unsigned __int16 *)&dword_1800328FC;
        v22 = 2;
      }
      v37 = a4;
      v38 = v22;
      v39 = 0;
      if ( a3 )
      {
        do
          ++v17;
        while ( a3[v17] );
        v18 = 2 * v17 + 2;
      }
      else
      {
        a3 = (const unsigned __int16 *)&dword_1800328FC;
      }
      v35 = v18;
      v29 = 8;
      v32 = &v27;
      v34 = a3;
      p_SRWLock = &SRWLock;
      v36 = 0;
      v28 = &v26;
      v33 = 16;
      v31 = 4;
      tlgWriteTransfer_EventWriteTransfer(v13, &dword_180036E54, v15 + 8);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v23 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v11) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v12,
                          v11);
      *v23 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v23;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v23 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000d09c  mov     [rsp-8+arg_8], rbx
0x18000d0a1  mov     [rsp-8+arg_10], rsi
0x18000d0a6  push    rbp
0x18000d0a7  push    rdi
0x18000d0a8  push    r12
0x18000d0aa  push    r14
0x18000d0ac  push    r15
0x18000d0ae  lea     rbp, [rsp-2Fh]
0x18000d0b3  sub     rsp, 0E0h
0x18000d0ba  mov     rax, cs:__security_cookie
0x18000d0c1  xor     rax, rsp
0x18000d0c4  mov     [rbp+4Fh+var_30], rax
0x18000d0c8  xor     r15d, r15d
0x18000d0cb  xorps   xmm0, xmm0
0x18000d0ce  mov     rsi, r9
0x18000d0d1  mov     r14, r8
0x18000d0d4  mov     rdi, rcx
0x18000d0d7  movups  [rbp+4Fh+var_C0], xmm0
0x18000d0db  test    rdx, rdx
0x18000d0de  jz      short loc_18000D0E8
0x18000d0e0  movups  xmm0, xmmword ptr [rdx]
0x18000d0e3  movdqu  [rbp+4Fh+var_C0], xmm0
0x18000d0e8  lea     rdx, [rsp+100h+SRWLock]
0x18000d0ed  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d0f2  mov     rbx, [rdi+110h]
0x18000d0f9  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d0fe  mov     r12, 400000000000h
0x18000d108  mov     rcx, [rax+8]
0x18000d10c  mov     eax, [rcx]
0x18000d10e  cmp     eax, 5
0x18000d111  jbe     short loc_18000D13C
0x18000d113  mov     rdx, [rcx+18h]
0x18000d117  mov     rax, [rcx+10h]
0x18000d11b  test    r12, rax
0x18000d11e  jz      short loc_18000D13C
0x18000d120  mov     rax, rdx
0x18000d123  and     rax, r12
0x18000d126  cmp     rax, rdx
0x18000d129  jnz     short loc_18000D13C
0x18000d12b  lea     rdx, [rbx+8]; ActivityId
0x18000d12f  mov     ecx, 3; ControlCode
0x18000d134  call    cs:__imp_EventActivityIdControl
0x18000d13a  jmp     short loc_18000D143
0x18000d13c  xorps   xmm0, xmm0
0x18000d13f  movups  xmmword ptr [rbx+8], xmm0
0x18000d143  mov     rcx, [rsp+100h+SRWLock]; SRWLock
0x18000d148  mov     dword ptr [rbx], 1
0x18000d14e  test    rcx, rcx
0x18000d151  jz      short loc_18000D159
0x18000d153  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d159  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d15e  mov     rbx, [rax+8]
0x18000d162  mov     eax, [rbx]
0x18000d164  cmp     eax, 5
0x18000d167  jbe     loc_18000D2AD
0x18000d16d  mov     rcx, [rbx+18h]
0x18000d171  mov     rax, [rbx+10h]
0x18000d175  test    r12, rax
0x18000d178  jz      loc_18000D2AD
0x18000d17e  mov     rax, rcx
0x18000d181  and     rax, r12
0x18000d184  cmp     rax, rcx
0x18000d187  jnz     loc_18000D2AD
0x18000d18d  call    cs:__imp_GetCurrentThreadId
0x18000d193  mov     r10, [rdi+110h]
0x18000d19a  mov     dword ptr [rsp+100h+SRWLock], eax
0x18000d19e  mov     [rbp+4Fh+var_C8], r15
0x18000d1a2  cmp     [r10+4], r15b
0x18000d1a6  jz      short loc_18000D1C3
0x18000d1a8  lea     r9, [r10+18h]
0x18000d1ac  cmp     [r9], r15d
0x18000d1af  jnz     short loc_18000D1C6
0x18000d1b1  cmp     [r9+4], r15d
0x18000d1b5  jnz     short loc_18000D1C6
0x18000d1b7  cmp     [r9+8], r15d
0x18000d1bb  jnz     short loc_18000D1C6
0x18000d1bd  cmp     [r9+0Ch], r15d
0x18000d1c1  jnz     short loc_18000D1C6
0x18000d1c3  mov     r9, r15
0x18000d1c6  mov     rcx, [rbp+4Fh+arg_20]
0x18000d1ca  lea     r11, dword_1800328FC
0x18000d1d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d1d5  mov     r8d, 2
0x18000d1db  test    rcx, rcx
0x18000d1de  jz      short loc_18000D1F6
0x18000d1e0  mov     rdx, rax
0x18000d1e3  inc     rdx
0x18000d1e6  cmp     [rcx+rdx*2], r15w
0x18000d1eb  jnz     short loc_18000D1E3
0x18000d1ed  lea     edx, ds:2[rdx*2]
0x18000d1f4  jmp     short loc_18000D1FC
0x18000d1f6  mov     rcx, r11
0x18000d1f9  mov     edx, r8d
0x18000d1fc  mov     [rbp+4Fh+var_40], rcx
0x18000d200  mov     [rbp+4Fh+var_38], edx
0x18000d203  mov     [rbp+4Fh+var_34], r15d
0x18000d207  test    rsi, rsi
0x18000d20a  jz      short loc_18000D222
0x18000d20c  mov     rcx, rax
0x18000d20f  inc     rcx
0x18000d212  cmp     [rsi+rcx*2], r15w
0x18000d217  jnz     short loc_18000D20F
0x18000d219  lea     ecx, ds:2[rcx*2]
0x18000d220  jmp     short loc_18000D228
0x18000d222  mov     rsi, r11
0x18000d225  mov     ecx, r8d
0x18000d228  mov     [rbp+4Fh+var_50], rsi
0x18000d22c  mov     [rbp+4Fh+var_48], ecx
0x18000d22f  mov     [rbp+4Fh+var_44], r15d
0x18000d233  test    r14, r14
0x18000d236  jz      short loc_18000D24C
0x18000d238  inc     rax
0x18000d23b  cmp     [r14+rax*2], r15w
0x18000d240  jnz     short loc_18000D238
0x18000d242  lea     r8d, ds:2[rax*2]
0x18000d24a  jmp     short loc_18000D24F
0x18000d24c  mov     r14, r11
0x18000d24f  mov     ecx, 8
0x18000d254  mov     [rbp+4Fh+var_58], r8d
0x18000d258  lea     rax, [rbp+4Fh+var_C0]
0x18000d25c  mov     [rbp+4Fh+var_88], rcx
0x18000d260  mov     [rbp+4Fh+var_70], rax
0x18000d264  lea     r8, [r10+8]
0x18000d268  lea     rax, [rsp+100h+SRWLock]
0x18000d26d  mov     [rbp+4Fh+var_60], r14
0x18000d271  mov     [rbp+4Fh+var_80], rax
0x18000d275  lea     rdx, dword_180036E54
0x18000d27c  lea     rax, [rbp+4Fh+var_C8]
0x18000d280  mov     [rbp+4Fh+var_54], r15d
0x18000d284  mov     [rbp+4Fh+var_90], rax
0x18000d288  lea     rax, [rbp+4Fh+var_B0]
0x18000d28c  mov     [rsp+100h+var_D8], rax
0x18000d291  mov     [rsp+100h+var_E0], ecx
0x18000d295  mov     rcx, rbx
0x18000d298  mov     [rbp+4Fh+var_68], 10h
0x18000d2a0  mov     [rbp+4Fh+var_78], 4
0x18000d2a8  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d2ad  cmp     [rdi+138h], r15d
0x18000d2b4  jnz     short loc_18000D2ED
0x18000d2b6  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d2bd  lea     rbx, [rdi+120h]
0x18000d2c4  jz      short loc_18000D2EA
0x18000d2c6  mov     dl, 1
0x18000d2c8  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d2cd  mov     [rbx], rax
0x18000d2d0  test    rax, rax
0x18000d2d3  jz      short loc_18000D2ED
0x18000d2d5  mov     rcx, [rax]
0x18000d2d8  mov     [rbx+10h], rcx
0x18000d2dc  mov     [rax], rbx
0x18000d2df  call    cs:__imp_GetCurrentThreadId
0x18000d2e5  mov     [rbx+18h], eax
0x18000d2e8  jmp     short loc_18000D2ED
0x18000d2ea  mov     [rbx], r15
0x18000d2ed  mov     rcx, [rbp+4Fh+var_30]
0x18000d2f1  xor     rcx, rsp; StackCookie
0x18000d2f4  call    __security_check_cookie
0x18000d2f9  lea     r11, [rsp+100h+var_20]
0x18000d301  mov     rbx, [r11+38h]
0x18000d305  mov     rsi, [r11+40h]
0x18000d309  mov     rsp, r11
0x18000d30c  pop     r15
0x18000d30e  pop     r14
0x18000d310  pop     r12
0x18000d312  pop     rdi
0x18000d313  pop     rbp
0x18000d314  retn
```
