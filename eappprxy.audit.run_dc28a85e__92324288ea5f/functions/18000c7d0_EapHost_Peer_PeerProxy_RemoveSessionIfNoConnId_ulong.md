# EapHost::Peer::PeerProxy::RemoveSessionIfNoConnId(ulong)

- ea: `0x18000c7d0`
- end: `0x18000c885`
- name: `?RemoveSessionIfNoConnId@PeerProxy@Peer@EapHost@@QEAAHK@Z`
- size: `181`
- prototype: `__int64 __fastcall(EapHost::Peer::PeerProxy *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006100`
- `0x180006d20`

## callees

- `0x1800017a4`
- `0x18000c6e0`
- `0x18000c7d0`
- `0x18000cdfc`
- `0x18000ce34`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::PeerProxy::RemoveSessionIfNoConnId(EapHost::Peer::PeerProxy *this, int a2)
{
  unsigned int v2; // edi
  _QWORD *i; // rbx
  _DWORD *v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+28h] [rbp-10h]

  v2 = 0;
  v8 = 0;
  v9 = 0;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v8, &CriticalSection);
  for ( i = *(_QWORD **)peerProxy; i != (_QWORD *)peerProxy; i = (_QWORD *)*i )
  {
    v5 = (_DWORD *)i[2];
    if ( a2 == *v5 )
    {
      *v5 = 0;
      v6 = i[2];
      if ( *(_QWORD *)(v6 + 4) == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)(v6 + 12) == *(_QWORD *)GUID_NULL.Data4 )
      {
        EapHost::Peer::ConnectionSessionInfo::ReduceRefCount((EapHost::Peer::ConnectionSessionInfo *)v6);
        v2 = 1;
        *(_QWORD *)i[1] = *i;
        *(_QWORD *)(*i + 8LL) = i[1];
        --qword_1800154C8;
        operator delete(i);
      }
      break;
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v8);
  return v2;
}

```

## disassembly

```asm
0x18000c7d0  mov     rax, rsp
0x18000c7d3  mov     [rax+8], rbx
0x18000c7d7  mov     [rax+10h], rsi
0x18000c7db  push    rdi
0x18000c7dc  sub     rsp, 30h
0x18000c7e0  xor     edi, edi
0x18000c7e2  lea     rcx, [rax-18h]; this
0x18000c7e6  mov     esi, edx
0x18000c7e8  mov     [rax-18h], rdi
0x18000c7ec  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000c7f3  mov     [rax-10h], edi
0x18000c7f6  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000c7fb  mov     rcx, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000c802  mov     rbx, [rcx]
0x18000c805  cmp     rbx, rcx
0x18000c808  jz      short loc_18000C868
0x18000c80a  mov     rax, [rbx+10h]
0x18000c80e  cmp     esi, [rax]
0x18000c810  jz      short loc_18000C817
0x18000c812  mov     rbx, [rbx]
0x18000c815  jmp     short loc_18000C805
0x18000c817  mov     [rax], edi
0x18000c819  mov     rcx, [rbx+10h]; this
0x18000c81d  mov     rax, [rcx+4]
0x18000c821  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18000c828  jnz     short loc_18000C868
0x18000c82a  mov     rax, [rcx+0Ch]
0x18000c82e  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18000c835  jnz     short loc_18000C868
0x18000c837  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000c83c  mov     rdx, [rbx+8]
0x18000c840  mov     edi, 1
0x18000c845  mov     rax, [rbx]
0x18000c848  mov     rcx, rbx; void *
0x18000c84b  mov     [rdx], rax
0x18000c84e  mov     rdx, [rbx]
0x18000c851  mov     rax, [rbx+8]
0x18000c855  mov     [rdx+8], rax
0x18000c859  lea     edx, [rdi+17h]; unsigned __int64
0x18000c85c  sub     cs:qword_1800154C8, rdi
0x18000c863  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c868  lea     rcx, [rsp+38h+var_18]; this
0x18000c86d  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000c872  mov     rbx, [rsp+38h+arg_0]
0x18000c877  mov     eax, edi
0x18000c879  mov     rsi, [rsp+38h+arg_8]
0x18000c87e  add     rsp, 30h
0x18000c882  pop     rdi
0x18000c883  retn
```
