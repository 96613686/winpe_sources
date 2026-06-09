# _ReleaseUserLockEntry(_USER_LOCK_ENTRY *)

- ea: `0x180032ef8`
- end: `0x180032f77`
- name: `?_ReleaseUserLockEntry@@YAXPEAU_USER_LOCK_ENTRY@@@Z`
- size: `127`
- prototype: `void __fastcall(struct _USER_LOCK_ENTRY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032998`
- `0x18003df0c`

## callees

- `0x180032ef8`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180032f0e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032f0e`
- `ntdll!RtlReleaseResource` at `0x180032f64`
- `ntdll!RtlReleaseResource` at `0x180032f64`
- `ntdll!RtlDeleteResource` at `0x180032f2b`
- `ntdll!RtlDeleteResource` at `0x180032f2b`

## pseudocode

```c
void __fastcall _ReleaseUserLockEntry(struct _USER_LOCK_ENTRY *a1)
{
  __int64 v2; // rax
  struct _USER_LOCK_ENTRY **v3; // rcx

  if ( a1 )
  {
    RtlAcquireResourceExclusive(&g_UserLockList_Lock, 1u);
    _InterlockedDecrement((volatile signed __int32 *)a1 + 4);
    if ( !*((_DWORD *)a1 + 4) )
    {
      if ( *((_DWORD *)a1 + 32) )
        RtlDeleteResource((PRTL_RESOURCE)((char *)a1 + 24));
      v2 = *(_QWORD *)a1;
      if ( *(struct _USER_LOCK_ENTRY **)(*(_QWORD *)a1 + 8LL) != a1
        || (v3 = (struct _USER_LOCK_ENTRY **)*((_QWORD *)a1 + 1), *v3 != a1) )
      {
        __fastfail(3u);
      }
      *v3 = (struct _USER_LOCK_ENTRY *)v2;
      *(_QWORD *)(v2 + 8) = v3;
      ((void (__fastcall *)(struct _USER_LOCK_ENTRY *))g_pLsaFunctionTable->FreeLsaHeap)(a1);
    }
    RtlReleaseResource(&g_UserLockList_Lock);
  }
}

```

## disassembly

```asm
0x180032ef8  test    rcx, rcx
0x180032efb  jz      short locret_180032F6F
0x180032efd  push    rbx
0x180032efe  sub     rsp, 20h
0x180032f02  mov     rbx, rcx
0x180032f05  mov     dl, 1; Wait
0x180032f07  lea     rcx, ?g_UserLockList_Lock@@3U_RTL_RESOURCE@@A; Resource
0x180032f0e  call    cs:__imp_RtlAcquireResourceExclusive
0x180032f14  lock dec dword ptr [rbx+10h]
0x180032f18  cmp     dword ptr [rbx+10h], 0
0x180032f1c  jnz     short loc_180032F5D
0x180032f1e  cmp     dword ptr [rbx+80h], 0
0x180032f25  jz      short loc_180032F31
0x180032f27  lea     rcx, [rbx+18h]; Resource
0x180032f2b  call    cs:__imp_RtlDeleteResource
0x180032f31  mov     rax, [rbx]
0x180032f34  cmp     [rax+8], rbx
0x180032f38  jnz     short loc_180032F70
0x180032f3a  mov     rcx, [rbx+8]
0x180032f3e  cmp     [rcx], rbx
0x180032f41  jnz     short loc_180032F70
0x180032f43  mov     [rcx], rax
0x180032f46  mov     [rax+8], rcx
0x180032f4a  mov     rcx, rbx
0x180032f4d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032f54  mov     rax, [rax+30h]
0x180032f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f5d  lea     rcx, ?g_UserLockList_Lock@@3U_RTL_RESOURCE@@A; Resource
0x180032f64  call    cs:__imp_RtlReleaseResource
0x180032f6a  add     rsp, 20h
0x180032f6e  pop     rbx
0x180032f6f  retn
0x180032f70  mov     ecx, 3
0x180032f75  int     29h; Win8: RtlFailFast(ecx)
```
