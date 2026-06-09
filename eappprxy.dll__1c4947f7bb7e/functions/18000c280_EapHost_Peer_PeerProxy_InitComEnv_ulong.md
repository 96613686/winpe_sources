# EapHost::Peer::PeerProxy::InitComEnv(ulong)

- ea: `0x18000c280`
- end: `0x18000c4f8`
- name: `?InitComEnv@PeerProxy@Peer@EapHost@@QEAAJK@Z`
- size: `632`
- prototype: `__int64 __fastcall(EapHost::Peer::PeerProxy *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009b90`

## callees

- `0x18000ade4`
- `0x18000c280`
- `0x18000cae8`
- `0x18000cda4`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000d1dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000c437`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000c437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c44b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c316`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c380`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c316`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c380`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c482`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapHost::Peer::PeerProxy::InitComEnv(EapHost::Peer::PeerProxy *this, int a2)
{
  HANDLE EventW; // rdi
  DWORD v3; // eax
  signed int v4; // ebx
  EapHost::Peer::PeerProxy *v5; // rcx
  bool v6; // sf
  HANDLE v7; // rbx
  DWORD LastError; // eax
  void *v9; // rbx
  signed int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+38h] [rbp-10h]
  int v14; // [rsp+58h] [rbp+10h] BYREF

  v14 = a2;
  v12 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, 4);
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v12, &CriticalSection);
  LODWORD(qword_180015528) = qword_180015528 + 1;
  if ( (_DWORD)qword_180015528 != 1 )
  {
    v4 = dword_180015530;
    v5 = (EapHost::Peer::PeerProxy *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_27;
  }
  qword_180015528 = 0x400000001LL;
  v14 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v7 = CreateEventW(0, 0, 0, 0);
    if ( !v7 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, LastError);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      CloseHandle(EventW);
      goto LABEL_27;
    }
    ObjectHandle::Clear((ObjectHandle *)&qword_1800154F8);
    hHandle = EventW;
    ObjectHandle::Clear((ObjectHandle *)&qword_180015508);
    hEvent = v7;
    v9 = (void *)_o__beginthreadex(0, 0, EapHost::Peer::PeerProxy::InitUninitComEnvProc, &peerProxy, 0, &v14, v12, v13);
    if ( v9 )
    {
      ObjectHandle::Clear((ObjectHandle *)&qword_180015518);
      qword_180015520 = v9;
      if ( !WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      {
        v4 = dword_180015530;
        ObjectHandle::Clear((ObjectHandle *)&qword_1800154F8);
        goto LABEL_27;
      }
    }
    v10 = GetLastError();
    v4 = v10;
    if ( v10 <= 0 )
    {
LABEL_27:
      v6 = v4 < 0;
      goto LABEL_28;
    }
    v4 = (unsigned __int16)v10;
LABEL_11:
    v4 |= 0x80070000;
    goto LABEL_27;
  }
  v3 = GetLastError();
  v4 = v3;
  v5 = (EapHost::Peer::PeerProxy *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, v3);
  v6 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4;
    goto LABEL_11;
  }
