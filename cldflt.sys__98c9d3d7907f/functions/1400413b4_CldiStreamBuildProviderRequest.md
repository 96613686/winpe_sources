# CldiStreamBuildProviderRequest

- ea: `0x1400413b4`
- end: `0x140041588`
- name: `CldiStreamBuildProviderRequest`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140074eb0`

## callees

- `0x140003c50`
- `0x14000c960`
- `0x14000ff64`
- `0x140035dc8`
- `0x1400413b4`
- `0x140056650`
- `0x140058cbc`
- `0x140075050`
- `0x1400819ac`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004154c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004154c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041540`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041540`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041525`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041525`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041510`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041510`
- `ntoskrnl!PsGetProcessId` at `0x1400413dc`
- `ntoskrnl!PsGetProcessId` at `0x1400413dc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400413cd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400413cd`

## pseudocode

```c
__int64 __fastcall CldiStreamBuildProviderRequest(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  struct _KPROCESS *CurrentProcess; // rax
  int ProcessId; // eax
  KIRQL *v10; // rdx
  char *Request; // rdi
  unsigned int v12; // esi
  KIRQL v13; // dl
  _QWORD *v14; // rdx

  CurrentProcess = IoGetCurrentProcess();
  ProcessId = (unsigned int)PsGetProcessId(CurrentProcess);
  Request = CldiStreamAllocateRequest(0, a4, ProcessId, (__int64)a1, 1073741825, 0, 0, 0, 1, 0);
  if ( Request )
  {
    CldiStreamCdqACQUIRE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v10);
    if ( !a1[7] )
    {
      a1[7] = Request;
      v14 = (_QWORD *)a1[3];
      if ( (_QWORD *)*v14 != a1 + 2 )
        __fastfail(3u);
      *((_QWORD *)Request + 1) = a1 + 2;
      *((_QWORD *)Request + 2) = v14;
      *v14 = Request + 8;
      a1[3] = Request + 8;
      *((_QWORD *)Request + 44) = 0;
      *((_QWORD *)Request + 45) = HsmpGetStreamSize(*(_QWORD *)*a1);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      CldiStreamInsertIntoGlobalRequestListNoLock(Request);
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      Request = 0;
    }
    v12 = 0;
    CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*a1 + 8LL) + 144LL), v13);
    if ( Request )
      CldiStreamDeleteRequest(Request);
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
0x1400413b4  push    rbx
0x1400413b6  push    rbp
0x1400413b7  push    rsi
0x1400413b8  push    rdi
0x1400413b9  push    r14
0x1400413bb  push    r15
0x1400413bd  sub     rsp, 58h
0x1400413c1  mov     ebp, r9d
0x1400413c4  mov     r14, r8
0x1400413c7  mov     r15, rdx
0x1400413ca  mov     rbx, rcx
0x1400413cd  call    cs:__imp_IoGetCurrentProcess
0x1400413d4  nop     dword ptr [rax+rax+00h]
0x1400413d9  mov     rcx, rax; Process
0x1400413dc  call    cs:__imp_PsGetProcessId
0x1400413e3  nop     dword ptr [rax+rax+00h]
0x1400413e8  mov     [rsp+88h+var_40], 0
0x1400413f1  mov     r9, rbx
0x1400413f4  mov     byte ptr [rsp+88h+var_48], 1
0x1400413f9  mov     r8d, eax
0x1400413fc  mov     [rsp+88h+var_50], 0
0x140041405  mov     edx, ebp
0x140041407  mov     [rsp+88h+var_58], 0
0x140041410  xor     ecx, ecx
0x140041412  mov     [rsp+88h+var_60], 0
0x14004141b  mov     dword ptr [rsp+88h+var_68], 40000001h
0x140041423  call    CldiStreamAllocateRequest
0x140041428  mov     rdi, rax
0x14004142b  test    rax, rax
0x14004142e  jnz     short loc_1400414AA
0x140041430  mov     esi, 0C000009Ah
0x140041435  mov     ecx, esi
0x140041437  call    HsmDbgBreakOnStatus
0x14004143c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041443  lea     rax, WPP_GLOBAL_Control
0x14004144a  cmp     rcx, rax
0x14004144d  jz      loc_140041578
0x140041453  test    dword ptr [rcx+2Ch], 100h
0x14004145a  jz      loc_140041578
0x140041460  cmp     byte ptr [rcx+29h], 2
0x140041464  jb      loc_140041578
0x14004146a  mov     rax, [rbx]
0x14004146d  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041474  mov     rcx, [rcx+18h]
0x140041478  mov     r9, rbx
0x14004147b  mov     [rsp+88h+var_48], esi
0x14004147f  mov     dword ptr [rsp+88h+var_50], ebp
0x140041483  mov     rdx, [rax]
0x140041486  mov     [rsp+88h+var_58], r14
0x14004148b  mov     [rsp+88h+var_60], r15
0x140041490  mov     rax, [rdx+10h]
0x140041494  lea     edx, [rdi+3Ch]
0x140041497  mov     rax, [rax+20h]
0x14004149b  mov     [rsp+88h+var_68], rax
0x1400414a0  call    WPP_SF_qiiiLd
0x1400414a5  jmp     loc_140041578
0x1400414aa  mov     rax, [rbx]
0x1400414ad  mov     ebp, 90h
0x1400414b2  mov     rcx, [rax+8]
0x1400414b6  add     rcx, rbp; Cbdq
0x1400414b9  call    CldiStreamCdqACQUIRE
0x1400414be  cmp     qword ptr [rbx+38h], 0
0x1400414c3  jnz     loc_14004155A
0x1400414c9  lea     rcx, [rbx+10h]
0x1400414cd  mov     [rbx+38h], rdi
0x1400414d1  mov     rdx, [rcx+8]
0x1400414d5  cmp     [rdx], rcx
0x1400414d8  jz      short loc_1400414E1
0x1400414da  mov     ecx, 3
0x1400414df  int     29h; Win8: RtlFailFast(ecx)
0x1400414e1  lea     rax, [rdi+8]
0x1400414e5  mov     [rax], rcx
0x1400414e8  mov     [rax+8], rdx
0x1400414ec  mov     [rdx], rax
0x1400414ef  mov     [rcx+8], rax
0x1400414f3  mov     qword ptr [rdi+160h], 0
0x1400414fe  mov     rcx, [rbx]
0x140041501  mov     rcx, [rcx]
0x140041504  call    HsmpGetStreamSize
0x140041509  mov     [rdi+168h], rax
0x140041510  call    cs:__imp_KeEnterCriticalRegion
0x140041517  nop     dword ptr [rax+rax+00h]
0x14004151c  mov     dl, 1; Wait
0x14004151e  lea     rcx, Resource; Resource
0x140041525  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004152c  nop     dword ptr [rax+rax+00h]
0x140041531  mov     rcx, rdi
0x140041534  call    CldiStreamInsertIntoGlobalRequestListNoLock
0x140041539  lea     rcx, Resource; Resource
0x140041540  call    cs:__imp_ExReleaseResourceLite
0x140041547  nop     dword ptr [rax+rax+00h]
0x14004154c  call    cs:__imp_KeLeaveCriticalRegion
0x140041553  nop     dword ptr [rax+rax+00h]
0x140041558  xor     edi, edi
0x14004155a  mov     rcx, [rbx]
0x14004155d  xor     esi, esi
0x14004155f  mov     rcx, [rcx+8]
0x140041563  add     rcx, rbp; Cbdq
0x140041566  call    CldiStreamCdqRELEASE
0x14004156b  test    rdi, rdi
0x14004156e  jz      short loc_140041578
0x140041570  mov     rcx, rdi; Entry
0x140041573  call    CldiStreamDeleteRequest
0x140041578  mov     eax, esi
0x14004157a  add     rsp, 58h
0x14004157e  pop     r15
0x140041580  pop     r14
0x140041582  pop     rdi
0x140041583  pop     rsi
0x140041584  pop     rbp
0x140041585  pop     rbx
0x140041586  retn
```
