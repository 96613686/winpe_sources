# EapHost::Peer::PeerProxy::RemoveSessionwithClearConn(_GUID const &,_EAP_ERROR * *)

- ea: `0x18000c88c`
- end: `0x18000ca08`
- name: `?RemoveSessionwithClearConn@PeerProxy@Peer@EapHost@@QEAAKAEBU_GUID@@PEAPEAU_EAP_ERROR@@@Z`
- size: `380`
- prototype: `unsigned int __fastcall(EapHost::Peer::PeerProxy *__hidden this, const struct _GUID *, struct _EAP_ERROR **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800069e0`

## callees

- `0x1800017a4`
- `0x18000c160`
- `0x18000c204`
- `0x18000c6e0`
- `0x18000c88c`
- `0x18000ca10`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapHost::Peer::PeerProxy::RemoveSessionwithClearConn(
        EapHost::Peer::PeerProxy *this,
        const struct _GUID *a2,
        struct _EAP_ERROR **a3)
{
  __int64 v5; // rdi
  unsigned int v6; // ebp
  void *i; // rbx
  __int64 v8; // rcx
  _QWORD *HostApis; // rax
  __int64 v10; // rsi
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h]
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF
  EapHost::Peer::PeerProxy *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = this;
  v5 = 0;
  v6 = 0;
  v12 = 0;
  v13 = 0;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v12, &CriticalSection);
  for ( i = *(void **)peerProxy; i != (void *)peerProxy; i = *(void **)i )
  {
    v8 = *((_QWORD *)i + 2);
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)(v8 + 4) && *(_QWORD *)a2->Data4 == *(_QWORD *)(v8 + 12) )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 172), 1, 0) )
      {
        EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v12);
        return 1237;
      }
      EapHost::Peer::ConnectionSessionInfo::FreeBuffers(*((EapHost::Peer::ConnectionSessionInfo **)i + 2));
      HostApis = (_QWORD *)EapHost::Peer::ConnectionSessionInfo::GetHostApis(*((_QWORD *)i + 2), &v15);
      v10 = *HostApis;
      if ( *HostApis )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*HostApis);
        v5 = v10;
      }
      if ( v15 )
        (*(void (__fastcall **)(EapHost::Peer::PeerProxy *))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v5 )
      {
        v14 = (__int128)*a2;
        v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, struct _EAP_ERROR **))(*(_QWORD *)v5 + 112LL))(
               v5,
               &v14,
               a3);
      }
      EapHost::Peer::ConnectionSessionInfo::StopListeningThread(*((EapHost::Peer::ConnectionSessionInfo **)i + 2), 1);
      EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(*((EapHost::Peer::ConnectionSessionInfo **)i + 2));
      **((_QWORD **)i + 1) = *(_QWORD *)i;
      *(_QWORD *)(*(_QWORD *)i + 8LL) = *((_QWORD *)i + 1);
      --qword_1800154C8;
      operator delete(i);
      break;
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v12);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x18000c88c  mov     rax, rsp
0x18000c88f  mov     [rax+10h], rbx
0x18000c893  mov     [rax+18h], rbp
0x18000c897  mov     [rax+8], rcx
0x18000c89b  push    rsi
0x18000c89c  push    rdi
0x18000c89d  push    r12
0x18000c89f  push    r14
0x18000c8a1  push    r15
0x18000c8a3  sub     rsp, 40h
0x18000c8a7  mov     r15, r8
0x18000c8aa  mov     r14, rdx
0x18000c8ad  xor     edi, edi
0x18000c8af  xor     ebp, ebp
0x18000c8b1  mov     [rax-48h], rdi
0x18000c8b5  mov     [rax-40h], edi
0x18000c8b8  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000c8bf  lea     rcx, [rax-48h]; this
0x18000c8c3  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000c8c8  mov     r9, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000c8cf  mov     rbx, [r9]
0x18000c8d2  cmp     rbx, r9
0x18000c8d5  jz      loc_18000C9BA
0x18000c8db  mov     rcx, [rbx+10h]
0x18000c8df  mov     rax, [r14]
0x18000c8e2  cmp     rax, [rcx+4]
0x18000c8e6  jnz     short loc_18000C8F2
0x18000c8e8  mov     rax, [r14+8]
0x18000c8ec  cmp     rax, [rcx+0Ch]
0x18000c8f0  jz      short loc_18000C8F7
0x18000c8f2  mov     rbx, [rbx]
0x18000c8f5  jmp     short loc_18000C8D2
0x18000c8f7  xor     eax, eax
0x18000c8f9  lea     r12d, [rax+1]
0x18000c8fd  lock cmpxchg [rcx+0ACh], r12d
0x18000c906  jnz     loc_18000C9F6
0x18000c90c  mov     rcx, [rbx+10h]; this
0x18000c910  call    ?FreeBuffers@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::FreeBuffers(void)
0x18000c915  lea     rdx, [rsp+68h+arg_0]
0x18000c91a  mov     rcx, [rbx+10h]
0x18000c91e  call    ?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ; EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)
0x18000c923  mov     rsi, [rax]
0x18000c926  test    rsi, rsi
0x18000c929  jz      short loc_18000C93D
0x18000c92b  mov     rax, [rsi]
0x18000c92e  mov     rcx, rsi
0x18000c931  mov     rax, [rax+8]
0x18000c935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c93a  mov     rdi, rsi
0x18000c93d  mov     rcx, [rsp+68h+arg_0]
0x18000c942  test    rcx, rcx
0x18000c945  jz      short loc_18000C954
0x18000c947  mov     rax, [rcx]
0x18000c94a  mov     rax, [rax+10h]
0x18000c94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c953  nop
0x18000c954  test    rdi, rdi
0x18000c957  jz      short loc_18000C97C
0x18000c959  movups  xmm0, xmmword ptr [r14]
0x18000c95d  movdqu  [rsp+68h+var_38], xmm0
0x18000c963  mov     rax, [rdi]
0x18000c966  mov     r8, r15
0x18000c969  lea     rdx, [rsp+68h+var_38]
0x18000c96e  mov     rcx, rdi
0x18000c971  mov     rax, [rax+70h]
0x18000c975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c97a  mov     ebp, eax
0x18000c97c  mov     dl, r12b; bool
0x18000c97f  mov     rcx, [rbx+10h]; this
0x18000c983  call    ?StopListeningThread@ConnectionSessionInfo@Peer@EapHost@@QEAAX_N@Z; EapHost::Peer::ConnectionSessionInfo::StopListeningThread(bool)
0x18000c988  mov     rcx, [rbx+10h]; this
0x18000c98c  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000c991  mov     rdx, [rbx+8]
0x18000c995  mov     rcx, [rbx]
0x18000c998  mov     [rdx], rcx
0x18000c99b  mov     rdx, [rbx]
0x18000c99e  mov     rcx, [rbx+8]
0x18000c9a2  mov     [rdx+8], rcx
0x18000c9a6  sub     cs:qword_1800154C8, r12
0x18000c9ad  mov     edx, 18h; unsigned __int64
0x18000c9b2  mov     rcx, rbx; void *
0x18000c9b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c9ba  lea     rcx, [rsp+68h+var_48]; this
0x18000c9bf  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000c9c4  nop
0x18000c9c5  test    rdi, rdi
0x18000c9c8  jz      short loc_18000C9DA
0x18000c9ca  mov     rax, [rdi]
0x18000c9cd  mov     rcx, rdi
0x18000c9d0  mov     rax, [rax+10h]
0x18000c9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d9  nop
0x18000c9da  mov     eax, ebp
0x18000c9dc  lea     r11, [rsp+68h+var_28]
0x18000c9e1  mov     rbx, [r11+38h]
0x18000c9e5  mov     rbp, [r11+40h]
0x18000c9e9  mov     rsp, r11
0x18000c9ec  pop     r15
0x18000c9ee  pop     r14
0x18000c9f0  pop     r12
0x18000c9f2  pop     rdi
0x18000c9f3  pop     rsi
0x18000c9f4  retn
0x18000c9f6  lea     rcx, [rsp+68h+var_48]; this
0x18000c9fb  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000ca00  nop
0x18000ca01  mov     eax, 4D5h
0x18000ca06  jmp     short loc_18000C9DC
```
