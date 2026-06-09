# TransientSubChecker::CheckerThread::CheckerThread(CEventSystem2 &)

- ea: `0x180035080`
- end: `0x18003517b`
- name: `??0CheckerThread@TransientSubChecker@@QEAA@AEAVCEventSystem2@@@Z`
- size: `251`
- prototype: `TransientSubChecker::CheckerThread *__fastcall(TransientSubChecker::CheckerThread *this, struct CEventSystem2 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034588`

## callees

- `0x180009034`
- `0x180035080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800350b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800350eb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800350b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800350eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003510a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035143`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003510a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035143`

## string_xrefs

- `0x18003512d`: `com\complus\src\events\tier2\notify.cpp`
- `0x180035161`: `com\complus\src\events\tier2\notify.cpp`
- `0x180035121`: `CreateEvent`
- `0x180035155`: `CreateEvent`

## pseudocode

```c
TransientSubChecker::CheckerThread *__fastcall TransientSubChecker::CheckerThread::CheckerThread(
        TransientSubChecker::CheckerThread *this,
        struct CEventSystem2 *a2)
{
  HANDLE EventW; // rax
  HANDLE v4; // rax

  *((_QWORD *)this + 2) = a2;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 18) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 32), 0x1F4u);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 36) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 104), 0x1F4u);
  *((_DWORD *)this + 38) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( !EventW )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x630u, 0x11u, L"CreateEvent");
  v4 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = v4;
  if ( !v4 )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x633u, 0x11u, L"CreateEvent");
  return this;
}

```

## disassembly

```asm
0x180035080  mov     [rsp+arg_0], rbx
0x180035085  push    rdi
0x180035086  sub     rsp, 20h
0x18003508a  mov     [rcx+10h], rdx
0x18003508e  mov     rdi, rcx
0x180035091  mov     qword ptr [rcx], 0
0x180035098  mov     edx, 1F4h; dwSpinCount
0x18003509d  mov     qword ptr [rcx+8], 0
0x1800350a5  mov     dword ptr [rcx+18h], 0
0x1800350ac  mov     dword ptr [rcx+48h], 0
0x1800350b3  add     rcx, 20h ; ' '; lpCriticalSection
0x1800350b7  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800350bd  mov     [rdi+48h], eax
0x1800350c0  mov     edx, 1F4h; dwSpinCount
0x1800350c5  mov     qword ptr [rdi+50h], 0
0x1800350cd  lea     rcx, [rdi+68h]; lpCriticalSection
0x1800350d1  mov     qword ptr [rdi+58h], 0
0x1800350d9  mov     qword ptr [rdi+60h], 0
0x1800350e1  mov     dword ptr [rdi+90h], 0
0x1800350eb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800350f1  mov     edx, 1; bManualReset
0x1800350f6  mov     [rdi+90h], eax
0x1800350fc  xor     r9d, r9d; lpName
0x1800350ff  mov     [rdi+98h], edx
0x180035105  xor     r8d, r8d; bInitialState
0x180035108  xor     ecx, ecx; lpEventAttributes
0x18003510a  call    cs:__imp_CreateEventW
0x180035110  mov     [rdi+8], rax
0x180035114  mov     ebx, 11h
0x180035119  test    rax, rax
0x18003511c  jnz     short loc_180035139
0x18003511e  mov     r8d, ebx; unsigned __int16
0x180035121  lea     r9, aCreateevent; "CreateEvent"
0x180035128  mov     edx, 630h; unsigned int
0x18003512d  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180035134  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180035139  xor     r9d, r9d; lpName
0x18003513c  xor     r8d, r8d; bInitialState
0x18003513f  xor     edx, edx; bManualReset
0x180035141  xor     ecx, ecx; lpEventAttributes
0x180035143  call    cs:__imp_CreateEventW
0x180035149  mov     [rdi+50h], rax
0x18003514d  test    rax, rax
0x180035150  jnz     short loc_18003516D
0x180035152  mov     r8d, ebx; unsigned __int16
0x180035155  lea     r9, aCreateevent; "CreateEvent"
0x18003515c  mov     edx, 633h; unsigned int
0x180035161  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180035168  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18003516d  mov     rbx, [rsp+28h+arg_0]
0x180035172  mov     rax, rdi
0x180035175  add     rsp, 20h
0x180035179  pop     rdi
0x18003517a  retn
```
