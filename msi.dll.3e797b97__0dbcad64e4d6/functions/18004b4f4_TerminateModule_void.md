# TerminateModule(void)

- ea: `0x18004b4f4`
- end: `0x18004b6a4`
- name: `?TerminateModule@@YAXXZ`
- size: `432`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18004c2f4`

## callees

- `0x18004a014`
- `0x18004b4f4`
- `0x18004b6ac`
- `0x18004b888`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004b55e`
- `KERNEL32!DeleteCriticalSection` at `0x18004b571`
- `KERNEL32!DeleteCriticalSection` at `0x18004b584`
- `KERNEL32!DeleteCriticalSection` at `0x18004b597`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5aa`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5bd`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5d0`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5e3`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5f6`
- `KERNEL32!DeleteCriticalSection` at `0x18004b609`
- `KERNEL32!DeleteCriticalSection` at `0x18004b61c`
- `KERNEL32!DeleteCriticalSection` at `0x18004b62f`
- `KERNEL32!DeleteCriticalSection` at `0x18004b642`
- `KERNEL32!DeleteCriticalSection` at `0x18004b655`
- `KERNEL32!DeleteCriticalSection` at `0x18004b55e`
- `KERNEL32!DeleteCriticalSection` at `0x18004b571`
- `KERNEL32!DeleteCriticalSection` at `0x18004b584`
- `KERNEL32!DeleteCriticalSection` at `0x18004b597`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5aa`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5bd`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5d0`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5e3`
- `KERNEL32!DeleteCriticalSection` at `0x18004b5f6`
- `KERNEL32!DeleteCriticalSection` at `0x18004b609`
- `KERNEL32!DeleteCriticalSection` at `0x18004b61c`
- `KERNEL32!DeleteCriticalSection` at `0x18004b62f`
- `KERNEL32!DeleteCriticalSection` at `0x18004b642`
- `KERNEL32!DeleteCriticalSection` at `0x18004b655`
- `KERNEL32!DeleteCriticalSection` at `0x18004b66c`
- `KERNEL32!GetCurrentThreadId` at `0x18004b500`
- `KERNEL32!GetCurrentThreadId` at `0x18004b500`
- `KERNEL32!TlsFree` at `0x18004b678`
- `KERNEL32!TlsFree` at `0x18004b678`
- `KERNEL32!FreeLibrary` at `0x18004b693`
- `KERNEL32!FreeLibrary` at `0x18004b693`

## pseudocode

```c
void TerminateModule(void)
{
  unsigned __int64 v0; // [rsp+30h] [rbp+8h]

  v0 = GetCurrentThreadId() | 0xFFFFFFFF00000000uLL;
  CheckAllHandlesClosed(0, v0);
  FreeGlobals();
  CAPITempBuffer<unsigned short,1>::Destroy(&off_180310150);
  if ( g_dwImpersonationSlot != -1 )
  {
    TlsFree(g_dwImpersonationSlot);
    g_dwImpersonationSlot = -1;
  }
  if ( g_hMsgInstance )
    FreeLibrary(g_hMsgInstance);
  g_hMsgInstance = 0;
  DeleteCriticalSection(&g_csMessageDll);
  DeleteCriticalSection(&g_csWriteLog);
  DeleteCriticalSection(&g_csImpersonationLock);
  DeleteCriticalSection(&g_csSharedServicesLock);
  DeleteCriticalSection(&g_csRecacheResolveSourceLock);
  DeleteCriticalSection(&g_csThreadImpersonationLock);
  DeleteCriticalSection(&g_csTransactionLock);
  DeleteCriticalSection(&g_csEnumLock);
  DeleteCriticalSection(&g_csPolicyTableLock);
  DeleteCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  DeleteCriticalSection(&g_csLUIDLock);
  DeleteCriticalSection(&g_csEnumStateManagerLock);
  DeleteCriticalSection(&g_csConfigManagerLock);
  DeleteCriticalSection(&g_csServerInterfaceLock);
  DeleteCriticalSection(&CMsiHandle::m_csLock);
}

