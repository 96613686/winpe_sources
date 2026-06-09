# EapHost::Peer::PeerProxy::AddSession(EapHost::Peer::ConnectionSessionInfoPtr &)

- ea: `0x18000b8bc`
- end: `0x18000bab7`
- name: `?AddSession@PeerProxy@Peer@EapHost@@QEAAKAEAVConnectionSessionInfoPtr@23@@Z`
- size: `507`
- prototype: `unsigned int __fastcall(EapHost::Peer::PeerProxy *__hidden this, struct EapHost::Peer::ConnectionSessionInfoPtr *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180006100`

## callees

- `0x1800017a4`
- `0x1800030f8`
- `0x18000ade4`
- `0x18000b1b0`
- `0x18000b408`
- `0x18000b8bc`
- `0x18000bd30`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000d1dc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b9f2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b9f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b937`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b923`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b923`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapHost::Peer::PeerProxy::AddSession(
        EapHost::Peer::PeerProxy *this,
        struct EapHost::Peer::ConnectionSessionInfoPtr *a2)
{
  _QWORD *v3; // rsi
  HANDLE EventW; // rdi
  DWORD LastError; // eax
  unsigned int v6; // edi
  EapHost::Peer::PeerProxy *v7; // rcx
  unsigned int v8; // eax
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD **v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  _QWORD *v15; // rbx
  void *v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h]
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF
  int v20; // [rsp+48h] [rbp-20h]
  void **v21; // [rsp+50h] [rbp-18h]
  __int64 v22; // [rsp+58h] [rbp-10h]

  v3 = *(_QWORD **)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
      (_DWORD)v3 + 20,
      *(_DWORD *)v3);
  v19 = 0;
  v20 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    ObjectHandle::Clear((ObjectHandle *)(v3 + 13));
    v3[14] = EventW;
    EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v19, &CriticalSection);
    if ( *(_QWORD *)((char *)v3 + 4) == *(_QWORD *)&GUID_NULL.Data1
      && *(_QWORD *)((char *)v3 + 12) == *(_QWORD *)GUID_NULL.Data4
      || (v8 = EapHost::Peer::PeerProxy::FindAndReplace(v7, (struct EapHost::Peer::ConnectionSessionInfo *)v3),
          v6 = v8,
          v8 == 1168) )
    {
      std::list<EapHost::Peer::ConnectionSessionInfo *>::list<EapHost::Peer::ConnectionSessionInfo *>(&v17);
      if ( v18 == 0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("list too long");
      v9 = v17;
      v21 = &v17;
      v22 = 0;
      v10 = operator new(0x18u);
      v10[2] = v3;
      ++v18;
      v11 = (_QWORD *)v9[1];
      *v10 = v9;
      v10[1] = v11;
      v9[1] = v10;
      *v11 = v10;
      v12 = (_QWORD **)peerProxy;
      peerProxy = (__int64)v17;
      v17 = v12;
      v13 = qword_1800154C8;
      qword_1800154C8 = v18;
      v18 = v13;
      v6 = 0;
      *v12[1] = 0;
      v14 = *v12;
      if ( *v12 )
      {
        do
        {
          v15 = (_QWORD *)*v14;
          operator delete(v14, 0x18u);
          v14 = v15;
        }
        while ( v15 );
      }
      operator delete(v17, 0x18u);
    }
    else if ( v8 )
    {
      goto LABEL_19;
    }
    *(_QWORD *)a2 = 0;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, LastError);
LABEL_19:
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v19);
  return v6;
}

```

## disassembly

