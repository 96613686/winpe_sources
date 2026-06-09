# Notifier::NotifyThread::NotifyThread(CEventSystem2 &)

- ea: `0x180035214`
- end: `0x18003531e`
- name: `??0NotifyThread@Notifier@@QEAA@AEAVCEventSystem2@@@Z`
- size: `266`
- prototype: `Notifier::NotifyThread *__fastcall(Notifier::NotifyThread *this, struct CEventSystem2 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035184`

## callees

- `0x180009034`
- `0x180035214`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035257`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035284`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035257`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035284`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800352aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800352e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800352aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800352e1`

## string_xrefs

- `0x1800352cb`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800352ff`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800352bf`: `CreateEvent`
- `0x1800352f3`: `CreateEvent`

## pseudocode

```c
Notifier::NotifyThread *__fastcall Notifier::NotifyThread::NotifyThread(
        Notifier::NotifyThread *this,
        struct CEventSystem2 *a2)
{
  HANDLE EventW; // rax
  HANDLE v4; // rax

  *((_QWORD *)this + 8) = a2;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 28) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 72), 0x1F4u);
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_DWORD *)this + 46) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 144), 0x1F4u);
  *((_DWORD *)this + 48) = 1;
  *((_DWORD *)this + 49) = 1;
  *((_DWORD *)this + 50) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 7) = EventW;
  if ( !EventW )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x157u, 0x14u, L"CreateEvent");
  v4 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 15) = v4;
  if ( !v4 )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x159u, 0x14u, L"CreateEvent");
  return this;
}

```

## disassembly

```asm
0x180035214  mov     [rsp+arg_0], rbx
0x180035219  mov     [rsp+arg_8], rbp
0x18003521e  push    rdi
0x18003521f  sub     rsp, 20h
0x180035223  xor     ebp, ebp
0x180035225  mov     [rcx+40h], rdx
0x180035229  mov     [rcx], rbp
0x18003522c  mov     rdi, rcx
0x18003522f  mov     [rcx+8], rbp
0x180035233  mov     edx, 1F4h; dwSpinCount
0x180035238  mov     [rcx+10h], rbp
0x18003523c  mov     [rcx+18h], rbp
0x180035240  mov     [rcx+20h], rbp
0x180035244  mov     [rcx+28h], rbp
0x180035248  mov     [rcx+30h], rbp
0x18003524c  mov     [rcx+38h], rbp
0x180035250  mov     [rcx+70h], ebp
0x180035253  add     rcx, 48h ; 'H'; lpCriticalSection
0x180035257  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003525d  mov     [rdi+70h], eax
0x180035260  lea     rbx, [rdi+90h]
0x180035267  mov     [rdi+78h], rbp
0x18003526b  mov     edx, 1F4h; dwSpinCount
0x180035270  mov     [rdi+80h], rbp
0x180035277  mov     rcx, rbx; lpCriticalSection
0x18003527a  mov     [rdi+88h], rbp
0x180035281  mov     [rbx+28h], ebp
0x180035284  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003528a  mov     [rbx+28h], eax
0x18003528d  lea     edx, [rbp+1]; bManualReset
0x180035290  mov     [rdi+0C0h], edx
0x180035296  xor     r9d, r9d; lpName
0x180035299  xor     r8d, r8d; bInitialState
0x18003529c  mov     [rdi+0C4h], edx
0x1800352a2  xor     ecx, ecx; lpEventAttributes
0x1800352a4  mov     [rdi+0C8h], ebp
0x1800352aa  call    cs:__imp_CreateEventW
0x1800352b0  mov     [rdi+38h], rax
0x1800352b4  lea     ebx, [rbp+14h]
0x1800352b7  test    rax, rax
0x1800352ba  jnz     short loc_1800352D7
0x1800352bc  mov     r8d, ebx; unsigned __int16
0x1800352bf  lea     r9, aCreateevent; "CreateEvent"
0x1800352c6  mov     edx, 157h; unsigned int
0x1800352cb  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x1800352d2  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800352d7  xor     r9d, r9d; lpName
0x1800352da  xor     r8d, r8d; bInitialState
0x1800352dd  xor     edx, edx; bManualReset
0x1800352df  xor     ecx, ecx; lpEventAttributes
0x1800352e1  call    cs:__imp_CreateEventW
0x1800352e7  mov     [rdi+78h], rax
0x1800352eb  test    rax, rax
0x1800352ee  jnz     short loc_18003530B
0x1800352f0  mov     r8d, ebx; unsigned __int16
0x1800352f3  lea     r9, aCreateevent; "CreateEvent"
0x1800352fa  mov     edx, 159h; unsigned int
0x1800352ff  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180035306  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18003530b  mov     rbx, [rsp+28h+arg_0]
0x180035310  mov     rax, rdi
0x180035313  mov     rbp, [rsp+28h+arg_8]
0x180035318  add     rsp, 20h
0x18003531c  pop     rdi
0x18003531d  retn
```
