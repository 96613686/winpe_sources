# ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(char const *,void *)

- ea: `0x180014f14`
- end: `0x1800150d6`
- name: `?StartActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@QEAAXPEBDPEAX@Z`
- size: `450`
- prototype: `void __fastcall(ComputeCore::Diagnostics::TraceProvider::HcsClientApi *__hidden this, const char *, void *)`
- caller_count: `54`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015990`
- `0x180015af0`
- `0x180015fc0`
- `0x180016110`
- `0x1800161d0`
- `0x1800163a0`
- `0x180016460`
- `0x180016670`
- `0x180016770`
- `0x180016aa0`
- `0x180016c60`
- `0x180016e50`
- `0x180017180`
- `0x1800172c0`
- `0x180017410`
- `0x1800175c0`
- `0x180017780`
- `0x180017900`
- `0x180017a50`
- `0x18001a5e0`
- `0x18001a680`
- `0x18001a7b0`
- `0x18001ab70`
- `0x18001ac20`
- `0x18001ad60`
- `0x18001ae00`
- `0x18001af70`
- `0x18001b0a0`
- `0x18001b1d0`
- `0x18001b310`
- `0x18001b450`
- `0x18001b4f0`
- `0x18001b620`
- `0x18001b750`
- `0x18001b880`
- `0x18001b950`
- `0x18001ba80`
- `0x18001bbb0`
- `0x18001bce0`
- `0x18001be50`
- `0x18001bf80`
- `0x180028d50`
- `0x180028ea0`
- `0x1800290a0`
- `0x1800291f0`
- `0x180029380`
- `0x180029460`
- `0x1800295f0`
- `0x1800296d0`
- `0x180029810`

## callees

- `0x1800016ec`
- `0x1800067c0`
- `0x18000d0fc`
- `0x180014a2c`
- `0x180014f14`
- `0x1800150dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014fb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fef`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f92`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f92`

## pseudocode

```c
void __fastcall ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(
        ComputeCore::Diagnostics::TraceProvider::HcsClientApi *this,
        const char *a2,
        void *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rcx
  int v9; // edi
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-79h] BYREF
  void *v16; // [rsp+38h] [rbp-71h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v19; // [rsp+70h] [rbp-39h]
  __int64 v20; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v22; // [rsp+88h] [rbp-21h]
  const char *v23; // [rsp+90h] [rbp-19h]
  int v24; // [rsp+98h] [rbp-11h]
  int v25; // [rsp+9Ch] [rbp-Dh]
  void **v26; // [rsp+A0h] [rbp-9h]
  __int64 v27; // [rsp+A8h] [rbp-1h]

  SRWLock = 0;
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)ComputeCore::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 4u
    && (*(_QWORD *)(v7 + 16) & 0x20000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x20000LL) == *(_QWORD *)(v7 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  v9 = 1;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v10 = *((_QWORD *)ComputeCore::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v10 > 4u
    && (*(_QWORD *)(v10 + 16) & 0x20000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x20000LL) == *(_QWORD *)(v10 + 24) )
  {
    v16 = a3;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    v27 = 8;
    v26 = &v16;
    if ( a2 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      v9 = v14 + 1;
    }
    else
    {
      a2 = (const char *)&byte_1800AD7F5;
    }
    v23 = a2;
    p_SRWLock = &SRWLock;
    v24 = v9;
    v19 = &v17;
    v25 = 0;
    v22 = 4;
    v20 = 8;
    tlgWriteTransfer_EventWriteTransfer(v10, (int)&qword_1800C5E58, v12 + 8, v13, 6u, &v18);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)((char *)this + 288));
}

