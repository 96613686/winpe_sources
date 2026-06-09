# EapHost::Peer::PeerProxy::UninitComEnv(void)

- ea: `0x18000cae8`
- end: `0x18000cd9b`
- name: `?UninitComEnv@PeerProxy@Peer@EapHost@@QEAAXXZ`
- size: `691`
- prototype: `void __fastcall(EapHost::Peer::PeerProxy *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a8f0`
- `0x18000c280`

## callees

- `0x1800017a4`
- `0x1800022a8`
- `0x18000adb4`
- `0x18000ade4`
- `0x18000c204`
- `0x18000c6e0`
- `0x18000ca10`
- `0x18000cae8`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000d1dc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ccfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ccfd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ccde`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ccde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EapHost::Peer::PeerProxy::UninitComEnv(EapHost::Peer::PeerProxy *this)
{
  __int64 v1; // rbx
  int v2; // eax
  __int64 v3; // rax
  __int64 *v4; // rdi
  _QWORD *HostApis; // rax
  __int64 v6; // rsi
  __int64 v7; // rcx
  int v8; // eax
  _QWORD *v9; // rcx
  _QWORD *v10; // rdi
  DWORD LastError; // eax
  __int64 v12; // [rsp+20h] [rbp-20h] BYREF
  int v13; // [rsp+28h] [rbp-18h]
  __int128 v14; // [rsp+30h] [rbp-10h] BYREF
  EapHost::Peer::PeerProxy *v15; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF
  __int64 v17; // [rsp+80h] [rbp+40h]

  v15 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids);
  v1 = 0;
  v17 = 0;
  pv = 0;
  v12 = 0;
  v13 = 0;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v12, &CriticalSection);
  v2 = qword_180015528;
  if ( (int)qword_180015528 > 0 )
  {
    LODWORD(qword_180015528) = qword_180015528 - 1;
    if ( v2 == 1 )
    {
      v3 = peerProxy;
      v4 = *(__int64 **)peerProxy;
      while ( v4 != (__int64 *)v3 )
      {
        HostApis = (_QWORD *)EapHost::Peer::ConnectionSessionInfo::GetHostApis(v4[2], &v15);
        v6 = *HostApis;
        if ( v1 != *HostApis )
        {
          if ( v6 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*HostApis);
          if ( v1 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
          v1 = v6;
          v17 = v6;
        }
        if ( v15 )
          (*(void (__fastcall **)(EapHost::Peer::PeerProxy *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v1 )
        {
          v7 = v4[2];
          if ( *(_QWORD *)(v7 + 4) != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)(v7 + 12) != *(_QWORD *)GUID_NULL.Data4 )
          {
            v14 = *(_OWORD *)(v7 + 4);
            v8 = (*(__int64 (__fastcall **)(__int64, __int128 *, LPVOID *))(*(_QWORD *)v1 + 112LL))(v1, &v14, &pv);
            if ( v8 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
                  (unsigned int)v8);
              }
              if ( pv )
              {
                Free<TaskAllocator>((LPVOID *)pv);
                CoTaskMemFree(pv);
              }
            }
          }
        }
        EapHost::Peer::ConnectionSessionInfo::StopListeningThread((EapHost::Peer::ConnectionSessionInfo *)v4[2], 1);
        EapHost::Peer::ConnectionSessionInfo::ReduceRefCount((EapHost::Peer::ConnectionSessionInfo *)v4[2]);
        v4 = (__int64 *)*v4;
        v3 = peerProxy;
      }
      **(_QWORD **)(v3 + 8) = 0;
      v9 = *(_QWORD **)v3;
      if ( *(_QWORD *)v3 )
      {
        do
        {
          v10 = (_QWORD *)*v9;
          operator delete(v9, 0x18u);
          v9 = v10;
        }
        while ( v10 );
      }
      *(_QWORD *)peerProxy = peerProxy;
      *(_QWORD *)(peerProxy + 8) = peerProxy;
      qword_1800154C8 = 0;
      if ( hEvent )
      {
        if ( SetEvent(hEvent) )
        {
          if ( qword_180015520 )
            WaitForSingleObject(qword_180015520, 0xFFFFFFFF);
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
              LastError);
        }
      }
      ObjectHandle::Clear((ObjectHandle *)&qword_1800154F8);
      ObjectHandle::Clear((ObjectHandle *)&qword_180015508);
      ObjectHandle::Clear((ObjectHandle *)&qword_180015518);
      *(__int64 *)((char *)&qword_180015528 + 4) = 0;
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v12);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000cae8  mov     [rsp-28h+arg_0], rcx
0x18000caed  push    rbp
0x18000caee  push    rbx
0x18000caef  push    rsi
0x18000caf0  push    rdi
0x18000caf1  push    r15
0x18000caf3  mov     rbp, rsp
0x18000caf6  sub     rsp, 40h
0x18000cafa  lea     r15, WPP_GLOBAL_Control
0x18000cb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb08  cmp     rcx, r15
0x18000cb0b  jz      short loc_18000CB28
0x18000cb0d  test    byte ptr [rcx+1Ch], 4
0x18000cb11  jz      short loc_18000CB28
0x18000cb13  mov     edx, 18h
0x18000cb18  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000cb1f  mov     rcx, [rcx+10h]
0x18000cb23  call    WPP_SF_
0x18000cb28  xor     ebx, ebx
0x18000cb2a  mov     [rbp+arg_10], rbx
0x18000cb2e  mov     [rbp+pv], rbx
0x18000cb32  mov     [rbp+var_20], rbx
0x18000cb36  mov     [rbp+var_18], ebx
0x18000cb39  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000cb40  lea     rcx, [rbp+var_20]; this
0x18000cb44  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000cb49  nop
0x18000cb4a  mov     eax, dword ptr cs:qword_180015528
0x18000cb50  test    eax, eax
0x18000cb52  jle     loc_18000CD70
0x18000cb58  sub     eax, 1
0x18000cb5b  mov     dword ptr cs:qword_180015528, eax
0x18000cb61  jnz     loc_18000CD70
0x18000cb67  mov     rax, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000cb6e  mov     rdi, [rax]
0x18000cb71  cmp     rdi, rax
0x18000cb74  jz      loc_18000CC8A
0x18000cb7a  lea     rdx, [rbp+arg_0]
0x18000cb7e  mov     rcx, [rdi+10h]
0x18000cb82  call    ?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ; EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)
0x18000cb87  mov     rsi, [rax]
0x18000cb8a  cmp     rbx, rsi
0x18000cb8d  jz      short loc_18000CBBE
0x18000cb8f  test    rsi, rsi
0x18000cb92  jz      short loc_18000CBA3
0x18000cb94  mov     rax, [rsi]
0x18000cb97  mov     rcx, rsi
0x18000cb9a  mov     rax, [rax+8]
0x18000cb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba3  test    rbx, rbx
0x18000cba6  jz      short loc_18000CBB7
0x18000cba8  mov     rax, [rbx]
0x18000cbab  mov     rcx, rbx
0x18000cbae  mov     rax, [rax+10h]
0x18000cbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb7  mov     rbx, rsi
0x18000cbba  mov     [rbp+arg_10], rbx
0x18000cbbe  mov     rcx, [rbp+arg_0]
0x18000cbc2  test    rcx, rcx
0x18000cbc5  jz      short loc_18000CBD4
0x18000cbc7  mov     rax, [rcx]
0x18000cbca  mov     rax, [rax+10h]
0x18000cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd3  nop
0x18000cbd4  test    rbx, rbx
0x18000cbd7  jz      loc_18000CC67
0x18000cbdd  mov     rcx, [rdi+10h]
0x18000cbe1  mov     rax, [rcx+4]
0x18000cbe5  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18000cbec  jnz     short loc_18000CBFB
0x18000cbee  mov     rax, [rcx+0Ch]
0x18000cbf2  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18000cbf9  jz      short loc_18000CC67
0x18000cbfb  movups  xmm0, xmmword ptr [rcx+4]
0x18000cbff  movdqu  [rbp+var_10], xmm0
0x18000cc04  mov     rax, [rbx]
0x18000cc07  lea     r8, [rbp+pv]
0x18000cc0b  lea     rdx, [rbp+var_10]
0x18000cc0f  mov     rcx, rbx
0x18000cc12  mov     rax, [rax+70h]
0x18000cc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1b  test    eax, eax
0x18000cc1d  jns     short loc_18000CC67
0x18000cc1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc26  cmp     rcx, r15
0x18000cc29  jz      short loc_18000CC49
0x18000cc2b  test    byte ptr [rcx+1Ch], 1
0x18000cc2f  jz      short loc_18000CC49
0x18000cc31  mov     edx, 19h
0x18000cc36  mov     r9d, eax
0x18000cc39  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000cc40  mov     rcx, [rcx+10h]
0x18000cc44  call    WPP_SF_d
0x18000cc49  mov     rcx, [rbp+pv]; void *
0x18000cc4d  test    rcx, rcx
0x18000cc50  jz      short loc_18000CC67
0x18000cc52  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x18000cc57  mov     rcx, [rbp+pv]; pv
0x18000cc5b  call    cs:__imp_CoTaskMemFree
0x18000cc62  nop     dword ptr [rax+rax+00h]
0x18000cc67  mov     dl, 1; bool
0x18000cc69  mov     rcx, [rdi+10h]; this
0x18000cc6d  call    ?StopListeningThread@ConnectionSessionInfo@Peer@EapHost@@QEAAX_N@Z; EapHost::Peer::ConnectionSessionInfo::StopListeningThread(bool)
0x18000cc72  mov     rcx, [rdi+10h]; this
0x18000cc76  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000cc7b  mov     rdi, [rdi]
0x18000cc7e  mov     rax, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000cc85  jmp     loc_18000CB71
0x18000cc8a  mov     rcx, [rax+8]
0x18000cc8e  mov     qword ptr [rcx], 0
0x18000cc95  mov     rcx, [rax]; void *
0x18000cc98  test    rcx, rcx
0x18000cc9b  jz      short loc_18000CCB2
0x18000cc9d  mov     rdi, [rcx]
0x18000cca0  mov     edx, 18h; unsigned __int64
0x18000cca5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ccaa  mov     rcx, rdi
0x18000ccad  test    rdi, rdi
0x18000ccb0  jnz     short loc_18000CC9D
0x18000ccb2  mov     rax, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000ccb9  mov     [rax], rax
0x18000ccbc  mov     rax, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000ccc3  mov     [rax+8], rax
0x18000ccc7  mov     cs:qword_1800154C8, 0
0x18000ccd2  mov     rcx, cs:hEvent; hEvent
0x18000ccd9  test    rcx, rcx
0x18000ccdc  jz      short loc_18000CD41
0x18000ccde  call    cs:__imp_SetEvent
0x18000cce5  nop     dword ptr [rax+rax+00h]
0x18000ccea  test    eax, eax
0x18000ccec  jz      short loc_18000CD0B
0x18000ccee  mov     rcx, cs:qword_180015520; hHandle
0x18000ccf5  test    rcx, rcx
0x18000ccf8  jz      short loc_18000CD41
0x18000ccfa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ccfd  call    cs:__imp_WaitForSingleObject
0x18000cd04  nop     dword ptr [rax+rax+00h]
0x18000cd09  jmp     short loc_18000CD41
0x18000cd0b  call    cs:__imp_GetLastError
0x18000cd12  nop     dword ptr [rax+rax+00h]
0x18000cd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd1e  cmp     rcx, r15
0x18000cd21  jz      short loc_18000CD41
0x18000cd23  test    byte ptr [rcx+1Ch], 1
0x18000cd27  jz      short loc_18000CD41
0x18000cd29  mov     edx, 1Ah
0x18000cd2e  mov     r9d, eax
0x18000cd31  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000cd38  mov     rcx, [rcx+10h]
0x18000cd3c  call    WPP_SF_d
0x18000cd41  lea     rcx, qword_1800154F8; this
0x18000cd48  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000cd4d  lea     rcx, qword_180015508; this
0x18000cd54  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000cd59  lea     rcx, qword_180015518; this
0x18000cd60  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000cd65  mov     cs:qword_180015528+4, 0
0x18000cd70  lea     rcx, [rbp+var_20]; this
0x18000cd74  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000cd79  nop
0x18000cd7a  test    rbx, rbx
0x18000cd7d  jz      short loc_18000CD8F
0x18000cd7f  mov     rax, [rbx]
0x18000cd82  mov     rcx, rbx
0x18000cd85  mov     rax, [rax+10h]
0x18000cd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd8e  nop
0x18000cd8f  add     rsp, 40h
0x18000cd93  pop     r15
0x18000cd95  pop     rdi
0x18000cd96  pop     rsi
0x18000cd97  pop     rbx
0x18000cd98  pop     rbp
0x18000cd99  retn
```
