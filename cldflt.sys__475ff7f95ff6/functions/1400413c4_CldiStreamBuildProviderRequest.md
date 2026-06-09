# CldiStreamBuildProviderRequest

- ea: `0x1400413c4`
- end: `0x140041591`
- name: `CldiStreamBuildProviderRequest`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140074fd0`

## callees

- `0x140003c50`
- `0x14000c960`
- `0x14000ffcc`
- `0x140035dc8`
- `0x1400413c4`
- `0x140056770`
- `0x140058ddc`
- `0x140075170`
- `0x140081b4c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004155a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004155a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004154e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004154e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041533`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041533`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004151e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004151e`
- `ntoskrnl!PsGetProcessId` at `0x1400413ec`
- `ntoskrnl!PsGetProcessId` at `0x1400413ec`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400413dd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400413dd`

## pseudocode

```c
__int64 __fastcall CldiStreamBuildProviderRequest(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  struct _KPROCESS *CurrentProcess; // rax
  int ProcessId; // eax
  KIRQL *v10; // rdx
  char *Request; // rsi
  unsigned int v12; // edi
  _QWORD *v13; // rdx
  KIRQL v14; // dl

  CurrentProcess = IoGetCurrentProcess();
  ProcessId = (unsigned int)PsGetProcessId(CurrentProcess);
  Request = CldiStreamAllocateRequest(0, a4, ProcessId, (__int64)a1, 1073741825, 0, 0, 0, 1, 0);
  if ( Request )
  {
    CldiStreamCdqACQUIRE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v10);
    if ( a1[7] )
    {
      CldiStreamDeleteRequest(Request);
      v12 = 0;
    }
    else
    {
      a1[7] = Request;
      v13 = (_QWORD *)a1[3];
      if ( (_QWORD *)*v13 != a1 + 2 )
        __fastfail(3u);
      v12 = 0;
      *((_QWORD *)Request + 1) = a1 + 2;
      *((_QWORD *)Request + 2) = v13;
      *v13 = Request + 8;
      a1[3] = Request + 8;
      *((_QWORD *)Request + 44) = 0;
      *((_QWORD *)Request + 45) = HsmpGetStreamSize(*(_QWORD *)*a1);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      CldiStreamInsertIntoGlobalRequestListNoLock(Request);
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
    }
    CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v14);
  }
  else
  {
    v12 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiiiLd(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
        a1,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*a1 + 16LL) + 32LL),
        a2,
        a3,
        a4,
        -1073741670);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1400413c4  push    rbx
0x1400413c6  push    rbp
0x1400413c7  push    rsi
0x1400413c8  push    rdi
0x1400413c9  push    r14
0x1400413cb  push    r15
0x1400413cd  sub     rsp, 58h
0x1400413d1  mov     ebp, r9d
0x1400413d4  mov     r14, r8
0x1400413d7  mov     r15, rdx
0x1400413da  mov     rbx, rcx
0x1400413dd  call    cs:__imp_IoGetCurrentProcess
0x1400413e4  nop     dword ptr [rax+rax+00h]
0x1400413e9  mov     rcx, rax; Process
0x1400413ec  call    cs:__imp_PsGetProcessId
0x1400413f3  nop     dword ptr [rax+rax+00h]
0x1400413f8  mov     [rsp+88h+var_40], 0
0x140041401  mov     r9, rbx
0x140041404  mov     byte ptr [rsp+88h+var_48], 1
0x140041409  mov     r8d, eax
0x14004140c  mov     [rsp+88h+var_50], 0
0x140041415  mov     edx, ebp
0x140041417  mov     [rsp+88h+var_58], 0
0x140041420  xor     ecx, ecx
0x140041422  mov     [rsp+88h+var_60], 0
0x14004142b  mov     dword ptr [rsp+88h+var_68], 40000001h
0x140041433  call    CldiStreamAllocateRequest
0x140041438  mov     rsi, rax
0x14004143b  test    rax, rax
0x14004143e  jnz     short loc_1400414BA
0x140041440  mov     edi, 0C000009Ah
0x140041445  mov     ecx, edi
0x140041447  call    HsmDbgBreakOnStatus
0x14004144c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041453  lea     rax, WPP_GLOBAL_Control
0x14004145a  cmp     rcx, rax
0x14004145d  jz      loc_140041581
0x140041463  test    dword ptr [rcx+2Ch], 100h
0x14004146a  jz      loc_140041581
0x140041470  cmp     byte ptr [rcx+29h], 2
0x140041474  jb      loc_140041581
0x14004147a  mov     rax, [rbx]
0x14004147d  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041484  mov     rcx, [rcx+18h]
0x140041488  mov     r9, rbx
0x14004148b  mov     [rsp+88h+var_48], edi
0x14004148f  mov     dword ptr [rsp+88h+var_50], ebp
0x140041493  mov     rdx, [rax]
0x140041496  mov     [rsp+88h+var_58], r14
0x14004149b  mov     [rsp+88h+var_60], r15
0x1400414a0  mov     rax, [rdx+10h]
0x1400414a4  lea     edx, [rsi+3Ch]
0x1400414a7  mov     rax, [rax+20h]
0x1400414ab  mov     [rsp+88h+var_68], rax
0x1400414b0  call    WPP_SF_qiiiLd
0x1400414b5  jmp     loc_140041581
0x1400414ba  mov     rax, [rbx]
0x1400414bd  mov     ebp, 90h
0x1400414c2  mov     rcx, [rax+8]
0x1400414c6  add     rcx, rbp; Cbdq
0x1400414c9  call    CldiStreamCdqACQUIRE
0x1400414ce  cmp     qword ptr [rbx+38h], 0
0x1400414d3  jnz     loc_140041568
0x1400414d9  lea     rcx, [rbx+10h]
0x1400414dd  mov     [rbx+38h], rsi
0x1400414e1  mov     rdx, [rcx+8]
0x1400414e5  cmp     [rdx], rcx
0x1400414e8  jz      short loc_1400414F1
0x1400414ea  mov     ecx, 3
0x1400414ef  int     29h; Win8: RtlFailFast(ecx)
0x1400414f1  lea     rax, [rsi+8]
0x1400414f5  xor     edi, edi
0x1400414f7  mov     [rax], rcx
0x1400414fa  mov     [rax+8], rdx
0x1400414fe  mov     [rdx], rax
0x140041501  mov     [rcx+8], rax
0x140041505  mov     [rsi+160h], rdi
0x14004150c  mov     rcx, [rbx]
0x14004150f  mov     rcx, [rcx]
0x140041512  call    HsmpGetStreamSize
0x140041517  mov     [rsi+168h], rax
0x14004151e  call    cs:__imp_KeEnterCriticalRegion
0x140041525  nop     dword ptr [rax+rax+00h]
0x14004152a  mov     dl, 1; Wait
0x14004152c  lea     rcx, Resource; Resource
0x140041533  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004153a  nop     dword ptr [rax+rax+00h]
0x14004153f  mov     rcx, rsi
0x140041542  call    CldiStreamInsertIntoGlobalRequestListNoLock
0x140041547  lea     rcx, Resource; Resource
0x14004154e  call    cs:__imp_ExReleaseResourceLite
0x140041555  nop     dword ptr [rax+rax+00h]
0x14004155a  call    cs:__imp_KeLeaveCriticalRegion
0x140041561  nop     dword ptr [rax+rax+00h]
0x140041566  jmp     short loc_140041572
0x140041568  mov     rcx, rsi; Entry
0x14004156b  call    CldiStreamDeleteRequest
0x140041570  xor     edi, edi
0x140041572  mov     rcx, [rbx]
0x140041575  mov     rcx, [rcx+8]
0x140041579  add     rcx, rbp; Cbdq
0x14004157c  call    CldiStreamCdqRELEASE
0x140041581  mov     eax, edi
0x140041583  add     rsp, 58h
0x140041587  pop     r15
0x140041589  pop     r14
0x14004158b  pop     rdi
0x14004158c  pop     rsi
0x14004158d  pop     rbp
0x14004158e  pop     rbx
0x14004158f  retn
```
