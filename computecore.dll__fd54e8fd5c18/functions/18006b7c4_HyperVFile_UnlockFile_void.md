# HyperVFile::UnlockFile(void)

- ea: `0x18006b7c4`
- end: `0x18006ba53`
- name: `?UnlockFile@HyperVFile@@IEAAXXZ`
- size: `655`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `5`
- callee_count: `16`
- tags: ``

## callers

- `0x1800613bc`
- `0x18006743c`
- `0x180068020`
- `0x18006b2d0`
- `0x18006ba60`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180007dbc`
- `0x180007e24`
- `0x180060f70`
- `0x180061240`
- `0x180064e74`
- `0x180066284`
- `0x1800696b4`
- `0x1800697a8`
- `0x18006b7c4`
- `0x180081f2c`
- `0x180082140`
- `0x1800886d0`
- `0x1800890cc`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b9ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b9ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b803`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b809`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b809`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HyperVFile::UnlockFile(HyperVFile *this)
{
  char *v2; // rsi
  const unsigned __int16 *v3; // rbx
  int v4; // eax
  int v5; // eax
  char v6; // r14
  int IsDebugTraceEnabled; // ebx
  _DWORD *v8; // rcx
  __int64 v9; // rax
  _OWORD v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v11; // [rsp+50h] [rbp-B0h]
  struct _GUID v12; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v13; // [rsp+70h] [rbp-90h]
  _QWORD v14[42]; // [rsp+80h] [rbp-80h] BYREF

  v2 = (char *)this + 752;
  AcquireSRWLockExclusive((PSRWLOCK)this + 94);
  *((_DWORD *)v2 + 2) = GetCurrentThreadId();
  memset_0(v14, 0, sizeof(v14));
  v3 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "HyperVFile_Unlock");
  v14[0] = &HyperVStorageTrace::HyperVFile_Unlock::`vftable';
  v12 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::HyperVFile_Unlock::StartActivity((HyperVStorageTrace::HyperVFile_Unlock *)v14, &v12, v3);
  v4 = *((_DWORD *)this + 192);
  if ( v4 )
  {
    v5 = v4 - 1;
    *((_DWORD *)this + 192) = v5;
    if ( !v5
      && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 8LL))(*((_QWORD *)this + 75))
      && !*((_DWORD *)this + 101) )
    {
      HyperVStoragePerfTracker::StartOperation((char *)this + 432, &v12);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 96LL))(*((_QWORD *)this + 75));
      v10[0] = v12;
      v10[1] = v13;
      v6 = 1;
      v11 = 1;
      HyperVStoragePerfTracker::LogOperation((_DWORD)this + 432, (unsigned int)v10, 11, 0, 7);
      IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC020u);
      v8 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
      if ( !v8 || !*v8 )
        v6 = 0;
      if ( IsDebugTraceEnabled || v6 )
      {
        if ( dword_1800E46D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 16LL) )
        {
          Init_thread_header(&dword_1800E46D0);
          if ( dword_1800E46D0 == -1 )
          {
            byte_1800E1CF4 = IsDebugTraceEnabled != 0;
            byte_1800E1CF5 = v6;
            Init_thread_footer(&dword_1800E46D0);
          }
        }
        v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC020u, (const struct HvsDebugTraceParameters *)&off_1800E1CE0, v9);
      }
    }
  }
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14, 0);
  v14[0] = &HyperVStorageTrace::HyperVFile_Unlock::`vftable';
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(v14);
  if ( *((_DWORD *)v2 + 2) )
  {
    *((_DWORD *)v2 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v2);
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v2);
  }
}

