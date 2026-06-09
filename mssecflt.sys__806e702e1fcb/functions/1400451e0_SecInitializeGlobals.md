# SecInitializeGlobals

- ea: `0x1400451e0`
- end: `0x140045572`
- name: `SecInitializeGlobals`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x140045000`

## callees

- `0x140010587`
- `0x140011610`
- `0x140011700`
- `0x1400119c0`
- `0x1400402e0`
- `0x140040610`
- `0x1400451e0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14004552f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004552f`
- `ntoskrnl!PsProcessType` at `0x140045511`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004537d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400453b5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400453ed`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140045425`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004537d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400453b5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400453ed`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140045425`
- `ntoskrnl!PsInitialSystemProcess` at `0x140045525`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045225`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045459`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045225`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045459`
- `ntoskrnl!KeInitializeEvent` at `0x140045345`
- `ntoskrnl!KeInitializeEvent` at `0x140045345`

## pseudocode

```c
int __fastcall SecInitializeGlobals(__int64 a1, const void **a2)
{
  PVOID PoolWithTag; // rax
  int result; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  SIZE_T v9; // rdx
  PVOID v10; // rax
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _BYTE *v14; // rbx

  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(64, 1344, 1684497235);
  else
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x540u, 0x64676353u);
  SecData = PoolWithTag;
  if ( !PoolWithTag )
    return -1073741670;
  memset(PoolWithTag, 0, 0x540u);
  *(_WORD *)SecData = -5632;
  *((_WORD *)SecData + 1) = 1344;
  *((_QWORD *)SecData + 1) = a1;
  *((_QWORD *)SecData + 42) = 0;
  FltInitializePushLock_0((PULONG_PTR)SecData + 41);
  FltInitializePushLock_0((PULONG_PTR)SecData + 146);
  *((_BYTE *)SecData + 1176) = 0;
  v6 = (char *)SecData + 304;
  *((_QWORD *)SecData + 39) = (char *)SecData + 304;
  *v6 = v6;
  v7 = (char *)SecData + 1216;
  *((_QWORD *)SecData + 153) = (char *)SecData + 1216;
  *v7 = v7;
  v8 = (char *)SecData + 1248;
  *((_QWORD *)SecData + 157) = (char *)SecData + 1248;
  *v8 = v8;
  FltInitializePushLock_0((PULONG_PTR)SecData + 151);
  FltInitializePushLock_0((PULONG_PTR)SecData + 155);
  FltInitializePushLock_0((PULONG_PTR)SecData + 163);
  KeInitializeEvent((PRKEVENT)((char *)SecData + 1184), SynchronizationEvent, 1u);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 3, 0, 0, 0, 0x68u, 0x78696353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 4, 0, 0, 0, 0x10000u, 0x71666353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 7, 0, 0, 0, 0x320u, 0x57746553u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 8, 0, 0, 0, 0x10u, 0x73636353u, 0);
  v9 = *(unsigned __int16 *)a2 + 24LL;
  v10 = qword_140020008
      ? (PVOID)qword_140020008(256, v9, 1953719123)
      : ExAllocatePoolWithTag(PagedPool, v9, 0x74736353u);
  *((_QWORD *)SecData + 40) = v10;
  v11 = (void *)*((_QWORD *)SecData + 40);
  if ( !v11 )
    return -1073741670;
  memmove(v11, a2[1], *(unsigned __int16 *)a2);
  v12 = *(unsigned __int16 *)a2;
  v13 = *((_QWORD *)SecData + 40);
  *(_OWORD *)(v13 + v12) = *(_OWORD *)L"\\Parameters";
  *(_QWORD *)(v13 + v12 + 16) = *(_QWORD *)L"ers";
  *((_DWORD *)SecData + 316) = 0;
  *((_BYTE *)SecData + 1280) = 0;
  v14 = SecData;
  v14[1312] = KclHvciIsActive();
  result = ObOpenObjectByPointer(
             PsInitialSystemProcess,
             0x200u,
             0,
             0x40u,
             (POBJECT_TYPE)PsProcessType,
             0,
             (PHANDLE)SecData + 166);
  if ( result >= 0 )
  {
    result = KclInitializeSenseServiceSid(0x64736353u, (_QWORD *)SecData + 165);
    if ( result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400451e0  mov     [rsp+arg_0], rbx
0x1400451e5  mov     [rsp+arg_8], rbp
0x1400451ea  mov     [rsp+arg_10], rsi
0x1400451ef  push    rdi
0x1400451f0  sub     rsp, 40h
0x1400451f4  mov     rax, cs:qword_140020008
0x1400451fb  xor     ebp, ebp
0x1400451fd  mov     ebx, 540h
0x140045202  mov     rdi, rdx
0x140045205  mov     rsi, rcx
0x140045208  mov     r8d, 64676353h; Tag
0x14004520e  mov     edx, ebx; NumberOfBytes
0x140045210  test    rax, rax
0x140045213  jz      short loc_140045220
0x140045215  lea     ecx, [rbp+40h]
0x140045218  call    cs:__guard_dispatch_icall_fptr
0x14004521e  jmp     short loc_140045231
0x140045220  mov     ecx, 200h; PoolType
0x140045225  call    cs:__imp_ExAllocatePoolWithTag
0x14004522c  nop     dword ptr [rax+rax+00h]
0x140045231  mov     cs:SecData, rax
0x140045238  test    rax, rax
0x14004523b  jnz     short loc_140045247
0x14004523d  mov     eax, 0C000009Ah
0x140045242  jmp     loc_14004555C
0x140045247  mov     r8, rbx; Size
0x14004524a  xor     edx, edx; Val
0x14004524c  mov     rcx, rax; void *
0x14004524f  call    memset
0x140045254  mov     rax, cs:SecData
0x14004525b  mov     word ptr [rax], 0EA00h
0x140045260  mov     rax, cs:SecData
0x140045267  mov     [rax+2], bx
0x14004526b  mov     rax, cs:SecData
0x140045272  mov     [rax+8], rsi
0x140045276  mov     rax, cs:SecData
0x14004527d  mov     [rax+150h], rbp
0x140045284  mov     rcx, cs:SecData
0x14004528b  add     rcx, 148h; PushLock
0x140045292  call    FltInitializePushLock_0
0x140045297  mov     rcx, cs:SecData
0x14004529e  add     rcx, 490h; PushLock
0x1400452a5  call    FltInitializePushLock_0
0x1400452aa  mov     rax, cs:SecData
0x1400452b1  mov     [rax+498h], bpl
0x1400452b8  mov     rax, cs:SecData
0x1400452bf  add     rax, 130h
0x1400452c5  mov     [rax+8], rax
0x1400452c9  mov     [rax], rax
0x1400452cc  mov     rax, cs:SecData
0x1400452d3  add     rax, 4C0h
0x1400452d9  mov     [rax+8], rax
0x1400452dd  mov     [rax], rax
0x1400452e0  mov     rax, cs:SecData
0x1400452e7  add     rax, 4E0h
0x1400452ed  mov     [rax+8], rax
0x1400452f1  mov     [rax], rax
0x1400452f4  mov     rcx, cs:SecData
0x1400452fb  add     rcx, 4B8h; PushLock
0x140045302  call    FltInitializePushLock_0
0x140045307  mov     rcx, cs:SecData
0x14004530e  add     rcx, 4D8h; PushLock
0x140045315  call    FltInitializePushLock_0
0x14004531a  mov     rcx, cs:SecData
0x140045321  add     rcx, 518h; PushLock
0x140045328  call    FltInitializePushLock_0
0x14004532d  mov     rcx, cs:SecData
0x140045334  mov     ebx, 1
0x140045339  add     rcx, 4A0h; Event
0x140045340  mov     r8b, bl; State
0x140045343  mov     edx, ebx; Type
0x140045345  call    cs:__imp_KeInitializeEvent
0x14004534c  nop     dword ptr [rax+rax+00h]
0x140045351  mov     rcx, cs:SecData
0x140045358  xor     r9d, r9d; Flags
0x14004535b  mov     [rsp+48h+Depth], bp; Depth
0x140045360  add     rcx, 180h; Lookaside
0x140045367  mov     [rsp+48h+Tag], 78696353h; Tag
0x14004536f  xor     r8d, r8d; Free
0x140045372  xor     edx, edx; Allocate
0x140045374  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x14004537d  call    cs:__imp_ExInitializePagedLookasideList
0x140045384  nop     dword ptr [rax+rax+00h]
0x140045389  mov     rcx, cs:SecData
0x140045390  xor     r9d, r9d; Flags
0x140045393  mov     [rsp+48h+Depth], bp; Depth
0x140045398  add     rcx, 200h; Lookaside
0x14004539f  mov     [rsp+48h+Tag], 71666353h; Tag
0x1400453a7  xor     r8d, r8d; Free
0x1400453aa  xor     edx, edx; Allocate
0x1400453ac  mov     [rsp+48h+Size], 10000h; Size
0x1400453b5  call    cs:__imp_ExInitializePagedLookasideList
0x1400453bc  nop     dword ptr [rax+rax+00h]
0x1400453c1  mov     rcx, cs:SecData
0x1400453c8  xor     r9d, r9d; Flags
0x1400453cb  mov     [rsp+48h+Depth], bp; Depth
0x1400453d0  add     rcx, 380h; Lookaside
0x1400453d7  mov     [rsp+48h+Tag], 57746553h; Tag
0x1400453df  xor     r8d, r8d; Free
0x1400453e2  xor     edx, edx; Allocate
0x1400453e4  mov     [rsp+48h+Size], 320h; Size
0x1400453ed  call    cs:__imp_ExInitializePagedLookasideList
0x1400453f4  nop     dword ptr [rax+rax+00h]
0x1400453f9  mov     rcx, cs:SecData
0x140045400  xor     r9d, r9d; Flags
0x140045403  mov     [rsp+48h+Depth], bp; Depth
0x140045408  add     rcx, 400h; Lookaside
0x14004540f  mov     [rsp+48h+Tag], 73636353h; Tag
0x140045417  xor     r8d, r8d; Free
0x14004541a  mov     [rsp+48h+Size], 10h; Size
0x140045423  xor     edx, edx; Allocate
0x140045425  call    cs:__imp_ExInitializePagedLookasideList
0x14004542c  nop     dword ptr [rax+rax+00h]
0x140045431  movzx   edx, word ptr [rdi]
0x140045434  mov     r8d, 74736353h; Tag
0x14004543a  mov     rax, cs:qword_140020008
0x140045441  add     rdx, 18h; NumberOfBytes
0x140045445  test    rax, rax
0x140045448  jz      short loc_140045457
0x14004544a  mov     ecx, 100h
0x14004544f  call    cs:__guard_dispatch_icall_fptr
0x140045455  jmp     short loc_140045465
0x140045457  mov     ecx, ebx; PoolType
0x140045459  call    cs:__imp_ExAllocatePoolWithTag
0x140045460  nop     dword ptr [rax+rax+00h]
0x140045465  mov     rcx, rax
0x140045468  mov     rax, cs:SecData
0x14004546f  mov     [rax+140h], rcx
0x140045476  mov     rax, cs:SecData
0x14004547d  mov     rcx, [rax+140h]; void *
0x140045484  test    rcx, rcx
0x140045487  jz      loc_14004523D
0x14004548d  movzx   r8d, word ptr [rdi]; Size
0x140045491  mov     rdx, [rdi+8]; Src
0x140045495  call    memmove
0x14004549a  mov     rax, cs:SecData
0x1400454a1  movups  xmm0, xmmword ptr cs:aParameters; "\\Parameters"
0x1400454a8  movzx   edx, word ptr [rdi]
0x1400454ab  mov     rcx, [rax+140h]
0x1400454b2  movups  xmmword ptr [rcx+rdx], xmm0
0x1400454b6  movsd   xmm0, qword ptr cs:aParameters+10h; "ers"
0x1400454be  movsd   qword ptr [rcx+rdx+10h], xmm0
0x1400454c4  mov     rax, cs:SecData
0x1400454cb  mov     [rax+4F0h], ebp
0x1400454d1  mov     rax, cs:SecData
0x1400454d8  mov     [rax+500h], bpl
0x1400454df  mov     rbx, cs:SecData
0x1400454e6  call    KclHvciIsActive
0x1400454eb  mov     [rbx+520h], al
0x1400454f1  mov     r9d, 40h ; '@'; DesiredAccess
0x1400454f7  mov     rax, cs:SecData
0x1400454fe  xor     r8d, r8d; PassedAccessState
0x140045501  add     rax, 530h
0x140045507  mov     edx, 200h; HandleAttributes
0x14004550c  mov     qword ptr [rsp+48h+Depth], rax; Handle
0x140045511  mov     rax, cs:__imp_PsProcessType
0x140045518  mov     byte ptr [rsp+48h+Tag], bpl; AccessMode
0x14004551d  mov     rcx, [rax]
0x140045520  mov     [rsp+48h+Size], rcx; ObjectType
0x140045525  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14004552c  mov     rcx, [rcx]; Object
0x14004552f  call    cs:__imp_ObOpenObjectByPointer
0x140045536  nop     dword ptr [rax+rax+00h]
0x14004553b  test    eax, eax
0x14004553d  js      short loc_14004555C
0x14004553f  mov     rdx, cs:SecData
0x140045546  mov     ecx, 64736353h; Tag
0x14004554b  add     rdx, 528h
0x140045552  call    KclInitializeSenseServiceSid
0x140045557  test    eax, eax
0x140045559  cmovns  eax, ebp
0x14004555c  mov     rbx, [rsp+48h+arg_0]
0x140045561  mov     rbp, [rsp+48h+arg_8]
0x140045566  mov     rsi, [rsp+48h+arg_10]
0x14004556b  add     rsp, 40h
0x14004556f  pop     rdi
0x140045570  retn
```
