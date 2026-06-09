# LsapCreateLsaLogonSession(_LUID *,_LSAP_LOGON_SESSION * *)

- ea: `0x18007c5d0`
- end: `0x18007c81d`
- name: `?LsapCreateLsaLogonSession@@YAJPEAU_LUID@@PEAPEAU_LSAP_LOGON_SESSION@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct _LUID *, struct _LSAP_LOGON_SESSION **)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005e150`
- `0x1800cd5f0`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x1800284d4`
- `0x18007c5d0`
- `0x1800b86d0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007c6ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007c6ae`
- `ntdll!RtlDeleteResource` at `0x18007c680`
- `ntdll!RtlDeleteResource` at `0x18007c7ec`
- `ntdll!RtlDeleteResource` at `0x18007c680`
- `ntdll!RtlDeleteResource` at `0x18007c7ec`
- `ntdll!RtlInitializeResource` at `0x18007c644`
- `ntdll!RtlInitializeResource` at `0x18007c644`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007c752`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007c752`
- `ntdll!RtlReleaseResource` at `0x18007c797`
- `ntdll!RtlReleaseResource` at `0x18007c797`
- `ntdll!RtlDeleteCriticalSection` at `0x18007c7fb`
- `ntdll!RtlDeleteCriticalSection` at `0x18007c7fb`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c662`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c662`

## pseudocode

```c
__int64 __fastcall LsapCreateLsaLogonSession(struct _LUID *a1, struct _LSAP_LOGON_SESSION **a2)
{
  __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  struct _LIST_ENTRY near **v6; // rcx
  struct _LIST_ENTRY near *v7; // rax
  void *v9; // rdx
  __int128 v10; // [rsp+40h] [rbp-38h] BYREF

  v10 = 0;
  v4 = LsapAllocate(704);
  *a2 = (struct _LSAP_LOGON_SESSION *)v4;
  if ( !v4 )
    return 3221225495LL;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_05668a43f07036cee45d35059337a059_Traceguids,
      (unsigned int)a1->HighPart,
      a1->LowPart);
  }
  RtlInitializeResource((PRTL_RESOURCE)(v4 + 16));
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 320));
  *(struct _LUID *)(v4 + 112) = *a1;
  GetSystemTimeAsFileTime((LPFILETIME)(v4 + 256));
  *(_QWORD *)&v10 = a1->HighPart;
  *((_QWORD *)&v10 + 1) = a1->LowPart;
  if ( (*((unsigned int (__fastcall **)(void *, __int128 *, __int64, _QWORD, _DWORD))LogonSessionPackage + 4))(
         LogonSessionTable,
         &v10,
         v4,
         0,
         0) )
  {
    v5 = (*(unsigned __int8 *)(v4 + 115)
        + 37
        * (*(unsigned __int8 *)(v4 + 114)
         + 37 * (*(unsigned __int8 *)(v4 + 113) + 37 * ((unsigned __int64)*(unsigned __int8 *)(v4 + 112) + 11623883))))
       % LogonSessionListCount;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&(&LogonSessionListLock)[12 * v5], 1u);
    v6 = &(&LogonSessionList)[2 * (unsigned int)v5];
    v7 = *v6;
    if ( (struct _LIST_ENTRY near **)(*v6)->Blink != v6 )
      __fastfail(3u);
    *(_QWORD *)v4 = v7;
    *(_QWORD *)(v4 + 8) = v6;
    v7->Blink = (struct _LIST_ENTRY *)v4;
    *v6 = (struct _LIST_ENTRY near *)v4;
    ++*((_DWORD *)&LogonSessionCount + v5);
    RtlReleaseResource((PRTL_RESOURCE)&(&LogonSessionListLock)[12 * v5]);
    return 0;
  }
  else
  {
    RtlDeleteResource((PRTL_RESOURCE)(v4 + 16));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 320));
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v4, v9);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x18007c5d0  mov     [rsp+arg_10], rbx
0x18007c5d5  push    rsi
0x18007c5d6  push    rdi
0x18007c5d7  push    r14
0x18007c5d9  sub     rsp, 60h
0x18007c5dd  mov     rax, cs:__security_cookie
0x18007c5e4  xor     rax, rsp
0x18007c5e7  mov     [rsp+78h+var_28], rax
0x18007c5ec  mov     rbx, rdx
0x18007c5ef  mov     rsi, rcx
0x18007c5f2  xorps   xmm0, xmm0
0x18007c5f5  movups  [rsp+78h+var_38], xmm0
0x18007c5fa  mov     ecx, 2C0h
0x18007c5ff  call    LsapAllocate
0x18007c604  mov     rdi, rax
0x18007c607  mov     [rbx], rax
0x18007c60a  test    rax, rax
0x18007c60d  jz      loc_18007C816
0x18007c613  mov     [rsp+78h+var_40], rax
0x18007c618  mov     [rsp+78h+var_48], 0
0x18007c620  lea     rax, WPP_GLOBAL_Control
0x18007c627  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c62e  cmp     rcx, rax
0x18007c631  jz      short loc_18007C640
0x18007c633  test    dword ptr [rcx+1Ch], 800000h
0x18007c63a  jnz     loc_18007C7C4
0x18007c640  lea     rcx, [rdi+10h]; Resource
0x18007c644  call    cs:__imp_RtlInitializeResource
0x18007c64b  nop     dword ptr [rax+rax+00h]
0x18007c650  mov     [rsp+78h+var_48], 1
0x18007c658  lea     r14, [rdi+140h]
0x18007c65f  mov     rcx, r14; CriticalSection
0x18007c662  call    cs:__imp_RtlInitializeCriticalSection
0x18007c669  nop     dword ptr [rax+rax+00h]
0x18007c66e  jmp     short loc_18007C6A0
0x18007c670  cmp     [rsp+78h+var_48], 0
0x18007c675  jz      short loc_18007C68C
0x18007c677  mov     rcx, [rsp+78h+var_40]
0x18007c67c  add     rcx, 10h; Resource
0x18007c680  call    cs:__imp_RtlDeleteResource
0x18007c687  nop     dword ptr [rax+rax+00h]
0x18007c68c  mov     rcx, [rsp+78h+var_40]; struct _RTL_BALANCED_NODE *
0x18007c691  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18007c696  mov     eax, 0C0000017h
0x18007c69b  jmp     loc_18007C7A5
0x18007c6a0  mov     rax, [rsi]
0x18007c6a3  mov     [rdi+70h], rax
0x18007c6a7  lea     rcx, [rdi+100h]; lpSystemTimeAsFileTime
0x18007c6ae  call    cs:__imp_GetSystemTimeAsFileTime
0x18007c6b5  nop     dword ptr [rax+rax+00h]
0x18007c6ba  movsxd  rax, dword ptr [rsi+4]
0x18007c6be  mov     qword ptr [rsp+78h+var_38], rax
0x18007c6c3  mov     eax, [rsi]
0x18007c6c5  mov     qword ptr [rsp+78h+var_38+8], rax
0x18007c6ca  mov     rax, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x18007c6d1  mov     [rsp+78h+var_58], 0
0x18007c6d9  xor     r9d, r9d
0x18007c6dc  mov     r8, rdi
0x18007c6df  lea     rdx, [rsp+78h+var_38]
0x18007c6e4  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x18007c6eb  mov     rax, [rax+20h]
0x18007c6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6f4  test    eax, eax
0x18007c6f6  jz      loc_18007C7E8
0x18007c6fc  movzx   eax, byte ptr [rdi+70h]
0x18007c700  add     rax, 0B15DCBh
0x18007c706  imul    rdx, rax, 25h ; '%'
0x18007c70a  movzx   eax, byte ptr [rdi+71h]
0x18007c70e  add     rdx, rax
0x18007c711  imul    rcx, rdx, 25h ; '%'
0x18007c715  movzx   eax, byte ptr [rdi+72h]
0x18007c719  add     rcx, rax
0x18007c71c  imul    rax, rcx, 25h ; '%'
0x18007c720  movzx   ecx, byte ptr [rdi+73h]
0x18007c724  add     rax, rcx
0x18007c727  mov     ecx, cs:?LogonSessionListCount@@3KA; ulong LogonSessionListCount
0x18007c72d  xor     edx, edx
0x18007c72f  div     rcx
0x18007c732  mov     ebx, edx
0x18007c734  lea     rax, [rbx+rbx*2]
0x18007c738  shl     rax, 5
0x18007c73c  lea     r14, __ImageBase
0x18007c743  lea     rsi, rva ?LogonSessionListLock@@3PAU_RTL_RESOURCE@@A[r14]; _RTL_RESOURCE near * LogonSessionListLock ...
0x18007c74a  add     rsi, rax
0x18007c74d  mov     dl, 1; Wait
0x18007c74f  mov     rcx, rsi; Resource
0x18007c752  call    cs:__imp_RtlAcquireResourceExclusive
0x18007c759  nop     dword ptr [rax+rax+00h]
0x18007c75e  mov     eax, ebx
0x18007c760  shl     rax, 4
0x18007c764  lea     rcx, rva ?LogonSessionList@@3PAU_LIST_ENTRY@@A[r14]; _LIST_ENTRY near * LogonSessionList ...
0x18007c76b  add     rcx, rax
0x18007c76e  mov     rax, [rcx]
0x18007c771  cmp     [rax+8], rcx
0x18007c775  jz      short loc_18007C77E
0x18007c777  mov     ecx, 3
0x18007c77c  int     29h; Win8: RtlFailFast(ecx)
0x18007c77e  mov     [rdi], rax
0x18007c781  mov     [rdi+8], rcx
0x18007c785  mov     [rax+8], rdi
0x18007c789  mov     [rcx], rdi
0x18007c78c  inc     rva ?LogonSessionCount@@3PAKA[r14+rbx*4]; ulong near * LogonSessionCount ...
0x18007c794  mov     rcx, rsi; Resource
0x18007c797  call    cs:__imp_RtlReleaseResource
0x18007c79e  nop     dword ptr [rax+rax+00h]
0x18007c7a3  xor     eax, eax
0x18007c7a5  mov     rcx, [rsp+78h+var_28]
0x18007c7aa  xor     rcx, rsp; StackCookie
0x18007c7ad  call    __security_check_cookie
0x18007c7b2  mov     rbx, [rsp+78h+arg_10]
0x18007c7ba  add     rsp, 60h
0x18007c7be  pop     r14
0x18007c7c0  pop     rdi
0x18007c7c1  pop     rsi
0x18007c7c2  retn
0x18007c7c4  mov     edx, 0Ch
0x18007c7c9  mov     eax, [rsi]
0x18007c7cb  mov     [rsp+78h+var_58], eax
0x18007c7cf  mov     r9d, [rsi+4]
0x18007c7d3  lea     r8, WPP_05668a43f07036cee45d35059337a059_Traceguids
0x18007c7da  mov     rcx, [rcx+10h]
0x18007c7de  call    WPP_SF_Dd
0x18007c7e3  jmp     loc_18007C640
0x18007c7e8  lea     rcx, [rdi+10h]; Resource
0x18007c7ec  call    cs:__imp_RtlDeleteResource
0x18007c7f3  nop     dword ptr [rax+rax+00h]
0x18007c7f8  mov     rcx, r14; CriticalSection
0x18007c7fb  call    cs:__imp_RtlDeleteCriticalSection
0x18007c802  nop     dword ptr [rax+rax+00h]
0x18007c807  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18007c80a  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18007c80f  mov     eax, 0C0000001h
0x18007c814  jmp     short loc_18007C7A5
0x18007c816  mov     eax, 0C0000017h
0x18007c81b  jmp     short loc_18007C7A5
```