```

## disassembly

```asm
0x18006b7c4  mov     [rsp-8+arg_8], rbx
0x18006b7c9  mov     [rsp-8+arg_10], rsi
0x18006b7ce  push    rbp
0x18006b7cf  push    rdi
0x18006b7d0  push    r13
0x18006b7d2  push    r14
0x18006b7d4  push    r15
0x18006b7d6  lea     rbp, [rsp-0E0h]
0x18006b7de  sub     rsp, 1E0h
0x18006b7e5  mov     rax, cs:__security_cookie
0x18006b7ec  xor     rax, rsp
0x18006b7ef  mov     [rbp+100h+var_30], rax
0x18006b7f6  mov     rdi, rcx
0x18006b7f9  lea     rsi, [rcx+2F0h]
0x18006b800  mov     rcx, rsi; SRWLock
0x18006b803  call    cs:__imp_AcquireSRWLockExclusive
0x18006b809  call    cs:__imp_GetCurrentThreadId
0x18006b80f  mov     [rsi+8], eax
0x18006b812  xor     edx, edx; Val
0x18006b814  mov     r8d, 150h; Size
0x18006b81a  lea     rcx, [rbp+100h+var_180]; void *
0x18006b81e  call    memset_0
0x18006b823  mov     rcx, [rdi+258h]
0x18006b82a  mov     rax, [rcx]
0x18006b82d  mov     rax, [rax+48h]
0x18006b831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b836  mov     rbx, rax
0x18006b839  lea     rdx, aHypervfileUnlo_0; "HyperVFile_Unlock"
0x18006b840  lea     rcx, [rbp+100h+var_180]
0x18006b844  call    ??0?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006b849  lea     r13, ??_7HyperVFile_Unlock@HyperVStorageTrace@@6B@; const HyperVStorageTrace::HyperVFile_Unlock::`vftable'
0x18006b850  mov     [rbp+100h+var_180], r13
0x18006b854  movups  xmm0, xmmword ptr [rdi+238h]
0x18006b85b  movdqu  xmmword ptr [rsp+200h+var_1A0.Data1], xmm0
0x18006b861  mov     r8, rbx; unsigned __int16 *
0x18006b864  lea     rdx, [rsp+200h+var_1A0]; struct _GUID
0x18006b869  lea     rcx, [rbp+100h+var_180]; this
0x18006b86d  call    ?StartActivity@HyperVFile_Unlock@HyperVStorageTrace@@QEAAXU_GUID@@PEBG@Z; HyperVStorageTrace::HyperVFile_Unlock::StartActivity(_GUID,ushort const *)
0x18006b872  nop
0x18006b873  mov     eax, [rdi+300h]
0x18006b879  test    eax, eax
0x18006b87b  jz      loc_18006B9B1
0x18006b881  sub     eax, 1
0x18006b884  mov     [rdi+300h], eax
0x18006b88a  jnz     loc_18006B9B1
0x18006b890  mov     rcx, [rdi+258h]
0x18006b897  mov     rax, [rcx]
0x18006b89a  mov     rax, [rax+8]
0x18006b89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8a3  test    eax, eax
0x18006b8a5  jz      loc_18006B9B1
0x18006b8ab  cmp     dword ptr [rdi+194h], 0
0x18006b8b2  jnz     loc_18006B9B1
0x18006b8b8  lea     rbx, [rdi+1B0h]
0x18006b8bf  lea     rdx, [rsp+200h+var_1A0]
0x18006b8c4  mov     rcx, rbx
0x18006b8c7  call    ?StartOperation@HyperVStoragePerfTracker@@QEAA?AUTimedOperation@1@XZ; HyperVStoragePerfTracker::StartOperation(void)
0x18006b8cc  mov     rcx, [rdi+258h]
0x18006b8d3  mov     rax, [rcx]
0x18006b8d6  mov     rax, [rax+60h]
0x18006b8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8df  movups  xmm0, xmmword ptr [rsp+200h+var_1A0.Data1]
0x18006b8e4  movaps  [rsp+200h+var_1D0], xmm0
0x18006b8e9  movups  xmm1, [rsp+200h+var_190]
0x18006b8ee  movaps  [rsp+200h+var_1C0], xmm1
0x18006b8f3  mov     r14b, 1
0x18006b8f6  mov     [rsp+200h+var_1B0], r14b
0x18006b8fb  mov     eax, [rsp+200h+var_1AF]
0x18006b8ff  mov     [rsp+200h+var_1AF], eax
0x18006b903  movzx   eax, [rsp+200h+var_1AB]
0x18006b908  mov     [rsp+200h+var_1AB], ax
0x18006b90d  mov     al, [rsp+200h+var_1A9]
0x18006b911  mov     [rsp+200h+var_1A9], al
0x18006b915  mov     [rsp+200h+var_1E0], 7
0x18006b91d  xor     r9d, r9d
0x18006b920  lea     r8d, [r9+0Bh]
0x18006b924  lea     rdx, [rsp+200h+var_1D0]
0x18006b929  mov     rcx, rbx
0x18006b92c  call    ?LogOperation@HyperVStoragePerfTracker@@QEAAXV?$optional@UTimedOperation@HyperVStoragePerfTracker@@@std@@W4HvsPerfOperationType@@_KW4HvsPerfRecordType@@@Z; HyperVStoragePerfTracker::LogOperation(std::optional<HyperVStoragePerfTracker::TimedOperation>,HvsPerfOperationType,unsigned __int64,HvsPerfRecordType)
0x18006b931  mov     ecx, 0C020h; unsigned __int16
0x18006b936  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x18006b93b  mov     ebx, eax
0x18006b93d  test    eax, eax
0x18006b93f  setnz   r15b
0x18006b943  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006b948  mov     rcx, [rax+8]
0x18006b94c  test    rcx, rcx
0x18006b94f  jz      short loc_18006B957
0x18006b951  mov     ecx, [rcx]
0x18006b953  test    ecx, ecx
0x18006b955  jnz     short loc_18006B95A
0x18006b957  xor     r14b, r14b
0x18006b95a  test    ebx, ebx
0x18006b95c  jnz     short loc_18006B963
0x18006b95e  test    r14b, r14b
0x18006b961  jz      short loc_18006B9B1
0x18006b963  mov     ecx, cs:_tls_index
0x18006b969  mov     rax, gs:58h
0x18006b972  mov     edx, 10h
0x18006b977  mov     rax, [rax+rcx*8]
0x18006b97b  mov     ecx, [rdx+rax]
0x18006b97e  cmp     cs:dword_1800E46D0, ecx
0x18006b984  jg      loc_18006BA1B
0x18006b98a  mov     rcx, [rdi+258h]
0x18006b991  mov     rax, [rcx]
0x18006b994  mov     rax, [rax+48h]
0x18006b998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b99d  mov     r8, rax
0x18006b9a0  lea     rdx, off_1800E1CE0; struct HvsDebugTraceParameters *
0x18006b9a7  mov     ecx, 0C020h; unsigned int
0x18006b9ac  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x18006b9b1  xor     edx, edx
0x18006b9b3  lea     rcx, [rbp+100h+var_180]
0x18006b9b7  call    ?Stop@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006b9bc  mov     [rbp+100h+var_180], r13
0x18006b9c0  lea     rcx, [rbp+100h+var_180]
0x18006b9c4  call    ?Destroy@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18006b9c9  lea     rcx, [rbp+100h+var_180]
0x18006b9cd  call    ??1?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18006b9d2  mov     rcx, rsi; SRWLock
0x18006b9d5  cmp     dword ptr [rsi+8], 0
0x18006b9d9  jz      short loc_18006B9EA
0x18006b9db  mov     dword ptr [rsi+8], 0
0x18006b9e2  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b9e8  jmp     short loc_18006B9F0
0x18006b9ea  call    cs:__imp_ReleaseSRWLockShared
0x18006b9f0  mov     rcx, [rbp+100h+var_30]
0x18006b9f7  xor     rcx, rsp; StackCookie
0x18006b9fa  call    __security_check_cookie
0x18006b9ff  lea     r11, [rsp+200h+var_20]
0x18006ba07  mov     rbx, [r11+38h]
0x18006ba0b  mov     rsi, [r11+40h]
0x18006ba0f  mov     rsp, r11
0x18006ba12  pop     r15
0x18006ba14  pop     r14
0x18006ba16  pop     r13
0x18006ba18  pop     rdi
0x18006ba19  pop     rbp
0x18006ba1a  retn
0x18006ba1b  lea     rcx, dword_1800E46D0
0x18006ba22  call    _Init_thread_header
0x18006ba27  cmp     cs:dword_1800E46D0, 0FFFFFFFFh
0x18006ba2e  jnz     loc_18006B98A
0x18006ba34  mov     cs:byte_1800E1CF4, r15b
0x18006ba3b  mov     cs:byte_1800E1CF5, r14b
0x18006ba42  lea     rcx, dword_1800E46D0
0x18006ba49  call    _Init_thread_footer
0x18006ba4e  jmp     loc_18006B98A
```
