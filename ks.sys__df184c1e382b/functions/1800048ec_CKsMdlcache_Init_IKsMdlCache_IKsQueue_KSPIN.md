# CKsMdlcache::Init(IKsMdlCache * *,IKsQueue *,_KSPIN *)

- ea: `0x1800048ec`
- end: `0x180004a6b`
- name: `?Init@CKsMdlcache@@QEAAJPEAPEAUIKsMdlCache@@PEAUIKsQueue@@PEAU_KSPIN@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(CKsMdlcache *__hidden this, struct IKsMdlCache **, struct IKsQueue *, struct _KSPIN *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800047dc`

## callees

- `0x1800048ec`
- `0x18000b7bc`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180004957`
- `ntoskrnl!RtlInitUnicodeString` at `0x180004957`
- `ntoskrnl!ZwClose` at `0x1800049f7`
- `ntoskrnl!ZwClose` at `0x1800049f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800049e5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800049e5`
- `ntoskrnl!ZwOpenEvent` at `0x1800049bf`
- `ntoskrnl!ZwOpenEvent` at `0x1800049bf`
- `ntoskrnl!KeInitializeSpinLock` at `0x180004972`
- `ntoskrnl!KeInitializeSpinLock` at `0x180004972`
- `ntoskrnl!KeInitializeEvent` at `0x180004987`
- `ntoskrnl!KeInitializeEvent` at `0x180004987`

## pseudocode

```c
__int64 __fastcall CKsMdlcache::Init(
        CKsMdlcache *this,
        struct IKsMdlCache **a2,
        struct IKsQueue *a3,
        struct _KSPIN *a4)
{
  struct IKsMdlCache **v5; // rsi
  NTSTATUS v7; // ebx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *EventHandle; // [rsp+C0h] [rbp+48h] BYREF

  EventHandle = a3;
  v5 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      10,
      (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids);
  }
  *((_DWORD *)this + 26) = 1;
  EventHandle = 0;
  *((_QWORD *)this + 7) = a4;
  *((_QWORD *)this + 12) = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\LowMemoryCondition");
  *((_QWORD *)this + 9) = (char *)this + 64;
  *((_QWORD *)this + 8) = (char *)this + 64;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 10);
  KeInitializeEvent((PRKEVENT)((char *)this + 112), NotificationEvent, 1u);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenEvent(&EventHandle, 0, &ObjectAttributes) < 0 )
  {
    *((_DWORD *)this + 26) = 0;
  }
  else
  {
    v7 = ObReferenceObjectByHandle(EventHandle, 0, 0, 0, (PVOID *)this + 12, 0);
    ZwClose(EventHandle);
    if ( v7 >= 0 )
    {
      *v5 = (struct IKsMdlCache *)this;
      (*(void (__fastcall **)(CKsMdlcache *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  *((_DWORD *)this + 22) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800048ec  mov     [rsp-30h+EventHandle], r8
0x1800048f1  push    rbp
0x1800048f2  push    rbx
0x1800048f3  push    rsi
0x1800048f4  push    rdi
0x1800048f5  push    r14
0x1800048f7  push    r15
0x1800048f9  mov     rbp, rsp
0x1800048fc  sub     rsp, 78h
0x180004900  mov     r14, r9
0x180004903  mov     rsi, rdx
0x180004906  mov     rdi, rcx
0x180004909  lea     rax, WPP_RECORDER_INITIALIZED
0x180004910  xor     r15d, r15d
0x180004913  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000491a  jnz     loc_180004A33
0x180004920  xorps   xmm1, xmm1
0x180004923  mov     dword ptr [rdi+68h], 1
0x18000492a  xorps   xmm0, xmm0
0x18000492d  mov     [rbp+EventHandle], r15
0x180004931  lea     rbx, [rdi+60h]
0x180004935  mov     [rdi+38h], r14
0x180004939  lea     rdx, SourceString; "\\KernelObjects\\LowMemoryCondition"
0x180004940  mov     [rbx], r15
0x180004943  lea     rcx, [rbp+DestinationString]; DestinationString
0x180004947  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000494b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18000494f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180004953  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180004957  call    cs:__imp_RtlInitUnicodeString
0x18000495e  nop     dword ptr [rax+rax+00h]
0x180004963  lea     rax, [rdi+40h]
0x180004967  lea     rcx, [rdi+50h]; SpinLock
0x18000496b  mov     [rax+8], rax
0x18000496f  mov     [rax], rax
0x180004972  call    cs:__imp_KeInitializeSpinLock
0x180004979  nop     dword ptr [rax+rax+00h]
0x18000497e  lea     rcx, [rdi+70h]; Event
0x180004982  mov     r8b, 1; State
0x180004985  xor     edx, edx; Type
0x180004987  call    cs:__imp_KeInitializeEvent
0x18000498e  nop     dword ptr [rax+rax+00h]
0x180004993  lea     rax, [rbp+DestinationString]
0x180004997  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000499e  xorps   xmm0, xmm0
0x1800049a1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800049a5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800049a9  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1800049ad  xor     edx, edx; DesiredAccess
0x1800049af  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1800049b6  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800049ba  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800049bf  call    cs:__imp_ZwOpenEvent
0x1800049c6  nop     dword ptr [rax+rax+00h]
0x1800049cb  test    eax, eax
0x1800049cd  js      short loc_180004A2D
0x1800049cf  mov     rcx, [rbp+EventHandle]; Handle
0x1800049d3  xor     r9d, r9d; AccessMode
0x1800049d6  mov     [rsp+78h+HandleInformation], r15; HandleInformation
0x1800049db  xor     r8d, r8d; ObjectType
0x1800049de  xor     edx, edx; DesiredAccess
0x1800049e0  mov     [rsp+78h+Object], rbx; Object
0x1800049e5  call    cs:__imp_ObReferenceObjectByHandle
0x1800049ec  nop     dword ptr [rax+rax+00h]
0x1800049f1  mov     rcx, [rbp+EventHandle]; Handle
0x1800049f5  mov     ebx, eax
0x1800049f7  call    cs:__imp_ZwClose
0x1800049fe  nop     dword ptr [rax+rax+00h]
0x180004a03  test    ebx, ebx
0x180004a05  js      short loc_180004A19
0x180004a07  mov     [rsi], rdi
0x180004a0a  mov     rcx, rdi
0x180004a0d  mov     rax, [rdi]
0x180004a10  mov     rax, [rax+8]
0x180004a14  call    _guard_dispatch_icall
0x180004a19  mov     [rdi+58h], r15d
0x180004a1d  xor     eax, eax
0x180004a1f  add     rsp, 78h
0x180004a23  pop     r15
0x180004a25  pop     r14
0x180004a27  pop     rdi
0x180004a28  pop     rsi
0x180004a29  pop     rbx
0x180004a2a  pop     rbp
0x180004a2b  retn
0x180004a2d  mov     [rdi+68h], r15d
0x180004a31  jmp     short loc_180004A19
0x180004a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a3a  cmp     [rcx+48h], r15w
0x180004a3f  jz      loc_180004920
0x180004a45  mov     rcx, [rcx+40h]
0x180004a49  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180004a50  mov     r9d, 0Ah
0x180004a56  mov     [rsp+78h+Object], rax
0x180004a5b  mov     dl, 5
0x180004a5d  lea     r8d, [r9-9]
0x180004a61  call    WPP_RECORDER_SF_
0x180004a66  jmp     loc_180004920
```
