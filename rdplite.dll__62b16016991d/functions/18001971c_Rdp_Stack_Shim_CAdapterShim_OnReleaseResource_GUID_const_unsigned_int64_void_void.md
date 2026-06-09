# Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(_GUID const &,unsigned __int64,void *,void *)

- ea: `0x18001971c`
- end: `0x1800197dd`
- name: `?OnReleaseResource@CAdapterShim@Shim@Stack@Rdp@@QEAAXAEBU_GUID@@_KPEAX2@Z`
- size: `193`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this, const struct _GUID *, unsigned __int64, void *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021580`
- `0x180021640`

## callees

- `0x18000edbc`
- `0x18000f30c`
- `0x18000fc30`
- `0x180018cd0`
- `0x180019290`
- `0x180019348`

## string_xrefs

- `0x180019781`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(
        Rdp::Stack::Shim::CAdapterShim *this,
        const struct _GUID *a2,
        __int64 a3,
        void *a4,
        void *a5)
{
  __int64 v9; // rbx
  _BYTE v10[56]; // [rsp+30h] [rbp-38h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v10, (char *)this + 232);
  Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::AllocatePool(*((_QWORD *)this + 41));
  v9 = Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::EnsureBuffer(*((_QWORD *)this + 41), 52);
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    (_DWORD)retaddr,
    611,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    -2147024882,
    v9);
  *(_DWORD *)(v9 + 8) = 6;
  *(_DWORD *)v9 = 52;
  *(struct _GUID *)(v9 + 12) = *a2;
  *(_QWORD *)(v9 + 28) = a3;
  *(_QWORD *)(v9 + 36) = a4;
  *(_QWORD *)(v9 + 44) = a5;
  Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::Flush(*((_QWORD *)this + 41));
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v10);
}

```

## disassembly

```asm
0x18001971c  push    rbx
0x18001971e  push    rbp
0x18001971f  push    rsi
0x180019720  push    rdi
0x180019721  push    r14
0x180019723  sub     rsp, 40h
0x180019727  mov     rbp, r9
0x18001972a  mov     rsi, r8
0x18001972d  mov     rdi, rdx
0x180019730  mov     r14, rcx
0x180019733  lea     rdx, [rcx+0E8h]
0x18001973a  lea     rcx, [rsp+68h+var_38]
0x18001973f  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180019744  nop
0x180019745  mov     rcx, [r14+148h]
0x18001974c  call    ?AllocatePool@?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::AllocatePool(void)
0x180019751  mov     edx, 34h ; '4'
0x180019756  mov     rcx, [r14+148h]
0x18001975d  call    ?EnsureBuffer@?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@QEAAPEAX_K@Z; Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::EnsureBuffer(unsigned __int64)
0x180019762  mov     rbx, rax
0x180019765  mov     rcx, [rsp+68h]
0x18001976a  lea     rax, aUnableToEnsure; "Unable to ensure RDPCTRL_DST_RELEASE_RE"...
0x180019771  mov     [rsp+68h+var_40], rax
0x180019776  mov     [rsp+68h+var_48], rbx
0x18001977b  mov     r9d, 8007000Eh
0x180019781  lea     r8, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180019788  mov     edx, 263h
0x18001978d  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180019792  mov     dword ptr [rbx+8], 6
0x180019799  mov     dword ptr [rbx], 34h ; '4'
0x18001979f  movups  xmm0, xmmword ptr [rdi]
0x1800197a2  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800197a7  mov     [rbx+1Ch], rsi
0x1800197ab  mov     [rbx+24h], rbp
0x1800197af  mov     rax, [rsp+68h+arg_20]
0x1800197b7  mov     [rbx+2Ch], rax
0x1800197bb  mov     rcx, [r14+148h]
0x1800197c2  call    ?Flush@?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::Flush(void)
0x1800197c7  nop
0x1800197c8  lea     rcx, [rsp+68h+var_38]
0x1800197cd  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x1800197d2  add     rsp, 40h
0x1800197d6  pop     r14
0x1800197d8  pop     rdi
0x1800197d9  pop     rsi
0x1800197da  pop     rbp
0x1800197db  pop     rbx
0x1800197dc  retn
```