LABEL_28:
  if ( v6 )
    EapHost::Peer::PeerProxy::UninitComEnv(v5);
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c280  mov     rax, rsp
0x18000c283  mov     [rax+8], rbx
0x18000c287  mov     [rax+18h], rbp
0x18000c28b  mov     [rax+10h], edx
0x18000c28e  push    rdi
0x18000c28f  sub     rsp, 40h
0x18000c293  mov     qword ptr [rax-18h], 0
0x18000c29b  mov     dword ptr [rax-10h], 0
0x18000c2a2  lea     rbp, WPP_GLOBAL_Control
0x18000c2a9  mov     edi, 4
0x18000c2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2b5  cmp     rcx, rbp
0x18000c2b8  jz      short loc_18000C2D6
0x18000c2ba  test    [rcx+1Ch], dil
0x18000c2be  jz      short loc_18000C2D6
0x18000c2c0  lea     edx, [rdi+10h]
0x18000c2c3  mov     r9d, edi
0x18000c2c6  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c2cd  mov     rcx, [rcx+10h]
0x18000c2d1  call    WPP_SF_d
0x18000c2d6  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000c2dd  lea     rcx, [rsp+48h+var_18]; this
0x18000c2e2  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000c2e7  mov     eax, dword ptr cs:qword_180015528
0x18000c2ed  inc     eax
0x18000c2ef  mov     dword ptr cs:qword_180015528, eax
0x18000c2f5  cmp     eax, 1
0x18000c2f8  jnz     loc_18000C4A6
0x18000c2fe  mov     [rsp+48h+arg_8], 0
0x18000c306  mov     dword ptr cs:qword_180015528+4, edi
0x18000c30c  xor     r9d, r9d; lpName
0x18000c30f  xor     r8d, r8d; bInitialState
0x18000c312  xor     edx, edx; bManualReset
0x18000c314  xor     ecx, ecx; lpEventAttributes
0x18000c316  call    cs:__imp_CreateEventW
0x18000c31d  nop     dword ptr [rax+rax+00h]
0x18000c322  mov     rdi, rax
0x18000c325  test    rax, rax
0x18000c328  jnz     short loc_18000C376
0x18000c32a  call    cs:__imp_GetLastError
0x18000c331  nop     dword ptr [rax+rax+00h]
0x18000c336  mov     ebx, eax
0x18000c338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c33f  cmp     rcx, rbp
0x18000c342  jz      short loc_18000C360
0x18000c344  test    byte ptr [rcx+1Ch], 1
0x18000c348  jz      short loc_18000C360
0x18000c34a  lea     edx, [rdi+15h]
0x18000c34d  mov     r9d, eax
0x18000c350  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c357  mov     rcx, [rcx+10h]
0x18000c35b  call    WPP_SF_d
0x18000c360  test    ebx, ebx
0x18000c362  jle     loc_18000C4D3
0x18000c368  movzx   ebx, bx
0x18000c36b  or      ebx, 80070000h
0x18000c371  jmp     loc_18000C4D1
0x18000c376  xor     r9d, r9d; lpName
0x18000c379  xor     r8d, r8d; bInitialState
0x18000c37c  xor     edx, edx; bManualReset
0x18000c37e  xor     ecx, ecx; lpEventAttributes
0x18000c380  call    cs:__imp_CreateEventW
0x18000c387  nop     dword ptr [rax+rax+00h]
0x18000c38c  mov     rbx, rax
0x18000c38f  test    rax, rax
0x18000c392  jnz     short loc_18000C3ED
0x18000c394  call    cs:__imp_GetLastError
0x18000c39b  nop     dword ptr [rax+rax+00h]
0x18000c3a0  mov     ebx, eax
0x18000c3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a9  cmp     rcx, rbp
0x18000c3ac  jz      short loc_18000C3CC
0x18000c3ae  test    byte ptr [rcx+1Ch], 1
0x18000c3b2  jz      short loc_18000C3CC
0x18000c3b4  mov     edx, 16h
0x18000c3b9  mov     r9d, eax
0x18000c3bc  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c3c3  mov     rcx, [rcx+10h]
0x18000c3c7  call    WPP_SF_d
0x18000c3cc  test    ebx, ebx
0x18000c3ce  jle     short loc_18000C3D9
0x18000c3d0  movzx   ebx, bx
0x18000c3d3  or      ebx, 80070000h
0x18000c3d9  mov     rcx, rdi; hObject
0x18000c3dc  call    cs:__imp_CloseHandle
0x18000c3e3  nop     dword ptr [rax+rax+00h]
0x18000c3e8  jmp     loc_18000C4D1
0x18000c3ed  lea     rcx, qword_1800154F8; this
0x18000c3f4  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000c3f9  mov     cs:hHandle, rdi
0x18000c400  lea     rcx, qword_180015508; this
0x18000c407  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000c40c  mov     cs:hEvent, rbx
0x18000c413  lea     rax, [rsp+48h+arg_8]
0x18000c418  mov     [rsp+48h+var_20], rax
0x18000c41d  mov     [rsp+48h+var_28], 0
0x18000c425  lea     r9, ?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000c42c  lea     r8, ?InitUninitComEnvProc@PeerProxy@Peer@EapHost@@CAIPEAX@Z; EapHost::Peer::PeerProxy::InitUninitComEnvProc(void *)
0x18000c433  xor     edx, edx
0x18000c435  xor     ecx, ecx
0x18000c437  call    cs:__imp__o__beginthreadex
0x18000c43e  nop     dword ptr [rax+rax+00h]
0x18000c443  mov     rbx, rax
0x18000c446  test    rax, rax
0x18000c449  jnz     short loc_18000C465
0x18000c44b  call    cs:__imp_GetLastError
0x18000c452  nop     dword ptr [rax+rax+00h]
0x18000c457  mov     ebx, eax
0x18000c459  test    eax, eax
0x18000c45b  jle     short loc_18000C4D1
0x18000c45d  movzx   ebx, ax
0x18000c460  jmp     loc_18000C36B
0x18000c465  lea     rcx, qword_180015518; this
0x18000c46c  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000c471  mov     cs:qword_180015520, rbx
0x18000c478  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c47b  mov     rcx, cs:hHandle; hHandle
0x18000c482  call    cs:__imp_WaitForSingleObject
0x18000c489  nop     dword ptr [rax+rax+00h]
0x18000c48e  test    eax, eax
0x18000c490  jnz     short loc_18000C44B
0x18000c492  mov     ebx, cs:dword_180015530
0x18000c498  lea     rcx, qword_1800154F8; this
0x18000c49f  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000c4a4  jmp     short loc_18000C4D1
0x18000c4a6  mov     ebx, cs:dword_180015530
0x18000c4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b3  cmp     rcx, rbp
0x18000c4b6  jz      short loc_18000C4D1
0x18000c4b8  test    [rcx+1Ch], dil
0x18000c4bc  jz      short loc_18000C4D1
0x18000c4be  mov     edx, dword ptr cs:qword_180015528+4
0x18000c4c4  mov     [rsp+48h+var_28], edx
0x18000c4c8  mov     rcx, [rcx+10h]
0x18000c4cc  call    WPP_SF_DD
0x18000c4d1  test    ebx, ebx
0x18000c4d3  jns     short loc_18000C4DB
0x18000c4d5  call    ?UninitComEnv@PeerProxy@Peer@EapHost@@QEAAXXZ; EapHost::Peer::PeerProxy::UninitComEnv(void)
0x18000c4da  nop
0x18000c4db  lea     rcx, [rsp+48h+var_18]; this
0x18000c4e0  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000c4e5  mov     eax, ebx
0x18000c4e7  mov     rbx, [rsp+48h+arg_0]
0x18000c4ec  mov     rbp, [rsp+48h+arg_10]
0x18000c4f1  add     rsp, 40h
0x18000c4f5  pop     rdi
0x18000c4f6  retn
```
