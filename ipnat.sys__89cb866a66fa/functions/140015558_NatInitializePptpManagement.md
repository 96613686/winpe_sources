# NatInitializePptpManagement

- ea: `0x140015558`
- end: `0x1400157ca`
- name: `NatInitializePptpManagement`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000540c`
- `0x140015558`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140015608`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140015608`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400155a3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400155a3`

## pseudocode

```c
__int64 NatInitializePptpManagement()
{
  int Editor; // eax
  unsigned int v1; // ebx
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  KeInitializeSpinLock(&PptpMappingLock);
  qword_1400320C8 = (__int64)&PptpMappingList;
  PptpMappingList = &PptpMappingList;
  qword_1400320D8 = (__int64)&qword_1400320D0;
  qword_1400320D0 = (__int64)&qword_1400320D0;
  ExInitializeNPagedLookasideList(&PptpLookasideList, NatAllocateFunction, 0, 0x200u, 0x48u, 0x5074614Eu, 0xAu);
  PptpRegisterEditorClient = 1;
  qword_140032128 = (__int64)NatOutboundDataHandlerPptpClient;
  byte_140032108 = 6;
  qword_140032130 = (__int64)NatInboundDataHandlerPptpClient;
  word_14003210A = -17658;
  dword_14003210C = 1;
  qword_140032110 = 0;
  qword_140032118 = 0;
  qword_140032120 = (__int64)NatDeleteHandlerPptp;
  Editor = NatCreateEditor(&PptpRegisterEditorClient);
  v1 = Editor;
  if ( Editor >= 0 )
  {
    PptpRegisterEditorServer = 1;
    qword_1400321A8 = (__int64)NatInboundDataHandlerPptpServer;
    byte_140032188 = 6;
    qword_1400321B0 = (__int64)NatOutboundDataHandlerPptpServer;
    word_14003218A = -17658;
    dword_14003218C = 0;
    qword_140032190 = 0;
    qword_140032198 = 0;
    qword_1400321A0 = (__int64)NatDeleteHandlerPptp;
    v4 = NatCreateEditor(&PptpRegisterEditorServer);
    v1 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, v4);
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v3 = 83;
      goto LABEL_23;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        80,
        WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids,
        (unsigned int)Editor);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v3 = 81;
LABEL_23:
      WPP_SF_d(v2->AttachedDevice, v3, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140015558  push    rbx
0x14001555a  push    rbp
0x14001555b  push    rsi
0x14001555c  push    r12
0x14001555e  push    r13
0x140015560  sub     rsp, 40h
0x140015564  mov     rcx, cs:WPP_GLOBAL_Control
0x14001556b  lea     rsi, WPP_GLOBAL_Control
0x140015572  lea     rbp, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140015579  cmp     rcx, rsi
0x14001557c  jz      short loc_14001559C
0x14001557e  mov     eax, [rcx+2Ch]
0x140015581  test    al, 1
0x140015583  jz      short loc_14001559C
0x140015585  cmp     byte ptr [rcx+29h], 6
0x140015589  jb      short loc_14001559C
0x14001558b  mov     rcx, [rcx+18h]
0x14001558f  mov     edx, 4Fh ; 'O'
0x140015594  mov     r8, rbp
0x140015597  call    WPP_SF_
0x14001559c  lea     rcx, PptpMappingLock; SpinLock
0x1400155a3  call    cs:__imp_KeInitializeSpinLock
0x1400155aa  nop     dword ptr [rax+rax+00h]
0x1400155af  lea     rax, PptpMappingList
0x1400155b6  mov     [rsp+68h+Depth], 0Ah; Depth
0x1400155bd  mov     cs:qword_1400320C8, rax
0x1400155c4  lea     rdx, NatAllocateFunction; Allocate
0x1400155cb  mov     cs:PptpMappingList, rax
0x1400155d2  lea     rcx, PptpLookasideList; Lookaside
0x1400155d9  lea     rax, qword_1400320D0
0x1400155e0  mov     [rsp+68h+Tag], 5074614Eh; Tag
0x1400155e8  mov     r9d, 200h; Flags
0x1400155ee  mov     cs:qword_1400320D8, rax
0x1400155f5  xor     r8d, r8d; Free
0x1400155f8  mov     cs:qword_1400320D0, rax
0x1400155ff  mov     [rsp+68h+Size], 48h ; 'H'; Size
0x140015608  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001560f  nop     dword ptr [rax+rax+00h]
0x140015614  lea     rax, NatOutboundDataHandlerPptpClient
0x14001561b  mov     cs:PptpRegisterEditorClient, 1
0x140015626  mov     cs:qword_140032128, rax
0x14001562d  lea     r12, NatDeleteHandlerPptp
0x140015634  lea     rax, NatInboundDataHandlerPptpClient
0x14001563b  mov     cs:byte_140032108, 6
0x140015642  mov     r13d, 0BB06h
0x140015648  mov     cs:qword_140032130, rax
0x14001564f  lea     rcx, PptpRegisterEditorClient
0x140015656  mov     cs:word_14003210A, r13w
0x14001565e  mov     cs:dword_14003210C, 1
0x140015668  mov     cs:qword_140032110, 0
0x140015673  mov     cs:qword_140032118, 0
0x14001567e  mov     cs:qword_140032120, r12
0x140015685  call    NatCreateEditor
0x14001568a  mov     ebx, eax
0x14001568c  test    eax, eax
0x14001568e  jns     short loc_1400156F1
0x140015690  mov     rcx, cs:WPP_GLOBAL_Control
0x140015697  cmp     rcx, rsi
0x14001569a  jz      loc_1400157BB
0x1400156a0  mov     edx, [rcx+2Ch]
0x1400156a3  test    dl, 1
0x1400156a6  jz      short loc_1400156C2
0x1400156a8  cmp     byte ptr [rcx+29h], 2
0x1400156ac  jb      short loc_1400156C2
0x1400156ae  mov     rcx, [rcx+18h]
0x1400156b2  mov     edx, 50h ; 'P'
0x1400156b7  mov     r9d, eax
0x1400156ba  mov     r8, rbp
0x1400156bd  call    WPP_SF_d
0x1400156c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156c9  cmp     rcx, rsi
0x1400156cc  jz      loc_1400157BB
0x1400156d2  mov     eax, [rcx+2Ch]
0x1400156d5  test    al, 1
0x1400156d7  jz      loc_1400157BB
0x1400156dd  cmp     byte ptr [rcx+29h], 6
0x1400156e1  jb      loc_1400157BB
0x1400156e7  mov     edx, 51h ; 'Q'
0x1400156ec  jmp     loc_1400157AC
0x1400156f1  lea     rax, NatInboundDataHandlerPptpServer
0x1400156f8  mov     cs:PptpRegisterEditorServer, 1
0x140015703  mov     cs:qword_1400321A8, rax
0x14001570a  lea     rcx, PptpRegisterEditorServer
0x140015711  lea     rax, NatOutboundDataHandlerPptpServer
0x140015718  mov     cs:byte_140032188, 6
0x14001571f  mov     cs:qword_1400321B0, rax
0x140015726  mov     cs:word_14003218A, r13w
0x14001572e  mov     cs:dword_14003218C, 0
0x140015738  mov     cs:qword_140032190, 0
0x140015743  mov     cs:qword_140032198, 0
0x14001574e  mov     cs:qword_1400321A0, r12
0x140015755  call    NatCreateEditor
0x14001575a  mov     ebx, eax
0x14001575c  test    eax, eax
0x14001575e  jz      short loc_14001578E
0x140015760  mov     rcx, cs:WPP_GLOBAL_Control
0x140015767  cmp     rcx, rsi
0x14001576a  jz      short loc_1400157BB
0x14001576c  mov     edx, [rcx+2Ch]
0x14001576f  test    dl, 1
0x140015772  jz      short loc_14001578E
0x140015774  cmp     byte ptr [rcx+29h], 2
0x140015778  jb      short loc_14001578E
0x14001577a  mov     rcx, [rcx+18h]
0x14001577e  mov     edx, 52h ; 'R'
0x140015783  mov     r9d, eax
0x140015786  mov     r8, rbp
0x140015789  call    WPP_SF_d
0x14001578e  mov     rcx, cs:WPP_GLOBAL_Control
0x140015795  cmp     rcx, rsi
0x140015798  jz      short loc_1400157BB
0x14001579a  mov     eax, [rcx+2Ch]
0x14001579d  test    al, 1
0x14001579f  jz      short loc_1400157BB
0x1400157a1  cmp     byte ptr [rcx+29h], 6
0x1400157a5  jb      short loc_1400157BB
0x1400157a7  mov     edx, 53h ; 'S'
0x1400157ac  mov     rcx, [rcx+18h]
0x1400157b0  mov     r9d, ebx
0x1400157b3  mov     r8, rbp
0x1400157b6  call    WPP_SF_d
0x1400157bb  mov     eax, ebx
0x1400157bd  add     rsp, 40h
0x1400157c1  pop     r13
0x1400157c3  pop     r12
0x1400157c5  pop     rsi
0x1400157c6  pop     rbp
0x1400157c7  pop     rbx
0x1400157c8  retn
```
