# FreeClusterCommon(_CLUSTER *,int,int)

- ea: `0x180023bf4`
- end: `0x180023d3d`
- name: `?FreeClusterCommon@@YAXPEAU_CLUSTER@@HH@Z`
- size: `329`
- prototype: `void __fastcall(struct _CLUSTER *, int, int)`
- caller_count: `11`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f650`
- `0x180025650`
- `0x18002a7a0`
- `0x18004b238`
- `0x18004d528`
- `0x1800559c4`
- `0x180057c9c`
- `0x18005c424`
- `0x180063cb0`
- `0x18006c010`
- `0x18008652c`

## callees

- `0x180003320`
- `0x180019b68`
- `0x18001cff4`
- `0x1800236a8`
- `0x180023bf4`
- `0x180023d94`
- `0x180026ae0`
- `0x1800294a0`
- `0x18005f650`
- `0x18009e484`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180023c4d`
- `RPCRT4!RpcBindingFree` at `0x180023c4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023c80`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023c80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023caf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023caf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d2c`

## pseudocode

```c
void __fastcall FreeClusterCommon(struct _CLUSTER *a1, __int64 a2, int a3)
{
  void *v4; // rcx
  void *v5; // rdi
  struct _SEC_WINNT_AUTH_IDENTITY_W *v6; // rcx
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF
  struct _CLUSTER *v8; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( a3 )
    {
      cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v7, (RTL_SRWLOCK *)qword_180124540);
      v8 = a1;
      std::_Hash<std::_Uset_traits<void *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<void *>,0>>::_Erase<void *>(
        &qword_180124550,
        &v8);
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v7);
    }
    if ( *((_QWORD *)a1 + 5) )
      RpcBindingFree((RPC_BINDING_HANDLE *)a1 + 5);
    *((_QWORD *)a1 + 5) = 0;
    FreeObsoleteRpcHandlesEx(a1, 1, 1);
    FreeObsoleteRpcHandlesEx(a1, 1, 0);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
    LocalFree(*((HLOCAL *)a1 + 2));
    LocalFree(*((HLOCAL *)a1 + 3));
    FreeReconnectCandidates(a1);
    v4 = (void *)*((_QWORD *)a1 + 42);
    if ( v4 != (void *)-1LL )
    {
      CloseHandle(v4);
      *((_QWORD *)a1 + 42) = -1;
    }
    if ( *((_DWORD *)a1 + 87) )
    {
      v5 = (void *)*((_QWORD *)a1 + 44);
      if ( v5 )
      {
        std::vector<std::shared_ptr<_CLUSTER>>::_Tidy(*((_QWORD *)a1 + 44));
        operator delete(v5);
      }
      *((_DWORD *)a1 + 87) = 0;
    }
    v6 = (struct _SEC_WINNT_AUTH_IDENTITY_W *)*((_QWORD *)a1 + 45);
    if ( v6 )
    {
      DeleteAuthInfoStrings(v6);
      LocalFree(*((HLOCAL *)a1 + 45));
      *((_QWORD *)a1 + 45) = 0;
    }
    ClRtlRemoveItemQueue(v6, (char *)a1 + 200);
    LocalFree(a1);
  }
}

