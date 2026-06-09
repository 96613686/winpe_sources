# OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)

- ea: `0x1800529dc`
- end: `0x180052b1c`
- name: `?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z`
- size: `320`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180014594`
- `0x180014b08`
- `0x180016220`
- `0x18001ffc0`
- `0x1800272ec`
- `0x18004a3e4`
- `0x1800532e0`
- `0x180053380`

## callees

- `0x18003c79c`
- `0x180044c70`
- `0x1800529dc`
- `0x1800536d4`
- `0x180053b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800529fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800529fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180052b07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180052b07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052a27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052a27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052a36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052a36`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180052ab3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180052ab3`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180052a76`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180052a76`

## pseudocode

```c
__int64 __fastcall OnQueryStateUpdateStub(int a1, int a2, __int64 a3)
{
  unsigned int v6; // esi
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  struct _SLIST_ENTRY *v9; // rax
  struct _SLIST_ENTRY *v10; // rdi
  signed __int32 v11; // eax
  _BYTE v13[16]; // [rsp+20h] [rbp-78h] BYREF
  int v14; // [rsp+30h] [rbp-68h]
  int v15; // [rsp+40h] [rbp-58h]
  int v16; // [rsp+44h] [rbp-54h]
  __int64 v17; // [rsp+48h] [rbp-50h]
  signed __int32 v18; // [rsp+50h] [rbp-48h]

  v6 = 0;
  v7 = *(_QWORD *)(a3 + 16);
  AcquireSRWLockShared((PSRWLOCK)v7);
  if ( a1 && *(_DWORD *)(v7 + 8) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
    {
      memset_0(v13, 0, 0x40u);
      v14 = 3;
      v15 = a1;
      v16 = a2;
      v17 = a3;
      v18 = _InterlockedIncrement((volatile signed __int32 *)(v7 + 440));
      v6 = CQueryContext::SubmitWorkItem((PSRWLOCK)v7, (const struct _QUERY_WORK_ITEM *)v13);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v9 = (struct _SLIST_ENTRY *)HeapAlloc(ProcessHeap, 0, 0x40u);
      v10 = v9;
      if ( v9 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 452));
        *((_QWORD *)&v9[1].Next + 1) = v7;
        LODWORD(v9[1].Next) = 3;
        LODWORD(v9[2].Next) = a1;
        HIDWORD(v9[2].Next) = a2;
        *((_QWORD *)&v9[2].Next + 1) = a3;
        InterlockedPushEntrySList(g_QueryWorkItemList, v9);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_60814245>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_60814245>::GetImpl'::`2'::impl) )
          v11 = _InterlockedIncrement((volatile signed __int32 *)(v7 + 440));
        else
          v11 = ++*(_DWORD *)(v7 + 440);
        LODWORD(v10[3].Next) = v11;
        SubmitThreadpoolWork(g_QueryThreadpoolWork);
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  ReleaseSRWLockShared((PSRWLOCK)v7);
  return v6;
}

```

## disassembly

```asm
0x1800529dc  push    rbx
0x1800529de  push    rbp
0x1800529df  push    rsi
0x1800529e0  push    rdi
0x1800529e1  push    r14
0x1800529e3  push    r15
0x1800529e5  sub     rsp, 68h
0x1800529e9  mov     rbp, r8
0x1800529ec  mov     r15d, edx
0x1800529ef  mov     r14d, ecx
0x1800529f2  xor     esi, esi
0x1800529f4  mov     rbx, [r8+10h]
0x1800529f8  mov     rcx, rbx; SRWLock
0x1800529fb  call    cs:__imp_AcquireSRWLockShared
0x180052a01  test    r14d, r14d
0x180052a04  jz      loc_180052B04
0x180052a0a  cmp     [rbx+8], esi
0x180052a0d  jz      loc_180052B04
0x180052a13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x180052a1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180052a1f  test    al, al
0x180052a21  jnz     loc_180052ABB
0x180052a27  call    cs:__imp_GetProcessHeap
0x180052a2d  mov     rcx, rax; hHeap
0x180052a30  xor     edx, edx; dwFlags
0x180052a32  lea     r8d, [rsi+40h]; dwBytes
0x180052a36  call    cs:__imp_HeapAlloc
0x180052a3c  mov     rdi, rax
0x180052a3f  test    rax, rax
0x180052a42  jnz     short loc_180052A4E
0x180052a44  mov     esi, 8007000Eh
0x180052a49  jmp     loc_180052B04
0x180052a4e  lock inc dword ptr [rbx+1C4h]
0x180052a55  mov     [rax+18h], rbx
0x180052a59  mov     dword ptr [rax+10h], 3
0x180052a60  mov     [rax+20h], r14d
0x180052a64  mov     [rax+24h], r15d
0x180052a68  mov     [rax+28h], rbp
0x180052a6c  mov     rdx, rdi; ListEntry
0x180052a6f  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180052a76  call    cs:__imp_InterlockedPushEntrySList
0x180052a7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_60814245@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_60814245@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_60814245> `wil::Feature<__WilFeatureTraits_Feature_bugfix_60814245>::GetImpl(void)'::`2'::impl
0x180052a83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_60814245@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_60814245>::__private_IsEnabled(void)
0x180052a88  test    al, al
0x180052a8a  jz      short loc_180052A9D
0x180052a8c  mov     eax, 1
0x180052a91  lock xadd [rbx+1B8h], eax
0x180052a99  inc     eax
0x180052a9b  jmp     short loc_180052AA9
0x180052a9d  inc     dword ptr [rbx+1B8h]
0x180052aa3  mov     eax, [rbx+1B8h]
0x180052aa9  mov     [rdi+30h], eax
0x180052aac  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x180052ab3  call    cs:__imp_SubmitThreadpoolWork
0x180052ab9  jmp     short loc_180052B04
0x180052abb  xor     edx, edx; Val
0x180052abd  lea     r8d, [rdx+40h]; Size
0x180052ac1  lea     rcx, [rsp+98h+var_78]; void *
0x180052ac6  call    memset_0
0x180052acb  mov     [rsp+98h+var_68], 3
0x180052ad3  mov     [rsp+98h+var_58], r14d
0x180052ad8  mov     [rsp+98h+var_54], r15d
0x180052add  mov     [rsp+98h+var_50], rbp
0x180052ae2  mov     eax, 1
0x180052ae7  lock xadd [rbx+1B8h], eax
0x180052aef  inc     eax
0x180052af1  mov     [rsp+98h+var_48], eax
0x180052af5  lea     rdx, [rsp+98h+var_78]; struct _QUERY_WORK_ITEM *
0x180052afa  mov     rcx, rbx; SRWLock
0x180052afd  call    ?SubmitWorkItem@CQueryContext@@IEAAJAEBU_QUERY_WORK_ITEM@@@Z; CQueryContext::SubmitWorkItem(_QUERY_WORK_ITEM const &)
0x180052b02  mov     esi, eax
0x180052b04  mov     rcx, rbx; SRWLock
0x180052b07  call    cs:__imp_ReleaseSRWLockShared
0x180052b0d  mov     eax, esi
0x180052b0f  add     rsp, 68h
0x180052b13  pop     r15
0x180052b15  pop     r14
0x180052b17  pop     rdi
0x180052b18  pop     rsi
0x180052b19  pop     rbp
0x180052b1a  pop     rbx
0x180052b1b  retn
```
