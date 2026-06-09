# PsmpStartServer

- ea: `0x180025078`
- end: `0x1800251ef`
- name: `PsmpStartServer`
- size: `375`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f1b0`

## callees

- `0x180024dc8`
- `0x180024e4c`
- `0x180024fd8`
- `0x180025078`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002509b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002509b`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002517c`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002517c`
- `RPCRT4!RpcServerInqBindingsEx` at `0x18002519c`
- `RPCRT4!RpcServerInqBindingsEx` at `0x18002519c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180025188`
- `RPCRT4!I_RpcMapWin32Status` at `0x180025188`

## pseudocode

```c
__int64 PsmpStartServer()
{
  int Descriptor; // ebx
  RPC_STATUS v1; // eax
  unsigned int i; // edi
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 68;
  CreateWellKnownSid(WinMediumLabelSid, 0, PsmpMediumLabel, &cbSid);
  Descriptor = PsmpInitializeQueryDescriptor();
  if ( Descriptor >= 0 )
  {
    qword_18003FA48 = (__int64)qword_180031A30;
    qword_18003FA90 = (__int64)PsmpAppContainerDescriptor;
    qword_18003FA50 = (__int64)PsmpSystemDescriptor;
    qword_18003FB10 = (__int64)PsmpAppContainerDescriptor;
    qword_18003FA68 = (__int64)qword_1800322A0;
    qword_18003FA78 = (__int64)&PsmpAuthenticateManagementInterface;
    qword_18003FA88 = (__int64)qword_180032910;
    qword_18003FAA8 = (__int64)qword_180030F10;
    qword_18003FAB0 = (__int64)PsmpQueryDescriptor;
    qword_18003FAC8 = (__int64)qword_180031700;
    qword_18003FAD0 = (__int64)PsmpTcDescriptor;
    qword_18003FAE8 = (__int64)qword_180032A30;
    qword_18003FAF0 = (__int64)PsmpResourceTimerDescriptor;
    qword_18003FB08 = (__int64)qword_180030BF0;
    v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, PsmpAppContainerDescriptor);
    if ( v1 )
      return (unsigned int)I_RpcMapWin32Status(v1);
    v1 = RpcServerInqBindingsEx(PsmpAppContainerDescriptor, &PsmpBindingVector);
    if ( v1 )
    {
      PsmpBindingVector = 0;
      return (unsigned int)I_RpcMapWin32Status(v1);
    }
    for ( i = 0; i < 7; ++i )
    {
      Descriptor = PsmpRegisterInterface((__int64)&PsmpRpcBindings[4 * i]);
      if ( Descriptor < 0 )
      {
        PsmpCleanupServer();
        return (unsigned int)Descriptor;
      }
    }
    return 0;
  }
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x180025078  mov     [rsp+arg_8], rbx
0x18002507d  push    rdi
0x18002507e  sub     rsp, 20h
0x180025082  xor     edx, edx; DomainSid
0x180025084  mov     [rsp+28h+cbSid], 44h ; 'D'
0x18002508c  lea     r9, [rsp+28h+cbSid]; cbSid
0x180025091  lea     r8, PsmpMediumLabel; pSid
0x180025098  lea     ecx, [rdx+43h]; WellKnownSidType
0x18002509b  call    cs:__imp_CreateWellKnownSid
0x1800250a1  call    PsmpInitializeQueryDescriptor
0x1800250a6  mov     ebx, eax
0x1800250a8  test    eax, eax
0x1800250aa  js      loc_1800251E2
0x1800250b0  lea     rax, qword_180031A30
0x1800250b7  mov     edx, 0Ah; MaxCalls
0x1800250bc  mov     cs:qword_18003FA48, rax
0x1800250c3  lea     rbx, PsmpAppContainerDescriptor
0x1800250ca  lea     rax, PsmpSystemDescriptor
0x1800250d1  mov     cs:qword_18003FA90, rbx
0x1800250d8  mov     cs:qword_18003FA50, rax
0x1800250df  lea     rcx, Protseq; "ncalrpc"
0x1800250e6  lea     rax, qword_1800322A0
0x1800250ed  mov     cs:qword_18003FB10, rbx
0x1800250f4  mov     cs:qword_18003FA68, rax
0x1800250fb  mov     r8, rbx; SecurityDescriptor
0x1800250fe  lea     rax, PsmpAuthenticateManagementInterface
0x180025105  mov     cs:qword_18003FA78, rax
0x18002510c  lea     rax, qword_180032910
0x180025113  mov     cs:qword_18003FA88, rax
0x18002511a  lea     rax, qword_180030F10
0x180025121  mov     cs:qword_18003FAA8, rax
0x180025128  lea     rax, PsmpQueryDescriptor
0x18002512f  mov     cs:qword_18003FAB0, rax
0x180025136  lea     rax, qword_180031700
0x18002513d  mov     cs:qword_18003FAC8, rax
0x180025144  lea     rax, PsmpTcDescriptor
0x18002514b  mov     cs:qword_18003FAD0, rax
0x180025152  lea     rax, qword_180032A30
0x180025159  mov     cs:qword_18003FAE8, rax
0x180025160  lea     rax, PsmpResourceTimerDescriptor
0x180025167  mov     cs:qword_18003FAF0, rax
0x18002516e  lea     rax, qword_180030BF0
0x180025175  mov     cs:qword_18003FB08, rax
0x18002517c  call    cs:__imp_RpcServerUseProtseqW
0x180025182  test    eax, eax
0x180025184  jz      short loc_180025192
0x180025186  mov     ecx, eax; Status
0x180025188  call    cs:__imp_I_RpcMapWin32Status
0x18002518e  mov     ebx, eax
0x180025190  jmp     short loc_1800251E2
0x180025192  lea     rdx, PsmpBindingVector; BindingVector
0x180025199  mov     rcx, rbx; SecurityDescriptor
0x18002519c  call    cs:__imp_RpcServerInqBindingsEx
0x1800251a2  test    eax, eax
0x1800251a4  jz      short loc_1800251B3
0x1800251a6  mov     cs:PsmpBindingVector, 0
0x1800251b1  jmp     short loc_180025186
0x1800251b3  xor     edi, edi
0x1800251b5  cmp     edi, 7
0x1800251b8  jnb     short loc_1800251E0
0x1800251ba  lea     rax, PsmpRpcBindings
0x1800251c1  mov     ecx, edi
0x1800251c3  shl     rcx, 5
0x1800251c7  add     rcx, rax
0x1800251ca  call    PsmpRegisterInterface
0x1800251cf  mov     ebx, eax
0x1800251d1  test    eax, eax
0x1800251d3  js      short loc_1800251D9
0x1800251d5  inc     edi
0x1800251d7  jmp     short loc_1800251B5
0x1800251d9  call    PsmpCleanupServer
0x1800251de  jmp     short loc_1800251E2
0x1800251e0  xor     ebx, ebx
0x1800251e2  mov     eax, ebx
0x1800251e4  mov     rbx, [rsp+28h+arg_8]
0x1800251e9  add     rsp, 20h
0x1800251ed  pop     rdi
0x1800251ee  retn
```
