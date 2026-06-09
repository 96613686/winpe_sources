# CFlipManager::Initialize(void *)

- ea: `0x14004f040`
- end: `0x14004f46a`
- name: `?Initialize@CFlipManager@@IEAAJPEAX@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CFlipManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004f010`

## callees

- `0x14000cff0`
- `0x140011574`
- `0x14001206c`
- `0x14004f040`
- `0x140054430`
- `0x1400544c8`
- `0x1400a0cb0`
- `0x1403db360`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004f3ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f3d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f3e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f429`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f3ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f3d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f3e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f429`
- `ntoskrnl!ZwClose` at `0x14004f397`
- `ntoskrnl!ZwClose` at `0x14004f3c0`
- `ntoskrnl!ZwClose` at `0x14004f415`
- `ntoskrnl!ZwClose` at `0x14004f397`
- `ntoskrnl!ZwClose` at `0x14004f3c0`
- `ntoskrnl!ZwClose` at `0x14004f415`
- `ntoskrnl!ExEventObjectType` at `0x14004f1b0`
- `ntoskrnl!ExEventObjectType` at `0x14004f21c`
- `ntoskrnl!ExEventObjectType` at `0x14004f2ee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f1d8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f244`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f294`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f316`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f1d8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f244`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f294`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f316`
- `ntoskrnl!ZwCreateEvent` at `0x14004f19a`
- `ntoskrnl!ZwCreateEvent` at `0x14004f206`
- `ntoskrnl!ZwCreateEvent` at `0x14004f2d8`
- `ntoskrnl!ZwCreateEvent` at `0x14004f19a`
- `ntoskrnl!ZwCreateEvent` at `0x14004f206`
- `ntoskrnl!ZwCreateEvent` at `0x14004f2d8`
- `HAL!KeQueryPerformanceCounter` at `0x14004f352`
- `HAL!KeQueryPerformanceCounter` at `0x14004f352`

## pseudocode

```c
__int64 __fastcall CFlipManager::Initialize(CFlipManager *this, void *a2)
{
  signed __int32 v3; // eax
  struct CDWMBackchannelManager *v4; // rbx
  PVOID v5; // r12
  struct _KEVENT *v6; // r14
  PVOID v7; // r13
  PVOID v8; // r15
  NTSTATUS SessionFlipManagerRegistry; // edi
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  HANDLE v12; // rdi
  struct _OBJECT_TYPE *SharedSyncObjectType; // rax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  __int128 QuadPart; // rax
  HANDLE v17; // rcx
  void (__fastcall *v18)(_QWORD); // rbx
  unsigned int TracingId; // eax
  PVOID Object; // [rsp+30h] [rbp-49h] BYREF
  HANDLE v22; // [rsp+38h] [rbp-41h] BYREF
  PVOID v23; // [rsp+40h] [rbp-39h] BYREF
  PVOID v24; // [rsp+48h] [rbp-31h] BYREF
  PVOID v25; // [rsp+50h] [rbp-29h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+58h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  struct CDWMBackchannelManager *v28; // [rsp+E0h] [rbp+67h] BYREF
  HANDLE v29; // [rsp+E8h] [rbp+6Fh]
  void *EventHandle; // [rsp+F0h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+F8h] [rbp+7Fh] BYREF

  v29 = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *((_BYTE *)this + 32) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 29) = 1;
  *((_QWORD *)this + 30) = 1;
  *((_QWORD *)this + 31) = 1;
  *((_QWORD *)this + 33) = 1;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *((_QWORD *)this + 32) = 0;
  v3 = _InterlockedExchangeAdd(&CFlipManager::s_nextFlipManagerTracingId, 1u);
  *((_QWORD *)this + 34) = 0;
  *((_DWORD *)this + 85) = v3 + 1;
  v4 = 0;
  *((_QWORD *)this + 35) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *((_QWORD *)this + 36) = 0;
  v5 = 0;
  *(_OWORD *)((char *)this + 360) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  v6 = 0;
  *((_QWORD *)this + 28) = 0;
  v7 = 0;
  *((_QWORD *)this + 40) = 0;
  v8 = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  *((_QWORD *)this + 27) = (char *)this + 208;
  *((_QWORD *)this + 26) = (char *)this + 208;
  EventHandle = 0;
  Handle = 0;
  v28 = 0;
  v22 = 0;
  if ( (unsigned int)Feature_CompSwapchainRenderAndPresentSync__private_IsEnabledDeviceUsageNoInline(1) )
  {
    Object = 0;
    SessionFlipManagerRegistry = DxgkGetSessionFlipManagerRegistry((struct IFlipManagerRegistry **)&Object);
    if ( SessionFlipManagerRegistry < 0 )
      goto LABEL_15;
    (**(void (__fastcall ***)(PVOID, char *, char *))Object)(Object, (char *)this - 32, (char *)this + 344);
  }
  SessionFlipManagerRegistry = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( SessionFlipManagerRegistry >= 0 )
  {
    Object = 0;
    v10 = ObReferenceObjectByHandle(EventHandle, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &Object, 0);
    v5 = Object;
    SessionFlipManagerRegistry = v10;
    if ( v10 >= 0 )
    {
      SessionFlipManagerRegistry = ZwCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
      if ( SessionFlipManagerRegistry >= 0 )
      {
        v23 = 0;
        v11 = ObReferenceObjectByHandle(Handle, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &v23, 0);
        v6 = (struct _KEVENT *)v23;
        SessionFlipManagerRegistry = v11;
        if ( v11 >= 0 )
        {
          v12 = v29;
          if ( !v29
            || (*((_QWORD *)this + 6) = 1,
                v24 = 0,
                SharedSyncObjectType = (struct _OBJECT_TYPE *)DxgkGetSharedSyncObjectType(),
                v14 = ObReferenceObjectByHandle(v12, 0x1F0000u, SharedSyncObjectType, 1, &v24, 0),
                v7 = v24,
                SessionFlipManagerRegistry = v14,
                v14 >= 0) )
          {
            SessionFlipManagerRegistry = CDWMBackchannelManager::Create(v6, &v28);
            if ( SessionFlipManagerRegistry < 0
              || (SessionFlipManagerRegistry = ZwCreateEvent(&v22, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0),
                  SessionFlipManagerRegistry < 0)
              || (v25 = 0,
                  v15 = ObReferenceObjectByHandle(v22, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &v25, 0),
                  v8 = v25,
                  SessionFlipManagerRegistry = v15,
                  v15 < 0) )
            {
              v4 = v28;
            }
            else
            {
              *((_QWORD *)this + 36) = v5;
              *((_QWORD *)this + 37) = v6;
              v5 = 0;
              *((_QWORD *)this + 38) = v7;
              v6 = 0;
              v7 = 0;
              PerformanceFrequency.QuadPart = 0;
              KeQueryPerformanceCounter(&PerformanceFrequency);
              QuadPart = PerformanceFrequency.QuadPart;
              *((_QWORD *)this + 40) = v8;
              v8 = 0;
              *((_QWORD *)this + 39) = QuadPart / 2;
              *((_QWORD *)this + 28) = v28;
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( EventHandle )
    ZwClose(EventHandle);
  if ( v5 )
    ObfDereferenceObject(v5);
  if ( Handle )
    ZwClose(Handle);
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( v4 )
    (**(void (__fastcall ***)(struct CDWMBackchannelManager *, __int64))v4)(v4, 1);
  v17 = v22;
  if ( v22 )
    ZwClose(v22);
  if ( v8 )
    ObfDereferenceObject(v8);
  v18 = *(void (__fastcall **)(_QWORD))(DxgkGetWin32kImportTable(v17) + 328);
  TracingId = CFlipManager::GetTracingId(this);
  v18(TracingId);
  return (unsigned int)SessionFlipManagerRegistry;
}

```

## disassembly

```asm
0x14004f040  mov     [rsp-8+arg_8], rdx
0x14004f045  push    rbp
0x14004f046  push    rbx
0x14004f047  push    rsi
0x14004f048  push    rdi
0x14004f049  push    r12
0x14004f04b  push    r13
0x14004f04d  push    r14
0x14004f04f  push    r15
0x14004f051  lea     rbp, [rsp-1Fh]
0x14004f056  sub     rsp, 98h
0x14004f05d  xor     edi, edi
0x14004f05f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004f067  mov     rsi, rcx
0x14004f06a  mov     [rcx+20h], dil
0x14004f06e  mov     [rcx+28h], rdi
0x14004f072  xorps   xmm0, xmm0
0x14004f075  mov     [rcx+30h], rdi
0x14004f079  mov     [rcx+0A8h], rdi
0x14004f080  lea     ecx, [rdi+1]
0x14004f083  mov     [rsi+0E8h], rcx
0x14004f08a  mov     eax, ecx
0x14004f08c  mov     [rsi+0F0h], rcx
0x14004f093  mov     [rsi+0F8h], rcx
0x14004f09a  mov     [rsi+108h], rcx
0x14004f0a1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14004f0a9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14004f0ad  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x14004f0b1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004f0b6  mov     [rsi+100h], rdi
0x14004f0bd  lock xadd cs:?s_nextFlipManagerTracingId@CFlipManager@@0JA, eax; long CFlipManager::s_nextFlipManagerTracingId
0x14004f0c5  add     eax, ecx
0x14004f0c7  mov     [rsi+110h], rdi
0x14004f0ce  mov     [rsi+154h], eax
0x14004f0d4  mov     ebx, edi
0x14004f0d6  lea     rax, [rsi+158h]
0x14004f0dd  mov     [rsi+118h], rdi
0x14004f0e4  movups  xmmword ptr [rax], xmm0
0x14004f0e7  mov     [rsi+120h], rdi
0x14004f0ee  mov     r12d, edi
0x14004f0f1  movups  xmmword ptr [rax+10h], xmm0
0x14004f0f5  lea     rax, [rsi+0D0h]
0x14004f0fc  mov     [rsi+128h], rdi
0x14004f103  mov     [rsi+130h], rdi
0x14004f10a  mov     r14d, edi
0x14004f10d  mov     [rsi+0E0h], rdi
0x14004f114  mov     r13d, edi
0x14004f117  mov     [rsi+140h], rdi
0x14004f11e  mov     r15d, edi
0x14004f121  mov     [rsi+18h], rdi
0x14004f125  mov     [rsi+148h], rdi
0x14004f12c  mov     [rsi+150h], edi
0x14004f132  mov     [rax+8], rax
0x14004f136  mov     [rax], rax
0x14004f139  mov     [rbp+57h+EventHandle], rdi
0x14004f13d  mov     [rbp+57h+Handle], rdi
0x14004f141  mov     [rbp+57h+arg_0], rbx
0x14004f145  mov     [rbp+57h+var_98], rdi
0x14004f149  call    Feature_CompSwapchainRenderAndPresentSync__private_IsEnabledDeviceUsageNoInline
0x14004f14e  test    eax, eax
0x14004f150  jz      short loc_14004F185
0x14004f152  lea     rcx, [rbp+57h+Object]; struct IFlipManagerRegistry **
0x14004f156  mov     [rbp+57h+Object], rdi
0x14004f15a  call    DxgkGetSessionFlipManagerRegistry
0x14004f15f  mov     edi, eax
0x14004f161  test    eax, eax
0x14004f163  js      loc_14004F38E
0x14004f169  mov     rcx, [rbp+57h+Object]
0x14004f16d  lea     rdx, [rsi-20h]
0x14004f171  lea     r8, [rsi+158h]
0x14004f178  mov     rax, [rcx]
0x14004f17b  mov     rax, [rax]
0x14004f17e  call    _guard_dispatch_icall
0x14004f183  xor     edi, edi
0x14004f185  xor     r9d, r9d; EventType
0x14004f188  mov     [rsp+0D0h+InitialState], dil; InitialState
0x14004f18d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004f191  mov     edx, 1F0003h; DesiredAccess
0x14004f196  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14004f19a  call    cs:__imp_ZwCreateEvent
0x14004f1a1  nop     dword ptr [rax+rax+00h]
0x14004f1a6  mov     edi, eax
0x14004f1a8  test    eax, eax
0x14004f1aa  js      loc_14004F38E
0x14004f1b0  mov     r8, cs:ExEventObjectType
0x14004f1b7  lea     rax, [rbp+57h+Object]
0x14004f1bb  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14004f1bf  xor     r9d, r9d; AccessMode
0x14004f1c2  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f1c7  mov     edx, 100002h; DesiredAccess
0x14004f1cc  mov     [rbp+57h+Object], rbx
0x14004f1d0  mov     r8, [r8]; ObjectType
0x14004f1d3  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f1d8  call    cs:__imp_ObReferenceObjectByHandle
0x14004f1df  nop     dword ptr [rax+rax+00h]
0x14004f1e4  mov     r12, [rbp+57h+Object]
0x14004f1e8  mov     edi, eax
0x14004f1ea  test    eax, eax
0x14004f1ec  js      loc_14004F38E
0x14004f1f2  xor     r9d, r9d; EventType
0x14004f1f5  mov     [rsp+0D0h+InitialState], bl; InitialState
0x14004f1f9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004f1fd  mov     edx, 1F0003h; DesiredAccess
0x14004f202  lea     rcx, [rbp+57h+Handle]; EventHandle
0x14004f206  call    cs:__imp_ZwCreateEvent
0x14004f20d  nop     dword ptr [rax+rax+00h]
0x14004f212  mov     edi, eax
0x14004f214  test    eax, eax
0x14004f216  js      loc_14004F38E
0x14004f21c  mov     r8, cs:ExEventObjectType
0x14004f223  lea     rax, [rbp+57h+var_90]
0x14004f227  mov     rcx, [rbp+57h+Handle]; Handle
0x14004f22b  xor     r9d, r9d; AccessMode
0x14004f22e  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f233  mov     edx, 100002h; DesiredAccess
0x14004f238  mov     [rbp+57h+var_90], rbx
0x14004f23c  mov     r8, [r8]; ObjectType
0x14004f23f  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f244  call    cs:__imp_ObReferenceObjectByHandle
0x14004f24b  nop     dword ptr [rax+rax+00h]
0x14004f250  mov     r14, [rbp+57h+var_90]
0x14004f254  mov     edi, eax
0x14004f256  test    eax, eax
0x14004f258  js      loc_14004F38E
0x14004f25e  mov     rdi, [rbp+57h+arg_8]
0x14004f262  test    rdi, rdi
0x14004f265  jz      short loc_14004F2AE
0x14004f267  mov     qword ptr [rsi+30h], 1
0x14004f26f  mov     [rbp+57h+var_88], rbx
0x14004f273  call    DxgkGetSharedSyncObjectType
0x14004f278  mov     r8, rax; ObjectType
0x14004f27b  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f280  lea     rax, [rbp+57h+var_88]
0x14004f284  mov     r9b, 1; AccessMode
0x14004f287  mov     edx, 1F0000h; DesiredAccess
0x14004f28c  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f291  mov     rcx, rdi; Handle
0x14004f294  call    cs:__imp_ObReferenceObjectByHandle
0x14004f29b  nop     dword ptr [rax+rax+00h]
0x14004f2a0  mov     r13, [rbp+57h+var_88]
0x14004f2a4  mov     edi, eax
0x14004f2a6  test    eax, eax
0x14004f2a8  js      loc_14004F38E
0x14004f2ae  lea     rdx, [rbp+57h+arg_0]; struct CDWMBackchannelManager **
0x14004f2b2  mov     rcx, r14; struct _KEVENT *
0x14004f2b5  call    ?Create@CDWMBackchannelManager@@SAJPEAU_KEVENT@@PEAPEAV1@@Z; CDWMBackchannelManager::Create(_KEVENT *,CDWMBackchannelManager * *)
0x14004f2ba  mov     edi, eax
0x14004f2bc  test    eax, eax
0x14004f2be  js      loc_14004F38A
0x14004f2c4  xor     r9d, r9d; EventType
0x14004f2c7  mov     [rsp+0D0h+InitialState], bl; InitialState
0x14004f2cb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004f2cf  mov     edx, 1F0003h; DesiredAccess
0x14004f2d4  lea     rcx, [rbp+57h+var_98]; EventHandle
0x14004f2d8  call    cs:__imp_ZwCreateEvent
0x14004f2df  nop     dword ptr [rax+rax+00h]
0x14004f2e4  mov     edi, eax
0x14004f2e6  test    eax, eax
0x14004f2e8  js      loc_14004F38A
0x14004f2ee  mov     r8, cs:ExEventObjectType
0x14004f2f5  lea     rax, [rbp+57h+var_80]
0x14004f2f9  mov     rcx, [rbp+57h+var_98]; Handle
0x14004f2fd  xor     r9d, r9d; AccessMode
0x14004f300  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f305  mov     edx, 100002h; DesiredAccess
0x14004f30a  mov     [rbp+57h+var_80], rbx
0x14004f30e  mov     r8, [r8]; ObjectType
0x14004f311  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f316  call    cs:__imp_ObReferenceObjectByHandle
0x14004f31d  nop     dword ptr [rax+rax+00h]
0x14004f322  mov     r15, [rbp+57h+var_80]
0x14004f326  mov     edi, eax
0x14004f328  test    eax, eax
0x14004f32a  js      short loc_14004F38A
0x14004f32c  mov     [rsi+120h], r12
0x14004f333  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14004f337  mov     [rsi+128h], r14
0x14004f33e  xor     r12d, r12d
0x14004f341  mov     [rsi+130h], r13
0x14004f348  xor     r14d, r14d
0x14004f34b  xor     r13d, r13d
0x14004f34e  mov     qword ptr [rbp+57h+PerformanceFrequency], rbx
0x14004f352  call    cs:__imp_KeQueryPerformanceCounter
0x14004f359  nop     dword ptr [rax+rax+00h]
0x14004f35e  mov     rax, qword ptr [rbp+57h+PerformanceFrequency]
0x14004f362  lea     ecx, [r12+2]
0x14004f367  cqo
0x14004f369  mov     [rsi+140h], r15
0x14004f370  idiv    rcx
0x14004f373  xor     r15d, r15d
0x14004f376  mov     [rsi+138h], rax
0x14004f37d  mov     rax, [rbp+57h+arg_0]
0x14004f381  mov     [rsi+0E0h], rax
0x14004f388  jmp     short loc_14004F38E
0x14004f38a  mov     rbx, [rbp+57h+arg_0]
0x14004f38e  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14004f392  test    rcx, rcx
0x14004f395  jz      short loc_14004F3A3
0x14004f397  call    cs:__imp_ZwClose
0x14004f39e  nop     dword ptr [rax+rax+00h]
0x14004f3a3  test    r12, r12
0x14004f3a6  jz      short loc_14004F3B7
0x14004f3a8  mov     rcx, r12; Object
0x14004f3ab  call    cs:__imp_ObfDereferenceObject
0x14004f3b2  nop     dword ptr [rax+rax+00h]
0x14004f3b7  mov     rcx, [rbp+57h+Handle]; Handle
0x14004f3bb  test    rcx, rcx
0x14004f3be  jz      short loc_14004F3CC
0x14004f3c0  call    cs:__imp_ZwClose
0x14004f3c7  nop     dword ptr [rax+rax+00h]
0x14004f3cc  test    r14, r14
0x14004f3cf  jz      short loc_14004F3E0
0x14004f3d1  mov     rcx, r14; Object
0x14004f3d4  call    cs:__imp_ObfDereferenceObject
0x14004f3db  nop     dword ptr [rax+rax+00h]
0x14004f3e0  test    r13, r13
0x14004f3e3  jz      short loc_14004F3F4
0x14004f3e5  mov     rcx, r13; Object
0x14004f3e8  call    cs:__imp_ObfDereferenceObject
0x14004f3ef  nop     dword ptr [rax+rax+00h]
0x14004f3f4  test    rbx, rbx
0x14004f3f7  jz      short loc_14004F40C
0x14004f3f9  mov     rax, [rbx]
0x14004f3fc  mov     edx, 1
0x14004f401  mov     rcx, rbx
0x14004f404  mov     rax, [rax]
0x14004f407  call    _guard_dispatch_icall
0x14004f40c  mov     rcx, [rbp+57h+var_98]; Handle
0x14004f410  test    rcx, rcx
0x14004f413  jz      short loc_14004F421
0x14004f415  call    cs:__imp_ZwClose
0x14004f41c  nop     dword ptr [rax+rax+00h]
0x14004f421  test    r15, r15
0x14004f424  jz      short loc_14004F435
0x14004f426  mov     rcx, r15; Object
0x14004f429  call    cs:__imp_ObfDereferenceObject
0x14004f430  nop     dword ptr [rax+rax+00h]
0x14004f435  call    DxgkGetWin32kImportTable
0x14004f43a  mov     rcx, rsi; this
0x14004f43d  mov     rbx, [rax+148h]
0x14004f444  call    ?GetTracingId@CFlipManager@@QEAAIXZ; CFlipManager::GetTracingId(void)
0x14004f449  mov     ecx, eax
0x14004f44b  mov     rax, rbx
0x14004f44e  call    _guard_dispatch_icall
0x14004f453  mov     eax, edi
0x14004f455  add     rsp, 98h
0x14004f45c  pop     r15
0x14004f45e  pop     r14
0x14004f460  pop     r13
0x14004f462  pop     r12
0x14004f464  pop     rdi
0x14004f465  pop     rsi
0x14004f466  pop     rbx
0x14004f467  pop     rbp
0x14004f468  retn
```
