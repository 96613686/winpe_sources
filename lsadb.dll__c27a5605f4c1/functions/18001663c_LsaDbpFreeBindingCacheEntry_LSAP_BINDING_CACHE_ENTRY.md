# LsaDbpFreeBindingCacheEntry(_LSAP_BINDING_CACHE_ENTRY *)

- ea: `0x18001663c`
- end: `0x18001669e`
- name: `?LsaDbpFreeBindingCacheEntry@@YAXPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z`
- size: `98`
- prototype: `void __fastcall(struct _LSAP_BINDING_CACHE_ENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800164a8`
- `0x1800165f0`

## callees

- `0x18001663c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001666b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001666b`
- `LSASRV!LsapFreeString` at `0x18001664d`
- `LSASRV!LsapFreeString` at `0x18001664d`
- `LSASRV!LsapFreeLsaHeap` at `0x180016692`
- `LSASRV!LsapFreeLsaHeap` at `0x180016692`
- `ADVAPI32!LsaClose` at `0x18001665c`
- `ADVAPI32!LsaClose` at `0x18001665c`
- `NETLOGON!I_NetLogonFree` at `0x18001667a`
- `NETLOGON!I_NetLogonFree` at `0x180016689`
- `NETLOGON!I_NetLogonFree` at `0x18001667a`
- `NETLOGON!I_NetLogonFree` at `0x180016689`

## pseudocode

```c
void __fastcall LsaDbpFreeBindingCacheEntry(struct _LSAP_BINDING_CACHE_ENTRY *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  void *v4; // rcx
  void *v5; // rcx

  if ( a1 )
  {
    LsapFreeString((char *)a1 + 32);
    v4 = (void *)*((_QWORD *)a1 + 9);
    if ( v4 )
      LsaClose(v4);
    v5 = (void *)*((_QWORD *)a1 + 6);
    if ( v5 )
      LocalFree(v5);
    if ( *((_QWORD *)a1 + 7) )
      I_NetLogonFree();
    if ( *((_QWORD *)a1 + 8) )
      I_NetLogonFree();
    LsapFreeLsaHeap(a1, v2, v3);
  }
}

```

## disassembly

```asm
0x18001663c  test    rcx, rcx
0x18001663f  jz      short locret_18001669D
0x180016641  push    rbx
0x180016642  sub     rsp, 20h
0x180016646  mov     rbx, rcx
0x180016649  add     rcx, 20h ; ' '
0x18001664d  call    cs:__imp_LsapFreeString
0x180016653  mov     rcx, [rbx+48h]; ObjectHandle
0x180016657  test    rcx, rcx
0x18001665a  jz      short loc_180016662
0x18001665c  call    cs:__imp_LsaClose
0x180016662  mov     rcx, [rbx+30h]; hMem
0x180016666  test    rcx, rcx
0x180016669  jz      short loc_180016671
0x18001666b  call    cs:__imp_LocalFree
0x180016671  mov     rcx, [rbx+38h]
0x180016675  test    rcx, rcx
0x180016678  jz      short loc_180016680
0x18001667a  call    cs:__imp_I_NetLogonFree
0x180016680  mov     rcx, [rbx+40h]
0x180016684  test    rcx, rcx
0x180016687  jz      short loc_18001668F
0x180016689  call    cs:__imp_I_NetLogonFree
0x18001668f  mov     rcx, rbx
0x180016692  call    cs:__imp_LsapFreeLsaHeap
0x180016698  add     rsp, 20h
0x18001669c  pop     rbx
0x18001669d  retn
```
