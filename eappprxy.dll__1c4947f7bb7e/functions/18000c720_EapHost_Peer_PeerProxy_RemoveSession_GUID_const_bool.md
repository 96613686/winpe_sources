# EapHost::Peer::PeerProxy::RemoveSession(_GUID const &,bool)

- ea: `0x18000c720`
- end: `0x18000c7c8`
- name: `?RemoveSession@PeerProxy@Peer@EapHost@@QEAAXAEBU_GUID@@_N@Z`
- size: `168`
- prototype: `void __fastcall(EapHost::Peer::PeerProxy *__hidden this, const struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180006100`

## callees

- `0x1800017a4`
- `0x18000c6e0`
- `0x18000c720`
- `0x18000ca10`
- `0x18000cdfc`
- `0x18000ce34`

## pseudocode

```c
void __fastcall EapHost::Peer::PeerProxy::RemoveSession(EapHost::Peer::PeerProxy *this, const struct _GUID *a2)
{
  void *i; // rbx
  __int64 v4; // rcx
  __int64 v5; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+28h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v5, &CriticalSection);
  for ( i = *(void **)peerProxy; i != (void *)peerProxy; i = *(void **)i )
  {
    v4 = *((_QWORD *)i + 2);
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)(v4 + 4) && *(_QWORD *)a2->Data4 == *(_QWORD *)(v4 + 12) )
    {
      EapHost::Peer::ConnectionSessionInfo::StopListeningThread((EapHost::Peer::ConnectionSessionInfo *)v4, 0);
      EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(*((EapHost::Peer::ConnectionSessionInfo **)i + 2));
      **((_QWORD **)i + 1) = *(_QWORD *)i;
      *(_QWORD *)(*(_QWORD *)i + 8LL) = *((_QWORD *)i + 1);
      --qword_1800154C8;
      operator delete(i);
      break;
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v5);
}

```

## disassembly

```asm
0x18000c720  mov     rax, rsp
0x18000c723  mov     [rax+8], rbx
0x18000c727  push    rdi
0x18000c728  sub     rsp, 30h
0x18000c72c  mov     rdi, rdx
0x18000c72f  mov     qword ptr [rax-18h], 0
0x18000c737  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000c73e  mov     dword ptr [rax-10h], 0
0x18000c745  lea     rcx, [rax-18h]; this
0x18000c749  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000c74e  mov     r8, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000c755  mov     rbx, [r8]
0x18000c758  cmp     rbx, r8
0x18000c75b  jz      short loc_18000C7B2
0x18000c75d  mov     rcx, [rbx+10h]; this
0x18000c761  mov     rax, [rdi]
0x18000c764  cmp     rax, [rcx+4]
0x18000c768  jnz     short loc_18000C774
0x18000c76a  mov     rax, [rdi+8]
0x18000c76e  cmp     rax, [rcx+0Ch]
0x18000c772  jz      short loc_18000C779
0x18000c774  mov     rbx, [rbx]
0x18000c777  jmp     short loc_18000C758
0x18000c779  xor     edx, edx; bool
0x18000c77b  call    ?StopListeningThread@ConnectionSessionInfo@Peer@EapHost@@QEAAX_N@Z; EapHost::Peer::ConnectionSessionInfo::StopListeningThread(bool)
0x18000c780  mov     rcx, [rbx+10h]; this
0x18000c784  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000c789  mov     rdx, [rbx+8]
0x18000c78d  mov     rcx, rbx; void *
0x18000c790  mov     rax, [rbx]
0x18000c793  mov     [rdx], rax
0x18000c796  mov     rdx, [rbx]
0x18000c799  mov     rax, [rbx+8]
0x18000c79d  mov     [rdx+8], rax
0x18000c7a1  mov     edx, 18h; unsigned __int64
0x18000c7a6  dec     cs:qword_1800154C8
0x18000c7ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c7b2  lea     rcx, [rsp+38h+var_18]; this
0x18000c7b7  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000c7bc  mov     rbx, [rsp+38h+arg_0]
0x18000c7c1  add     rsp, 30h
0x18000c7c5  pop     rdi
0x18000c7c6  retn
```