```

## disassembly

```asm
0x180014f14  push    rbp
0x180014f16  push    rbx
0x180014f17  push    rsi
0x180014f18  push    rdi
0x180014f19  push    r12
0x180014f1b  push    r13
0x180014f1d  push    r14
0x180014f1f  push    r15
0x180014f21  lea     rbp, [rsp-1Fh]
0x180014f26  sub     rsp, 0C8h
0x180014f2d  mov     rax, cs:__security_cookie
0x180014f34  xor     rax, rsp
0x180014f37  mov     [rbp+57h+var_50], rax
0x180014f3b  mov     rsi, rdx
0x180014f3e  xor     r12d, r12d
0x180014f41  lea     rdx, [rbp+57h+SRWLock]
0x180014f45  mov     [rbp+57h+SRWLock], r12
0x180014f49  mov     r15, r8
0x180014f4c  mov     r14, rcx
0x180014f4f  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014f54  mov     rbx, [r14+110h]
0x180014f5b  call    ?Instance@TraceProvider@Diagnostics@ComputeCore@@KAPEAV123@XZ; ComputeCore::Diagnostics::TraceProvider::Instance(void)
0x180014f60  mov     r13d, 20000h
0x180014f66  mov     rdx, [rax+8]
0x180014f6a  mov     eax, [rdx]
0x180014f6c  cmp     eax, 4
0x180014f6f  jbe     short loc_180014F9A
0x180014f71  mov     rcx, [rdx+18h]
0x180014f75  mov     rax, [rdx+10h]
0x180014f79  test    r13, rax
0x180014f7c  jz      short loc_180014F9A
0x180014f7e  mov     rax, rcx
0x180014f81  and     rax, r13
0x180014f84  cmp     rax, rcx
0x180014f87  jnz     short loc_180014F9A
0x180014f89  lea     rdx, [rbx+8]; ActivityId
0x180014f8d  lea     ecx, [r12+3]; ControlCode
0x180014f92  call    cs:__imp_EventActivityIdControl
0x180014f98  jmp     short loc_180014FA1
0x180014f9a  xorps   xmm0, xmm0
0x180014f9d  movups  xmmword ptr [rbx+8], xmm0
0x180014fa1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180014fa5  mov     edi, 1
0x180014faa  mov     [rbx], edi
0x180014fac  test    rcx, rcx
0x180014faf  jz      short loc_180014FB7
0x180014fb1  call    cs:__imp_ReleaseSRWLockExclusive
0x180014fb7  call    ?Instance@TraceProvider@Diagnostics@ComputeCore@@KAPEAV123@XZ; ComputeCore::Diagnostics::TraceProvider::Instance(void)
0x180014fbc  mov     rbx, [rax+8]
0x180014fc0  mov     eax, [rbx]
0x180014fc2  cmp     eax, 4
0x180014fc5  jbe     loc_1800150A4
0x180014fcb  mov     rcx, [rbx+18h]
0x180014fcf  mov     rax, [rbx+10h]
0x180014fd3  test    r13, rax
0x180014fd6  jz      loc_1800150A4
0x180014fdc  mov     rax, rcx
0x180014fdf  and     rax, r13
0x180014fe2  cmp     rax, rcx
0x180014fe5  jnz     loc_1800150A4
0x180014feb  mov     [rbp+57h+var_C8], r15
0x180014fef  call    cs:__imp_GetCurrentThreadId
0x180014ff5  mov     r8, [r14+110h]
0x180014ffc  mov     dword ptr [rbp+57h+SRWLock], eax
0x180014fff  mov     [rbp+57h+var_C0], r12
0x180015003  cmp     [r8+4], r12b
0x180015007  jz      short loc_180015024
0x180015009  lea     r9, [r8+18h]
0x18001500d  cmp     [r9], r12d
0x180015010  jnz     short loc_180015027
0x180015012  cmp     [r9+4], r12d
0x180015016  jnz     short loc_180015027
0x180015018  cmp     [r9+8], r12d
0x18001501c  jnz     short loc_180015027
0x18001501e  cmp     [r9+0Ch], r12d
0x180015022  jnz     short loc_180015027
0x180015024  mov     r9, r12; int
0x180015027  mov     [rbp+57h+var_58], 8
0x18001502f  lea     rax, [rbp+57h+var_C8]
0x180015033  mov     [rbp+57h+var_60], rax
0x180015037  test    rsi, rsi
0x18001503a  jz      short loc_18001504E
0x18001503c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015040  inc     rax
0x180015043  cmp     [rsi+rax], r12b
0x180015047  jnz     short loc_180015040
0x180015049  lea     edi, [rax+1]
0x18001504c  jmp     short loc_180015055
0x18001504e  lea     rsi, byte_1800AD7F5
0x180015055  lea     rax, [rbp+57h+SRWLock]
0x180015059  mov     [rbp+57h+var_70], rsi
0x18001505d  mov     [rbp+57h+var_80], rax
0x180015061  lea     rdx, qword_1800C5E58; int
0x180015068  lea     rax, [rbp+57h+var_C0]
0x18001506c  mov     [rbp+57h+var_68], edi
0x18001506f  mov     [rbp+57h+var_90], rax
0x180015073  add     r8, 8; int
0x180015077  lea     rax, [rbp+57h+var_B0]
0x18001507b  mov     [rbp+57h+var_64], r12d
0x18001507f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x180015084  mov     rcx, rbx; int
0x180015087  mov     [rsp+100h+var_E0], 6; ULONG
0x18001508f  mov     [rbp+57h+var_78], 4
0x180015097  mov     [rbp+57h+var_88], 8
0x18001509f  call    _tlgWriteTransfer_EventWriteTransfer
0x1800150a4  lea     rcx, [r14+120h]; this
0x1800150ab  cmp     [rcx+18h], r12d
0x1800150af  jnz     short loc_1800150B6
0x1800150b1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800150b6  mov     rcx, [rbp+57h+var_50]
0x1800150ba  xor     rcx, rsp; StackCookie
0x1800150bd  call    __security_check_cookie
0x1800150c2  add     rsp, 0C8h
0x1800150c9  pop     r15
0x1800150cb  pop     r14
0x1800150cd  pop     r13
0x1800150cf  pop     r12
0x1800150d1  pop     rdi
0x1800150d2  pop     rsi
0x1800150d3  pop     rbx
0x1800150d4  pop     rbp
0x1800150d5  retn
```