```

## disassembly

```asm
0x18004b4f4  sub     rsp, 28h
0x18004b4f8  mov     dword ptr [rsp+28h+arg_0+4], 0FFFFFFFFh
0x18004b500  call    cs:__imp_GetCurrentThreadId
0x18004b507  nop     dword ptr [rax+rax+00h]
0x18004b50c  mov     dword ptr [rsp+28h+arg_0], eax
0x18004b510  xor     ecx, ecx
0x18004b512  mov     rdx, [rsp+28h+arg_0]
0x18004b517  call    ?CheckAllHandlesClosed@@YAI_NUUniqueThreadID@@@Z; CheckAllHandlesClosed(bool,UniqueThreadID)
0x18004b51c  call    ?FreeGlobals@@YAXXZ; FreeGlobals(void)
0x18004b521  lea     rcx, off_180310150
0x18004b528  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004b52d  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x18004b533  cmp     ecx, 0FFFFFFFFh
0x18004b536  jnz     loc_18004B678
0x18004b53c  mov     rcx, cs:?g_hMsgInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x18004b543  test    rcx, rcx
0x18004b546  jnz     loc_18004B693
0x18004b54c  lea     rcx, ?g_csMessageDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b553  mov     cs:?g_hMsgInstance@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hMsgInstance
0x18004b55e  call    cs:__imp_DeleteCriticalSection
0x18004b565  nop     dword ptr [rax+rax+00h]
0x18004b56a  lea     rcx, ?g_csWriteLog@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b571  call    cs:__imp_DeleteCriticalSection
0x18004b578  nop     dword ptr [rax+rax+00h]
0x18004b57d  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b584  call    cs:__imp_DeleteCriticalSection
0x18004b58b  nop     dword ptr [rax+rax+00h]
0x18004b590  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b597  call    cs:__imp_DeleteCriticalSection
0x18004b59e  nop     dword ptr [rax+rax+00h]
0x18004b5a3  lea     rcx, ?g_csRecacheResolveSourceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b5aa  call    cs:__imp_DeleteCriticalSection
0x18004b5b1  nop     dword ptr [rax+rax+00h]
0x18004b5b6  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b5bd  call    cs:__imp_DeleteCriticalSection
0x18004b5c4  nop     dword ptr [rax+rax+00h]
0x18004b5c9  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b5d0  call    cs:__imp_DeleteCriticalSection
0x18004b5d7  nop     dword ptr [rax+rax+00h]
0x18004b5dc  lea     rcx, ?g_csEnumLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b5e3  call    cs:__imp_DeleteCriticalSection
0x18004b5ea  nop     dword ptr [rax+rax+00h]
0x18004b5ef  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b5f6  call    cs:__imp_DeleteCriticalSection
0x18004b5fd  nop     dword ptr [rax+rax+00h]
0x18004b602  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b609  call    cs:__imp_DeleteCriticalSection
0x18004b610  nop     dword ptr [rax+rax+00h]
0x18004b615  lea     rcx, ?g_csLUIDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b61c  call    cs:__imp_DeleteCriticalSection
0x18004b623  nop     dword ptr [rax+rax+00h]
0x18004b628  lea     rcx, ?g_csEnumStateManagerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b62f  call    cs:__imp_DeleteCriticalSection
0x18004b636  nop     dword ptr [rax+rax+00h]
0x18004b63b  lea     rcx, ?g_csConfigManagerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b642  call    cs:__imp_DeleteCriticalSection
0x18004b649  nop     dword ptr [rax+rax+00h]
0x18004b64e  lea     rcx, ?g_csServerInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004b655  call    cs:__imp_DeleteCriticalSection
0x18004b65c  nop     dword ptr [rax+rax+00h]
0x18004b661  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CMsiHandle::m_csLock
0x18004b668  add     rsp, 28h
0x18004b66c  jmp     cs:__imp_DeleteCriticalSection
0x18004b678  call    cs:__imp_TlsFree
0x18004b67f  nop     dword ptr [rax+rax+00h]
0x18004b684  mov     cs:?g_dwImpersonationSlot@@3KA, 0FFFFFFFFh; ulong g_dwImpersonationSlot
0x18004b68e  jmp     loc_18004B53C
0x18004b693  call    cs:__imp_FreeLibrary
0x18004b69a  nop     dword ptr [rax+rax+00h]
0x18004b69f  jmp     loc_18004B54C
```