```asm
0x18000b8bc  push    rbp
0x18000b8be  push    rbx
0x18000b8bf  push    rsi
0x18000b8c0  push    rdi
0x18000b8c1  push    r12
0x18000b8c3  push    r14
0x18000b8c5  mov     rbp, rsp
0x18000b8c8  sub     rsp, 68h
0x18000b8cc  mov     r14, rdx
0x18000b8cf  mov     rsi, [rdx]
0x18000b8d2  lea     rbx, WPP_GLOBAL_Control
0x18000b8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8e0  cmp     rcx, rbx
0x18000b8e3  jz      short loc_18000B90A
0x18000b8e5  test    byte ptr [rcx+1Ch], 4
0x18000b8e9  jz      short loc_18000B90A
0x18000b8eb  lea     r9, [rsi+14h]
0x18000b8ef  mov     edx, 11h
0x18000b8f4  mov     eax, [rsi]
0x18000b8f6  mov     [rsp+68h+var_48], eax
0x18000b8fa  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000b901  mov     rcx, [rcx+10h]
0x18000b905  call    WPP_SF_Sd
0x18000b90a  mov     [rbp+var_28], 0
0x18000b912  mov     [rbp+var_20], 0
0x18000b919  xor     r9d, r9d; lpName
0x18000b91c  xor     r8d, r8d; bInitialState
0x18000b91f  xor     edx, edx; bManualReset
0x18000b921  xor     ecx, ecx; lpEventAttributes
0x18000b923  call    cs:__imp_CreateEventW
0x18000b92a  nop     dword ptr [rax+rax+00h]
0x18000b92f  mov     rdi, rax
0x18000b932  test    rax, rax
0x18000b935  jnz     short loc_18000B97C
0x18000b937  call    cs:__imp_GetLastError
0x18000b93e  nop     dword ptr [rax+rax+00h]
0x18000b943  mov     edi, eax
0x18000b945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b94c  cmp     rcx, rbx
0x18000b94f  jz      loc_18000BA9E
0x18000b955  test    byte ptr [rcx+1Ch], 1
0x18000b959  jz      loc_18000BA9E
0x18000b95f  mov     edx, 12h
0x18000b964  mov     r9d, eax
0x18000b967  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000b96e  mov     rcx, [rcx+10h]
0x18000b972  call    WPP_SF_d
0x18000b977  jmp     loc_18000BA9E
0x18000b97c  lea     rcx, [rsi+68h]; this
0x18000b980  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000b985  mov     [rsi+70h], rdi
0x18000b989  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000b990  lea     rcx, [rbp+var_28]; this
0x18000b994  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000b999  mov     rax, [rsi+4]
0x18000b99d  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18000b9a4  jnz     short loc_18000B9B3
0x18000b9a6  mov     rax, [rsi+0Ch]
0x18000b9aa  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18000b9b1  jz      short loc_18000B9D1
0x18000b9b3  mov     rdx, rsi; struct EapHost::Peer::ConnectionSessionInfo *
0x18000b9b6  call    ?FindAndReplace@PeerProxy@Peer@EapHost@@QEAAKPEAVConnectionSessionInfo@23@@Z; EapHost::Peer::PeerProxy::FindAndReplace(EapHost::Peer::ConnectionSessionInfo *)
0x18000b9bb  mov     edi, eax
0x18000b9bd  cmp     eax, 490h
0x18000b9c2  jz      short loc_18000B9D1
0x18000b9c4  test    eax, eax
0x18000b9c6  jnz     loc_18000BA9E
0x18000b9cc  jmp     loc_18000BA97
0x18000b9d1  lea     rcx, [rbp+var_38]
0x18000b9d5  call    ??0?$list@PEAVConnectionSessionInfo@Peer@EapHost@@V?$allocator@PEAVConnectionSessionInfo@Peer@EapHost@@@std@@@std@@QEAA@AEBV01@@Z; std::list<EapHost::Peer::ConnectionSessionInfo *>::list<EapHost::Peer::ConnectionSessionInfo *>(std::list<EapHost::Peer::ConnectionSessionInfo *> const &)
0x18000b9da  nop
0x18000b9db  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000b9e5  cmp     [rbp+var_30], rax
0x18000b9e9  jnz     short loc_18000B9FF
0x18000b9eb  lea     rcx, aListTooLong; "list too long"
0x18000b9f2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b9ff  mov     rbx, [rbp+var_38]
0x18000ba03  lea     rax, [rbp+var_38]
0x18000ba07  mov     [rbp+var_18], rax
0x18000ba0b  mov     [rbp+var_10], 0
0x18000ba13  mov     r12d, 18h
0x18000ba19  mov     ecx, r12d; dwBytes
0x18000ba1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba21  mov     [rax+10h], rsi
0x18000ba25  inc     [rbp+var_30]
0x18000ba29  mov     rcx, [rbx+8]
0x18000ba2d  mov     [rax], rbx
0x18000ba30  mov     [rax+8], rcx
0x18000ba34  mov     [rbx+8], rax
0x18000ba38  mov     [rcx], rax
0x18000ba3b  mov     rdx, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000ba42  mov     rax, [rbp+var_38]
0x18000ba46  mov     cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A, rax; EapHost::Peer::PeerProxy peerProxy
0x18000ba4d  mov     [rbp+var_38], rdx
0x18000ba51  mov     rcx, cs:qword_1800154C8
0x18000ba58  mov     rax, [rbp+var_30]
0x18000ba5c  mov     cs:qword_1800154C8, rax
0x18000ba63  mov     [rbp+var_30], rcx
0x18000ba67  xor     edi, edi
0x18000ba69  mov     rax, [rdx+8]
0x18000ba6d  mov     [rax], rdi
0x18000ba70  mov     rcx, [rdx]; void *
0x18000ba73  test    rcx, rcx
0x18000ba76  jz      short loc_18000BA8B
0x18000ba78  mov     rbx, [rcx]
0x18000ba7b  mov     rdx, r12; unsigned __int64
0x18000ba7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba83  mov     rcx, rbx
0x18000ba86  test    rbx, rbx
0x18000ba89  jnz     short loc_18000BA78
0x18000ba8b  mov     rdx, r12; unsigned __int64
0x18000ba8e  mov     rcx, [rbp+var_38]; void *
0x18000ba92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba97  mov     qword ptr [r14], 0
0x18000ba9e  lea     rcx, [rbp+var_28]; this
0x18000baa2  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000baa7  mov     eax, edi
0x18000baa9  add     rsp, 68h
0x18000baad  pop     r14
0x18000baaf  pop     r12
0x18000bab1  pop     rdi
0x18000bab2  pop     rsi
0x18000bab3  pop     rbx
0x18000bab4  pop     rbp
0x18000bab5  retn
```