```

## disassembly

```asm
0x180023bf4  test    rcx, rcx
0x180023bf7  jz      locret_180023D3C
0x180023bfd  mov     [rsp+arg_8], rbx
0x180023c02  push    rdi
0x180023c03  sub     rsp, 30h
0x180023c07  mov     rbx, rcx
0x180023c0a  test    r8d, r8d
0x180023c0d  jz      short loc_180023C40
0x180023c0f  lea     rdx, qword_180124540; struct cxl::NonReentrantRWLock *
0x180023c16  lea     rcx, [rsp+38h+var_18]; this
0x180023c1b  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180023c20  lea     rdx, [rsp+38h+arg_0]
0x180023c25  mov     [rsp+38h+arg_0], rbx
0x180023c2a  lea     rcx, qword_180124550
0x180023c31  call    ??$_Erase@PEAX@?$_Hash@V?$_Uset_traits@PEAXV?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@PEAX@2@$0A@@std@@@std@@AEAA_KAEBQEAX@Z; std::_Hash<std::_Uset_traits<void *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<void *>,0>>::_Erase<void *>(void * const &)
0x180023c36  lea     rcx, [rsp+38h+var_18]
0x180023c3b  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180023c40  lea     rdi, [rbx+28h]
0x180023c44  cmp     qword ptr [rdi], 0
0x180023c48  jz      short loc_180023C53
0x180023c4a  mov     rcx, rdi; Binding
0x180023c4d  call    cs:__imp_RpcBindingFree
0x180023c53  mov     qword ptr [rdi], 0
0x180023c5a  mov     rcx, rbx; struct _CLUSTER *
0x180023c5d  mov     edi, 1
0x180023c62  mov     r8d, edi; int
0x180023c65  mov     edx, edi; int
0x180023c67  call    ?FreeObsoleteRpcHandlesEx@@YAXPEAU_CLUSTER@@HH@Z; FreeObsoleteRpcHandlesEx(_CLUSTER *,int,int)
0x180023c6c  xor     r8d, r8d; int
0x180023c6f  mov     edx, edi; int
0x180023c71  mov     rcx, rbx; struct _CLUSTER *
0x180023c74  call    ?FreeObsoleteRpcHandlesEx@@YAXPEAU_CLUSTER@@HH@Z; FreeObsoleteRpcHandlesEx(_CLUSTER *,int,int)
0x180023c79  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180023c80  call    cs:__imp_DeleteCriticalSection
0x180023c86  mov     rcx, [rbx+10h]; hMem
0x180023c8a  call    cs:__imp_LocalFree
0x180023c90  mov     rcx, [rbx+18h]; hMem
0x180023c94  call    cs:__imp_LocalFree
0x180023c9a  mov     rcx, rbx; struct _CLUSTER *
0x180023c9d  call    ?FreeReconnectCandidates@@YAXPEAU_CLUSTER@@@Z; FreeReconnectCandidates(_CLUSTER *)
0x180023ca2  mov     rcx, [rbx+150h]; hObject
0x180023ca9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023cad  jz      short loc_180023CC0
0x180023caf  call    cs:__imp_CloseHandle
0x180023cb5  mov     qword ptr [rbx+150h], 0FFFFFFFFFFFFFFFFh
0x180023cc0  cmp     dword ptr [rbx+15Ch], 0
0x180023cc7  jz      short loc_180023CF4
0x180023cc9  mov     rdi, [rbx+160h]
0x180023cd0  test    rdi, rdi
0x180023cd3  jz      short loc_180023CEA
0x180023cd5  mov     rcx, rdi
0x180023cd8  call    ?_Tidy@?$vector@V?$shared_ptr@U_CLUSTER@@@std@@V?$allocator@V?$shared_ptr@U_CLUSTER@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<_CLUSTER>>::_Tidy(void)
0x180023cdd  mov     edx, 18h
0x180023ce2  mov     rcx, rdi; Block
0x180023ce5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023cea  mov     dword ptr [rbx+15Ch], 0
0x180023cf4  mov     rcx, [rbx+168h]; struct _SEC_WINNT_AUTH_IDENTITY_W *
0x180023cfb  test    rcx, rcx
0x180023cfe  jz      short loc_180023D1D
0x180023d00  call    ?DeleteAuthInfoStrings@@YAXPEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z; DeleteAuthInfoStrings(_SEC_WINNT_AUTH_IDENTITY_W *)
0x180023d05  mov     rcx, [rbx+168h]; hMem
0x180023d0c  call    cs:__imp_LocalFree
0x180023d12  mov     qword ptr [rbx+168h], 0
0x180023d1d  lea     rdx, [rbx+0C8h]
0x180023d24  call    ClRtlRemoveItemQueue
0x180023d29  mov     rcx, rbx; hMem
0x180023d2c  call    cs:__imp_LocalFree
0x180023d32  mov     rbx, [rsp+38h+arg_8]
0x180023d37  add     rsp, 30h
0x180023d3b  pop     rdi
0x180023d3c  retn
```
