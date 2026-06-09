# CFlipManager::Initialize(void *)

- ea: `0x14004ee40`
- end: `0x14004f26a`
- name: `?Initialize@CFlipManager@@IEAAJPEAX@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CFlipManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004ee10`

## callees

- `0x14000ce30`
- `0x1400113b4`
- `0x140011eac`
- `0x14004ee40`
- `0x140054250`
- `0x1400542e8`
- `0x1400a01e0`
- `0x1403daf40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004f1ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f1d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f1e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f229`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f1ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f1d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f1e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f229`
- `ntoskrnl!ZwClose` at `0x14004f197`
- `ntoskrnl!ZwClose` at `0x14004f1c0`
- `ntoskrnl!ZwClose` at `0x14004f215`
- `ntoskrnl!ZwClose` at `0x14004f197`
- `ntoskrnl!ZwClose` at `0x14004f1c0`
- `ntoskrnl!ZwClose` at `0x14004f215`
- `ntoskrnl!ExEventObjectType` at `0x14004efb0`
- `ntoskrnl!ExEventObjectType` at `0x14004f01c`
- `ntoskrnl!ExEventObjectType` at `0x14004f0ee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004efd8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f044`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f094`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f116`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004efd8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f044`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f094`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f116`
- `ntoskrnl!ZwCreateEvent` at `0x14004ef9a`
- `ntoskrnl!ZwCreateEvent` at `0x14004f006`
- `ntoskrnl!ZwCreateEvent` at `0x14004f0d8`
- `ntoskrnl!ZwCreateEvent` at `0x14004ef9a`
- `ntoskrnl!ZwCreateEvent` at `0x14004f006`
- `ntoskrnl!ZwCreateEvent` at `0x14004f0d8`
- `HAL!KeQueryPerformanceCounter` at `0x14004f152`
- `HAL!KeQueryPerformanceCounter` at `0x14004f152`

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
  __int64 v9; // rdx
  NTSTATUS SessionFlipManagerRegistry; // edi
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  HANDLE v13; // rdi
  struct _OBJECT_TYPE *SharedSyncObjectType; // rax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  __int128 QuadPart; // rax
  __int128 v18; // rtt
  HANDLE v19; // rcx
  void (__fastcall *v20)(_QWORD); // rbx
  unsigned int TracingId; // eax
  PVOID Object; // [rsp+30h] [rbp-49h] BYREF
  HANDLE v24; // [rsp+38h] [rbp-41h] BYREF
  PVOID v25; // [rsp+40h] [rbp-39h] BYREF
  PVOID v26; // [rsp+48h] [rbp-31h] BYREF
  PVOID v27; // [rsp+50h] [rbp-29h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+58h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  struct CDWMBackchannelManager *v30; // [rsp+E0h] [rbp+67h] BYREF
  HANDLE v31; // [rsp+E8h] [rbp+6Fh]
  void *EventHandle; // [rsp+F0h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+F8h] [rbp+7Fh] BYREF

  v31 = a2;
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
  v30 = 0;
  v24 = 0;
  if ( (unsigned int)Feature_CompSwapchainRenderAndPresentSync__private_IsEnabledDeviceUsageNoInline() )
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
    v11 = ObReferenceObjectByHandle(EventHandle, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &Object, 0);
    v5 = Object;
    SessionFlipManagerRegistry = v11;
    if ( v11 >= 0 )
    {
      SessionFlipManagerRegistry = ZwCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
      if ( SessionFlipManagerRegistry >= 0 )
      {
        v25 = 0;
        v12 = ObReferenceObjectByHandle(Handle, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &v25, 0);
        v6 = (struct _KEVENT *)v25;
        SessionFlipManagerRegistry = v12;
        if ( v12 >= 0 )
        {
          v13 = v31;
          if ( !v31
            || (*((_QWORD *)this + 6) = 1,
                v26 = 0,
                SharedSyncObjectType = (struct _OBJECT_TYPE *)DxgkGetSharedSyncObjectType(),
                v15 = ObReferenceObjectByHandle(v13, 0x1F0000u, SharedSyncObjectType, 1, &v26, 0),
                v7 = v26,
                SessionFlipManagerRegistry = v15,
                v15 >= 0) )
          {
            SessionFlipManagerRegistry = CDWMBackchannelManager::Create(v6, &v30);
            if ( SessionFlipManagerRegistry < 0
              || (SessionFlipManagerRegistry = ZwCreateEvent(&v24, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0),
                  SessionFlipManagerRegistry < 0)
              || (v27 = 0,
                  v16 = ObReferenceObjectByHandle(v24, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &v27, 0),
                  v8 = v27,
                  SessionFlipManagerRegistry = v16,
                  v16 < 0) )
            {
              v4 = v30;
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
              v18 = QuadPart;
              v9 = QuadPart % 2;
              v8 = 0;
              *((_QWORD *)this + 39) = v18 / 2;
              *((_QWORD *)this + 28) = v30;
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
  v19 = v24;
  if ( v24 )
    ZwClose(v24);
  if ( v8 )
    ObfDereferenceObject(v8);
  v20 = *(void (__fastcall **)(_QWORD))(DxgkGetWin32kImportTable(v19, v9) + 328);
  TracingId = CFlipManager::GetTracingId(this);
  v20(TracingId);
  return (unsigned int)SessionFlipManagerRegistry;
}

```

## disassembly

```asm
0x14004ee40  mov     [rsp-8+arg_8], rdx
0x14004ee45  push    rbp
0x14004ee46  push    rbx
0x14004ee47  push    rsi
0x14004ee48  push    rdi
0x14004ee49  push    r12
0x14004ee4b  push    r13
0x14004ee4d  push    r14
0x14004ee4f  push    r15
0x14004ee51  lea     rbp, [rsp-1Fh]
0x14004ee56  sub     rsp, 98h
0x14004ee5d  xor     edi, edi
0x14004ee5f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004ee67  mov     rsi, rcx
0x14004ee6a  mov     [rcx+20h], dil
0x14004ee6e  mov     [rcx+28h], rdi
0x14004ee72  xorps   xmm0, xmm0
0x14004ee75  mov     [rcx+30h], rdi
0x14004ee79  mov     [rcx+0A8h], rdi
0x14004ee80  lea     ecx, [rdi+1]
0x14004ee83  mov     [rsi+0E8h], rcx
0x14004ee8a  mov     eax, ecx
0x14004ee8c  mov     [rsi+0F0h], rcx
0x14004ee93  mov     [rsi+0F8h], rcx
0x14004ee9a  mov     [rsi+108h], rcx
0x14004eea1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14004eea9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14004eead  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x14004eeb1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004eeb6  mov     [rsi+100h], rdi
0x14004eebd  lock xadd cs:?s_nextFlipManagerTracingId@CFlipManager@@0JA, eax; long CFlipManager::s_nextFlipManagerTracingId
0x14004eec5  add     eax, ecx
0x14004eec7  mov     [rsi+110h], rdi
0x14004eece  mov     [rsi+154h], eax
0x14004eed4  mov     ebx, edi
0x14004eed6  lea     rax, [rsi+158h]
0x14004eedd  mov     [rsi+118h], rdi
0x14004eee4  movups  xmmword ptr [rax], xmm0
0x14004eee7  mov     [rsi+120h], rdi
0x14004eeee  mov     r12d, edi
0x14004eef1  movups  xmmword ptr [rax+10h], xmm0
0x14004eef5  lea     rax, [rsi+0D0h]
0x14004eefc  mov     [rsi+128h], rdi
0x14004ef03  mov     [rsi+130h], rdi
0x14004ef0a  mov     r14d, edi
0x14004ef0d  mov     [rsi+0E0h], rdi
0x14004ef14  mov     r13d, edi
0x14004ef17  mov     [rsi+140h], rdi
0x14004ef1e  mov     r15d, edi
0x14004ef21  mov     [rsi+18h], rdi
0x14004ef25  mov     [rsi+148h], rdi
0x14004ef2c  mov     [rsi+150h], edi
0x14004ef32  mov     [rax+8], rax
0x14004ef36  mov     [rax], rax
0x14004ef39  mov     [rbp+57h+EventHandle], rdi
0x14004ef3d  mov     [rbp+57h+Handle], rdi
0x14004ef41  mov     [rbp+57h+arg_0], rbx
0x14004ef45  mov     [rbp+57h+var_98], rdi
0x14004ef49  call    Feature_CompSwapchainRenderAndPresentSync__private_IsEnabledDeviceUsageNoInline
0x14004ef4e  test    eax, eax
0x14004ef50  jz      short loc_14004EF85
0x14004ef52  lea     rcx, [rbp+57h+Object]; struct IFlipManagerRegistry **
0x14004ef56  mov     [rbp+57h+Object], rdi
0x14004ef5a  call    DxgkGetSessionFlipManagerRegistry
0x14004ef5f  mov     edi, eax
0x14004ef61  test    eax, eax
0x14004ef63  js      loc_14004F18E
0x14004ef69  mov     rcx, [rbp+57h+Object]
0x14004ef6d  lea     rdx, [rsi-20h]
0x14004ef71  lea     r8, [rsi+158h]
0x14004ef78  mov     rax, [rcx]
0x14004ef7b  mov     rax, [rax]
0x14004ef7e  call    _guard_dispatch_icall
0x14004ef83  xor     edi, edi
0x14004ef85  xor     r9d, r9d; EventType
0x14004ef88  mov     [rsp+0D0h+InitialState], dil; InitialState
0x14004ef8d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004ef91  mov     edx, 1F0003h; DesiredAccess
0x14004ef96  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14004ef9a  call    cs:__imp_ZwCreateEvent
0x14004efa1  nop     dword ptr [rax+rax+00h]
0x14004efa6  mov     edi, eax
0x14004efa8  test    eax, eax
0x14004efaa  js      loc_14004F18E
0x14004efb0  mov     r8, cs:ExEventObjectType
0x14004efb7  lea     rax, [rbp+57h+Object]
0x14004efbb  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14004efbf  xor     r9d, r9d; AccessMode
0x14004efc2  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004efc7  mov     edx, 100002h; DesiredAccess
0x14004efcc  mov     [rbp+57h+Object], rbx
0x14004efd0  mov     r8, [r8]; ObjectType
0x14004efd3  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004efd8  call    cs:__imp_ObReferenceObjectByHandle
0x14004efdf  nop     dword ptr [rax+rax+00h]
0x14004efe4  mov     r12, [rbp+57h+Object]
0x14004efe8  mov     edi, eax
0x14004efea  test    eax, eax
0x14004efec  js      loc_14004F18E
0x14004eff2  xor     r9d, r9d; EventType
0x14004eff5  mov     [rsp+0D0h+InitialState], bl; InitialState
0x14004eff9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004effd  mov     edx, 1F0003h; DesiredAccess
0x14004f002  lea     rcx, [rbp+57h+Handle]; EventHandle
0x14004f006  call    cs:__imp_ZwCreateEvent
0x14004f00d  nop     dword ptr [rax+rax+00h]
0x14004f012  mov     edi, eax
0x14004f014  test    eax, eax
0x14004f016  js      loc_14004F18E
0x14004f01c  mov     r8, cs:ExEventObjectType
0x14004f023  lea     rax, [rbp+57h+var_90]
0x14004f027  mov     rcx, [rbp+57h+Handle]; Handle
0x14004f02b  xor     r9d, r9d; AccessMode
0x14004f02e  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f033  mov     edx, 100002h; DesiredAccess
0x14004f038  mov     [rbp+57h+var_90], rbx
0x14004f03c  mov     r8, [r8]; ObjectType
0x14004f03f  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f044  call    cs:__imp_ObReferenceObjectByHandle
0x14004f04b  nop     dword ptr [rax+rax+00h]
0x14004f050  mov     r14, [rbp+57h+var_90]
0x14004f054  mov     edi, eax
0x14004f056  test    eax, eax
0x14004f058  js      loc_14004F18E
0x14004f05e  mov     rdi, [rbp+57h+arg_8]
0x14004f062  test    rdi, rdi
0x14004f065  jz      short loc_14004F0AE
0x14004f067  mov     qword ptr [rsi+30h], 1
0x14004f06f  mov     [rbp+57h+var_88], rbx
0x14004f073  call    DxgkGetSharedSyncObjectType
0x14004f078  mov     r8, rax; ObjectType
0x14004f07b  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f080  lea     rax, [rbp+57h+var_88]
0x14004f084  mov     r9b, 1; AccessMode
0x14004f087  mov     edx, 1F0000h; DesiredAccess
0x14004f08c  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f091  mov     rcx, rdi; Handle
0x14004f094  call    cs:__imp_ObReferenceObjectByHandle
0x14004f09b  nop     dword ptr [rax+rax+00h]
0x14004f0a0  mov     r13, [rbp+57h+var_88]
0x14004f0a4  mov     edi, eax
0x14004f0a6  test    eax, eax
0x14004f0a8  js      loc_14004F18E
0x14004f0ae  lea     rdx, [rbp+57h+arg_0]; struct CDWMBackchannelManager **
0x14004f0b2  mov     rcx, r14; struct _KEVENT *
0x14004f0b5  call    ?Create@CDWMBackchannelManager@@SAJPEAU_KEVENT@@PEAPEAV1@@Z; CDWMBackchannelManager::Create(_KEVENT *,CDWMBackchannelManager * *)
0x14004f0ba  mov     edi, eax
0x14004f0bc  test    eax, eax
0x14004f0be  js      loc_14004F18A
0x14004f0c4  xor     r9d, r9d; EventType
0x14004f0c7  mov     [rsp+0D0h+InitialState], bl; InitialState
0x14004f0cb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004f0cf  mov     edx, 1F0003h; DesiredAccess
0x14004f0d4  lea     rcx, [rbp+57h+var_98]; EventHandle
0x14004f0d8  call    cs:__imp_ZwCreateEvent
0x14004f0df  nop     dword ptr [rax+rax+00h]
0x14004f0e4  mov     edi, eax
0x14004f0e6  test    eax, eax
0x14004f0e8  js      loc_14004F18A
0x14004f0ee  mov     r8, cs:ExEventObjectType
0x14004f0f5  lea     rax, [rbp+57h+var_80]
0x14004f0f9  mov     rcx, [rbp+57h+var_98]; Handle
0x14004f0fd  xor     r9d, r9d; AccessMode
0x14004f100  mov     [rsp+0D0h+HandleInformation], rbx; HandleInformation
0x14004f105  mov     edx, 100002h; DesiredAccess
0x14004f10a  mov     [rbp+57h+var_80], rbx
0x14004f10e  mov     r8, [r8]; ObjectType
0x14004f111  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x14004f116  call    cs:__imp_ObReferenceObjectByHandle
0x14004f11d  nop     dword ptr [rax+rax+00h]
0x14004f122  mov     r15, [rbp+57h+var_80]
0x14004f126  mov     edi, eax
0x14004f128  test    eax, eax
0x14004f12a  js      short loc_14004F18A
0x14004f12c  mov     [rsi+120h], r12
0x14004f133  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14004f137  mov     [rsi+128h], r14
0x14004f13e  xor     r12d, r12d
0x14004f141  mov     [rsi+130h], r13
0x14004f148  xor     r14d, r14d
0x14004f14b  xor     r13d, r13d
0x14004f14e  mov     qword ptr [rbp+57h+PerformanceFrequency], rbx
0x14004f152  call    cs:__imp_KeQueryPerformanceCounter
0x14004f159  nop     dword ptr [rax+rax+00h]
0x14004f15e  mov     rax, qword ptr [rbp+57h+PerformanceFrequency]
0x14004f162  lea     ecx, [r12+2]
0x14004f167  cqo
0x14004f169  mov     [rsi+140h], r15
0x14004f170  idiv    rcx
0x14004f173  xor     r15d, r15d
0x14004f176  mov     [rsi+138h], rax
0x14004f17d  mov     rax, [rbp+57h+arg_0]
0x14004f181  mov     [rsi+0E0h], rax
0x14004f188  jmp     short loc_14004F18E
0x14004f18a  mov     rbx, [rbp+57h+arg_0]
0x14004f18e  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14004f192  test    rcx, rcx
0x14004f195  jz      short loc_14004F1A3
0x14004f197  call    cs:__imp_ZwClose
0x14004f19e  nop     dword ptr [rax+rax+00h]
0x14004f1a3  test    r12, r12
0x14004f1a6  jz      short loc_14004F1B7
0x14004f1a8  mov     rcx, r12; Object
0x14004f1ab  call    cs:__imp_ObfDereferenceObject
0x14004f1b2  nop     dword ptr [rax+rax+00h]
0x14004f1b7  mov     rcx, [rbp+57h+Handle]; Handle
0x14004f1bb  test    rcx, rcx
0x14004f1be  jz      short loc_14004F1CC
0x14004f1c0  call    cs:__imp_ZwClose
0x14004f1c7  nop     dword ptr [rax+rax+00h]
0x14004f1cc  test    r14, r14
0x14004f1cf  jz      short loc_14004F1E0
0x14004f1d1  mov     rcx, r14; Object
0x14004f1d4  call    cs:__imp_ObfDereferenceObject
0x14004f1db  nop     dword ptr [rax+rax+00h]
0x14004f1e0  test    r13, r13
0x14004f1e3  jz      short loc_14004F1F4
0x14004f1e5  mov     rcx, r13; Object
0x14004f1e8  call    cs:__imp_ObfDereferenceObject
0x14004f1ef  nop     dword ptr [rax+rax+00h]
0x14004f1f4  test    rbx, rbx
0x14004f1f7  jz      short loc_14004F20C
0x14004f1f9  mov     rax, [rbx]
0x14004f1fc  mov     edx, 1
0x14004f201  mov     rcx, rbx
0x14004f204  mov     rax, [rax]
0x14004f207  call    _guard_dispatch_icall
0x14004f20c  mov     rcx, [rbp+57h+var_98]; Handle
0x14004f210  test    rcx, rcx
0x14004f213  jz      short loc_14004F221
0x14004f215  call    cs:__imp_ZwClose
0x14004f21c  nop     dword ptr [rax+rax+00h]
0x14004f221  test    r15, r15
0x14004f224  jz      short loc_14004F235
0x14004f226  mov     rcx, r15; Object
0x14004f229  call    cs:__imp_ObfDereferenceObject
0x14004f230  nop     dword ptr [rax+rax+00h]
0x14004f235  call    DxgkGetWin32kImportTable
0x14004f23a  mov     rcx, rsi; this
0x14004f23d  mov     rbx, [rax+148h]
0x14004f244  call    ?GetTracingId@CFlipManager@@QEAAIXZ; CFlipManager::GetTracingId(void)
0x14004f249  mov     ecx, eax
0x14004f24b  mov     rax, rbx
0x14004f24e  call    _guard_dispatch_icall
0x14004f253  mov     eax, edi
0x14004f255  add     rsp, 98h
0x14004f25c  pop     r15
0x14004f25e  pop     r14
0x14004f260  pop     r13
0x14004f262  pop     r12
0x14004f264  pop     rdi
0x14004f265  pop     rsi
0x14004f266  pop     rbx
0x14004f267  pop     rbp
0x14004f268  retn
```
